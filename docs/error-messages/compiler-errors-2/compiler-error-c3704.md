---
title: Ошибка компилятора C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: 11e5792344b6f8fba6183f4ab87e1799db803b46
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757947"
---
# <a name="compiler-error-c3704"></a>Ошибка компилятора C3704

"функция": метод vararg не может порождать события

Предпринята попытка использовать [__event](../../cpp/event.md) в методе vararg. Чтобы устранить эту ошибку, замените вызов `fireEvent(int i, ...)` `fireEvent(int i)` вызовом, как показано в следующем примере кода.

Следующий пример приводит к возникновению ошибки C3704:

```cpp
// C3704.cpp
[ event_source(native) ]
class CEventSrc {
   public:
      __event void fireEvent(int i, ...);   // C3704
      // try the following line instead:
      // __event void fireEvent(int i);
};

int main() {
}
```
