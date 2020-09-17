---
title: _controlfp_s
ms.date: 4/2/2020
api_name:
- _controlfp_s
- _o__controlfp_s
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- controlfp_s
- _controlfp_s
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
ms.openlocfilehash: 0e734a0286ac21ed0883cc10b0cd4ee5857ba448
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917267"
---
# <a name="_controlfp_s"></a>_controlfp_s

Возвращает и задает управляющее слово блока операций с плавающей запятой. Это версия функции [_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _controlfp_s(
    unsigned int *currentControl,
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>Параметры

*куррентконтрол*<br/>
Значения битов в текущем управляющем слове.

*невконтрол*<br/>
Значения битов в новом управляющем слове.

*маска*<br/>
Маска для установки битов нового управляющего слова.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном **выполнении или код ошибки значения "** nКод".

## <a name="remarks"></a>Примечания

Функция **_controlfp_s** — это независимая от платформы и более безопасная версия **_control87**, которая получает управляющее слово с плавающей запятой в адрес, хранящийся в *куррентконтрол* , и задает его с помощью *невконтрол*. Биты в значениях показывают состояние элемента управления блоком операций с плавающей запятой. Состояние элемента управления блока операций с плавающей запятой позволяет программе изменять режимы точности, округления и бесконечности в пакете математических операций с числами с плавающей запятой в зависимости от платформы. Кроме того, **_controlfp_s** можно использовать для маскирования или раскрытия исключений с плавающей запятой.

Если значение параметра *Mask* равно 0, **_controlfp_s** получает управляющее слово с плавающей запятой и сохраняет полученное значение в *куррентконтрол*.

Если параметр *Mask* имеет ненулевое значение, то для него задаются новые значения. для любого установленного бита (то есть равного 1) в *маске*соответствующий бит *New* используется для обновления управляющего слова. Иными словами, *фпкнтрл* = ((*фпкнтрл* & ~*Mask*) &#124; (*невконтрол* & *Маска*)), где *фпкнтрл* — это управляющее слово с плавающей запятой. В этом сценарии для *куррентконтрол* задается значение после завершения изменения. Это не старое битовое значение Control-Word.

> [!NOTE]
> По умолчанию библиотеки времени выполнения маскируют все исключения для операций с плавающей запятой .

**_controlfp_s** практически идентично функции **_control87** на платформах Intel (x86), x64 и ARM. Если вы нацелены на платформы x86, x64 или ARM, можно использовать **_control87** или **_controlfp_s**.

Различие между **_control87** и **_controlfp_s** заключается в том, как они воспринимают ненормальные значения. Для платформ Intel (x86), x64 и ARM **_control87** может устанавливать и очищать маску исключения денормализованного операнда. **_controlfp_s** не изменяет маску исключения денормализованного операнда. В следующем примере показано это различие.

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call.
unsigned int current_word = 0;
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged.
```

Возможные значения константы маски (*маски*) и новых значений элементов управления (*невконтрол*) показаны в следующей таблице шестнадцатеричных значений. Используйте перечисленные ниже переносимые константы (**_MCW_EM**, **_EM_INVALID**и т. д.) в качестве аргументов для этих функций вместо явного предоставления шестнадцатеричных значений.

Платформы на основе Intel (x86) аппаратно поддерживают входные и выходные значения DENORMAL. В случае x86 значения DENORMAL сохраняются. Платформа ARM и платформы x64 с поддержкой SSE2 позволяют использовать ненормальные операнды и результаты для очистки или принудительно применяют к нулю. Функции **_controlfp_s**, **_controlfp**и **_control87** предоставляют маску для изменения этого поведения. В следующем примере показано использование этой маски:

```C
unsigned int current_word = 0;
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

На платформах ARM функция **_controlfp_s** применяется к регистру регистра fpscr. В архитектурах x64 затрагивается только управляющее слово SSE2, хранящееся в регистре МКСКСР. На платформах Intel (x86) **_controlfp_s** влияет на управляющие слова как для x87, так и для SSE2, если они есть. Два управляющих слова могут быть несовместимыми друг с другом (из-за предыдущего вызова [__control87_2](control87-controlfp-control87-2.md), например); Если между двумя управляющими словами существует несоответствие, **_controlfp_s** устанавливает флаг **EM_AMBIGUOUS** в *куррентконтрол*. Это предупреждение о том, что возвращенное управляющее слово может неточно представлять состояние обоих управляющих слов блоков операций с плавающей запятой.

В архитектурах ARM и x64 изменение режима бесконечности или точности с плавающей запятой не поддерживается. Если на платформе x64 используется маска контроля точности, функция создает утверждение и вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

Если маска задана неправильно, эта функция создает исключение недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **еинвал** и **устанавливает значение** переводится в **еинвал**.

Эта функция игнорируется, если для компиляции используется [/CLR (компиляция среды CLR)](../../build/reference/clr-common-language-runtime-compilation.md) , так как среда CLR поддерживает только точность с плавающей запятой по умолчанию.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="mask-constants-and-values"></a>Константы и значения маски

Для маски **_MCW_EM** очистка задает исключение, которое позволяет устранить аппаратное исключение. Этот параметр скрывает исключение. Если происходит **_EM_UNDERFLOW** или **_EM_OVERFLOW** , аппаратное исключение не создается до тех пор, пока не будет выполнена следующая инструкция с плавающей запятой. Чтобы создать исключение оборудования сразу после **_EM_UNDERFLOW** или **_EM_OVERFLOW**, вызовите инструкцию MASM фваит.

|Mask|Шестнадцатеричное значение|Константа|Шестнадцатеричное значение|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (нормальное управление)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (маска исключения прерывания)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (контроль бесконечности)<br /><br /> (Не поддерживается на платформах ARM или x64.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (элемент управления округлением)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (Управление точностью)<br /><br /> (Не поддерживается на платформах ARM или x64.)|0x00030000|**_PC_24** (24 бита)<br /><br /> **_PC_53** (53 бит)<br /><br /> **_PC_64** (64 бит)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_controlfp_s**|\<float.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_contrlfp_s.c
// processor: x86
// This program uses _controlfp_s to output the FP control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word;
    int err;

    // Show original FP control word and do calculation.
    err = _controlfp_s(&control_word, 0, 0);
    if ( err ) /* handle error here */;

    printf( "Original: 0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    err = _controlfp_s(&control_word, _PC_24, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "24-bit:   0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    err = _controlfp_s(&control_word, _CW_DEFAULT, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "Default:  0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x9001f
0.1 * 0.1 = 1.000000000000000e-002
24-bit:   0xa001f
0.1 * 0.1 = 9.999999776482582e-003
Default:  0x9001f
0.1 * 0.1 = 1.000000000000000e-002
```

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_control87, _controlfp \__control87_2](control87-controlfp-control87-2.md)<br/>
