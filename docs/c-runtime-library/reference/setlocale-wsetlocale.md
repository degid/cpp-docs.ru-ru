---
title: setlocale, _wsetlocale
description: Описывает функции библиотеки среды выполнения Microsoft C (CRT) setlocale и _wsetlocale .
ms.date: 4/2/2020
api_name:
- _wsetlocale
- setlocale
- _o__wsetlocale
- _o_setlocale
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
- _wsetlocale
- _tsetlocale
- setlocale
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
no-loc:
- setlocale
- _wsetlocale
ms.openlocfilehash: 812aab43667416a5892d8e24d03d0e67cad8d0ac
ms.sourcegitcommit: b51703a96ee35ee2376d5f0775b70f03ccbe6d9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "88086998"
---
# <a name="no-locsetlocale-no-loc_wsetlocale"></a>setlocale, _wsetlocale

Устанавливает или извлекает языковой стандарт времени выполнения.

## <a name="syntax"></a>Синтаксис

```C
char *setlocale(
   int category,
   const char *locale
);
wchar_t *_wsetlocale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>Параметры

*категори*\
Категория, на которую влияет языковой стандарт.

*языкового стандарта*\
Указатель языкового стандарта.

## <a name="return-value"></a>Возвращаемое значение

Если заданы допустимые *язык и региональные параметры* и *Категория* , возвращает указатель на строку, связанную с заданным *языковым стандартом* и *категорией*. Если *языковой стандарт* или *Категория* недействительна, возвращает пустой указатель, а текущие параметры языкового стандарта программы не изменяются.

Например, вызов

```C
setlocale( LC_ALL, "en-US" );
```

задает все категории, возвращая только строку

```Output
en-US
```

Можно скопировать строку, возвращенную `setlocale`, для восстановления этой части данных о языковом стандарте программы. Глобальное или локальное хранилище потока используется для строки, возвращаемой `setlocale`. Последующие вызовы `setlocale` перезаписывают эту строку, что аннулирует указатели строк, возвращенные предыдущими вызовами.

## <a name="remarks"></a>Примечания

Используйте `setlocale` функцию, чтобы задать, изменить или запросить некоторые или все сведения о языковом стандарте текущей программы, указанные в параметрах *locale* и *Category*. *языковой стандарт* — это локальность (страна, регион и язык), для которой можно настроить определенные аспекты программы. К некоторым категориям, зависящим от языкового стандарта, относится формат дат и отображения денежных значений. Если для языкового *стандарта* задана строка по умолчанию для языка с несколькими формами, поддерживаемыми на компьютере, следует проверить `setlocale` возвращаемое значение, чтобы узнать, какой язык действует. Например, если задать для параметра *locale* значение "Китайский", то возвращаемым значением может быть "китайский-упрощенный" или "Китайский (традиционное письмо)".

`_wsetlocale`— Это версия с расширенными символами `setlocale` ; аргумент *локали* и возвращаемое значение `_wsetlocale` являются строками расширенных символов. Поведение`_wsetlocale` и `setlocale` идентично в противном случае.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tsetlocale`|`setlocale`|`setlocale`|`_wsetlocale`|

Аргумент *Category* определяет части информации о языковом стандарте программы, которые затрагиваются. Макросы, используемые для *категории* и части программы, на которые они влияют, выглядят следующим образом:

|флаг *категории*|Область применения|
|-|-|
| `LC_ALL` | Все категории, перечисленные ниже. |
| `LC_COLLATE` | Функции `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll` и `wcsxfrm`. |
| `LC_CTYPE` | Функции обработки символов (за исключением `isdigit`, `isxdigit`, `mbstowcs` и `mbtowc`, которые не затрагиваются). |
| `LC_MONETARY` | Информация о форматировании денежных значений, возвращаемая функцией `localeconv`. |
| `LC_NUMERIC` | Символ десятичного разделителя для информации процедур форматированного вывода (например, `printf`), для процедур преобразования данных и для форматирования не относящихся к денежным значений, возвращаемой `localeconv`. Помимо символа десятичного разделителя `LC_NUMERIC` также задает разделитель тысяч и строку элемента управления группировкой, возвращаемую [localeconv](localeconv.md). |
| `LC_TIME` | Функции `strftime` и `wcsftime`. |

Эта функция проверяет параметр категории. Если параметр category не является одним из значений, указанных в предыдущей таблице, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `NULL`.

Аргумент *locale* является указателем на строку, указывающую языковой стандарт. Дополнительные сведения о формате аргумента *языкового стандарта* см. в разделе [языковые имена, языки и строки страны или региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Если аргумент *locale* указывает на пустую строку, языковой стандарт соответствует исходной среде, определенной реализацией. Значение `C` задает минимальную подходящую ANSI среду для переноса C. Языковой стандарт `C` предполагает, что все типы данных ``char`` соответствуют 1 байту, а их значение всегда меньше 256.

При запуске программы выполняется эквивалент следующего оператора:

`setlocale( LC_ALL, "C" );`

Аргумент *locale* может принимать имя локали, строку языка, языковую строку и код страны или региона, кодовую страницу, языковую строку, код страны или региона и кодовую страницу. Набор доступных имен языковых стандартов, языков, кодов стран и регионов, а также кодовых страниц включает все поддерживаемые API NLS Windows. Набор имен языковых стандартов, поддерживаемых `setlocale`, см. в разделе [Строки имени языкового стандарта, языка и страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Набор строковых значений языка и страны или региона, поддерживаемых `setlocale`, представлен в разделах [Строки языка](../../c-runtime-library/language-strings.md) и [Строки страны или региона](../../c-runtime-library/country-region-strings.md). Рекомендуется использовать форму имени языкового стандарта для обеспечения производительности и удобства поддержки строк языкового стандарта, внедренных в код или сериализованных в хранилище. Строковые значения имен языкового стандарта реже подвергаются изменению обновлением операционной системы, чем язык и форма названия страны или региона.

Указатель null, который передается в качестве аргумента *локали* , указывает `setlocale` на запрос, а не на установку международного окружения. Если аргумент *locale* является пустым указателем, текущее значение языкового стандарта программы не меняется. Вместо этого `setlocale` возвращает указатель на строку, связанную с *категорией* текущего языкового стандарта потока. Если аргумент *Category* имеет значение `LC_ALL` , функция возвращает строку, указывающую текущее значение каждой категории, разделенную точкой с запятой. Например, последовательность вызовов

```C
// Set all categories and return "en-US"
setlocale(LC_ALL, "en-US");
// Set only the LC_MONETARY category and return "fr-FR"
setlocale(LC_MONETARY, "fr-FR");
printf("%s\n", setlocale(LC_ALL, NULL));
```

возвращает

```Output
LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US
```

и это строка, связанная с категорией `LC_ALL`.

Следующие примеры относятся к категории `LC_ALL`. Любая из строк ". OCP "и". ACP» можно использовать вместо номера кодовой страницы для указания использования пользовательской кодовой страницы OEM по умолчанию и кодовой страницы ANSI по умолчанию для этого имени языкового стандарта соответственно.

- `setlocale( LC_ALL, "" );`

   Задает языковой стандарт по умолчанию, т.е. заданную по умолчанию для пользователя кодовую страницу ANSI, полученную от операционной системы. Для имени языкового стандарта задается значение, возвращаемое функцией [жетусердефаултлокаленаме](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename). Кодовая страница задается значением, возвращаемым функцией [жетакп](/windows/win32/api/winnls/nf-winnls-getacp).

- `setlocale( LC_ALL, ".OCP" );`

   Задает языковой стандарт для текущей кодовой страницы OEM, полученной от операционной системы. Для имени языкового стандарта задается значение, возвращаемое функцией [жетусердефаултлокаленаме](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename). Кодовая страница задается в качестве значения [LOCALE_IDEFAULTCODEPAGE](/windows/win32/intl/locale-idefault-constants) для имени локали пользователя по умолчанию по [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex).

- `setlocale( LC_ALL, ".ACP" );`

   Задает языковой стандарт согласно текущей кодовой странице ANSI, полученной от операционной системы. Для имени языкового стандарта задается значение, возвращаемое функцией [жетусердефаултлокаленаме](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename). Кодовая страница задается в качестве значения [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) для имени локали пользователя по умолчанию по [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex).

- `setlocale( LC_ALL, "<localename>" );`

   Задает языковой стандарт для имени языкового стандарта, указанного в *\<localename>* . Кодовая страница задается в качестве значения [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) для указанного имени локали по [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex).

- `setlocale( LC_ALL, "<language>_<country>" );`

   Задает языковой стандарт и страну или регион, указанные в параметре *\<language>* и, а также *\<country>* кодовую страницу по умолчанию, полученную из операционной системы узла. Кодовая страница задается в качестве значения [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) для указанного имени локали по [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex).

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   Задает языковой стандарт для языка, страны или региона, а также кодовую страницу, определяемую *\<language>* *\<country>* *\<code_page>* строками, и. Можно использовать различные сочетания языка, страны или региона и кодовой страницы. Например, этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей 1252.

   `setlocale( LC_ALL, "French_Canada.1252" );`

   Этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей по умолчанию ANSI.

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   Этот вызов устанавливает языковой стандарт "французский (Канада)" с кодовой страницей по умолчанию OEM.

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   Устанавливает языковой стандарт для языка, указанного в параметре *\<language>* , и использует страну или регион по умолчанию для указанного языка и кодовую страницу пользователя по умолчанию ANSI для этой страны или региона, полученную из операционной системы узла. Например, следующие вызовы `setlocale` функционально эквивалентны:

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   Рекомендуется использовать первую форму для обеспечения производительности и простоты обслуживания.

- `setlocale( LC_ALL, ".<code_page>" );`

   Задает кодовую страницу согласно значению, отображаемому *<code_page>*, вместе с языком и страной или регионом по умолчанию (согласно определению операционной системы) для заданной кодовой страницы.

Эта категория должна быть `LC_ALL` или `LC_CTYPE` для реализации изменения кодовой страницы. Например, если страной и языком по умолчанию операционной системы являются «США» и «английский», следующие два вызова `setlocale` функционально эквивалентны:

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

Дополнительные сведения см. в описании [setlocale](../../preprocessor/setlocale.md) директивы pragma в [справочнике по препроцессору C/C++](../../preprocessor/c-cpp-preprocessor-reference.md).

Функция [_configthreadlocale](configthreadlocale.md) используется в для определения того, влияет ли `setlocale` на языковой стандарт всех потоков в программе или только на языковой стандарт вызывающего потока.

## <a name="utf-8-support"></a>Поддержка UTF-8

Начиная с Windows 10 Build 17134 (обновление от апреля 2018), универсальная среда выполнения C поддерживает использование кодовой страницы UTF-8. Это означает, что `char` строки, передаваемые в функции среды выполнения C, будут ждать строк в кодировке UTF-8. Чтобы включить режим UTF-8, используйте "UTF-8" в качестве кодовой страницы при использовании `setlocale` . Например, `setlocale(LC_ALL, ".utf8")` будет использовать текущую кодовую страницу ANSI Windows (ACP) по умолчанию для языкового стандарта и кодировку UTF-8 для кодовой страницы.

После вызова `setlocale(LC_ALL, ".UTF8")` вы можете передать " 😊 " в, `mbtowcs` и он будет правильно преобразован в `wchar_t` строку, в то время как ранее для этого не существовал параметр языкового стандарта.

Режим UTF-8 также включается для функций с историческим переводом `char` строк с помощью кодовой страницы Windows ANSI по умолчанию (ACP). Например, вызов [`_mkdir("😊")`](../reference/mkdir-wmkdir.md) при использовании кодовой страницы UTF-8 правильно создаст каталог с этим символом эмодзи в качестве имени папки, а не требует, чтобы ACP был изменен на UTF-8 перед запуском программы. Аналогичным образом, вызов [`_getcwd()`](../reference/getcwd-wgetcwd.md) внутри этой папки вернет строку в кодировке UTF-8. Для обеспечения совместимости ACP по-прежнему используется, если кодовая страница языка C не имеет значение UTF-8.

Следующие аспекты среды выполнения C не могут использовать кодировку UTF-8, так как они задаются во время запуска программы и должны использовать кодовую страницу ANSI Windows по умолчанию (ACP): [`__argv`](../argc-argv-wargv.md) , [`_acmdln`](../acmdln-tcmdln-wcmdln.md) и [`_pgmptr`](../pgmptr-wpgmptr.md) .

Предыдущая поддержка этой поддержки [ `mbrtoc16` , `mbrtoc32` ,, ](../reference/mbrtoc16-mbrtoc323.md) [ `c16rtomb` и `c32rtomb` ](../reference/c16rtomb-c32rtomb1.md) существовала для преобразования между строками UTF-8, UTF-16 (то же кодирование, что и `wchar_t` на платформах Windows) и UTF-32. По соображениям совместимости эти API-интерфейсы переводятся только в кодировку UTF-8 и не задаются кодовой страницей с помощью `setlocale` .

Чтобы использовать эту функцию в ОС до Windows 10, например Windows 7, необходимо использовать [Локальное развертывание приложения](../../windows/universal-crt-deployment.md#local-deployment) или компоновку, используя версию 17134 Windows SDK или более позднюю. Для операционных систем Windows 10 до 17134 поддерживается только статическая компоновка.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`setlocale`|\<locale.h>|
|`_wsetlocale`|\<locale.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_setlocale.c
//
// This program demonstrates the use of setlocale when
// using two independent threads.
//

#include <locale.h>
#include <process.h>
#include <windows.h>
#include <stdio.h>
#include <time.h>

#define BUFF_SIZE 100

// Retrieve the date in the current
// locale's format.
int get_date(unsigned char* str)
{
    __time64_t ltime;
    struct tm  thetime;

    // Retrieve the current time
    _time64(&ltime);
    _gmtime64_s(&thetime, &ltime);

    // Format the current time structure into a string
    // "%#x" is the long date representation in the
    // current locale
    if (!strftime((char *)str, BUFF_SIZE, "%#x",
                  (const struct tm *)&thetime))
    {
        printf("strftime failed!\n");
        return -1;
    }
    return 0;
}

// This thread sets its locale to the argument
// and prints the date.
uintptr_t __stdcall SecondThreadFunc( void* pArguments )
{
    unsigned char str[BUFF_SIZE];
    char * locale = (char *)pArguments;

    // Set the thread locale
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, locale));

    // Retrieve the date string from the helper function
    if (get_date(str) == 0)
    {
        printf("The date in %s locale is: '%s'\n", locale, str);
    }

    _endthreadex( 0 );
    return 0;
}

// The main thread sets the locale to English
// and then spawns a second thread (above) and prints the date.
int main()
{
    HANDLE          hThread;
    unsigned        threadID;
    unsigned char   str[BUFF_SIZE];

    // Enable per-thread locale causes all subsequent locale
    // setting changes in this thread to only affect this thread.
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Set the locale of the main thread to US English.
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "en-US"));

    // Create the second thread with a German locale.
    // Our thread function takes an argument of the locale to use.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,
                                      "de-DE", 0, &threadID );

    if (get_date(str) == 0)
    {
        // Retrieve the date string from the helper function
        printf("The date in en-US locale is: '%s'\n\n", str);
    }

    // Wait for the created thread to finish.
    WaitForSingleObject( hThread, INFINITE );

    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
The thread locale is now set to en-US.
The time in en-US locale is: 'Wednesday, May 12, 2004'

The thread locale is now set to de-DE.
The time in de-DE locale is: 'Mittwoch, 12. Mai 2004'
```

## <a name="see-also"></a>См. также раздел

[Имена языковых стандартов, языки и строки страны или региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[_configthreadlocale](configthreadlocale.md)\
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)\
[Языкового стандарта](../../c-runtime-library/locale.md)\
[localeconv](localeconv.md)\
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)\
[функции mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)\
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)\
[_setmbcp](setmbcp.md)\
[Функции strcoll](../../c-runtime-library/strcoll-functions.md)\
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)\
[стрксфрм, вксксфрм, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)\
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)\
[wctomb, _wctomb_l](wctomb-wctomb-l.md)
