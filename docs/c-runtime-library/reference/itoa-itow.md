---
title: _itoa, функции _itow
description: Справочник по API для _itoa и _itow; , который преобразует целое число в строку.
ms.date: 4/2/2020
api_name:
- itoa
- _itoa
- ltoa
- _ltoa
- ultoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- _o__i64toa
- _o__i64tow
- _o__itoa
- _o__itow
- _o__ltoa
- _o__ltow
- _o__ui64toa
- _o__ui64tow
- _o__ultoa
- _o__ultow
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
- api-ms-win-crt-convert-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _itoa
- _ltoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- itoa
- ltoa
- ultoa
- i64toa
- ui64toa
- itow
- ltow
- ultow
- i64tow
- ui64tow
- itot
- _itot
- ltot
- _ltot
- ultot
- _ultot
- i64tot
- _i64tot
- ui64tot
- _ui64tot
- _MAX_ITOSTR_BASE16_COUNT
- _MAX_ITOSTR_BASE10_COUNT
- _MAX_ITOSTR_BASE8_COUNT
- _MAX_ITOSTR_BASE2_COUNT
- _MAX_LTOSTR_BASE16_COUNT
- _MAX_LTOSTR_BASE10_COUNT
- _MAX_LTOSTR_BASE8_COUNT
- _MAX_LTOSTR_BASE2_COUNT
- _MAX_ULTOSTR_BASE16_COUNT
- _MAX_ULTOSTR_BASE10_COUNT
- _MAX_ULTOSTR_BASE8_COUNT
- _MAX_ULTOSTR_BASE2_COUNT
- _MAX_I64TOSTR_BASE16_COUNT
- _MAX_I64TOSTR_BASE10_COUNT
- _MAX_I64TOSTR_BASE8_COUNT
- _MAX_I64TOSTR_BASE2_COUNT
- _MAX_U64TOSTR_BASE16_COUNT
- _MAX_U64TOSTR_BASE10_COUNT
- _MAX_U64TOSTR_BASE8_COUNT
- _MAX_U64TOSTR_BASE2_COUNT
helpviewer_keywords:
- _itot function
- ui64toa function
- _ui64toa function
- converting integers
- itot function
- _i64tow function
- _i64toa function
- _itow function
- ui64tow function
- integers, converting
- itoa function
- _ui64tow function
- i64tow function
- itow function
- i64toa function
- converting numbers, to strings
- _itoa function
ms.assetid: 46592a00-77bb-4e73-98c0-bf629d96cea6
ms.openlocfilehash: c8d64dcc1efdb9371feb98d8674a7a2c41c7ab3a
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555467"
---
# <a name="itoa-_itoa-ltoa-_ltoa-ultoa-_ultoa-_i64toa-_ui64toa-_itow-_ltow-_ultow-_i64tow-_ui64tow"></a>itoa, _itoa, ltoa, _ltoa, ultoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, _ultow, _i64tow, _ui64tow

Преобразует целое число в строку. Доступны более безопасные версии этих функций, см. [_itoa_s _itow_s функции](itoa-s-itow-s.md).

## <a name="syntax"></a>Синтаксис

```C
char * _itoa( int value, char *buffer, int radix );
char * _ltoa( long value, char *buffer, int radix );
char * _ultoa( unsigned long value, char *buffer, int radix );
char * _i64toa( long long value, char *buffer, int radix );
char * _ui64toa( unsigned long long value, char *buffer, int radix );

wchar_t * _itow( int value, wchar_t *buffer, int radix );
wchar_t * _ltow( long value, wchar_t *buffer, int radix );
wchar_t * _ultow( unsigned long value, wchar_t *buffer, int radix );
wchar_t * _i64tow( long long value, wchar_t *buffer, int radix );
wchar_t * _ui64tow( unsigned long long value, wchar_t *buffer, int radix );

// These POSIX versions of the functions have deprecated names:
char * itoa( int value, char *buffer, int radix );
char * ltoa( long value, char *buffer, int radix );
char * ultoa( unsigned long value, char *buffer, int radix );

// The following template functions are C++ only:
template <size_t size>
char *_itoa( int value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( long value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( unsigned long value, char (&buffer)[size], int radix );

template <size_t size>
char *_i64toa( long long value, char (&buffer)[size], int radix );

template <size_t size>
char * _ui64toa( unsigned long long value, char (&buffer)[size], int radix );

template <size_t size>
wchar_t * _itow( int value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ltow( long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ultow( unsigned long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _i64tow( long long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ui64tow( unsigned long long value, wchar_t (&buffer)[size],
   int radix );
```

### <a name="parameters"></a>Параметры

*value*<br/>
Число, которое требуется преобразовать.

*двойной*<br/>
Буфер, содержащий результат преобразования.

*основание системы счисления*<br/>
Основание, используемое для преобразования *значения*, которое должно находиться в диапазоне 2-36.

*size*<br/>
Длина буфера в единицах символьного типа. Этот параметр выводится из аргумента *buffer* в C++.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на *буфер*. Ошибки не возвращаются.

## <a name="remarks"></a>Примечания

Функции **_itoa**, **_ltoa**, **_ultoa**, **_i64toa**и **_ui64toa** преобразуют цифры заданного аргумента *значения* в строку символов, заканчивающуюся нулем, и сохраняют результат (до 33 символов для **_itoa**, **_ltoa**и **_ultoa**и 65 для **_i64toa** и **_ui64toa**) в *буфере*. Если *основание системы счисления* равно 10, а *значение* отрицательное, то первым символом хранимой строки будет знак "минус" ( **-** ). Функции **_itow**, **_ltow**, **_ultow**, **_i64tow**и **_ui64tow** — это версии **_itoa**, **_ltoa**, **_ultoa**, **_i64toa**и **_ui64toa**для расширенных символов соответственно.

> [!IMPORTANT]
> Эти функции могут записывать после конца буфера, который слишком мал. Чтобы предотвратить переполнение буфера, убедитесь, что *буфер* достаточно велик, чтобы вместить преобразованные цифры, а также завершающий символ NULL и знак подписывания. Неправильное использование этих функций может привести к серьезным проблемам безопасности в коде.

Из-за возможных проблем безопасности эти функции по умолчанию приводят к нерекомендуемому предупреждению [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) **. Эта функция или переменная может быть ненадежной. Вместо этого рекомендуется использовать** *safe_function* **. Чтобы отключить функцию устаревания, используйте _CRT_SECURE_NO_WARNINGS.** Мы рекомендуем изменить исходный код так, чтобы он использовал *safe_function* , предлагаемый предупреждающим сообщением. Более безопасные функции не записывают больше символов, чем заданный размер буфера. Дополнительные сведения см. в разделе [функции _itoa_s, _itow_s](itoa-s-itow-s.md).

Чтобы использовать эти функции без предупреждения об устаревании, определите **_CRT_SECURE_NO_WARNINGS** макрос препроцессора перед включением всех заголовков CRT. Это можно сделать из командной строки в командной строке разработчика, добавив параметр компилятора **/D_CRT_SECURE_NO_WARNINGS** в команду **CL** . В противном случае определите макрос в исходных файлах. При использовании предварительно скомпилированных заголовков определите макрос в верхней части предкомпилированного заголовка include File, *PCH.h* (*stdafx.h* в Visual Studio 2017 и более ранних версиях). Чтобы определить макрос в исходном коде, используйте директиву **#define** перед включением любого заголовка CRT, как показано в следующем примере:

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

В C++ эти функции имеют шаблонные перегрузки, которые вызывают их более безопасные аналоги. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Имена POSIX **Итоа**, **лтоа**и **ултоа** существуют в качестве псевдонимов для функций **_itoa**, **_ltoa**и **_ultoa** . Имена POSIX являются устаревшими, так как они не соответствуют соглашениям об именах глобальных функций, связанных с реализацией ISO C. По умолчанию эти функции приводят к нерекомендуемому предупреждению [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **имя POSIX для этого элемента является устаревшим. Вместо этого используйте имя, соответствующее стандарту ISO C и C++:** *new_name*. Мы рекомендуем изменить исходный код, чтобы использовать более безопасные версии этих функций, **_itoa_s**, **_ltoa_s**или **_ultoa_s**. Дополнительные сведения см. в разделе [функции _itoa_s, _itow_s](itoa-s-itow-s.md).

Для переносимости исходного кода можно хранить имена POSIX в коде. Чтобы использовать эти функции без предупреждения об устаревании, определите и **_CRT_NONSTDC_NO_WARNINGS** , и **_CRT_SECURE_NO_WARNINGS** макросы препроцессора перед включением всех заголовков CRT. Это можно сделать из командной строки в командной строке разработчика, добавив параметры компилятора **/D_CRT_SECURE_NO_WARNINGS** и **/D_CRT_NONSTDC_NO_WARNINGS** в команду **CL** . В противном случае определите макросы в исходных файлах. При использовании предварительно скомпилированных заголовков определите макросы в верхней части файла, включаемого в предкомпилированный заголовок. Чтобы определить макросы в исходном коде, используйте директивы **#define** перед включением любого заголовка CRT, как показано в следующем примере:

```C
#define _CRT_NONSTDC_NO_WARNINGS 1
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

### <a name="maximum-conversion-count-macros"></a>Макрос максимального числа преобразований

Чтобы облегчить создание безопасных буферов для преобразований, CRT включает некоторые удобные макросы. Они определяют размер буфера, необходимого для преобразования наибольшего возможного значения каждого целочисленного типа, включая завершающий символ NULL и знак подписывания, для нескольких распространенных базовых типов. Чтобы гарантировать, что буфер преобразования достаточен для получения любого преобразования в базе, указанной в системе *счисления*, используйте один из этих определенных макросов при выделении буфера. Это помогает предотвратить ошибки переполнения буфера при преобразовании целочисленных типов в строки. Эти макросы определяются при включении stdlib.h или WCHAR.h в источнике.

Чтобы использовать один из этих макросов в функции преобразования строк, объявите буфер преобразования соответствующего символьного типа и используйте значение макроса для целочисленного типа и Base в качестве измерения буфера. В этой таблице перечислены макросы, подходящие для каждой функции в перечисленных базовых базах:

|Функции|radix|Макросы|
|-|-|-|
|**_itoa**, **_itow**|16<br/>10<br/>8<br/>2|**_MAX_ITOSTR_BASE16_COUNT**<br/>**_MAX_ITOSTR_BASE10_COUNT**<br/>**_MAX_ITOSTR_BASE8_COUNT**<br/>**_MAX_ITOSTR_BASE2_COUNT**|
|**_ltoa**, **_ltow**|16<br/>10<br/>8<br/>2|**_MAX_LTOSTR_BASE16_COUNT**<br/>**_MAX_LTOSTR_BASE10_COUNT**<br/>**_MAX_LTOSTR_BASE8_COUNT**<br/>**_MAX_LTOSTR_BASE2_COUNT**|
|**_ultoa**, **_ultow**|16<br/>10<br/>8<br/>2|**_MAX_ULTOSTR_BASE16_COUNT**<br/>**_MAX_ULTOSTR_BASE10_COUNT**<br/>**_MAX_ULTOSTR_BASE8_COUNT**<br/>**_MAX_ULTOSTR_BASE2_COUNT**|
|**_i64toa**, **_i64tow**|16<br/>10<br/>8<br/>2|**_MAX_I64TOSTR_BASE16_COUNT**<br/>**_MAX_I64TOSTR_BASE10_COUNT**<br/>**_MAX_I64TOSTR_BASE8_COUNT**<br/>**_MAX_I64TOSTR_BASE2_COUNT**|
|**_ui64toa**, **_ui64tow**|16<br/>10<br/>8<br/>2|**_MAX_U64TOSTR_BASE16_COUNT**<br/>**_MAX_U64TOSTR_BASE10_COUNT**<br/>**_MAX_U64TOSTR_BASE8_COUNT**<br/>**_MAX_U64TOSTR_BASE2_COUNT**|

В этом примере используется макрос счетчика преобразования для определения буфера, достаточного для размещения **`unsigned long long`** в базовом 2:

```cpp
#include <wchar.h>
#include <iostream>
int main()
{
    wchar_t buffer[_MAX_U64TOSTR_BASE2_COUNT];
    std:wcout << _ui64tow(0xFFFFFFFFFFFFFFFFull, buffer, 2) << std::endl;
}
```

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_itot**|**_itoa**|**_itoa**|**_itow**|
|**_ltot**|**_ltoa**|**_ltoa**|**_ltow**|
|**_ultot**|**_ultoa**|**_ultoa**|**_ultow**|
|**_i64tot**|**_i64toa**|**_i64toa**|**_i64tow**|
|**_ui64tot**|**_ui64toa**|**_ui64toa**|**_ui64tow**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**Итоа**, **лтоа**, **ултоа**|\<stdlib.h>|
|**_itoa**, **_ltoa**, **_ultoa**, **_i64toa**, **_ui64toa**|\<stdlib.h>|
|**_itow**, **_ltow**, **_ultow**, **_i64tow**, **_ui64tow**|\<stdlib.h> или \<wchar.h>|

Эти функции и макросы относятся только к Microsoft. Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

В этом примере демонстрируется использование некоторых целочисленных функций преобразования. Обратите внимание на использование макроса **_CRT_SECURE_NO_WARNINGS** для предупреждения C4996.

```C
// crt_itoa.c
// Compile by using: cl /W4 crt_itoa.c
// This program makes use of the _itoa functions
// in various examples.

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>      // for printf
#include <string.h>     // for strnlen
#include <stdlib.h>     // for _countof, _itoa fns, _MAX_COUNT macros

int main(void)
{
    char buffer[_MAX_U64TOSTR_BASE2_COUNT];
    int r;

    for (r = 10; r >= 2; --r)
    {
        _itoa(-1, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _i64toa(-1LL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _ui64toa(0xffffffffffffffffULL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
}
```

```Output
base 10: -1 (2 chars)
base 9: 12068657453 (11 chars)
base 8: 37777777777 (11 chars)
base 7: 211301422353 (12 chars)
base 6: 1550104015503 (13 chars)
base 5: 32244002423140 (14 chars)
base 4: 3333333333333333 (16 chars)
base 3: 102002022201221111210 (21 chars)
base 2: 11111111111111111111111111111111 (32 chars)

base 10: -1 (2 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)

base 10: 18446744073709551615 (20 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)
```

## <a name="see-also"></a>Дополнительно

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[_itoa_s, функции _itow_s](itoa-s-itow-s.md)<br/>
