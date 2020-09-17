---
title: strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l
ms.date: 4/2/2020
api_name:
- _wcstok_s_l
- _mbstok_s_l
- _mbstok_s
- strtok_s
- wcstok_s
- _strtok_s_l
- _o__mbstok_s
- _o__mbstok_s_l
- _o_strtok_s
- _o_wcstok_s
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcstok_s_l
- _wcstok_s_l
- _tcstok_s
- _mbstok_s_l
- strtok_s
- wcstok_s
- _mbstok_s
- _strtok_s_l
helpviewer_keywords:
- _strtok_s_l function
- _mbstok_s_l function
- strings [C++], searching
- mbstok_s_l function
- wcstok_s_l function
- _wcstok_s_l function
- _tcstok_s function
- _tcstok_s_l function
- strtok_s_l function
- wcstok_s function
- tokens, finding in strings
- mbstok_s function
- _mbstok_s function
- strtok_s function
ms.assetid: 7696c972-f83b-4617-8c82-95973e9fdb46
ms.openlocfilehash: 52c998f14fee080efc1d288abbba012752757632
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912669"
---
# <a name="strtok_s-_strtok_s_l-wcstok_s-_wcstok_s_l-_mbstok_s-_mbstok_s_l"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l

Находит следующий токен в строке с использованием текущего или переданного языкового стандарта. Эти версии [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) отличаются повышенной безопасностью (см. раздел [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md)).

> [!IMPORTANT]
> **_mbstok_s** и **_mbstok_s_l** нельзя использовать в приложениях, которые выполняются в среда выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char* strtok_s(
   char* str,
   const char* delimiters,
   char** context
);

char* _strtok_s_l(
   char* str,
   const char* delimiters,
   char** context,
   _locale_t locale
);

wchar_t* wcstok_s(
   wchar_t* str,
   const wchar_t* delimiters,
   wchar_t** context
);

wchar_t *_wcstok_s_l(
   wchar_t* str,
   const wchar_t* delimiters,
   wchar_t** context,
   _locale_t locale
);

unsigned char* _mbstok_s(
   unsigned char* str,
   const unsigned char* delimiters,
   char** context
);

unsigned char* _mbstok_s_l(
   unsigned char* str,
   const unsigned char* delimiters,
   char** context,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Строка, содержащая токен или токены для поиска.

*разделители*<br/>
Набор символов разделителя для использования.

*context*<br/>
Используется для хранения сведений о положении между вызовами функции.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на следующий токен, найденный в *str*. Возвращает **значение NULL** , если больше не найдено маркеров. Каждый вызов изменяет функцию *str* , подставляя символ NULL для первого разделителя, который происходит после возвращаемого маркера.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*str*|*разделители*|*context*|Возвращаемое значение|**errno**|
|----------------|------------------|---------------|------------------|-------------|
|**ЗАКАНЧИВАЮЩ**|any|указатель на указатель NULL|**ЗАКАНЧИВАЮЩ**|**еинвал**|
|any|**ЗАКАНЧИВАЮЩ**|any|**ЗАКАНЧИВАЮЩ**|**еинвал**|
|any|any|**ЗАКАНЧИВАЮЩ**|**ЗАКАНЧИВАЮЩ**|**еинвал**|

Если *str* имеет **значение NULL** , а *контекст* является указателем на допустимый указатель контекста, то ошибка отсутствует.

## <a name="remarks"></a>Примечания

Семейство функций **strtok_s** находит следующий токен в *str*. Набор символов в *разделителях* указывает возможные разделители токена, которые должны быть найдены в *str* при текущем вызове. **wcstok_s** и **_mbstok_s** — это версии **strtok_s**для расширенных символов и многобайтовых символов. Аргументы и возвращаемые значения **wcstok_s** и **_wcstok_s_l** являются строками расширенных символов. **_mbstok_s** и **_mbstok_s_l** являются строками многобайтовых символов. В остальном эти функции ведут себя одинаково.

Эта функция проверяет свои параметры. При возникновении состояния ошибки, как в таблице условий ошибок, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции **устанавливают** значение **еинвал** и возвращают **значение NULL**.

При первом вызове функции **strtok_s**функция пропускает ведущие разделители и возвращает указатель на первый маркер в *str*, завершая токен нулевым символом. Дополнительные токены можно разделить из оставшейся части *str* на серию вызовов **strtok_s**. Каждый вызов **strtok_s** изменяет *str* , вставляя символ NULL после маркера, возвращенного этим вызовом. Указатель *контекста* следит за тем, какая строка считывается и где в строке находится следующий токен для считывания. Чтобы считать следующий токен из *str*, вызовите **Strtok_s** со значением **null** для аргумента *str* и передайте тот же параметр *контекста* . Аргумент **NULL** *str* NULL заставляет **strtok_s** искать следующий токен в измененной *str*. Аргумент *разделителей* может принимать любое значение от одного вызова к следующему, чтобы набор разделителей мог различаться.

Так как параметр *контекста* заменяет статические буферы, используемые в **strtok** и **_strtok_l**, можно одновременно анализировать две строки в одном потоке.

На выходное значение влияет параметр категории **LC_CTYPE** языкового стандарта. Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md).

Версии этих функций без суффикса **_l** используют текущий языковой стандарт потока для этого поведения, зависящего от языкового стандарта. Версии с суффиксом **_l** идентичны, за исключением того, что вместо них используется языковой стандарт, заданный параметром *locale* . Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtok_s**|\<string.h>|
|**_strtok_s_l**|\<string.h>|
|**wcstok_s**,<br />**_wcstok_s_l**|\<string.h> или \<wchar.h>|
|**_mbstok_s**,<br />**_mbstok_s_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|\_Юникод & \_MBCS не определен|\_Определенный MBCS|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok_s**|**strtok_s**|**_mbstok_s**|**wcstok_s**|
|**_tcstok_s_l**|**_strtok_s_l**|**_mbstok_s_l**|**_wcstok_s_l**|

## <a name="example"></a>Пример

```C
// crt_strtok_s.c
// In this program, a loop uses strtok_s
// to print all the tokens (separated by commas
// or blanks) in two strings at the same time.

#include <string.h>
#include <stdio.h>

char string1[] =
    "A string\tof ,,tokens\nand some  more tokens";
char string2[] =
    "Another string\n\tparsed at the same time.";
char seps[]   = " ,\t\n";
char *token1 = NULL;
char *token2 = NULL;
char *next_token1 = NULL;
char *next_token2 = NULL;

int main(void)
{
    printf("Tokens:\n");

    // Establish string and get the first token:
    token1 = strtok_s(string1, seps, &next_token1);
    token2 = strtok_s(string2, seps, &next_token2);

    // While there are tokens in "string1" or "string2"
    while ((token1 != NULL) || (token2 != NULL))
    {
        // Get next token:
        if (token1 != NULL)
        {
            printf(" %s\n", token1);
            token1 = strtok_s(NULL, seps, &next_token1);
        }
        if (token2 != NULL)
        {
            printf("        %s\n", token2);
            token2 = strtok_s(NULL, seps, &next_token2);
        }
    }
}
```

```Output
Tokens:
A
        Another
string
        string
of
        parsed
tokens
        at
and
        the
some
        same
more
        time.
tokens
```

## <a name="see-also"></a>См. также раздел

[Управление строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
