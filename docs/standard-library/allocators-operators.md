---
title: Операторы &lt;allocator&gt;
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 969c9f8e05a9fafad4d3a1102060e2b3d4d0eb2e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844786"
---
# <a name="ltallocatorsgt-operators"></a>Операторы &lt;allocator&gt;

Это функции операторов глобального шаблона, определенные в &lt; распределительах &gt; . Функции оператора члена класса см. в документации по классу.

[operator!=](#op_neq)\
[operator==](#op_eq_eq)

## <a name="operator"></a><a name="op_neq"></a> operator!=

Проверяет на неравенство между объектами распределителя указанного класса.

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Один из объектов allocator для проверки на неравенство.

*right*\
Один из объектов allocator для проверки на неравенство.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объекты распределителя не равны; значение **`false`** , если объекты распределителя равны.

### <a name="remarks"></a>Примечания

Оператор-шаблон возвращает `!(left == right)`.

## <a name="operator"></a><a name="op_eq_eq"></a> operator==

Проверяет на равенство объекты распределителя указанного класса.

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Один из объектов allocator для проверки на равенство.

*right*\
Один из объектов allocator для проверки на равенство.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объекты распределителя равны; значение **`false`** , если объекты распределителя не равны.

### <a name="remarks"></a>Примечания

Этот оператор шаблона возвращает `left.equals(right)`.

## <a name="see-also"></a>См. также раздел

[\<allocators>](allocators-header.md)
