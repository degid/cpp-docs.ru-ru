---
title: Класс shared_future
ms.date: 11/04/2016
f1_keywords:
- future/std::shared_future
- future/std::shared_future::shared_future
- future/std::shared_future::get
- future/std::shared_future::valid
- future/std::shared_future::wait
- future/std::shared_future::wait_for
- future/std::shared_future::wait_until
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
helpviewer_keywords:
- std::shared_future [C++]
- std::shared_future [C++], shared_future
- std::shared_future [C++], get
- std::shared_future [C++], valid
- std::shared_future [C++], wait
- std::shared_future [C++], wait_for
- std::shared_future [C++], wait_until
ms.openlocfilehash: dcc1f4bf1ce25890945f1d9e207f2363122c0ad2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217497"
---
# <a name="shared_future-class"></a>Класс shared_future

Описывает *асинхронный возвращаемый объект*. В отличие от объекта [future](../standard-library/future-class.md), *асинхронный поставщик* может быть связан с любым числом объектов `shared_future`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
class shared_future;
```

## <a name="remarks"></a>Примечания

Не вызывайте никакие методы, кроме `valid`, `operator=`, и деструктор в объекте `shared_future`, который является *пустым*.

Объекты `shared_future` не синхронизируются. Вызов методов из нескольких потоков для одного объекта становится причиной состязания за данные с непредсказуемыми результатами.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[shared_future](#shared_future)|Формирует объект `shared_future`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get](#get)|Получает результат, который хранится в *связанном асинхронном состоянии*.|
|[допустимым](#valid)|Указывает, является ли объект не пустым.|
|[ожидания](#wait)|Блокирует текущий поток, пока не будет готово связанное асинхронное состояние.|
|[wait_for](#wait_for)|Выполняет блокировку, пока не будет готово связанное асинхронное состояние или не истечет указанный период времени.|
|[wait_until](#wait_until)|Выполняет блокировку, пока не будет готово связанное асинхронное состояние или не наступит указанный момент времени.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[shared_future::operator=](#op_eq)|Назначает новое связанное асинхронное состояние.|

## <a name="requirements"></a>Требования

**Заголовок:**\<future>

**Пространство имен:** std

## <a name="shared_futureget"></a><a name="get"></a>shared_future:: Get

Получает результат, который хранится в *связанном асинхронном состоянии*.

```cpp
const Ty& get() const;

Ty& get() const;

void get() const;
```

### <a name="remarks"></a>Примечания

Если результат — исключение, метод создает его повторно. В противном случае результат будет возвращен.

До получения результата данный метод блокирует текущий поток, пока не будет готово связанное асинхронное состояние.

Для частичной специализации `shared_future<Ty&>` хранимое значение фактически является ссылкой на объект, который был передан *асинхронному поставщику* в качестве возвращаемого значения.

Так как для специализации не существует сохраненного значения `shared_future<void>` , метод возвращает **`void`** .

## <a name="shared_futureoperator"></a><a name="op_eq"></a>shared_future::operator=

Передает *связанное асинхронное состояние* из указанного объекта.

```cpp
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```

### <a name="parameters"></a>Параметры

*right*\
Объект `shared_future`.

### <a name="return-value"></a>Возвращаемое значение

`*this`

### <a name="remarks"></a>Примечания

Для первого оператора *право* больше не имеет связанного асинхронного состояния после операции.

Во втором методе свойство *right* сохраняет связанное с ним асинхронное состояние.

## <a name="shared_futureshared_future-constructor"></a><a name="shared_future"></a>Конструктор shared_future:: shared_future

Формирует объект `shared_future`.

```cpp
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```

### <a name="parameters"></a>Параметры

*right*\
Класс [future](../standard-library/future-class.md) или объект `shared_future`.

### <a name="remarks"></a>Примечания

Первый конструктор конструирует `shared_future` объект, который не имеет *связанного асинхронного состояния*.

Второй и третий конструкторы создают `shared_future` объект и передают связанное асинхронное состояние *справа*. *Право* больше не имеет связанного асинхронного состояния.

Четвертый конструктор конструирует `shared_future` объект, имеющий то же связанное асинхронное состояние, что и *право*.

## <a name="shared_futurevalid"></a><a name="valid"></a>shared_future:: допустимое

Указывает, имеет ли объект *связанное асинхронное состояние*.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект имеет связанное асинхронное состояние. в противном случае — **`false`** .

## <a name="shared_futurewait"></a><a name="wait"></a>shared_future:: wait

Блокирует текущий поток, пока *связанное асинхронное состояние* не будет *Готово*.

```cpp
void wait() const;
```

### <a name="remarks"></a>Примечания

Связанное асинхронное состояние имеет значение "ready", только если его асинхронный поставщик сохранил возвращаемое значение или исключение.

## <a name="shared_futurewait_for"></a><a name="wait_for"></a>shared_future:: wait_for

Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready* или не истечет указанный период времени.

```cpp
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>Параметры

*Rel_time*\
Объект [chrono::duration](../standard-library/duration-class.md), который указывает на максимальный интервал времени, в течение которого поток может быть заблокирован.

### <a name="return-value"></a>Возвращаемое значение

Состояние [future_status](../standard-library/future-enums.md#future_status), которое указывает причину возврата.

### <a name="remarks"></a>Примечания

Связанное асинхронное состояние *Готово* , только если его асинхронный поставщик сохранил возвращаемое значение или не сохранил исключение.

## <a name="shared_futurewait_until"></a><a name="wait_until"></a>shared_future:: wait_until

Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready* или не наступит указанный момент времени.

```cpp
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>Параметры

*Abs_time*\
Объект [chrono::time_point](../standard-library/time-point-class.md), который указывает время, по истечении которого поток можно разблокировать.

### <a name="return-value"></a>Возвращаемое значение

Состояние [future_status](../standard-library/future-enums.md#future_status), которое указывает причину возврата.

### <a name="remarks"></a>Примечания

Связанное асинхронное состояние имеет значение "ready", только если его асинхронный поставщик сохранил возвращаемое значение или исключение.

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<future>](../standard-library/future.md)
