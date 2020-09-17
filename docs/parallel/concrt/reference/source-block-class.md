---
title: Класс source_block
ms.date: 11/04/2016
f1_keywords:
- source_block
- AGENTS/concurrency::source_block
- AGENTS/concurrency::source_block::source_block
- AGENTS/concurrency::source_block::accept
- AGENTS/concurrency::source_block::acquire_ref
- AGENTS/concurrency::source_block::consume
- AGENTS/concurrency::source_block::link_target
- AGENTS/concurrency::source_block::release
- AGENTS/concurrency::source_block::release_ref
- AGENTS/concurrency::source_block::reserve
- AGENTS/concurrency::source_block::unlink_target
- AGENTS/concurrency::source_block::unlink_targets
- AGENTS/concurrency::source_block::accept_message
- AGENTS/concurrency::source_block::async_send
- AGENTS/concurrency::source_block::consume_message
- AGENTS/concurrency::source_block::enable_batched_processing
- AGENTS/concurrency::source_block::initialize_source
- AGENTS/concurrency::source_block::link_target_notification
- AGENTS/concurrency::source_block::process_input_messages
- AGENTS/concurrency::source_block::propagate_output_messages
- AGENTS/concurrency::source_block::propagate_to_any_targets
- AGENTS/concurrency::source_block::release_message
- AGENTS/concurrency::source_block::remove_targets
- AGENTS/concurrency::source_block::reserve_message
- AGENTS/concurrency::source_block::resume_propagation
- AGENTS/concurrency::source_block::sync_send
- AGENTS/concurrency::source_block::unlink_target_notification
- AGENTS/concurrency::source_block::wait_for_outstanding_async_sends
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
ms.openlocfilehash: 304bc65d969fa677d67bf578021a63f628e0a1f5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228444"
---
# <a name="source_block-class"></a>Класс source_block

Класс `source_block` — это абстрактный базовый класс только для блоков источника. Класс предоставляет основные функции управления соединениями, а также проверки распространенных ошибок.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```

### <a name="parameters"></a>Параметры

*_TargetLinkRegistry*<br/>
Свяжите реестр, который будет использоваться для хранения целевых ссылок.

*_MessageProcessorType*<br/>
Тип процессора для обработки сообщений.

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`target_iterator`|Итератор для прохода по подключенным целевым объектам.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[source_block](#ctor)|Формирует объект `source_block`.|
|[Деструктор ~ source_block](#dtor)|Уничтожает `source_block` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[гласит](#accept)|Принимает сообщение, которое было предложено этим `source_block` объектом, передавая владение вызывающему объекту.|
|[acquire_ref](#acquire_ref)|Получает счетчик ссылок на этот `source_block` объект, чтобы предотвратить удаление.|
|[потребляющие](#consume)|Использует сообщение, которое было ранее предложено этим `source_block` объектом и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[link_target](#link_target)|Связывает целевой блок с этим `source_block` объектом.|
|[отпускании](#release)|Освобождает предыдущее успешное резервирование сообщения.|
|[release_ref](#release_ref)|Освобождает счетчик ссылок на этот `source_block` объект.|
|[reserve](#reserve)|Резервирует сообщение, которое было ранее предложено этим `source_block` объектом.|
|[unlink_target](#unlink_target)|Отменяет связь с целевым блоком из этого `source_block` объекта.|
|[unlink_targets](#unlink_targets)|Отменяет связь всех целевых блоков с этим `source_block` объектом. (Переопределяет метод [ISource:: unlink_targets](isource-class.md#unlink_targets).)|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[accept_message](#accept_message)|При переопределении в производном классе принимает предлагаемое сообщение источником. Блоки сообщений должны переопределять этот метод для проверки `_MsgId` и возврата сообщения.|
|[async_send](#async_send)|Асинхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано.|
|[consume_message](#consume_message)|При переопределении в производном классе использует ранее зарезервированное сообщение.|
|[enable_batched_processing](#enable_batched_processing)|Активирует пакетную обработку для этого блока.|
|[initialize_source](#initialize_source)|Инициализирует в `message_propagator` этом объекте `source_block` .|
|[link_target_notification](#link_target_notification)|Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим `source_block` объектом.|
|[process_input_messages](#process_input_messages)|Обработка входных сообщений. Подходит только для блоков распространения, производных от source_block.|
|[propagate_output_messages](#propagate_output_messages)|Распространение сообщений в целевые объекты.|
|[propagate_to_any_targets](#propagate_to_any_targets)|При переопределении в производном классе распространяет данное сообщение на все или все связанные целевые объекты. Это основная подпрограммы распространения для блоков сообщений.|
|[release_message](#release_message)|При переопределении в производном классе освобождает предыдущее резервирование сообщения.|
|[remove_targets](#remove_targets)|Удаляет все целевые ссылки для этого исходного блока. Его следует вызывать из деструктора.|
|[reserve_message](#reserve_message)|При переопределении в производном классе резервирует сообщение, которое было ранее предложено этим `source_block` объектом.|
|[resume_propagation](#resume_propagation)|При переопределении в производном классе возобновляет распространение после освобождения резервирования.|
|[sync_send](#sync_send)|Синхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано.|
|[unlink_target_notification](#unlink_target_notification)|Обратный вызов, уведомляющий о том, что для цели удалена связь с этим `source_block` объектом.|
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|Ожидает завершения всех асинхронных распространителей. Это время ожидания для этого распространителя используется в деструкторах блоков сообщений, чтобы убедиться в том, что все асинхронные распространители имеют достаточно времени для завершения перед уничтожением блока.|

## <a name="remarks"></a>Примечания

Блоки сообщений должны быть производными от этого блока, чтобы воспользоваться преимуществами управления ссылками и синхронизации, предоставляемыми этим классом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

`source_block`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept"></a><a name="accept"></a>гласит

Принимает сообщение, которое было предложено этим `source_block` объектом, передавая владение вызывающему объекту.

```cpp
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `accept` метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объект, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если параметр имеет значение `_PTarget` `NULL` .

`accept`Метод вызывается целевым объектом, в то время как сообщение предлагается этим `ISource` блоком. Возвращаемый указатель на сообщение может отличаться от переданного в `propagate` метод `ITarget` блока, если этот источник решит создать копию сообщения.

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

При переопределении в производном классе принимает предлагаемое сообщение источником. Блоки сообщений должны переопределять этот метод для проверки `_MsgId` и возврата сообщения.

```cpp
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
Удостоверение объекта среды выполнения `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение о том, что вызывающий объект теперь является владельцем.

### <a name="remarks"></a>Примечания

Чтобы передавать владение, должен быть возвращен указатель на исходный текст. Чтобы обеспечить владение, необходимо выполнить и вернуть копию полезных данных сообщения.

## <a name="acquire_ref"></a><a name="acquire_ref"></a>acquire_ref

Получает счетчик ссылок на этот `source_block` объект, чтобы предотвратить удаление.

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объектом, который связан с этим источником во время выполнения `link_target` метода.

## <a name="async_send"></a><a name="async_send"></a>async_send

Асинхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано.

```cpp
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Указатель на `message` объект для асинхронной отправки.

## <a name="consume"></a><a name="consume"></a>потребляющие

Использует сообщение, которое было ранее предложено этим `source_block` объектом и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.

```cpp
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект зарезервированного `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `consume` метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объект, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если параметр имеет значение `_PTarget` `NULL` .

Метод вызывает исключение [bad_target](bad-target-class.md) , если параметр не `_PTarget` представляет целевой объект, вызвавший `reserve` .

`consume`Метод аналогичен `accept` , но ему всегда должен предшествовать вызов `reserve` , который возвращает **`true`** .

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

При переопределении в производном классе использует ранее зарезервированное сообщение.

```cpp
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект для используемого `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение о том, что вызывающий объект теперь является владельцем.

### <a name="remarks"></a>Примечания

Аналогично `accept` , но всегда предшествует вызову `reserve` .

## <a name="enable_batched_processing"></a><a name="enable_batched_processing"></a>enable_batched_processing

Активирует пакетную обработку для этого блока.

```cpp
void enable_batched_processing();
```

## <a name="initialize_source"></a><a name="initialize_source"></a>initialize_source

Инициализирует в `message_propagator` этом объекте `source_block` .

```cpp
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Параметры

*_PScheduler*<br/>
Планировщик, который будет использоваться для планирования задач.

*_PScheduleGroup*<br/>
Группа расписаний, которая будет использоваться для планирования задач.

## <a name="link_target"></a><a name="link_target"></a>link_target

Связывает целевой блок с этим `source_block` объектом.

```cpp
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на `ITarget` блок, связываемый с этим `source_block` объектом.

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если параметр имеет значение `_PTarget` `NULL` .

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим `source_block` объектом.

```cpp
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```

## <a name="process_input_messages"></a><a name="process_input_messages"></a>process_input_messages

Обработка входных сообщений. Подходит только для блоков распространения, производных от source_block.

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на сообщение, которое должно быть обработано.

## <a name="propagate_output_messages"></a><a name="propagate_output_messages"></a>propagate_output_messages

Распространение сообщений в целевые объекты.

```cpp
virtual void propagate_output_messages();
```

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets

При переопределении в производном классе распространяет данное сообщение на все или все связанные целевые объекты. Это основная подпрограммы распространения для блоков сообщений.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на сообщение, которое должно быть распространено.

## <a name="release"></a><a name="release"></a>отпускании

Освобождает предыдущее успешное резервирование сообщения.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект зарезервированного `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `release` метод.

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если параметр имеет значение `_PTarget` `NULL` .

Метод вызывает исключение [bad_target](bad-target-class.md) , если параметр не `_PTarget` представляет целевой объект, вызвавший `reserve` .

## <a name="release_message"></a><a name="release_message"></a>release_message

При переопределении в производном классе освобождает предыдущее резервирование сообщения.

```cpp
virtual void release_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` `message` Объект для освобожденного объекта.

## <a name="release_ref"></a><a name="release_ref"></a>release_ref

Освобождает счетчик ссылок на этот `source_block` объект.

```cpp
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объектом, для которого удаляется связь из этого источника. Блоку источника разрешено освобождать все ресурсы, зарезервированные для целевого блока.

## <a name="remove_targets"></a><a name="remove_targets"></a>remove_targets

Удаляет все целевые ссылки для этого исходного блока. Его следует вызывать из деструктора.

```cpp
void remove_targets();
```

## <a name="reserve"></a><a name="reserve"></a>предназначен

Резервирует сообщение, которое было ранее предложено этим `source_block` объектом.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `reserve` метод.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если сообщение было успешно зарезервировано, **`false`** в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если параметр имеет значение `_PTarget` `NULL` .

После вызова метода `reserve` , если он выполняется, необходимо вызвать метод `consume` или `release` , чтобы получить или предоставить владение сообщениями соответственно.

## <a name="reserve_message"></a><a name="reserve_message"></a>reserve_message

При переопределении в производном классе резервирует сообщение, которое было ранее предложено этим `source_block` объектом.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` `message` Объект для резервируемого объекта.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если сообщение было успешно зарезервировано, **`false`** в противном случае.

### <a name="remarks"></a>Примечания

После `reserve` вызова метода, если он возвращает значение **`true`** , `consume` `release` метод или должен быть вызван, чтобы принять или освободить владение сообщением.

## <a name="resume_propagation"></a><a name="resume_propagation"></a>resume_propagation

При переопределении в производном классе возобновляет распространение после освобождения резервирования.

```cpp
virtual void resume_propagation() = 0;
```

## <a name="source_block"></a><a name="ctor"></a>source_block

Формирует объект `source_block`.

```cpp
source_block();
```

## <a name="source_block"></a><a name="dtor"></a>~ source_block

Уничтожает `source_block` объект.

```cpp
virtual ~source_block();
```

## <a name="sync_send"></a><a name="sync_send"></a>sync_send

Синхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано.

```cpp
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Указатель на `message` объект для синхронной отправки.

## <a name="unlink_target"></a><a name="unlink_target"></a>unlink_target

Отменяет связь с целевым блоком из этого `source_block` объекта.

```cpp
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на `ITarget` блок, который необходимо удалить из этого `source_block` объекта.

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если параметр имеет значение `_PTarget` `NULL` .

## <a name="unlink_target_notification"></a><a name="unlink_target_notification"></a>unlink_target_notification

Обратный вызов, уведомляющий о том, что для цели удалена связь с этим `source_block` объектом.

```cpp
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
`ITarget`Несвязанный блок.

## <a name="unlink_targets"></a><a name="unlink_targets"></a>unlink_targets

Отменяет связь всех целевых блоков с этим `source_block` объектом.

```cpp
virtual void unlink_targets();
```

## <a name="wait_for_outstanding_async_sends"></a><a name="wait_for_outstanding_async_sends"></a>wait_for_outstanding_async_sends

Ожидает завершения всех асинхронных распространителей. Это время ожидания для этого распространителя используется в деструкторах блоков сообщений, чтобы убедиться в том, что все асинхронные распространители имеют достаточно времени для завершения перед уничтожением блока.

```cpp
void wait_for_outstanding_async_sends();
```

## <a name="see-also"></a>См. также статью

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс ISource](isource-class.md)
