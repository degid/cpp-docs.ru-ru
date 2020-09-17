---
title: _strtime_s, _wstrtime_s
ms.date: 4/2/2020
api_name:
- _wstrtime_s
- _strtime_s
- _o__strtime_s
- _o__wstrtime_s
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wstrtime_s
- strtime_s
- wstrtime_s
- _strtime_s
helpviewer_keywords:
- wstrtime_s function
- copying time to buffers
- strtime_s function
- _wstrtime_s function
- time, copying
- _strtime_s function
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
ms.openlocfilehash: 54828bf894ffc9062125c9680ec087cdf929b1a2
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910928"
---
# <a name="_strtime_s-_wstrtime_s"></a>_strtime_s, _wstrtime_s

Копирует текущее время в буфер. Это версии функции [_strtime, _wstrtime](strtime-wstrtime.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _strtime_s(
   char *buffer,
   size_t numberOfElements
);
errno_t _wstrtime_s(
   wchar_t *buffer,
   size_t numberOfElements
);
template <size_t size>
errno_t _strtime_s(
   char (&buffer)[size]
); // C++ only
template <size_t size>
errno_t _wstrtime_s(
   wchar_t (&buffer)[size]
); // C++ only
```

### <a name="parameters"></a>Параметры

*двойной*<br/>
Буфер длиной не менее 10 символов, в который будет записано время.

*numberOfElements*<br/>
Размер буфера.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении.

Если возникает ошибка, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определены в ERRNO.H; ошибки, создаваемые этой функцией, см. в таблице ниже. Дополнительные сведения о кодах ошибок см. в разделе [Константы errno](../../c-runtime-library/errno-constants.md).

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*двойной*|*numberOfElements*|Возвращает|Содержимое *буфера*|
|--------------|------------------------|------------|--------------------------|
|**ЗАКАНЧИВАЮЩ**|(любые)|**еинвал**|Без изменений|
|Not **null** (указывает на допустимый буфер)|0|**еинвал**|Без изменений|
|Not **null** (указывает на допустимый буфер)|0 < size < 9|**еинвал**|Пустая строка.|
|Not **null** (указывает на допустимый буфер)|Size > 9|0|Текущая дата в формате, указанном в разделе "Примечания"|

## <a name="security-issues"></a>Проблемы с безопасностью

Передача недопустимого значения, отличного от**null** , для буфера приведет к нарушению прав доступа, если параметр *numberOfElements* больше 9.

Передача значения для *numberOfElements* , превышающих фактический размер буфера, приведет к переполнению буфера.

## <a name="remarks"></a>Примечания

Эти функции предоставляют более безопасные версии [_strtime](strtime-wstrtime.md) и [_wstrtime](strtime-wstrtime.md). Функция **_strtime_s** копирует текущее местное время в буфер, на который указывает *тиместр*. Время форматируется как **чч: мм: СС** , где **чч** — две цифры, представляющие час в 24-часовом формате, а **mm** — две цифры, представляющие минуты после часа, а **SS** — две цифры, представляющие секунды. Например, строка **18:23:44** представляет 23 минуты и 44 секунд после 18:00 Размер буфера должен составлять не менее 9 байт; фактический размер указывается в качестве второго параметра.

**_wstrtime** — это версия **_strtime**для расширенных символов; аргумент и возвращаемое значение **_wstrtime** являются строками расширенных символов. В остальном эти функции ведут себя одинаково.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Версии отладочной библиотеки этих функций сначала заполняют буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mapping"></a>Сопоставление универсальных текстовых функций:

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime_s**|**_strtime_s**|**_strtime_s**|**_wstrtime_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_strtime_s**|\<time.h>|
|**_wstrtime_s**|\<time.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// strtime_s.c

#include <time.h>
#include <stdio.h>

int main()
{
    char tmpbuf[9];
    errno_t err;

    // Set time zone from TZ environment variable. If TZ is not set,
    // the operating system is queried to obtain the default value
    // for the variable.
    //
    _tzset();

    // Display operating system-style date and time.
    err = _strtime_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
      exit(1);
    }
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );
    err = _strdate_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
       exit(1);
    }
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );

}
```

```Output
OS time:            14:37:49
OS date:            04/25/03
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
