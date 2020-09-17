---
title: Класс gslice
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice
- valarray/std::gslice::size
- valarray/std::gslice::start
- valarray/std::gslice::stride
helpviewer_keywords:
- std::gslice [C++]
- std::gslice [C++], size
- std::gslice [C++], start
- std::gslice [C++], stride
ms.assetid: f47cffd0-ea59-4b13-848b-7a5ce1d7e2a3
ms.openlocfilehash: 07c987fb08a213bb66da628bec3021a3bf9ba24a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370624"
---
# <a name="gslice-class"></a>Класс gslice

Служебный класс, используемый для определения многомерных подмножеств valarray. Если valarray рассматривается как многомерная матрица со всеми элементами в массиве, срез извлекает вектор из многомерного массива.

## <a name="remarks"></a>Примечания

Класс хранит параметры, характеризующие объект типа [gslice_array](../standard-library/gslice-array-class.md). Подмножество valarray косвенно построено, когда объект class gslice отображается в качестве аргумента для объекта типа [valarray](../standard-library/valarray-class.md#op_at)**\<Type>. ** Хранимые значения, задающие подмножество, выбираемое из родительского valarray, включают:

- Начальный индекс.

- Вектор длины `valarray<size_t>`класса .

- Вектором `valarray<size_t>`шага класса .

Длина обоих векторов должна быть одинаковой.

Если набор, определенный с помощью gslice, является подмножеством постоянного valarray, то gslice является новым valarray. Если набор, определенный с помощью gslice, является подмножеством постоянного valarray, то gslice является новым valarray. Механизм оценки для неконстантных valarray экономит время и память.

Операции над valarray гарантируются только в том случае, если исходное и конечное подмножества, определенные с помощью gslice, различаются, а все индексы являются допустимыми.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[gslice](#gslice)|Определяет подмножество `valarray`, состоящее из нескольких фрагментов `valarray`, начинающихся с указанного элемента.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Размер](#size)|Находит значения массива, указывающие количество элементов в общем срезе `valarray`.|
|[Начать](#start)|Находит индекс начала общего среза `valarray`.|
|[Шаг](#stride)|Находит расстояние между элементами в общем срезе `valarray`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<valarray>

**Пространство имен:** std

## <a name="gslicegslice"></a><a name="gslice"></a>gslice:gslice

Служебный класс, используемый для определения многомерных срезов valarray.

```cpp
gslice();

gslice(
    size_t _StartIndex,
    const valarray<size_t>& _LenArray,
    const valarray<size_t>& _IncArray);
```

### <a name="parameters"></a>Параметры

*_StartIndex*\
Индекс valarray первого элемента в подмножестве.

*_LenArray*\
Массив, указывающий число элементов в каждом срезе.

*_IncArray*\
Массив, указывающий шаг в каждом срезе.

### <a name="return-value"></a>Возвращаемое значение

Конструктор по умолчанию хранит нуль для начального индекса и векторы нулевой длины для векторов длины и шага. Второй конструктор хранит *_StartIndex* для стартового индекса, *_LenArray* для массива длины и *_IncArray* для массива шага.

### <a name="remarks"></a>Примечания

**gslice** определяет подмножество valarray, состоящее из нескольких срезов valarray, каждый из которых начинается с одного и того же указанного элемента. Единственным отличием между `gslice` и [slice::slice](../standard-library/slice-class.md#slice) является возможность применения массивов для определения нескольких срезов. Первый срез имеет первый элемент с индексом *_StartIndex,* ряд элементов, указанных первым элементом *_LenArray,* и шаг, данный первым элементом *_IncArray.* Следующий набор ортогональных срезов имеет первые элементы, задаваемые первом срезом. Второй элемент *_LenArray* определяет количество элементов. Шаг дается вторым элементом *_IncArray*. Третье измерение срезов будет брать элементы двумерного массива в качестве начальных элементов и продолжать аналогичным образом

### <a name="example"></a>Пример

```cpp
// gslice_ctor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:" << endl << "(";
   for ( i = 0 ; i < 20 ; i++ )
      cout << " " << va [ i ];
   cout << " )" << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];

   cout << "The valarray for vaGSlice is vaResult:" << endl
        << "va[vaGSlice] = (";

   for ( i = 0 ; i < 8 ; i++ )
      cout << " " << vaResult [ i ];
   cout << ")" << endl;
}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 )
The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19)
```

## <a name="gslicesize"></a><a name="size"></a>gslice::размер

Находит значения массива, указывающие количество элементов в общем срезе valarray.

```cpp
valarray<size_t> size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Valarray, указывающее число элементов в каждом срезе общего среза valarray.

### <a name="remarks"></a>Примечания

Функция-член возвращает сохраненные длины срезов.

### <a name="example"></a>Пример

```cpp
// gslice_size.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   size_t sizeVA;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   sizeVA = va.size ( );
   cout << "The size of the valarray is: "
        << sizeVA << "." << endl << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   const valarray <size_t> sizeGS = vaGSlice.size ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The size of vaResult is:"
        << "\n vaGSlice.size ( ) = ( ";
      for ( i = 0 ; i < 2 ; i++ )
         cout << sizeGS[ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The size of the valarray is: 20.

The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The size of vaResult is:
vaGSlice.size ( ) = ( 4 4 ).
```

## <a name="gslicestart"></a><a name="start"></a>gslice::start

Находит начальный индекс общего среза valarray.

```cpp
size_t start() const;
```

### <a name="return-value"></a>Возвращаемое значение

Начальный индекс общего среза valarray.

### <a name="example"></a>Пример

```cpp
// gslice_start.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for (i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   size_t vaGSstart = vaGSlice.start ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The index of the first element of vaResult is: "
        << vaGSstart << "." << endl;
}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The index of the first element of vaResult is: 0.
```

## <a name="gslicestride"></a><a name="stride"></a>gslice::stride

Находит расстояние между элементами в общем срезе valarray.

```cpp
valarray<size_t> stride() const;
```

### <a name="return-value"></a>Возвращаемое значение

Valarray, указывающее расстояние между элементами в каждом срезе общего среза valarray.

### <a name="example"></a>Пример

```cpp
// gslice_stride.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for (i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for (i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   const valarray <size_t> strideGS = vaGSlice.stride ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The strides of vaResult are:"
        << "\n vaGSlice.stride ( ) = ( ";
      for ( i = 0 ; i < 2 ; i++ )
         cout << strideGS[ i ] << " ";
   cout << ")." << endl;

}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The strides of vaResult are:
vaGSlice.stride ( ) = ( 7 4 ).
```

## <a name="see-also"></a>См. также раздел

[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
