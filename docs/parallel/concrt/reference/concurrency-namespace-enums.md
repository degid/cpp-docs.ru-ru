---
title: Перечисления пространства имен concurrency
ms.date: 11/04/2016
f1_keywords:
- CONCRT/concurrency::Agents_EventType
- CONCRT/concurrency::Concrt_TraceFlags
- CONCRT/concurrency::CriticalRegionType
- CONCRT/concurrency::PolicyElementKey
- CONCRT/concurrency::SchedulerType
- CONCRT/concurrency::SwitchingProxyState
- CONCRT/concurrency::WinRTInitializationType
- CONCRT/concurrency::join_type
- CONCRT/concurrency::message_status Enumeration
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
ms.openlocfilehash: 8b9aec0a3464b921ca80f731ac4a3c26e72ef34e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832247"
---
# <a name="concurrency-namespace-enums"></a>Перечисления пространства имен concurrency

:::row:::
   :::column span="":::
      [`agent_status`](#agent_status)\
      [`Agents_EventType`](#agents_eventtype)\
      [`ConcRT_EventType`](#concrt_eventtype)\
      [`Concrt_TraceFlags`](#concrt_traceflags)\
      [`CriticalRegionType`](#criticalregiontype)
   :::column-end:::
   :::column span="":::
      [`DynamicProgressFeedbackType`](#dynamicprogressfeedbacktype)\
      [`join_type`](#join_type)\
      [`message_status`](#message_status)\
      [`PolicyElementKey`](#policyelementkey)\
      [`SchedulerType`](#schedulertype)
   :::column-end:::
   :::column span="":::
      [`SchedulingProtocolType`](#schedulingprotocoltype)\
      [`SwitchingProxyState`](#switchingproxystate)\
      [`task_group_status`](#task_group_status)\
      [`WinRTInitializationType`](#winrtinitializationtype)
   :::column-end:::
:::row-end:::

## <a name="agent_status-enumeration"></a><a name="agent_status"></a> Перечисление agent_status

Допустимые состояния для объекта `agent`.

```cpp
enum agent_status;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`agent_canceled`|Объект `agent` отменен.|
|`agent_created`|Объект `agent` создан, но не запущен.|
|`agent_done`|`agent`Завершение без отмены.|
|`agent_runnable`|Был `agent` запущен, но не введен `run` метод.|
|`agent_started`|`agent`Запущен.|

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронные агенты](../../../parallel/concrt/asynchronous-agents.md).

### <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

## <a name="agents_eventtype-enumeration"></a><a name="agents_eventtype"></a> Перечисление Agents_EventType

Типы событий, которые можно отслеживать с помощью функции трассировки, предоставляемой библиотекой агентов.

```cpp
enum Agents_EventType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`AGENTS_EVENT_CREATE`|Тип события, который представляет создание объекта|
|`AGENTS_EVENT_DESTROY`|Тип события, который представляет удаление объекта|
|`AGENTS_EVENT_END`|Тип события, который представляет завершение некоторой обработки|
|`AGENTS_EVENT_LINK`|Тип события, который представляет связывание блоков сообщений|
|`AGENTS_EVENT_NAME`|Тип события, который представляет имя для объекта|
|`AGENTS_EVENT_SCHEDULE`|Тип события, который представляет расписание процесса|
|`AGENTS_EVENT_START`|Тип события, который представляет запуск некоторой обработки|
|`AGENTS_EVENT_UNLINK`|Тип события, который представляет отвязку блоков сообщений|

### <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

## <a name="concrt_eventtype-enumeration"></a><a name="concrt_eventtype"></a> Перечисление ConcRT_EventType

Типы событий, которые можно отслеживать с помощью функций трассировки, обеспечиваемых средой выполнения с параллелизмом.

```cpp
enum ConcRT_EventType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`CONCRT_EVENT_ATTACH`|Тип события, представляющий действие присоединения к планировщику.|
|`CONCRT_EVENT_BLOCK`|Тип события, представляющий акт блокирования контекста.|
|`CONCRT_EVENT_DETACH`|Тип события, представляющий действие отсоединения от планировщика.|
|`CONCRT_EVENT_END`|Тип события, отмечающий начало пары событий начала/окончания.|
|`CONCRT_EVENT_GENERIC`|Тип события, используемый для прочих событий.|
|`CONCRT_EVENT_IDLE`|Тип события, представляющий действие контекста, которое становится бездействующим.|
|`CONCRT_EVENT_START`|Тип события, отмечающий начало пары событий начала/окончания.|
|`CONCRT_EVENT_UNBLOCK`|Тип события, представляющий действие разблокировки контекста.|
|`CONCRT_EVENT_YIELD`|Тип события, представляющий акт выдается контекст.|

### <a name="requirements"></a>Требования

**Заголовок:** **пространство имен** ConcRT.h: Concurrency

## <a name="concrt_traceflags-enumeration"></a><a name="concrt_traceflags"></a> Перечисление Concrt_TraceFlags

Флажки трассировки для типов событий

```cpp
enum Concrt_TraceFlags;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`AgentEventFlag`||
|`AllEventsFlag`||
|`ContextEventFlag`||
|`PPLEventFlag`||
|`ResourceManagerEventFlag`||
|`SchedulerEventFlag`||
|`VirtualProcessorEventFlag`||

### <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

## <a name="criticalregiontype-enumeration"></a><a name="criticalregiontype"></a> Перечисление CriticalRegionType

Тип критической области, внутри которой находится контекст.

```cpp
enum CriticalRegionType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`InsideCriticalRegion`|Указывает, что контекст находится внутри критической области. В критической области асинхронные приостановки скрыты от планировщика. Если такая приостановка происходит, диспетчер ресурсов ждет, пока поток будет готов к запуску, и просто возобновит его вместо повторного вызова планировщика. Любые блокировки, сделанные внутри такого региона, должны быть выполнены крайне осторожно.|
|`InsideHyperCriticalRegion`|Указывает, что контекст находится внутри области, критической для Hyper-in. В области, критической для Hyper-in, синхронные и асинхронные приостановки будут скрыты от планировщика. Если произойдет такая приостановка или блокировка, диспетчер ресурсов ждет, пока поток станет готов к запуску, и просто возобновит его вместо повторного вызова планировщика. Блокировки, сделанные внутри такого региона, никогда не должны использоваться совместно с кодом, выполняющимся за пределами такого региона. Это вызовет непредсказуемую взаимоблокировку.|
|`OutsideCriticalRegion`|Указывает, что контекст находится вне любой критической области.|

### <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

## <a name="dynamicprogressfeedbacktype-enumeration"></a><a name="dynamicprogressfeedbacktype"></a> Перечисление DynamicProgressFeedbackType

Используется политикой `DynamicProgressFeedback` для описания того, будет ли к ресурсам планировщика применена повторная балансировка в соответствии со статистическими данными, полученными из планировщика, или только на основе перехода виртуальных процессоров в состояние бездействия и из него через вызовы методов `Activate` и `Deactivate` для интерфейса `IVirtualProcessorRoot`. Дополнительные сведения о доступных политиках планировщика см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).

```cpp
enum DynamicProgressFeedbackType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`ProgressFeedbackDisabled`|Планировщик не собирает сведения о ходе выполнения. Перераспределение выполняется только на уровне подписки базового аппаратного потока. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](IExecutionResource-structure.md).<br /><br /> Это значение зарезервировано для использования средой выполнения.|
|`ProgressFeedbackEnabled`|Планировщик собирает сведения о ходе выполнения и передает их в Диспетчер ресурсов. Диспетчер ресурсов будет использовать эти статистические сведения для перераспределения ресурсов от имени планировщика в дополнение к уровню подписки базового аппаратного потока. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](IExecutionResource-structure.md).|

## <a name="join_type-enumeration"></a><a name="join_type"></a> Перечисление join_type

Тип блока обмена сообщениями `join`.

```cpp
enum join_type;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`greedy`|Жадные `join` блоки обмена сообщениями немедленно принимают сообщение при распространении. Это более эффективно, но имеет возможность динамической блокировки в зависимости от конфигурации сети.|
|`non_greedy`|`join`Блоки обмена сообщениями, не являющиеся жадными, откладывают сообщения и пытаются их использовать после того, как все поступили. Они гарантированно работают, но выполняются медленнее.|

### <a name="requirements"></a>Требования

**Заголовок:** agents.h

## <a name="message_status-enumeration"></a><a name="message_status"></a> Перечисление message_status

Допустимые ответы на предложение объекта `message` блоку.

```cpp
enum message_status;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`accepted`|Цель приняла сообщение.|
|`declined`|Целевой объект не принял сообщение.|
|`missed`|Целевой объект попытался принять сообщение, но он больше не был доступен.|
|`postponed`|Целевой объект отложил сообщение.|

### <a name="requirements"></a>Требования

**Заголовок:** agents.h

## <a name="policyelementkey-enumeration"></a><a name="policyelementkey"></a> Перечисление PolicyElementKey

Ключи политики, описывающие аспекты поведения планировщика. Каждый элемент политики описан с помощью пары «ключ — значение». Дополнительные сведения о политиках планировщика и их влиянии на планировщики см. в разделе [планировщик задач](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

```cpp
enum PolicyElementKey;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`ContextPriority`|Приоритет потока операционной системы каждого контекста в планировщике. Если для этого раздела задано значение, `INHERIT_THREAD_PRIORITY` контексты в планировщике будут наследовать приоритет потока, создавшего планировщик.<br /><br /> Допустимые значения: любое из допустимых значений для `SetThreadPriority` функции Windows и специальное значение. `INHERIT_THREAD_PRIORITY`<br /><br /> Значение по умолчанию: `THREAD_PRIORITY_NORMAL`|
|`ContextStackSize`|Зарезервированный размер стека каждого контекста в планировщике в килобайтах.<br /><br /> Допустимые значения: положительные целые числа<br /><br /> Значение по умолчанию: `0` , указывающее, что используется значение по умолчанию для размера стека.|
|`DynamicProgressFeedback`|Определяет, будут ли перераспределяться ресурсы для планировщика в соответствии со статистической информацией, собранной из планировщика, или только на основе уровня подписки базовых аппаратных потоков. Дополнительные сведения см. в разделе [DynamicProgressFeedbackType](#dynamicprogressfeedbacktype).<br /><br /> Допустимые значения: член `DynamicProgressFeedbackType` перечисления, `ProgressFeedbackEnabled` либо `ProgressFeedbackDisabled`<br /><br /> Значение по умолчанию: `ProgressFeedbackEnabled`|
|`LocalContextCacheSize`|Если `SchedulingProtocol` для ключа политики задано значение `EnhanceScheduleGroupLocality` , это указывает максимальное количество доступных для выполнения контекстов, которые могут быть кэшированы в каждой локальной очереди виртуального процессора. Такие контексты обычно выполняются в порядке ЛИФО на виртуальном процессоре, который привел к готовности их к запуску. Обратите внимание, что этот ключ политики не имеет смысла, если `SchedulingProtocol` для ключа задано значение `EnhanceForwardProgress` .<br /><br /> Допустимые значения: неотрицательные целые числа<br /><br /> Значение по умолчанию: `8`|
|`MaxConcurrency`|Максимальный уровень параллелизма, требуемый планировщиком. Диспетчер ресурсов попытается изначально выделить столько виртуальных процессоров. Специальное значение [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) указывает, что требуемый уровень параллелизма совпадает с количеством аппаратных потоков на компьютере. Если значение, указанное для `MinConcurrency` , больше, чем число аппаратных потоков на компьютере и `MaxConcurrency` указано как `MaxExecutionResources` , значение для `MaxConcurrency` будет возникать в соответствии с `MinConcurrency` заданным значением.<br /><br /> Допустимые значения: положительные целые числа и специальное значение `MaxExecutionResources`<br /><br /> Значение по умолчанию: `MaxExecutionResources`|
|`MaxPolicyElementKey`|Ключ элемента максимальной политики. Недопустимый ключ элемента.|
|`MinConcurrency`|Минимальный уровень параллелизма, который должен быть предоставлен планировщику диспетчером ресурсов. Число виртуальных процессоров, назначенных планировщику, никогда не будет ниже минимального. Специальное значение [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) указывает, что минимальный уровень параллелизма совпадает с количеством аппаратных потоков на компьютере. Если значение, указанное для `MaxConcurrency` , меньше, чем число аппаратных потоков на компьютере и `MinConcurrency` указано как `MaxExecutionResources` , значение для `MinConcurrency` будет меньше, чтобы соответствовать значению для параметра `MaxConcurrency` .<br /><br /> Допустимые значения: неотрицательные целые числа и специальное значение `MaxExecutionResources` . Обратите внимание, что для политик планировщика, используемых для создания планировщиков исполняющей среды с параллелизмом, значение `0` недопустимо.<br /><br /> Значение по умолчанию: `1`|
|`SchedulerKind`|Тип потоков, которые будут использоваться планировщиком для базовых контекстов выполнения. Дополнительные сведения см. в разделе [SchedulerType](#schedulertype).<br /><br /> Допустимые значения: элемент перечисления `SchedulerType`, например `ThreadScheduler`<br /><br /> Значение по умолчанию: `ThreadScheduler` . Это преобразуется в потоки Win32 во всех операционных системах.|
|`SchedulingProtocol`|Описывает, какой алгоритм планирования будет использоваться планировщиком. Дополнительные сведения см. в разделе [SchedulingProtocolType](#schedulingprotocoltype).<br /><br /> Допустимые значения: член `SchedulingProtocolType` перечисления, `EnhanceScheduleGroupLocality` либо `EnhanceForwardProgress`<br /><br /> Значение по умолчанию: `EnhanceScheduleGroupLocality`|
|`TargetOversubscriptionFactor`|Предварительное количество виртуальных процессоров на аппаратный поток. Коэффициент переподписки целевого объекта при необходимости может быть увеличен диспетчером ресурсов для обеспечения `MaxConcurrency` аппаратными потоками на компьютере.<br /><br /> Допустимые значения: положительные целые числа<br /><br /> Значение по умолчанию: `1`|
|`WinRTInitialization`||

### <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

## <a name="schedulertype-enumeration"></a><a name="schedulertype"></a> Перечисление SchedulerType

Используется политикой `SchedulerKind` для описания типа потоков, которые должен использовать планировщик для базовых контекстов выполнения. Дополнительные сведения о доступных политиках планировщика см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).

```cpp
enum SchedulerType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`ThreadScheduler`|Указывает явный запрос обычных потоков Win32.|
|`UmsThreadDefault`|Планируемые потоки пользовательского режима (UMS) не поддерживаются в среда выполнения с параллелизмом в Visual Studio 2013. Использование `UmsThreadDefault` в качестве значения для политики `SchedulerType` не приведет к ошибке. Однако, планировщик, созданный с помощью этой политики, по умолчанию будет настроен на использование потоков Win32.|

### <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

## <a name="schedulingprotocoltype-enumeration"></a><a name="schedulingprotocoltype"></a> Перечисление SchedulingProtocolType

Используется политикой `SchedulingProtocol` для описания того, какой алгоритм планирования будет использоваться для планировщика. Дополнительные сведения о доступных политиках планировщика см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).

```cpp
enum SchedulingProtocolType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`EnhanceForwardProgress`|Планировщик предпочитает выполнять циклический перебор групп расписаний после выполнения каждой задачи. Незаблокированные контексты обычно планируются по принципу "первым поступил — первым обслужен" (FIFO). Виртуальные процессоры не кэшируют незаблокированные контексты.|
|`EnhanceScheduleGroupLocality`|Планировщик предпочитает продолжить работу над задачами в текущей группе расписаний перед перемещением в другую группу расписаний. Незаблокированные контексты кэшируются для каждого виртуального процессора и обычно планируются в режиме "последним поступает — первым обслужен" виртуальным процессором, который разблокировал их.|

### <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

## <a name="switchingproxystate-enumeration"></a><a name="switchingproxystate"></a> Перечисление Свитчингпроксистате

Используется для обозначения состояния прокси-потока, когда он выполняет совместное переключение контекста на другой прокси-поток.

```cpp
enum SwitchingProxyState;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`Blocking`|Указывает, что вызывающий поток блокируется совместно и должен быть исключительно владельцем вызывающего объекта до тех пор, пока снова не запустятся и выполняется другое действие.|
|`Idle`|Указывает, что вызывающий поток больше не нужен планировщику и возвращается в диспетчер ресурсов. Контекст, который был отправлен, больше не может использоваться диспетчер ресурсов.|
|`Nesting`|Указывает, что вызывающий поток вкладывает дочерний планировщик и необходим вызывающему объекту для присоединения к другому планировщику.|

### <a name="remarks"></a>Примечания

Параметр типа `SwitchingProxyState` передается в метод `IThreadProxy::SwitchTo` для указания Диспетчер ресурсов, как обрабатывать прокси-поток, выполняющий вызов.

Дополнительные сведения об использовании этого типа см. в разделе [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto).

## <a name="task_group_status-enumeration"></a><a name="task_group_status"></a> Перечисление task_group_status

Описывает состояние выполнения объекта `task_group` или `structured_task_group`. Значение этого типа возвращается многочисленными методами, которые ожидают выполнения задач, запланированных для завершения группой задач.

```cpp
enum task_group_status;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`canceled`|Объект `task_group` или `structured_task_group` отменен. Одна или несколько задач, возможно, не были выполнены.|
|`completed`|Задачи, поставленные в очередь объекта `task_group` или `structured_task_group`, завершены успешно.|
|`not_complete`|Задачи, поставленные в очередь объекта `task_group`, не завершены. Обратите внимание, что это значение в настоящее время не возвращается исполняющей средой с параллелизмом.|

### <a name="requirements"></a>Требования

**Заголовок:** pplinterface.h

## <a name="winrtinitializationtype-enumeration"></a><a name="winrtinitializationtype"></a> Перечисление WinRTInitializationType

Используется политикой `WinRTInitialization` для описания того, будет ли среда выполнения Windows инициализирована в потоках планировщика для приложения, которое работает в операционных системах Windows с версии 8 или выше, и каким образом это будет выполняться. Дополнительные сведения о доступных политиках планировщика см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).

```cpp
enum WinRTInitializationType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`DoNotInitializeWinRT`|Когда приложение выполняется в операционной системе Windows версии 8 и выше, потоки в планировщике не инициализируют среду выполнения Windows.|
|`InitializeWinRTAsMTA`|Когда приложение выполняется в операционной системе Windows версии 8 или выше, каждый поток в планировщике инициализирует среду выполнения Windows и объявляет, что это часть многопотокового подразделения.|

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)
