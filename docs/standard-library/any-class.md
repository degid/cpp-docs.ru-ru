---
title: любой класс
ms.date: 04/04/2019
f1_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
helpviewer_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
ms.openlocfilehash: defec0f6ab8f59219afddcefc67ea93435347978
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844747"
---
# <a name="any-class"></a>любой класс

Хранит экземпляр любого типа, удовлетворяющего требованиям конструктора, или не имеет значения, которое называется состоянием класса любой объект.

Хранимый экземпляр называется вложенным значением. Два состояния одинаковы, если оба имеют значение, либо оба имеют значение, а содержащиеся в них значения совпадают.

## <a name="syntax"></a>Синтаксис

```cpp
class any
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[всеми](#any)|Создает объект типа `any`.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[emplace](#emplace)|Задает любое значение.|
|[has_value](#has_value)|Возвращает **`true`** , если any имеет значение.|
|[reset](#reset)|Сбрасывает объект.|
|[swap](#swap)|Меняет местами два объекта.|
|[type](#type)|Возвращает любой тип.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator=](#op_eq)|Заменяет объект на копию другого объекта.|

## <a name="any"></a><a name="any"></a> всеми

Создает объект типа `any`. Также включает деструктор.

```cpp
constexpr any() noexcept;
any(const any& other);
any(any&& other) noexcept;
template <class T>
    any(T&& value);
template <class T, class... Args>
    explicit any(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    explicit any(in_place_type_t<T>, initializer_list<U>, Args&&...);

~any();
```

## <a name="emplace"></a><a name="emplace"></a> emplace

Задает любое значение.

```cpp
template <class T, class... Args>
    decay_t<T>& emplace(Args&& ...);
template <class T, class U, class... Args>
    decay_t<T>& emplace(initializer_list<U>, Args&&...);
```

## <a name="has_value"></a><a name="has_value"></a> has_value

Возвращает **`true`** , если any имеет значение.

```cpp
bool has_value() const noexcept;
```

## <a name="operator"></a><a name="op_eq"></a> operator=

Заменяет объект на копию другого объекта.

```cpp
any& operator=(const any& right);
any& operator=(any&& right) noexcept;
template <class T>
    any& operator=(T&& right);
```

### <a name="parameters"></a>Параметры

*right*\
Объект, который копируется в Any.

## <a name="reset"></a><a name="reset"></a> reset

Сбрасывает объект.

```cpp
void reset() noexcept;
```

## <a name="swap"></a><a name="swap"></a> swap

Меняет местами два объекта.

```cpp
void swap(any& rhs) noexcept;
```

## <a name="type"></a>Тип <a name="type"></a>

Возвращает любой тип.

```cpp
const type_info& type() const noexcept;
```
