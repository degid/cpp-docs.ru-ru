---
title: Операторы &lt;scoped_allocator&gt;
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 907772069c192b3ef75c7366e079b1da1dd36f8d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846255"
---
# <a name="ltscoped_allocatorgt-operators"></a>Операторы &lt;scoped_allocator&gt;

[operator!=](#op_neq)\
[operator==](#op_eq_eq)

## <a name="operator"></a><a name="op_neq"></a> operator!=

Сравнивает два объекта `scoped_allocator_adaptor`, чтобы определить их неравенство.

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Параметры

*left*\
Левый объект `scoped_allocator_adaptor`.

*right*\
Правой объект `scoped_allocator_adaptor`.

### <a name="return-value"></a>Возвращаемое значение

`!(left == right)`

## <a name="operator"></a><a name="op_eq_eq"></a> operator==

Сравнивает два объекта `scoped_allocator_adaptor`, чтобы определить, равны ли они.

```cpp
template <class Outer, class... Inner>
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Параметры

*left*\
Левый объект `scoped_allocator_adaptor`.

*right*\
Правой объект `scoped_allocator_adaptor`.

### <a name="return-value"></a>Возвращаемое значение

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>См. также раздел

[<scoped_allocator>](../standard-library/scoped-allocator.md)
