---
title: Операторы &lt;hash_set&gt;
ms.date: 03/27/2019
f1_keywords:
- hash_set/std::operator!=
- hash_set/std::operator==
ms.assetid: 403d8e4e-0b3f-43fb-bc5a-8100c4f331c5
ms.openlocfilehash: 04b662ea260ca650fc51b17c804594fe25434f61
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845799"
---
# <a name="lthash_setgt-operators"></a>Операторы &lt;hash_set&gt;

[operator!=](#op_neq)\
[operator!= (hash_multiset)](#op_neq_hash_multiset)\
[operator==](#op_eq_eq)\
[operator== (hash_multiset)](#op_eq_eq_hash_multiset)

## <a name="operator"></a><a name="op_neq"></a> operator!=

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Проверяет неравенство объекта hash_set слева от оператора и объекта hash_set справа от оператора.

```cpp
bool operator!=(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `hash_set`.

*right*\
Объект типа `hash_set`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если hash_sets не равны; **`false`** если Hash_sets равны.

### <a name="remarks"></a>Примечания

Сравнение между объектами hash_set основывается на попарном сравнении их элементов. Два объекта hash_set равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

Элементы [<hash_map>](../standard-library/hash-map.md) и [<hash_set ](../standard-library/hash-set.md)>заголовков находятся в [пространстве имен stdext](../standard-library/stdext-namespace.md).

### <a name="example"></a>Пример

```cpp
// hash_set_op_ne.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1, hs2, hs3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hs1.insert ( i );
      hs2.insert ( i * i );
      hs3.insert ( i );
   }

   if ( hs1 != hs2 )
      cout << "The hash_sets hs1 and hs2 are not equal." << endl;
   else
      cout << "The hash_sets hs1 and hs2 are equal." << endl;

   if ( hs1 != hs3 )
      cout << "The hash_sets hs1 and hs3 are not equal." << endl;
   else
      cout << "The hash_sets hs1 and hs3 are equal." << endl;
}
```

```Output
The hash_sets hs1 and hs2 are not equal.
The hash_sets hs1 and hs3 are equal.
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator==

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Проверяет равенство объекта hash_set слева от оператора и объекта hash_set справа от оператора.

```cpp
bool operator!==(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `hash_set`.

*right*\
Объект типа `hash_set`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если hash_set слева от оператора равно hash_set с правой стороны оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Сравнение между объектами hash_set основывается на попарном сравнении их элементов. Два объекта hash_set равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// hash_set_op_eq.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 == s2 )
      cout << "The hash_sets s1 and s2 are equal." << endl;
   else
      cout << "The hash_sets s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The hash_sets s1 and s3 are equal." << endl;
   else
      cout << "The hash_sets s1 and s3 are not equal." << endl;
}
```

```Output
The hash_sets s1 and s2 are not equal.
The hash_sets s1 and s3 are equal.
```

## <a name="operator-hash_multiset"></a><a name="op_neq_hash_multiset"></a> operator!= (hash_multiset)

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Проверяет неравенство объекта hash_multiset слева от оператора и объекта hash_multiset справа от оператора.

```cpp
bool operator!=(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `hash_multiset`.

*right*\
Объект типа `hash_multiset`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если hash_multisets не равны; **`false`** если Hash_multisets равны.

### <a name="remarks"></a>Примечания

Сравнение между объектами hash_multiset основывается на попарном сравнении их элементов. Два объекта hash_multiset равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// hashset_op_ne.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1, hs2, hs3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hs1.insert ( i );
      hs2.insert ( i * i );
      hs3.insert ( i );
   }

   if ( hs1 != hs2 )
      cout << "The hash_multisets hs1 and hs2 are not equal." << endl;
   else
      cout << "The hash_multisets hs1 and hs2 are equal." << endl;

   if ( hs1 != hs3 )
      cout << "The hash_multisets hs1 and hs3 are not equal." << endl;
   else
      cout << "The hash_multisets hs1 and hs3 are equal." << endl;
}
```

```Output
The hash_multisets hs1 and hs2 are not equal.
The hash_multisets hs1 and hs3 are equal.
```

## <a name="operator-hash_multiset"></a><a name="op_eq_eq_hash_multiset"></a> operator== (hash_multiset)

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Проверяет равенство объекта hash_multiset слева от оператора и объекта hash_multiset справа от оператора.

```cpp
bool operator!==(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `hash_multiset`.

*right*\
Объект типа `hash_multiset`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если hash_multiset слева от оператора равно hash_multiset с правой стороны оператора; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Сравнение между объектами hash_multiset основывается на попарном сравнении их элементов. Два объекта hash_multiset равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// hash_multiset_op_eq.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> s1, s2, s3;
   int i;

   for ( i = 0 ; i < 3 ; i++ )
   {
      s1.insert ( i );
      s2.insert ( i * i );
      s3.insert ( i );
   }

   if ( s1 == s2 )
      cout << "The hash_multisets s1 and s2 are equal." << endl;
   else
      cout << "The hash_multisets s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The hash_multisets s1 and s2 are equal." << endl;
   else
      cout << "The hash_multisets s1 and s2 are not equal." << endl;
}
```

```Output
The hash_multisets s1 and s2 are not equal.
The hash_multisets s1 and s2 are equal.
```

## <a name="see-also"></a>См. также раздел

[<hash_set>](../standard-library/hash-set.md)
