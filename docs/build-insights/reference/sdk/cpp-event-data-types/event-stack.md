---
title: Класс EventStack
description: Ссылка на класс SDK EventStack.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: eaaaedcbf57fdaf8e437a80a7823488febac3e1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324982"
---
# <a name="eventstack-class"></a>Класс EventStack

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `EventStack` представляет собой набор объектов [событий.](event.md) Все события, полученные от SDK Build Insights, `EventStack` происходят в виде объекта. Последней записью в этом стеке является событие, которое в настоящее время обрабатывается. Записи, предшествующие последней записи, являются родительской иерархией текущего события. Для получения более подробной информации о модели событий, используемой в исследованиях сc, смотрите [таблицу событий](../event-table.md).

## <a name="syntax"></a>Синтаксис

```cpp
class EventStack
{
public:
    EventStack(const EVENT_COLLECTION_DATA& data);

    size_t      Size() const;
    RawEvent    Back() const;
    RawEvent    operator[] (size_t index) const;
};
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

[EventStack](#event-stack)

### <a name="functions"></a>Функции

[Задний](#back)
[оператор (](#subscript-operator)
[Size](#size)

## <a name="back"></a><a name="back"></a>Назад

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [RawEvent,](raw-event.md) представляющий последнюю запись в стеке. Последняя запись в стеке события — это событие, которое было срабатывано.

## <a name="eventstack"></a><a name="event-stack"></a>EventStack

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>Параметры

*Данных*\
Необработанные данные, из которых построен. `EventStack`

### <a name="remarks"></a>Примечания

Обычно вам не нужно `EventStack` строить объекты самостоятельно. Они предоставляются вам SDK Build Insights, когда события обрабатываются во время анализа или сеанса перезаписи.

## <a name="operator"></a><a name="subscript-operator"></a>оператор

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>Параметры

*Индекс*\
Индекс элемента для доступа в стеке события.

### <a name="return-value"></a>Возвращаемое значение

Объект [RawEvent,](raw-event.md) представляющий событие, хранящееся в положении, указанном *индексом* в стеке события.

## <a name="size"></a><a name="size"></a> Размер

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер стека событий.

::: moniker-end
