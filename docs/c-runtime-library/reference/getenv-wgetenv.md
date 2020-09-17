---
title: getenv, _wgetenv
description: Описывает библиотеку getenv и _wgetenv функции среды выполнения Microsoft C.
ms.date: 4/2/2020
api_name:
- getenv
- _wgetenv
- _o__wgetenv
- _o_getenv
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
- _wgetenv
- getenv
- _tgetenv
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
no-loc:
- getenv
- _wgetenv
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
ms.openlocfilehash: ea7fba1dd47123919dc0a01fd84bad65481b9db9
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913665"
---
# <a name="getenv-_wgetenv"></a>getenv, _wgetenv

Получает значение из текущей среды. Существуют более безопасные версии этих функций; см. раздел [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *getenv(
   const char *varname
);
wchar_t *_wgetenv(
   const wchar_t *varname
);
```

### <a name="parameters"></a>Параметры

*varname*<br/>
Имя переменной среды.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на запись таблицы окружения, содержащую *имя_переменной*. Изменять значение переменной среды с помощью возвращенного указателя небезопасно. Используйте функцию [_putenv](putenv-wputenv.md) , чтобы изменить значение переменной среды. Возвращаемое значение равно **null** , если *VarName* не найден в таблице Environment.

## <a name="remarks"></a>Примечания

Функция **getenv** выполняет поиск в списке переменных среды для *VarName*. **getenv** не учитывает регистр в операционной системе Windows. **getenv** и **_putenv** используют копию окружения, на которую указывает глобальная переменная **_environ** для доступа к среде. **getenv** работает только с структурами данных, доступными библиотеке времени выполнения, но не в среде "сегмент", созданной для процесса операционной системой. Поэтому программы, использующие аргумент *envp* для [Main](../../cpp/main-function-command-line-args.md) или [wmain](../../cpp/main-function-command-line-args.md) , могут получить недействительные данные.

Если *имя_переменной* имеет **значение NULL**, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция **устанавливает** **Еинвал** и возвращает **значение NULL**.

**_wgetenv** — это версия **getenv**с расширенными символами; аргумент и возвращаемое значение **_wgetenv** являются строками расширенных символов. **_Wenviron** глобальная переменная — это версия **_environ**для расширенных символов.

В программе многобайтовой кодировки (например, в однобайтовой программе ASCII) **_wenviron** изначально имеет **значение NULL** , так как среда состоит из многобайтовых строк. Затем при первом вызове [_wputenv](putenv-wputenv.md)или при первом вызове метода **_wgetenv** если среда (MBCS) уже существует, создается соответствующая среда строк расширенных символов, которая затем указывается на **_wenviron**.

Аналогично в программе Юникода (**_wmain**) **_Environ** изначально имеет **значение NULL** , поскольку среда состоит из строк расширенных символов. Затем при первом вызове **_putenv**или при первом вызове **getenv** если среда (Юникод) уже существует, создается соответствующая среда MBCS, на которую указывает **_environ**.

Если в программе одновременно существуют две копии среды (многобайтовой кодировки и Юникода), система времени выполнения должна поддерживать обе копии, что отрицательно сказывается на скорости выполнения программы. Например, при каждом вызове **_putenv**вызов **_wputenv** также выполняется автоматически, чтобы соответствовать двум строкам среды.

> [!CAUTION]
> В редких случаях, когда система времени выполнения поддерживает и версию Юникода, и многобайтовую версию, эти две версии среды могут не полностью соответствовать друг другу. Это происходит потому, что хотя любая уникальная расширенная строка сопоставляется уникальной строке Юникода, сопоставление уникальной строки Юникода со строкой многобайтовой кодировки не обязательно будет уникальными. Дополнительные сведения см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv** и **_getenv** семейств функций не являются потокобезопасными. **_getenv** может возвращать указатель на строку, когда **_putenv** изменяет строку, вызывая случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**getenv**|**getenv**|**_wgetenv**|

Чтобы проверить или изменить значение **переменной среды,** используйте **getenv**, **_putenv** и **_tzset** при необходимости. Дополнительные сведения о параметре "Описание" см **. в разделе** [_tzset](tzset.md) и [_daylight, часовой пояс и _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**getenv**|\<stdlib.h>|
|**_wgetenv**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getenv.c
// compile with: /W3
// This program uses getenv to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *libvar;

   // Get the value of the LIB environment variable.
   libvar = getenv( "LIB" ); // C4996
   // Note: getenv is deprecated; consider using getenv_s instead

   if( libvar != NULL )
      printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects the environment
   // variable of the current process. The command processor's
   // environment is not changed.
   _putenv( "LIB=c:\\mylib;c:\\yourlib" ); // C4996
   // Note: _putenv is deprecated; consider using putenv_s instead

   // Get new value.
   libvar = getenv( "LIB" ); // C4996

   if( libvar != NULL )
      printf( "New LIB variable is: %s\n", libvar );
}
```

```Output
Original LIB variable is: C:\progra~1\devstu~1\vc\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[Константы среды](../../c-runtime-library/environmental-constants.md)<br/>
