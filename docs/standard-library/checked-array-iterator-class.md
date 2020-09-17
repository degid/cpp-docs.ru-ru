---
title: Класс checked_array_iterator
ms.date: 03/27/2019
f1_keywords:
- iterator/checked_array_iterator
- iterator/stdext::checked_array_iterator::difference_type
- iterator/stdext::checked_array_iterator::pointer
- iterator/stdext::checked_array_iterator::reference
- iterator/stdext::checked_array_iterator::base
helpviewer_keywords:
- stdext::checked_array_iterator [C++], difference_type
- stdext::checked_array_iterator [C++], pointer
- stdext::checked_array_iterator [C++], reference
- stdext::checked_array_iterator [C++], base
ms.assetid: 7f07185e-d588-4ae3-9c4f-84ec4aa25a28
ms.openlocfilehash: 467a94212d7b1e9d28a3229660b8a8619993b201
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684945"
---
# <a name="checked_array_iterator-class"></a>Класс checked_array_iterator

Класс `checked_array_iterator` предоставляет возможность преобразовать массив или указатель в проверенный итератор. Используйте этот класс в качестве оболочки (с помощью функции [make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator)) для необработанных указателей или массивов, как способ целенаправленного выполнения проверки и управления непроверенными предупреждениями об указателях вместо глобального отключения данных предупреждений. При необходимости можно использовать непроверенную версию данного класса, [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md).

> [!NOTE]
> Этот класс является расширением стандартной библиотеки C++, которое предоставляется Майкрософт. Код, реализованный с помощью этой функции, нельзя перенести в стандартные среды сборки C, не поддерживающие это расширение Microsoft. Пример создания кода, не требующего использования данного класса — это второй пример, представленный ниже.

## <a name="syntax"></a>Синтаксис

```cpp
template <class _Iterator>
class checked_array_iterator;
```

## <a name="remarks"></a>Примечания

Этот класс определяется в пространстве имен [stdext](../standard-library/stdext-namespace.md).

Дополнительные сведения и пример кода функции проверяемого итератора см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).

## <a name="examples"></a>Примеры

В следующем примере показано, как задать и использовать проверенный итератор массива.

Если назначение не может вместить все скопированные элементы (например, в случае изменения строки):

```cpp
copy(a, a + 5, checked_array_iterator<int*>(b, 5));
```

значение

```cpp
copy(a, a + 5, checked_array_iterator<int*>(b, 4));
```

Произойдет ошибка исполняющей среды.

```cpp
// compile with: /EHsc /W4 /MTd
#include <algorithm>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[]={0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b, 5));

   cout << "(";
   for (int i = 0 ; i < 5 ; i++)
      cout << " " << b[i];
   cout << " )" << endl;

   // constructor example
   checked_array_iterator<int*> checked_out_iter(b, 5);
   copy(a, a + 5, checked_out_iter);

   cout << "(";
   for (int i = 0 ; i < 5 ; i++)
      cout << " " << b[i];
   cout << " )" << endl;
}
/* Output:
( 0 1 2 3 4 )
( 0 1 2 3 4 )
*/
```

Чтобы исключить необходимость класса `checked_array_iterator` при использовании алгоритмов стандартной библиотеки C++, попробуйте применить `vector` вместо динамически выделяемого массива. В следующем примере показано, как это сделать.

```cpp
// compile with: /EHsc /W4 /MTd

#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    std::vector<int> v(10);
    int *arr = new int[10];
    for (int i = 0; i < 10; ++i)
    {
        v[i] = i;
        arr[i] = i;
    }

    // std::copy(v.begin(), v.end(), arr); will result in
    // warning C4996. To avoid this warning while using int *,
    // use the Microsoft extension checked_array_iterator.
    std::copy(v.begin(), v.end(),
              stdext::checked_array_iterator<int *>(arr, 10));

    // Instead of using stdext::checked_array_iterator and int *,
    // consider using std::vector to encapsulate the array. This will
    // result in no warnings, and the code will be portable.
    std::vector<int> arr2(10);    // Similar to int *arr = new int[10];
    std::copy(v.begin(), v.end(), arr2.begin());

    for (int j = 0; j < arr2.size(); ++j)
    {
        cout << " " << arr2[j];
    }
    cout << endl;

    return 0;
}
/* Output:
0 1 2 3 4 5 6 7 8 9
*/
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[checked_array_iterator](#checked_array_iterator)|Формирование итератора `checked_array_iterator` по умолчанию или итератора `checked_array_iterator` из базового итератора.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[difference_type](#difference_type)|Тип, обеспечивающий разницу между двумя итераторами `checked_array_iterator`, которые ссылаются на элементы в одном контейнере.|
|[pointer](#pointer)|Тип, содержащий указатель на элемент, к которому обращается итератор `checked_array_iterator`.|
|[reference](#reference)|Тип, содержащий ссылку на элемент, к которому обращается итератор `checked_array_iterator`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[base](#base)|Восстановление базового итератора из соответствующего итератора `checked_array_iterator`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator==](#op_eq_eq)|Проверка двух итераторов `checked_array_iterator` на равенство.|
|[operator!](#op_neq)|Проверка двух итераторов `checked_array_iterator` на неравенство.|
|[operator<](#op_lt)|Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора меньше итератора `checked_array_iterator` с правой стороны.|
|[operator>](#op_gt)|Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора больше итератора `checked_array_iterator` с правой стороны.|
|[operator<](#op_lt_eq)|Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора меньше или равен итератору `checked_array_iterator` с правой стороны.|
|[operator>](#op_gt_eq)|Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора больше или равен итератора `checked_array_iterator` с правой стороны.|
|[operator*](#op_star)|Возвращение элемента, к которому обращается `checked_array_iterator`.|
|[operator->](#op_arrow)|Возвращение указателя на элемент, к которому обращается `checked_array_iterator`.|
|[operator++](#op_add_add)|Увеличение `checked_array_iterator` до следующего элемента.|
|[operator--](#operator--)|Уменьшение `checked_array_iterator` до предыдущего элемента.|
|[operator+=](#op_add_eq)|Добавление заданного смещения к итератору `checked_array_iterator`.|
|[operator+](#op_add)|Добавление смещения к итератору и возврат нового итератора `checked_array_iterator`, который обращается к вставленному элементу в новой позиции смещения.|
|[operator-=](#operator-_eq)|Уменьшение заданного смещения из `checked_array_iterator`.|
|[operator-](#operator-)|Уменьшение смещения из итератора и возврат нового итератора `checked_array_iterator`, который обращается к вставленному элементу в новой позиции смещения.|
|[operator&#91;&#93;](#op_at)|Возврат ссылки на смещение элемента из элемента, к которому обращается `checked_array_iterator`, на указанное число позиций.|

## <a name="requirements"></a>Требования

**Заголовок:**\<iterator>

**Пространство имен:** stdext

## <a name="checked_array_iteratorbase"></a><a name="base"></a> checked_array_iterator::base

Восстановление базового итератора из соответствующего итератора `checked_array_iterator`.

```cpp
_Iterator base() const;
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_base.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main() {
   using namespace std;

   int V1[10];

   for (int i = 0; i < 10 ; i++)
      V1[i] = i;

   int* bpos;

   stdext::checked_array_iterator<int*> rpos(V1, 10);
   rpos++;

   bpos = rpos.base ( );
   cout << "The iterator underlying rpos is bpos & it points to: "
        << *bpos << "." << endl;
}
/* Output:
The iterator underlying rpos is bpos & it points to: 1.
*/
```

## <a name="checked_array_iteratorchecked_array_iterator"></a><a name="checked_array_iterator"></a> checked_array_iterator::checked_array_iterator

Формирование итератора `checked_array_iterator` по умолчанию или итератора `checked_array _iterator` из базового итератора.

```cpp
checked_array_iterator();

checked_array_iterator(
    ITerator ptr,
    size_t size,
    size_t index = 0);
```

### <a name="parameters"></a>Параметры

*указатель*\
Указатель на массив.

*size*\
Размер массива.

*index*\
Элемент в массиве для инициализации итератора (необязательно).  По умолчанию итератор инициализируется первым элементом в массиве.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_ctor.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   for (int i = 0 ; i < 5 ; i++)
      cout << b[i] << " ";
   cout << endl;

   checked_array_iterator<int*> checked_output_iterator(b,5);
   copy (a, a + 5, checked_output_iterator);
   for (int i = 0 ; i < 5 ; i++)
      cout << b[i] << " ";
   cout << endl;

   checked_array_iterator<int*> checked_output_iterator2(b,5,3);
   cout << *checked_output_iterator2 << endl;
}
/* Output:
0 1 2 3 4
0 1 2 3 4
3
*/
```

## <a name="checked_array_iteratordifference_type"></a><a name="difference_type"></a> checked_array_iterator::difference_type

Тип, обеспечивающий разницу между двумя итераторами `checked_array_iterator`, которые ссылаются на элементы в одном контейнере.

```cpp
typedef typename iterator_traits<_Iterator>::difference_type difference_type;
```

### <a name="remarks"></a>Примечания

Тип отличия `checked_array_iterator` совпадает с типом отличия итератора.

Пример кода см. в разделе [checked_array_iterator::operator[]](#op_at) .

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratoroperator"></a><a name="op_eq_eq"></a> checked_array_iterator::operator==

Проверка двух итераторов `checked_array_iterator` на равенство.

```cpp
bool operator==(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
Итератор `checked_array_iterator`, по которому выполняется проверка на равенство.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_opeq.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);
   checked_array_iterator<int*> checked_output_iterator2(b,5);

   if (checked_output_iterator2 == checked_output_iterator)
      cout << "checked_array_iterators are equal" << endl;
   else
      cout << "checked_array_iterators are not equal" << endl;

   copy (a, a + 5, checked_output_iterator);
   checked_output_iterator++;

   if (checked_output_iterator2 == checked_output_iterator)
      cout << "checked_array_iterators are equal" << endl;
   else
      cout << "checked_array_iterators are not equal" << endl;
}
/* Output:
checked_array_iterators are equal
checked_array_iterators are not equal
*/
```

## <a name="checked_array_iteratoroperator"></a><a name="op_neq"></a> checked_array_iterator::operator!=

Проверка двух итераторов `checked_array_iterator` на неравенство.

```cpp
bool operator!=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
Итератор `checked_array_iterator`, по которому выполняется проверка на неравенство.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_opneq.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);
   checked_array_iterator<int*> checked_output_iterator2(b,5);

   if (checked_output_iterator2 != checked_output_iterator)
      cout << "checked_array_iterators are not equal" << endl;
   else
      cout << "checked_array_iterators are equal" << endl;

   copy (a, a + 5, checked_output_iterator);
   checked_output_iterator++;

   if (checked_output_iterator2 != checked_output_iterator)
      cout << "checked_array_iterators are not equal" << endl;
   else
      cout << "checked_array_iterators are equal" << endl;
}
/* Output:
checked_array_iterators are equal
checked_array_iterators are not equal
*/
```

## <a name="checked_array_iteratoroperatorlt"></a><a name="op_lt"></a> checked_array_iterator::operator&lt;

Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора меньше итератора `checked_array_iterator` с правой стороны.

```cpp
bool operator<(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
Итератор `checked_array_iterator`, по которому выполняется проверка на неравенство.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_oplt.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);
   checked_array_iterator<int*> checked_output_iterator2(b,5);

   if (checked_output_iterator2 < checked_output_iterator)
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;
   else
      cout << "checked_output_iterator2 is not less than checked_output_iterator" << endl;

   copy (a, a + 5, checked_output_iterator);
   checked_output_iterator++;

   if (checked_output_iterator2 < checked_output_iterator)
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;
   else
      cout << "checked_output_iterator2 is not less than checked_output_iterator" << endl;
}
/* Output:
checked_output_iterator2 is not less than checked_output_iterator
checked_output_iterator2 is less than checked_output_iterator
*/
```

## <a name="checked_array_iteratoroperatorgt"></a><a name="op_gt"></a> checked_array_iterator::operator&gt;

Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора больше итератора `checked_array_iterator` с правой стороны.

```cpp
bool operator>(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
Итератор `checked_array_iterator`, с которым выполняется сравнение.

### <a name="remarks"></a>Примечания

Пример кода см. в разделе [checked_array_iterator::operator&lt;](#op_lt) .

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratoroperatorlt"></a><a name="op_lt_eq"></a> checked_array_iterator::operator&lt;=

Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора меньше или равен итератору `checked_array_iterator` с правой стороны.

```cpp
bool operator<=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
Итератор `checked_array_iterator`, с которым выполняется сравнение.

### <a name="remarks"></a>Примечания

Пример кода см. в разделе [checked_array_iterator::operator&gt;=](#op_gt_eq) .

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratoroperatorgt"></a><a name="op_gt_eq"></a> checked_array_iterator::operator&gt;=

Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора больше или равен итератора `checked_array_iterator` с правой стороны.

```cpp
bool operator>=(const checked_array_iterator<_Iterator>& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
Итератор `checked_array_iterator`, с которым выполняется сравнение.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_opgteq.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);
   checked_array_iterator<int*> checked_output_iterator2(b,5);

   if (checked_output_iterator2 >= checked_output_iterator)
      cout << "checked_output_iterator2 is greater than or equal to checked_output_iterator" << endl;
   else
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;

   copy (a, a + 5, checked_output_iterator);
   checked_output_iterator++;

   if (checked_output_iterator2 >= checked_output_iterator)
      cout << "checked_output_iterator2 is greater than or equal to checked_output_iterator" << endl;
   else
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;
}
/* Output:
checked_output_iterator2 is greater than or equal to checked_output_iterator
checked_output_iterator2 is less than checked_output_iterator
*/
```

## <a name="checked_array_iteratoroperator"></a><a name="op_star"></a> checked_array_iterator::operator*

Возвращение элемента, к которому обращается `checked_array_iterator`.

```cpp
reference operator*() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение элемента, найденного итератором `checked_array_iterator`.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterator_pointer.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <utility>
#include <iostream>

using namespace std;
using namespace stdext;

int main() {
   int a[] = {0, 1, 2, 3, 4};
   int b[5];
   pair<int, int> c[1];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   for (int i = 0 ; i < 5 ; i++)
      cout << b[i] << endl;

    c[0].first = 10;
    c[0].second = 20;

   checked_array_iterator<int*> checked_output_iterator(b,5);
   checked_array_iterator<int*>::pointer p = &(*checked_output_iterator);
   checked_array_iterator<pair<int, int>*> chk_c(c, 1);
   checked_array_iterator<pair<int, int>*>::pointer p_c = &(*chk_c);

   cout << "b[0] = " << *p << endl;
   cout << "c[0].first = " << p_c->first << endl;
}
/* Output:
0
1
2
3
4
b[0] = 0
c[0].first = 10
*/
```

## <a name="checked_array_iteratoroperator-gt"></a><a name="op_arrow"></a> checked_array_iterator::operator-&gt;

Возвращение указателя на элемент, к которому обращается `checked_array_iterator`.

```cpp
pointer operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент, к которому обращается `checked_array_iterator`.

### <a name="remarks"></a>Примечания

Пример кода см. в разделе [checked_array_iterator::operator](#pointer).

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratoroperator"></a><a name="op_add_add"></a> checked_array_iterator::operator++

Увеличение `checked_array_iterator` до следующего элемента.

```cpp
checked_array_iterator& operator++();

checked_array_iterator<_Iterator> operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает предварительно увеличенный `checked_array_iterator`, а второй, постинкрементный оператор, возвращает копию увеличенного `checked_array_iterator`.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_op_plus_plus.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace stdext;
   using namespace std;
   int a[] = {6, 3, 77, 199, 222};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);

   cout << *checked_output_iterator << endl;
   ++checked_output_iterator;
   cout << *checked_output_iterator << endl;
   checked_output_iterator++;
   cout << *checked_output_iterator << endl;
}
/* Output:
6
3
77
*/
```

## <a name="checked_array_iteratoroperator--"></a><a name="operator--"></a> checked_array_iterator::operator--

Уменьшение `checked_array_iterator` до предыдущего элемента.

```cpp
checked_array_iterator<_Iterator>& operator--();

checked_array_iterator<_Iterator> operator--(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает предварительно уменьшенный `checked_array_iterator`, а второй, постдекрементный оператор, возвращает копию уменьшенного `checked_array_iterator`.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_op_minus_minus.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace stdext;
   using namespace std;
   int a[] = {6, 3, 77, 199, 222};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);

   cout << *checked_output_iterator << endl;
   checked_output_iterator++;
   cout << *checked_output_iterator << endl;
   checked_output_iterator--;
   cout << *checked_output_iterator << endl;
}
/* Output:
6
3
6
*/
```

## <a name="checked_array_iteratoroperator"></a><a name="op_add_eq"></a> checked_array_iterator::operator+=

Добавление заданного смещения к итератору `checked_array_iterator`.

```cpp
checked_array_iterator<_Iterator>& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Параметры

*_Off*\
Смещение, на которое необходимо увеличить итератор.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент, к которому обращается `checked_array_iterator`.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_op_plus_eq.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace stdext;
   using namespace std;
   int a[] = {6, 3, 77, 199, 222};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);

   cout << *checked_output_iterator << endl;
   checked_output_iterator += 3;
   cout << *checked_output_iterator << endl;
}
/* Output:
6
199
*/
```

## <a name="checked_array_iteratoroperator"></a><a name="op_add"></a> checked_array_iterator::operator+

Добавление смещения к итератору и возврат нового итератора `checked_array_iterator`, который обращается к вставленному элементу в новой позиции смещения.

```cpp
checked_array_iterator<_Iterator> operator+(difference_type _Off) const;
```

### <a name="parameters"></a>Параметры

*_Off*\
Смещение для добавления к `checked_array_iterator`.

### <a name="return-value"></a>Возвращаемое значение

Объект `checked_array_iterator`, который обращается к элементу смещения.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_op_plus.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace stdext;
   using namespace std;
   int a[] = {6, 3, 77, 199, 222};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);

   cout << *checked_output_iterator << endl;
   checked_output_iterator = checked_output_iterator + 3;
   cout << *checked_output_iterator << endl;
}
/* Output:
6
199
*/
```

## <a name="checked_array_iteratoroperator-"></a><a name="operator-_eq"></a> checked_array_iterator::operator-=

Уменьшение заданного смещения из `checked_array_iterator`.

```cpp
checked_array_iterator<_Iterator>& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Параметры

*_Off*\
Смещение, на которое необходимо увеличить итератор.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент, к которому обращается `checked_array_iterator`.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_op_minus_eq.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace stdext;
   using namespace std;
   int a[] = {6, 3, 77, 199, 222};
   int b[5];
   copy(a, a + 5, checked_array_iterator<int*>(b,5));

   checked_array_iterator<int*> checked_output_iterator(b,5);

   checked_output_iterator += 3;
   cout << *checked_output_iterator << endl;
   checked_output_iterator -= 2;
   cout << *checked_output_iterator << endl;
}
/* Output:
199
3
*/
```

## <a name="checked_array_iteratoroperator-"></a><a name="operator-"></a> checked_array_iterator::operator-

Уменьшение смещения из итератора и возврат нового итератора `checked_array_iterator`, который обращается к вставленному элементу в новой позиции смещения.

```cpp
checked_array_iterator<_Iterator> operator-(difference_type _Off) const;

difference_type operator-(const checked_array_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*_Off*\
Смещение, на которое необходимо уменьшить `checked_array_iterator`.

### <a name="return-value"></a>Возвращаемое значение

Объект `checked_array_iterator`, который обращается к элементу смещения.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratoroperator"></a><a name="op_at"></a> checked_array_iterator::operator[]

Возврат ссылки на смещение элемента из элемента, к которому обращается `checked_array_iterator`, на указанное число позиций.

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>Параметры

*_Off*\
Смещение от адреса `checked_array_iterator`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на смещение элемента.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// checked_array_iterators_op_diff.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main() {
   using namespace std;
   int V1[10];

   for (int i = 0; i < 10 ; i++)
      V1[i] = i;

   // Declare a difference type for a parameter
   stdext::checked_array_iterator<int*>::difference_type diff = 2;

   stdext::checked_array_iterator<int*> VChkIter(V1, 10);

   stdext::checked_array_iterator<int*>::reference refrpos = VChkIter [diff];

   cout << refrpos + 1 << endl;
}
/* Output:
3
*/
```

## <a name="checked_array_iteratorpointer"></a><a name="pointer"></a> checked_array_iterator::pointer

Тип, содержащий указатель на элемент, к которому обращается итератор `checked_array_iterator`.

```cpp
typedef typename iterator_traits<_Iterator>::pointer pointer;
```

### <a name="remarks"></a>Примечания

Пример кода см. в разделе [checked_array_iterator::operator*](#op_star).

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

## <a name="checked_array_iteratorreference"></a><a name="reference"></a> checked_array_iterator::reference

Тип, содержащий ссылку на элемент, к которому обращается итератор `checked_array_iterator`.

```cpp
typedef typename iterator_traits<_Iterator>::reference reference;
```

### <a name="remarks"></a>Примечания

Пример кода см. в разделе [checked_array_iterator::operator[]](#op_at) .

Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

## <a name="see-also"></a>См. также

[\<iterator>](../standard-library/iterator.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
