---
title: '&lt;&gt;операторы string_view'
description: Справочник по API для `string_view` операторов, которые используются для сравнения двух `string_view` объектов, `string_view` а также и другого строкового объекта
ms.date: 9/4/2020
f1_keywords:
- xstring/basic_string_view::operator!=
- xstring/basic_string_view::operator&gt;
- xstring/basic_string_view::operator&gt;=
- xstring/basic_string_view::operator&lt;
- xstring/basic_string_view::operator&lt;&lt;
- xstring/basic_string_view::operator&lt;=
- xstring/basic_string_view::operator+
- xstring/basic_string_view::operator==
helpviewer_keywords:
- std::basic_string_view::operator!=
- std::basic_string_view::operator&gt;
- std::basic_string_view::operator&gt;=
- std::basic_string_view::operator&lt;
- std::basic_string_view::operator&lt;&lt;
- std::basic_string_view::operator&lt;=, std::basic_string_view::operator==
ms.openlocfilehash: 832e49aaf01a4ea124b7a6881b93bd93b7337215
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039889"
---
# <a name="ltstring_viewgt-operators"></a>&lt;&gt;операторы string_view

Используйте эти операторы для сравнения двух string_view объектов, string_view и другого строкового объекта (например, [std:: String](basic-string-class.md)или **char \* **), для которых предоставляется неявное преобразование.

[operator!=](#op_neq)\
[operator&gt;](#op_gt)\
[operator&gt;=](#op_gt_eq)\
[operator&lt;](#op_lt)\
[operator&lt;&lt;](#op_lt_lt)\
[operator&lt;=](#op_lt_eq)\
[operator==](#op_eq_eq)\
[оператор "" ОКП](#op_sv)

## <a name="operator"></a><a name="op_neq"></a> operator!=

Проверяет неравенство объекта слева от оператора объекту справа от оператора.

```cpp
template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator!=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*right*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если объект в левой части оператора не лексикографически равным объекту с правой стороны; в противном случае — значение **`false`** .

### <a name="remarks"></a>Комментарии

Неявное преобразование должно существовать из *convertible_string_type* string_view на другой стороне.

Сравнение основано на парном лексикографическом сравнении последовательностей символов. Если число элементов равно количеству и все элементы равны, то два объекта равны. В противном случае они не равны.

## <a name="operator"></a><a name="op_eq_eq"></a> operator==

Проверяет равенство объекта слева от оператора объекту справа от оператора.

```cpp
template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator==(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*right*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект слева от оператора лексикографически равен объекту в правой части; в противном случае — значение **`false`** .

### <a name="remarks"></a>Комментарии

Неявное преобразование должно существовать из *convertible_string_type* string_view на другой стороне.

Сравнение основано на парном лексикографическом сравнении последовательностей символов. Если число элементов равно количеству и все элементы равны, то два объекта равны.

## <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

Проверяет, меньше ли объект в левой части оператора, чем объект справа sidestring_view

```cpp
template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*right*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект слева от оператора лексикографически меньше объекта с правой стороны; в противном случае — значение **`false`** .

### <a name="remarks"></a>Комментарии

Неявное преобразование должно существовать из *convertible_string_type* string_view на другой стороне.

Сравнение основано на парном лексикографическом сравнении последовательностей символов. При обнаружении первой неравной пары символов возвращается результат этого сравнения. Если неравные символы не найдены, но одна последовательность короче, более короткая последовательность меньше чем длинная. Иными словами, "Cat" меньше "кошки".

### <a name="example"></a>Пример

```cpp
#include <string>
#include <string_view>

using namespace std;

int main()
{
    string_view sv1 { "ABA" };
    string_view sv2{ "ABAC" };
    string_view sv3{ "ABAD" };
    string_view sv4{ "ABACE" };

    bool result = sv2 > sv1; // true
    result = sv3 > sv2; // true
    result = sv3 != sv1; // true
    result = sv4 < sv3; // true because `C` < `D`
}
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> operator&lt;=

Проверяет, что объект слева от оператора меньше или равен объекту справа от оператора.

```cpp
template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*right*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект слева от оператора лексикографически меньше или равен объекту в правой части; в противном случае — значение **`false`** .

### <a name="remarks"></a>Комментарии

См [. &lt; оператор](#op_lt).

## <a name="operatorltlt"></a><a name="op_lt_lt"></a> operator&lt;&lt;

Записывает string_view в поток вывода.

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>Параметры

*OSTR*\
поток вывода, в который выполняется запись.

*Str*\
String_view, который необходимо указать в потоке вывода.

### <a name="return-value"></a>Возвращаемое значение

поток вывода, в который выполняется запись.

### <a name="remarks"></a>Комментарии

Этот оператор используется для вставки содержимого string_view в поток вывода, например с помощью [std:: cout](iostream.md#cout).

## <a name="operatorgt"></a><a name="op_gt"></a> operator&gt;

Проверяет, что объект слева от оператора больше, чем объект справа от оператора.

```cpp
template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*right*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если объект в левой части оператора лексикографически больше, чем объект string_view с правой стороны; в противном случае — значение **`false`** .

### <a name="remarks"></a>Комментарии

См [. &lt; оператор](#op_lt).

## <a name="operatorgt"></a><a name="op_gt_eq"></a> operator&gt;=

Проверяет, что объект слева от оператора больше или равен объекту справа от оператора.

```cpp
template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*right*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект слева от оператора лексикографически больше или равен объекту с правой стороны; в противном случае — значение **`false`** .

### <a name="remarks"></a>Комментарии

См [. &lt; оператор](#op_lt).

## <a name="operator-sv-string_view-literal"></a><a name="op_sv"></a> оператор "ОКП (string_view литерал)

Конструирует string_view из строкового литерала. Требуется пространство имен `std::literals::string_view_literals` .

### <a name="example"></a>Пример

```cpp

using namespace std;
using namespace literals::string_view_literals;

    string_view sv{ "Hello"sv };
    wstring_view wsv{ L"Hello"sv };
    u16string_view sv16{ u"Hello"sv };
    u32string_view sv32{ U"Hello"sv };
```

## <a name="requirements"></a>Требования

[/std:c++17](../build/reference/std-specify-language-standard-version.md)

## <a name="see-also"></a>См. также раздел

[\<string_view>](../standard-library/string-view.md)
