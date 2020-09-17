---
title: Класс choice
ms.date: 11/04/2016
f1_keywords:
- choice
- AGENTS/concurrency::choice
- AGENTS/concurrency::choice::choice
- AGENTS/concurrency::choice::accept
- AGENTS/concurrency::choice::acquire_ref
- AGENTS/concurrency::choice::consume
- AGENTS/concurrency::choice::has_value
- AGENTS/concurrency::choice::index
- AGENTS/concurrency::choice::link_target
- AGENTS/concurrency::choice::release
- AGENTS/concurrency::choice::release_ref
- AGENTS/concurrency::choice::reserve
- AGENTS/concurrency::choice::unlink_target
- AGENTS/concurrency::choice::unlink_targets
- AGENTS/concurrency::choice::value
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
ms.openlocfilehash: a5b9bc26b6d9ec66dc74e7adaad31eea1eece118
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224985"
---
# <a name="choice-class"></a>Класс choice

Блок обмена сообщениями `choice` — это блок с несколькими источниками и одной целью, который представляет взаимодействие потока управления с набором источников. Блок choice будет ожидать доступа к любому из нескольких источников для создания сообщения и распространит индекс источника, создавшего сообщение.

## <a name="syntax"></a>Синтаксис

```cpp
template<
    class T
>
class choice: public ISource<size_t>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
`tuple`Тип на основе, представляющий полезные данные источников входных данных.

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`type`|Псевдоним типа для `T` .|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[choice](#ctor)|Перегружен. Создает блок обмена сообщениями `choice` .|
|[Деструктор выбора ~](#dtor)|Уничтожает `choice` блок обмена сообщениями.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[гласит](#accept)|Принимает сообщение, которое было предложено этим `choice` блоком, передавая владение вызывающему объекту.|
|[acquire_ref](#acquire_ref)|Получает счетчик ссылок `choice` для этого блока обмена сообщениями, чтобы предотвратить удаление.|
|[потребляющие](#consume)|Использует сообщение, которое было ранее предложено этим `choice` блоком обмена сообщениями и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[has_value](#has_value)|Проверяет `choice` , инициализирован ли этот блок обмена сообщениями со значением.|
|[номер](#index)|Возвращает индекс в, `tuple` представляющий элемент, выбранный `choice` блоком обмена сообщениями.|
|[link_target](#link_target)|Связывает целевой блок с этим `choice` блоком обмена сообщениями.|
|[отпускании](#release)|Освобождает предыдущее успешное резервирование сообщения.|
|[release_ref](#release_ref)|Освобождает счетчик ссылок в этом `choice` блоке обмена сообщениями.|
|[reserve](#reserve)|Резервирует сообщение, которое было ранее предложено этим `choice` блоком обмена сообщениями.|
|[unlink_target](#unlink_target)|Отменяет связь целевого блока с этим `choice` блоком обмена сообщениями.|
|[unlink_targets](#unlink_targets)|Отменяет связь со всеми целевыми объектами из этого `choice` блока обмена сообщениями. (Переопределяет метод [ISource:: unlink_targets](isource-class.md#unlink_targets).)|
|[value](#value)|Возвращает сообщение, чей индекс был выбран `choice` блоком обмена сообщениями.|

## <a name="remarks"></a>Примечания

Блок Choice гарантирует, что будет использоваться только одно из входящих сообщений.

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

`choice`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept"></a><a name="accept"></a>гласит

Принимает сообщение, которое было предложено этим `choice` блоком, передавая владение вызывающему объекту.

```cpp
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `accept` метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение о том, что вызывающий объект теперь является владельцем.

## <a name="acquire_ref"></a><a name="acquire_ref"></a>acquire_ref

Получает счетчик ссылок `choice` для этого блока обмена сообщениями, чтобы предотвратить удаление.

```cpp
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объектом, который связан с этим источником во время выполнения `link_target` метода.

## <a name="choice"></a><a name="ctor"></a>усмотрени

Создает блок обмена сообщениями `choice` .

```cpp
explicit choice(
    T _Tuple);

choice(
    Scheduler& _PScheduler,
    T _Tuple);

choice(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

choice(
    choice&& _Choice);
```

### <a name="parameters"></a>Параметры

*_Tuple*<br/>
Объект `tuple` источников по выбору.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `choice` .

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `choice` . Используемый объект `Scheduler` подразумевается группой расписаний.

*_Choice*<br/>
Блок обмена сообщениями `choice` , из которого выполняется копирование. Обратите внимание, что исходный объект становится потерянным, превращая этот конструктор в конструктор перемещения.

### <a name="remarks"></a>Примечания

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .

Конструкция перемещения не выполняется при блокировке. Это означает, что пользователь должен убедиться в отсутствии простых задач во время перемещения. В противном случае могут возникнуть многочисленные гонки, приводящие к исключениям или недопустимому состоянию.

## <a name="choice"></a><a name="dtor"></a>~ Choice

Уничтожает `choice` блок обмена сообщениями.

```cpp
~choice();
```

## <a name="consume"></a><a name="consume"></a>потребляющие

Использует сообщение, которое было ранее предложено этим `choice` блоком обмена сообщениями и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.

```cpp
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
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

## <a name="has_value"></a><a name="has_value"></a>has_value

Проверяет `choice` , инициализирован ли этот блок обмена сообщениями со значением.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`**, если блок получил значение; **`false`** в противном случае —.

## <a name="index"></a><a name="index"></a>номер

Возвращает индекс в, `tuple` представляющий элемент, выбранный `choice` блоком обмена сообщениями.

```cpp
size_t index();
```

### <a name="return-value"></a>Возвращаемое значение

Индекс сообщения.

### <a name="remarks"></a>Примечания

Полезные данные сообщения можно извлечь с помощью `get` метода.

## <a name="link_target"></a><a name="link_target"></a>link_target

Связывает целевой блок с этим `choice` блоком обмена сообщениями.

```cpp
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на `ITarget` блок, связываемый с этим `choice` блоком обмена сообщениями.

## <a name="release"></a><a name="release"></a>отпускании

Освобождает предыдущее успешное резервирование сообщения.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` `message` Объект для освобожденного объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `release` метод.

## <a name="release_ref"></a><a name="release_ref"></a>release_ref

Освобождает счетчик ссылок в этом `choice` блоке обмена сообщениями.

```cpp
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объектом, для которого удаляется связь из этого источника. Блоку источника разрешено освобождать все ресурсы, зарезервированные для целевого блока.

## <a name="reserve"></a><a name="reserve"></a>предназначен

Резервирует сообщение, которое было ранее предложено этим `choice` блоком обмена сообщениями.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
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

Отменяет связь целевого блока с этим `choice` блоком обмена сообщениями.

```cpp
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на `ITarget` блок, который необходимо удалить из этого `choice` блока сообщений.

## <a name="unlink_targets"></a><a name="unlink_targets"></a>unlink_targets

Отменяет связь со всеми целевыми объектами из этого `choice` блока обмена сообщениями.

```cpp
virtual void unlink_targets();
```

### <a name="remarks"></a>Примечания

Этот метод не требуется вызывать из деструктора, так как деструктор для внутреннего `single_assignment` блока будет иметь правильную связь.

## <a name="value"></a>Значение<a name="value"></a>

Возвращает сообщение, чей индекс был выбран `choice` блоком обмена сообщениями.

```cpp
template <
    typename _Payload_type
>
_Payload_type const& value();
```

### <a name="parameters"></a>Параметры

*_Payload_type*<br/>
Тип полезных данных сообщения.

### <a name="return-value"></a>Возвращаемое значение

Полезные данные сообщения.

### <a name="remarks"></a>Примечания

Поскольку блок сообщений `choice` может принимать входные данные с различными типами полезной нагрузки, необходимо указать тип полезной нагрузки в момент извлечения. Тип можно определить на основе результата `index` метода.

## <a name="see-also"></a>См. также статью

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс join](join-class.md)<br/>
[Класс single_assignment](single-assignment-class.md)
