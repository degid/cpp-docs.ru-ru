---
title: '&lt;необязательные &gt; операторы'
ms.date: 11/04/2016
f1_keywords:
- optional/std::operator!=
- optional/std::operator==
- optional/std::operatoroperator&gt;
- optional/std::operatoroperator&gt=;
- optional/std::operatoroperator&lt;
- optional/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (optional)
- std::operator== (optional)
- std::operatoroperator&gt; (optional)
- std::operatoroperator&gt=; (optional)
- std::operatoroperator&lt; (optional)
- std::operatoroperator&lt;= (optional)
ms.openlocfilehash: c7eca76f71f12e7f7fe0e60c0a4cfe456d54c374
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224686"
---
# <a name="ltoptionalgt-operators"></a>&lt;необязательные &gt; операторы

## <a name="operator"></a><a name="op_eq_eq"></a> operator==

Проверяет равенство объекта `optional` слева от оператора объекту `optional` справа от оператора.

```cpp
template <class T, class U> constexpr bool operator==(const optional<T>& left, const optional<U>& right);
template <class T> constexpr bool operator==(const optional<T>& left, nullopt_t right) noexcept;
template <class T> constexpr bool operator==(nullopt_t left, const optional<T>& right) noexcept;
template <class T, class U> constexpr bool operator==(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator==(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `optional` , `nullopt_t` или `T` .

*right*\
Объект типа `optional` , `nullopt_t` или `T` .

## <a name="operator"></a><a name="op_neq"></a> operator!=

Проверяет неравенство объекта `optional` слева от оператора объекту `optional` справа от оператора.

```cpp
template <class T, class U> constexpr bool operator!=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator!=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator!=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator!=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator!=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `optional` , `nullopt_t` или `T` .

*right*\
Объект типа `optional` , `nullopt_t` или `T` .

### <a name="remarks"></a>Примечания

Эта функция шаблона возвращает `!(left == right)`.

## <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

Проверяет, меньше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора.

```cpp
template <class T, class U> constexpr bool operator<(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `optional` , `nullopt_t` или `T` .

*right*\
Объект типа `optional` , `nullopt_t` или `T` .

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если список слева от оператора меньше, но не равен списку с правой стороны оператора; в противном случае — значение **`false`** .

## <a name="operatorlt"></a><a name="op_lt_eq"></a> operator&lt;=

Проверяет, меньше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора, или равен ему.

```cpp
template <class T, class U> constexpr bool operator<=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `optional` , `nullopt_t` или `T` .

*right*\
Объект типа `optional` , `nullopt_t` или `T` .

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если список слева от оператора меньше или равен списку с правой стороны оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Эта функция шаблона возвращает `!(right < left)`.

## <a name="operatorgt"></a><a name="op_gt"></a> operator&gt;

Проверяет больше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора.

```cpp
template <class T, class U> constexpr bool operator>(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `optional` , `nullopt_t` или `T` .

*right*\
Объект типа `optional` , `nullopt_t` или `T` .

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если список в левой части оператора больше списка с правой стороны оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Эта функция шаблона возвращает `right < left`.

## <a name="operatorgt"></a><a name="op_gt_eq"></a> operator&gt;=

Проверяет больше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора, или равен ему.

```cpp
template <class T, class U> constexpr bool operator>=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `optional` , `nullopt_t` или `T` .

*right*\
Объект типа `optional` , `nullopt_t` или `T` .

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если `optional` слева от оператора больше или равно объекту `optional` справа от оператора; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

Функция шаблона возвращает `!(left < right)`.
