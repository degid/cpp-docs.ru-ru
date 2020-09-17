---
title: Класс timer
ms.date: 11/04/2016
f1_keywords:
- timer
- AGENTS/concurrency::timer
- AGENTS/concurrency::timer::timer
- AGENTS/concurrency::timer::pause
- AGENTS/concurrency::timer::start
- AGENTS/concurrency::timer::stop
- AGENTS/concurrency::timer::accept_message
- AGENTS/concurrency::timer::consume_message
- AGENTS/concurrency::timer::link_target_notification
- AGENTS/concurrency::timer::propagate_to_any_targets
- AGENTS/concurrency::timer::release_message
- AGENTS/concurrency::timer::reserve_message
- AGENTS/concurrency::timer::resume_propagation
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
ms.openlocfilehash: 026aef03bb813585decb206c1691835330a4dd05
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224946"
---
# <a name="timer-class"></a>Класс timer

Блок обмена сообщениями `timer` — это блок `source_block` с одной целью, который может отправлять сообщение своей цели по истечении указанного периода времени или через заданные интервалы времени.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных выходных сообщений этого блока.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[активности](#ctor)|Перегружен. Конструирует `timer` блок обмена сообщениями, который будет запускать заданное сообщение после указанного интервала.|
|[Деструктор ~ Timer](#dtor)|Уничтожает `timer` блок обмена сообщениями.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[pause](#pause)|Останавливает `timer` блок обмена сообщениями. Если это `timer` блок повторяющегося обмена сообщениями, его можно перезапустить при последующем `start()` вызове. Для неповторяющихся таймеров это действие аналогично `stop` вызову.|
|[start](#start)|Запускает `timer` блок обмена сообщениями. Указанное число миллисекунд после вызова этого параметра, указанное значение будет распространяться в нисходящем направлении как `message` .|
|[stop](#stop)|Останавливает `timer` блок обмена сообщениями.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[accept_message](#accept_message)|Принимает сообщение, которое было предложено этим `timer` блоком обмена сообщениями, передавая владение вызывающему объекту.|
|[consume_message](#consume_message)|Использует сообщение, которое было ранее предложено `timer` и зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[link_target_notification](#link_target_notification)|Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим `timer` блоком обмена сообщениями.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Пытается предложить сообщение, созданное `timer` блоком, ко всем связанным целевым объектам.|
|[release_message](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Резервирует сообщение, которое было ранее предложено этим `timer` блоком обмена сообщениями. (Переопределяет [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Возобновляет распространение после освобождения резервирования. (Переопределяет [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

[source_block](source-block-class.md)

`timer`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

Принимает сообщение, которое было предложено этим `timer` блоком обмена сообщениями, передавая владение вызывающему объекту.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект предлагаемого `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объект, владельцем которого стал вызывающий объект.

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

Использует сообщение, которое было ранее предложено `timer` и зарезервировано целевым объектом, передавая владение вызывающему объекту.

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

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим `timer` блоком обмена сообщениями.

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на вновь связанный целевой объект.

## <a name="pause"></a><a name="pause"></a>работу

Останавливает `timer` блок обмена сообщениями. Если это `timer` блок повторяющегося обмена сообщениями, его можно перезапустить при последующем `start()` вызове. Для неповторяющихся таймеров это действие аналогично `stop` вызову.

```cpp
void pause();
```

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets

Пытается предложить сообщение, созданное `timer` блоком, ко всем связанным целевым объектам.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
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

Резервирует сообщение, которое было ранее предложено этим `timer` блоком обмена сообщениями.

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

## <a name="start"></a><a name="start"></a>запустить

Запускает `timer` блок обмена сообщениями. Указанное число миллисекунд после вызова этого параметра, указанное значение будет распространяться в нисходящем направлении как `message` .

```cpp
void start();
```

## <a name="stop"></a><a name="stop"></a>позиции

Останавливает `timer` блок обмена сообщениями.

```cpp
void stop();
```

## <a name="timer"></a><a name="ctor"></a>активности

Конструирует `timer` блок обмена сообщениями, который будет запускать заданное сообщение после указанного интервала.

```cpp
timer(
    unsigned int _Ms,
    T const& value,
    ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    Scheduler& _Scheduler,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    ScheduleGroup& _ScheduleGroup,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);
```

### <a name="parameters"></a>Параметры

*_Ms*<br/>
Число миллисекунд, которое должно пройти после вызова метода Start для указанного сообщения, чтобы передать его в нисходящее распространение.

*value*<br/>
Значение, которое будет распространяться дальше по истечении времени ожидания.

*_PTarget*<br/>
Целевой объект, в который таймер будет распространять свое сообщение.

*_Repeating*<br/>
Значение true показывает, что таймер будет срабатывать каждые `_Ms` миллисекунды.

*_Scheduler*<br/>
`Scheduler`Объект, в котором запланирована задача распространения для `timer` блока обмена сообщениями.

*_ScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `timer` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Примечания

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_Scheduler` или `_ScheduleGroup` .

## <a name="timer"></a><a name="dtor"></a>~ Timer

Уничтожает `timer` блок обмена сообщениями.

```cpp
~timer();
```

## <a name="see-also"></a>См. также статью

[Пространство имен Concurrency](concurrency-namespace.md)
