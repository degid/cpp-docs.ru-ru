---
title: Класс queue
ms.date: 11/04/2016
f1_keywords:
- queue/std::queue::container_type
- queue/std::queue::size_type
- queue/std::queue::value_type
- queue/std::queue::back
- queue/std::queue::empty
- queue/std::queue::front
- queue/std::queue::pop
- queue/std::queue::push
- queue/std::queue::size
helpviewer_keywords:
- std::queue [C++], container_type
- std::queue [C++], size_type
- std::queue [C++], value_type
- std::queue [C++], back
- std::queue [C++], empty
- std::queue [C++], front
- std::queue [C++], pop
- std::queue [C++], push
- std::queue [C++], size
ms.assetid: 28c20ab0-3a72-4185-9e0f-5a44eea0e204
ms.openlocfilehash: e0bfa4ab037b52b237bd674d5f705de4e9699383
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832611"
---
# <a name="queue-class"></a>Класс queue

Класс-шаблон адаптера контейнера, который предоставляет ограничение функциональности для некоторого базового типа контейнера, ограничивая доступ к его передним и задним элементам. Элементы могут добавляться сзади или удаляться спереди. Элементы могут проверяться на любом конце очереди.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type, class Container = deque <Type>>
class queue
```

### <a name="parameters"></a>Параметры

*Type*\
Тип данных элемента для сохранения в очереди.

*Container*\
Тип базового контейнера, используемый для реализации очереди.

## <a name="remarks"></a>Примечания

Элементы класса, `Type` оговоренные в первом параметре шаблона объекта очереди, являются синонимами [value_type](#value_type) и должны соответствовать типу элемента в базовом классе контейнера, `Container` указанном вторым параметром-шаблоном. Объект `Type` должен быть назначаемым, чтобы можно было скопировать объекты этого типа и присвоить значения переменным этого типа.

К подходящим базовым классам контейнера для очереди относятся [deque](../standard-library/deque-class.md) и [List](../standard-library/list-class.md)или любой другой контейнер последовательности, поддерживающий операции `front` , `back` , `push_back` и `pop_front` . Класс базового контейнера инкапсулирован в адаптер контейнера, который предоставляет только ограниченный набор функций-членов контейнера последовательностей в виде открытого интерфейса.

Объекты очередей сравнимы по равенству только в том случае, если элементы класса `Type` сравнимы по равенству и меньше, чем сравнимы, только если элементы класса `Type` менее сравнимы.

В стандартной библиотеке C++ определено три типа адаптеров контейнера: стек (stack), очередь (queue) и очередь с приоритетом (priority_queue). Каждый ограничивает функциональность некоторого базового класса контейнеров для обеспечения точно управляемого интерфейса к стандартной структуре данных.

- [Класс Stack](../standard-library/stack-class.md) поддерживает структуру данных «последним пов основе» (LIFO). Хороший аналог такого подхода — стопка тарелок. Элементы (тарелки) можно вставлять, проверять или удалять только из верхней части стека, которая является последним элементом в конце базового контейнера. Ограничение на доступ только к верхнему элементу является причиной использования класса стека.

- Класс очереди поддерживает структуру данных "первым поступил — первым обслужен" (FIFO). Хороший аналог такого подхода — очередь из людей к банковскому служащему. Элементы (люди) можно добавлять в конец очереди и удалять из начала очереди. Проверять можно как начало, так и конец очереди. Ограничение на доступ только к переднему и заднему элементам в таком подходе является причиной использования класса очереди.

- [Класс priority_queue](../standard-library/priority-queue-class.md) упорядочивает элементы, чтобы наибольший элемент всегда находился сверху. Он поддерживает вставку элемента, а также проверку и удаление верхнего элемента. Хороший аналог такого подхода — очередь из людей, упорядоченная по возрасту, росту или любому другому критерию.

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[очереди](#queue)|Создает `queue`, который является пустым или копией объекта базового контейнера.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[container_type](#container_type)|Тип, предоставляющий базовый контейнер для изменения в `queue`.|
|[size_type](#size_type)|Целочисленный Typedef без знака, который может представлять число элементов в `queue`.|
|[value_type](#value_type)|Тип, представляющий тип объекта, который хранится в виде элемента в `queue`.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[back](#back)|Возвращает ссылку на последний и наиболее недавно добавленный элемент в конец `queue`.|
|[empty](#empty)|Проверяет, является ли `queue` пустым.|
|[front](#front)|Возвращает ссылку на первый элемент в начале `queue`.|
|[pор](#pop)|Удаляет элемент из начала `queue`.|
|[push](#push)|Добавляет элемент в конец `queue`.|
|[size](#size)|Возвращает количество элементов в контейнере `queue`.|

## <a name="back"></a><a name="back"></a> back

Возвращает ссылку на последний и наиболее недавно добавленный элемент в конце очереди.

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последний элемент очереди. Если очередь пуста, возвращаемое значение не определено.

### <a name="remarks"></a>Примечания

Если возвращаемое значение `back` присвоено `const_reference`, то объект очереди изменить нельзя. Если возвращаемое значение `back` присваивается `reference` , то объект очереди можно изменить.

При компиляции с помощью [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), для которого задано значение 1 или 2, при попытке доступа к элементу в пустой очереди возникнет ошибка времени выполнения.  Дополнительные сведения см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// queue_back.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1;

   q1.push( 10 );
   q1.push( 11 );

   int& i = q1.back( );
   const int& ii = q1.front( );

   cout << "The integer at the back of queue q1 is " << i
        << "." << endl;
   cout << "The integer at the front of queue q1 is " << ii
        << "." << endl;
}
```

## <a name="container_type"></a><a name="container_type"></a> container_type

Тип, предоставляющий базовый контейнер для изменения.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Container`. Два класса контейнеров последовательности в стандартной библиотеке C++ — класс list и класс по умолчанию deque — соответствуют требованиям для использования в качестве базового контейнера для объекта очереди. Также можно использовать пользовательские типы, удовлетворяющие требованиям.

Дополнительные сведения о `Container` см. в разделе "Примечания" документации к [Класс queue](../standard-library/queue-class.md).

### <a name="example"></a>Пример

См. пример для [queue](#queue) с примером объявления и использования `container_type`.

## <a name="empty"></a><a name="empty"></a> empty

Проверяет, пуста ли очередь.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если очередь пуста; **`false`** значение, если очередь не пуста.

### <a name="example"></a>Пример

```cpp
// queue_empty.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
using namespace std;

   // Declares queues with default deque base container
   queue <int> q1, q2;

   q1.push( 1 );

   if ( q1.empty( ) )
      cout << "The queue q1 is empty." << endl;
   else
      cout << "The queue q1 is not empty." << endl;

   if ( q2.empty( ) )
      cout << "The queue q2 is empty." << endl;
   else
      cout << "The queue q2 is not empty." << endl;
}
```

```Output
The queue q1 is not empty.
The queue q2 is empty.
```

## <a name="front"></a><a name="front"></a> front

Возвращает ссылку на первый элемент в начале очереди.

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Возвращаемое значение

Первый элемент очереди. Если очередь пуста, возвращаемое значение не определено.

### <a name="remarks"></a>Примечания

Если возвращаемое значение `front` присвоено `const_reference`, то объект очереди изменить нельзя. Если возвращаемое значение `front` присваивается `reference` , то объект очереди можно изменить.

Функция-член возвращает `reference` к первому элементу управляемой последовательности, который должен быть непустым.

При компиляции с помощью [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), для которого задано значение 1 или 2, при попытке доступа к элементу в пустой очереди возникнет ошибка времени выполнения.  Дополнительные сведения см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// queue_front.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main() {
   using namespace std;
   queue <int> q1;

   q1.push( 10 );
   q1.push( 20 );
   q1.push( 30 );

   queue <int>::size_type i;
   i = q1.size( );
   cout << "The queue length is " << i << "." << endl;

   int& ii = q1.back( );
   int& iii = q1.front( );

   cout << "The integer at the back of queue q1 is " << ii
        << "." << endl;
   cout << "The integer at the front of queue q1 is " << iii
        << "." << endl;
}
```

## <a name="pop"></a><a name="pop"></a> pор

Удаляет элемент из начала очереди.

```cpp
void pop();
```

### <a name="remarks"></a>Примечания

Для применения функции-члена очередь не должна быть пустой. Начало (верх) очереди — это положение, занимаемое последним добавленным элементом, которое является последним элементом в конце контейнера.

### <a name="example"></a>Пример

```cpp
// queue_pop.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1, s2;

   q1.push( 10 );
   q1.push( 20 );
   q1.push( 30 );

   queue <int>::size_type i;
   i = q1.size( );
   cout << "The queue length is " << i << "." << endl;

   i = q1.front( );
   cout << "The element at the front of the queue is "
        << i << "." << endl;

   q1.pop( );

   i = q1.size( );
   cout << "After a pop the queue length is "
        << i << "." << endl;

   i = q1. front ( );
   cout << "After a pop, the element at the front of the queue is "
        << i << "." << endl;
}
```

```Output
The queue length is 3.
The element at the front of the queue is 10.
After a pop the queue length is 2.
After a pop, the element at the front of the queue is 20.
```

## <a name="push"></a><a name="push"></a> push

Добавляет элемент в конец queue.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Параметры

*val*\
Элемент, добавляемый в конец очереди.

### <a name="remarks"></a>Примечания

Конец очереди — это положение, занимаемое последним добавленным элементом, которое является последним элементом в конце контейнера.

### <a name="example"></a>Пример

```cpp
// queue_push.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1;

   q1.push( 10 );
   q1.push( 20 );
   q1.push( 30 );

   queue <int>::size_type i;
   i = q1.size( );
   cout << "The queue length is " << i << "." << endl;

   i = q1.front( );
   cout << "The element at the front of the queue is "
        << i << "." << endl;
}
```

```Output
The queue length is 3.
The element at the front of the queue is 10.
```

## <a name="queue"></a><a name="queue"></a> queue

Создает пустую очередь или очередь-копию базового объекта-контейнера.

```cpp
queue();

explicit queue(const container_type& right);
```

### <a name="parameters"></a>Параметры

*right*\
Контейнер, в **`const`** который должна быть создана копия очереди.

### <a name="remarks"></a>Примечания

Базовый контейнер по умолчанию для очереди — deque. В качестве базового контейнера также можно указать список, но нельзя указать вектор, так как у него нет необходимой функции-члена `pop_front`.

### <a name="example"></a>Пример

```cpp
// queue_queue.cpp
// compile with: /EHsc
#include <queue>
#include <vector>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares queue with default deque base container
   queue <char> q1;

   // Explicitly declares a queue with deque base container
   queue <char, deque<char> > q2;

   // These lines don't cause an error, even though they
   // declares a queue with a vector base container
   queue <int, vector<int> > q3;
   q3.push( 10 );
   // but the following would cause an error because vector has
   // no pop_front member function
   // q3.pop( );

   // Declares a queue with list base container
   queue <int, list<int> > q4;

   // The second member function copies elements from a container
   list<int> li1;
   li1.push_back( 1 );
   li1.push_back( 2 );
   queue <int, list<int> > q5( li1 );
   cout << "The element at the front of queue q5 is "
        << q5.front( ) << "." << endl;
   cout << "The element at the back of queue q5 is "
        << q5.back( ) << "." << endl;
}
```

```Output
The element at the front of queue q5 is 1.
The element at the back of queue q5 is 2.
```

## <a name="size"></a><a name="size"></a> size

Возвращает число элементов в очереди.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая длина очереди.

### <a name="example"></a>Пример

```cpp
// queue_size.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1, q2;
   queue <int>::size_type i;

   q1.push( 1 );
   i = q1.size( );
   cout << "The queue length is " << i << "." << endl;

   q1.push( 2 );
   i = q1.size( );
   cout << "The queue length is now " << i << "." << endl;
}
```

```Output
The queue length is 1.
The queue length is now 2.
```

## <a name="size_type"></a><a name="size_type"></a> size_type

Тип целого числа без знака, который может представлять количество элементов в очереди.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `size_type` базового контейнера, адаптированного очередью.

### <a name="example"></a>Пример

См. пример для [queue::front](#front) с примером объявления и использования `size_type`.

## <a name="value_type"></a><a name="value_type"></a> value_type

Тип, представляющий тип объекта, который хранится в виде элемента в очереди.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `value_type` базового контейнера, адаптированного очередью.

### <a name="example"></a>Пример

```cpp
// queue_value_type.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
using namespace std;

   // Declares queues with default deque base container
   queue<int>::value_type AnInt;

   AnInt = 69;
   cout << "The value_type is AnInt = " << AnInt << endl;

   queue<int> q1;
   q1.push(AnInt);
   cout << "The element at the front of the queue is "
        << q1.front( ) << "." << endl;
}
```

```Output
The value_type is AnInt = 69
The element at the front of the queue is 69.
```

## <a name="see-also"></a>См. также раздел

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
