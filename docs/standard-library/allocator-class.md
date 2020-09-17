---
title: Класс allocator
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator
- memory/std::allocator::const_pointer
- memory/std::allocator::const_reference
- memory/std::allocator::difference_type
- memory/std::allocator::pointer
- memory/std::allocator::reference
- memory/std::allocator::size_type
- memory/std::allocator::value_type
- memory/std::allocator::address
- memory/std::allocator::allocate
- memory/std::allocator::construct
- memory/std::allocator::deallocate
- memory/std::allocator::destroy
- memory/std::allocator::max_size
- memory/std::allocator::rebind
helpviewer_keywords:
- std::allocator [C++]
- std::allocator [C++], const_pointer
- std::allocator [C++], const_reference
- std::allocator [C++], difference_type
- std::allocator [C++], pointer
- std::allocator [C++], reference
- std::allocator [C++], size_type
- std::allocator [C++], value_type
- std::allocator [C++], address
- std::allocator [C++], allocate
- std::allocator [C++], construct
- std::allocator [C++], deallocate
- std::allocator [C++], destroy
- std::allocator [C++], max_size
- std::allocator [C++], rebind
ms.assetid: 3fd58076-56cc-43bb-ad58-b4b7c9c6b410
ms.openlocfilehash: 4857de0b77d69a0d256da2200e5f4d0eb9d51c51
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844825"
---
# <a name="allocator-class"></a>Класс allocator

Шаблон класса описывает объект, который управляет выделением и освобождением памяти для массивов объектов типа `Type` . Объект класса `allocator` является объектом распределителя по умолчанию, указанным в конструкторах для нескольких шаблонов классов контейнеров в стандартной библиотеке C++.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class allocator
```

### <a name="parameters"></a>Параметры

*Type*\
Тип объекта, для которого выполняется выделение и освобождение памяти.

## <a name="remarks"></a>Примечания

Все контейнеры стандартной библиотеки C++ имеют параметр шаблона, который по умолчанию имеет значение `allocator` . Создание контейнера с пользовательским распределителем дает возможность управлять выделением и освобождением памяти для элементов контейнера.

Например, объект распределителя может выделить память в закрытой куче или в общей памяти. Он также может выполнить оптимизацию для крупных или мелких объектов. Он может также указывать, посредством определения типов, которые он предоставляет, что доступ к элементам возможен только через специальные объекты метода доступа, управляющие общей памятью или выполняющие автоматическую сборку мусора. Таким образом, класс, который выделяет память с использованием объекта распределителя, должен использовать эти типы для объявления указателя и объектов ссылок, как это делают контейнеры в библиотеке стандартов C++.

<strong>(Только C++ 98/03)</strong> При наследовании от класса распределителя необходимо предоставить структуру [повторной привязки](#rebind) , `_Other` typedef которой ссылается на вновь производный класс.

Таким образом, распределитель определяет следующие типы:

- [pointer](#pointer) ведет себя как указатель на `Type` .

- [const_pointer](#const_pointer) ведет себя как Константный указатель на `Type` .

- [ссылка](#reference) ведет себя как ссылка на `Type` .

- [const_reference](#const_reference) ведет себя как Константная ссылка на `Type` .

Они `Type` указывают форму, которую должны принимать указатели и ссылки для выделенных элементов. ( [распределитель::p оинтер](#pointer) не обязательно такой же, как и `Type*` для всех объектов распределителя, хотя он имеет это очевидное определение для класса `allocator` .)

**C++11 and later:** чтобы включить операции перемещения в распределитель, используйте минимальный интерфейс распределителя и реализуйте конструктор копирования, операторы == и !=, функции allocate и deallocate. Дополнительные сведения и пример см. в статье [Распределители](allocators.md).

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[allocator](#allocator)|Конструкторы, используемые для создания объектов `allocator`.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[const_pointer](#const_pointer)|Тип, предоставляющий постоянный указатель на тип объекта, управляемого распределителем.|
|[const_reference](#const_reference)|Тип, предоставляющий постоянную ссылку на тип объекта, управляемого распределителем.|
|[difference_type](#difference_type)|Тип целого числа со знаком, который может представлять разницу между значениями указателей на тип объекта, управляемого распределителем.|
|[pointer](#pointer)|Тип, предоставляющий указатель на тип объекта, управляемого распределителем.|
|[reference](#reference)|Тип, предоставляющий ссылку на тип объекта, управляемого распределителем.|
|[size_type](#size_type)|Целочисленный тип без знака, который может представлять длину любой последовательности, которую `allocator` может выделить объект типа.|
|[value_type](#value_type)|Тип, управляемый распределителем.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[address](#address)|Находит адрес объекта, значение которого задано.|
|[памяти](#allocate)|Выделяет блок памяти, достаточный для хранения по крайней мере некоторого указанного числа элементов.|
|[создания](#construct)|Создает определенный тип объекта по указанному адресу, инициализированный с использованием заданного значения.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|
|[завершить](#destroy)|Вызывает деструктор объектов без освобождения памяти, в которой хранился объект.|
|[max_size](#max_size)|Возвращает число элементов типа `Type`, которые могут быть выделены объектом класса `allocator` в пределах имеющейся свободной памяти.|
|[rebind](#rebind)|Структура, позволяющая распределителю, предназначенному для объектов одного типа, выделять память для объектов другого типа.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator=](#op_eq)|Назначает один объект `allocator` другому объекту `allocator`.|

### <a name="address"></a>адрес <a name="address"></a>

Находит адрес объекта, значение которого задано.

```cpp
pointer address(reference val) const;
const_pointer address(const_reference val) const;
```

#### <a name="parameters"></a>Параметры

*val*\
Константное или неконстантное значение объекта, адрес которого ищется.

#### <a name="return-value"></a>Возвращаемое значение

Константный или неконстантный указатель на найденный объект соответственно константного или неконстантного значения.

#### <a name="remarks"></a>Примечания

Функции элементов возвращают адрес *Val*в форме, которую указатели должны принимать для выделенных элементов.

#### <a name="example"></a>Пример

```cpp
// allocator_address.cpp
// compile with: /EHsc
#include <memory>
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1Ptr;
   const int k = 8;
   v1Ptr = v1Alloc.address( *find(v1.begin( ), v1.end( ), k) );
   // v1Ptr = v1Alloc.address( k );
   cout << "The integer addressed by v1Ptr has a value of: "
        << "*v1Ptr = " << *v1Ptr << "." << endl;
}
```

```Output
The original vector v1 is:
( 2 4 6 8 10 12 14 ).
The integer addressed by v1Ptr has a value of: *v1Ptr = 8.
```

### <a name="allocate"></a><a name="allocate"></a> памяти

Выделяет блок памяти, достаточный для хранения по крайней мере некоторого указанного числа элементов.

```cpp
pointer allocate(size_type count, const void* _Hint);
```

#### <a name="parameters"></a>Параметры

*count*\
Количество элементов, для которых необходимо выделить достаточный объем памяти.

*_Hint*\
Константный указатель, который может помочь объекту allocator удовлетворить запрос хранилища, найдя адрес объекта, выделенного до запроса.

#### <a name="return-value"></a>Возвращаемое значение

Указатель на выделенный объект или значение null, если память не была выделена.

#### <a name="remarks"></a>Примечания

Функция-член выделяет хранилище для массива элементов count типа `Type` , вызывая оператор New (*Count*). Она возвращает указатель на выделенный объект. Аргумент hint помогает некоторым распределителям улучшить расположение ссылок; недопустимый вариант — это адрес объекта, выделенный ранее тем же объектом allocator, который еще не был освобожден. Чтобы не предоставлять подсказок, используйте аргумент пустого указателя.

#### <a name="example"></a>Пример

```cpp
// allocator_allocate.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<int> v1Alloc;
   allocator<int>::pointer v1aPtr;
   v1aPtr = v1Alloc.allocate ( 10 );

   int i;
   for ( i = 0 ; i < 10 ; i++ )
   {
      v1aPtr[ i ] = i;
   }

   for ( i = 0 ; i < 10 ; i++ )
   {
      cout << v1aPtr[ i ] << " ";
   }
   cout << endl;
   v1Alloc.deallocate( v1aPtr, 10 );
}
```

```Output
0 1 2 3 4 5 6 7 8 9
```

### <a name="allocator"></a><a name="allocator"></a> выделен

Конструкторы, используемые для создания объектов allocator.

```cpp
allocator();
allocator(const allocator<Type>& right);
template <class Other>
    allocator(const allocator<Other>& right);
```

#### <a name="parameters"></a>Параметры

*right*\
Объект allocator для копирования.

#### <a name="remarks"></a>Примечания

Конструктор не выполняет никаких действий. Однако в целом объект allocator, построенный из другого объекта allocator, должен оцениваться как эквивалентный ему, и должно быть разрешено перемешивание выделения и освобождения объектов между этими двумя объектами allocator.

#### <a name="example"></a>Пример

```cpp
// allocator_allocator.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int {
public:
   Int( int i )
   {
      cout << "Constructing " << ( void* )this  << endl;
      x = i;
      bIsConstructed = true;
   };
   ~Int( )
   {
      cout << "Destructing " << ( void* )this << endl;
      bIsConstructed = false;
   };
   Int &operator++( )
   {
      x++;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( )
{
   allocator<double> Alloc;
   vector <Int>:: allocator_type v1Alloc;

   allocator<double> cAlloc(Alloc);
   allocator<Int> cv1Alloc(v1Alloc);

   if ( cv1Alloc == v1Alloc )
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."
           << endl;

   if ( cAlloc == Alloc )
      cout << "The allocator objects cAlloc & Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cAlloc & Alloc are not equal."
           << endl;
}
```

```Output
The allocator objects cv1Alloc & v1Alloc are equal.
The allocator objects cAlloc & Alloc are equal.
```

### <a name="const_pointer"></a><a name="const_pointer"></a> const_pointer

Тип, предоставляющий постоянный указатель на тип объекта, управляемого распределителем.

```cpp
typedef const value_type *const_pointer;
```

#### <a name="remarks"></a>Примечания

Тип указателя описывает объект, `ptr` который может обозначать через выражение `*ptr` любой объект const, который может быть выделен объектом типа `allocator` .

#### <a name="example"></a>Пример

```cpp
// allocator_const_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( i * 2 );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1Ptr;
   const int k = 10;
   v1Ptr = v1Alloc.address( k );

   cout << "The integer's address found has a value of: "
        << *v1Ptr << "." << endl;
}
```

```Output
The original vector v1 is:
( 2 4 6 8 10 12 14 ).
The integer's address found has a value of: 10.
```

### <a name="const_reference"></a><a name="const_reference"></a> const_reference

Тип, предоставляющий постоянную ссылку на тип объекта, управляемого распределителем.

```cpp
typedef const value_type& const_reference;
```

#### <a name="remarks"></a>Примечания

Ссылочный тип описывает объект, который может обозначать любой объект const, который может быть выделен объектом типа `allocator` .

#### <a name="example"></a>Пример

```cpp
// allocator_const_ref.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter, vfIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vfIter = v.begin( );
   allocator<double>::const_reference vcref =*vfIter;
   cout << "The value of the element referred to by vref is: "
        << vcref << ",\n the first element in the vector." << endl;

   // const references can have their elements modified,
   // so the following would generate an error:
   // vcref = 150;
   // but the value of the first element could be modified through
   // its nonconst iterator and the const reference would remain valid
*vfIter = 175;
   cout << "The value of the element referred to by vcref,"
        <<"\n after nofication through its nonconst iterator, is: "
        << vcref << "." << endl;
}
```

```Output
The original vector v is:
( 100 200 300 400 500 600 700 ).
The value of the element referred to by vref is: 100,
the first element in the vector.
The value of the element referred to by vcref,
after nofication through its nonconst iterator, is: 175.
```

### <a name="construct"></a><a name="construct"></a> создания

Создает определенный тип объекта по указанному адресу, инициализированный с использованием заданного значения.

```cpp
void construct(pointer ptr, const Type& val);
void construct(pointer ptr, Type&& val);
template <class _Other>
    void construct(pointer ptr, _Other&&... val);
```

#### <a name="parameters"></a>Параметры

*ptr*\
Указатель места, в котором должен создаваться объект.

*val*\
Значение, с которым создаваемый объект будет инициализирован.

#### <a name="remarks"></a>Примечания

Первая функция-член эквивалентна `new ((void *) ptr) Type(val)` .

#### <a name="example"></a>Пример

```cpp
// allocator_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 3 * i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::pointer v1PtrA;
   int kA = 6, kB = 7;
   v1PtrA = v1Alloc.address( *find( v1.begin( ), v1.end( ), kA ) );
   v1Alloc.destroy ( v1PtrA );
   v1Alloc.construct ( v1PtrA , kB );

   cout << "The modified vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
( 3 6 9 12 15 18 21 ).
The modified vector v1 is:
( 3 7 9 12 15 18 21 ).
```

### <a name="deallocate"></a><a name="deallocate"></a> deallocate

Освобождает указанное число объектов из памяти, начиная с заданной позиции.

```cpp
void deallocate(pointer ptr, size_type count);
```

#### <a name="parameters"></a>Параметры

*ptr*\
Указатель на первый объект, который должен быть освобожден из хранилища.

*count*\
Количество объектов для освобождения из хранилища.

#### <a name="remarks"></a>Примечания

Функция-член освобождает хранилище для массива объектов счетчика типа `Type` , начиная с *ptr*, путем вызова `operator delete(ptr)` . Указатель *ptr* должен быть возвращен ранее путем вызова метода [allocate](#allocate) для объекта распределителя, который сравнивает ** \* этот**объект, выделяя объект массива такого же размера и типа. `deallocate` никогда не создает исключений.

#### <a name="example"></a>Пример

Пример использования этой функции-члена см. в разделе [allocator::allocate](#allocate).

### <a name="destroy"></a><a name="destroy"></a> завершить

Вызывает деструктор объектов без освобождения памяти, в которой хранился объект.

```cpp
void destroy(pointer ptr);
```

#### <a name="parameters"></a>Параметры

*ptr*\
Указатель, обозначающий адрес уничтожаемого объекта.

#### <a name="remarks"></a>Примечания

Функция-член уничтожает объект, обозначенный *ptr*, путем вызова деструктора `ptr->Type::~Type` .

#### <a name="example"></a>Пример

```cpp
// allocator_destroy.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::pointer v1PtrA;
   int kA = 12, kB = -99;
   v1PtrA = v1Alloc.address( *find(v1.begin( ), v1.end( ), kA) );
   v1Alloc.destroy ( v1PtrA );
   v1Alloc.construct ( v1PtrA , kB );

   cout << "The modified vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
( 2 4 6 8 10 12 14 ).
The modified vector v1 is:
( 2 4 6 8 10 -99 14 ).
```

### <a name="difference_type"></a><a name="difference_type"></a> difference_type

Тип целого числа со знаком, который может представлять разницу между значениями указателей на тип объекта, управляемого распределителем.

```cpp
typedef ptrdiff_t difference_type;
```

#### <a name="remarks"></a>Примечания

Тип целого числа со знаком описывает объект, который может представлять разницу между адресами любых двух элементов в последовательности, которую может выделить объект типа `allocator` .

#### <a name="example"></a>Пример

```cpp
// allocator_diff_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 0 ; i <= 7 ; i++ )
   {
      v1.push_back( i * 2 );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1PtrA, v1PtrB;
   const int kA = 4, kB =12;
   v1PtrA = v1Alloc.address( kA );
   v1PtrB = v1Alloc.address( kB );
   allocator<int>::difference_type v1diff = *v1PtrB - *v1PtrA;

   cout << "Pointer v1PtrA addresses " << *v1PtrA << "." << endl;
   cout << "Pointer v1PtrB addresses " << *v1PtrB <<  "." << endl;
   cout << "The difference between the integer's addresses is: "
        << v1diff << "." << endl;
}
```

```Output
The original vector v1 is:
( 0 2 4 6 8 10 12 14 ).
Pointer v1PtrA addresses 4.
Pointer v1PtrB addresses 12.
The difference between the integer's addresses is: 8.
```

### <a name="max_size"></a><a name="max_size"></a> max_size

Возвращает количество элементов типа `Type`, которые могут быть выделены объектом класса в пределах имеющейся свободной памяти.

```cpp
size_type max_size() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Количество элементов, которые могут быть выделены.

#### <a name="example"></a>Пример

```cpp
// allocator_max_size.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   vector <double> v2;
   vector <double> ::iterator v2Iter;
   vector <double> :: allocator_type v2Alloc;
   allocator<int>::size_type v1size;
   v1size = v1Alloc.max_size( );

   cout << "The number of integers that can be allocated before\n"
        << " the free memory in the vector v1 is used up is: "
        << v1size << "." << endl;

   int ii;
   for ( ii = 1 ; ii <= 7 ; ii++ )
   {
      v2.push_back( ii * 10.0 );
   }

   cout << "The original vector v2 is:\n ( " ;
   for ( v2Iter = v2.begin( ) ; v2Iter != v2.end( ) ; v2Iter++ )
      cout << *v2Iter << " ";
   cout << ")." << endl;
   allocator<double>::size_type v2size;
   v2size = v2Alloc.max_size( );

   cout << "The number of doubles that can be allocated before\n"
        << " the free memory in the vector v2 is used up is: "
        << v2size << "." << endl;
}
```

### <a name="operator"></a><a name="op_eq"></a> operator=

Назначает один объект allocator другому объекту allocator.

```cpp
template <class Other>
    allocator<Type>& operator=(const allocator<Other>& right);
```

#### <a name="parameters"></a>Параметры

*right*\
Объект allocator для назначения другому такому объекту.

#### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект allocator

#### <a name="remarks"></a>Примечания

Оператор присваивания шаблона не выполняет никаких действий. Однако в целом объект allocator, назначенный другому объекту allocator, должен оцениваться как эквивалентный ему, и должно быть разрешено перемешивание выделения и освобождения объектов между этими двумя объектами allocator.

#### <a name="example"></a>Пример

```cpp
// allocator_op_assign.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int {
public:
   Int(int i)
   {
      cout << "Constructing " << ( void* )this  << endl;
      x = i;
      bIsConstructed = true;
   };
   ~Int( ) {
      cout << "Destructing " << ( void* )this << endl;
      bIsConstructed = false;
   };
   Int &operator++( )
   {
      x++;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( )
{
   allocator<Int> Alloc;
   allocator<Int> cAlloc ;
   cAlloc = Alloc;
}
```

### <a name="pointer"></a><a name="pointer"></a> pointer

Тип, предоставляющий указатель на тип объекта, управляемого распределителем.

```cpp
typedef value_type *pointer;
```

#### <a name="remarks"></a>Примечания

Тип указателя описывает объект, `ptr` который может обозначать через выражение ** \* ptr**любой объект, который может быть выделен объектом типа `allocator` .

#### <a name="example"></a>Пример

```cpp
// allocator_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 3 * i );
   }

   cout << "The original vector v1 is:\n( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1Ptr;
   const int k = 12;
   v1Ptr = v1Alloc.address( k );

   cout << "The integer addressed by v1Ptr has a value of: "
        << "*v1Ptr = " << *v1Ptr << "." << endl;
}
```

```Output
The original vector v1 is:
( 3 6 9 12 15 18 21 ).
The integer addressed by v1Ptr has a value of: *v1Ptr = 12.
```

### <a name="rebind"></a><a name="rebind"></a> повторно привязать

Структура, позволяющая распределителю, предназначенному для объектов одного типа, выделять память для объектов другого типа.

```cpp
struct rebind { typedef allocator<_Other> other; };
```

#### <a name="parameters"></a>Параметры

*иной*\
Тип элемента, для которого выделяется память.

#### <a name="remarks"></a>Примечания

Эту структуру удобно использовать для выделения памяти для типа, который отличается от типа элемента реализуемого контейнера.

Шаблон класса Member определяет тип other. Его единственная цель — предоставить имя типа с `allocator<_Other>` учетом имени типа `allocator<Type>` .

Например, при наличии объекта распределителя `al` типа `A` можно выделить объект типа `_Other` с помощью выражения:

```cpp
A::rebind<Other>::other(al).allocate(1, (Other *)0)
```

Кроме того, можно дать имя его типу указателя, написав тип:

```cpp
A::rebind<Other>::other::pointer
```

#### <a name="example"></a>Пример

```cpp
// allocator_rebind.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

typedef vector<int>::allocator_type IntAlloc;
int main( )
{
   IntAlloc v1Iter;
   vector<int> v1;

   IntAlloc::rebind<char>::other::pointer pszC =
      IntAlloc::rebind<char>::other(v1.get_allocator()).allocate(1, (void *)0);

   int * pInt = v1Iter.allocate(10);
}
```

### <a name="reference"></a><a name="reference"></a> IsReference

Тип, предоставляющий ссылку на тип объекта, управляемого распределителем.

```cpp
typedef value_type& reference;
```

#### <a name="remarks"></a>Примечания

Ссылочный тип описывает объект, который может обозначать любой объект, который может быть выделен объектом типа `allocator` .

#### <a name="example"></a>Пример

```cpp
// allocator_reference.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter, vfIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vfIter = v.begin( );
   allocator<double>::reference vref =*vfIter;
   cout << "The value of the element referred to by vref is: "
        << vref << ",\n the first element in the vector." << endl;

   // nonconst references can have their elements modified
   vref = 150;
   cout << "The element referred to by vref after being modified is: "
        << vref << "." << endl;
}
```

```Output
The original vector v is:
( 100 200 300 400 500 600 700 ).
The value of the element referred to by vref is: 100,
the first element in the vector.
The element referred to by vref after being modified is: 150.
```

### <a name="size_type"></a><a name="size_type"></a> size_type

Целочисленный тип без знака, который может представлять длину любой последовательности, которую `allocator` может выделить объект типа.

```cpp
typedef size_t size_type;
```

#### <a name="example"></a>Пример

```cpp
// allocator_size_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   allocator<double>::size_type vsize;
   vsize = vAlloc.max_size( );

   cout << "The number of doubles that can be allocated before\n"
        << " the free memory in the vector v is used up is: "
        << vsize << "." << endl;
}
```

### <a name="value_type"></a><a name="value_type"></a> value_type

Тип, управляемый распределителем.

```cpp
typedef Type value_type;
```

#### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Type`.

#### <a name="example"></a>Пример

```cpp
// allocator_value_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>
using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter, vfIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vfIter = v.begin( );
   allocator<double>::value_type vecVal = 150.0;
*vfIter = vecVal;
   cout << "The value of the element addressed by vfIter is: "
        << *vfIter << ",\n the first element in the vector." << endl;

   cout << "The modified vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v is:
( 100 200 300 400 500 600 700 ).
The value of the element addressed by vfIter is: 150,
the first element in the vector.
The modified vector v is:
( 150 200 300 400 500 600 700 ).
```

## <a name="helpers"></a>Вспомогательные методы

### <a name="allocator_arg_t"></a><a name="allocator_arg_t"></a> allocator_arg_t

```cpp
struct allocator_arg_t { explicit allocator_arg_t() = default; };
inline constexpr allocator_arg_t allocator_arg{};
```

### <a name="uses_allocator"></a><a name="uses_allocator"></a> uses_allocator

```cpp
template <class T, class Alloc> struct uses_allocator;
```
