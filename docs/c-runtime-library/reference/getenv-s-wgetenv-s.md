---
title: getenv_s, _wgetenv_s
description: Описывает библиотеку getenv_s и _wgetenv_s функции среды выполнения Microsoft C.
ms.date: 4/2/2020
api_name:
- getenv_s
- _wgetenv_s
- _o__wgetenv_s
- _o_getenv_s
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
- getenv_s
- _tgetenv_s
- _wgetenv_s
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
no-loc:
- getenv_s
- _wgetenv_s
- _putenv_s
- main
- wmain
- errno
- EINVAL
- ERANGE
- _environ
- _wenviron
- _putenv
- _wputenv
- _tgetenv_s
- _tzset
- _dupenv_s
- _wdupenv_s
ms.openlocfilehash: 0713ed5735916c31edaab1a178a5e9b1b7cf5377
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913672"
---
# <a name="getenv_s-_wgetenv_s"></a>getenv_s, _wgetenv_s

Получает значение из текущей среды. Это версии функций [getenv, _wgetenv](getenv-wgetenv.md) с повышенной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t getenv_s(
   size_t *pReturnValue,
   char* buffer,
   size_t numberOfElements,
   const char *varname
);
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *varname
);
template <size_t size>
errno_t getenv_s(
   size_t *pReturnValue,
   char (&buffer)[size],
   const char *varname
); // C++ only
template <size_t size>
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t (&buffer)[size],
   const wchar_t *varname
); // C++ only
```

### <a name="parameters"></a>Параметры

*претурнвалуе*<br/>
Требуемый размер буфера или 0, если переменная не найдена.

*двойной*<br/>
Буфер для хранения значения переменной среды.

*numberOfElements*<br/>
Размер *буфера*.

*varname*<br/>
Имя переменной среды.

## <a name="return-value"></a>Возвращаемое значение

Ноль при успехе; код ошибки при неудаче.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*претурнвалуе*|*двойной*|*numberOfElements*|*varname*|Возвращаемое значение|
|--------------------|--------------|------------------------|---------------|------------------|
|**ЗАКАНЧИВАЮЩ**|any|any|any|**еинвал**|
|any|**ЗАКАНЧИВАЮЩ**|> 0|any|**еинвал**|
|any|any|any|**ЗАКАНЧИВАЮЩ**|**еинвал**|

При любом из этих условий ошибки вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **функции устанавливают значение** **еинвал** и возвращают **еинвал**.

Кроме того, если буфер слишком мал, эти функции возвращают **ERANGE**. Они не вызывают обработчик недопустимого параметра. Они записывают требуемый размер буфера в *претурнвалуе*и таким образом позволяют программам повторно вызывать функцию с большим размером буфера.

## <a name="remarks"></a>Примечания

Функция **getenv_s** выполняет поиск в списке переменных среды для *VarName*. **getenv_s** не учитывает регистр в операционной системе Windows. **getenv_s** и [_putenv_s](putenv-s-wputenv-s.md) используют копию среды, на которую указывает глобальная переменная **_environ** для доступа к среде. **getenv_s** работает только с структурами данных, которые доступны библиотеке времени выполнения, а не в сегменте среды, созданном для процесса операционной системой. Поэтому программы, использующие аргумент *envp* для [Main](../../cpp/main-function-command-line-args.md) или [wmain](../../cpp/main-function-command-line-args.md) , могут получить недействительные данные.

**_wgetenv_s** — это версия **getenv_s**для расширенных символов; аргумент и возвращаемое значение **_wgetenv_s** являются строками расширенных символов. **_Wenviron** глобальная переменная — это версия **_environ**для расширенных символов.

В программе многобайтовой кодировки (например, в однобайтовой программе ASCII) **_wenviron** изначально имеет **значение NULL** , так как среда состоит из многобайтовых строк. Затем при первом вызове [_wputenv](putenv-wputenv.md)или при первом вызове **_wgetenv_s**, если среда (MBCS) уже существует, создается соответствующая среда строк расширенных символов, которая затем указывается на **_wenviron**.

Аналогично в программе Юникода (**_wmain**) **_Environ** изначально имеет **значение NULL** , поскольку среда состоит из строк расширенных символов. Затем при первом вызове [_putenv](putenv-wputenv.md)или при первом вызове метода **getenv_s** если среда (Юникод) уже существует, создается соответствующая среда MBCS, на которую указывает **_environ**.

Если две копии среды (многобайтовой кодировки и Юникода) существуют одновременно в программе, система времени выполнения должна поддерживать обе копии, что отрицательно сказывается на скорости выполнения программы. Например, при вызове **_putenv**вызов **_wputenv** также выполняется автоматически, чтобы соответствовать двум строкам среды.

> [!CAUTION]
> В редких случаях, когда система времени выполнения поддерживает как версию Юникода, так и многобайтовую версию среды, эти две версии среды могут не полностью соответствовать друг другу. Это происходит потому, что хотя любая уникальная строка с многобайтовыми символами сопоставляется уникальной строке Юникода, сопоставление уникальной строки Юникода со строкой многобайтовой кодировки не обязательно будет уникальными. Дополнительные сведения см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv_s** и **_getenv_s** семейств функций не являются потокобезопасными. **_getenv_s** может возвращать указатель на строку, когда **_putenv_s** изменяет строку и тем самым вызывает случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устранена необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

Чтобы проверить или изменить значение **переменной среды,** используйте **getenv_s**, **_putenv**и **_tzset**в соответствии с требованиями. Дополнительные сведения о параметре "Описание" см **. в разделе** [_tzset](tzset.md) и [_daylight, _dstbias, _timezone и _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**getenv_s**|\<stdlib.h>|
|**_wgetenv_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getenv_s.c
// This program uses getenv_s to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char* libvar;
   size_t requiredSize;

   getenv_s( &requiredSize, NULL, 0, "LIB");
   if (requiredSize == 0)
   {
      printf("LIB doesn't exist!\n");
      exit(1);
   }

   libvar = (char*) malloc(requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects
   // the environment variable of the current process. The command
   // processor's environment is not changed.
   _putenv_s( "LIB", "c:\\mylib;c:\\yourlib" );

   getenv_s( &requiredSize, NULL, 0, "LIB");

   libvar = (char*) realloc(libvar, requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the new value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "New LIB variable is: %s\n", libvar );

   free(libvar);
}
```

```Output
Original LIB variable is: c:\vctools\lib;c:\vctools\atlmfc\lib;c:\vctools\PlatformSDK\lib;c:\vctools\Visual Studio SDKs\DIA Sdk\lib;c:\vctools\Visual Studio SDKs\BSC Sdk\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Константы среды](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
