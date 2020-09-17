---
title: Класс IAnalyzer
description: Ссылка на класс SDK IAnalyzer по сборке СЗ.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IAnalyzer
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: be9d80bb94450458c73fd6ce8d908985ba6f293d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329174"
---
# <a name="ianalyzer-class"></a>Класс IAnalyzer

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `IAnalyzer` предоставляет интерфейс для анализа отслеживания событий для отслеживания Windows (ETW). Он используется с функциями [MakeDynamicAnalyzerGroup,](../functions/make-dynamic-analyzer-group.md) [MakeDynamicReloggerGroup,](../functions/make-dynamic-relogger-group.md) [MakeStaticAnalyzerGroup](../functions/make-dynamic-analyzer-group.md)и [MakeStaticReloggGroup.](../functions/make-static-analyzer-group.md) Используйте `IAnalyzer` в качестве базового класса для создания собственного анализатора, который может быть частью группы анализатора или перелога.

## <a name="syntax"></a>Синтаксис

```cpp
class IAnalyzer : public IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
    virtual AnalysisControl OnStopActivity(const EventStack& eventStack)
    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
    virtual AnalysisControl OnBeginAnalysis();
    virtual AnalysisControl OnEndAnalysis();
    virtual AnalysisControl OnBeginAnalysisPass();
    virtual AnalysisControl OnEndAnalysisPass();

    AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnBeginRelogging() final;
    AnalysisControl OnEndRelogging() final;
    AnalysisControl OnBeginReloggingPass() final;
    AnalysisControl OnEndReloggingPass() final;

    virtual ~IAnalyzer();
};
```

## <a name="remarks"></a>Примечания

Полученные классы `IAnalyzer` могут использоваться как в качестве анализаторов, так и в релоггерах. При использовании в качестве релоггеров функции релоггера перенаправляются на эквивалент анализатора. Обратное не верно: класс, который `IRelogger` происходит от не может быть использован в качестве анализатора. Использование анализатора в группе перелогов является общим шаблоном. При размещении в раннем положении группы релоггеров анализатор может предварительно вычислить информацию и сделать ее доступной для релоггеров в более поздних позициях.

Значение возврата по умолчанию для всех функций, которые не переопределены, находится `AnalysisControl::CONTINUE`под этим. Для получения дополнительной информации [см.](analysis-control-enum-class.md)

## <a name="members"></a>Участники

В дополнение к участнику [OnTraceInfo](irelogger-class.md#on-trace-info) из интерфейса, `IRelogger` `IAnalyzer` класс содержит следующие элементы:

### <a name="destructor"></a>Деструктор

[ЗиАнализ](#ianalyzer-destructor)

### <a name="functions"></a>Функции

[OnBeginAnalysis](#on-begin-analysis)\
[OnBeginAnalysisPass](#on-begin-analysis-pass)\
[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndAnalysis](#on-end-analysis)\
[OnEndAnalysisPass](#on-end-analysis-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnendReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStartActivity](#on-start-activity)\
[OnStopActivity](#on-stop-activity)

## <a name="ianalyzer"></a><a name="ianalyzer-destructor"></a>ЗиАнализ

Уничтожает класс IAnalyzer.

```cpp
virtual ~IAnalyzer();
```

## <a name="onbeginanalysis"></a><a name="on-begin-analysis"></a>OnBeginAnalysis

Для анализаторов, входят в группу анализаторов, эта функция называется до начала первого прохода анализа. Для анализаторов, входящих в группу перелогов, эта функция вызывается до начала прохождения перезаписи. Для анализаторов, входящих в группу анализаторов и релоггеров одного и того же сеанса relogging, эта функция называется дважды до начала первого прохода анализа.

```cpp
virtual AnalysisControl OnBeginAnalysis();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onbeginanalysispass"></a><a name="on-begin-analysis-pass"></a>OnBeginAnalysisPass

Для анализаторов, входят в группу анализаторов, эта функция называется в начале каждого анализа. Для анализаторов, внеех группы релоггеров, эта функция вызывается в начале перелога. Для анализаторов, входящих как в группу анализаторов, так и в группу релогга одного и того же сеанса relogging, эта функция вызывается в начале каждого прохода анализа и в начале перелога.

```cpp
virtual AnalysisControl OnBeginAnalysisPass();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a>OnBeginRelogging

```cpp
AnalysisControl OnBeginRelogging() final;
```

Эта функция не может быть переопределена. Это называется SDK Build Insights, когда анализатор является частью группы перелогов. Эта функция перенаправляет вызов на [OnBeginAnalysis.](#on-begin-analysis)

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [OnBeginAnalysis.](#on-begin-analysis)

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a>OnBeginReloggingPass

Эта функция не может быть переопределена. Это называется SDK Build Insights, когда анализатор является частью группы перелогов. Эта функция перенаправляет вызов на [OnBeginAnalysisPass.](#on-begin-analysis-pass)

```cpp
AnalysisControl OnBeginReloggingPass() final;
```

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [OnBeginAnalysisPass.](#on-begin-analysis-pass)

## <a name="onendanalysis"></a><a name="on-end-analysis"></a>OnEndAnalysis

Для анализаторов, входят в группу анализаторов, эта функция называется после окончания последнего прохода анализа. Для анализаторов, входящих в группу перелоггеров, эта функция называется после окончания прохода перезаписи. Для анализаторов, которые являются частью группы анализатора и перелогера одного и того же сеанса relogging, эта функция называется дважды:

1. после того, как все анализ проходит закончились и до начала перезаписи проход начинается, и
1. после окончания перезаписи.

```cpp
virtual AnalysisControl OnEndAnalysis();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onendanalysispass"></a><a name="on-end-analysis-pass"></a>OnEndAnalysisPass

Для анализаторов, входят в группу анализаторов, эта функция называется в конце каждого анализа. Для анализаторов, внеех группы перелоггеров, эта функция вызывается в конце прохода relogger. Для анализаторов, входящих как в группу анализаторов, так и в группу релогга одного и того же сеанса relogging, эта функция вызывается в конце каждого прохода анализа и в конце прохода relogger.

```cpp
virtual AnalysisControl OnEndAnalysisPass();
```

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a>OnEndRelogging

Эта функция не может быть переопределена. Это называется SDK Build Insights, когда анализатор является частью группы перелогов. Эта функция перенаправляет вызов на [OnEndAnalysis.](#on-end-analysis)

```cpp
AnalysisControl OnEndRelogging() final;
```

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [OnEndAnalysis.](#on-end-analysis)

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a>OnendReloggingPass

Эта функция не может быть переопределена. Это называется SDK Build Insights, когда анализатор является частью группы перелогов. Эта функция перенаправляет вызов [на OnEndAnalysisPass.](#on-end-analysis-pass)

```cpp
AnalysisControl OnEndReloggingPass() final;
```

### <a name="return-value"></a>Возвращаемое значение

Результат вызова [OnEndAnalysisPass.](#on-end-analysis-pass)

## <a name="onsimpleevent"></a><a name="on-simple-event"></a>OnSimpleEvent

Эта функция вызывается при обработке простого события. Вторая версия этой функции не может быть переопределена. Это называется SDK Build Insights, когда анализатор является частью группы перелогов. Все вызовы в версию 2 перенаправляются в версию 1.

### <a name="version-1"></a>версия 1

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

### <a name="version-2"></a>версия 2

```cpp
AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Параметры

*EventStack*\
Стек события для этого простого события. Для получения дополнительной информации [Events](../event-table.md)о стеках событий см.

*relogСессия*\
Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onstartactivity"></a><a name="on-start-activity"></a>OnStartActivity

Эта функция вызывается при обработке события начала действия. Вторая версия этой функции не может быть переопределена. Это называется SDK Build Insights, когда анализатор является частью группы перелогов. Все вызовы в версию 2 перенаправляются в версию 1.

### <a name="version-1"></a>версия 1

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>версия 2

```cpp
AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Параметры

*EventStack*\
Стек события для этого события начала события. Для получения дополнительной информации [Events](../event-table.md)о стеках событий см.

*relogСессия*\
Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a>OnStopActivity

Эта функция вызывается при обработке события остановки активности. Вторая версия этой функции не может быть переопределена. Это называется SDK Build Insights, когда анализатор является частью группы перелогов. Все вызовы в версию 2 перенаправляются в версию 1.

### <a name="version-1"></a>версия 1

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>версия 2

```cpp
AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Параметры

*EventStack*\
Стек события для этого события остановки события. Для получения дополнительной информации [Events](../event-table.md)о стеках событий см.

*relogСессия*\
Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Код [AnalysisControl,](analysis-control-enum-class.md) описывающий, что должно произойти дальше.

::: moniker-end
