---
title: Класс TraceInfo
description: Ссылка на класс SDK TraceInfo.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 75d53937e3999f5692dee0ecf419e0ce5f49a274
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324174"
---
# <a name="traceinfo-class"></a>Класс TraceInfo

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `TraceInfo` используется для доступа к полезным свойствам о анализируемом или перелогированном следе.

## <a name="syntax"></a>Синтаксис

```cpp
class TraceInfo
{
public:
    TraceInfo(const TRACE_INFO_DATA& data);

    const unsigned long& LogicalProcessorCount() const;

    const long long& TickFrequency() const;
    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;

    std::chrono::nanoseconds Duration() const;
};
```

## <a name="remarks"></a>Примечания

`StartTimestamp` Вычтите `StopTimestamp` из, чтобы получить количество клещей, прошедших в течение всего следа. Используйте `TickFrequency` для преобразования полученного значения в единицу времени. Пример преобразования тиков во время можно [EVENT_DATA.](../c-event-data-types/event-data-struct.md)

Если вы не хотите преобразовывать `TraceInfo` тики самостоятельно, класс предоставляет функцию члена, которая возвращает продолжительность трассировки в наносекундах. Используйте стандартную `chrono` библиотеку СЗ, чтобы преобразовать это значение в другие единицы времени.

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

[TraceInfo](#trace-info)

### <a name="functions"></a>Функции

[Длительность](#duration)
[LogicalProcessorCount](#logical-processor-count)
[StartTimestamp](#start-timestamp)
[StopTimestamp](#stop-timestamp)
[TickFrequency](#tick-frequency)

## <a name="duration"></a><a name="duration"></a>Длительность

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Возвращаемое значение

Продолжительность активности в наносекундах.

## <a name="logicalprocessorcount"></a><a name="logical-processor-count"></a>ЛогическийПроцессорCount

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество логических процессоров на машине, где был собран след.

## <a name="starttimestamp"></a><a name="start-timestamp"></a>StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение тика, захваченное во время запуска трассы.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a>Стоп-таймштамп

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение тика, захваченное во время остановки трассы.

## <a name="tickfrequency"></a><a name="tick-frequency"></a>ТикЧастота

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество тиков в секунду для использования при оценке продолжительности, измеренной в клещах.

## <a name="traceinfo"></a><a name="trace-info"></a>TraceInfo

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>Параметры

*Данных*\
Данные, содержащие информацию о следе.

::: moniker-end
