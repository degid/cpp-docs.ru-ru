---
title: Функции &lt;numeric&gt;
description: Описывает шаблоны функций, предоставляемые заголовком &lt;numeric&gt;в C++ стандартной библиотеке.
ms.date: 10/30/2019
f1_keywords:
- numeric/std::accumulate
- numeric/std::adjacent_difference
- numeric/std::exclusive_scan
- numeric/std::gcd
- numeric/std::inclusive_scan
- numeric/std::inner_product
- numeric/std::iota
- numeric/std::lcm
- numeric/std::partial_sum
- numeric/std::reduce
- numeric/std::transform_exclusive_scan
- numeric/std::transform_inclusive_scan
- numeric/std::transform_reduce
ms.assetid: a4b0449a-c80c-4a1d-8d9f-d7fcd0058f8b
helpviewer_keywords:
- std::accumulate [C++]
- std::adjacent_difference [C++]
- std::exclusive_scan [C++]
- std::gcd [C++]
- std::inclusive_scan [C++]
- std::inner_product [C++]
- std::iota [C++]
- std::lcm [C++]
- std::partial_sum [C++]
- std::reduce [C++]
- std::transform_exclusive_scan [C++]
- std::transform_inclusive_scan [C++]
- std::transform_reduce [C++]
ms.openlocfilehash: 88a97a3d110c684090b78570077927e32541eed7
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425367"
---
# <a name="ltnumericgt-functions"></a>Функции &lt;numeric&gt;

## <a name="accumulate"></a>накапливаются

Вычисляет сумму всех элементов в указанном диапазоне, включая начальное значение, путем вычисления последовательных частичных сумм. Или, вычисление результата последовательных частичных результатов указанной бинарной операции.

```cpp
template <class InputIterator, class Type>
Type accumulate(
    InputIterator first,
    InputIterator last,
    Type init);

template <class InputIterator, class Type, class BinaryOperation>
Type accumulate(
    InputIterator first,
    InputIterator last,
    Type init,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Параметры

*первый*\
Входной итератор, обращающийся к первому элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*.

*последние*\
Входной итератор, обращающийся к последнему элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*, это одна из позиций за пределами окончательного элемента, фактически включаемого в итерационное накопление.

*инициализация*\
Начальное значение, к которому каждый элемент в свою очередь добавляется или объединяется с помощью *Binary_Op*.

*binary_op*\
Двоичная операция, применяемая к каждому элементу в указанном диапазоне и результату предыдущих приложений.

### <a name="return-value"></a>Возвращаемое значение

Сумма значений *init* и всех элементов в указанном диапазоне для первой функции шаблона или для второй функции шаблона результат применения бинарной операции *Binary_Op* вместо операции Sum, to (* PartialResult, *in_iter*), где *PartialResult* является результатом выполнения предыдущих приложений операции, а *in_iter* является итератором, указывающим на следующий элемент в диапазоне.

### <a name="remarks"></a>Примечания

Начальное значение обеспечивает правильность определенного результата, если диапазон пуст, в этом случае возвращается *init* . Бинарная операция не обязательно должна быть ассоциативной или коммутативной. Результат инициализируется начальным значением *init* , а затем *результат* = *Binary_Op*(*result*, *in_iter*) вычисляется итеративно через диапазон, где *in_iter* — это итератор, указывающий на каждый последовательный элемент в диапазоне. Диапазон должен быть допустимым, а сложность — линейной с размером диапазона. Возвращаемый тип бинарного оператора должен поддерживать преобразование в **Type**, чтобы гарантировать закрытие в ходе перебора.

### <a name="example"></a>Пример

```cpp
// numeric_accum.cpp
// compile with: /EHsc
#include <vector>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2(20);
   vector <int>::iterator iter1, iter2;

   int i;
   for (i = 1; i < 21; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   // The first member function for the accumulated sum
   int total;
   total = accumulate(v1.begin(), v1.end(), 0);

   cout << "The sum of the integers from 1 to 20 is: "
        << total << "." << endl;

   // Constructing a vector of partial sums
   int j = 0, partotal;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      partotal = accumulate(v1.begin(), iter1 + 1, 0);
      v2[j] = partotal;
      j++;
   }

   cout << "The vector of partial sums is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function for the accumulated product
   vector <int> v3, v4(10);
   vector <int>::iterator iter3, iter4;

   int s;
   for (s = 1; s < 11; s++)
   {
      v3.push_back(s);
   }

   cout << "The original vector v3 is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl;

   int ptotal;
   ptotal = accumulate(v3.begin(), v3.end(), 1, multiplies<int>());

   cout << "The product of the integers from 1 to 10 is: "
        << ptotal << "." << endl;

   // Constructing a vector of partial products
   int k = 0, ppartotal;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++) {
      ppartotal = accumulate(v3.begin(), iter3 + 1, 1, multiplies<int>());
      v4[k] = ppartotal;
      k++;
   }

   cout << "The vector of partial products is:\n ( " ;
   for (iter4 = v4.begin(); iter4 != v4.end(); iter4++)
      cout << *iter4 << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).
The sum of the integers from 1 to 20 is: 210.
The vector of partial sums is:
( 1 3 6 10 15 21 28 36 45 55 66 78 91 105 120 136 153 171 190 210 ).

The original vector v3 is:
( 1 2 3 4 5 6 7 8 9 10 ).
The product of the integers from 1 to 10 is: 3628800.
The vector of partial products is:
( 1 2 6 24 120 720 5040 40320 362880 3628800 ).
```

## <a name="adjacent_difference"></a>adjacent_difference

Вычисление последовательных различий между каждым элементом и его предшественником в диапазоне ввода. Выводит результаты в диапазон назначения. Или вычисление результата обобщенной процедуры, в которой операция Difference заменяется другой, заданной бинарной операцией.

```cpp
template <class InputIterator, class OutIterator>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIterator, class BinaryOperation>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);

template <class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 adjacent_difference(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result);

template <class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2,
class BinaryOperation>
ForwardIterator2 adjacent_difference(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Параметры

*exec*\
Политика выполнения.

*первый*\
Итератор ввода, обращающийся к первому элементу в диапазоне ввода, элементы которого необходимо отличить от соответствующих им предшественников или где с парой значений должна быть выполнена другая заданная бинарная операция.

*последние*\
Итератор ввода, обращающийся к последнему элементу в диапазоне ввода, элементы которого необходимо отличить от соответствующих им предшественников или где с парой значений должна быть выполнена другая заданная бинарная операция.

\ *результатов*
Итератор вывода, обращающийся к первому элементу в диапазоне назначения, где необходимо сохранить ряд различий или результаты определенной операции.

*binary_op*\
Бинарная операция, применяемая в обобщенной операции, которая заменяет операцию вычитания в разностной процедуре.

### <a name="return-value"></a>Возвращаемое значение

Выходной итератор, обращающийся к концу целевого диапазона: `result` + (`last` - `first`).

### <a name="remarks"></a>Примечания

*Результат* итератора вывода может быть тем же итератором *, что и у итератора*ввода, чтобы `adjacent_difference` значения могли быть вычислены на месте.

Для последовательности значений *a*1, *a*2, *a*3 во входном диапазоне первая функция-шаблон сохраняет последовательные *`adjacent_difference` значения 1*, *a*2 – *a*1, a3 *и 2 в*диапазоне назначения.

Для последовательности значений *a*1 (2, *a*3) во входном диапазоне Вторая функция *-* шаблон сохраняет последовательные *`adjacent_difference` значения 1* *, 2* *Binary_Op* *a*1, 3 *Binary_Op* *a*2 в диапазоне назначения. *a*

Бинарная операция *Binary_Op* не обязательно должна быть ассоциативной или коммутативной, так как указан порядок примененных операций.

### <a name="example"></a>Пример

```cpp
// numeric_adj_diff.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend, LIterend2;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t * t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the adjacent_differences of
   // elements in a list output to a vector
   VIterend = adjacent_difference ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "Output vector containing adjacent_differences is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the adjacent products of the elements in a list
   VIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the adjacent products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of adjacent_differences in place
   LIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "In place output adjacent_differences in list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend2 ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="exclusive_scan"></a>exclusive_scan

Вычисляет монопольную операцию суммирования по префиксу, используя `std::plus<>()` или указанный бинарный оператор для диапазона с учетом начального значения. Записывает результаты в диапазон, начиная с указанного места назначения. *Исключающая сумма префикса* означает, что *n*-й элемент ввода не включается в сумму *n*-го. Перегрузки, включающие аргумент политики выполнения, выполняются в соответствии с указанной политикой.

```cpp
template<class InputIterator, class OutputIterator, class Type>
OutputIterator exclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    Type init);

template<class InputIterator, class OutputIterator, class Type, class BinaryOperation>
OutputIterator exclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    Type init,
    BinaryOperation binary_op);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type>
ForwardIterator2 exclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    Type init);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type, class BinaryOperation>
ForwardIterator2 exclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    Type init,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Параметры

*exec*\
Политика выполнения.

*первый*\
Входной итератор, обращающийся к первому элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*.

*последние*\
Входной итератор, обращающийся к последнему элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*, это одна из позиций за пределами окончательного элемента, фактически включаемого в итерационное накопление.

\ *результатов*
Выходной итератор, обращающийся к первому элементу в диапазоне назначения, где будут храниться ряд сумм или результаты указанной операции.

*инициализация*\
Начальное значение, к которому каждый элемент в свою очередь добавляется или объединяется с помощью *Binary_Op*.

*binary_op*\
Двоичная операция, применяемая к каждому элементу в указанном диапазоне и результату предыдущих приложений.

### <a name="return-value"></a>Возвращаемое значение

Выходной итератор, обращающийся к концу целевого диапазона: *result* + (*последний* - *first*).

## <a name="gcd"></a>GCD

Вычисление наибольшего общего делителя целых чисел m и n.

```cpp
template <class M, class N>
constexpr common_type_t<M,N> gcd(M m, N n);
```

### <a name="parameters"></a>Параметры

*m*, *n*\
Значения целочисленного типа.

### <a name="return-value"></a>Возвращаемое значение

Возвращает наибольший общий делитель абсолютных значений *m* и *n*или нуль, если оба значения *m* и *n* равны нулю. Результаты не определены, если абсолютные значения *m* или *n* не могут быть представлены как значения типа `common_type_t<M,N>`.

## <a name="inclusive_scan"></a>inclusive_scan

Вычисляет включающую операцию суммирования по префиксу с помощью `std::plus<>()` или указанного бинарного оператора для диапазона с учетом начального значения. Записывает результаты в диапазон, начиная с указанного места назначения. Сумма *включающего префикса* означает, что *n*-й элемент ввода включен в сумму *n*a. Перегрузки, включающие аргумент политики выполнения, выполняются в соответствии с указанной политикой.

```cpp
template<class InputIterator, class OutputIterator>
OutputIterator inclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template<class InputIterator, class OutputIterator, class BinaryOperation>
OutputIterator inclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);

template<class InputIterator, class OutputIterator, class BinaryOperation, class Type>
OutputIterator inclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op,
    Type init);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 inclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2,
class BinaryOperation>
ForwardIterator2 inclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryOperation binary_op);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2,
class BinaryOperation, class Type>
ForwardIterator2 inclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryOperation binary_op,
    Type init);
```

### <a name="parameters"></a>Параметры

*exec*\
Политика выполнения.

*первый*\
Входной итератор, обращающийся к первому элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*.

*последние*\
Входной итератор, обращающийся к последнему элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*, это одна из позиций за пределами окончательного элемента, фактически включаемого в итерационное накопление.

\ *результатов*
Выходной итератор, обращающийся к первому элементу в диапазоне назначения, где будут храниться ряд сумм или результаты указанной операции.

*инициализация*\
Начальное значение, к которому каждый элемент в свою очередь добавляется или объединяется с помощью *Binary_Op*.

*binary_op*\
Двоичная операция, применяемая к каждому элементу в указанном диапазоне и результату предыдущих приложений.

### <a name="return-value"></a>Возвращаемое значение

Выходной итератор, обращающийся к концу целевого диапазона: *result* + (*последний* - *first*).

## <a name="inner_product"></a>inner_product

Вычисляет сумму поэлементного умножения двух диапазонов и добавляет ее к указанному начальному значению либо вычисляет результат обобщенной процедуры, где бинарные операции суммы и умножения заменены на другие указанные бинарные операции.

```cpp
template <class InputIterator1, class InputIterator2, class Type>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             init);

template <class InputIterator1, class InputIterator2, class Type, class BinaryOperation1, class BinaryOperation2>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             init,
    BinaryOperation1 binary_op1,
    BinaryOperation2 binary_op2);
```

### <a name="parameters"></a>Параметры

*first1*\
Входной итератор, адресующий первый элемент в первом диапазоне, для которого нужно вычислить внутреннее произведение или обобщенное внутреннее произведение со вторым диапазоном.

*last1*\
Входной итератор, адресующий последний элемент в первом диапазоне, для которого нужно вычислить внутреннее произведение или обобщенное внутреннее произведение со вторым диапазоном.

*first2*\
Входной итератор, адресующий первый элемент во втором диапазоне, для которого нужно вычислить внутреннее произведение или обобщенное внутреннее произведение с первым диапазоном.

*инициализация*\
Начальное значение, к которому прибавляется внутреннее произведение или обобщенное внутреннее произведение диапазонов.

*binary_op1*\
Бинарная операция, которая заменяет операцию внутреннего произведения суммирования, применяемую к поэлементным произведениям в обобщении внутреннего произведения.

*binary_op2*\
Бинарная операция, которая заменяет операцию внутреннего поэлементного произведения умножения в обобщении внутреннего произведения.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает сумму поэлементного произведения и добавляет к ней указанное начальное значение. Таким образом, для диапазонов значений *a*i и *b*i она возвращает:

*init* + (*a*1 \* *б*1) + (*a*2 \* *б*2) +... + (*a*n \* *b*n)

путем итеративной замены *init* на *init* + (*a*i \* *b*i).

Вторая функция-член возвращает:

*init* *binary_op1* (*a*1 *binary_op2* *б*1) *binary_op1* (*a*2 *binary_op2* *b*2) *binary_op1* ... *binary_op1* (*a*n *binary_op2* *б*n)

путем итеративной замены *init* на *init* *binary_op1* (*a*i *binary_op2* *b*).

### <a name="remarks"></a>Примечания

Начальное значение обеспечивает правильность определенного результата, если диапазон пуст. В этом случае возвращается *init* . Бинарные операции не должны быть ассоциативными или коммутативной. Диапазон должен быть допустимым, а сложность — линейной с размером диапазона. Возвращаемый тип бинарного оператора должен поддерживать преобразование в **Type**, чтобы гарантировать закрытие в ходе перебора.

### <a name="example"></a>Пример

```cpp
// numeric_inner_prod.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main()
{
   using namespace std;

   vector <int> v1, v2(7), v3(7);
   vector <int>::iterator iter1, iter2, iter3;

   int i;
   for (i = 1; i <= 7; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   list <int> l1, l2(7);
   list <int>::iterator lIter1, lIter2;

   int t;
   for (t = 1; t <= 7; t++)
   {
      l1.push_back(t);
   }

   cout << "The original list l1 is:\n ( " ;
   for (lIter1 = l1.begin(); lIter1 != l1.end(); lIter1++)
      cout << *lIter1 << " ";
   cout << ")." << endl;

   // The first member function for the inner product
   int inprod;
   inprod = inner_product(v1.begin(), v1.end(), l1.begin(), 0);

   cout << "The inner_product of the vector v1 and the list l1 is: "
        << inprod << "." << endl;

   // Constructing a vector of partial inner_products between v1 & l1
   int j = 0, parinprod;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++) {
      parinprod = inner_product(v1.begin(), iter1 + 1, l1.begin(), 0);
      v2[j] = parinprod;
      j++;
   }

   cout << "Vector of partial inner_products between v1 & l1 is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function used to compute
   // the product of the element-wise sums
   int inprod2;
   inprod2 = inner_product (v1.begin(), v1.end(),
      l1.begin(), 1, multiplies<int>(), plus<int>());

   cout << "The sum of the element-wise products of v1 and l1 is: "
        << inprod2 << "." << endl;

   // Constructing a vector of partial sums of element-wise products
   int k = 0, parinprod2;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      parinprod2 =
         inner_product(v1.begin(), iter1 + 1, l1.begin(), 1,
         multiplies<int>(), plus<int>());
      v3[k] = parinprod2;
      k++;
   }

   cout << "Vector of partial sums of element-wise products is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl << endl;
}
```

## <a name="iota"></a>Йота

Хранит начальное значение, начиная с первого элемента и заполняя последовательные приращения этого значения (`value++`) в каждом из элементов в интервале `[first,  last)`.

```cpp
template <class ForwardIterator, class Type>
void iota(ForwardIterator first, ForwardIterator last, Type value);
```

### <a name="parameters"></a>Параметры

*первый*\
Входной итератор, адресующий первый элемент в диапазоне для заполнения.

*последние*\
Входной итератор, адресующий последний элемент в диапазоне для заполнения.

*value*\
Начальное значение для хранения в первом элементе и последовательное приращение для последующих элементов.

### <a name="example"></a>Пример

Следующий пример показывает некоторые способы использования функции `iota` заполнением [списка](../standard-library/list.md) целых чисел, а затем заполнением [вектора](../standard-library/vector.md)`list`, так что можно будет использовать функцию [random_shuffle](../standard-library/algorithm-functions.md#random_shuffle).

```cpp
// compile by using: cl /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <numeric>
#include <list>
#include <vector>
#include <iostream>

using namespace std;

int main(void)
{
    list <int> intList(10);
    vector <list<int>::iterator> intVec(intList.size());

    // Fill the list
    iota(intList.begin(), intList.end(), 0);

    // Fill the vector with the list so we can shuffle it
    iota(intVec.begin(), intVec.end(), intList.begin());

    random_shuffle(intVec.begin(), intVec.end());

    // Output results
    cout << "Contents of the integer list: " << endl;
    for (auto i: intList) {
        cout << i << ' ';
    }
    cout << endl << endl;

    cout << "Contents of the integer list, shuffled by using a vector: " << endl;
    for (auto i: intVec) {
        cout << *i << ' ';
    }
    cout << endl;
}
```

## <a name="lcm"></a>Функция

```cpp
template <class M, class N>
constexpr common_type_t<M,N> lcm(M m, N n);
```

## <a name="partial_sum"></a>partial_sum

Вычисляет ряд сумм в диапазоне ввода из первого элемента через *n*-й элемент и сохраняет результат каждой такой суммы в *n*-й элемент диапазона назначения. Или вычисляет результат обобщенной процедуры, в которой операция Sum заменяется другой заданной бинарной операцией.

```cpp
template <class InputIterator, class OutIt>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIt, class Fn2>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Параметры

*первый*\
Итератор ввода, обращающийся к первому элементу в диапазоне, который необходимо частично суммировать или объединить в соответствии с заданной бинарной операцией.

*последние*\
Итератор ввода, обращающийся к последнему элементу в диапазоне, который необходимо частично суммировать или объединить в соответствии с указанной бинарной операцией, который расположен на одну позицию далее за последним элементом, фактически включенным в совокупности, в которой проводятся итерации.

\ *результатов*
Выходной итератор, обращающийся к первому элементу целевого диапазона для хранения ряда частичных сумм или последовательных результатов указанной бинарной операции.

*binary_op*\
Бинарная операция, применяемая в обобщенной операции, заменяющая операцию Sum в процедуре частичной суммы.

### <a name="return-value"></a>Возвращаемое значение

Выходной итератор, обращающийся к концу целевого диапазона: *result* + (*последний* - *first*).

### <a name="remarks"></a>Примечания

*Результатом* итератора вывода может быть тот же итератор, что и в *первом*итераторе ввода, чтобы можно было вычислить частичные суммы на месте.

Для *последовательности значений 1*, *a*2,... *значение*x во входном диапазоне первая функция шаблона сохраняет последовательные частичные суммы в диапазоне назначения. *N*-й элемент предоставляется (*a*1 + *a*2 + *a*3 +... + *a*n).

Для последовательности значений *a*1, *a*2, *a*3 во входном диапазоне Вторая функция-шаблон сохраняет последовательные частичные результаты в диапазоне назначения. *N*-й элемент задается ((... *((1* *Binary_Op* *a*2) *Binary_Op* *3)* *Binary_Op* ...) *Binary_Op* *a*n).

Бинарная операция *Binary_Op* не обязательно должна быть ассоциативной или коммутативной, так как указан порядок примененных операций.

### <a name="example"></a>Пример

```cpp
// numeric_partial_sum.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the partial sums of
   // elements in a list output to a vector
   VIterend = partial_sum ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "The output vector containing the partial sums is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the partial product of the elements in a list
   VIterend2 = partial_sum ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the partial products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of partial sums in place
   LIterend = partial_sum ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "The in place output partial_sum list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="reduce"></a>свести

Сокращает все элементы в указанном диапазоне (возможно, включая начальное значение), вычисляя суммы в произвольном и, возможно переставляютсям заказе. Или уменьшается путем вычисления результатов указанной бинарной операции. Перегрузки, включающие аргумент политики выполнения, выполняются в соответствии с указанной политикой.

```cpp
template<class InputIterator>
typename iterator_traits<InputIterator>::value_type reduce(
    InputIterator first,
    InputIterator last);

template<class InputIterator, class Type>
Type reduce(
    InputIterator first,
    InputIterator last,
    Type init);

template<class InputIterator, class Type, class BinaryOperation>
Type reduce(
    InputIterator first,
    InputIterator last,
    Type init,
    BinaryOperation binary_op);

template<class ExecutionPolicy, class ForwardIterator>
typename iterator_traits<ForwardIterator>::value_type reduce(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last);

template<class ExecutionPolicy, class ForwardIterator, class Type>
Type reduce(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Type init);

template<class ExecutionPolicy, class ForwardIterator, class Type, class BinaryOperation>
Type reduce(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Type init,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Параметры

*exec*\
Политика выполнения.

*первый*\
Входной итератор, обращающийся к первому элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*.

*последние*\
Входной итератор, обращающийся к последнему элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*, это одна из позиций за пределами окончательного элемента, фактически включаемого в итерационное накопление.

\ *результатов*
Выходной итератор, обращающийся к первому элементу в диапазоне назначения, где будут храниться ряд сумм или результаты указанной операции.

*инициализация*\
Начальное значение, к которому каждый элемент в свою очередь добавляется или объединяется с помощью *Binary_Op*.

*binary_op*\
Двоичная операция, применяемая к каждому элементу в указанном диапазоне и результату предыдущих приложений.

### <a name="return-value"></a>Возвращаемое значение

Результат применения *Binary_Op* или `std::plus<>()` к *init* и всем элементам в указанном диапазоне до (* PartialResult, *in_iter*), где *PartialResult* является результатом предыдущих приложений операции, а *in_iter* является итератором, указывающим на некоторый элемент в диапазоне. В перегрузках, которые не задают *init*, используемое значение *init* эквивалентно `typename iterator_traits<InputIterator>::value_type{}`.

### <a name="remarks"></a>Примечания

`reduce` поведение является недетерминированным, если *Binary_Op* не является ассоциативным и коммутативной. Поведение не определено, если *Binary_Op* изменяет любой элемент или делает недействительным любой итератор в интервале \[*первый*, *последний*] включительно.

## <a name="transform_exclusive_scan"></a>transform_exclusive_scan

Преобразует элементы диапазона с заданным унарным оператором, затем вычисляет операцию монопольной суммы по префиксу, используя `std::plus<>()` или указанный бинарный оператор для диапазона, учитывая начальное значение. Записывает результаты в диапазон, начиная с указанного места назначения. *Исключающая сумма префикса* означает, что *n*-й элемент ввода не включается в сумму *n*-го. Перегрузки, включающие аргумент политики выполнения, выполняются в соответствии с указанной политикой. Суммирование может выполняться в произвольном порядке.

```cpp
template<class InputIterator, class OutputIterator, class Type, class BinaryOperation, class UnaryOperation>
OutputIterator transform_exclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    Type init,
    BinaryOperation binary_op,
    UnaryOperation unary_op);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type, class BinaryOperation, class UnaryOperation>
ForwardIterator2 transform_exclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    Type init,
    BinaryOperation binary_op,
    UnaryOperation unary_op);
```

### <a name="parameters"></a>Параметры

*exec*\
Политика выполнения.

*первый*\
Входной итератор, обращающийся к первому элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*.

*последние*\
Входной итератор, обращающийся к последнему элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*, это одна из позиций за пределами окончательного элемента, фактически включаемого в итерационное накопление.

\ *результатов*
Выходной итератор, обращающийся к первому элементу в диапазоне назначения, где будут храниться ряд сумм или результаты указанной операции.

*инициализация*\
Начальное значение, к которому каждый элемент в свою очередь добавляется или объединяется с помощью *Binary_Op*.

*binary_op*\
Двоичная операция, применяемая к каждому элементу в указанном диапазоне и результату предыдущих приложений.

*unary_op*\
Унарная операция, применяемая к каждому элементу в указанном диапазоне.

## <a name="transform_inclusive_scan"></a>transform_inclusive_scan

Преобразует элементы диапазона с заданным унарным оператором, затем вычисляет операцию суммирования по префиксу с помощью `std::plus<>()` или указанного бинарного оператора для диапазона, учитывая начальное значение. Записывает результаты в диапазон, начиная с указанного места назначения. Сумма *включающего префикса* означает, что *n*-й элемент ввода включен в сумму *n*a. Перегрузки, включающие аргумент политики выполнения, выполняются в соответствии с указанной политикой. Суммирование может выполняться в произвольном порядке.

```cpp
template<class InputIterator, class OutputIterator, class BinaryOperation, class UnaryOperation>
OutputIterator transform_inclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op,
    UnaryOperation unary_op);

template<class InputIterator, class OutputIterator, class BinaryOperation, class UnaryOperation, class Type>
OutputIterator transform_inclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op,
    UnaryOperation unary_op,
    Type init);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class BinaryOperation, class UnaryOperation>
ForwardIterator2 transform_inclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryOperation binary_op,
    UnaryOperation unary_op);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class BinaryOperation, class UnaryOperation, class Type>
ForwardIterator2 transform_inclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryOperation binary_op,
    UnaryOperation unary_op,
    Type init);
```

### <a name="parameters"></a>Параметры

*exec*\
Политика выполнения.

*первый*\
Входной итератор, обращающийся к первому элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*.

*последние*\
Входной итератор, обращающийся к последнему элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*, это одна из позиций за пределами окончательного элемента, фактически включаемого в итерационное накопление.

\ *результатов*
Выходной итератор, обращающийся к первому элементу в диапазоне назначения, где будут храниться ряд сумм или результаты указанной операции.

*binary_op*\
Двоичная операция, применяемая к каждому элементу в указанном диапазоне и результату предыдущих приложений.

*unary_op*\
Унарная операция, применяемая к каждому элементу в указанном диапазоне.

*инициализация*\
Начальное значение, к которому каждый элемент в свою очередь добавляется или объединяется с помощью *Binary_Op*.

## <a name="transform_reduce"></a>transform_reduce

Преобразует диапазон элементов, а затем применяет функтор, который сокращает преобразованные элементы в произвольном порядке. Фактически, `transform`, за которым следует `reduce`.

```cpp
template<class InputIterator1, class InputIterator2, class Type>
Type transform_reduce(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    Type init);

template<class InputIterator1, class InputIterator2, class Type, class BinaryOperation1, class BinaryOperation2>
Type transform_reduce(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    Type init,
    BinaryOperation1 binary_op1,
    BinaryOperation2 binary_op2);

template<class InputIterator, class Type, class BinaryOperation, class UnaryOperation>
Type transform_reduce(
    InputIterator first,
    InputIterator last,
    Type init,
    BinaryOperation binary_op,
    UnaryOperation unary_op);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type>
Type transform_reduce(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    Type init);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type, class BinaryOperation1, class BinaryOperation2>
Type transform_reduce(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    Type init,
    BinaryOperation1 binary_op1,
    BinaryOperation2 binary_op2);

template<class ExecutionPolicy, class ForwardIterator, class Type, class BinaryOperation, class UnaryOperation>
Type transform_reduce(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Type init,
    BinaryOperation binary_op,
    UnaryOperation unary_op);
```

### <a name="parameters"></a>Параметры

*exec*\
Политика выполнения.

*первый*\
Входной итератор, обращающийся к первому элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*.

*first1*\
Входной итератор, обращающийся к первому элементу в диапазоне для суммирования или объединения с помощью *binary_op1*.

*последние*\
Входной итератор, обращающийся к последнему элементу в диапазоне для суммирования или объединения с помощью *Binary_Op*, это одна из позиций за пределами окончательного элемента, фактически включаемого в итерационное накопление.

*last1*\
Входной итератор, обращающийся к последнему элементу в диапазоне для суммирования или объединения с помощью *binary_op1*, это одна из позиций за пределами окончательного элемента, фактически включаемого в итерационное накопление.

\ *результатов*
Выходной итератор, обращающийся к первому элементу в диапазоне назначения, где будут храниться ряд сумм или результаты указанной операции.

*инициализация*\
Начальное значение, к которому каждый элемент в свою очередь добавляется или объединяется с помощью *Binary_Op*.

*binary_op*\
Двоичная операция, применяемая к каждому элементу в указанном диапазоне и результату предыдущих приложений.

*unary_op*\
Унарная операция, применяемая к каждому элементу в указанном диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Преобразованный и сокращенный результат.
