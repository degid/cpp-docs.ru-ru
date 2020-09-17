---
title: asctime, _wasctime
ms.date: 4/2/2020
api_name:
- _wasctime
- asctime
- _o__wasctime
- _o_asctime
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
- _tasctime
- asctime
- _wasctime
helpviewer_keywords:
- asctime function
- tasctime function
- wasctime function
- _tasctime function
- _wasctime function
- time structure conversion
- time, converting
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
ms.openlocfilehash: 00c6be8ee409d76b80d323102950f8c1d6420ba3
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909424"
---
# <a name="asctime-_wasctime"></a>asctime, _wasctime

Преобразование структуры времени **TM** в символьную строку. Существуют более безопасные версии этих функций; см. раздел [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *asctime(
   const struct tm *timeptr
);
wchar_t *_wasctime(
   const struct tm *timeptr
);
```

### <a name="parameters"></a>Параметры

*timeptr*<br/>
Структура даты/времени.

## <a name="return-value"></a>Возвращаемое значение

**asctime** возвращает указатель на результат символьной строки; **_wasctime** возвращает указатель на результат строки расширенных символов. Код ошибки не возвращается.

## <a name="remarks"></a>Примечания

Существуют более безопасные версии этих функций; см. раздел [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

Функция **asctime** преобразует время, хранящееся в виде структуры, в символьную строку. Значение *timeptr* обычно получается из вызова **gmtime** или **localtime**, который возвращает указатель на структуру **TM** , определенную во времени. Высоты.

|Член timeptr|Применение|
|--------------------|-----------|
|**tm_hour**|Часов после полуночи (0-23)|
|**tm_isdst**|Положительно, если действует летнее время; 0 если летнее время не действует; отрицательно, если состояние летнего времени неизвестно. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST).|
|**tm_mday**|День месяца (1-31)|
|**tm_min**|Минут после часа (0-59)|
|**tm_mon**|Месяц (0-11; Январь = 0)|
|**tm_sec**|Секунды после минуты (0-59)|
|**tm_wday**|День недели (0-6; Воскресенье = 0)|
|**tm_yday**|День года (0-365; 1 января = 0)|
|**tm_year**|Год (текущий год минус 1900)|

Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. Дополнительные сведения о настройке местного времени см. в описании функций [time](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md) и [localtime](localtime-localtime32-localtime64.md). Сведения об определении среды часового пояса и глобальных переменных см. в описании функции [_tzset](tzset.md).

Строковый результат, формируемый **asctime** , содержит ровно 26 символов и имеет `Wed Jan 02 02:03:55 1980\n\0`форму. Время в 24-часовом формате. Все поля имеют постоянную ширину. Символ новой строки и нуль-символ занимают две последние позиции строки. **asctime** использует один статически выделенный буфер для хранения возвращаемой строки. Каждый вызов этой функции уничтожает результат предыдущего вызова.

**_wasctime** — это версия **asctime**с расширенными символами. в противном случае **_wasctime** и **asctime** работают одинаково.

Эти функции проверяют свои параметры. Если *timeptr* является пустым указателем или содержит значения вне допустимого диапазона, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает **значение NULL** и **устанавливает** для **еинвал**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mapping"></a>Сопоставление универсальных текстовых функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime**|**asctime**|**asctime**|**_wasctime**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**asctime**|\<time.h>|
|**_wasctime**|\<time.h> или \<wchar.h>|

## <a name="example"></a>Пример

Эта программа помещает системное время в длинное целое число **аклокк**, преобразует его в структуру **невтиме** и затем преобразовывает в виде строки для вывода, используя функцию **asctime** .

```C
// crt_asctime.c
// compile with: /W3

#include <time.h>
#include <stdio.h>

int main( void )
{
    struct tm   *newTime;
    time_t      szClock;

    // Get time in seconds
    time( &szClock );

    // Convert time to struct tm form
    newTime = localtime( &szClock );

    // Print local time as a string.
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996
    // Note: asctime is deprecated; consider using asctime_s instead
}
```

```Output
Current date and time: Sun Feb 03 11:38:58 2002
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
