---
title: _tzset
ms.date: 4/2/2020
api_name:
- _tzset
- _o__tzset
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
- _tzset
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
ms.openlocfilehash: 0791fe6002b751906c6bc6f83dafe1ccf202bc8b
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562029"
---
# <a name="_tzset"></a>_tzset

Задает переменные среды, относящиеся ко времени.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
void _tzset( void );
```

## <a name="remarks"></a>Примечания

Функция **_tzset** использует текущее **значение переменной среды, чтобы** присвоить значения трем глобальным переменным: **_daylight**, **_timezone**и **_tzname**. Эти переменные используются функциями [_ftime](ftime-ftime32-ftime64.md) и [localtime](localtime-localtime32-localtime64.md) для внесения исправлений с всеобщего скоординированного времени (UTC) в местное время, а функция [времени](time-time32-time64.md) — для расчета времени в формате UTC из системного времени. Чтобы задать переменную **среды,** используйте следующий синтаксис:

> **Set**_ТЗН_ \[ **+**&#124;**-** ]*чч* \[ **:**_мм_ \[ **:**_СС_]] [*дзн*]

 *тзн* \
 Трехбуквенное имя часового пояса, например, PST. Необходимо указать правильное смещение локального времени относительно времени в формате UTC.

 *формате* \
 Различие в часах между временем в формате UTC и местным временем. Знак (+) для положительных значений необязателен.

 *мм* \
 Минуты. Отделен от *чч* двоеточием (**:**).

 *НН* \
 Секунды. Отделен от *mm* двоеточием (**:**).

 *дзн* \
 Трехбуквенный часовой пояс с переходом на летнее время, например, PDT. Если переход на летнее время на локальном компьютере никогда не действует **, задайте для параметра** *дзн*значение без значения. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST).

> [!NOTE]
> Не забывайте о вычислении знака разницы во времени. Поскольку разница во времени является смещением локального времени относительно времени в формате UTC (а не наоборот), ее знак может отличаться от интуитивно ожидаемого. Для часовых поясов до пояса времени в формате UTC разница во времени отрицательная; для часовых поясов после пояса времени в формате UTC разница положительная.

Например, чтобы задать переменную **окружения** в соответствии с текущим часовым поясом в Германии, введите в командной строке следующее:

> **Set 1GDT = GST-**

Эта команда использует GST для указания немецкого стандартного времени, учитывая, что время в формате UTC отстает на один час от времени в Германии (или, другими словами, что время в Германии на один час опережает время в формате UTC) и учитывая, что Германия использует переход на летнее время.

Если значение **свойства, указанное в** параметре, не задано, **_tzset** пытается использовать сведения о часовом поясе, указанные операционной системой. В операционной системе Windows эти данные определяются в приложении Дата/время в Панели управления. Если **_tzset** не может получить эти сведения, по умолчанию используется PST8PDT, что означает тихоокеанское значение часового пояса.

В зависимости от значения **переменной среды, в глобальные** переменные присваиваются следующие значения **_daylight**, **_timezone**и **_tzname** при вызове **_tzset** :

|Глобальная переменная|Описание|Значение по умолчанию|
|---------------------|-----------------|-------------------|
|**_daylight**|Ненулевое значение, если в параметре "летнее время" **указано значение "** часовой пояс". в противном случае — значение 0.|1|
|**_timezone**|Разница в секундах между местным временем и временем в формате UTC.|28800 (28800 секунд равны 8 часам)|
|**_tzname**[0]|Строковое значение имени часового **пояса из переменной** среды, пусто **, если параметрические значения не заданы** .|PST|
|**_tzname**[1]|Строковое значение летнего времени для часового пояса; пусто, если часовой пояс с переходом на летнее время не **указан в переменной** среды,|PDT|

Значения по умолчанию, приведенные в предыдущей таблице для **_daylight** и массив **_tzname** , соответствуют "PST8PDT". Если зона летнего времени пропущена **в переменной среды,** значение **_daylight** равно 0, а функции [_ftime](ftime-ftime32-ftime64.md), [gmtime](gmtime-gmtime32-gmtime64.md)и [localtime](localtime-localtime32-localtime64.md) возвращают 0 для флагов летнего времени.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_tzset**|\<time.h>|

Функция **_tzset** относится только к Microsoft. Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_tzset.cpp
// This program uses _tzset to set the global variables
// named _daylight, _timezone, and _tzname. Since TZ is
// not being explicitly set, it uses the system time.

#include <time.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    _tzset();
    int daylight;
    _get_daylight( &daylight );
    printf( "_daylight = %d\n", daylight );
    long timezone;
    _get_timezone( &timezone );
    printf( "_timezone = %ld\n", timezone );
    size_t s;
    char tzname[100];
    _get_tzname( &s, tzname, sizeof(tzname), 0 );
    printf( "_tzname[0] = %s\n", tzname );
    exit( 0 );
}
```

```Output
_daylight = 1
_timezone = 28800
_tzname[0] = Pacific Standard Time
```

## <a name="see-also"></a>См. также

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
