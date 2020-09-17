---
title: using - объявление
ms.date: 11/04/2016
helpviewer_keywords:
- using declaration
- declarations [C++], using-declaration
- namespaces [C++], unqualified names in
- using keyword [C++]
ms.assetid: 4184e2b1-3adc-408e-b5f3-0b3f8b554723
ms.openlocfilehash: 3aa0c7c4615aaf5eae9f4eae534e52167bf79ff0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227027"
---
# <a name="using-declaration"></a>using - объявление

**`using`** Объявление вводит имя в декларативную область, в которой отображается объявление using.

## <a name="syntax"></a>Синтаксис

```
using [typename] nested-name-specifier unqualified-id ;
using declarator-list ;
```

### <a name="parameters"></a>Параметры

*спецификатор вложенного имени* Последовательность пространств имен, классов или перечислений, а также операторы разрешения области (::), заканчивающиеся оператором разрешения области. Чтобы ввести имя из глобального пространства имен, можно использовать один оператор разрешения области. Ключевое слово **`typename`** является необязательным и может использоваться для разрешения зависимых имен при их внедрении в шаблон класса из базового класса.

*неполный идентификатор* Неполное выражение идентификатора, которое может представлять собой идентификатор, имя перегруженного оператора, определяемый пользователем литеральный оператор или имя функции преобразования, Имя деструктора класса или имя шаблона и список аргументов.

*декларатор-список* Разделенный запятыми список **`typename`** *описателей с* *квалификаторами неполного* имени ([]) с разделителем-запятой, за которым следует, по желанию, многоточие.

## <a name="remarks"></a>Примечания

Объявление using вводит неполное имя в качестве синонима сущности, объявленной в другой части. Он позволяет использовать одно имя из определенного пространства имен без явного уточнения в области объявления, в которой оно отображается. Это отличается от [директивы using](../cpp/namespaces-cpp.md#using_directives), которая позволяет использовать *все* имена в пространстве имен без уточнения. **`using`** Ключевое слово также используется для [псевдонимов типов](../cpp/aliases-and-typedefs-cpp.md).

## <a name="example"></a>Пример

Объявление using может использоваться в определении класса.

```cpp
// using_declaration1.cpp
#include <stdio.h>
class B {
public:
   void f(char) {
      printf_s("In B::f()\n");
   }

   void g(char) {
      printf_s("In B::g()\n");
   }
};

class D : B {
public:
   using B::f;    // B::f(char) is now visible as D::f(char)
   using B::g;    // B::g(char) is now visible as D::g(char)
   void f(int) {
      printf_s("In D::f()\n");
      f('c');     // Invokes B::f(char) instead of recursing
   }

   void g(int) {
      printf_s("In D::g()\n");
      g('c');     // Invokes B::g(char) instead of recursing
   }
};

int main() {
   D myD;
   myD.f(1);
   myD.g('a');
}
```

```Output
In D::f()
In B::f()
In B::g()
```

## <a name="example"></a>Пример

Если объявление using объявляет член, оно должно ссылаться на член базового класса.

```cpp
// using_declaration2.cpp
#include <stdio.h>

class B {
public:
   void f(char) {
      printf_s("In B::f()\n");
   }

   void g(char) {
      printf_s("In B::g()\n");
   }
};

class C {
public:
   int g();
};

class D2 : public B {
public:
   using B::f;   // ok: B is a base of D2
   // using C::g;   // error: C isn't a base of D2
};

int main() {
   D2 MyD2;
   MyD2.f('a');
}
```

```Output
In B::f()
```

## <a name="example"></a>Пример

На члены, объявленные с помощью объявления using, можно ссылаться с помощью явной квалификации. Префикс `::` указывает на глобальное пространство имен.

```cpp
// using_declaration3.cpp
#include <stdio.h>

void f() {
   printf_s("In f\n");
}

namespace A {
   void g() {
      printf_s("In A::g\n");
   }
}

namespace X {
   using ::f;   // global f is also visible as X::f
   using A::g;   // A's g is now visible as X::g
}

void h() {
   printf_s("In h\n");
   X::f();   // calls ::f
   X::g();   // calls A::g
}

int main() {
   h();
}
```

```Output
In h
In f
In A::g
```

## <a name="example"></a>Пример

Если используется объявление using, то созданный им синоним указывает только на определения, которые являются действительными в точке его создания. Определения, добавляемые в пространство имен после объявления using, не являются допустимыми синонимами.

Имя, определенное **`using`** объявлением, является псевдонимом для его исходного имени. Оно не влияет на тип, компоновку и другие атрибуты исходного объявления.

```cpp
// post_declaration_namespace_additions.cpp
// compile with: /c
namespace A {
   void f(int) {}
}

using A::f;   // f is a synonym for A::f(int) only

namespace A {
   void f(char) {}
}

void f() {
   f('a');   // refers to A::f(int), even though A::f(char) exists
}

void b() {
   using A::f;   // refers to A::f(int) AND A::f(char)
   f('a');   // calls A::f(char);
}
```

## <a name="example"></a>Пример

Говоря о функциях в пространствах имен, если в области объявления задан набор локальных объявлений и объявлений using для одного имени, то все они должны указывать на одну и ту же сущность, либо же все они должны указывать на функции.

```cpp
// functions_in_namespaces1.cpp
// C2874 expected
namespace B {
    int i;
    void f(int);
    void f(double);
}

void g() {
    int i;
    using B::i;   // error: i declared twice
    void f(char);
    using B::f;   // ok: each f is a function
}
```

В приведенном выше примере второй оператор `using B::i` объявляет вторую переменную `int i` в функции `g()`. Оператор `using B::f` не конфликтует с функцией `f(char)`, поскольку имена функций, вводимых в код при помощи `B::f`, имеют разные типы параметров.

## <a name="example"></a>Пример

Локальное объявление функции не может иметь такое же имя и тип, что и функция, введенная в код объявлением using. Пример:

```cpp
// functions_in_namespaces2.cpp
// C2668 expected
namespace B {
    void f(int);
    void f(double);
}

namespace C {
    void f(int);
    void f(double);
    void f(char);
}

void h() {
    using B::f;          // introduces B::f(int) and B::f(double)
    using C::f;          // C::f(int), C::f(double), and C::f(char)
    f('h');              // calls C::f(char)
    f(1);                // C2668 ambiguous: B::f(int) or C::f(int)?
    void f(int);         // C2883 conflicts with B::f(int) and C::f(int)
}
```

## <a name="example"></a>Пример

Говоря о наследовании, когда объявление using вводит имя из базового класса в область видимости производного класса, то функции-члены из производного класса переопределяют виртуальные функции-члены из базового класса, имеющие такое же имя и типы аргументов.

```cpp
// using_declaration_inheritance1.cpp
#include <stdio.h>
struct B {
   virtual void f(int) {
      printf_s("In B::f(int)\n");
   }

   virtual void f(char) {
      printf_s("In B::f(char)\n");
   }

   void g(int) {
      printf_s("In B::g\n");
   }

   void h(int);
};

struct D : B {
   using B::f;
   void f(int) {   // ok: D::f(int) overrides B::f(int)
      printf_s("In D::f(int)\n");
   }

   using B::g;
   void g(char) {   // ok: there is no B::g(char)
      printf_s("In D::g(char)\n");
   }

   using B::h;
   void h(int) {}   // Note: D::h(int) hides non-virtual B::h(int)
};

void f(D* pd) {
   pd->f(1);     // calls D::f(int)
   pd->f('a');   // calls B::f(char)
   pd->g(1);     // calls B::g(int)
   pd->g('a');   // calls D::g(char)
}

int main() {
   D * myd = new D();
   f(myd);
}
```

```Output
In D::f(int)
In B::f(char)
In B::g
In D::g(char)
```

## <a name="example"></a>Пример

Все экземпляры имени, упоминаемого в объявлении using, должны быть доступны. В частности, если объявление using используется в производном классе для доступа к базовому классу, то имя члена должно быть доступно. Если имя относится к перегруженной функции-члену, то все функции с этим именем должны быть доступны.

Дополнительные сведения о специальных возможностях членов см. в разделе [Управление доступом к](../cpp/member-access-control-cpp.md)членам.

```cpp
// using_declaration_inheritance2.cpp
// C2876 expected
class A {
private:
   void f(char);
public:
   void f(int);
protected:
   void g();
};

class B : public A {
   using A::f;   // C2876: A::f(char) is inaccessible
public:
   using A::g;   // B::g is a public synonym for A::g
};
```

## <a name="see-also"></a>См. также статью

[Пространства имен](../cpp/namespaces-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
