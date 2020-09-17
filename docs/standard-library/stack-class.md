---
title: Класс stack
ms.date: 11/04/2016
f1_keywords:
- stack/std::stack::container_type
- stack/std::stack::size_type
- stack/std::stack::value_type
- stack/std::stack::empty
- stack/std::stack::pop
- stack/std::stack::push
- stack/std::stack::size
- stack/std::stack::top
helpviewer_keywords:
- std::stack [C++], container_type
- std::stack [C++], size_type
- std::stack [C++], value_type
- std::stack [C++], empty
- std::stack [C++], pop
- std::stack [C++], push
- std::stack [C++], size
- std::stack [C++], top
ms.assetid: 02151c1e-eab0-41b8-be94-a839ead78ecf
ms.openlocfilehash: f1d44a4242542ac6856fd7208fe423c43ae79997
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844305"
---
# <a name="stack-class"></a>Класс stack

Класс адаптера контейнера шаблона, который предоставляет ограничение функциональности, ограничивая доступ к элементу, который был последним добавлен в некоторый тип базового контейнера. Класс стека используется в том случае, когда важно пояснить, что в контейнере выполняются только операции стека.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type, class Container= deque <Type>>
class stack
```

### <a name="parameters"></a>Параметры

*Type*\
Тип данных элемента для сохранения в стеке.

*Container*\
Тип базового контейнера, используемый для реализации стека. Значение по умолчанию — класс `deque` *\<Type>* .

## <a name="remarks"></a>Примечания

Элементы класса, `Type` оговоренные в первом параметре шаблона объекта Stack, являются синонимами [value_type](#value_type) и должны соответствовать типу элемента в базовом классе контейнера, `Container` указанном вторым параметром-шаблоном. Объект `Type` должен быть назначаемым, чтобы можно было скопировать объекты этого типа и присвоить значения переменным этого типа.

Подходящие базовые классы контейнеров для Stack включают [deque](../standard-library/deque-class.md), [класс List](../standard-library/list-class.md)и [класс Vector](../standard-library/vector-class.md), а также любой другой контейнер последовательности, который поддерживает операции `back` , `push_back` и `pop_back` . Класс базового контейнера инкапсулирован в адаптер контейнера, который предоставляет только ограниченный набор функций-членов контейнера последовательностей в виде открытого интерфейса.

Объекты стека сравнимы по равенству только в том случае, если элементы класса `Type` сравнимы по равенству и меньше, чем сравнимы, только если элементы класса `Type` менее сравнимы.

- Класс стека поддерживает структуру данных «последним поступил — первым обслужен» (LIFO). Хороший аналог такого подхода — стопка тарелок. Элементы (тарелки) можно вставлять, проверять или удалять только из верхней части стека, которая является последним элементом в конце базового контейнера. Ограничение на доступ только к верхнему элементу является причиной использования класса стека.

- [Класс queue](../standard-library/queue-class.md) поддерживает структуру данных "первым поступил — первым обслужен" (FIFO). Хороший аналог такого подхода — очередь из людей к банковскому служащему. Элементы (люди) можно добавлять в конец очереди и удалять из начала очереди. Проверять можно как начало, так и конец очереди. Ограничение на доступ только к переднему и заднему элементам в таком подходе является причиной использования класса очереди.

- [Класс priority_queue](../standard-library/priority-queue-class.md) упорядочивает элементы, чтобы наибольший элемент всегда находился сверху. Он поддерживает вставку элемента, а также проверку и удаление верхнего элемента. Хороший аналог такого подхода — очередь из людей, упорядоченная по возрасту, росту или любому другому критерию.

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[ячейку](#stack)|Создает `stack`, который является пустым или копией объекта базового контейнера.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[container_type](#container_type)|Тип, предоставляющий базовый контейнер для принятия `stack`.|
|[size_type](#size_type)|Целочисленный Typedef без знака, который может представлять число элементов в `stack`.|
|[value_type](#value_type)|Тип, представляющий тип объекта, который хранится в виде элемента в `stack`.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[empty](#empty)|Проверяет, является ли `stack` пустым.|
|[pор](#pop)|Удаляет элемент из верхней части `stack`.|
|[push](#push)|Добавляет элемент в верхнюю часть `stack`.|
|[size](#size)|Возвращает количество элементов в контейнере `stack`.|
|[В начало](#top)|Возвращает ссылку на элемент в верхней части `stack`.|

## <a name="container_type"></a><a name="container_type"></a> container_type

Тип, предоставляющий базовый контейнер для изменения.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Container`. Все три класса контейнеров последовательности стандартной библиотеки C++ (класс vector, класс list и класс по умолчанию deque) соответствуют требованиям для использования в качестве базового контейнера для объекта стека. Также можно использовать пользовательские типы, удовлетворяющие таким требованиям.

Дополнительные сведения о `Container` см. в подразделе "Примечания" раздела [Класс stack](../standard-library/stack-class.md).

### <a name="example"></a>Пример

См. пример объявления и использования `container_type` в разделе [stack::stack](#stack).

## <a name="empty"></a><a name="empty"></a> empty

Проверяет, пуст ли стек.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если стек пуст; **`false`** значение, если стек не пуст.

### <a name="example"></a>Пример

```cpp
// stack_empty.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   // Declares stacks with default deque base container
   stack <int> s1, s2;

   s1.push( 1 );

   if ( s1.empty( ) )
      cout << "The stack s1 is empty." << endl;
   else
      cout << "The stack s1 is not empty." << endl;

   if ( s2.empty( ) )
      cout << "The stack s2 is empty." << endl;
   else
      cout << "The stack s2 is not empty." << endl;
}
```

```Output
The stack s1 is not empty.
The stack s2 is empty.
```

## <a name="pop"></a><a name="pop"></a> pор

Удаляет элемент из верхней части стека.

```cpp
void pop();
```

### <a name="remarks"></a>Примечания

Для применения функции-члена стек должен быть непустым. Начало (верх) стека — это положение, занимаемое последним добавленным элементом, которое является последним элементом в конце контейнера.

### <a name="example"></a>Пример

```cpp
// stack_pop.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   stack <int> s1, s2;

   s1.push( 10 );
   s1.push( 20 );
   s1.push( 30 );

   stack <int>::size_type i;
   i = s1.size( );
   cout << "The stack length is " << i << "." << endl;

   i = s1.top( );
   cout << "The element at the top of the stack is "
        << i << "." << endl;

   s1.pop( );

   i = s1.size( );
   cout << "After a pop, the stack length is "
        << i << "." << endl;

   i = s1.top( );
   cout << "After a pop, the element at the top of the stack is "
        << i << "." << endl;
}
```

```Output
The stack length is 3.
The element at the top of the stack is 30.
After a pop, the stack length is 2.
After a pop, the element at the top of the stack is 20.
```

## <a name="push"></a><a name="push"></a> push

Добавляет элемент в верхнюю часть стека.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Параметры

*val*\
Элемент, добавленный в верх стека.

### <a name="remarks"></a>Примечания

Начало (верх) стека — это положение, занимаемое последним добавленным элементом, которое является последним элементом в конце контейнера.

### <a name="example"></a>Пример

```cpp
// stack_push.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   stack <int> s1;

   s1.push( 10 );
   s1.push( 20 );
   s1.push( 30 );

   stack <int>::size_type i;
   i = s1.size( );
   cout << "The stack length is " << i << "." << endl;

   i = s1.top( );
   cout << "The element at the top of the stack is "
        << i << "." << endl;
}
```

```Output
The stack length is 3.
The element at the top of the stack is 30.
```

## <a name="size"></a><a name="size"></a> size

Возвращает количество элементов в стеке.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая длина стека.

### <a name="example"></a>Пример

```cpp
// stack_size.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   stack <int> s1, s2;
   stack <int>::size_type i;

   s1.push( 1 );
   i = s1.size( );
   cout << "The stack length is " << i << "." << endl;

   s1.push( 2 );
   i = s1.size( );
   cout << "The stack length is now " << i << "." << endl;
}
```

```Output
The stack length is 1.
The stack length is now 2.
```

## <a name="size_type"></a><a name="size_type"></a> size_type

Целочисленный тип без знака, который может представлять количество элементов в стеке.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для `size_type` базового контейнера, адаптированного стеком.

### <a name="example"></a>Пример

См. пример объявления и использования `size_type` в разделе [size](#size).

## <a name="stack"></a><a name="stack"></a> ячейку

Создает стек, который является пустым или представляет собой копию класса базового контейнера.

```cpp
stack();

explicit stack(const container_type& right);
```

### <a name="parameters"></a>Параметры

*right*\
Контейнер, копией которого должен стать создаваемый стек.

### <a name="example"></a>Пример

```cpp
// stack_stack.cpp
// compile with: /EHsc
#include <stack>
#include <vector>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stack with default deque base container
   stack <char> dsc1;

   //Explicitly declares a stack with deque base container
   stack <char, deque<char> > dsc2;

   // Declares a stack with vector base containers
   stack <int, vector<int> > vsi1;

   // Declares a stack with list base container
   stack <int, list<int> > lsi;

   // The second member function copies elements from a container
   vector<int> v1;
   v1.push_back( 1 );
   stack <int, vector<int> > vsi2( v1 );
   cout << "The element at the top of stack vsi2 is "
        << vsi2.top( ) << "." << endl;
}
```

```Output
The element at the top of stack vsi2 is 1.
```

## <a name="top"></a><a name="top"></a> Вверх

Возвращает ссылку на элемент вверху стека.

```cpp
reference top();

const_reference top() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на последний элемент в контейнере, вставленный вверху стека.

### <a name="remarks"></a>Примечания

Для применения функции-члена стек должен быть непустым. Начало (верх) стека — это положение, занимаемое последним добавленным элементом, которое является последним элементом в конце контейнера.

Если возвращаемое значение `top` присваивается `const_reference` , то объект стека изменить нельзя. Если возвращаемое значение `top` присваивается `reference` , то объект стека можно изменить.

### <a name="example"></a>Пример

```cpp
// stack_top.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   stack <int> s1;

   s1.push( 1 );
   s1.push( 2 );

   int& i = s1.top( );
   const int& ii = s1.top( );

   cout << "The top integer of the stack s1 is "
        << i << "." << endl;
   i--;
   cout << "The next integer down is "<< ii << "." << endl;
}
```

```Output
The top integer of the stack s1 is 2.
The next integer down is 1.
```

## <a name="value_type"></a><a name="value_type"></a> value_type

Тип, представляющий тип объекта, который хранится в стеке в виде элемента.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для `value_type` базового контейнера, адаптированного стеком.

### <a name="example"></a>Пример

```cpp
// stack_value_type.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   // Declares stacks with default deque base container
   stack<int>::value_type AnInt;

   AnInt = 69;
   cout << "The value_type is AnInt = " << AnInt << endl;

   stack<int> s1;
   s1.push( AnInt );
   cout << "The element at the top of the stack is "
        << s1.top( ) << "." << endl;
}
```

```Output
The value_type is AnInt = 69
The element at the top of the stack is 69.
```

## <a name="see-also"></a>См. также раздел

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
