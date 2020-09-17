---
title: Ошибка компилятора C3918
ms.date: 11/04/2016
f1_keywords:
- C3918
helpviewer_keywords:
- C3918
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
ms.openlocfilehash: cd9c40ef90715e9beca43a114dba475ab29b5e78
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686042"
---
# <a name="compiler-error-c3918"></a>Ошибка компилятора C3918

для использования требуется "member", чтобы быть членом данных

C3918 может возникать по нескольким причинам, связанным с событиями.

## <a name="examples"></a>Примеры

C3918 может возникать, поскольку в текущем контексте требуется член класса. Следующий пример приводит к возникновению ошибки C3918.

```cpp
// C3918.cpp
// compile with: /clr /c
public ref class C {
public:
   System::Object ^ o;
   delegate void Del();

   event Del^ MyEvent {
      void add(Del^ev) {
         if ( MyEvent != nullptr) {}   // C3918
         if ( o != nullptr) {}   // OK
   }
   void remove(Del^){}
   }
};
```

C3918 также вызывается при попытке проверить тривиальное событие на значение null (имя события больше не будет предоставлять прямой доступ к делегату резервного хранилища для события).

Следующий пример приводит к возникновению ошибки C3918.

```cpp
// C3918_2.cpp
// compile with: /clr /c
using namespace System;
public delegate int MyDel(int);

interface struct IEFace {
   event MyDel ^ E;
};

ref struct EventSource : public IEFace {
   virtual event MyDel ^ E;
   void Fire_E(int i) {
      if (E)   // C3918
         E(i);
   }
};
```

C3918 также может возникать, если вы неправильно подписались на событие. Следующий пример приводит к возникновению ошибки C3918.

```cpp
// C3918_3.cpp
// compile with: /clr /c
using namespace System;

public delegate void del();

public ref class A {
public:
   event del^ e {
      void add(del ^handler ) {
         d += handler;
      }

      void remove(del ^handler) {
         d -= handler;
      }

      void raise() {
         d();
      }
   }

   del^ d;
   void f() {}

   A() {
      e = gcnew del(this, &A::f);   // C3918
      // try the following line instead
      // e += gcnew del(this, &A::f);
      e();
   }
};

int main() {
   A a;
}
```
