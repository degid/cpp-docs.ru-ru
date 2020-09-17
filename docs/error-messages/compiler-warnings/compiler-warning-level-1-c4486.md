---
title: Предупреждение компилятора (уровень 1) C4486
ms.date: 11/04/2016
f1_keywords:
- C4486
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
ms.openlocfilehash: 893dd9241f83895d253fc8b5513f56cab272e31c
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684681"
---
# <a name="compiler-warning-level-1-c4486"></a>Предупреждение компилятора (уровень 1) C4486

"функция": частный виртуальный метод класса ссылки или класса значения должен быть помечен как "Sealed"

Поскольку закрытая виртуальная функция-член управляемого класса или структуры не может быть доступна или переопределена, она должна быть помечена как [sealed](../../extensions/sealed-cpp-component-extensions.md).

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C4486.

```cpp
// C4486.cpp
// compile with: /clr /c /W1
ref class B {
private:
   virtual void f() {}   // C4486
   virtual void f1() sealed {}   // OK
};
```

В следующем примере показано одно возможное использование закрытой запечатанной виртуальной функции.

```cpp
// C4486_b.cpp
// compile with: /clr /c
ref class B {};

ref class D : B {};

interface class I {
   B^ mf();
};

ref class E : I {
private:
   virtual B^ g() sealed = I::mf {
      return gcnew B;
   }

public:
   virtual D^ mf() {
      return gcnew D;
   }
};
```
