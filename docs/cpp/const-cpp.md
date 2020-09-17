---
title: const (C++)
ms.date: 11/04/2016
f1_keywords:
- const_cpp
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
ms.openlocfilehash: db79e228f1fabc4b2da0a7778126a1b576a67768
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229042"
---
# <a name="const-c"></a>const (C++)

При изменении объявления данных **`const`** ключевое слово указывает, что объект или переменная не являются изменяемыми.

## <a name="syntax"></a>Синтаксис

```
const declaration ;
member-function const ;
```

## <a name="const-values"></a>Значения-константы

**`const`** Ключевое слово указывает, что значение переменной является константой и сообщает компилятору о том, что программист не сможет его изменить.

```cpp
// constant_values1.cpp
int main() {
   const int i = 5;
   i = 10;   // C3892
   i++;   // C2105
}
```

В C++ **`const`** вместо директивы препроцессора [#define](../preprocessor/hash-define-directive-c-cpp.md) можно использовать ключевое слово, чтобы определить постоянные значения. Значения, определенные с помощью, **`const`** подчиняются проверке типа и могут использоваться вместо константных выражений. В C++ можно указать размер массива с помощью **`const`** переменной следующим образом:

```cpp
// constant_values2.cpp
// compile with: /c
const int maxarray = 255;
char store_char[maxarray];  // allowed in C++; not allowed in C
```

В языке C константные значения по умолчанию имеют внешнюю компоновку, поэтому они могут использоваться только в файлах исходного кода. В языке C++ константные значения по умолчанию имеют внутреннюю компоновку, которая позволяет использовать их в файлах заголовков.

**`const`** Ключевое слово также можно использовать в объявлениях указателей.

```cpp
// constant_values3.cpp
int main() {
   char *mybuf = 0, *yourbuf;
   char *const aptr = mybuf;
   *aptr = 'a';   // OK
   aptr = yourbuf;   // C3892
}
```

Указатель на переменную, объявленную как, **`const`** может быть назначен только указателю, который также объявлен как **`const`** .

```cpp
// constant_values4.cpp
#include <stdio.h>
int main() {
   const char *mybuf = "test";
   char *yourbuf = "test2";
   printf_s("%s\n", mybuf);

   const char *bptr = mybuf;   // Pointer to constant data
   printf_s("%s\n", bptr);

   // *bptr = 'a';   // Error
}
```

Указатели на данные-константы можно использовать в качестве параметров функций, чтобы функция не могла изменять параметр, переданный посредством указателя.

Для объектов, объявленных как **`const`** , можно вызывать только константные функции членов. Это гарантирует, что константный объект не будет изменен.

```cpp
birthday.getMonth();    // Okay
birthday.setMonth( 4 ); // Error
```

Для объектов, не объявленных как константы, можно вызывать как константные, так и неконстантные функции-члены. Можно также перегружать функцию-член с помощью **`const`** ключевого слова; это позволяет вызывать другую версию функции для постоянных и неконстантных объектов.

Нельзя объявлять конструкторы или деструкторы с **`const`** ключевым словом.

## <a name="const-member-functions"></a>Функции-члены-константы

Объявление функции-члена с помощью **`const`** ключевого слова указывает, что функция является функцией "только для чтения", которая не изменяет объект, для которого она вызывается. Функция-член константы не может изменять какие-либо нестатические элементы данных или вызывать функции-члены, не являющиеся константами. Чтобы объявить функцию-член константы, поместите **`const`** ключевое слово после закрывающей скобки списка аргументов. **`const`** Ключевое слово требуется как в объявлении, так и в определении.

```cpp
// constant_member_function.cpp
class Date
{
public:
   Date( int mn, int dy, int yr );
   int getMonth() const;     // A read-only function
   void setMonth( int mn );   // A write function; can't be const
private:
   int month;
};

int Date::getMonth() const
{
   return month;        // Doesn't modify anything
}
void Date::setMonth( int mn )
{
   month = mn;          // Modifies data member
}
int main()
{
   Date MyDate( 7, 4, 1998 );
   const Date BirthDate( 1, 18, 1953 );
   MyDate.setMonth( 4 );    // Okay
   BirthDate.getMonth();    // Okay
   BirthDate.setMonth( 4 ); // C2662 Error
}
```

## <a name="c-and-c-const-differences"></a>Различия констант C и C++

При объявлении переменной, как **`const`** в файле исходного кода на языке C, это можно сделать следующим образом:

```cpp
const int i = 2;
```

Затем эту переменную можно использовать в другом модуле следующим образом:

```cpp
extern const int i;
```

Но чтобы получить такое же поведение в C++, необходимо объявить **`const`** переменную как:

```cpp
extern const int i = 2;
```

Если вы хотите объявить **`extern`** переменную в файле исходного кода C++ для использования в файле исходного кода на языке C, используйте:

```cpp
extern "C" const int x=10;
```

для предотвращения изменения имени компилятором C++.

## <a name="remarks"></a>Примечания

При использовании списка параметров функции-члена **`const`** ключевое слово указывает, что функция не изменяет объект, для которого она вызывается.

Дополнительные сведения о **`const`** см. в следующих разделах:

- [константные и переменные указатели](../cpp/const-and-volatile-pointers.md)

- [Квалификаторы типов (Справочник по языку C)](../c-language/type-qualifiers.md)

- [volatile](../cpp/volatile-cpp.md)

- [#define](../preprocessor/hash-define-directive-c-cpp.md)

## <a name="see-also"></a>См. также статью

[Ключевые слова](../cpp/keywords-cpp.md)
