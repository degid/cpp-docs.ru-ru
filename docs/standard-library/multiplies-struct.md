---
title: multiplies - структура
ms.date: 11/04/2016
f1_keywords:
- functional/std::multiplies
helpviewer_keywords:
- multiplies class
- multiplies struct
ms.assetid: ec85e8af-70ad-44ad-90f0-d961a5847864
ms.openlocfilehash: 3bccaf2a5e6594652a1179b357cdbbee2d2436b3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240582"
---
# <a name="multiplies-struct"></a>multiplies - структура

Стандартный объект функции, который выполняет над своими аргументами операцию умножения (двоичное `operator*`).

## <a name="syntax"></a>Синтаксис

```
template <class Type = void>
struct multiplies : public binary_function <Type, Type, Type>
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator*
template <>
struct multiplies<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) * std::forward<U>(Right));
};
```

### <a name="parameters"></a>Параметры

*Тип*, *T*, *U*\
Тип, поддерживающий бинарный `operator*`, который принимает операнды указанного или выводимого типа.

*Слева*\
Левый операнд в операции умножения. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа *Type*. Специализированный шаблон выполняет точную передачу ссылочных аргументов lvalue и rvalue выводимого типа *T*.

*right*\
Правый операнд в операции умножения. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа *Type*. Специализированный шаблон выполняет точную пересылку lvalue и rvalue ссылочных аргументов выводимого типа *U*.

## <a name="return-value"></a>Возвращаемое значение

Результат `Left * Right`. Специализированный шаблон выполняет точную передачу результата типа, возвращаемого `operator*`.

## <a name="example"></a>Пример

```cpp
// functional_multiplies.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <int> v1, v2, v3 ( 6 );
   vector <int>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 1 ; i <= 6 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   int j;
   for ( j = 1 ; j <= 6 ; j++ )
   {
      v2.push_back( 3 * j );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Finding the element-wise products of the elements of v1 & v2
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      multiplies<int>( ) );

   cout << "The element-wise products of vectors V1 & v2\n are: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 2 4 6 8 10 12 )
The vector v2 = ( 3 6 9 12 15 18 )
The element-wise products of vectors V1 & v2
are: ( 6 24 54 96 150 216 )
```
