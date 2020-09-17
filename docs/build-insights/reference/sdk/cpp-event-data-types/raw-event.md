---
title: Класс RawEvent
description: Ссылка на исследования в отношении справок о сборке SDK RawEvent.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RawEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 83629457ac3a0d1f991f6b084af2f3400612b2ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324383"
---
# <a name="rawevent-class"></a>Класс RawEvent

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `RawEvent` используется для представления общего события в [EventStack.](event-stack.md)

## <a name="syntax"></a>Синтаксис

```cpp
class RawEvent
{
public:
    RawEvent(const EVENT_DATA& event);

    const unsigned short&        EventId() const;
    const unsigned long long&    EventInstanceId() const;
    const long long&             TickFrequency() const;
    const long long&             StartTimestamp() const;
    const long long&             StopTimestamp() const;
    const long long&             ExclusiveDurationTicks() const;
    const long long&             CPUTicks() const;
    const long long&             ExclusiveCPUTicks() const;
    const long long&             WallClockTimeResponsibilityTicks() const;
    const long long&             ExclusiveWallClockTimeResponsibilityTicks() const;
    const void*                  Data() const;
    const unsigned long&         ProcessId() const;
    const unsigned long&         ThreadId() const;
    const unsigned short&        ProcessorIndex() const;
    const char*                  EventName() const;
    const wchar_t*               EventWideName() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>Примечания

Несколько функций `RawEvent` участника в классе возвращают количество тиков. В качестве источника тиков используется счетчик производительности Windows. Подсчет тиков должен использоваться с частотой тика, чтобы преобразовать его в единицу времени, как секунды. Функция `TickFrequency` участника может быть вызвана для получения частоты тика. Например, на [странице EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) можно примером того, как преобразовать тики в единицу времени.

Если вы не хотите преобразовывать `RawEvent` тики самостоятельно, класс предоставляет функции членов, которые возвращают значения времени в наносекундах. Используйте стандартную `chrono` библиотеку СЗ, чтобы преобразовать наносекунды в другие единицы времени.

## <a name="members"></a>Участники

### <a name="constructor"></a>Конструктор

[RawEvent](#raw-event)

### <a name="functions"></a>Функции

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Данных](#data)\
[Длительность](#duration)\
[EventId](#event-id)
[EventInstanceId](#event-instance-id)
[EventName](#event-name)\
[EventWideName](#event-wide-name)\
[ЭксклюзивныеCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ЭксклюзивныеDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeОтветственность](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeОтветственностьTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[ProcessId](#process-id)\
[ПроцессорИндекс](#processor-index)\
[StartTimestamp](#start-timestamp)\
[Стоп-таймштамп](#stop-timestamp)\
[ThreadId](#thread-id)\
[ТикЧастота](#tick-frequency)\
[WallClockTimeОтветственность](#wall-clock-time-responsibility)\
[WallClockTimeОтветственностьTicks](#wall-clock-time-responsibility-ticks)

## <a name="rawevent"></a><a name="raw-event"></a>RawEvent

```cpp
RawEvent(const EVENT_DATA& data);
```

### <a name="parameters"></a>Параметры

*Событие*\
Данные события.

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

## <a name="data"></a><a name="data"></a>Данных

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на дополнительные данные, содержащиеся в этом событии. Для получения дополнительной информации о том, как интерпретировать это поле, см [EVENT_DATA.](../c-event-data-types/event-data-struct.md)

## <a name="duration"></a><a name="duration"></a>Длительность

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Продолжительность активности в наносекундах.

## <a name="eventid"></a><a name="event-id"></a>Eventid

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер, идентифицирующие тип события. Список идентификаторов событий можно узнать [EVENT_ID.](../c-event-data-types/event-id-enum.md)

## <a name="eventinstanceid"></a><a name="event-instance-id"></a>EventInstanceId

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер, который однозначно идентифицирует событие внутри следа. Это значение не изменяется при анализе или повторном прослеживании одного и того же следа несколько раз. Используйте это значение для определения одного и того же события в нескольких анализа или перезаписи проходов по тому же следу.

## <a name="eventname"></a><a name="event-name"></a>EventName

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка ANSI, содержащая имя типа события, идентифицированного [EventId.](#event-id)

## <a name="eventwidename"></a><a name="event-wide-name"></a>EventWideName

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Широкая строка, содержащая имя типа события, идентифицированного [EventId.](#event-id)

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

## <a name="processid"></a><a name="process-id"></a>ProcessId

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор процесса, в котором произошло событие.

## <a name="processorindex"></a><a name="processor-index"></a>ПроцессорИндекс

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс с нулевым уровнем для логического процессора, на котором произошло событие.

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

## <a name="threadid"></a><a name="thread-id"></a>ThreadId

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор для потока, в котором произошло событие.

## <a name="tickfrequency"></a><a name="tick-frequency"></a>ТикЧастота

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество тиков в секунду для использования при оценке продолжительности, измеренной в тиках для этого события.

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

Подсчет тиков, представляющий вклад этой деятельности в общее время настенных часов. Настенные часы время ответственность тик отличается от обычного тика. Ответственность за время стены учитывает параллелизм между действиями. Два параллельных действия могут иметь продолжительность 50 тиков и одно и то же время начала и остановки. В этом случае обоим назначена ответственность за время настенных часов в размере 25 тиков.

::: moniker-end
