---
title: Класс multitype_join
ms.date: 11/04/2016
f1_keywords:
- multitype_join
- AGENTS/concurrency::multitype_join
- AGENTS/concurrency::multitype_join::multitype_join
- AGENTS/concurrency::multitype_join::accept
- AGENTS/concurrency::multitype_join::acquire_ref
- AGENTS/concurrency::multitype_join::consume
- AGENTS/concurrency::multitype_join::link_target
- AGENTS/concurrency::multitype_join::release
- AGENTS/concurrency::multitype_join::release_ref
- AGENTS/concurrency::multitype_join::reserve
- AGENTS/concurrency::multitype_join::unlink_target
- AGENTS/concurrency::multitype_join::unlink_targets
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
ms.openlocfilehash: c648e77e404cf39eab281a93e03d8b427da375f8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87205864"
---
# <a name="multitype_join-class"></a>Класс multitype_join

Блок обмена сообщениями `multitype_join` — это блок с несколькими источниками и одной целью, который объединяет сообщения разных типов от каждого из своих источников и предлагает кортеж объединенных сообщений своему целевому объекту.

## <a name="syntax"></a>Синтаксис

```cpp
template<
    typename T,
    join_type _Jtype = non_greedy
>
class multitype_join: public ISource<typename _Unwrap<T>::type>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
`tuple`Тип полезных данных сообщений, соединяемых и распространяемых блоком.

*_Jtype*<br/>
Тип `join` блока: `greedy` или`non_greedy`

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`type`|Псевдоним типа для `T` .|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[multitype_join](#ctor)|Перегружен. Создает блок обмена сообщениями `multitype_join` .|
|[Деструктор ~ multitype_join](#dtor)|Уничтожает `multitype_join` блок обмена сообщениями.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[гласит](#accept)|Принимает сообщение, которое было предложено этим `multitype_join` блоком, передавая владение вызывающему объекту.|
|[acquire_ref](#acquire_ref)|Получает счетчик ссылок `multitype_join` для этого блока обмена сообщениями, чтобы предотвратить удаление.|
|[потребляющие](#consume)|Использует сообщение, которое было ранее предложено `multitype_join` блоком обмена сообщениями и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[link_target](#link_target)|Связывает целевой блок с этим `multitype_join` блоком обмена сообщениями.|
|[отпускании](#release)|Освобождает предыдущее успешное резервирование сообщения.|
|[release_ref](#release_ref)|Освобождает счетчик ссылок в этом `multiple_join` блоке обмена сообщениями.|
|[reserve](#reserve)|Резервирует сообщение, которое было ранее предложено этим `multitype_join` блоком обмена сообщениями.|
|[unlink_target](#unlink_target)|Отменяет связь целевого блока с этим `multitype_join` блоком обмена сообщениями.|
|[unlink_targets](#unlink_targets)|Отменяет связь со всеми целевыми объектами из этого `multitype_join` блока обмена сообщениями. (Переопределяет метод [ISource:: unlink_targets](isource-class.md#unlink_targets).)|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

`multitype_join`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept"></a><a name="accept"></a>гласит

Принимает сообщение, которое было предложено этим `multitype_join` блоком, передавая владение вызывающему объекту.

```cpp
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `accept` метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение о том, что вызывающий объект теперь является владельцем.

## <a name="acquire_ref"></a><a name="acquire_ref"></a>acquire_ref

Получает счетчик ссылок `multitype_join` для этого блока обмена сообщениями, чтобы предотвратить удаление.

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объектом, который связан с этим источником во время выполнения `link_target` метода.

## <a name="consume"></a><a name="consume"></a>потребляющие

Использует сообщение, которое было ранее предложено `multitype_join` блоком обмена сообщениями и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.

```cpp
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект зарезервированного `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `consume` метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объект, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Примечания

`consume`Метод аналогичен `accept` , но ему всегда должен предшествовать вызов `reserve` , который возвращает **`true`** .

## <a name="link_target"></a><a name="link_target"></a>link_target

Связывает целевой блок с этим `multitype_join` блоком обмена сообщениями.

```cpp
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на `ITarget` блок, связываемый с этим `multitype_join` блоком обмена сообщениями.

## <a name="multitype_join"></a><a name="ctor"></a>multitype_join

Создает блок обмена сообщениями `multitype_join` .

```cpp
explicit multitype_join(
    T _Tuple);

multitype_join(
    Scheduler& _PScheduler,
    T _Tuple);

multitype_join(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

multitype_join(
    multitype_join&& _Join);
```

### <a name="parameters"></a>Параметры

*_Tuple*<br/>
Объект `tuple` источников для этого блока обмена сообщениями `multitype_join` .

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` .

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` . Используемый объект `Scheduler` подразумевается группой расписаний.

*_Join*<br/>
Блок обмена сообщениями `multitype_join` , из которого выполняется копирование. Обратите внимание, что исходный объект становится потерянным, превращая этот конструктор в конструктор перемещения.

### <a name="remarks"></a>Примечания

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .

Конструкция перемещения не выполняется при блокировке. Это означает, что пользователь должен убедиться в отсутствии простых задач во время перемещения. В противном случае могут возникнуть многочисленные гонки, приводящие к исключениям или недопустимому состоянию.

## <a name="multitype_join"></a><a name="dtor"></a>~ multitype_join

Уничтожает `multitype_join` блок обмена сообщениями.

```cpp
~multitype_join();
```

## <a name="release"></a><a name="release"></a>отпускании

Освобождает предыдущее успешное резервирование сообщения.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` `message` Объект для освобожденного объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `release` метод.

## <a name="release_ref"></a><a name="release_ref"></a>release_ref

Освобождает счетчик ссылок в этом `multiple_join` блоке обмена сообщениями.

```cpp
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объектом, для которого удаляется связь из этого источника. Блоку источника разрешено освобождать все ресурсы, зарезервированные для целевого блока.

## <a name="reserve"></a><a name="reserve"></a>предназначен

Резервирует сообщение, которое было ранее предложено этим `multitype_join` блоком обмена сообщениями.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` `message` Объект для резервируемого объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `reserve` метод.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если сообщение было успешно зарезервировано, **`false`** в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.

### <a name="remarks"></a>Примечания

После вызова метода `reserve` , если он выполняется, необходимо вызвать метод `consume` или `release` , чтобы получить или предоставить владение сообщениями соответственно.

## <a name="unlink_target"></a><a name="unlink_target"></a>unlink_target

Отменяет связь целевого блока с этим `multitype_join` блоком обмена сообщениями.

```cpp
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на `ITarget` блок, который необходимо удалить из этого `multitype_join` блока сообщений.

## <a name="unlink_targets"></a><a name="unlink_targets"></a>unlink_targets

Отменяет связь со всеми целевыми объектами из этого `multitype_join` блока обмена сообщениями.

```cpp
virtual void unlink_targets();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс choice](choice-class.md)<br/>
[Класс join](join-class.md)
