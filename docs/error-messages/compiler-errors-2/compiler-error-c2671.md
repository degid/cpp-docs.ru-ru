---
title: Ошибка компилятора C2671
ms.date: 11/04/2016
f1_keywords:
- C2671
helpviewer_keywords:
- C2671
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
ms.openlocfilehash: 795c3413699a2af0ae587980a658baa2bbcdd887
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216132"
---
# <a name="compiler-error-c2671"></a>Ошибка компилятора C2671

"функция": статические функции члена не имеют указателей "this"

**`static`** Функция-член попыталась получить доступ **`this`** .

Следующий пример приводит к возникновению ошибки C2671:

```cpp
// C2671.cpp
struct S {
   static S* const func() { return this; }  // C2671
};
```
