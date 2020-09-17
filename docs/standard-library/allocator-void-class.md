---
title: Класс allocator&lt;void&gt;
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: b6ca3f8b994756a21d85860fd8aff429ee38e58b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87204935"
---
# <a name="allocatorltvoidgt-class"></a>Класс allocator&lt;void&gt;

Специализация распределителя шаблонов класса для типа **`void`** , определяющая типы, имеющие смысл в этом контексте.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```

## <a name="remarks"></a>Примечания

Класс явно специализирует [распределителя](allocator-class.md) шаблонов классов для типа **`void`** . Его конструкторы и оператор присваивания ведут себя так же, как и для шаблона класса, но он определяет только следующие типы:

- [const_pointer](allocator-class.md#const_pointer);

- [pointer](allocator-class.md#pointer).

- [value_type](allocator-class.md#value_type).

- [Повторная привязка](allocator-class.md#rebind), шаблон вложенного класса.
