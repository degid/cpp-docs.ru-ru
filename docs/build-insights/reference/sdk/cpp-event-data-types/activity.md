---
title: Класс Activity
description: Ссылка на класс активности SDK Построить СЗД.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2ea04150aec9c0b2366d97e6e4c15de557a4f47c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325249"
---
# <a name="activity-class"></a>Класс Activity

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Activity` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия любому событию активности. Обратитесь в [таблицу событий,](../event-table.md) чтобы просмотреть все события, которые могут быть сопоставлены с классом. `Activity`

## <a name="syntax"></a>Синтаксис

```cpp
class Activity : public Event
{
public:
    Activity(const RawEvent& event);

    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;
    const long long& ExclusiveDurationTicks() const;
    const long long& CPUTicks() const;
    const long long& ExclusiveCPUTicks() const;
    const long long& WallClockTimeResponsibilityTicks() const;
    const long long& ExclusiveWallClockTimeResponsibilityTicks() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>Примечания

Несколько функций `Activity` участника в классе возвращают количество тиков. В качестве источника тиков используется счетчик производительности Windows. Подсчет тиков должен использоваться с частотой тика, чтобы преобразовать его в единицу времени, такую как секунды. Функция `TickFrequency` участника, доступная в базовом классе [Event,](event.md) может быть вызвана для получения частоты тика. На [странице EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) показан пример преобразования тиков в единицу времени.

Если вы не хотите преобразовывать тики `Activity` в единицы времени самостоятельно, класс предоставляет функции членов, которые возвращают значения времени в наносекундах. Используйте стандартную `chrono` библиотеку СЗ, чтобы преобразовать их в другие единицы времени.

## <a name="members"></a>Участники

Наряду со своими членами, унаследованные от базового класса [Event,](event.md) `Activity` класс содержит следующие члены:

### <a name="constructor"></a>Конструктор

[Действие](#activity)

### <a name="functions"></a>Функции

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Длительность](#duration)\
[ЭксклюзивныеCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ЭксклюзивныеDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeОтветственность](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeОтветственностьTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[StartTimestamp](#start-timestamp)\
[Стоп-таймштамп](#stop-timestamp)\
[WallClockTimeОтветственность](#wall-clock-time-responsibility)\
[WallClockTimeОтветственностьTicks](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a><a name="activity"></a> Действие

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Любое событие активности.

## <a name="cputicks"></a><a name="cpu-ticks"></a>CPUTicks

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество тиков процессора, которые произошли во время этого действия. Тик процессора отличается от обычного тика. Клещи процессора учитываются только тогда, когда CPU исполняет код в действии. Тики процессора не учитываются при сном потоке, связанном с действием.

## <a name="cputime"></a><a name="cpu-time"></a>CPUTime

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>Возвращаемое значение

Время выполнения процессором кода внутри этого действия. Это значение может быть выше, чем продолжительность действия, если действия ребенка выполняются на отдельных потоках. Значение возвращается в наносекундах.

## <a name="duration"></a><a name="duration"></a>Длительность

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Продолжительность активности в наносекундах.

## <a name="exclusivecputicks"></a><a name="exclusive-cpu-ticks"></a>ЭксклюзивныеCPUTicks

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

То же [самое, что и CPUTicks,](#cpu-ticks)но не включая клещи процессора, которые произошли в детской деятельности.

## <a name="exclusivecputime"></a><a name="exclusive-cpu-time"></a>ExclusiveCPUTime

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>Возвращаемое значение

То же самое, что [и CPUTime](#cpu-time), за исключением того, что время действия ребенка в цОС не включено.

## <a name="exclusiveduration"></a><a name="exclusive-duration"></a>ExclusiveDuration

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Продолжительность деятельности в наносекундах, не считая количества времени, затраченного на детскую деятельность.

## <a name="exclusivedurationticks"></a><a name="exclusive-duration-ticks"></a>ЭксклюзивныеDurationTicks

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество тиков, которые произошли в этом действии, исключая количество тиков, которые произошли в деятельности ребенка.

## <a name="exclusivewallclocktimeresponsibility"></a><a name="exclusive-wall-clock-time-responsibility"></a>ExclusiveWallClockTimeОтветственность

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Возвращаемое значение

То же, [что WallClockTimeResponsibility](#wall-clock-time-responsibility), но не включая настенные часы ответственность за деятельность ребенка.

## <a name="exclusivewallclocktimeresponsibilityticks"></a><a name="exclusive-wall-clock-time-responsibility-ticks"></a>ExclusiveWallClockTimeОтветственностьTicks

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

То же, [что WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks), но не включая настенные часы ответственность тикает деятельности ребенка.

## <a name="starttimestamp"></a><a name="start-timestamp"></a>StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение тика, захваченное во время начала действия.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a>Стоп-таймштамп

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение тика, захваченное во время остановки действия.

## <a name="wallclocktimeresponsibility"></a><a name="wall-clock-time-responsibility"></a>WallClockTimeОтветственность

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Возвращаемое значение

Настенные часы ответственность за эту деятельность, в наносекундах. Для получения дополнительной информации о том, что настенные часы время ответственность означает, см [WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks).

## <a name="wallclocktimeresponsibilityticks"></a><a name="wall-clock-time-responsibility-ticks"></a>WallClockTimeОтветственностьTicks

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Возвращаемое значение

Подсчет тиков, представляющий вклад этой деятельности в общее время настенных часов. Настенные часы время ответственность тик отличается от обычного тика. Ответственность за время стены учитывает параллелизм между действиями. Два параллельных действия могут иметь продолжительность 50 тиков, и то же время начала и остановки. В этом случае обоим назначена ответственность за время настенных часов в размере 25 тиков.

::: moniker-end
