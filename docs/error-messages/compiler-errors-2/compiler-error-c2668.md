---
title: Ошибка компилятора C2668
ms.date: 03/28/2017
f1_keywords:
- C2668
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
ms.openlocfilehash: f59cb33bed15847ed1a7a2dbe99ea030babf3337
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177161"
---
# <a name="compiler-error-c2668"></a>Ошибка компилятора C2668

"функция": неоднозначный вызов перегруженной функции

Не удалось разрешить указанный перегруженный вызов функции. Может потребоваться явное приведение одного или нескольких фактических параметров.

Эту ошибку также можно получить с помощью шаблона. Если в одном и том же классе есть обычная функция-член и шаблонная функция-член с одинаковой сигнатурой, то шаблон должен быть первым. Это ограничение текущей реализации визуального C++элемента.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2668:

```cpp
// C2668.cpp
struct A {};
struct B : A {};
struct X {};
struct D : B, X {};

void func( X, X ){}
void func( A, B ){}
D d;
int main() {
   func( d, d );   // C2668 D has an A, B, and X
   func( (X)d, (X)d );   // OK, uses func( X, X )
}
```

## <a name="example"></a>Пример

Другим способом устранения этой ошибки является [объявление using](../../cpp/using-declaration.md):

```cpp
// C2668b.cpp
// compile with: /EHsc /c
// C2668 expected
#include <iostream>
class TypeA {
public:
   TypeA(int value) {}
};

class TypeB {
   TypeB(int intValue);
   TypeB(double dbValue);
};

class TestCase {
public:
   void AssertEqual(long expected, long actual, std::string
                    conditionExpression = "");
};

class AppTestCase : public TestCase {
public:
   // Uncomment the following line to resolve.
   // using TestCase::AssertEqual;
   void AssertEqual(const TypeA expected, const TypeA actual,
                    std::string conditionExpression = "");
   void AssertEqual(const TypeB expected, const TypeB actual,
                    std::string conditionExpression = "");
};

class MyTestCase : public AppTestCase {
   void TestSomething() {
      int actual = 0;
      AssertEqual(0, actual, "Value");
   }
};
```

## <a name="example"></a>Пример

Эта ошибка также может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio .NET 2003: неоднозначное преобразование при приведении константы 0.

Преобразование при приведении с использованием константы 0 является неоднозначным, так как для int требуется преобразование как в Long, так и в void *. Чтобы устранить эту ошибку, приведите 0 к точному типу параметра функции, для которого она используется, чтобы не выполнять преобразования (этот код будет действительным в Visual Studio .NET 2003 и Visual Studio .NET версии Visual C++).

```cpp
// C2668c.cpp
#include "stdio.h"
void f(long) {
   printf_s("in f(long)\n");
}
void f(void*) {
   printf_s("in f(void*)\n");
}
int main() {
   f((int)0);   // C2668

   // OK
   f((long)0);
   f((void*)0);
}
```

## <a name="example"></a>Пример

Эта ошибка может возникать, если CRT теперь имеет функции float и Double для всех математических функций.

```cpp
// C2668d.cpp
#include <math.h>
int main() {
   int i = 0;
   float f;
   f = cos(i);   // C2668
   f = cos((float)i);   // OK
}
```

## <a name="example"></a>Пример

Эта ошибка может возникать из-за того, что Pow (int, int) был удален из Math.h в CRT.

```cpp
// C2668e.cpp
#include <math.h>
int main() {
   pow(9,9);   // C2668
   pow((double)9,9);   // OK
}
```

## <a name="example"></a>Пример

Этот код успешно выполнен в Visual Studio 2015, но в Visual Studio 2017 и более поздних версий с C2668 не работает. В Visual Studio 2015 компилятор ошибочно интерпретировал инициализацию копии списка так же, как обычную инициализацию копии. Он рассматривал только преобразование конструкторов для разрешения перегрузки.

```cpp
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```
