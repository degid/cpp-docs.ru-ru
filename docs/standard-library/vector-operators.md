---
title: Операторы &lt;vector&gt;
ms.date: 11/04/2016
f1_keywords:
- vector/std::operator!=
- vector/std::operator&gt;
- vector/std::operator&gt;=
- vector/std::operator&lt;
- vector/std::operator&lt;=
- vector/std::operator==
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
helpviewer_keywords:
- std::operator!= (vector)
- std::operator&gt; (vector)
- std::operator&gt;= (vector)
- std::operator&lt; (vector)
- std::operator&lt;= (vector)
- std::operator== (vector)
ms.openlocfilehash: 6e3b78a7b7176be917da5a3e44e9bf54efc0b08c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224543"
---
# <a name="ltvectorgt-operators"></a>Операторы &lt;vector&gt;

## <a name="operator"></a><a name="op_neq"></a> operator!=

Проверяет неравенство объекта слева от оператора объекту справа от оператора.

```cpp
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `vector`.

*right*\
Объект типа `vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если векторы не равны; **`false`** значение, если векторы равны.

### <a name="remarks"></a>Примечания

Два объекта vector равны, если они содержат одинаковое количество элементов и соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// vector_op_ne.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
     v2.push_back( 2 );

   if ( v1 != v2 )
      cout << "Vectors not equal." << endl;
   else
      cout << "Vectors equal." << endl;
}
```

```Output
Vectors not equal.
```

## <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

Проверяет, что объект слева от оператора меньше, чем объект справа от оператора.

```cpp
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `vector`.

*right*\
Объект типа `vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если вектор слева от оператора меньше вектора в правой части оператора; в противном случае — значение **`false`** .

### <a name="example"></a>Пример

```cpp
// vector_op_lt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 < v2 )
      cout << "Vector v1 is less than vector v2." << endl;
   else
      cout << "Vector v1 is not less than vector v2." << endl;
}
```

```Output
Vector v1 is less than vector v2.
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> operator&lt;=

Проверяет, что объект слева от оператора меньше или равен объекту справа от оператора.

```cpp
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `vector`.

*right*\
Объект типа `vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если вектор слева от оператора меньше или равен вектору в правой части оператора; в противном случае — значение **`false`** .

### <a name="example"></a>Пример

```cpp
// vector_op_le.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 <= v2 )
      cout << "Vector v1 is less than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is greater than vector v2." << endl;
}
```

```Output
Vector v1 is less than or equal to vector v2.
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator==

Проверяет равенство объекта слева от оператора объекту справа от оператора.

```cpp
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `vector`.

*right*\
Объект типа `vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если вектор слева от оператора равен вектору в правой части оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Два объекта vector равны, если они содержат одинаковое количество элементов и соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// vector_op_eq.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v2.push_back( 1 );

   if ( v1 == v2 )
      cout << "Vectors equal." << endl;
   else
      cout << "Vectors not equal." << endl;
}
```

```Output
Vectors equal.
```

## <a name="operatorgt"></a><a name="op_gt"></a> operator&gt;

Проверяет, что объект слева от оператора больше, чем объект справа от оператора.

```cpp
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `vector`.

*right*\
Объект типа `vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если вектор в левой части оператора больше вектора справа от оператора; в противном случае — значение **`false`** .

### <a name="example"></a>Пример

```cpp
// vector_op_gt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

   v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 > v2 )
      cout << "Vector v1 is greater than vector v2." << endl;
   else
      cout << "Vector v1 is not greater than vector v2." << endl;
}
```

```Output
Vector v1 is greater than vector v2.
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> operator&gt;=

Проверяет, что объект слева от оператора больше или равен объекту справа от оператора.

```cpp
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `vector`.

*right*\
Объект типа `vector`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если вектор слева от оператора больше или равен вектору в правой части вектора; в противном случае — значение **`false`** .

### <a name="example"></a>Пример

```cpp
// vector_op_ge.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

     v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 >= v2 )
      cout << "Vector v1 is greater than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is less than vector v2." << endl;
}
```

```Output
Vector v1 is greater than or equal to vector v2.
```
