---
title: Операторы &lt;valarray&gt;
ms.date: 03/27/2019
f1_keywords:
- valarray/std::operator!=
- valarray/std::operator%
- valarray/std::operator&amp;
- valarray/std::operator&amp;&amp;
- valarray/std::operator&gt;
- valarray/std::operator&gt;&gt;
- valarray/std::operator&gt;=
- valarray/std::operator&lt;
- valarray/std::operator&lt;&lt;
- valarray/std::operator&lt;=
- valarray/std::operator*
- valarray/std::operator+
- valarray/std::operator-
- valarray/std::operator/
- valarray/std::operator==
- valarray/std::operator^
- valarray/std::operator|
- valarray/std::operator||
ms.assetid: 8a53562c-90ab-4eb3-85d3-ada5259d90b0
helpviewer_keywords:
- std::operator!= (valarray), std::operator&amp; (valarray)
- std::operator&amp;&amp; (valarray)
- std::operator&gt; (valarray)
- std::operator&gt;&gt; (valarray)
- std::operator&gt;= (valarray)
- std::operator&lt; (valarray)
- std::operator&lt;&lt; (valarray)
- std::operator&lt;= (valarray), std::operator== (valarray)
ms.openlocfilehash: 76eb3553090cd88cf0798b2b17bbd49906852e40
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212013"
---
# <a name="ltvalarraygt-operators"></a>Операторы &lt;valarray&gt;

## <a name="operator"></a><a name="op_neq"></a> operator!=

Проверяет, не равны ли все элементы двух одинаковых по размеру объектов valarray или не равны ли все элементы объекта valarray указанному значению.

```cpp
template <class Type>
valarray<bool>
operator!=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator!=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator!=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которых проверяются на неравенство.

*right*\
Второй из двух объектов valarray, элементы которых проверяются на неравенство.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **`true`** значение, если соответствующие элементы не равны.

- **`false`** значение, если соответствующие элементы не равны.

### <a name="remarks"></a>Примечания

Первый оператор шаблона возвращает объект класса [valarray \<bool> ](../standard-library/valarray-bool-class.md), каждый из элементов которого `I` имеет значение `left[I] != right[I]` .

Второй оператор шаблона сохраняет в элементе `I` `left[I] != right` .

Третий оператор шаблона сохраняет в элементе `I` `left != right[I]` .

### <a name="example"></a>Пример

```cpp
// valarray_op_ne.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL != vaR );
   cout << "The element-by-element result of "
        << "the not equal comparison test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the not equal comparison test is the
valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
```

## <a name="operator"></a><a name="op_mod"></a> operator

Вычисляет остаток от деления соответствующих элементов двух одинаковых по размеру объектов valarray, остаток от деления объекта valarray на указанное значение или остаток от деления указанного значения на объект valarray.

```cpp
template <class Type>
valarray<Type>
operator%(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator%(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator%(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Значение или объект valarray, который служит в качестве делимого, которое делится на другое значение или на объект valarray.

*right*\
Значение или объект valarray, который выступает в качестве делителя, на который делится другое значение или объект valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого являются остатками по элементу *влево* , разделенными *вправо*.

### <a name="example"></a>Пример

```cpp
// valarray_op_rem.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 6 ), vaR ( 6 );
   valarray<int> vaREM ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  53;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -67;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  3*i+1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaREM = ( vaL % vaR );
   cout << "The remainders from the element-by-element "
        << "division is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaREM [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 53 -67 53 -67 53 -67 ).
The initial Right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
valarray: ( 0 -3 4 -7 1 -3 ).
```

## <a name="operatoramp"></a><a name="op_amp"></a> operator&amp;

Вычисляет результат применения побитовой операции **И** между соответствующими элементами двух одинаковых по размеру объектов valarray или между объектом valarray и указанным значением типа элемента.

```cpp
template <class Type>
valarray<Type>
operator&(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator&(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator&(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которого объединяются с помощью операции "побитовое `AND`", или указанное значение типа элемента, которое объединяется с помощью этой побитовой операции с каждым элементом объекта valarray.

*right*\
Второй из двух объектов valarray, элементы которого объединяются с помощью операции "побитовое `AND`", или указанное значение типа элемента, которое объединяется с помощью этой побитовой операции с каждым элементом объекта valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляют собой сочетание побитового и *левого* и *правого*сочетания операции and.

### <a name="remarks"></a>Примечания

Побитовую операцию можно использовать только для работы с битами **`char`** и **`int`** типами данных и вариантами, а не с, **`float`** **`double`** , **longdouble**, **`void`** **`bool`** или другими, более сложными типами данных.

Побитовое `AND` имеет ту же таблицу истинности, что и логическое `AND`, но применяется к типам данных на уровне отдельных битов. Оператор [operator&&](#op_amp_amp) применяется на уровне элемента, интерпретируя все ненулевые значения как true. Результатом является объект valarray из логических значений. Побитовый `AND` [оператор&](#op_amp), напротив, может привести к появлению valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

### <a name="example"></a>Пример

```cpp
// valarray_op_bitand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaBWA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i+1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaBWA = ( vaL & vaR );
   cout << "The element-by-element result of "
        << "the bitwise operator & is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaBWA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 0 2 0 4 0 6 0 8 0 10 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the bitwise operator & is the
valarray: ( 0 0 0 0 0 4 0 0 0 8 ).
```

## <a name="operatorampamp"></a><a name="op_amp_amp"></a> operator&amp;&amp;

Вычисляет результат применения логической операции **И** между соответствующими элементами двух одинаковых по размеру объектов valarray или между объектом valarray и указанным значением типа элемента valarray.

```cpp
template <class Type>
valarray<bool>
operator&&(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator&&(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator&&(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которого объединяются с помощью операции "логическое `AND`", или указанное значение типа элемента, которое объединяется с помощью этой логической операции с каждым элементом объекта valarray.

*right*\
Второй из двух объектов valarray, элементы которого объединяются с помощью операции "логическое `AND`", или указанное значение типа элемента, которое объединяется с помощью этой логической операции с каждым элементом объекта valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого имеют тип bool и является сочетанием элемента логической `AND` операции *Left* и *right*.

### <a name="remarks"></a>Примечания

Логическое значение `ANDoperator&&` применяется на уровне элемента, подсчитывающем все ненулевые значения как true, а результат — valarray логических значений. Побитовая версия `AND` [оператора&,](#op_amp), напротив, может привести к появлению valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

### <a name="example"></a>Пример

```cpp
// valarray_op_logand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL && vaR );
   cout << "The element-by-element result of "
        << "the logical AND operator&& is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&& is the
valarray: ( 0 0 0 1 0 1 0 1 0 1 ).
```

## <a name="operatorgt"></a><a name="op_gt"></a> operator&gt;

Проверяет, что элементы одного объекта valarray больше чем элементы одинакового по размеру объекта valarray или что все элементы объекта valarray больше или меньше, чем указанное значение.

```cpp
template <class Type>
valarray<bool>
operator>(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator>(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator>(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

*right*\
Второй из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **`true`**, если *левый* элемент или значение больше соответствующего *правого* элемента или значения.

- **`false`** Если *левый* элемент или значение не больше соответствующего *правого* элемента или значения.

### <a name="remarks"></a>Примечания

Если количество элементов в двух объектах valarray не равно, результат не определен.

### <a name="example"></a>Пример

```cpp
// valarray_op_gt.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL > vaR );
   cout << "The element-by-element result of "
        << "the greater than comparison test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than comparison test is the
valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> operator&gt;=

Проверяет, больше или равны ли элементы одного valarray элементам одинакового по размеру valarray, или проверяет, больше или равны ли либо меньше или равны ли все элементы valarray указанному значению.

```cpp
template <class Type>
valarray<bool>
operator>=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator>=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator>=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

*right*\
Второй из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **`true`** Если *левый* элемент или значение больше или равно соответствующему *правому* элементу или значению.

- **`false`**, если *левый* элемент или значение меньше соответствующего *правого* элемента или значения.

### <a name="remarks"></a>Примечания

Если количество элементов в двух объектах valarray не равно, результат не определен.

### <a name="example"></a>Пример

```cpp
// valarray_op_ge.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL >= vaR );
   cout << "The element-by-element result of "
        << "the greater than or equal test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than or equal test is the
valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
```

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a> operator&gt;&gt;

Сдвигает вправо биты для каждого элемента valarray на указанное число позиций или на поэлементную сумму, указанную вторым valarray.

```cpp
template <class Type>
valarray<Type>
operator>>(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator>>(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator>>(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Значение для сдвига или объект valarray, элементы которого будут сдвигаться.

*right*\
Значение, которое указывает количество позиций для сдвига вправо, или объект valarray, элементы которого указывают поэлементное количество позиций для сдвига вправо.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого были сдвинуты вправо указанное на количество позиций.

### <a name="remarks"></a>Примечания

Для чисел со знаком их знак сохраняется.

### <a name="example"></a>Пример

```cpp
// valarray_op_rs.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  64;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -64;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL >> vaR );
   cout << "The element-by-element result of "
        << "the right shift is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
```

## <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

Проверяет, меньше ли элементы одного valarray, чем элементы одинакового по размеру valarray или больше ли либо меньше ли все элементы valarray, чем указанное значение.

```cpp
template <class Type>
valarray<bool>
operator<(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator<(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator<(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

*right*\
Второй из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **`true`**, если *левый* элемент или значение меньше соответствующего *правого* элемента или значения.

- **`false`** Если *левый* элемент или значение не меньше соответствующего *правого* элемента или значения.

### <a name="remarks"></a>Примечания

Если количество элементов в двух объектах valarray не равно, результат не определен.

### <a name="example"></a>Пример

```cpp
// valarray_op_lt.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL < vaR );
   cout << "The element-by-element result of "
        << "the less-than comparson test is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the less-than comparson test is the
valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> operator&lt;=

Проверяет, меньше или равны ли элементы одного valarray элементам одинакового по размеру valarray, или проверяет, больше или равны ли либо меньше или равны ли все элементы valarray указанному значению.

```cpp
template <class Type>
valarray<bool>
operator<=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator<=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator<=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

*right*\
Второй из двух объектов valarray, элементы которого будут участвовать в сравнении, или указанное значение, которое будет сравниваться с каждым элементом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **`true`** Если *левый* элемент или значение меньше или равно соответствующему *правому* элементу или значению.

- **`false`**, если *левый* элемент или значение больше соответствующего *правого* элемента или значения.

### <a name="remarks"></a>Примечания

Если количество элементов в двух объектах valarray не равно, результат не определен.

### <a name="example"></a>Пример

```cpp
// valarray_op_le.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL <= vaR );
   cout << "The element-by-element result of "
        << "the less than or equal test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the less than or equal test is the
valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
```

## <a name="operatorltlt"></a><a name="op_lt_lt"></a> operator&lt;&lt;

Сдвигает влево биты для каждого элемента valarray на указанное число позиций или на поэлементную сумму, указанную вторым valarray.

```cpp
template <class Type>
valarray<Type>
operator<<(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator<<(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator<<(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Значение для сдвига или объект valarray, элементы которого будут сдвигаться.

*right*\
Значение, которое указывает количество позиций для сдвига влево, или объект valarray, элементы которого указывают поэлементное количество позиций для сдвига влево.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого были сдвинуты влево указанное на количество позиций.

### <a name="remarks"></a>Примечания

Для чисел со знаком их знак сохраняется.

### <a name="example"></a>Пример

```cpp
// valarray_op_ls.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL << vaR );
   cout << "The element-by-element result of "
        << "the left shift is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift is the
valarray: ( 1 -2 4 -8 16 -32 64 -128 ).
```

## <a name="operator"></a><a name="op_star"></a> operator

Вычисляет результат поэлементного умножения для двух одинаковых по размеру объектов valarray или результат умножения объекта valarray на указанное значение.

```cpp
template <class Type>
valarray<Type>
operator*(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator*(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator*(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которого будут участвовать в умножении, или указанное значение, которое будет умножаться на каждый элемент valarray.

*right*\
Второй из двух объектов valarray, элементы которого будут участвовать в умножении, или указанное значение, которое будет умножаться на каждый элемент valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого являются поэлементным продуктом *слева* и *справа*.

### <a name="example"></a>Пример

```cpp
// valarray_op_eprod.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL * vaR );
   cout << "The element-by-element result of "
        << "the multiplication is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the multiplication is the
valarray: ( 0 -1 4 -3 8 -5 12 -7 ).
```

## <a name="operator"></a><a name="op_add"></a> operator+

Вычисляет поэлементную сумму для двух одинаковых по размеру объектов valarray или результат сложения объекта valarray с указанным значением.

```cpp
template <class Type>
valarray<Type>
operator+(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator+(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator+(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которого будут участвовать в сложении, или указанное значение, которое будет складываться с каждым элементом valarray.

*right*\
Второй из двух объектов valarray, элементы которого будут участвовать в сложении, или указанное значение, которое будет складываться с каждым элементом valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого являются суммой значений *Left* и *right*на уровне элементов.

### <a name="example"></a>Пример

```cpp
// valarray_op_esum.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL + vaR );
   cout << "The element-by-element result of "
        << "the sum is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
valarray: ( 2 0 4 2 6 4 8 6 ).
```

## <a name="operator-"></a><a name="operator-"></a> operator

Вычисляет поэлементную разность для двух одинаковых по размеру объектов valarray или разность между объектом valarray и указанным значением.

```cpp
template <class Type>
valarray<Type>
operator-(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator-(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator-(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Значение или объект valarray, который выступает в качестве уменьшаемого, из которого вычитаются другие значения или объекты valarray.

*right*\
Значение или объект valarray, который выступает в качестве вычитаемого и вычитается из других значений или объектов valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляют собой разность элементов *Left* и *right*.

### <a name="remarks"></a>Примечания

Арифметическая терминология, используемая в описании вычитания:

разность = уменьшаемое - вычитаемое

### <a name="example"></a>Пример

```cpp
// valarray_op_ediff.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  10;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL - vaR );
   cout << "The element-by-element result of "
        << "the difference is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
```

## <a name="operator"></a><a name="op_div"></a> operator

Вычисляет результат поэлементного деления для двух одинаковых по размеру объектов valarray или результат деления объекта valarray на указанное значение.

```cpp
template <class Type>
valarray<Type>
operator/(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator/(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator/(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Значение или объект valarray, который служит в качестве делимого, которое делится на другое значение или на объект valarray для формирования частного.

*right*\
Значение или объект valarray, который выступает в качестве делителя, на который делится другое значение или объект valarray для формирования частного.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляют собой частное от *левого* края элементного частного *деления.*

### <a name="remarks"></a>Примечания

Арифметическая терминология, используемая в описании деления:

частное = делимое / делитель

### <a name="example"></a>Пример

```cpp
// valarray_op_equo.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<double> vaL ( 6 ), vaR ( 6 );
   valarray<double> vaNE ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  100;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -100;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  2*i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL / vaR );
   cout << "The element-by-element result of "
        << "the quotient is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
valarray: ( inf -50 25 -16.6667 12.5 -10 ).
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator==

Проверяет, равны ли все элементы двух одинаковых по размеру объектов valarray или равны ли все элементы объекта valarray указанному значению.

```cpp
template <class Type>
valarray<bool>
operator==(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator==(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator==(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которых проверяются на равенство.

*right*\
Второй из двух объектов valarray, элементы которых проверяются на равенство.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, состоящий из логических элементов, каждый из которых имеет значение:

- **`true`** значение, если соответствующие элементы равны.

- **`false`** значение, если соответствующие элементы не равны.

### <a name="remarks"></a>Примечания

Первый оператор шаблона возвращает объект класса [valarray \<bool> ](../standard-library/valarray-bool-class.md), каждый из элементов которого `I` имеет значение `left[I] == right[I]` . Второй оператор шаблона сохраняет в элементе `I` `left[I] == right` . Третий оператор шаблона сохраняет в элементе `I` `left == right[I]` .

### <a name="example"></a>Пример

```cpp
// valarray_op_eq.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL == vaR );
   cout << "The element-by-element result of "
        << "the equality comparison test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the equality comparison test is the
valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
```

## <a name="operator"></a><a name="op_xor"></a>Оператор ^

Вычисляет результат применения побитовой операции исключающего `OR`**ИЛИ** между соответствующими элементами двух одинаковых по размеру объектов valarray или между объектом valarray и указанным значением типа элемента.

```cpp
template <class Type>
valarray<Type>
operator^(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator^(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator^(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которого объединяются с помощью операции "исключающее **ИЛИ**", или указанное значение типа элемента, которое объединяется с помощью операции "исключающее ИЛИ" с каждым элементом объекта valarray.

*right*\
Второй из двух объектов valarray, элементы которого объединяются с помощью операции "исключающее **ИЛИ**", или указанное значение типа элемента, которое объединяется с помощью операции "исключающее ИЛИ" с каждым элементом объекта valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого являются поэлементным сочетанием побитовой операции **XOR** *Left* и *right*.

### <a name="remarks"></a>Примечания

Побитовую операцию можно использовать только для работы с битами **`char`** и **`int`** типами данных и вариантами, а не с,,, **`float`** **`double`** **`long double`** **`void`** **`bool`** или другими, более сложными типами данных.

Побитовое исключающее `OR` ( **XOR**) имеет следующую семантику: заданный бит *b*1 и *b*2, *b*1 **XOR** *b*2 имеет **`true`** значение true, если только один из битов равен false, или если оба бита имеют значение **`false`** true.

### <a name="example"></a>Пример

```cpp
// valarray_op_xor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL ^ vaR );
   cout << "The element-by-element result of "
        << "the bitwise XOR operator^ is the\n"
        << "valarray: ( ";
           for ( i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^ is the
valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
```

## <a name="operator124"></a><a name="op_or"></a>Оператор&#124;

Получает результат применения побитовой операции `OR` между соответствующими элементами двух одинаковых по размеру valarray или valarray и указанного значения типа элемента.

```cpp
template <class Type>
valarray<Type>
operator|(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator|(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator|(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которого объединяются с помощью операции "побитовое `OR`", или указанное значение типа элемента, которое объединяется с помощью этой побитовой операции с каждым элементом объекта valarray.

*right*\
Второй из двух объектов valarray, элементы которого объединяются с помощью операции "побитовое `OR`", или указанное значение типа элемента, которое объединяется с помощью этой побитовой операции с каждым элементом объекта valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого представляют собой сочетание побитовой `OR` операции *Left* и *right*в элементе.

### <a name="remarks"></a>Примечания

Побитовую операцию можно использовать только для работы с битами **`char`** и **`int`** типами данных и вариантами, а не с, **`float`** **`double`** , **longdouble**, **`void`** **`bool`** или другими, более сложными типами данных.

Побитовое "ИЛИ" имеет ту же таблицу истинности, что и логическое `OR` , но применяется к типам данных на уровне отдельных битов. В заданных битах *b*1 и *b*2, *b*1 `OR` *b*2, **`true`** Если хотя бы один из битов имеет значение true или **`false`** Если оба бита имеют значение false. Логический `OR` [оператор&#124;&#124;](../standard-library/valarray-operators.md#op_lor) применяется к уровню элемента, подсчитывает все ненулевые значения как **`true`** , а результат — valarray из логических значений. Применение оператора побитового "ИЛИ" `operator|`, напротив, может привести к появлению в объекте valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

### <a name="example"></a>Пример

```cpp
// valarray_op_bitor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial Left valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL | vaR );
   cout << "The element-by-element result of "
        << "the bitwise OR operator| is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise OR operator| is the
valarray: ( 1 0 1 3 3 4 7 6 7 9 ).
```

## <a name="operator124124"></a><a name="op_lor"></a>Оператор&#124;&#124;

Вычисляет результат применения логической операции `OR` между соответствующими элементами двух одинаковых по размеру объектов valarray или между объектом valarray и указанным значением типа элемента valarray.

```cpp
template <class Type>
valarray<bool>
operator||(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator||(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator||(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Первый из двух объектов valarray, элементы которого объединяются с помощью операции "логическое `OR`", или указанное значение типа элемента, которое объединяется с помощью этой логической операции с каждым элементом объекта valarray.

*right*\
Второй из двух объектов valarray, элементы которого объединяются с помощью операции "логическое `OR`", или указанное значение типа элемента, которое объединяется с помощью этой логической операции с каждым элементом объекта valarray.

### <a name="return-value"></a>Возвращаемое значение

Объект valarray, элементы которого имеют тип **`bool`** и являются сочетанием логической операции OR ( *слева* и *справа*) для элемента.

### <a name="remarks"></a>Примечания

Логическое значение `OR` `operator||` применяется на уровне элемента, считая все ненулевые значения как **`true`** , а результатом является valarray значений типа Boolean. Применение оператора побитового `OR`, [operator|](../standard-library/valarray-operators.md#op_or), напротив, может привести к появлению в объекте valarray значений, отличных от 0 или 1, в зависимости от результата побитовой операции.

### <a name="example"></a>Пример

```cpp
// valarray_op_logor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaLOR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  0;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  0;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLOR = ( vaL || vaR );
   cout << "The element-by-element result of "
        << "the logical OR operator|| is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaLOR [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 0 0 3 0 0 6 0 0 9 ).
The element-by-element result of the logical OR operator|| is the
valarray: ( 0 0 0 1 0 1 1 1 0 1 ).
```
