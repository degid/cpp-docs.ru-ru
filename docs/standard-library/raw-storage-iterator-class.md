---
title: Класс raw_storage_iterator
ms.date: 11/04/2016
f1_keywords:
- memory/std::raw_storage_iterator
- memory/std::raw_storage_iterator::element_type
- memory/std::raw_storage_iterator::iter_type
helpviewer_keywords:
- std::raw_storage_iterator [C++]
- std::raw_storage_iterator [C++], element_type
- std::raw_storage_iterator [C++], iter_type
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
ms.openlocfilehash: e5423d3b0801570167e1e0424aad18b9e8f74e7c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831428"
---
# <a name="raw_storage_iterator-class"></a>Класс raw_storage_iterator

Класс-адаптер, который предоставляется, чтобы алгоритмы могли сохранять свои результаты в неинициализированной памяти.

## <a name="syntax"></a>Синтаксис

```cpp
template <class OutputIterator, class Type>
    class raw_storage_iterator
```

### <a name="parameters"></a>Параметры

*OutputIterator*\
Указывает выходной итератор сохраняемого объекта.

*Type*\
Тип объекта, для которого выполняется выделение памяти.

## <a name="remarks"></a>Примечания

Класс описывает выходной итератор, который создает объекты типа `Type` в создаваемой им последовательности. Объект класса `raw_storage_iterator` \< **ForwardIterator**, **Type**> обращается к хранилищу через объект прямого итератора класса, `ForwardIterator` который задается при построении объекта. Для объекта, который сначала является классом `ForwardIterator` , выражение ** & \* сначала** должно обозначать несконструированное хранилище для следующего объекта (типа `Type` ) в созданной последовательности.

Этот класс адаптера используется, когда необходимо разделить выделение памяти и создание объектов. `raw_storage_iterator` можно использовать для копирования объектов в неинициализированное хранилище, например в память, выделенную с помощью функции `malloc`.

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[raw_storage_iterator](#raw_storage_iterator)|Создает итератор необработанного хранилища с указанным базовым выходным итератором.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[element_type](#element_type)|Предоставляет тип, описывающий элемент, в котором будет сохранен итератор необработанного хранилища.|
|[iter_type](#iter_type)|Предоставляет тип, который описывает итератор, базовый для итератора необработанного хранилища.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator*](#op_star)|Оператор разыменования, используемый для реализации выражения итератора вывода \* `ii`  =  `x` .|
|[operator=](#op_eq)|Оператор присваивания, используемый для реализации выражения итератора необработанного хранилища \* `i`  =  `x` для хранения в памяти.|
|[operator++](#op_add_add)|Преинкрементный и постинкрементный операторы для итераторов необработанного хранилища.|

### <a name="element_type"></a><a name="element_type"></a> element_type

Предоставляет тип, описывающий элемент, в котором будет сохранен итератор необработанного хранилища.

```cpp
typedef Type element_type;
```

#### <a name="remarks"></a>Примечания

Тип является синонимом для параметра шаблона класса raw_storage_iterator `Type` .

### <a name="iter_type"></a><a name="iter_type"></a> iter_type

Предоставляет тип, который описывает итератор, базовый для итератора необработанного хранилища.

```cpp
typedef ForwardIterator iter_type;
```

#### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `ForwardIterator`.

### <a name="operator"></a><a name="op_star"></a> operator\*

Оператор разыменования, используемый для реализации выражения итератора необработанного хранилища \* *II*  =  *x*.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator*();
```

#### <a name="return-value"></a>Возвращаемое значение

Ссылка на итератор необработанного хранилища

#### <a name="remarks"></a>Примечания

Требования к, предъявляемые к, `ForwardIterator` должны быть допустимыми только в случае, если итератору хранилища необработанных данных требуется только выражение \* *II*  =  *t* и что оно не говорит о **`operator`** себе или о `operator=` себе. Операторы-члены в этой реализации возвращают ** \*this**, поэтому [оператор =](#op_eq)(**консттипе**&) может выполнять фактическое хранилище в выражении, например \* *ptr*  =  `val` .

#### <a name="example"></a>Пример

```cpp
// raw_storage_iterator_op_deref.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };

   Int &operator=(int i)
   {
      if (!bIsConstructed)
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl;
      x = i;
      return *this;
   };

   int x;

private:
   bool bIsConstructed;
};

int main( void)
{
   Int *pInt = ( Int* ) malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;
*pInt = 5;
   raw_storage_iterator< Int*, Int > it( pInt );
*it = 5;
}
```

```Output
Not constructed.
Copying 5
Constructing 5
```

### <a name="operator"></a><a name="op_eq"></a> operator=

Оператор присваивания, используемый для реализации выражения итератора необработанного хранилища \* *i*  =  *x* для хранения в памяти.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator=(
    const Type& val);
```

#### <a name="parameters"></a>Параметры

*val*\
Значение объекта типа, `Type` вставляемого в память.

#### <a name="return-value"></a>Возвращаемое значение

Оператор вставляет `val` в память и возвращает ссылку на итератор необработанного хранилища.

#### <a name="remarks"></a>Примечания

Требования к `ForwardIterator` состоянию, которым должен удовлетворять итератор необработанного хранилища, должны \* быть допустимыми только для выражения *II*  =  *t* и не сообщать о **`operator`** `operator=` них. Эти операторы членов возвращают **`*this`** .

Оператор присваивания конструирует следующий объект в выходной последовательности с помощью хранимого значения итератора `first` , вычисляя выражение размещения New `new ( (void*) & *first ) Type( val )` .

#### <a name="example"></a>Пример

```cpp
// raw_storage_iterator_op_assign.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int( int i )
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if ( !bIsConstructed )
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl; x = i;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( void )
{
   Int *pInt = ( Int* )malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;

*pInt = 5;

   raw_storage_iterator<Int*, Int> it( pInt );
*it = 5;
}
```

```Output
Not constructed.
Copying 5
Constructing 5
```

### <a name="operator"></a><a name="op_add_add"></a> operator+ +

Преинкрементный и постинкрементный операторы для итераторов необработанного хранилища.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator++();

raw_storage_iterator<ForwardIterator, Type> operator++(int);
```

#### <a name="return-value"></a>Возвращаемое значение

Итератор необработанного хранилища или ссылка такой итератор.

#### <a name="remarks"></a>Примечания

Первый оператор в конечном итоге пытается извлечь и сохранить объект типа `CharType` из связанного входного потока. Второй оператор создает копию объекта, выполняет приращение объекта, а затем возвращает копию.

Первый оператор инкремента увеличивает объект итератора вывода, а затем возвращает ** \*this**.

Второй оператор инкремента создает копию ** \*this**объекта, увеличивает объект итератора вывода, а затем возвращает копию.

Конструктор сохраняет в `first` качестве объекта итератора вывода.

#### <a name="example"></a>Пример

```cpp
// raw_storage_iterator_op_incr.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

int main( void )
{
   int *pInt = new int[5];
   std::raw_storage_iterator<int*,int> it( pInt );
   for ( int i = 0; i < 5; i++, it++ ) {
      *it = 2 * i;
   };

   for ( int i = 0; i < 5; i++ ) cout << "array " << i << " = " << pInt[i] << endl;;

   delete[] pInt;
}
```

```Output
array 0 = 0
array 1 = 2
array 2 = 4
array 3 = 6
array 4 = 8
```

### <a name="raw_storage_iterator"></a><a name="raw_storage_iterator"></a> raw_storage_iterator

Создает итератор необработанного хранилища с указанным базовым выходным итератором.

```cpp
explicit raw_storage_iterator(ForwardIterator first);
```

#### <a name="parameters"></a>Параметры

*first*\
Прямой итератор, который лежит в основе создаваемого объекта `raw_storage_iterator`.

#### <a name="example"></a>Пример

```cpp
// raw_storage_iterator_ctor.cpp
// compile with: /EHsc /W3
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if (!bIsConstructed)
         cout << "Error! I'm not constructed!\n";
      cout << "Copying " << i << endl;  x = i; return *this;
   };
   int x;
   bool bIsConstructed;
};

int main( void )
{
   std::list<int> l;
   l.push_back( 1 );
   l.push_back( 2 );
   l.push_back( 3 );
   l.push_back( 4 );

   Int *pInt = (Int*)malloc(sizeof(Int)*l.size( ));
   memset (pInt, 0, sizeof(Int)*l.size( ));
   // Hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ), pInt );  // C4996
   for (unsigned int i = 0; i < l.size( ); i++)
      cout << "array " << i << " = " << pInt[i].x << endl;;

   memset (pInt, 0, sizeof(Int)*l.size( ));
   // hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ),
      std::raw_storage_iterator<Int*,Int>(pInt));  // C4996
   for (unsigned int i = 0; i < l.size( ); i++ )
      cout << "array " << i << " = " << pInt[i].x << endl;

   free(pInt);
}
```

```Output
Error! I'm not constructed!
Copying 1
Error! I'm not constructed!
Copying 2
Error! I'm not constructed!
Copying 3
Error! I'm not constructed!
Copying 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
Constructing 1
Constructing 2
Constructing 3
Constructing 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
```
