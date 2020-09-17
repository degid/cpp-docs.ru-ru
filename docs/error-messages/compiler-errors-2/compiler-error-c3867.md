---
title: Ошибка компилятора C3867
ms.date: 11/04/2016
f1_keywords:
- C3867
helpviewer_keywords:
- C3867
ms.assetid: bc5de03f-e01a-4407-88c3-2c63f0016a1e
ms.openlocfilehash: 40825bf92a892917f815c955ee4ba1fb6fa906c3
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686422"
---
# <a name="compiler-error-c3867"></a>Ошибка компилятора C3867

"func": в вызове функции отсутствует список аргументов; Используйте "&Func", чтобы создать указатель на член

Вы попытались получить адрес функции-члена без указания полного имени класса и оператора взятия адреса функции-члена.

Эта ошибка также может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio 2005: расширенное соответствие указателя на член. Код, скомпилированный до Visual Studio 2005, теперь создаст C3867.

## <a name="examples"></a>Примеры

Ошибка C3867 может быть вызвана компилятором с неправильно предложенным разрешением. По возможности используйте наиболее производный класс.

В следующем примере показано возникновение ошибки C3867 и приводятся сведения по ее устранению.

```cpp
// C3867_1.cpp
// compile with: /c
struct Base {
protected:
   void Test() {}
};

class Derived : public Base {
   virtual void Bar();
};

void Derived::Bar() {
   void (Base::*p1)() = Test;   // C3867
   &Derived::Test;   // OK
}
```

В следующем примере показано возникновение ошибки C3867 и приводятся сведения по ее устранению.

```cpp
// C3867_2.cpp
#include<stdio.h>

struct S {
   char *func() {
      return "message";
   }
};

class X {
public:
   void f() {}
};

int main() {
   X::f;   // C3867

   // OK
   X * myX = new X;
   myX->f();

   S s;
   printf_s("test %s", s.func);   // C3867
   printf_s("test %s", s.func());   // OK
}
```

В следующем примере показано возникновение ошибки C3867 и приводятся сведения по ее устранению.

```cpp
// C3867_3.cpp
class X {
public:
   void mf(){}
};

int main() {
   void (X::*pmf)() = X::mf;   // C3867

   // try the following line instead
   void (X::*pmf2)() = &X::mf;
}
```

Следующий пример приводит к возникновению ошибки C3867:

```cpp
// C3867_4.cpp
// compile with: /c
class A {
public:
   void f(int) {}

   typedef void (A::*TAmtd)(int);

   struct B {
      TAmtd p;
   };

   void g() {
      B b1;
      b1.p = f;   // C3867
   }
};
```

Следующий пример приводит к возникновению ошибки C3867:

```cpp
// C3867_5.cpp
// compile with: /EHsc
#include <iostream>

class Testpm {
public:
   void m_func1() {
      std::cout << m_num << "\tm_func1\n";
    }

   int m_num;
   typedef void (Testpm::*pmfn1)();
   void func(Testpm* p);
};

void Testpm::func(Testpm* p) {
   pmfn1 s = m_func1;   // C3867
   pmfn1 s2 = &Testpm::m_func1;   // OK
   (p->*s2)();
}

int main() {
   Testpm *pTestpm = new Testpm;
   pTestpm->m_num = 10;

   pTestpm->func(pTestpm);
}
```
