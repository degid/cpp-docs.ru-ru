---
title: Класс slice
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice
- valarray/std::slice::size
- valarray/std::slice::start
- valarray/std::slice::stride
helpviewer_keywords:
- std::slice [C++]
- std::slice [C++], size
- std::slice [C++], start
- std::slice [C++], stride
ms.assetid: 00f0b03d-d657-4b81-ba53-5a9034bb2bf2
ms.openlocfilehash: 05f87cbb6061e205f9731d2a903ce52a2482b214
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336721"
---
# <a name="slice-class"></a>Класс slice

Служебный класс, используемый для определения одномерных подмножеств родительского valarray. Если valarray рассматривается как двухмерная матрица со всеми элементами в массиве, срез извлекает одномерный вектор из двухмерного массива.

## <a name="remarks"></a>Примечания

Класс хранит параметры, характеризующие объект типа [slice_array](../standard-library/slice-array-class.md). Подмножество valarray косвенно создается, когда объект среза класса отображается как аргумент для объекта класса [valarray](../standard-library/valarray-class.md#op_at)**\<Type>**. Хранимые значения, задающие подмножество, выбираемое из родительского valarray, включают:

- начальный индекс в valarray;

- общую длину среза или количество элементов в нем;

- полный шаг или расстояние между последовательными индексами элементов в valarray.

Если набор, определенный при помощи среза, — подмножество постоянного valarray, то этот срез — новый valarray. Если набор, определенный при помощи среза, — подмножество постоянного valarray, то этот срез имеет семантику ссылки для исходного valarray. Механизм оценки для неконстантных valarray экономит время и память.

Операции над valarray гарантируются только в том случае, если исходное и конечное подмножества, определенные при помощи среза, различаются, а все индексы являются допустимыми.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[Ломтик](#slice)|Определяет подмножество `valarray`, состоящее из нескольких элементов, которые находятся на одинаковом расстоянии друг от друга и начинаются с указанного элемента.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Размер](#size)|Определяет число элементов в срезе `valarray`.|
|[Начать](#start)|Находит начальный индекс среза `valarray`.|
|[Шаг](#stride)|Находит расстояние между элементами в срезе `valarray`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<valarray>

**Пространство имен:** std

## <a name="slicesize"></a><a name="size"></a>ломтик:размер

Определяет число элементов в срезе valarray.

```cpp
size_t size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в срезе valarray.

### <a name="example"></a>Пример

```cpp
// slice_size.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   size_t sizeVA, sizeVAR;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i += 1 )
      va [ i ] =  i+1;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   sizeVA = va.size ( );
   cout << "The size of the valarray is: "
        << sizeVA << "." << endl << endl;

   slice vaSlice ( 3 , 6 , 3 );
   vaResult = va [ vaSlice ];

   cout << "The slice of valarray va is vaResult = "
        << "va[slice( 3, 6, 3)] =\n ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   sizeVAR = vaSlice.size ( );
   cout << "The size of slice vaSlice is: "
        << sizeVAR << "." << endl;
}
```

```Output
The operand valarray va is:
( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).
The size of the valarray is: 20.

The slice of valarray va is vaResult = va[slice( 3, 6, 3)] =
( 4 7 10 13 16 19 ).
The size of slice vaSlice is: 6.
```

## <a name="sliceslice"></a><a name="slice"></a>ломтик::срез

Определяет подмножество valarray, состоящее из нескольких элементов, которые находятся на одинаковом расстоянии друг от друга и начинаются с указанного элемента.

```cpp
slice();

slice(
    size_t _StartIndex,
    size_t _Len,
    size_t stride);
```

### <a name="parameters"></a>Параметры

*_StartIndex*\
Индекс valarray первого элемента в подмножестве.

*_Len*\
Количество элементов в подмножестве.

*Шаг*\
Расстояние между элементами в подмножестве.

### <a name="return-value"></a>Возвращаемое значение

Конструктор по умолчанию хранит нули для начального индекса, общей длины и полного шага. Второй конструктор хранит *_StartIndex* для стартового индекса, *_Len* для общей длины, и *шаг* для шага.

### <a name="remarks"></a>Примечания

Полный шаг может быть отрицательным.

### <a name="example"></a>Пример

```cpp
// slice_ctor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  2 * (i + 1 );

   cout << "The operand valarray va is:\n( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   slice vaSlice ( 1 , 7 , 3 );
   vaResult = va [ vaSlice ];

   cout << "\nThe slice of valarray va is vaResult:"
        << "\nva[slice( 1, 7, 3)] = ( ";
      for ( i = 0 ; i < 7 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The operand valarray va is:
( 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 ).

The slice of valarray va is vaResult:
va[slice( 1, 7, 3)] = ( 4 10 16 22 28 34 40 ).
```

## <a name="slicestart"></a><a name="start"></a>ломтик::начало

Находит начальный индекс среза valarray.

```cpp
size_t start() const;
```

### <a name="return-value"></a>Возвращаемое значение

Начальный индекс среза valarray.

### <a name="example"></a>Пример

```cpp
// slice_start.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   size_t startVAR;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i += 1 )
      va [ i ] = i+1;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   slice vaSlice ( 3 , 6 , 3 );
   vaResult = va [ vaSlice ];

   cout << "The slice of valarray va is vaResult = "
        << "va[slice( 3, 6, 3)] =\n ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   startVAR = vaSlice.start ( );
   cout << "The start index of slice vaSlice is: "
        << startVAR << "." << endl;
}
```

```Output
The operand valarray va is:
( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).
The slice of valarray va is vaResult = va[slice( 3, 6, 3)] =
( 4 7 10 13 16 19 ).
The start index of slice vaSlice is: 3.
```

## <a name="slicestride"></a><a name="stride"></a>ломтик::шаг

Находит расстояние между элементами в срезе valarray.

```cpp
size_t stride() const;
```

### <a name="return-value"></a>Возвращаемое значение

Расстояние между элементами в срезе valarray.

### <a name="example"></a>Пример

```cpp
// slice_stride.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   size_t strideVAR;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i += 1 )
      va [ i ] =  3 * ( i + 1 );

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   slice vaSlice ( 4 , 5 , 3 );
   vaResult = va [ vaSlice ];

   cout << "The slice of valarray va is vaResult = "
        << "va[slice( 4, 5, 3)] =\n ( ";
      for ( i = 0 ; i < 5 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   strideVAR = vaSlice.stride ( );
   cout << "The stride of slice vaSlice is: "
        << strideVAR << "." << endl;
}
```

```Output
The operand valarray va is:
( 3 6 9 12 15 18 21 24 27 30 33 36 39 42 45 48 51 54 57 60 ).
The slice of valarray va is vaResult = va[slice( 4, 5, 3)] =
( 15 24 33 42 51 ).
The stride of slice vaSlice is: 3.
```

## <a name="see-also"></a>См. также раздел

[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
