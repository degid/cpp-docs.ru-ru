---
title: Класс join
ms.date: 11/04/2016
f1_keywords:
- join
- AGENTS/concurrency::join
- AGENTS/concurrency::join::join
- AGENTS/concurrency::join::accept_message
- AGENTS/concurrency::join::consume_message
- AGENTS/concurrency::join::link_target_notification
- AGENTS/concurrency::join::propagate_message
- AGENTS/concurrency::join::propagate_to_any_targets
- AGENTS/concurrency::join::release_message
- AGENTS/concurrency::join::reserve_message
- AGENTS/concurrency::join::resume_propagation
helpviewer_keywords:
- join class
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
ms.openlocfilehash: c65eed8abafe424fa27c5b9a72d3c73b7127b68e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219590"
---
# <a name="join-class"></a>Класс join

Блок обмена сообщениями `join` — это упорядоченный блок `propagator_block` с несколькими источниками и одной целью, который объединяет сообщения типа `T` от каждого из своих источников.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T,
    join_type _Jtype = non_greedy>
class join : public propagator_block<single_link_registry<ITarget<std::vector<T>>>,
    multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных сообщений, соединяемых и распространяемых блоком.

*_Jtype*<br/>
Тип `join` блока: `greedy` или`non_greedy`

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[join](#ctor)|Перегружен. Создает блок обмена сообщениями `join` .|
|[Деструктор ~ Join](#dtor)|Уничтожает `join` блок.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[accept_message](#accept_message)|Принимает сообщение, которое было предложено этим `join` блоком обмена сообщениями, передавая владение вызывающему объекту.|
|[consume_message](#consume_message)|Использует сообщение, которое было ранее предложено `join` блоком обмена сообщениями и зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[link_target_notification](#link_target_notification)|Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим `join` блоком обмена сообщениями.|
|[propagate_message](#propagate_message)|Асинхронно передает сообщение из `ISource` блока в этот `join` блок обмена сообщениями. Он вызывается `propagate` методом при вызове из исходного блока.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Формирует выходное сообщение, содержащее входное сообщение из каждого источника, когда все они распространяют сообщение. Отправляет это выходное сообщение в все целевые объекты.|
|[release_message](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Резервирует сообщение, которое было ранее предложено этим `join` блоком обмена сообщениями. (Переопределяет [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Возобновляет распространение после освобождения резервирования. (Переопределяет [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`join`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

Принимает сообщение, которое было предложено этим `join` блоком обмена сообщениями, передавая владение вызывающему объекту.

```cpp
virtual message<_OutputType>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект предлагаемого `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объект, владельцем которого стал вызывающий объект.

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

Использует сообщение, которое было ранее предложено `join` блоком обмена сообщениями и зарезервировано целевым объектом, передавая владение вызывающему объекту.

```cpp
virtual message<_OutputType>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект для используемого `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объект, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Примечания

Аналогично `accept` , но всегда предшествует вызову `reserve` .

## <a name="join"></a><a name="ctor"></a>к

Создает блок обмена сообщениями `join` .

```cpp
join(
    size_t _NumInputs);

join(
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Параметры

*_NumInputs*<br/>
Число входов, `join` разрешенных для этого блока.

*_Filter*<br/>
Функция фильтра, которая определяет, следует ли принимать предлагаемые сообщения.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `join` .

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `join` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Примечания

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .

Тип `filter_method` — это функтор с сигнатурой, `bool (T const &)` которая вызывается этим `join` блоком обмена сообщениями для определения того, следует ли принимать предложенное сообщение.

## <a name="join"></a><a name="dtor"></a>~ соединение

Уничтожает `join` блок.

```cpp
~join();
```

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим `join` блоком обмена сообщениями.

```cpp
virtual void link_target_notification(_Inout_ ITarget<std::vector<T>> *);
```

## <a name="propagate_message"></a><a name="propagate_message"></a>propagate_message

Асинхронно передает сообщение из `ISource` блока в этот `join` блок обмена сообщениями. Он вызывается `propagate` методом при вызове из исходного блока.

```cpp
message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets

Формирует выходное сообщение, содержащее входное сообщение из каждого источника, когда все они распространяют сообщение. Отправляет это выходное сообщение в все целевые объекты.

```cpp
void propagate_to_any_targets(_Inout_opt_ message<_OutputType> *);
```

## <a name="release_message"></a><a name="release_message"></a>release_message

Освобождает предыдущее резервирование сообщения.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` `message` Объект для освобожденного объекта.

## <a name="reserve_message"></a><a name="reserve_message"></a>reserve_message

Резервирует сообщение, которое было ранее предложено этим `join` блоком обмена сообщениями.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект предлагаемого `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если сообщение было успешно зарезервировано, **`false`** в противном случае.

### <a name="remarks"></a>Примечания

После `reserve` вызова метода, если он возвращает значение **`true`** , `consume` `release` метод или должен быть вызван, чтобы принять или освободить владение сообщением.

## <a name="resume_propagation"></a><a name="resume_propagation"></a>resume_propagation

Возобновляет распространение после освобождения резервирования.

```cpp
virtual void resume_propagation();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс choice](choice-class.md)<br/>
[Класс multitype_join](multitype-join-class.md)
