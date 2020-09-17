---
title: Класс agent
ms.date: 11/04/2016
f1_keywords:
- agent
- AGENTS/concurrency::agent
- AGENTS/concurrency::agent::agent
- AGENTS/concurrency::agent::cancel
- AGENTS/concurrency::agent::start
- AGENTS/concurrency::agent::status
- AGENTS/concurrency::agent::status_port
- AGENTS/concurrency::agent::wait
- AGENTS/concurrency::agent::wait_for_all
- AGENTS/concurrency::agent::wait_for_one
- AGENTS/concurrency::agent::done
- AGENTS/concurrency::agent::run
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
ms.openlocfilehash: f1d98cdc6237f182e0240a85f2fdce3410232195
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213896"
---
# <a name="agent-class"></a>Класс agent

Класс, предназначенный для использования в качестве базового класса для всех независимых агентов. Он используется для скрытия состояния от других агентов и взаимодействия посредством передачи сообщений.

## <a name="syntax"></a>Синтаксис

```cpp
class agent;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Субагент](#ctor)|Перегружен. Конструирует агент.|
|[Деструктор агента ~](#dtor)|Уничтожает агент.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[cancel](#cancel)|Перемещает агент из `agent_created` `agent_runnable` состояний или в `agent_canceled` состояние.|
|[start](#start)|Перемещает агент из `agent_created` состояния в `agent_runnable` состояние и планирует его выполнение.|
|[status](#status)|Синхронный источник сведений о состоянии от агента.|
|[status_port](#status_port)|Асинхронный источник сведений о состоянии от агента.|
|[ожидания](#wait)|Ожидает завершения задачи агента.|
|[wait_for_all](#wait_for_all)|Ожидает завершения задач всеми указанными агентами.|
|[wait_for_one](#wait_for_one)|Ожидает завершения задачи одним из указанных агентов.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[готово](#done)|Перемещает агент в `agent_done` состояние, указывая на то, что агент завершен.|
|[запуска](#run)|Представляет главную задачу агента. `run`должен быть переопределен в производном классе и указывает, что должен делать агент после его запуска.|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронные агенты](../../../parallel/concrt/asynchronous-agents.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`agent`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="agent"></a><a name="ctor"></a>Субагент

Конструирует агент.

```cpp
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```

### <a name="parameters"></a>Параметры

*_PScheduler*<br/>
`Scheduler`Объект, в котором запланирована задача выполнения агента.

*_PGroup*<br/>
`ScheduleGroup`Объект, в котором запланирована задача выполнения агента. Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Примечания

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PGroup` .

## <a name="agent"></a><a name="dtor"></a>~ агент

Уничтожает агент.

```cpp
virtual ~agent();
```

### <a name="remarks"></a>Примечания

Удаление агента, который не находится в состоянии терминала (или), является ошибкой `agent_done` `agent_canceled` . Это можно избежать, ожидая, когда агент достигнет состояния терминала в деструкторе класса, наследующего от `agent` класса.

## <a name="cancel"></a><a name="cancel"></a>Отмена

Перемещает агент из `agent_created` `agent_runnable` состояний или в `agent_canceled` состояние.

```cpp
bool cancel();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если агент был отменен, **`false`** в противном случае. Агент не может быть отменен, если он уже запущен или уже завершен.

## <a name="done"></a><a name="done"></a>Договорились

Перемещает агент в `agent_done` состояние, указывая на то, что агент завершен.

```cpp
bool done();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если агент перемещается в `agent_done` состояние; **`false`** в противном случае —. Невозможно переместить агент, который был отменен, в `agent_done` состояние.

### <a name="remarks"></a>Примечания

Этот метод должен вызываться в конце `run` метода, если известно, что выполнение агента завершено.

## <a name="run"></a><a name="run"></a>запуска

Представляет главную задачу агента. `run`должен быть переопределен в производном классе и указывает, что должен делать агент после его запуска.

```cpp
virtual void run() = 0;
```

### <a name="remarks"></a>Примечания

`agent_started`Перед вызовом этого метода состояние агента изменится на right. Метод должен вызываться `done` в агенте с соответствующим состоянием перед возвратом и не может вызывать исключения.

## <a name="start"></a><a name="start"></a>запустить

Перемещает агент из `agent_created` состояния в `agent_runnable` состояние и планирует его выполнение.

```cpp
bool start();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если агент запущен правильно; **`false`** в противном случае —. Не удается запустить агент, который был отменен.

## <a name="status"></a><a name="status"></a>состояние

Синхронный источник сведений о состоянии от агента.

```cpp
agent_status status();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текущее состояние агента. Обратите внимание, что возвращаемое состояние может измениться сразу после возврата.

## <a name="status_port"></a><a name="status_port"></a>status_port

Асинхронный источник сведений о состоянии от агента.

```cpp
ISource<agent_status>* status_port();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает источник сообщения, который может отправить сообщения о текущем состоянии агента.

## <a name="wait"></a><a name="wait"></a>ожидания

Ожидает завершения задачи агента.

```cpp
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*_PAgent*<br/>
Указатель на агент, который нужно ожидать.

*_Timeout*<br/>
Максимальное время ожидания (в миллисекундах).

### <a name="return-value"></a>Возвращаемое значение

`agent_status`Агент по завершении ожидания. Может иметь значение `agent_canceled` или `agent_done` .

### <a name="remarks"></a>Примечания

Задача агента завершается, когда агент переходит в `agent_canceled` состояние или `agent_done` .

Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE` , исключение [operation_timed_out](operation-timed-out-class.md) возникает, если срок действия указанного времени истекает до того, как агент завершит свою задачу.

## <a name="wait_for_all"></a><a name="wait_for_all"></a>wait_for_all

Ожидает завершения задач всеми указанными агентами.

```cpp
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*count*<br/>
Число указателей агентов, имеющихся в массиве `_PAgents` .

*_PAgents*<br/>
Массив указателей на агенты, которые нужно ожидать.

*_PStatus*<br/>
Указатель на массив состояний агента. Каждое значение состояния будет представлять состояние соответствующего агента при возврате из метода.

*_Timeout*<br/>
Максимальное время ожидания (в миллисекундах).

### <a name="remarks"></a>Примечания

Задача агента завершается, когда агент переходит в `agent_canceled` состояние или `agent_done` .

Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE` , исключение [operation_timed_out](operation-timed-out-class.md) возникает, если срок действия указанного времени истекает до того, как агент завершит свою задачу.

## <a name="wait_for_one"></a><a name="wait_for_one"></a>wait_for_one

Ожидает завершения задачи одним из указанных агентов.

```cpp
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*count*<br/>
Число указателей агентов, имеющихся в массиве `_PAgents` .

*_PAgents*<br/>
Массив указателей на агенты, которые нужно ожидать.

*_Status*<br/>
Ссылка на переменную, в которой будет размещено состояние агента.

*_Index*<br/>
Ссылка на переменную, в которую будет помещен индекс агента.

*_Timeout*<br/>
Максимальное время ожидания (в миллисекундах).

### <a name="remarks"></a>Примечания

Задача агента завершается, когда агент переходит в `agent_canceled` состояние или `agent_done` .

Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE` , исключение [operation_timed_out](operation-timed-out-class.md) возникает, если срок действия указанного времени истекает до того, как агент завершит свою задачу.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)
