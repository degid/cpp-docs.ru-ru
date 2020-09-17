---
title: Класс insert_iterator
ms.date: 11/04/2016
f1_keywords:
- iterator/std::insert_iterator
- iterator/std::insert_iterator::container_type
- iterator/std::insert_iterator::reference
helpviewer_keywords:
- std::insert_iterator [C++]
- std::insert_iterator [C++], container_type
- std::insert_iterator [C++], reference
ms.assetid: d5d86405-872e-4e3b-9e68-c69a2b7e8221
ms.openlocfilehash: 530168f5e259934f7d614b305e6ac1092ba68f4d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233162"
---
# <a name="insert_iterator-class"></a>Класс insert_iterator

Описывает адаптер итератора, удовлетворяющий требованиям итератора вывода. Вставляет, а не перезаписывает элементы в последовательность, тем самым предоставляя семантику, отличную от семантики перезаписи, предоставляемой итераторами контейнеров последовательности и ассоциативных контейнеров C++. Класс `insert_iterator` шаблонизируется в адаптируемом типе контейнера.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Container>
class insert_iterator;
```

### <a name="parameters"></a>Параметры

*Container*\
Тип контейнера, в который итератор `insert_iterator` вставит элементы.

## <a name="remarks"></a>Примечания

Контейнер типа `Container` должен удовлетворять требованиям к контейнеру переменного размера и иметь функцию-член вставки с двумя аргументами, где параметры имеют тип `Container::iterator` и `Container::value_type` и возвращают тип `Container::iterator` . Последовательности из стандартной библиотеки С++ и упорядоченные ассоциативные контейнеры удовлетворяют данным требованиям и могут быть адаптированы к использованию в сочетании с `insert_iterator`s. Для ассоциативных контейнеров аргумент позиции обрабатывается как подсказка, которая потенциально может увеличить или снизить производительность в зависимости от эффективности подсказки. Итератор `insert_iterator` всегда необходимо инициализировать с его контейнером.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание:|
|-|-|
|[insert_iterator](#insert_iterator)|Создает итератор `insert_iterator`, добавляющий элемент в указанную позицию в контейнере.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[container_type](#container_type)|Тип, представляющий контейнер, в который будет осуществляться вставка общего типа.|
|[reference](#reference)|Тип, который предоставляет ссылку на элемент последовательности под управлением связанного контейнера.|

### <a name="operators"></a>Операторы

|Оператор|Описание:|
|-|-|
|[operator*](#op_star)|Оператор разыменования используется для реализации выражения итератора вывода * `i` = `x` для вставки общего типа.|
|[operator++](#op_add_add)|Увеличивает `insert_iterator` до следующего местоположения, в котором можно сохранить значение.|
|[operator=](#op_eq)|Оператор присваивания, используемый для реализации выражения итератора вывода * `i` = `x` для вставки общего типа.|

## <a name="requirements"></a>Требования

**Заголовок**:\<iterator>

**Пространство имен:** std

## <a name="insert_iteratorcontainer_type"></a><a name="container_type"></a>insert_iterator:: container_type

Тип, представляющий контейнер, в который будет осуществляться вставка общего типа.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра-шаблона *Container*.

### <a name="example"></a>Пример

```cpp
// insert_iterator_container_type.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   list<int> L1;
   insert_iterator<list<int> >::container_type L2 = L1;
   inserter ( L2, L2.end ( ) ) = 20;
   inserter ( L2, L2.end ( ) ) = 10;
   inserter ( L2, L2.begin ( ) ) = 40;

   list <int>::iterator vIter;
   cout << "The list L2 is: ( ";
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
/* Output:
The list L2 is: ( 40 20 10 ).
*/
```

## <a name="insert_iteratorinsert_iterator"></a><a name="insert_iterator"></a>insert_iterator:: insert_iterator

Создает итератор `insert_iterator`, добавляющий элемент в указанную позицию в контейнере.

```cpp
insert_iterator(Container& _Cont, typename Container::iterator _It);
```

### <a name="parameters"></a>Параметры

*_Cont*\
Контейнер, в который `insert_iterator` вставляет элементы.

*_It*\
Позиция для вставки.

### <a name="remarks"></a>Примечания

Все контейнеры имеют функцию-член вставки, которая вызывается `insert_iterator`. Для ассоциативных контейнеров параметр позиции — это просто предложение. Функция вставки предоставляет удобный способ вставки значений.

### <a name="example"></a>Пример

```cpp
// insert_iterator_insert_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for (i = 1 ; i < 4 ; ++i )
   {
      L.push_back ( 10 * i );
   }

   cout << "The list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;

   // Using the member function to insert an element
   inserter ( L, L.begin ( ) ) = 2;

   // Alternatively, you may use the template version
   insert_iterator< list < int> > Iter(L, L.end ( ) );
*Iter = 300;

   cout << "After the insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
/* Output:
The list L is:
( 10 20 30 ).
After the insertions, the list L is:
( 2 10 20 30 300 ).
*/
```

## <a name="insert_iteratoroperator"></a><a name="op_star"></a>insert_iterator::operator*

Разыменовывает итератор вставки и возвращает адреса элемента.

```cpp
insert_iterator<Container>& operator*();
```

### <a name="return-value"></a>Возвращаемое значение

Функция-член возвращает значение адресованного элемента.

### <a name="remarks"></a>Примечания

Используется для реализации значения ** \* iter**выражения итератора вывода  =  **value**. Если `Iter` является итератором, который обращается к элементу последовательности, то значение ** \* iter**  =  **value** заменяет этот элемент значением и не изменяет общее число элементов в последовательности.

### <a name="example"></a>Пример

```cpp
// insert_iterator_op_deref.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for (i = 0 ; i < 4 ; ++i )
   {
      L.push_back ( 2 * i );
   }

   cout << "The original list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;

   insert_iterator< list < int> > Iter(L, L.begin ( ) );
*Iter = 10;
*Iter = 20;
*Iter = 30;

   cout << "After the insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
/* Output:
The original list L is:
( 0 2 4 6 ).
After the insertions, the list L is:
( 10 20 30 0 2 4 6 ).
*/
```

## <a name="insert_iteratoroperator"></a><a name="op_add_add"></a>insert_iterator::operator++

Увеличивает `insert_iterator` до следующего местоположения, в котором можно сохранить значение.

```cpp
insert_iterator<Container>& operator++();

insert_iterator<Container> operator++(int);
```

### <a name="parameters"></a>Параметры

`insert_iterator`, адресующий следующее местоположение, в котором можно сохранить значение.

### <a name="remarks"></a>Примечания

Операторы preincrementation и postincrementation возвращают одинаковый результат.

### <a name="example"></a>Пример

```cpp
// insert_iterator_op_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 5 ; ++i )
   {
      vec.push_back (  i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is:\n ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   insert_iterator<vector<int> > ii ( vec, vec.begin ( ) );
*ii = 30;
   ii++;
*ii = 40;
   ii++;
*ii = 50;

   cout << "After the insertions, the vector vec becomes:\n ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
/* Output:
The vector vec is:
( 1 2 3 4 ).
After the insertions, the vector vec becomes:
( 30 40 50 1 2 3 4 ).
*/
```

## <a name="insert_iteratoroperator"></a><a name="op_eq"></a>insert_iterator::operator=

Вставляет значение в контейнер и возвращает итератор, который обновлен и указывает на новый элемент.

```cpp
insert_iterator<Container>& operator=(
    typename Container::const_reference val,);

insert_iterator<Container>& operator=(
    typename Container::value_type&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение, которое должно быть присвоено контейнеру.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент, вставленный в контейнер.

### <a name="remarks"></a>Примечания

Первый оператор-член вычисляет

`Iter = container->insert(Iter, val)`;

`++Iter;`

затем возвращает **`*this`** .

Второй оператор-член вычисляет

`Iter = container->insert(Iter, std::move(val));`

`++Iter;`

затем возвращает **`*this`** .

### <a name="example"></a>Пример

```cpp
// insert_iterator_op_assign.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for (i = 0 ; i < 4 ; ++i )
   {
      L.push_back ( 2 * i );
   }

   cout << "The original list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;

   insert_iterator< list < int> > Iter(L, L.begin ( ) );
*Iter = 10;
*Iter = 20;
*Iter = 30;

   cout << "After the insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
/* Output:
The original list L is:
( 0 2 4 6 ).
After the insertions, the list L is:
( 10 20 30 0 2 4 6 ).
*/
```

## <a name="insert_iteratorreference"></a><a name="reference"></a>insert_iterator:: Reference

Тип, который предоставляет ссылку на элемент последовательности под управлением связанного контейнера.

```cpp
typedef typename Container::reference reference;
```

### <a name="remarks"></a>Примечания

Тип, который описывает ссылку на элемент последовательности под управлением связанного контейнера.

### <a name="example"></a>Пример

```cpp
// insert_iterator_container_reference.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   list<int> L;
   insert_iterator<list<int> > iivIter( L , L.begin ( ) );
*iivIter = 10;
*iivIter = 20;
*iivIter = 30;

   list<int>::iterator LIter;
   cout << "The list L is: ( ";
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++ )
      cout << *LIter << " ";
   cout << ")." << endl;

   insert_iterator<list<int> >::reference
        RefFirst = *(L.begin ( ));
   cout << "The first element in the list L is: "
        << RefFirst << "." << endl;
}
/* Output:
The list L is: ( 10 20 30 ).
The first element in the list L is: 10.
*/
```

## <a name="see-also"></a>См. также раздел

[\<iterator>](../standard-library/iterator.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
