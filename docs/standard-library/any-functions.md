---
title: '&lt;функции&gt;'
ms.date: 04/04/2019
f1_keywords:
- any/std::any_cast
- any/std::make_any
- any/std::swap
ms.openlocfilehash: bb5f8b4411477cfcd33613ee0395227dced784f6
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79427311"
---
# <a name="ltanygt-functions"></a>&lt;функции&gt;

## <a name="any_cast"></a>any_cast

Делает объект в любом объекте.

```cpp
template<class T>
    T any_cast(const any& operand);
template<class T>
    T any_cast(any& operand);
template<class T>
    T any_cast(any&& operand);
template<class T>
    const T* any_cast(const any* operand) noexcept;
template<class T>
    T* any_cast(any* operand) noexcept;
```

## <a name="make_any"></a>make_any

Принимает значения и создает объект.

```cpp
template <class T, class... Args>
    any make_any(Args&& ...args);
template <class T, class U, class... Args>
    any make_any(initializer_list<U> il, Args&& ...args);
```

## <a name="swap"></a>позиции

Меняет местами элементы двух объектов.

```cpp
void swap(any& left, any& right) noexcept;
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `any`.

*right*\
Объект типа `any`.
