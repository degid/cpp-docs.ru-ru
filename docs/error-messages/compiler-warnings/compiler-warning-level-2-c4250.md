---
title: Предупреждение компилятора (уровень 2) C4250
ms.date: 11/04/2016
f1_keywords:
- C4250
helpviewer_keywords:
- C4250
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
ms.openlocfilehash: 10064784e1124ac365475f00b3577d22f5e7f3f1
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686526"
---
# <a name="compiler-warning-level-2-c4250"></a>Предупреждение компилятора (уровень 2) C4250

"Class1": наследует "class2:: member" через превосходство

Два или более члена имеют одно и то же имя. Объект в `class2` является унаследованным, так как является базовым классом для других классов, содержащих этот элемент.

Чтобы отключить C4250, используйте директиву pragma [warning](../../preprocessor/warning.md) .

Поскольку виртуальный базовый класс является общим для нескольких производных классов, имя в производном классе образует имя в базовом классе. Например, в следующей иерархии классов есть два определения Func, унаследованные в ромбе: экземпляр vbc:: Func () через слабый класс, а главный элемент:: Func () — через главный класс. Неквалифицированный вызов функции func () через объект класса-ромба всегда вызывает классный экземпляр:: Func ().  Если слабый класс должен ввести экземпляр Func (), ни одно из определений не будет основным, а вызов будет помечен как неоднозначный.

## <a name="examples"></a>Примеры

```cpp
// C4250.cpp
// compile with: /c /W2
#include <stdio.h>
struct vbc {
   virtual void func() { printf("vbc::func\n"); }
};

struct weak : public virtual vbc {};

struct dominant : public virtual vbc {
   void func() { printf("dominant::func\n"); }
};

struct diamond : public weak, public dominant {};

int main() {
   diamond d;
   d.func();   // C4250
}
```

Следующий пример приводит к возникновению ошибки C4250.

```cpp
// C4250_b.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;
class A {
public:
   virtual operator int () {
      return 2;
   }
};

class B : virtual public A {
public:
   virtual operator int () {
      return 3;
   }
};

class C : virtual public A {};

class E : public B, public C {};   // C4250

int main() {
   E eObject;
   cout << eObject.operator int() << endl;
}
```

В этом примере показана более сложная ситуация. Следующий пример приводит к возникновению ошибки C4250.

```cpp
// C4250_c.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;

class V {
public:
   virtual int f() {
      return 1024;
   }
};

class B : virtual public V {
public:
   int b() {
      return f(); // B::b() calls V::f()
   }
};

class M : virtual public V {
public:
   int f() {
      return 7;
   }
};

// because of dominance, f() is M::f() inside D,
// changing the meaning of B::b's f() call inside a D
class D : public B, public M {};   // C4250

int main() {
   D d;
   cout << "value is: " << d.b();   // invokes M::f()
}
```
