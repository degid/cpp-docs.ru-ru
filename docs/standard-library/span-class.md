---
title: класс Span (стандартная библиотека C++) | Документация Майкрософт
description: Справочник по API для класса span библиотеки стандартных шаблонов (STL), который предоставляет упрощенное представление для непрерывной последовательности объектов.
ms.date: 05/28/2020
f1_keywords:
- span/std::span
- span/std::span::const_pointer
- span/std::span::const_reference
- span/std::span::difference_type
- span/std::span::element_type
- span/std::span::iterator
- span/std::span::pointer
- span/std::span::reference
- span/std::span::reverse_iterator
- span/std::span::size_type
- span/std::span::value_type
- span/std::span::at
- span/std::span::assign
- span/std::span::back
- span/std::span::begin
- span/std::span::data
- span/std::span::empty
- span/std::span::end
- span/std::span::front
- span/std::span::rbegin
- span/std::span::rend
- span/std::span::size
- span/std::span::size_bytes
- span/std::span::operator=
- span/std::span::operator[]
helpviewer_keywords:
- std::span [C++]
- std::span [C++], const_pointer
- std::span [C++], const_reference
- std::span [C++], difference_type
- std::span [C++], element_type
- std::span [C++], iterator
- std::span [C++], pointer
- std::span [C++], reference
- std::span [C++], reverse_iterator
- std::span [C++], size_type
- std::span [C++], value_type
- std::span [C++], assign
- std::span [C++], at
- std::span [C++], back
- std::span [C++], begin
- std::span [C++], data
- std::span [C++], empty
- std::span [C++], end
- std::span [C++], front
- std::span [C++], rbegin
- std::span [C++], rend
- std::span [C++], size
- std::span [C++], size_bytes
ms.openlocfilehash: 297104820f5498e59397db9025aed1675984a060
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039968"
---
# <a name="span-class-c-standard-library"></a>класс Span (стандартная библиотека C++)

Предоставляет упрощенное представление для непрерывной последовательности объектов. Диапазон обеспечивает надежный способ итерации и индексирования объектов, которые упорядочены обратно в память, например объекты, хранящиеся в встроенном массиве, `std::array` или `std::vector` .

Если обычно осуществляется доступ к последовательности объектов обратной передачи с помощью указателя и индекса, то `span` является более безопасной и упрощенной альтернативой.

Размер `span` можно задать во время компиляции, указав его в качестве аргумента шаблона или в среде выполнения, указав `dynamic_extent` .

## <a name="syntax"></a>Синтаксис

```cpp
template<class T, size_t Extent = dynamic_extent>
class span;
```

### <a name="template-parameters"></a>Параметры шаблона

`T`\
 Тип элементов в диапазоне.

`Extent`\
 Число элементов в диапазоне, если оно указано во время компиляции. В противном случае  `std::dynamic_extent` , если число элементов будет указано во время выполнения.

[Инструкции по выведению](#deduction_guides)

## <a name="members"></a>Элементы

| **Определения типов** | **Описание** |
|-|-|
| [const_pointer](#pointer) | Тип указателя на **`const`** элемент. |
| [const_reference](#reference) | Тип ссылки на **`const`** элемент. |
| [difference_type](#difference_type) | Тип расстояния со знаком между двумя элементами. |
| [element_type](#element_type) | Тип элемента Span. |
| [итераци](#iterator) | Тип итератора для диапазона. |
| [вид](#pointer) | Тип указателя на элемент. |
| [reference](#reference) | Тип ссылки на элемент. |
| [reverse_iterator](#reverse_iterator) | Тип реверсивного итератора для диапазона. |
| [size_type](#size_type) | Тип для результата неподписанного расстояния между двумя элементами в диапазоне. |
| [value_type](#value_type) | Тип элемента, без **`const`** или **`volatile`** квалификации. |
| **Конструкторы** | **Описание** |
|[размещать](#span)| Создайте `span`|
| **Поддержка итераторов** | **Описание** |
|[начале](#begin) | Получение итератора, указывающего на первый элемент в диапазоне.|
|[конце](#end) | Получение итератора, указывающего на конец диапазона. |
|[rbegin](#rbegin) | Получение реверсивного итератора, указывающего на последний элемент в диапазоне; то есть начало инвертированного диапазона.|
|[rend](#rend) | Возвращает обратный итератор, указывающий на начало диапазона. то есть в конце противоположного диапазона.|
| **Элементы доступа**| **Описание** |
|[Назад](#back) | Возвращает последний элемент в диапазоне.|
|[data](#data) | Возвращает адрес первого элемента в диапазоне.|
|[крышку](#front) | Получение первого элемента в диапазоне.|
|[operator\[\]](#op_at) | Доступ к элементу в указанной позиции.|
| **Наблюдатели** | **Описание** |
|[empty](#empty)| Проверьте, пуст ли диапазон.|
|[size](#size) | Возвращает количество элементов в диапазоне.|
|[size_bytes](#size_bytes) | Возвращает размер диапазона в байтах.|
| **Вложенные представления** | **Описание**|
| [first](#first_view) | Получение поддиапазона от начала диапазона.|
| [last](#last_view) | Получение поддиапазона от конца диапазона.|
| [поддиапазон](#sub_view) | Получение поддиапазона из любого места в диапазоне.|
| **Операторы** | **Описание** |
|[Span::operator=](#op_eq)| Замените диапазон.|
|[Оператор Span::\[\]](#op_at)| Получение элемента в указанной позиции. |

## <a name="remarks"></a>Комментарии

Все `span` функции элементов имеют неизменную сложность времени.

В отличие от `array` или `vector` , диапазон не "владеет" элементами внутри него. Диапазон не освобождает хранилище для элементов внутри него, так как он не владеет хранилищем для этих объектов.

## <a name="requirements"></a>Требования

**Заголовок:**\<span>

**Пространство имен:** std

**Параметр компилятора:** [/std: c + + Latest](../build/reference/std-specify-language-standard-version.md)

## <a name="spanback"></a><a name="back"></a> `span::back`

Возвращает последний элемент в диапазоне.

```cpp
constexpr reference back() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на последний элемент в диапазоне.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    cout << mySpan.back();
}
```

```Output
2
```

## <a name="spanbegin"></a><a name="begin"></a> `span::begin`

Получение итератора, указывающего на первый элемент в диапазоне.

```cpp
constexpr iterator begin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на первый элемент в диапазоне.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto i = mySpan.begin();
    cout << *i;
}
```

```Output
0
```

## <a name="spandata"></a><a name="data"></a> `span::data`

Возвращает указатель на начало данных диапазона.

```cpp
constexpr pointer data() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый элемент, хранящийся в диапазоне.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    auto i = mySpan.data();
    cout << *i;
}
```

```Output
0
```

## <a name="spandifference_type"></a><a name="difference_type"></a> `span::difference_type`

Число элементов между двумя элементами в диапазоне.

```cpp
using difference_type = std::ptrdiff_t;
```

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::difference_type distance = mySpan.end() - mySpan.begin();
    cout << distance << std::endl;
}
```

```Output
3
```

## <a name="spanelement_type"></a><a name="element_type"></a> `span::element_type`

Тип элементов в диапазоне.

```cpp
using element_type = T;
```

### <a name="remarks"></a>Комментарии

Тип берется из параметра шаблона `T` при создании диапазона.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::element_type et = mySpan[2];
    cout << et << endl;
}
```

```Output
2
```

## <a name="spanempty"></a><a name="empty"></a> `span::empty`

Содержит ли диапазон элементы.

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает **`true`** значение `this->size() == 0` , если. В противном случае — значение **`false`** .

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    bool isEmpty = mySpan.empty(); // isEmpty == false
}
```

## <a name="spanend"></a><a name="end"></a> `span::end`

Получение итератора в конце диапазона.

```cpp
constexpr iterator end() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий сразу за концом диапазона.

### <a name="remarks"></a>Комментарии

`end` используется для проверки того, прошел ли итератор конец диапазона.

Не следует отменять ссылки на значение, возвращаемое этим итератором. Используйте его, чтобы определить, достигнут ли итератор за пределами последнего элемента в диапазоне.

### <a name="example"></a>Пример

```cpp
// Iteration
for (auto it = s1.begin(); it != s1.end(); ++it)
{
    cout << *it;
}
```

## <a name="spanfirst"></a><a name="first_view"></a> `span::first`

Получение поддиапазона, взятого с начала этого диапазона.

```cpp
constexpr auto first(size_type count) const noexcept;
template <size_t count> constexpr auto first() const noexcept;
```

### <a name="parameters"></a>Параметры

*count*\
Число элементов с начала этого диапазона, помещаемых в поддиапазон.  
Число элементов указывается в качестве параметра для шаблона или для функции, как показано ниже.

### <a name="return-value"></a>Возвращаемое значение

Диапазон, содержащий `count` элементы из начала этого диапазона.

### <a name="remarks"></a>Комментарии

Используйте версию шаблона этой функции, если это возможно, для проверки `count` во время компиляции и для сохранения сведений о диапазоне, так как он возвращает диапазон фиксированного экстента.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto first2 = mySpan.first(2);
    cout << "mySpan.first(2): ";
    for (auto& i : first2)
    {
        cout << i;
    }

    cout << "\nmySpan.first<2>: ";
    auto viewSpan = mySpan.first<2>();
    for (auto& i : viewSpan)
    {
        cout << i;
    }
}
```

```Output
mySpan.first(2): 01
mySpan.first<2>: 01
```

## <a name="spanfront"></a><a name="front"></a> `span::front`

Получение первого элемента в диапазоне.

```cpp
constexpr reference front() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на первый элемент в диапазоне.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto i = mySpan.front();
    cout << i;
}
```

```Output
0
```

## <a name="spaniterator"></a><a name="iterator"></a> `span::iterator`

Тип итератора над элементами Span.

```cpp
using iterator = implementation-defined-iterator-type;
```

### <a name="remarks"></a>Комментарии

Этот тип выступает в качестве итератора над элементами в диапазоне.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::iterator it = mySpan.begin();
    cout << *it++ << *it++ << *it;
}
```

```Output
012
```

## <a name="spanlast"></a><a name="last_view"></a> `span::last`

Получение поддиапазона, взятого из конца этого диапазона.

```cpp
constexpr span<element_type, dynamic_extent> last(const size_type count) const noexcept;
template <size_t count> constexpr span<element_type, count> last() const noexcept;
```

### <a name="parameters"></a>Параметры

*count*\
Число элементов из конца этого диапазона, помещаемых в поддиапазон.
Число может быть указано в качестве параметра для шаблона или для функции, как показано ниже.

### <a name="return-value"></a>Возвращаемое значение

Диапазон, содержащий последние `count` элементы из этого диапазона.

### <a name="remarks"></a>Комментарии

Используйте версию шаблона этой функции, если это возможно, для проверки `count` во время компиляции и для сохранения сведений о диапазоне, так как он возвращает диапазон фиксированного экстента.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto first2 = mySpan.last(2);
    cout << "mySpan.last(2): ";
    for (auto& i : last2)
    {
        cout << i;
    }

    cout << "\nmySpan.last<2>: ";
    auto viewSpan = mySpan.last<2>();
    for (auto& i : viewSpan)
    {
        cout << i;
    }
}
```

```Output
mySpan.last(2): 12
mySpan.last<2>: 12
```

## <a name="spanoperator"></a><a name="op_at"></a> `span::operator[]`

Получить элемент в диапазоне в указанной позиции.

```cpp
constexpr reference operator[](size_type offset) const;
```

### <a name="parameters"></a>Параметры

*offset*\
Отсчитываемый от нуля элемент в диапазоне для доступа.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент в *смещении*позиции. Если недопустимое расположение, поведение не определено.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    cout << mySpan[1];
}
```

```Output
1
```

## <a name="spanoperator"></a><a name="op_eq"></a> `span::operator=`

Назначьте еще один диапазон.

```cpp
constexpr span& operator=(const span& other) noexcept = default;
```

### <a name="parameters"></a>Параметры

*иной*\
Диапазон, который необходимо присвоить этому элементу.

### <a name="return-value"></a>Возвращаемое значение

`*this`

### <a name="remarks"></a>Комментарии

Назначение выполняет неполную копию указателя данных и размера. Неполная копия является надежной, так как `span` не выделяет память для элементов, которые она содержит.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    span<int> mySpan2;
    mySpan2 = mySpan;
    for (auto &i : mySpan2)
    {
        cout << it;
    }
}
```

```Output
012
```

## <a name="spanpointer"></a><a name="pointer"></a> `span::pointer`

Типы для указателя и **`const`** указателя на элемент span.

```cpp
using pointer = T*;
using const_pointer = const T*;
```

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    // pointer
    span<int>::pointer ptr = &mySpan[2];
    *ptr = 9;
    cout << mySpan[2];

    // const pointer
    span<int>::const_pointer cPtr = &mySpan[0];
    // *cPtr = 9; error - const
    cout << *cPtr;
}
```

```Output
90
```

## <a name="spanrbegin"></a><a name="rbegin"></a> `span::rbegin`

Получение реверсивного итератора, указывающего на последний элемент этого интервала.

```cpp
constexpr reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало инвертированного диапазона.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    for (auto rIt = s1.rbegin(); rIt != s1.rend(); ++rIt)
    {
        cout << *rIt;
    }
}
```

```Output
210
```

## <a name="spanreference"></a><a name="reference"></a> `span::reference`

Типы для ссылки и **`const`** ссылки на элемент span.

```cpp
using reference = T&;
using const_reference = const T&;
```

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    // reference
    span<int>::reference ref = mySpan[0];
    ref = 9;
    cout << mySpan[0];
    // const reference
    span<int>::const_reference cRef = mySpan[1];
    // cRef = 9; error because const
    cout << cRef;
}
```

```Output
91
```

## <a name="spanrend"></a><a name="rend"></a> `span::rend`

Получение итератора произвольного доступа, который указывает на место сразу за концом обращенного диапазона.

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Обратный итератор на заполнитель, следующий за последним элементом в обращенном диапазоне; то есть заполнитель перед первым элементом в неинвертированном диапазоне.

### <a name="remarks"></a>Комментарии

`rend` используется с обратным диапазоном точно так же, как [span:: end](#end) используется с диапазоном. Используйте его, чтобы проверить, достиг ли обратный итератор конца своего диапазона.

Значение, возвращаемое, `rend` не должно быть разыменовано.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    for (auto rIt = s1.rbegin(); rIt != s1.rend(); ++rIt)
    {
        cout << *rIt;
    }
}
```

## <a name="spanreverse_iterator"></a><a name="reverse_iterator"></a> `span::reverse_iterator`

Тип реверсивного итератора для диапазона.

```cpp
using reverse_iterator = std::reverse_iterator<iterator>;
```

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::reverse_iterator rIt = mySpan.rbegin();
    cout << *rIt++ << *rIt++ << *rIt;
}
```

```Output
210
```

## <a name="spansize"></a><a name="size"></a> `span::size`

Возвращает количество элементов в диапазоне.

```cpp
constexpr size_t size() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в диапазоне.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    cout << mySpan.size();
}
```

```Output
3
```

## <a name="spansize_bytes"></a><a name="size_bytes"></a> `span::size_bytes`

Получение размера элементов в диапазоне в байтах.

```cpp
constexpr size_type size_bytes() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Число байтов, занимаемых всеми элементами в диапазоне; то есть `sizeof(element_type)` умножается на число элементов в диапазоне.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    cout << mySpan.size_bytes(); // 3 elements * 4 (size of an int)
}
```

```Output
12
```

## <a name="spansize_type"></a><a name="size_type"></a> `span::size_type`

Тип без знака, подходящий для хранения количества элементов в диапазоне.

```cpp
using size_type = size_t;
```

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::size_type szType = mySpan.size();
    cout << szType;
}
```

```Output
3
```

## <a name="spanspan"></a><a name="span"></a> `span::span`

`span` конструкторы.

```cpp
constexpr span() noexcept
requires (Extent == 0 || Extent == dynamic_extent) = default;

template <class It>
constexpr explicit(Extent != dynamic_extent)
span(It first, size_type count) noexcept

template <class It, class End>
constexpr explicit(Extent != dynamic_extent)
span(It first, End last) noexcept(noexcept(last - first))

template <class T, size_t N>
requires (Extent == dynamic_extent || Extent == N) && is_convertible_v<T (*)[], T (*)[]>
constexpr span(array<T, N>& arr) noexcept

template <class T, size_t N>
requires (Extent == dynamic_extent || Extent == N) && is_convertible_v<const T (*)[], T (*)[]>
constexpr span(const array<T, N>& arr) noexcept

template <size_t N>
requires (Extent == dynamic_extent || Extent == N)
constexpr span(type_identity_t<T> (&arr)[N]) noexcept

template <class R>
constexpr explicit(Extent != dynamic_extent)
span(R&& r)

// default copy ctor
constexpr span(const span& other) noexcept = default;

// converting  ctor
template <class T, size_t OtherExtent>
requires (Extent == dynamic_extent || OtherExtent == dynamic_extent ||
              Extent == OtherExtent) && is_convertible_v<T (*)[], T (*)[]>
constexpr explicit(Extent != dynamic_extent && OtherExtent == dynamic_extent)
span(const span<T, OtherExtent>& other) noexcept
```

### <a name="parameters"></a>Параметры

*маленькая*\
Создание диапазона из массива.

*count*\
Число элементов, которые будут находиться в диапазоне.

*first*\
Итератор на первый элемент в диапазоне.

*last*\
Итератор, который сразу после последнего элемента в диапазоне.

*\N*\
Число элементов, которые будут находиться в диапазоне.

*иной*\
Создайте копию этого диапазона.

*Cерверный*\
Создайте диапазон из этого диапазона.

### <a name="remarks"></a>Комментарии

Диапазон не освобождает память для элементов в диапазоне, так как он не владеет хранилищем объектов внутри него.

|Конструктор  | Описание  |
|---------|---------|
|`span()` | Создайте пустой диапазон. Учитывается только при разрешении перегрузки, если параметр шаблона `Extent` имеет значение `0` или `dynamic_extent` .|
|`span(It first, size_type count)` | Создайте диапазон из первых `count` элементов итератора `first` .  Учитывается только при разрешении перегрузки, если параметр шаблона `Extent` не имеет `dynamic_extent` . |
|`span(It first, End last)` | Создайте диапазон из элементов в итераторе, `first` пока не будет `last` достигнут конец. Учитывается только при разрешении перегрузки, если параметр шаблона `Extent` не имеет `dynamic_extent` . `It` должен быть `contiguous_iterator` .  |
|`span(array<T, N>& arr) noexcept;`<br /><br />`span(const array<T, N>& arr) noexcept;`<br /><br />`span(type_identity_t<element_type> (&arr)[N]) noexcept;` |  Создание диапазона из `N` элементов указанного массива. Учитывается только при разрешении перегрузки, если параметр шаблона `Extent` равен `dynamic_extent` или равен `N` . |
|`span(R&& r)` |  Создание диапазона из диапазона. Участвует только в разрешении перегрузки, если параметр шаблона не имеет значение `Extent` `dynamic_extent` .|
|`span(const span& other)` |  Созданный компилятором конструктор копии. Неполная копия указателя данных является надежной, так как диапазон не выделяет память для хранения элементов. |
|`span(const span<OtherElementType, OtherExtent>& s) noexcept;` | Конструктор преобразования: Создайте диапазон из другого диапазона. Участвуют в разрешении перегрузки только в том случае, если параметр шаблона `Extent` имеет значение `dynamic_extent` , или равно `N` `dynamic_extent` `Extent` .|

### <a name="example"></a>Пример

```cpp
#include <span>

using namespace std;

int main()
{
    const int MAX=10;

    int x[MAX];
    for (int i = 0; i < MAX; i++)
    {
        x[i] = i;
    }

    span<int, MAX> span1{ x }; // fixed-size span: compiler error if size of x doesn't match template argument MAX
    span<int> span2{ x }; // size is inferred from x
    span<const int> span3 = span2; // converting constructor
    span<int> span4( span2 ); // copy constructor
}
```

## <a name="spansubspan"></a><a name="sub_view"></a> `span::subspan`

Получение поддиапазона этого диапазона.

```cpp
constexpr auto subspan(size_type offset, size_type count = dynamic_extent) const noexcept;

template <size_t offset, size_t count = dynamic_extent>
constexpr auto subspan() const noexcept
```

### <a name="parameters"></a>Параметры

*count*\
Число элементов, помещаемых в поддиапазон. Если `count` равно `dynamic_extent` (значение по умолчанию), поддиапазон берется `offset` до конца этого диапазона.

*offset*\
Расположение в этом диапазоне для запуска поддиапазона.

### <a name="return-value"></a>Возвращаемое значение

Диапазон, начинающийся с `offset` в этом диапазоне. Содержит `count` элементы.

### <a name="remarks"></a>Комментарии

Доступна версия шаблона этой функции, которая проверяет счетчик во время компиляции, что сохраняет сведения о диапазоне, возвращая диапазон фиксированного экстента.

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    cout << "mySpan.subspan(1,2): ";
    for (auto& i : mySpan.subspan(1,2))
    {
        cout << i;
    }
    cout << "\nmySpan.subspan<1,2>: ";
    for (auto& i : mySpan.subspan<1,2>())
    {
        cout << i;
    }
    cout << "\nmySpan.subspan<1>: ";
    for (auto& i : mySpan.subspan<1>)
    {
        cout << i;
    }
}
```

```Output
mySpan.subspan(1,2): 12
mySpan.subspan<1,2>: 12
mySpan.subspan<1>: 12
```

## <a name="spanvalue_type"></a><a name="value_type"></a> `span::value_type`

Тип элемента в диапазоне, без **`const`** или **`volatile`** квалификации.

```cpp
using value_type = std::remove_cv_t<T>;
```

### <a name="example"></a>Пример

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::value_type vType = mySpan[2];
    cout << vType;
}
```

```Output
2
```

## <a name="deduction-guides"></a><a name="deduction_guides"></a> Направляющие удержания

Для SPAN предоставлены следующие руководства по удержанию.

```cpp
// Allows the extent to be deduced from std::array and C++ built-in arrays

template <class T, size_t Extent>
span(T (&)[Extent]) -> span<T, Extent>;

template <class T, size_t Size>
span(array<T, Size>&) -> span<T, Size>;

template <class T, size_t Size>
span(const array<T, Size>&) -> span<const T, Size>;

// Allows the element type to be deduced from the iterator and the end of the span.
// The iterator must be contiguous

template <contiguous_iterator It, class End>
span(It, End) -> span<remove_reference_t<iter_reference_t<It>>>;

// Allows the element type to be deduced from a range.
// The range must be contiguous

template <ranges::contiguous_range Rng>
span(Rng &&) -> span<remove_reference_t<ranges::range_reference_t<Rng>>>;
```

## <a name="see-also"></a>См. также раздел

[\<span>](../standard-library/span.md)  
[Как использовать выведение аргументов шаблона класса](https://devblogs.microsoft.com/cppblog/how-to-use-class-template-argument-deduction/)
