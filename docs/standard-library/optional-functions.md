---
title: '&lt;необязательных функций&gt;'
ms.date: 11/04/2016
f1_keywords:
- optional/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: ebb7ccfb8a39bf1f45c7003d7c38e503ab20c89b
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425295"
---
# <a name="ltoptionalgt-functions"></a>&lt;необязательных функций&gt;

## <a name="make_optional"></a>make_optional

Делает объект необязательным.

```cpp
template <class T>
    constexpr optional<see below> make_optional(T&&);
template <class T, class... Args>
    constexpr optional<T> make_optional(Args&&... args);
template <class T, class U, class... Args>
    constexpr optional<T> make_optional(initializer_list<U> il, Args&&... args);
```

## <a name="nullopt"></a>нуллопт

```cpp
inline constexpr nullopt_t nullopt(unspecified );
```

## <a name="swap"></a>позиции

```cpp
template <class T>
    void swap(optional<T>&, optional<T>&) noexcept(see below );
```
