---
title: Класс IRelogger
description: Ссылка на класс SDK IRelogger.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 146377b2b44df43ed4b2f749efd9fb614a2a09c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329145"
---
# <a name="irelogger-class"></a>Класс IRelogger

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `IRelogger` предоставляет интерфейс для повторного отслеживания событий для отслеживания Windows (ETW). Он используется с функциями [MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md) и [MakeStaticReloggerGroup.](../functions/make-static-analyzer-group.md) Используйте `IRelogger` в качестве базового класса для создания собственного перелоггера, который может быть частью группы перелоггера.

## <a name="syntax"></a>Синтаксис

```cpp
class IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
    virtual AnalysisControl OnBeginRelogging();
    virtual AnalysisControl OnEndRelogging();
    virtual AnalysisControl OnBeginReloggingPass();
    virtual AnalysisControl OnEndReloggingPass() ;

    virtual ~IRelogger();
};
```

## <a name="remarks"></a>Примечания

Значение возврата по умолчанию для всех функций, которые не переопределены, находится `AnalysisControl::CONTINUE`под этим. Для получения дополнительной информации [см.](analysis-control-enum-class.md)

## <a name="members"></a>Участники

### <a name="destructor"></a>Деструктор

[Зарирегогер](#irelogger-destructor)

### <a name="functions"></a>Функции

[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnendReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStartActivity](#on-start-activity)\
[OnStopActivity](#on-stop-activity)\
[OnTraceInfo](#on-trace-info)

## <a name="irelogger"></a><a name="irelogger-destructor"></a>Зарирегогер

Уничтожает класс IRelogger.

```cpp
virtual ~IRelogger();
```

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a>OnBeginRelogging

Эта функция вызывается до начала пропуска relogging.

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a>OnBeginReloggingPass

Эта функция называется в начале перезаписи.

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a>OnEndRelogging

Эта функция вызывается после окончания пропуска для перезаписи.

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a>OnendReloggingPass

Эта функция называется в конце перезаписи.

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onsimpleevent"></a><a name="on-simple-event"></a>OnSimpleEvent

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

Эта функция вызывается при обработке простого события.

### <a name="parameters"></a>Параметры

*EventStack*\
Стек события для этого простого события. Для получения дополнительной информации [Events](../event-table.md)о стеках событий см.

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onstartactivity"></a><a name="on-start-activity"></a>OnStartActivity

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

Эта функция вызывается при обработке события начала действия.

### <a name="parameters"></a>Параметры

*EventStack*\
Стек события для этого события начала события. Для получения дополнительной информации [Events](../event-table.md)о стеках событий см.

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a>OnStopActivity

Эта функция вызывается при обработке события остановки активности.

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>Параметры

*EventStack*\
Стек события для этого события остановки события. Для получения дополнительной информации [Events](../event-table.md)о стеках событий см.

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="ontraceinfo"></a><a name="on-trace-info"></a>OnTraceInfo

```cpp
virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
```

Эта функция называется один раз в начале каждого анализа или перезаписи прохода.

### <a name="parameters"></a>Параметры

*traceInfo*\
Объект [TraceInfo,](../cpp-event-data-types/trace-info.md) содержащий полезные свойства о потребляемом следе.

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

::: moniker-end
