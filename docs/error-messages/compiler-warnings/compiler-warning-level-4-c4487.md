---
title: Предупреждение компилятора (уровень 4) C4487
ms.date: 11/04/2016
f1_keywords:
- C4487
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
ms.openlocfilehash: 33a2a4e36a2c1d3a3900b9f2f8261df7bbce9b00
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214351"
---
# <a name="compiler-warning-level-4-c4487"></a>Предупреждение компилятора (уровень 4) C4487

"derived_class_function": соответствует унаследованному невиртуальному методу "base_class_function", но не помечен явно как "New"

Функция в производном классе имеет ту же сигнатуру, что и Невиртуальная функция базового класса. C4487 напоминает, что функция производного класса не переопределяет функцию базового класса. Чтобы устранить это предупреждение, явно пометьте функцию производного класса как **`new`** .

Дополнительные сведения см. в разделе [New (новый слот в таблице vtable)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4487.

```cpp
// C4487.cpp
// compile with: /W4 /clr
using namespace System;
public ref struct B {
   void f() { Console::WriteLine("in B::f"); }
   void g() { Console::WriteLine("in B::g"); }
};

public ref struct D : B {
   void f() { Console::WriteLine("in D::f"); }   // C4487
   void g() new { Console::WriteLine("in D::g"); }   // OK
};

int main() {
   B ^ a = gcnew D;
   // will call base class functions
   a->f();
   a->g();
}
```
