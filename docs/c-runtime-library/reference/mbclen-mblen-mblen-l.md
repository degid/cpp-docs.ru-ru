---
title: _mbclen, mblen, _mblen_l, _mbclen_l
description: Описывает функции _mbclen, mblen, _mblen_l и _mbclen_l в библиотеке времени выполнения Microsoft C (CRT).
ms.date: 4/2/2020
api_name:
- _mbclen
- mblen
- _mblen_l
- _mbclen_l
- _o__mbclen
- _o__mbclen_l
- _o__mblen_l
- _o_mblen
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mblen
- ftclen
- _mbclen
- _mbclen_l
- tclen
- _ftclen
- _tclen
- mbclen
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- _mbclen_l function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
ms.openlocfilehash: b004babc9e7c82d25cd52ec036c3061c99b5f367
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914359"
---
# <a name="_mbclen-mblen-_mblen_l-_mbclen_l"></a>_mbclen, mblen, _mblen_l, _mbclen_l

Получает длину многобайтового символа и определяет его допустимость.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
size_t _mbclen(
   const unsigned char *c
);
size_t _mbclen_l(
   unsigned char const* c,
   _locale_t locale
);
int mblen(
   const char *mbstr,
   size_t count
);
int _mblen_l(
   const char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*ц*\
Многобайтовый символ.

*мбстр*\
Адрес последовательности байтов (многобайтовый символ).

*count*\
Число проверяемых байтов.

*языкового стандарта*\
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbclen** и **_mbclen_l** возвращают 1 или 2 в соответствии с длиной многобайтового символа *c*. Функции всегда возвращают значение 1 для UTF-8, независимо от того, является ли *c* многобайтовой. Для **_mbclen**не возвращается ошибка.

Если *мбстр* не **равно NULL**, **mblen** и **_mblen_l** возвращают длину многобайтового символа в байтах. Функции **mblen** и **_mblen_l** правильно работают в кодировке UTF-8 и могут возвращать значение от 1 до 3. Если *мбстр* имеет **значение NULL** (или указывает на широкий символ null), **mblen** и **_mblen_l** возвращают 0. Объект, на который указывает *мбстр* , должен образовывать допустимый многобайтовый символ в первые символы *Count* , или **mblen** , а **_mblen_l** возвращать-1.

## <a name="remarks"></a>Примечания

Функция **_mbclen** возвращает длину многобайтового символа *c*в байтах. Если *c* не указывает на старший байт многобайтового символа (как определено неявным вызовом [_ismbblead](ismbblead-ismbblead-l.md), результат **_mbclen** является непредсказуемым.

**mblen** возвращает длину в байтах *мбстр* , если это допустимый многобайтовый символ. Он также определяет допустимость многобайтовых символов, связанную с кодовой страницей. **mblen** проверяет *число* байтов, содержащихся в *мбстр*, но не более **MB_CUR_MAX** байтов.

На выходное значение влияет параметр категории **LC_CTYPE** языкового стандарта. Версии этих функций без суффикса **_l** используют текущий языковой стандарт для этого поведения, зависящего от языкового стандарта. **_L** версии с суффиксами ведут себя одинаково, но они используют переданный параметр языкового стандарта. Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md) и [locale](../../c-runtime-library/locale.md).

**_mbclen**, **_mblen_l**и **_Mbclen_l** являются специфичными для Майкрософт, а не частью стандартной библиотеки C. Мы не рекомендуем использовать их в том месте, где нужен переносимый код. Для стандартной совместимости C используйте вместо него **mblen** или **мбрлен** .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|Сопоставляется макросу или встраиваемой функции|**_mbclen**|Сопоставляется макросу или встраиваемой функции|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbclen**|\<mbstring.h>|
|**mblen**|\<stdlib.h>|
|**_mblen_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_mblen.c
/* illustrates the behavior of the mblen function
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    int      i;
    char    *pmbc = (char *)malloc( sizeof( char ) );
    wchar_t  wc   = L'a';

    printf( "Convert wide character to multibyte character:\n" );
    wctomb_s( &i, pmbc, sizeof(char), wc );
    printf( "   Characters converted: %u\n", i );
    printf( "   Multibyte character: %x\n\n", *pmbc );

    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );

    pmbc = NULL;
    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );
}
```

```Output
Convert wide character to multibyte character:
   Characters converted: 1
   Multibyte character: 61

Length in bytes of multibyte character 61: 1
Length in bytes of NULL multibyte character 0: 0
```

## <a name="see-also"></a>См. также раздел

[Классификация символов](../../c-runtime-library/character-classification.md)\
[Языкового стандарта](../../c-runtime-library/locale.md)\
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)\
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)\
[мбрлен](mbrlen.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)
