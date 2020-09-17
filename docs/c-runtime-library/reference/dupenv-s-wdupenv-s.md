---
title: _dupenv_s, _wdupenv_s
ms.date: 4/2/2020
api_name:
- _dupenv_s
- _wdupenv_s
- _o__dupenv_s
- _o__wdupenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
ms.openlocfilehash: 39184eff5db511dfb920782c3e29bf2b0cc9340e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915184"
---
# <a name="_dupenv_s-_wdupenv_s"></a>_dupenv_s, _wdupenv_s

Получает значение из текущей среды.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _dupenv_s(
   char **buffer,
   size_t *numberOfElements,
   const char *varname
);
errno_t _wdupenv_s(
   wchar_t **buffer,
   size_t *numberOfElements,
   const wchar_t *varname
);
```

### <a name="parameters"></a>Параметры

*двойной*<br/>
Буфер для хранения значения переменной.

*numberOfElements*<br/>
Размер *буфера*.

*varname*<br/>
Имя переменной среды.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном выполнении, код ошибки при сбое.

Эти функции проверяют свои параметры. Если *buffer* или *имя_переменной* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **функции устанавливают значение** **еинвал** и возвращают **еинвал**.

Если эти функции не могут выделить достаточно памяти, они устанавливают для *buffer* **значение NULL** , а *numberOfElements* — на 0 и возвращают **еномем**.

## <a name="remarks"></a>Примечания

Функция **_dupenv_s** выполняет поиск в списке переменных среды для *VarName*. Если переменная найдена, **_dupenv_s** выделяет буфер и копирует значение переменной в буфер. Адрес и длина буфера возвращаются в *buffer* и *numberOfElements*. Выделяя сам буфер, **_dupenv_s** предоставляет более удобную альтернативу [getenv_s _wgetenv_s](getenv-s-wgetenv-s.md).

> [!NOTE]
> Ответственность за освобождение памяти путем вызова функции [free](free.md) лежит на вызывающей программе.

Если переменная не найдена, то для параметра *buffer* задано **значение NULL**, *numberOfElements* — 0, а возвращаемое значение равно 0, поскольку эта ситуация не считается ошибкой.

Если вы не заинтересованы в размере буфера, вы можете передать **значение NULL** для *numberOfElements*.

**_dupenv_s** не учитывает регистр в операционной системе Windows. **_dupenv_s** использует копию среды, на которую указывает глобальная переменная **_environ** для доступа к среде. Обсуждение **_environ**см. в примечаниях в [getenv_s _wgetenv_s](getenv-s-wgetenv-s.md) .

Значение в поле *buffer* является копией значения переменной среды; изменение этого действия не влияет на среду. Чтобы изменить значение переменной среды, используйте функцию [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md).

**_wdupenv_s** — это версия **_dupenv_s**для расширенных символов; аргументы **_wdupenv_s** являются строками расширенных символов. **_Wenviron** глобальная переменная — это версия **_environ**для расширенных символов. Дополнительные сведения об **_wenviron**см. в примечаниях в [getenv_s _wgetenv_s](getenv-s-wgetenv-s.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s**|**_dupenv_s**|**_dupenv_s**|**_wdupenv_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_dupenv_s**|\<stdlib.h>|
|**_wdupenv_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_dupenv_s.c
#include  <stdlib.h>

int main( void )
{
   char *pValue;
   size_t len;
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );
   if ( err ) return -1;
   printf( "pathext = %s\n", pValue );
   free( pValue );
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );
   if ( err ) return -1;
   printf( "nonexistentvariable = %s\n", pValue );
   free( pValue ); // It's OK to call free with NULL
}
```

```Output
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl
nonexistentvariable = (null)
```

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Константы среды](../../c-runtime-library/environmental-constants.md)<br/>
[_dupenv_s_dbg, _wdupenv_s_dbg](dupenv-s-dbg-wdupenv-s-dbg.md)<br/>
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>
