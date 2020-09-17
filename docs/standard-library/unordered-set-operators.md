---
title: Операторы &lt;unordered_set&gt;
ms.date: 11/04/2016
f1_keywords:
- unordered_set/std::operator!=
- unordered_set/std::operator==
ms.assetid: 8653eea6-12f2-4dd7-aa2f-db38a71599a0
ms.openlocfilehash: 2b77c7d8e1b159198be471fb2da0bfb1f98bab0d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215495"
---
# <a name="ltunordered_setgt-operators"></a>Операторы &lt;unordered_set&gt;

## <a name="operator"></a><a name="op_neq"></a> operator!=

Проверяет, не равен ли объект [unordered_set](../standard-library/unordered-set-class.md) в левой части объекту unordered_set в правой части.

```cpp
bool operator!=(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `unordered_set`.

*right*\
Объект типа `unordered_set`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если unordered_sets не равны; значение **`false`** , если они равны.

### <a name="remarks"></a>Примечания

Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_set. Два объекта unordered_set равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// unordered_set_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_set<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 != c2: " << (c1 != c2) << endl;
   cout << "c1 != c3: " << (c1 != c3) << endl;
   cout << "c2 != c3: " << (c2 != c3) << endl;

    return (0);
}
```

**Выходные данные:**

`c1 != c2: true`

`c1 != c3: false`

`c2 != c3: true`

## <a name="operator"></a><a name="op_eq_eq"></a> operator==

Проверяет, равен ли объект [unordered_set](../standard-library/unordered-set-class.md) в левой части объекту unordered_set в правой части.

```cpp
bool operator==(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `unordered_set`.

*right*\
Объект типа `unordered_set`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если unordered_sets равны; **`false`** если они не равны.

### <a name="remarks"></a>Примечания

Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_set. Два объекта unordered_set равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// unordered_set_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_set<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 == c2: " << (c1 == c2) << endl;
   cout << "c1 == c3: " << (c1 == c3) << endl;
   cout << "c2 == c3: " << (c2 == c3) << endl;

    return (0);
}
```

```Output
c1 == c2: false
c1 == c3: true
c2 == c3: false
```

## <a name="operator"></a><a name="op_neq_unordered_multiset"></a> operator!=

Проверяет, не равен ли объект [unordered_multiset](../standard-library/unordered-multiset-class.md) в левой части объекту unordered_multiset в правой части.

```cpp
bool operator!=(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `unordered_multiset`.

*right*\
Объект типа `unordered_multiset`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если unordered_multisets не равны; значение **`false`** , если они равны.

### <a name="remarks"></a>Примечания

Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_multiset. Два объекта unordered_multiset равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// unordered_multiset_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_multiset<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');
    c1.insert('c');

    c2.insert('c');
    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 != c2: " << (c1 != c2) << endl;
   cout << "c1 != c3: " << (c1 != c3) << endl;
   cout << "c2 != c3: " << (c2 != c3) << endl;

    return (0);
}
```

```Output
c1 != c2: true
c1 != c3: false
c2 != c3: true
```

## <a name="operator"></a><a name="op_eq_eq_unordered_multiset"></a> operator==

Проверяет, равен ли объект [unordered_multiset](../standard-library/unordered-multiset-class.md) в левой части объекту unordered_multiset в правой части.

```cpp
bool operator==(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `unordered_multiset`.

*right*\
Объект типа `unordered_multiset`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если unordered_multisets равны; **`false`** если они не равны.

### <a name="remarks"></a>Примечания

Произвольный порядок хранения элементов не влияет на сравнение объектов unordered_multiset. Два объекта unordered_multiset равны, если они имеют одинаковое число элементов и элементы в одном контейнере представляют собой перестановки элементов в другом контейнере. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// unordered_multiset_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_multiset<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');
    c1.insert('c');

    c2.insert('c');
    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 == c2: " << (c1 == c2) << endl;
   cout << "c1 == c3: " << (c1 == c3) << endl;
   cout << "c2 == c3: " << (c2 == c3) << endl;

    return (0);
}
```

```Output
c1 == c2: false
c1 == c3: true
c2 == c3: false
```
