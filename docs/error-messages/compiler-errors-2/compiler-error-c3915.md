---
title: Ошибка компилятора C3915
ms.date: 11/04/2016
f1_keywords:
- C3915
helpviewer_keywords:
- C3915
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
ms.openlocfilehash: d83a837a24fe36b61d3f0fccae4dbe4e93cd3261
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686055"
---
# <a name="compiler-error-c3915"></a>Ошибка компилятора C3915

"тип" не имеет индексированного свойства по умолчанию (индексатора класса)

У типа нет индексированного свойства по умолчанию.

Для получения дополнительной информации см. [property](../../extensions/property-cpp-component-extensions.md).

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C3915.

```cpp
// C3915.cpp
// compile with: /clr
ref class X {
public:
// uncomment property to resolve this C3915
//   property int default[]
//   {
//      int get(int i)
//      {
//         return 863;
//      }
//   }
};

int main() {
   X^ x = new X;
   System::Console::WriteLine(x[1]);   // C3915
}
```

C3915 также может возникать при попытке использовать индексатор по умолчанию в том же компилируемого объекта, где он был определен с помощью <xref:System.Reflection.DefaultMemberAttribute> .

Следующий пример приводит к возникновению ошибки C3915.

```cpp
// C3915_b.cpp
// compile with: /clr
using namespace System;

[Reflection::DefaultMember("XXX")]
ref struct A {
   property Double XXX[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
};

ref struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
};

int main() {
   A ^ mya = gcnew A();
   Console::WriteLine("{0}", mya[3]);   // C3915

   B ^ myb = gcnew B();
   Console::WriteLine("{0}", myb[3]);   // OK
}
```
