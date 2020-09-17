---
title: Операторы &lt;stack&gt;
ms.date: 11/04/2016
f1_keywords:
- stack/std::operator!=
- stack/std::operator&gt;
- stack/std::operator&gt;=
- stack/std::operator&lt;
- stack/std::operator&lt;=
- stack/std::operator==
ms.assetid: 9c1fc282-2f61-4727-9e80-84ea5d4934a2
helpviewer_keywords:
- std::operator!= (stack)
- std::operator&gt; (stack)
- std::operator&gt;= (stack)
- std::operator&lt; (stack)
- std::operator&lt;= (stack)
- std::operator== (stack)
ms.openlocfilehash: ac694e517279e43a501bb8289544e5da5ddba72b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217419"
---
# <a name="ltstackgt-operators"></a>Операторы &lt;stack&gt;

## <a name="operator"></a><a name="op_neq"></a> operator!=

Проверяет, не равен ли объект стека слева от оператора объекту стека справа от оператора.

```cpp
bool operator!=(const stack <Type, Container>& left, const stack <Type, Container>& right,);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `stack`.

*right*\
Объект типа `stack`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если стеки или стеки не равны; значение **`false`** , если стеки или стеки равны.

### <a name="remarks"></a>Примечания

Сравнение между объектами стеков основывается на попарном сравнении элементов этих стеков. Два стека равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// stack_op_me.cpp
// compile with: /EHsc
#include <stack>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with vector base containers
   stack <int, vector<int> > s1, s2, s3;

   // The following would have cause an error because stacks with
   // different base containers are not equality comparable
   // stack <int, list<int> >  s3;

   s1.push( 1 );
   s2.push( 2 );
   s3.push( 1 );

   if ( s1 != s2 )
      cout << "The stacks s1 and s2 are not equal." << endl;
   else
      cout << "The stacks s1 and s2 are equal." << endl;

   if ( s1 != s3 )
      cout << "The stacks s1 and s3 are not equal." << endl;
   else
      cout << "The stacks s1 and s3 are equal." << endl;
}
```

```Output
The stacks s1 and s2 are not equal.
The stacks s1 and s3 are equal.
```

## <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

Проверяет, меньше ли объект стека слева от оператора объекта стека справа от оператора.

```cpp
bool operator<(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `stack`.

*right*\
Объект типа `stack`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если стек слева от оператора меньше и не равен стеку в правой части оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Сравнение между объектами стеков основывается на попарном сравнении элементов этих списков. Отношение "меньше" между двумя объектами стека основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// stack_op_lt.cpp
// compile with: /EHsc
#include <stack>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with list base container
   stack <int, list<int> > s1, s2, s3;

   s1.push( 2 );
   s1.push( 4 );
   s1.push( 6 );
   s1.push( 8 );
   s2.push( 5 );
   s2.push( 10 );
   s3.push( 2 );
   s3.push( 4 );
   s3.push( 6 );
   s3.push( 8 );

   if ( s1 >= s2 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s2." << endl;

   if ( s1>= s3 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s3." << endl;

   // to print out the stack s1 ( by unstacking the elements):
   stack <int>::size_type i_size_s1 = s1.size( );
   cout << "The stack s1 from the top down is: ( ";
   unsigned int i;
   for ( i = 1 ; i <= i_size_s1 ; i++ )
   {
      cout << s1.top( ) << " ";
      s1.pop( );
   }
   cout << ")." << endl;
}
```

```Output
The stack s1 is less than the stack s2.
The stack s1 is greater than or equal to the stack s3.
The stack s1 from the top down is: ( 8 6 4 2 ).
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> operator&lt;=

Проверяет, меньше или равен ли объект стека слева от оператора объекту стека справа от оператора.

```cpp
bool operator<=(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `stack`.

*right*\
Объект типа `stack`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если стек слева от оператора меньше или равен стеку в правой части оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Сравнение между объектами стеков основывается на попарном сравнении элементов этих списков. Отношение "меньше или равно" между двумя объектами стеков основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// stack_op_le.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with default deque base container
   stack <int> s1, s2, s3;

   s1.push( 5 );
   s1.push( 10 );
   s2.push( 1 );
   s2.push( 2 );
   s3.push( 5 );
   s3.push( 10 );

   if ( s1 <= s2 )
      cout << "The stack s1 is less than or equal to "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is greater than "
           << "the stack s2." << endl;

   if ( s1 <= s3 )
      cout << "The stack s1 is less than or equal to "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is greater than "
           << "the stack s3." << endl;
}
```

```Output
The stack s1 is greater than the stack s2.
The stack s1 is less than or equal to the stack s3.
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator==

Проверяет, равен ли объект стека слева от оператора объекту стека справа от оператора.

```cpp
bool operator==(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `stack`.

*right*\
Объект типа `stack`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если стеки или стеки равны; значение **`false`** , если стеки или стеки не равны.

### <a name="remarks"></a>Примечания

Сравнение между объектами стеков основывается на попарном сравнении элементов этих списков. Два стека равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// stack_op_eq.cpp
// compile with: /EHsc
#include <stack>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with vector base containers
   stack <int, vector<int> > s1, s2, s3;

   // The following would have cause an error because stacks with
   // different base containers are not equality comparable
   // stack <int, list<int> > s3;

   s1.push( 1 );
   s2.push( 2 );
   s3.push( 1 );

   if ( s1 == s2 )
      cout << "The stacks s1 and s2 are equal." << endl;
   else
      cout << "The stacks s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The stacks s1 and s3 are equal." << endl;
   else
      cout << "The stacks s1 and s3 are not equal." << endl;
}
```

```Output
The stacks s1 and s2 are not equal.
The stacks s1 and s3 are equal.
```

## <a name="operatorgt"></a><a name="op_gt"></a> operator&gt;

Проверяет, больше ли объект стека слева от оператора объекта стека справа от оператора.

```cpp
bool operator>(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `stack`.

*right*\
Объект типа `stack`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если стек слева от оператора больше и не равен стеку в правой части оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Сравнение между объектами стеков основывается на попарном сравнении элементов этих списков. Отношение "больше" между двумя объектами стеков основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// stack_op_gt.cpp
// compile with: /EHsc
#include <stack>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with list base container
   stack <int, list<int> > s1, s2, s3;

   s1.push( 1 );
   s1.push( 2 );
   s1.push( 3 );
   s2.push( 5 );
   s2.push( 10 );
   s3.push( 1 );
   s3.push( 2 );

   if ( s1 > s2 )
      cout << "The stack s1 is greater than "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is not greater than "
           << "the stack s2." << endl;

   if ( s1> s3 )
      cout << "The stack s1 is greater than "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is not greater than "
           << "the stack s3." << endl;
}
```

```Output
The stack s1 is not greater than the stack s2.
The stack s1 is greater than the stack s3.
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> operator&gt;=

Проверяет, больше или равен ли объект стека слева от оператора объекту стека справа от оператора.

```cpp
bool operator>=(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `stack`.

*right*\
Объект типа `stack`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если стек слева от оператора строго меньше стека в правой части оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Сравнение между объектами стеков основывается на попарном сравнении элементов этих списков. Отношение "больше или равно" между двумя объектами стеков основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// stack_op_ge.cpp
// compile with: /EHsc
#include <stack>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with list base container
   stack <int, list<int> > s1, s2, s3;

   s1.push( 1 );
   s1.push( 2 );
   s2.push( 5 );
   s2.push( 10 );
   s3.push( 1 );
   s3.push( 2 );

   if ( s1 >= s2 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s2." << endl;

   if ( s1>= s3 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s3." << endl;
}
```

```Output
The stack s1 is less than the stack s2.
The stack s1 is greater than or equal to the stack s3.
```
