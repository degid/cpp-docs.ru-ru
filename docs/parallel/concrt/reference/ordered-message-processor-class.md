---
title: Класс ordered_message_processor
ms.date: 11/04/2016
f1_keywords:
- ordered_message_processor
- AGENTS/concurrency::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::async_send
- AGENTS/concurrency::ordered_message_processor::initialize
- AGENTS/concurrency::ordered_message_processor::initialize_batched_processing
- AGENTS/concurrency::ordered_message_processor::sync_send
- AGENTS/concurrency::ordered_message_processor::wait
- AGENTS/concurrency::ordered_message_processor::process_incoming_message
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
ms.openlocfilehash: ea9ca799f36cac0d843a578eb7cef9c1e9c5cda6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138786"
---
# <a name="ordered_message_processor-class"></a>Класс ordered_message_processor

Класс `ordered_message_processor` представляет собой `message_processor`, который позволяет блокам обмена сообщениями обрабатывать сообщения в том порядке, в котором они их получают.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class ordered_message_processor : public message_processor<T>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных сообщений, обрабатываемых процессором.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`type`|Псевдоним типа для `T`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ordered_message_processor](#ctor)|Создает объект `ordered_message_processor`.|
|[Деструктор ~ ordered_message_processor](#dtor)|Уничтожает объект `ordered_message_processor`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[async_send](#async_send)|Асинхронно ставит в очередь сообщения и запускает задачу обработки, если это еще не сделано. (Переопределяет [message_processor:: async_send](message-processor-class.md#async_send).)|
|[устанавливает](#initialize)|Инициализирует объект `ordered_message_processor` с соответствующей функцией обратного вызова, планировщиком и группой расписаний.|
|[initialize_batched_processing](#initialize_batched_processing)|Инициализация обработки пакетных сообщений|
|[sync_send](#sync_send)|Синхронно ставит в очередь сообщения и запускает задачу обработки, если это еще не сделано. (Переопределяет [message_processor:: sync_send](message-processor-class.md#sync_send).)|
|[ожидания](#wait)|Ожидание конкретного процессора, используемое в деструкторах блоков сообщений, чтобы убедиться, что все задачи асинхронной обработки имеют время для завершения перед уничтожением блока. (Переопределяет [message_processor:: wait](message-processor-class.md#wait).)|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Функция обработки, которая вызывается асинхронно. Она вымещает сообщения из очереди и начинает их обработку. (Переопределяет [message_processor::p rocess_incoming_message](message-processor-class.md#process_incoming_message).)|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[message_processor](message-processor-class.md)

`ordered_message_processor`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="async_send"></a>async_send

Асинхронно ставит в очередь сообщения и запускает задачу обработки, если это еще не сделано.

```cpp
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Указатель на сообщение.

## <a name="initialize"></a>устанавливает

Инициализирует объект `ordered_message_processor` с соответствующей функцией обратного вызова, планировщиком и группой расписаний.

```cpp
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```

### <a name="parameters"></a>Параметры

*_PScheduler*<br/>
Указатель на планировщик, который будет использоваться для планирования задач с низкой плотностью.

*_PScheduleGroup*<br/>
Указатель на группу расписаний, которая будет использоваться для планирования задач с низкой плотностью.

*_Handler*<br/>
Обработчик функтор вызывается во время обратного вызова.

## <a name="initialize_batched_processing"></a>initialize_batched_processing

Инициализация обработки пакетных сообщений

```cpp
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```

### <a name="parameters"></a>Параметры

*_Processor*<br/>
Процессор функтор, вызванный во время обратного вызова.

*_Propagator*<br/>
Распространитель функтор вызывается во время обратного вызова.

## <a name="ctor"></a>ordered_message_processor

Создает объект `ordered_message_processor`.

```cpp
ordered_message_processor();
```

### <a name="remarks"></a>Примечания

Это `ordered_message_processor` не планирует асинхронные или синхронные обработчики, пока не будет вызвана функция `initialize`.

## <a name="dtor"></a>~ ordered_message_processor

Уничтожает объект `ordered_message_processor`.

```cpp
virtual ~ordered_message_processor();
```

### <a name="remarks"></a>Примечания

Ожидает завершения всех невыполненных асинхронных операций перед уничтожением процессора.

## <a name="process_incoming_message"></a>process_incoming_message

Функция обработки, которая вызывается асинхронно. Она вымещает сообщения из очереди и начинает их обработку.

```cpp
virtual void process_incoming_message();
```

## <a name="sync_send"></a>sync_send

Синхронно ставит в очередь сообщения и запускает задачу обработки, если это еще не сделано.

```cpp
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Указатель на сообщение.

## <a name="wait"></a>ожидания

Ожидание конкретного процессора, используемое в деструкторах блоков сообщений, чтобы убедиться, что все задачи асинхронной обработки имеют время для завершения перед уничтожением блока.

```cpp
virtual void wait();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
