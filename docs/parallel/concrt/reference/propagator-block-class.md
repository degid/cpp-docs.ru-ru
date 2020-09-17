---
title: Класс propagator_block
ms.date: 11/04/2016
f1_keywords:
- propagator_block
- AGENTS/concurrency::propagator_block
- AGENTS/concurrency::propagator_block::propagator_block
- AGENTS/concurrency::propagator_block::propagate
- AGENTS/concurrency::propagator_block::send
- AGENTS/concurrency::propagator_block::decline_incoming_messages
- AGENTS/concurrency::propagator_block::initialize_source_and_target
- AGENTS/concurrency::propagator_block::link_source
- AGENTS/concurrency::propagator_block::process_input_messages
- AGENTS/concurrency::propagator_block::propagate_message
- AGENTS/concurrency::propagator_block::register_filter
- AGENTS/concurrency::propagator_block::remove_network_links
- AGENTS/concurrency::propagator_block::send_message
- AGENTS/concurrency::propagator_block::unlink_source
- AGENTS/concurrency::propagator_block::unlink_sources
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
ms.openlocfilehash: 340af181669cbbf4c5ba910aa3ee862bd40ba27f
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138746"
---
# <a name="propagator_block-class"></a>Класс propagator_block

Класс `propagator_block` — это абстрактный базовый класс для блоков сообщений, которые являются одновременно блоками источников и целевыми блоками. Он объединяет функциональные возможности обоих классов, `source_block` и `target_block`.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

### <a name="parameters"></a>Параметры

*_TargetLinkRegistry*<br/>
Реестр ссылок, используемый для хранения целевых ссылок.

*_SourceLinkRegistry*<br/>
Реестр ссылок, используемый для хранения исходных ссылок.

*_MessageProcessorType*<br/>
Тип процессора для обработки сообщений.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`source_iterator`|Тип итератора для `source_link_manager` для этого `propagator_block`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[propagator_block](#ctor)|Формирует объект `propagator_block`.|
|[Деструктор ~ propagator_block](#dtor)|Уничтожает объект `propagator_block`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[распространения](#propagate)|Асинхронно передает сообщение из исходного блока в этот целевой блок.|
|[send](#send)|Синхронно инициирует сообщение для этого блока. Вызывается блоком `ISource`. По завершении этой функции сообщение уже будет распространено в блок.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[decline_incoming_messages](#decline_incoming_messages)|Указывает блоку, что следует отклонять новые сообщения.|
|[initialize_source_and_target](#initialize_source_and_target)|Инициализирует базовый объект. В частности, необходимо инициализировать объект `message_processor`.|
|[link_source](#link_source)|Связывает указанный блок источника с данным объектом `propagator_block`.|
|[process_input_messages](#process_input_messages)|Обработка входных сообщений. Это полезно только для блоков распространения, которые являются производными от source_block (переопределяет [source_block::p rocess_input_messages](source-block-class.md#process_input_messages).)|
|[propagate_message](#propagate_message)|При переопределении в производном классе этот метод асинхронно передает сообщение из блока `ISource` в этот объект `propagator_block`. Вызывается методом `propagate` при вызове из исходного блока.|
|[register_filter](#register_filter)|Регистрирует метод фильтра, который будет вызываться для каждого полученного сообщения.|
|[remove_network_links](#remove_network_links)|Удаляет все ссылки исходной и целевой сетей из этого объекта `propagator_block`.|
|[send_message](#send_message)|При переопределении в производном классе этот метод синхронно передает сообщение из блока `ISource` в этот объект `propagator_block`. Вызывается методом `send` при вызове из исходного блока.|
|[unlink_source](#unlink_source)|Отменяет связь указанного исходного блока с этим `propagator_block` объектом.|
|[unlink_sources](#unlink_sources)|Отменяет связь со всеми исходными блоками этого `propagator_block` объекта. (Переопределяет метод [ITarget:: unlink_sources](itarget-class.md#unlink_sources).)|

## <a name="remarks"></a>Примечания

Чтобы избежать множественного наследования, класс `propagator_block` наследует от класса `source_block` и `ITarget` абстрактного класса. Большая часть функциональных возможностей класса `target_block` реплицируется здесь.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

`propagator_block`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="decline_incoming_messages"></a>decline_incoming_messages

Указывает блоку, что следует отклонять новые сообщения.

```cpp
void decline_incoming_messages();
```

### <a name="remarks"></a>Примечания

Этот метод вызывается деструктором, чтобы гарантировать отклонение новых сообщений в процессе уничтожения.

## <a name="initialize_source_and_target"></a>initialize_source_and_target

Инициализирует базовый объект. В частности, необходимо инициализировать объект `message_processor`.

```cpp
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Параметры

*_PScheduler*<br/>
Планировщик, который будет использоваться для планирования задач.

*_PScheduleGroup*<br/>
Группа расписаний, которая будет использоваться для планирования задач.

## <a name="link_source"></a>link_source

Связывает указанный блок источника с данным объектом `propagator_block`.

```cpp
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Параметры

*_PSource*<br/>
Указатель на блок `ISource`, который должен быть связан.

## <a name="process_input_messages"></a>process_input_messages

Обработка входных сообщений. Подходит только для блоков распространения, производных от source_block.

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на сообщение, которое должно быть обработано.

## <a name="propagate"></a>распространения

Асинхронно передает сообщение из исходного блока в этот целевой блок.

```cpp
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

### <a name="remarks"></a>Примечания

Метод `propagate` вызывается в целевом блоке связанным исходным блоком. Она помещает в очередь асинхронную задачу для работы с сообщением, если она еще не находится в очереди или не исполняется.

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если параметр `_PMessage` или `_PSource` имеет значение `NULL`.

## <a name="propagate_message"></a>propagate_message

При переопределении в производном классе этот метод асинхронно передает сообщение из блока `ISource` в этот объект `propagator_block`. Вызывается методом `propagate` при вызове из исходного блока.

```cpp
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

## <a name="ctor"></a>propagator_block

Формирует объект `propagator_block`.

```cpp
propagator_block();
```

## <a name="dtor"></a>~ propagator_block

Уничтожает объект `propagator_block`.

```cpp
virtual ~propagator_block();
```

## <a name="register_filter"></a>register_filter

Регистрирует метод фильтра, который будет вызываться для каждого полученного сообщения.

```cpp
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>Параметры

*_Filter*<br/>
Метод Filter.

## <a name="remove_network_links"></a>remove_network_links

Удаляет все ссылки исходной и целевой сетей из этого объекта `propagator_block`.

```cpp
void remove_network_links();
```

## <a name="send"></a>Отправить

Синхронно инициирует сообщение для этого блока. Вызывается блоком `ISource`. По завершении этой функции сообщение уже будет распространено в блок.

```cpp
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

### <a name="remarks"></a>Примечания

Этот метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если параметр `_PMessage` или `_PSource` имеет значение `NULL`.

## <a name="send_message"></a>send_message

При переопределении в производном классе этот метод синхронно передает сообщение из блока `ISource` в этот объект `propagator_block`. Вызывается методом `send` при вызове из исходного блока.

```cpp
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

### <a name="remarks"></a>Примечания

По умолчанию этот блок возвращает `declined`, если только они не переопределены производным классом.

## <a name="unlink_source"></a>unlink_source

Отменяет связь указанного исходного блока с этим `propagator_block` объектом.

```cpp
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Параметры

*_PSource*<br/>
Указатель на блок `ISource`, связь с которым необходимо удалить.

## <a name="unlink_sources"></a>unlink_sources

Отменяет связь со всеми исходными блоками этого `propagator_block` объекта.

```cpp
virtual void unlink_sources();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс source_block](source-block-class.md)<br/>
[Класс ITarget](itarget-class.md)
