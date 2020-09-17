---
title: Класс condition_variable_any
ms.date: 11/04/2016
f1_keywords:
- condition_variable/std::condition_variable_any
- condition_variable/std::condition_variable_any::condition_variable_any
- condition_variable/std::condition_variable_any::notify_all
- condition_variable/std::condition_variable_any::notify_one
- condition_variable/std::condition_variable_any::wait
- condition_variable/std::condition_variable_any::wait_for
- condition_variable/std::condition_variable_any::wait_until
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
helpviewer_keywords:
- std::condition_variable_any
- std::condition_variable_any::condition_variable_any
- std::condition_variable_any::notify_all
- std::condition_variable_any::notify_one
- std::condition_variable_any::wait
- std::condition_variable_any::wait_for
- std::condition_variable_any::wait_until
ms.openlocfilehash: 9dc73de515aa8e321dbb28ca4a859b256613fbfe
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831481"
---
# <a name="condition_variable_any-class"></a>Класс condition_variable_any

Класс `condition_variable_any` используется для ожидания события, которое имеет любой тип `mutex`.

## <a name="syntax"></a>Синтаксис

```cpp
class condition_variable_any;
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[condition_variable_any](#condition_variable_any)|Формирует объект `condition_variable_any`.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[notify_all](#notify_all)|Разблокирует все потоки, которые ожидают объект `condition_variable_any`.|
|[notify_one](#notify_one)|Разблокирует один из потоков, которые ожидают объект `condition_variable_any`.|
|[ожидания](#wait)|Блокирует поток.|
|[wait_for](#wait_for)|Блокирует поток и задает интервал времени, после которого поток разблокируется.|
|[wait_until](#wait_until)|Блокирует поток и задает максимальный момент времени, в который поток разблокируется.|

## <a name="condition_variable_any"></a><a name="condition_variable_any"></a> condition_variable_any

Формирует объект `condition_variable_any`.

```cpp
condition_variable_any();
```

### <a name="remarks"></a>Примечания

При недостатке памяти этот конструктор вызывает объект [system_error](../standard-library/system-error-class.md), имеющий код ошибки `not_enough_memory`. Если объект не может быть создан из-за недоступности некоторых других ресурсов, конструктор создает объект `system_error`, имеющий код ошибки `resource_unavailable_try_again`.

## <a name="notify_all"></a><a name="notify_all"></a> notify_all

Разблокирует все потоки, которые ожидают объект `condition_variable_any`.

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a><a name="notify_one"></a> notify_one

Разблокирует один из потоков, которые ожидают объект `condition_variable_any`.

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a><a name="wait"></a> ожидания

Блокирует поток.

```cpp
template <class Lock>
void wait(Lock& Lck);

template <class Lock, class Predicate>
void wait(Lock& Lck, Predicate Pred);
```

### <a name="parameters"></a>Параметры

*лкк*\
Объект `mutex` любого типа.

*pred*\
Любое выражение, возвращающее значение **`true`** или **`false`** .

### <a name="remarks"></a>Примечания

Первый метод блокируется до оповещения объекта `condition_variable_any` путем вызова [notify_one](../standard-library/condition-variable-class.md#notify_one) или [notify_all](../standard-library/condition-variable-class.md#notify_all). Он может также ложно активироваться.

Второй метод фактически выполняет следующий код.

```cpp
while (!Pred())
    wait(Lck);
```

## <a name="wait_for"></a><a name="wait_for"></a> wait_for

Блокирует поток и задает интервал времени, после которого поток разблокируется.

```cpp
template <class Lock, class Rep, class Period>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time);

template <class Lock, class Rep, class Period, class Predicate>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time, Predicate Pred);
```

### <a name="parameters"></a>Параметры

*лкк*\
Объект `mutex` любого типа.

*Rel_time*\
Объект `chrono::duration`, указывающий количество времени до активации потока.

*pred*\
Любое выражение, возвращающее значение **`true`** или **`false`** .

### <a name="return-value"></a>Возвращаемое значение

Первый метод возвращает значение `cv_status::timeout` , если ожидание завершается по истечении *Rel_time* . В противном случае метод возвращает значение `cv_status::no_timeout`.

Второй метод возвращает значение *пред*.

### <a name="remarks"></a>Примечания

Первый метод блокируется до `condition_variable_any` сигнализации объекта вызовом [notify_one](../standard-library/condition-variable-class.md#notify_one) или [notify_all](../standard-library/condition-variable-class.md#notify_all)или до истечения интервала времени *Rel_time* . Он может также ложно активироваться.

Второй метод фактически выполняет следующий код.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a><a name="wait_until"></a> wait_until

Блокирует поток и задает максимальный момент времени, в который поток разблокируется.

```cpp
template <class Lock, class Clock, class Duration>
void wait_until(Lock& Lck, const chrono::time_point<Clock, Duration>& Abs_time);

template <class Lock, class Clock, class Duration, class Predicate>
void wait_until(
    Lock& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

template <class Lock>
void wait_until(Lock Lck, const xtime* Abs_time);

template <class Lock, class Predicate>
void wait_until(
    Lock Lck,
    const xtime* Abs_time,
    Predicate Pred);
```

### <a name="parameters"></a>Параметры

*лкк*\
Объект mutex.

*Abs_time*\
Объект [chrono::time_point](../standard-library/time-point-class.md).

*pred*\
Любое выражение, возвращающее значение **`true`** или **`false`** .

### <a name="return-value"></a>Возвращаемое значение

Методы, возвращающие `cv_status` тип, возвращают, `cv_status::timeout` Если ожидание завершается по истечении *Abs_time* . В противном случае эти методы возвращают `cv_status::no_timeout`.

Методы, возвращающие, **`bool`** возвращают значение " *пред*".

### <a name="remarks"></a>Примечания

Первый метод блокируется до `condition_variable` сигнализации объекта вызовом [notify_one](../standard-library/condition-variable-class.md#notify_one) или [notify_all](../standard-library/condition-variable-class.md#notify_all)или до *Abs_time*. Он может также ложно активироваться.

Второй метод фактически выполняет следующий код.

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

Третий и четвертый методы используют указатель на объект типа `xtime` для замены объекта `chrono::time_point`. Объект `xtime` задает максимальное время ожидания сигнала.
