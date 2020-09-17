---
title: localtime, _localtime32, _localtime64
ms.date: 4/2/2020
api_name:
- _localtime64
- _localtime32
- localtime
- _o__localtime32
- _o__localtime64
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
- localtime64
- _localtime64
- localtime32
- localtime
- _localtime32
helpviewer_keywords:
- localtime32 function
- _localtime32 function
- _localtime64 function
- localtime64 function
- localtime function
- time, converting values
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
ms.openlocfilehash: cacc0317bf48b7f4d33027558c3dc6c739e474dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218628"
---
# <a name="localtime-_localtime32-_localtime64"></a>localtime, _localtime32, _localtime64

Преобразует значение времени и корректирует его для местного часового пояса. Доступны более безопасные версии этих функций; см. раздел [localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md).

## <a name="syntax"></a>Синтаксис

```C
struct tm *localtime( const time_t *sourceTime );
struct tm *_localtime32( const __time32_t *sourceTime );
struct tm *_localtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Параметры

*саурцетиме*<br/>
Указатель на сохраненное время.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на результат структуры или **значение NULL** , если дата, передаваемая функции:

- До полуночи 1-го января 1970 года.

- После 03:14:07 января 19, 2038, UTC (с использованием **_time32** и **time32_t**).

- После 23:59:59 31 декабря 3000, UTC (с использованием **_time64** и **__time64_t**).

**_localtime64**, в котором используется структура **__time64_t** , позволяет выражать даты до 23:59:59, 31 декабря 3000, время в формате UTC, а **_localtime32** представляет даты до 23:59:59 18 января 2038 года по Гринвичу.

**localtime** — это встроенная функция, которая оценивается как **_localtime64**, а **time_t** эквивалентна **__time64_t**. Если необходимо заставить компилятор интерпретировать **time_t** как старый 32-разрядный **time_t**, можно определить **_USE_32BIT_TIME_T**. Это приведет к **_localtime32у**вычисления **localtime** . Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.

Поля структуры типа [TM](../../c-runtime-library/standard-types.md) хранят следующие значения, каждое из которых является **`int`** :

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

## <a name="remarks"></a>Примечания

Функция **localtime** преобразует время, хранящееся в виде значения [time_t](../../c-runtime-library/standard-types.md) , и сохраняет результат в виде структуры типа [TM](../../c-runtime-library/standard-types.md). **`long`** Значение *саурцетиме* представляет секунды, прошедшие с полуночи (00:00:00), 1 января 1970, UTC. Это значение обычно получается из функции [time](time-time32-time64.md) .

И 32-разрядные, и 64-разрядные версии [gmtime](gmtime-gmtime32-gmtime64.md), [функциях mktime](mktime-mktime32-mktime64.md), [мкгмтиме](mkgmtime-mkgmtime32-mkgmtime64.md)и **localtime** используют одну структуру **TM** для каждого потока для преобразования. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова.

**localtime** корректирует для местного часового пояса, если пользователь впервые устанавливает глобальную **переменную**среды. Если задано значение **, то также** автоматически устанавливаются три другие переменные среды (**_timezone**, **_daylight**и **_tzname**). Если переменная **IsDate** не задана, **localtime** пытается использовать сведения о часовом поясе, указанные в приложении "Дата и время" в панели управления. Если эти сведения недоступны, по умолчанию используется значение PST8PDT, что означает тихоокеанский часовой пояс. Описание этих переменных см. в разделе [_tzset](tzset.md). **Это расширение** Microsoft, а не часть стандартного определения **localtime**стандарта ANSI.

> [!NOTE]
> Целевая среда должна попытаться определить, действует ли летнее время.

Эти функции проверяют свои параметры. Если *саурцетиме* является пустым указателем или значение *саурцетиме* является отрицательным, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функции возвращают **значение NULL** и **задают значение** **еинвал**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C++|
|-------------|---------------------|-|
|**localtime**, **_localtime32** **_localtime64**|\<time.h>|\<ctime> или \<time.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_localtime.cpp
// compile with: /W3
// This program uses _time64 to get the current time
// and then uses localtime64() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

#include <stdio.h>
#include <string.h>
#include <time.h>

int main( void )
{
    struct tm *newtime;
    char am_pm[] = "AM";
    __time64_t long_time;

    _time64( &long_time );             // Get time as 64-bit integer.
                                       // Convert to local time.
    newtime = _localtime64( &long_time ); // C4996
    // Note: _localtime64 deprecated; consider _localetime64_s

    if( newtime->tm_hour > 12 )        // Set up extension.
        strcpy_s( am_pm, sizeof(am_pm), "PM" );
    if( newtime->tm_hour > 12 )        // Convert from 24-hour
        newtime->tm_hour -= 12;        //   to 12-hour clock.
    if( newtime->tm_hour == 0 )        // Set hour to 12 if midnight.
        newtime->tm_hour = 12;

    char buff[30];
    asctime_s( buff, sizeof(buff), newtime );
    printf( "%.19s %s\n", buff, am_pm );
}
```

```Output
Tue Feb 12 10:05:58 AM
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
