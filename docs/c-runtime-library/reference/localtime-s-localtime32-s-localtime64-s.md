---
title: localtime_s, _localtime32_s, _localtime64_s
ms.date: 4/2/2020
api_name:
- _localtime64_s
- _localtime32_s
- localtime_s
- _o__localtime32_s
- _o__localtime64_s
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
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
ms.openlocfilehash: 26ebadf49632b9e312f3d0c0a0788720d3230312
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218615"
---
# <a name="localtime_s-_localtime32_s-_localtime64_s"></a>localtime_s, _localtime32_s, _localtime64_s

Преобразует значение времени **time_t** в структуру **TM** и корректирует для местного часового пояса. Это версии функций [localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t localtime_s(
   struct tm* const tmDest,
   time_t const* const sourceTime
);
errno_t _localtime32_s(
   struct tm* tmDest,
   __time32_t const* sourceTime
);
errno_t _localtime64_s(
   struct tm* tmDest,
   __time64_t const* sourceTime
);
```

### <a name="parameters"></a>Параметры

*тмдест*<br/>
Указатель на структуру времени, которую требуется заполнить.

*саурцетиме*<br/>
Указатель на хранимое время.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Список этих ошибок см. в разделе [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*тмдест*|*саурцетиме*|Возвращаемое значение|Значение в *тмдест*|Вызывает обработчик недопустимого параметра|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**NULL**|any|**еинвал**|Без изменений|Да|
|Not **null** (указывает на допустимый объем памяти)|**NULL**|**еинвал**|Во всех полях заданы значения –1|Да|
|Not **null** (указывает на допустимый объем памяти)|меньше 0 или больше **_MAX__TIME64_T**|**еинвал**|Во всех полях заданы значения –1|Нет|

В случае первых двух условий ошибки вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции **устанавливают** значение **еинвал** и возвращают **еинвал**.

## <a name="remarks"></a>Примечания

Функция **localtime_s** преобразует время, хранящееся в качестве значения [time_t](../../c-runtime-library/standard-types.md) , и сохраняет результат в виде структуры типа [TM](../../c-runtime-library/standard-types.md). Значение **Time_t** *саурцетиме* представляет секунды, прошедшие с полуночи (00:00:00), 1 января 1970, UTC. Это значение обычно получается из функции [time](time-time32-time64.md) .

**localtime_s** исправляется для местного часового пояса, если пользователь впервые устанавливает глобальную переменную **среды.** Если задано значение **, то также** автоматически устанавливаются три другие переменные среды (**_timezone**, **_daylight**и **_tzname**). Если переменная **IsDate** не задана, **localtime_s** пытается использовать сведения о часовом поясе, указанные в приложении "Дата и время" в панели управления. Если эти сведения недоступны, по умолчанию используется значение PST8PDT, что означает тихоокеанский часовой пояс. Описание этих переменных см. в разделе [_tzset](tzset.md). **Это расширение** Microsoft, а не часть стандартного определения **localtime**стандарта ANSI.

> [!NOTE]
> Целевая среда должна попытаться определить, действует ли летнее время.

**_localtime64_s**, в котором используется структура **__time64_t** , позволяет выражать даты до 23:59:59, 18 января 3001, время в формате UTC, а **_localtime32_s** представляет даты до 23:59:59 18 января 2038 года по Гринвичу.

**localtime_s** — это встроенная функция, результатом которой является **_localtime64_s**, а **time_t** эквивалентна **__time64_t**. Если необходимо заставить компилятор интерпретировать **time_t** как старый 32-разрядный **time_t**, можно определить **_USE_32BIT_TIME_T**. Это приведет к тому, что **localtime_s** выдаст **_localtime32_s**. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.

Поля структуры типа [TM](../../c-runtime-library/standard-types.md) хранят следующие значения, каждое из которых является **`int`** .

|Поле|Описание|
|-|-|
|**tm_sec**|Секунд после минуты (0-59).|
|**tm_min**|Минут после часа (0-59).|
|**tm_hour**|Часы с полуночи (0-23).|
|**tm_mday**|День месяца (1-31).|
|**tm_mon**|Месяц (0-11; Январь = 0).|
|**tm_year**|Год (текущий год минус 1900).|
|**tm_wday**|День недели (0-6; Воскресенье = 0).|
|**tm_yday**|День года (0-365; 1 января = 0).|
|**tm_isdst**|Положительное значение, если действует летнее время; 0, если летнее время не действует; отрицательное значение, если состояние летнего времени неизвестно.|

Если задана **переменная среды, то библиотека** времени выполнения языка C принимает правила, соответствующие США для реализации вычисления летнего времени (DST).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C++|
|-------------|---------------------|-|
|**localtime_s**, **_localtime32_s** **_localtime64_s**|\<time.h>|\<ctime> или \<time.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_localtime_s.c
// This program uses _time64 to get the current time
// and then uses _localtime64_s() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

#include <stdio.h>
#include <string.h>
#include <time.h>

int main( void )
{
    struct tm newtime;
    char am_pm[] = "AM";
    __time64_t long_time;
    char timebuf[26];
    errno_t err;

    // Get time as 64-bit integer.
    _time64( &long_time );
    // Convert to local time.
    err = _localtime64_s( &newtime, &long_time );
    if (err)
    {
        printf("Invalid argument to _localtime64_s.");
        exit(1);
    }
    if( newtime.tm_hour > 12 )        // Set up extension.
        strcpy_s( am_pm, sizeof(am_pm), "PM" );
    if( newtime.tm_hour > 12 )        // Convert from 24-hour
        newtime.tm_hour -= 12;        // to 12-hour clock.
    if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.
        newtime.tm_hour = 12;

    // Convert to an ASCII representation.
    err = asctime_s(timebuf, 26, &newtime);
    if (err)
    {
        printf("Invalid argument to asctime_s.");
        exit(1);
    }
    printf( "%.19s %s\n", timebuf, am_pm );
}
```

```Output
Fri Apr 25 01:19:27 PM
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
