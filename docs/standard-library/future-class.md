---
title: Класс future
ms.date: 11/04/2016
f1_keywords:
- future/std::future
- future/std::future::future
- future/std::future::get
- future/std::future::share
- future/std::future::valid
- future/std::future::wait
- future/std::future::wait_for
- future/std::future::wait_until
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
helpviewer_keywords:
- std::future [C++]
- std::future [C++], future
- std::future [C++], get
- std::future [C++], share
- std::future [C++], valid
- std::future [C++], wait
- std::future [C++], wait_for
- std::future [C++], wait_until
ms.openlocfilehash: ac52429919f83a90a87141399952e248e18e0862
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220942"
---
# <a name="future-class"></a>Класс future

Описывает *асинхронный возвращаемый объект*.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
class future;
```

## <a name="remarks"></a>Примечания

Каждый стандартный *асинхронный поставщик* возвращает объект, тип которого является экземпляром данного шаблона. Объект `future` предоставляет только доступ к асинхронному поставщику, связанному с ним. Если требуется несколько асинхронных возвращаемых объектов, связанных с одним асинхронным поставщиком, скопируйте объект `future` в объект [shared_future](../standard-library/shared-future-class.md).

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[будущем](#future)|Формирует объект `future`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get](#get)|Получает результат, который хранится в связанном асинхронном состоянии.|
|[общий ресурс](#share)|Преобразует объект в `shared_future`.|
|[допустимым](#valid)|Указывает, является ли объект не пустым.|
|[ожидания](#wait)|Блокирует текущий поток, пока не будет готово связанное асинхронное состояние.|
|[wait_for](#wait_for)|Выполняет блокировку, пока не будет готово связанное асинхронное состояние или не истечет указанный период времени.|
|[wait_until](#wait_until)|Выполняет блокировку, пока не будет готово связанное асинхронное состояние или не наступит указанный момент времени.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[future::operator=](#op_eq)|Передает связанное асинхронное состояние из указанного объекта.|

## <a name="requirements"></a>Требования

**Заголовок:**\<future>

**Пространство имен:** std

## <a name="futurefuture-constructor"></a><a name="future"></a>Конструктор future.: Future

Формирует объект `future`.

```cpp
future() noexcept;
future(future&& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Other*\
Объект `future`.

### <a name="remarks"></a>Примечания

Первый конструктор создает объект `future`, который не имеет связанного асинхронного состояния.

Второй конструктор конструирует `future` объект и передает связанное асинхронное состояние из *другого*. *Другие* больше не имеют связанного асинхронного состояния.

## <a name="futureget"></a><a name="get"></a>будущее:: Get

Получает результат, который хранится в связанном асинхронном состоянии.

```cpp
Ty get();
```

### <a name="return-value"></a>Возвращаемое значение

Если результат — исключение, метод создает его повторно. В противном случае результат будет возвращен.

### <a name="remarks"></a>Примечания

До получения результата данный метод блокирует текущий поток, пока не будет готово связанное асинхронное состояние.

Для частичной специализации `future<Ty&>` хранимое значение является ссылкой на объект, который был передан асинхронному поставщику как возвращаемое значение.

Так как для специализации не существует сохраненного значения `future<void>` , метод возвращает **`void`** .

В других специализациях метод перемещает свое возвращаемое значение из сохраненного значения. Таким образом, этот метод следует вызывать только один раз.

## <a name="futureoperator"></a><a name="op_eq"></a>Фьючерс::operator=

Передает связанное асинхронное состояние из указанного объекта.

```cpp
future& operator=(future&& Right) noexcept;
```

### <a name="parameters"></a>Параметры

*right*\
Объект `future`.

### <a name="return-value"></a>Возвращаемое значение

`*this`

### <a name="remarks"></a>Примечания

После перемещения *право* больше не имеет связанного асинхронного состояния.

## <a name="futureshare"></a><a name="share"></a>будущее:: поделиться

Преобразует объект в объект [shared_future](../standard-library/shared-future-class.md).

```cpp
shared_future<Ty> share();
```

### <a name="return-value"></a>Возвращаемое значение

`shared_future(move(*this))`

## <a name="futurevalid"></a><a name="valid"></a>будущее:: допустимое

Указывает, имеет ли объект связанное асинхронное состояние.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект имеет связанное асинхронное состояние. в противном случае — **`false`** .

## <a name="futurewait"></a><a name="wait"></a>будущее:: wait

Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready*.

```cpp
void wait() const;
```

### <a name="remarks"></a>Примечания

Связанное асинхронное состояние *Готово* , только если его асинхронный поставщик сохранил возвращаемое значение или не сохранил исключение.

## <a name="futurewait_for"></a><a name="wait_for"></a>будущее:: wait_for

Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready* или не истечет указанный период времени.

```cpp
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>Параметры

*Rel_time*\
Объект [chrono::duration](../standard-library/duration-class.md), который указывает на максимальный интервал времени, в течение которого поток может быть заблокирован.

### <a name="return-value"></a>Возвращаемое значение

Состояние [future_status](../standard-library/future-enums.md#future_status), которое указывает причину возврата.

### <a name="remarks"></a>Примечания

Связанное асинхронное состояние имеет значение "ready", только если его асинхронный поставщик сохранил возвращаемое значение или исключение.

## <a name="futurewait_until"></a><a name="wait_until"></a>будущее:: wait_until

Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready* или не наступит указанный момент времени.

```cpp
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>Параметры

*Abs_time*\
Объект [chrono::time_point](../standard-library/time-point-class.md), который указывает время, по истечении которого поток можно разблокировать.

### <a name="return-value"></a>Возвращаемое значение

Состояние [future_status](../standard-library/future-enums.md#future_status), которое указывает причину возврата.

### <a name="remarks"></a>Примечания

Связанное асинхронное состояние *Готово* , только если его асинхронный поставщик сохранил возвращаемое значение или не сохранил исключение.

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<future>](../standard-library/future.md)
