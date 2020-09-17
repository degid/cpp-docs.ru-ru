---
title: _fpieee_flt
ms.date: 04/05/2018
api_name:
- _fpieee_flt
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fpieee_flt
- _fpieee_flt
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
ms.openlocfilehash: c6a77dcba06b58191781900d4e24202c6335cfb8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213571"
---
# <a name="_fpieee_flt"></a>_fpieee_flt

Вызывает определяемый пользователем обработчик исключений и прерываний для исключений IEEE с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
int _fpieee_flt(
   unsigned long excCode,
   struct _EXCEPTION_POINTERS *excInfo,
   int handler(_FPIEEE_RECORD *)
);
```

### <a name="parameters"></a>Параметры

*ексккоде*<br/>
Код исключения.

*ексЦинфо*<br/>
Указатель на структуру сведений об исключении Windows NT.

*обработке*<br/>
Указатель на пользовательскую подпрограмму обработчика исключений и прерываний IEEE.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение **_fpieee_flt** — это значение, возвращаемое *обработчиком*. Как таковая, подпрограмма фильтра IEEE может быть использована в выражении except механизма структурной обработки исключений (SEH).

## <a name="remarks"></a>Примечания

Функция **_fpieee_flt** вызывает определенный пользователем обработчик ловушек для исключений IEEE с плавающей запятой и предоставляет ему все релевантные сведения. Эта подпрограмма выполняет роль фильтра исключений в механизме SEH, который вызывает ваш собственные обработчик исключений IEEE в случае необходимости.

Структура **_FPIEEE_RECORD** , определенная в FPIEEE.h, содержит сведения, относящиеся к исключению IEEE с плавающей точкой. Эта структура передается в определяемый пользователем обработчик ловушек с **_fpieee_flt**.

|Поле _FPIEEE_RECORD|Описание|
|----------------------------|-----------------|
|**RoundingMode**<br/>**Точность**|Эти **`unsigned int`** поля содержат сведения о среде с плавающей запятой в момент возникновения исключения.|
|**Операция**|Это **`unsigned int`** поле указывает тип операции, вызвавшей ловушку. Если тип является сравнением (**_FpCodeCompare**), можно указать одно из специальных **_FPIEEE_COMPARE_RESULT** значений (как определено в FPIEEE.h) в поле **Results. Value** . Тип преобразования (**_FpCodeConvert**) указывает, что ловушка произошла во время операции преобразования с плавающей запятой. Вы можете просмотреть типы **операнд1** и **result** , чтобы определить тип выполняемого преобразования.|
|**Операнд1**<br/>**Операнд2**<br/>**Результат**|Эти **_FPIEEE_VALUE** структуры указывают типы и значения предложенного результата и операндов. Каждая структура содержит следующие поля:<br /><br /> **Операндвалид** — флаг, указывающий, допустимо ли ответное значение.<br />**Format** — тип данных соответствующего значения. Тип формата может быть возвращен даже в том случае, если соответствующее значение недопустимо.<br />**Значение-результат** или значение данных операнда.|
|**Причина**<br/>**Разрешить**<br/>**Состояние**|**_FPIEEE_EXCEPTION_FLAGS** содержит одно битовое поле для каждого типа исключения с плавающей точкой. Имеется соответствие между этими полями и аргументами, используемыми в маске исключения, переданной функции [_controlfp](control87-controlfp-control87-2.md). Точное смысловое значение каждого бита зависит от контекста:<br /><br /> **Причина** — каждый бит набора указывает конкретное возникшее исключение.<br />**Enable** — каждый бит набора указывает, что конкретное исключение в настоящий момент размаскировано.<br />**Состояние** — каждый бит набора указывает, что конкретное исключение находится в состоянии ожидания. Сюда входят исключения, которые не были вызваны, так как они были замаскированы **_controlfp**.|

Отключенные ожидающие исключения вызываются при их включении. Это может привести к неопределенному поведению при использовании **_fpieee_flt** в качестве фильтра исключений. Перед включением исключений для чисел с плавающей запятой обязательно вызывайте функцию [_clearfp](clear87-clearfp.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_fpieee_flt**|\<fpieee.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fpieee.c
// This program demonstrates the implementation of
// a user-defined floating-point exception handler using the
// _fpieee_flt function.

#include <fpieee.h>
#include <excpt.h>
#include <float.h>
#include <stddef.h>

int fpieee_handler( _FPIEEE_RECORD * );

int fpieee_handler( _FPIEEE_RECORD *pieee )
{
   // user-defined ieee trap handler routine:
   // there is one handler for all
   // IEEE exceptions

   // Assume the user wants all invalid
   // operations to return 0.

   if ((pieee->Cause.InvalidOperation) &&
       (pieee->Result.Format == _FpFormatFp32))
   {
        pieee->Result.Value.Fp32Value = 0.0F;

        return EXCEPTION_CONTINUE_EXECUTION;
   }
   else
      return EXCEPTION_EXECUTE_HANDLER;
}

#define _EXC_MASK    \
    _EM_UNDERFLOW  + \
    _EM_OVERFLOW   + \
    _EM_ZERODIVIDE + \
    _EM_INEXACT

int main( void )
{
   // ...

   __try {
      // unmask invalid operation exception
      _controlfp_s(NULL, _EXC_MASK, _MCW_EM);

      // code that may generate
      // fp exceptions goes here
   }
   __except ( _fpieee_flt( GetExceptionCode(),
                GetExceptionInformation(),
                fpieee_handler ) ){

      // code that gets control

      // if fpieee_handler returns
      // EXCEPTION_EXECUTE_HANDLER goes here

   }

   // ...
}
```

## <a name="see-also"></a>См. также раздел

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_control87, _controlfp \_ _control87_2](control87-controlfp-control87-2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
