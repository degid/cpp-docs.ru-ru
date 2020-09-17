---
title: Средства диагностики параллельного выполнения (среда выполнения с параллелизмом)
ms.date: 11/04/2016
helpviewer_keywords:
- Parallel Diagnostic Tools [Concurrency Runtime]
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
ms.openlocfilehash: 34b2421dfc53deeb35dcc659a8d555983e583737
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510496"
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>Средства диагностики параллельного выполнения (среда выполнения с параллелизмом)

Visual Studio предоставляет расширенную поддержку отладки и профилирования многопоточных приложений.

## <a name="debugging"></a>Отладка

Отладчик Visual Studio включает окно Параллельные **стеки** , окно **параллельных задач** и окно параллельных **контрольных значений** . Дополнительные сведения см. в разделе [Пошаговое руководство: Отладка параллельного](/visualstudio/debugger/walkthrough-debugging-a-parallel-application) приложения [и выполнение следующих действий: Используйте окно](/visualstudio/debugger/how-to-use-the-parallel-watch-window)параллельные контрольные значения.

## <a name="profiling"></a>Профилирование

Средства профилирования предоставляют три представления данных, в которых отображаются графические, табличные и числовые сведения о взаимодействии многопоточного приложения с самим собой и с другими программами. Представления позволяют быстро выявить области проблем и переходить от точек графических экранов к стекам вызовов, сайтам вызовов и исходному коду. Дополнительные сведения см. в разделе [Визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer).

## <a name="event-tracing"></a>Трассировка событий

Среда выполнения с параллелизмом использует [трассировку событий Windows](/windows/win32/ETW/event-tracing-portal) (ETW) для уведомления средств инструментирования, таких как профилировщики, при возникновении различных событий. Эти события включают в себя, когда планировщик активируется или деактивируется, когда контекст запускается, завершается, блокируется, разблокируется или выдается, а также при начале или окончании параллельного алгоритма.

Такие средства, как [Визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer) , используют эту функцию. Таким образом, обычно не требуется работать с этими событиями напрямую. Однако эти события полезны при разработке пользовательского профилировщика или при использовании таких средств трассировки событий, как [Xperf](https://go.microsoft.com/fwlink/p/?linkid=160628).

Среда выполнения с параллелизмом вызывает эти события только при включенной трассировке. Вызовите функцию [concurrency::EnableTracing](reference/concurrency-namespace-functions.md#enabletracing) , чтобы включить трассировку событий и функцию [concurrency::DisableTracing](reference/concurrency-namespace-functions.md#disabletracing) , чтобы отключить трассировку.

В следующей таблице описаны события, которые среда выполнения вызывает при включенной трассировке событий.

|событие|Описание|Значение|
|-----------|-----------------|-----------|
|[concurrency::ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)|Идентификатор поставщика трассировки событий Windows для среда выполнения с параллелизмом.|`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|
|[concurrency::ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)|Отмечает события, связанные с контекстами.|`5727a00f-50be-4519-8256-f7699871fecb`|
|[concurrency::PPLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)|Помечает вход и Exit для вызовов алгоритма [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) .|`31c8da6b-6165-4042-8b92-949e315f4d84`|
|[concurrency::PPLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)|Помечает вход и Exit для вызовов алгоритма [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) .|`5cb7d785-9d66-465d-bae1-4611061b5434`|
|[concurrency::P Плпараллелинвокивентгуид](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|Помечает вход и Exit для вызовов алгоритма [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) .|`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|
|[concurrency::SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)|Отмечает события, связанные с [планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md).|`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|
|[concurrency::VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)|Отмечает события, связанные с виртуальными процессорами.|`2f27805f-1676-4ecc-96fa-7eb09d44302f`|

Среда выполнения с параллелизмом определяет, но в настоящее время не вызывает следующие события. Среда выполнения резервирует эти события для будущего использования:

- [concurrency::ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)

- [concurrency::ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)

- [concurrency::ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)

- [concurrency::LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)

- [concurrency::ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)

Перечисление [concurrency::ConcRT_EventType](reference/concurrency-namespace-enums.md#concrt_eventtype) указывает возможные операции, которые отслеживает событие. Например, во время входа `parallel_for` алгоритма среда выполнения `PPLParallelForEventGuid` создает событие и предоставляет `CONCRT_EVENT_START` его в качестве операции. Перед возвратом `PPLParallelForEventGuid`алгоритма среда выполнения снова создает событие и предоставляет `CONCRT_EVENT_END` его в качестве операции. `parallel_for`

В следующем примере показано, как включить трассировку для вызова `parallel_for`. Среда выполнения не выполняет трассировку первого вызова, `parallel_for` так как трассировка не включена. Вызов метода `EnableTracing` позволяет среде выполнения выполнить трассировку второго `parallel_for`вызова.

[!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]

Среда выполнения отслеживает количество вызовов `EnableTracing` и. `DisableTracing` Поэтому при многократном вызове `EnableTracing` для отключения трассировки необходимо вызвать `DisableTracing` одинаковое число раз.

## <a name="see-also"></a>См. также

[Среда выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime.md)
