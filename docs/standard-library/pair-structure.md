---
title: Структура pair
ms.date: 11/04/2016
f1_keywords:
- utility/std::pair
helpviewer_keywords:
- pair class
ms.assetid: 539d3d67-80a2-4170-b347-783495d42109
ms.openlocfilehash: 6ccbea23835326d1e1840d8454f86c0eb72a5a7d
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042060"
---
# <a name="pair-structure"></a>Структура pair

Структура, позволяющая обрабатывать два объекта как один объект.

## <a name="syntax"></a>Синтаксис

```cpp
struct pair
{
    typedef T1 first_type;
    typedef T2 second_type;
    T1 first;
    T2 second;
    constexpr pair();
    pair(const pair&) = default;
    pair(pair&&) = default;
    constexpr pair(
        const T1& Val1,
        const T2& Val2);

    template <class Other1, class Other2>
    constexpr pair(const pair<Other1, Other2>& Right);

    template <class Other1, class Other2>
    constexpr pair(const pair <Other1 Val1, Other2 Val2>&& Right);

    template <class Other1, class Other2>
    constexpr pair(Other1&& Val1, Other2&& Val2);

    template <class... Args1, class... Args2>
    pair(piecewise_construct_t, tuple<Args1...> first_args, tuple<Args2...> second_args);

    pair& operator=(const pair& p);
    template<class U1, class U2> pair& operator=(const pair<U1, U2>& p);
    pair& operator=(pair&& p) noexcept(see below );
    template<class U1, class U2> pair& operator=(pair<U1, U2>&& p);

    void swap(pair& p) noexcept(see below );
};

template<class T1, class T2>
    pair(T1, T2) -> pair<T1, T2>;
```

### <a name="parameters"></a>Параметры

*Val1*\
Значение, которое инициализирует первый элемент `pair`.

*Val2*\
Значение, которое инициализирует второй элемент `pair`.

*right*\
Пара, значения которой будут использоваться для инициализации элементов другой пары.

## <a name="return-value"></a>Возвращаемое значение

Первый конструктор (по умолчанию) инициализирует первый элемент пары как тип по умолчанию, `T1` а второй элемент — по умолчанию для типа `T2` .  Он определяется, если оба типа являются конструируемым по умолчанию.

Второй конструктор инициализирует первый элемент пары в *val1* , а второй — *val2.*  Он определяется, если оба типа являются Copy-конструируемым.

Третий конструктор (шаблон) инициализирует первый элемент пары в `Right` . **первый** и второй `Right` . **второй**.  Он определяется в том случае, если оба типа пары конструируемым из предоставленных типов значений.


Четвертый конструктор инициализирует первый элемент из пары в *val1* , а второй — *val2* , используя [декларатор ссылки rvalue:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).  Он определяется в том случае, если оба типа пары конструируемым из предоставленных типов значений.

## <a name="remarks"></a>Комментарии

Структура шаблона хранит пару объектов типа `T1` и `T2` соответственно. Тип совпадает с `first_type` параметром шаблона `T1` , и тип совпадает с `second_type` параметром шаблона `T2` . `T1``T2`каждая из них должна предоставлять только конструктор по умолчанию, конструктор с одним аргументом и деструктор. Все члены типа `pair` являются открытыми, так как тип объявляется как, **`struct`** а не как **`class`** . Два наиболее распространенных способа применения пары — в качестве возвращаемых типов для функций, возвращающих два значения, и в качестве элементов для классов ассоциативных контейнеров [map](../standard-library/map-class.md) и [multimap](../standard-library/multimap-class.md), у которых есть ключ и тип значения, связанные с каждым элементом. Последний удовлетворяет требованиям для парного ассоциативного контейнера и имеет тип значения в форме `pair< const key_type, mapped_type >` .

## <a name="example"></a>Пример

```cpp
// utility_pair.cpp
// compile with: /EHsc
#include <utility>
#include <map>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;

   // Using the constructor to declare and initialize a pair
   pair <int, double> p1 ( 10, 1.1e-2 );

   // Compare using the helper function to declare and initialize a pair
   pair <int, double> p2;
   p2 = make_pair ( 10, 2.22e-1 );

   // Making a copy of a pair
   pair <int, double> p3 ( p1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;

   // Using a pair for a map element
   map <int, int> m1;
   map <int, int>::iterator m1_Iter;

   typedef pair <int, int> Map_Int_Pair;

   m1.insert ( Map_Int_Pair ( 1, 10 ) );
   m1.insert ( Map_Int_Pair ( 2, 20 ) );
   m1.insert ( Map_Int_Pair ( 3, 30 ) );

   cout << "The element pairs of the map m1 are:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " ( " << m1_Iter -> first << ", "
           << m1_Iter -> second << " )";
   cout   << "." << endl;

   // Using pair as a return type for a function
   pair< map<int,int>::iterator, bool > pr1, pr2;
   pr1 = m1.insert ( Map_Int_Pair ( 4, 40 ) );
   pr2 = m1.insert ( Map_Int_Pair (1, 10 ) );

   if( pr1.second == true )
   {
      cout << "The element (4,40) was inserted successfully in m1."
           << endl;
   }
   else
   {
      cout << "The element with a key value of\n"
           << " ( (pr1.first) -> first ) = " << ( pr1.first ) -> first
           << " is already in m1,\n so the insertion failed." << endl;
   }

   if( pr2.second == true )
   {
      cout << "The element (1,10) was inserted successfully in m1."
           << endl;
   }
   else
   {
      cout << "The element with a key value of\n"
           << " ( (pr2.first) -> first ) = " << ( pr2.first ) -> first
           << " is already in m1,\n so the insertion failed." << endl;
   }
}
```

```Output
The pair p1 is: ( 10, 0.011 ).
The pair p2 is: ( 10, 0.222 ).
The pair p3 is: ( 10, 0.011 ).
The element pairs of the map m1 are: ( 1, 10 ) ( 2, 20 ) ( 3, 30 ).
The element (4,40) was inserted successfully in m1.
The element with a key value of
( (pr2.first) -> first ) = 1 is already in m1,
so the insertion failed.
```
