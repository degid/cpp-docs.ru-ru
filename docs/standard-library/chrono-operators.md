---
title: Операторы &lt;chrono&gt;
ms.date: 11/04/2016
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: 82f0b7b0f55cf4d71ef7c0ed92a55ca0fa1139e0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230147"
---
# <a name="ltchronogt-operators"></a>Операторы &lt;chrono&gt;

## <a name="operator-"></a><a name="operator-"></a> operator

Оператор вычитания или отрицания объектов [duration](../standard-library/duration-class.md) и [time_point](../standard-library/time-point-class.md).

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator-(
       const duration<Rep1, Period1>& Left,
       cconst duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type
   operator-(
       const time_point<Clock, Duration1>& Time,
       const duration<Rep2, Period2>& Dur);

template <class Clock, class Duration1, class Duration2>
constexpr typename common_type<Duration1, Duration2>::type
   operator-(
       const time_point<Clock, Duration1>& Left,
       const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Левый объект `duration` или объект `time_point`.

*right*\
Правый объект `duration` или объект `time_point`.

*Таймаут*\
Объект `time_point`.

*Ожидаем*\
Объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает объект `duration`, длительность интервала которого равна разнице временных интервалов двух аргументов.

Вторая функция возвращает `time_point` объект, представляющий точку во времени, которая отменяется путем отрицания интервала времени, представленного в параметре *длит*, с момента времени, заданного параметром *time*.

Третья функция возвращает `duration` объект, представляющий интервал времени между *левым* и *правым*.

## <a name="operator"></a><a name="op_neq"></a> operator!=

Оператор неравенства для объектов [duration](../standard-library/duration-class.md) и [time_point](../standard-library/time-point-class.md).

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator!=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator!=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Левый объект `duration` или объект `time_point`.

*right*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Left == Right)`.

## <a name="operator"></a><a name="op_star"></a> operator

Оператор деления для объектов [duration](../standard-library/chrono-operators.md#op_star).

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator*(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Mult);

template <class Rep1, class Rep2, class Period2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period2>
   operator*(
       const Rep1& Mult,
       const duration<Rep2,
       Period2>& Dur);
```

### <a name="parameters"></a>Параметры

*Ожидаем*\
Объект `duration`.

*Mult*\
Целочисленное значение.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает `duration` объект, длина интервала которого равна *mult* умножению на длину *длит*.

Если `is_convertible<Rep2, common_type<Rep1, Rep2>>`*содержит значение true*, первая функция не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

Если `is_convertible<Rep1, common_type<Rep1, Rep2>>`*не содержит значение true*, вторая функция не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

## <a name="operator"></a><a name="op_div"></a> operator

Оператор деления для объектов[duration](../standard-library/chrono-operators.md#op_star).

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator/(
     const duration<Rep1, Period1>& Dur,
     const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<Rep1, Rep2>::type
   operator/(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>Параметры

*Ожидаем*\
Объект `duration`.

*Div*\
Целочисленное значение.

*Слева*\
Левый объект `duration`.

*right*\
Правой объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает объект Duration, длина интервала которого равна длительности *, деленной на* значение *div*.

Второй оператор возвращает отношение длины интервалов *влево* и *вправо*.

Если `is_convertible<Rep2, common_type<Rep1, Rep2>>`*содержит значение true*, а `Rep2` не является экземпляром `duration`, первый оператор не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

## <a name="operator"></a><a name="op_add"></a> operator+

Добавляет объекты [duration](../standard-library/duration-class.md) и [time_point](../standard-library/time-point-class.md).

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator+(
      const duration<Rep1, Period1>& Left,
      const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type>
   operator+(
      const time_point<Clock, Duration1>& Time,
      const duration<Rep2, Period2>& Dur);

template <class Rep1, class Period1, class Clock, class Duration2>
time_point<Clock, constexpr typename common_type<duration<Rep1, Period1>, Duration2>::type>
   operator+(
      const duration<Rep1, Period1>& Dur,
      const time_point<Clock, Duration2>& Time);
```

### <a name="parameters"></a>Параметры

*Слева*\
Левый объект `duration` или объект `time_point`.

*right*\
Правый объект `duration` или объект `time_point`.

*Таймаут*\
Объект `time_point`.

*Ожидаем*\
Объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает `duration` объект с интервалом времени, равным сумме интервалов *слева* и *справа*.

Вторая и третья функции возвращают `time_point` объект, представляющий точку во времени, которая отменяется с интервалом в *длит*от *момента времени*.

## <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

Определяет, справедливо ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) меньше, чем другой объект `duration` или `time_point`.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator<(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Левый объект `duration` или объект `time_point`.

*right*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает значение, **`true`** Если длина интервала *Left* меньше, чем длина интервала *справа*. В противном случае функция возвращает значение **`false`** .

Вторая функция возвращает, **`true`** Если *Left* находится перед *right*. В противном случае функция возвращает значение **`false`** .

## <a name="operatorlt"></a><a name="op_lt_eq"></a> operator&lt;=

Определяет, верно ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) меньше другого объекта `duration` или `time_point` или равен ему.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator<=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Левый объект `duration` или объект `time_point`.

*right*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Right < Left)`.

## <a name="operator"></a><a name="op_eq_eq"></a> operator==

Определяет, справедливо ли, что два объекта `duration` представляют интервалы времени, имеющие одинаковую длину, или, что два объекта `time_point` представляют один и тот же момент времени.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator==(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator==(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Левый объект `duration` или объект `time_point`.

*right*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает, **`true`** Если *Left* и *right* представляют интервалы времени, имеющие одинаковую длину. В противном случае функция возвращает значение **`false`** .

Вторая функция возвращает **`true`** , если *Left* и *right* представляют один и тот же момент времени. В противном случае функция возвращает значение **`false`** .

## <a name="operatorgt"></a><a name="op_gt"></a> operator&gt;

Определяет, верно ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) больше, чем другой объект `duration` или `time_point`.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Левый объект `duration` или объект `time_point`.

*right*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `Right < Left`.

## <a name="operatorgt"></a><a name="op_gt_eq"></a> operator&gt;=

Определяет, верно ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) больше другого объекта `duration` или `time_point` или равен ему.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Левый объект `duration` или объект `time_point`.

*right*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Left < Right)`.

## <a name="operator-modulo"></a><a name="op_modulo"></a>оператор остатка от деления

Оператор для операций вычисления остатка от деления над объектами [duration](../standard-library/duration-class.md).

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<Rep1, Period1, Rep2>::type
   operator%(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, _Period1>, duration<Rep2, Period2>>::type
   operator%(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>Параметры

*Ожидаем*\
Объект `duration`.

*Div*\
Целочисленное значение.

*Слева*\
Левый объект `duration`.

*right*\
Правой объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает `duration` объект, длина интервала которого равна длительности по модулю *div*. *Dur*

Вторая функция возвращает значение, представляющее *левый* остаток *от*деления.
