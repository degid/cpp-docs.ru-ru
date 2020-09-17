---
title: _create_locale, _wcreate_locale
ms.date: 4/2/2020
api_name:
- _create_locale
- __create_locale
- _wcreate_locale
- _o__create_locale
- _o__wcreate_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- create_locale
- _create_locale
- __create_locale
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
ms.openlocfilehash: 31bde3d032bdb47d63db5730ba53016de573332c
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912090"
---
# <a name="_create_locale-_wcreate_locale"></a>_create_locale, _wcreate_locale

Создает объект языкового стандарта.

## <a name="syntax"></a>Синтаксис

```C
_locale_t _create_locale(
   int category,
   const char *locale
);
_locale_t _wcreate_locale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>Параметры

*category*<br/>
Категория.

*locale*<br/>
Указатель языкового стандарта.

## <a name="return-value"></a>Возвращаемое значение

Если *заданы* допустимые *язык и региональные стандарты* , возвращает указанные параметры языкового стандарта в виде объекта **_locale_t** . Текущие параметры языкового стандарта программы не изменяются.

## <a name="remarks"></a>Примечания

Функция **_create_locale** позволяет создать объект, представляющий определенные параметры определенного региона, для использования в версиях многих функций CRT, зависящих от локали (функции с суффиксом **_l** ). Поведение аналогично **setlocale**, за исключением того, что вместо применения указанных параметров языкового стандарта к текущей среде параметры сохраняются в возвращаемой структуре **_locale_t** . Структура **_locale_t** должна быть освобождена с помощью [_free_locale](free-locale.md) , если она больше не нужна.

**_wcreate_locale** — это версия **_create_locale**для расширенных символов; Аргумент *locale* для **_wcreate_locale** является строкой расширенных символов. в противном случае **_wcreate_locale** и **_create_locale** ведут себя одинаково.

Аргумент *Category* указывает, какие части поведения зависит от языкового стандарта. Флаги, используемые для *категории* и частей программы, на которые они влияют, представлены в следующей таблице:

| флаг *категории* | Область применения |
|-----------------|---------|
| **LC_ALL** |Все категории, перечисленные ниже. |
| **LC_COLLATE** |Функции **strcoll**, **_stricoll**, **вксколл**, **_wcsicoll**, **стрксфрм**, **_strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**и **вксксфрм** . |
| **LC_CTYPE** | Функции обработки символов (кроме **знаков** **isxdigit**, **функции mbstowcs**и **mbtowc**, которые не затрагиваются). |
| **LC_MONETARY** | Сведения о денежном форматировании, возвращаемые функцией **localeconv** . |
| **LC_NUMERIC** | Символ десятичной запятой для отформатированных выходных подпрограмм (например, **printf**), для подпрограмм преобразования данных и для сведений о неденежном форматировании, возвращаемых функцией **localeconv**. В дополнение к символу десятичной запятой, **LC_NUMERIC** задает разделитель групп разрядов и строку управления группированием, возвращаемую функцией [localeconv](localeconv.md). |
| **LC_TIME** | Функции **strftime** и **wcsftime** . |

Эта функция проверяет параметры *категории* и *языкового стандарта* . Если параметр category не является одним из значений, указанных в предыдущей таблице, или если *языковой стандарт* равен **null**, функция возвращает **значение NULL**.

Аргумент *locale* является указателем на строку, указывающую языковой стандарт. Дополнительные сведения о формате аргумента *языкового стандарта* см. в разделе [языковые имена, языки и строки страны или региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).

Аргумент *locale* может принимать имя локали, строку языка, языковую строку и код страны или региона, кодовую страницу, языковую строку, код страны или региона и кодовую страницу. Набор доступных имен языковых стандартов, языков, кодов стран и регионов, а также кодовых страниц включает все, что поддерживается API NLS Windows. Набор имен языков, поддерживаемых **_create_locale** , описан в разделе [имена языков, языков и строк страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Набор строк языка и страны или региона, поддерживаемых **_create_locale** , указан в [строках языка](../../c-runtime-library/language-strings.md) и [строках страны или региона](../../c-runtime-library/country-region-strings.md).

Дополнительные сведения о региональных параметрах см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md).

Предыдущее имя этой функции, **__create_locale** (с двумя символами подчеркивания в начале), является устаревшим.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_create_locale**|\<locale.h>|
|**_wcreate_locale**|\<locale.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_create_locale.c
// Sets the current locale to "de-CH" using the
// setlocale function and demonstrates its effect on the strftime
// function.

#include <stdio.h>
#include <locale.h>
#include <time.h>

int main(void)
{
    time_t ltime;
    struct tm thetime;
    unsigned char str[100];
    _locale_t locale;

    // Create a locale object representing the German (Switzerland) locale
    locale = _create_locale(LC_ALL, "de-CH");
    time (&ltime);
    _gmtime64_s(&thetime, &ltime);

    // %#x is the long date representation, appropriate to
    // the current locale
    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In de-CH locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);

    // Create a locale object representing the default C locale
    locale = _create_locale(LC_ALL, "C");
    time(&ltime);
    _gmtime64_s(&thetime, &ltime);

    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In 'C' locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);
}
```

```Output
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'
```

## <a name="see-also"></a>См. также раздел

[Имена языковых стандартов, языки и строки страны или региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Language Strings](../../c-runtime-library/language-strings.md)<br/>
[строки страны и региона](../../c-runtime-library/country-region-strings.md)<br/>
[_free_locale](free-locale.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strcoll Functions](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
