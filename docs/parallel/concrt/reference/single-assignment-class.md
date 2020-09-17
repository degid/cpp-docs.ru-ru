---
title: Класс single_assignment
ms.date: 11/04/2016
f1_keywords:
- single_assignment
- AGENTS/concurrency::single_assignment
- AGENTS/concurrency::single_assignment::single_assignment
- AGENTS/concurrency::single_assignment::has_value
- AGENTS/concurrency::single_assignment::value
- AGENTS/concurrency::single_assignment::accept_message
- AGENTS/concurrency::single_assignment::consume_message
- AGENTS/concurrency::single_assignment::link_target_notification
- AGENTS/concurrency::single_assignment::propagate_message
- AGENTS/concurrency::single_assignment::propagate_to_any_targets
- AGENTS/concurrency::single_assignment::release_message
- AGENTS/concurrency::single_assignment::reserve_message
- AGENTS/concurrency::single_assignment::resume_propagation
- AGENTS/concurrency::single_assignment::send_message
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
ms.openlocfilehash: 6b92508c81311774816e804eb36ac8fbfb2aa82b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219564"
---
# <a name="single_assignment-class"></a>Класс single_assignment

Блок обмена сообщениями `single_assignment` — это упорядоченный блок `propagator_block` с несколькими источниками и несколькими целями, который может хранить один объект `message` с однократной записью.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных сообщения, хранимого и распространяемого буфером.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[single_assignment](#ctor)|Перегружен. Создает блок обмена сообщениями `single_assignment` .|
|[Деструктор ~ single_assignment](#dtor)|Уничтожает `single_assignment` блок обмена сообщениями.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[has_value](#has_value)|Проверяет `single_assignment` , инициализирован ли этот блок обмена сообщениями со значением.|
|[value](#value)|Возвращает ссылку на текущие полезные данные сообщения, хранящегося в `single_assignment` блоке обмена сообщениями.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[accept_message](#accept_message)|Принимает сообщение, которое было предложено этим `single_assignment` блоком обмена сообщениями, и возвращает копию сообщения вызывающему объекту.|
|[consume_message](#consume_message)|Использует сообщение, которое было ранее предложено `single_assignment` и зарезервировано целевым объектом, возвращая копию сообщения вызывающему объекту.|
|[link_target_notification](#link_target_notification)|Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим `single_assignment` блоком обмена сообщениями.|
|[propagate_message](#propagate_message)|Асинхронно передает сообщение из `ISource` блока в этот `single_assignment` блок обмена сообщениями. Он вызывается `propagate` методом при вызове из исходного блока.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Помещает объект `message _PMessage` в этот `single_assignment` блок обмена сообщениями и предлагает его всем связанным целевым объектам.|
|[release_message](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Резервирует сообщение, которое было ранее предложено этим `single_assignment` блоком обмена сообщениями. (Переопределяет [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Возобновляет распространение после освобождения резервирования. (Переопределяет [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Синхронно передает сообщение из `ISource` блока в этот `single_assignment` блок обмена сообщениями. Он вызывается `send` методом при вызове из исходного блока.|

## <a name="remarks"></a>Примечания

`single_assignment`Блок обмена сообщениями распространяет копии своего сообщения на каждый целевой объект.

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`single_assignment`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

Принимает сообщение, которое было предложено этим `single_assignment` блоком обмена сообщениями, и возвращает копию сообщения вызывающему объекту.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект предлагаемого `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объект, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Примечания

`single_assignment`Блок обмена сообщениями возвращает копии сообщения в целевые объекты, а не передает владение текущим сообщением.

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

Использует сообщение, которое было ранее предложено `single_assignment` и зарезервировано целевым объектом, возвращая копию сообщения вызывающему объекту.

```cpp
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект для используемого `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объект, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Примечания

Аналогично `accept` , но всегда предшествует вызову `reserve` .

## <a name="has_value"></a><a name="has_value"></a>has_value

Проверяет `single_assignment` , инициализирован ли этот блок обмена сообщениями со значением.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`**, если блок получил значение; **`false`** в противном случае —.

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим `single_assignment` блоком обмена сообщениями.

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на вновь связанный целевой объект.

## <a name="propagate_message"></a><a name="propagate_message"></a>propagate_message

Асинхронно передает сообщение из `ISource` блока в этот `single_assignment` блок обмена сообщениями. Он вызывается `propagate` методом при вызове из исходного блока.

```cpp
virtual message_status propagate_message(
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

Помещает объект `message` `_PMessage` в этот `single_assignment` блок обмена сообщениями и предлагает его всем связанным целевым объектам.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message` , владельцем которого является этот `single_assignment` блок обмена сообщениями.

## <a name="release_message"></a><a name="release_message"></a>release_message

Освобождает предыдущее резервирование сообщения.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` `message` Объект для освобожденного объекта.

## <a name="reserve_message"></a><a name="reserve_message"></a>reserve_message

Резервирует сообщение, которое было ранее предложено этим `single_assignment` блоком обмена сообщениями.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` `message` Объект для резервируемого объекта.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если сообщение было успешно зарезервировано, **`false`** в противном случае.

### <a name="remarks"></a>Примечания

После `reserve` вызова метода, если он возвращает значение **`true`** , `consume` `release` метод или должен быть вызван, чтобы принять или освободить владение сообщением.

## <a name="resume_propagation"></a><a name="resume_propagation"></a>resume_propagation

Возобновляет распространение после освобождения резервирования.

```cpp
virtual void resume_propagation();
```

## <a name="send_message"></a><a name="send_message"></a>send_message

Синхронно передает сообщение из `ISource` блока в этот `single_assignment` блок обмена сообщениями. Он вызывается `send` методом при вызове из исходного блока.

```cpp
virtual message_status send_message(
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

## <a name="single_assignment"></a><a name="ctor"></a>single_assignment

Создает блок обмена сообщениями `single_assignment` .

```cpp
single_assignment();

single_assignment(
    filter_method const& _Filter);

single_assignment(
    Scheduler& _PScheduler);

single_assignment(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

single_assignment(
    ScheduleGroup& _PScheduleGroup);

single_assignment(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Параметры

*_Filter*<br/>
Функция фильтра, которая определяет, следует ли принимать предлагаемые сообщения.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `single_assignment` .

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `single_assignment` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Примечания

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .

Тип `filter_method` — это функтор с сигнатурой, `bool (T const &)` которая вызывается этим `single_assignment` блоком обмена сообщениями для определения того, следует ли принимать предложенное сообщение.

## <a name="single_assignment"></a><a name="dtor"></a>~ single_assignment

Уничтожает `single_assignment` блок обмена сообщениями.

```cpp
~single_assignment();
```

## <a name="value"></a>Значение<a name="value"></a>

Возвращает ссылку на текущие полезные данные сообщения, хранящегося в `single_assignment` блоке обмена сообщениями.

```cpp
T const& value();
```

### <a name="return-value"></a>Возвращаемое значение

Полезная нагрузка хранимого сообщения.

### <a name="remarks"></a>Примечания

Этот метод будет ожидать появления сообщения, если в данный момент в блоке обмена сообщениями не хранится ни одного сообщения `single_assignment` .

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс overwrite_buffer](overwrite-buffer-class.md)<br/>
[Класс unbounded_buffer](unbounded-buffer-class.md)
