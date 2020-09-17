---
title: Ошибка компилятора C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: d8cfcae544d0948c21e093ba6457159b0214a583
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685623"
---
# <a name="compiler-error-c3764"></a>Ошибка компилятора C3764

"override_function": невозможно переопределить метод базового класса "base_class_function"

Компилятор обнаружил неправильно сформированное переопределение. Например, функция базового класса не была **`virtual`** . Дополнительные сведения см. в разделе [override](../../extensions/override-cpp-component-extensions.md).

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C3764.

```cpp
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

C3764 также может возникать, когда метод базового класса явно и имеет имя reпереопределен. Следующий пример приводит к возникновению ошибки C3764.

```cpp
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```
