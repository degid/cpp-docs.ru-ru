---
title: Ошибка компилятора C3229
ms.date: 11/04/2016
f1_keywords:
- C3229
helpviewer_keywords:
- C3229
ms.assetid: f2d90923-aa8b-444f-ab10-1f37dbb864e1
ms.openlocfilehash: cd1b4ec21cc041b611b20892c96de0e1170e7a11
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743332"
---
# <a name="compiler-error-c3229"></a>Ошибка компилятора C3229

"тип": косвенные обращения к параметру универсального типа не допускаются

Нельзя использовать универсальные параметры с `*`, `^`или `&`.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3229.

```cpp
// C3229.cpp
// compile with: /clr /c
generic <class T>
ref class C {
   T^ t;   // C3229
};

// OK
generic <class T>
ref class D {
   T u;
};
```

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3229.

```cpp
// C3229_b.cpp
// compile with: /clr /c
generic <class T>   // OK
ref class Utils {
   static void sort(T elems[], size_t size);   // C3229
   static void sort2(T elems, size_t size);   // OK
};
```
