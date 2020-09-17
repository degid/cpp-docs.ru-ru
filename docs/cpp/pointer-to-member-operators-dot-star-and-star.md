---
title: 'Операторы указателей на членов: .» и -&gt;*'
ms.date: 11/04/2016
f1_keywords:
- .*
- ->*
helpviewer_keywords:
- expressions [C++], pointer
- pointer-to-member operators [C++]
- .* operator
- expressions [C++], operators
- ->* operator
ms.assetid: 2632be3f-1c81-4523-b56c-982a92a68688
ms.openlocfilehash: 2100933bf525f0717978528301049085eaecd4f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320340"
---
# <a name="pointer-to-member-operators--and--gt"></a>Операторы указателей на членов: .» и -&gt;*

## <a name="syntax"></a>Синтаксис

```
expression .* expression
expression ->* expression
```

## <a name="remarks"></a>Примечания

Операторы указателей на членов, .» \*и ->, возвращают значение определенного участника класса для объекта, указанного на левой стороне выражения.  Правая часть должна определять член класса.  В следующем примере показано использование этих операторов.

```cpp
// expre_Expressions_with_Pointer_Member_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

class Testpm {
public:
   void m_func1() { cout << "m_func1\n"; }
   int m_num;
};

// Define derived types pmfn and pmd.
// These types are pointers to members m_func1() and
// m_num, respectively.
void (Testpm::*pmfn)() = &Testpm::m_func1;
int Testpm::*pmd = &Testpm::m_num;

int main() {
   Testpm ATestpm;
   Testpm *pTestpm = new Testpm;

// Access the member function
   (ATestpm.*pmfn)();
   (pTestpm->*pmfn)();   // Parentheses required since * binds
                        // less tightly than the function call.

// Access the member data
   ATestpm.*pmd = 1;
   pTestpm->*pmd = 2;

   cout  << ATestpm.*pmd << endl
         << pTestpm->*pmd << endl;
   delete pTestpm;
}
```

## <a name="output"></a>Выходные данные

```Output
m_func1
m_func1
1
2
```

В приведенном выше примере указатель на член, `pmfn`, используется для вызова функции-члена `m_func1`. Другой указатель на член, `pmd`, используется для обращения к члену `m_num`.

Бинарный оператор .* объединяет свой первый операнд, который должен быть объектом типа класса, со своим вторым операндом, который должен иметь тип указателя на член.

Двоичный оператор ->» сочетает в себе свою первую операнду, которая должна быть указателем на объект типа класса, со вторым образом, который должен быть типом указателя на члена.

В выражении с оператором .* первый операнд должен относиться к тому же типу класса, что и указатель на член, заданный во втором операнде (и быть доступным для него), или иметь доступный тип, однозначно производный от этого класса и доступный для него.

В выражении, содержащем > оператора, первая операнд должна быть типа "указатель на тип класса" типа, указанного во второй операнде, или она должна быть типа однозначно производное из этого класса.

## <a name="example"></a>Пример

Рассмотрим следующие классы и фрагмент программы:

```cpp
// expre_Expressions_with_Pointer_Member_Operators2.cpp
// C2440 expected
class BaseClass {
public:
   BaseClass(); // Base class constructor.
   void Func1();
};

// Declare a pointer to member function Func1.
void (BaseClass::*pmfnFunc1)() = &BaseClass::Func1;

class Derived : public BaseClass {
public:
   Derived();  // Derived class constructor.
   void Func2();
};

// Declare a pointer to member function Func2.
void (Derived::*pmfnFunc2)() = &Derived::Func2;

int main() {
   BaseClass ABase;
   Derived ADerived;

   (ABase.*pmfnFunc1)();   // OK: defined for BaseClass.
   (ABase.*pmfnFunc2)();   // Error: cannot use base class to
                           // access pointers to members of
                           // derived classes.

   (ADerived.*pmfnFunc1)();   // OK: Derived is unambiguously
                              // derived from BaseClass.
   (ADerived.*pmfnFunc2)();   // OK: defined for Derived.
}
```

Результатом операторов указателя \* на >является объект или функция типа, указанного в декларации указателя на участника. Таким образом, в предыдущем примере результатом выражения `ADerived.*pmfnFunc1()` является указатель на функцию, которая не возвращает значения (void). Если второй операнд имеет l-значение, то и результатом будет l-значение.

> [!NOTE]
> Если результатом одного из операторов указателя на член является функция, то результат может использоваться только как операнд к оператору вызова функции.

## <a name="see-also"></a>См. также раздел

[Операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
