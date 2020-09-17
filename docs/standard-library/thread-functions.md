---
title: Функции &lt;thread&gt;
ms.date: 11/04/2016
f1_keywords:
- thread/std::get_id
- thread/std::sleep_for
- thread/std::sleep_until
- thread/std::swap
- thread/std::yield
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
helpviewer_keywords:
- std::get_id [C++]
- std::sleep_for [C++]
- std::sleep_until [C++]
- std::swap [C++]
- std::yield [C++]
ms.openlocfilehash: 64a62180243d77f361c243b2a89de56b0a14920e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845046"
---
# <a name="ltthreadgt-functions"></a>Функции &lt;thread&gt;

[get_id](#get_id)\
[sleep_for](#sleep_for)\
[sleep_until](#sleep_until)\
[swap](#swap)\
[yield](#yield)

## <a name="get_id"></a><a name="get_id"></a> get_id

Уникально идентифицирует текущий поток выполнения.

```cpp
thread::id this_thread::get_id() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Объект типа [thread::id](../standard-library/thread-class.md), который уникально идентифицирует текущий поток выполнения.

## <a name="sleep_for"></a><a name="sleep_for"></a> sleep_for

Блокирует вызывающий поток.

```cpp
template <class Rep,
class Period>
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Параметры

*Rel_time*\
Объект [duration](../standard-library/duration-class.md), задающий интервал времени.

### <a name="remarks"></a>Примечания

Функция блокирует вызывающий поток в течение как минимум времени, заданного *Rel_time*. Эта функция не вызывает исключений.

## <a name="sleep_until"></a><a name="sleep_until"></a> sleep_until

Блокирует вызывающий поток по крайней мере до указанного времени.

```cpp
template <class Clock, class Duration>
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```

### <a name="parameters"></a>Параметры

*Abs_time*\
Представляет момент времени.

### <a name="remarks"></a>Примечания

Эта функция не вызывает исключений.

## <a name="swap"></a><a name="swap"></a> swap

Меняет местами состояния двух объектов `thread`.

```cpp
void swap(thread& Left, thread& Right) noexcept;
```

### <a name="parameters"></a>Параметры

*Слева*\
Левый объект `thread`.

*right*\
Правой объект `thread`.

### <a name="remarks"></a>Примечания

Функция вызывает `Left.swap(Right)`.

## <a name="yield"></a><a name="yield"></a> Получает

Сигнализирует операционной системе, что необходимо запустить другие потоки, даже если в обычной ситуации текущий поток продолжал бы выполняться.

```cpp
inline void yield() noexcept;
```

## <a name="see-also"></a>См. также раздел

[\<thread>](../standard-library/thread.md)
