---
title: Класс basic_string_view
description: Справочник по API `basic_string_view` , который ссылается на постоянную непрерывную последовательность объектов типа char.
ms.date: 9/8/2020
f1_keywords:
- xstring/std::basic_string_view
- xstring/std::basic_string_view::allocator_type
- xstring/std::basic_string_view::const_iterator
- xstring/std::basic_string_view::const_pointer
- xstring/std::basic_string_view::const_reference
- xstring/std::basic_string_view::const_reverse_iterator
- xstring/std::basic_string_view::difference_type
- xstring/std::basic_string_view::ends_with
- xstring/std::basic_string_view::starts_with
- xstring/std::basic_string_view::iterator
- xstring/std::basic_string_view::npos
- xstring/std::basic_string_view::pointer
- xstring/std::basic_string_view::reference
- xstring/std::basic_string_view::reverse_iterator
- xstring/std::basic_string_view::size_type
- xstring/std::basic_string_view::traits_type
- xstring/std::basic_string_view::value_type
- xstring/std::basic_string_view::append
- xstring/std::basic_string_view::assign
- xstring/std::basic_string_view::at
- xstring/std::basic_string_view::back
- xstring/std::basic_string_view::begin
- xstring/std::basic_string_view::c_str
- xstring/std::basic_string_view::capacity
- xstring/std::basic_string_view::cbegin
- xstring/std::basic_string_view::cend
- xstring/std::basic_string_view::clear
- xstring/std::basic_string_view::compare
- xstring/std::basic_string_view::copy
- xstring/std::basic_string_view::_Copy_s
- xstring/std::basic_string_view::crbegin
- xstring/std::basic_string_view::crend
- xstring/std::basic_string_view::data
- xstring/std::basic_string_view::empty
- xstring/std::basic_string_view::end
- xstring/std::basic_string_view::erase
- xstring/std::basic_string_view::find
- xstring/std::basic_string_view::find_first_not_of
- xstring/std::basic_string_view::find_first_of
- xstring/std::basic_string_view::find_last_not_of
- xstring/std::basic_string_view::find_last_of
- xstring/std::basic_string_view::front
- xstring/std::basic_string_view::get_allocator
- xstring/std::basic_string_view::insert
- xstring/std::basic_string_view::length
- xstring/std::basic_string_view::max_size
- xstring/std::basic_string_view::pop_back
- xstring/std::basic_string_view::push_back
- xstring/std::basic_string_view::rbegin
- xstring/std::basic_string_view::rend
- xstring/std::basic_string_view::remove_prefix
- xstring/std::basic_string_view::remove_suffix
- xstring/std::basic_string_view::replace
- xstring/std::basic_string_view::reserve
- xstring/std::basic_string_view::resize
- xstring/std::basic_string_view::rfind
- xstring/std::basic_string_view::shrink_to_fit
- xstring/std::basic_string_view::size
- xstring/std::basic_string_view::substr
- xstring/std::basic_string_view::swap
helpviewer_keywords:
- std::basic_string_view
- std::basic_string_view, allocator_type
- std::basic_string_view, const_iterator
- std::basic_string_view, const_pointer
- std::basic_string_view, const_reference
- std::basic_string_view, const_reverse_iterator
- std::basic_string_view, difference_type
- std::basic_string_view, iterator
- std::basic_string_view, npos
- std::basic_string_view, pointer
- std::basic_string_view, reference
- std::basic_string_view, reverse_iterator
- std::basic_string_view, size_type
- std::basic_string_view, traits_type
- std::basic_string_view, value_type
- std::basic_string_view, append
- std::basic_string_view, assign
- std::basic_string_view, at
- std::basic_string_view, back
- std::basic_string_view, begin
- std::basic_string_view, c_str
- std::basic_string_view, capacity
- std::basic_string_view, cbegin
- std::basic_string_view, cend
- std::basic_string_view, clear
- std::basic_string_view, compare
- std::basic_string_view, copy
- std::basic_string_view, crbegin
- std::basic_string_view, crend
- std::basic_string_view, data
- std::basic_string_view, empty
- std::basic_string_view, end
- std::basic_string_view, ends_with
- std::basic_string_view, erase
- std::basic_string_view, find
- std::basic_string_view, find_first_not_of
- std::basic_string_view, find_first_of
- std::basic_string_view, find_last_not_of
- std::basic_string_view, find_last_of
- std::basic_string_view, front
- std::basic_string_view, get_allocator
- std::basic_string_view, insert
- std::basic_string_view, length
- std::basic_string_view, max_size
- std::basic_string_view, pop_back
- std::basic_string_view, push_back
- std::basic_string_view, rbegin
- std::basic_string_view, rend
- std::basic_string_view, remove_prefix
- std::basic_string_view, remove_suffix
- std::basic_string_view, replace
- std::basic_string_view, reserve
- std::basic_string_view, resize
- std::basic_string_view, rfind
- std::basic_string_view, shrink_to_fit
- std::basic_string_view, size
- std::basic_string_view, starts_with
- std::basic_string_view, substr
- std::basic_string_view, swap
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
ms.openlocfilehash: 8eddf4bc6aae0338dc2e914aa57e6c1e7cc5c912
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040214"
---
# <a name="basic_string_view-class"></a>Класс basic_string_view

Шаблон класса `basic_string_view<charT>` был добавлен в c++ 17 для использования в качестве безопасного и эффективного способа, чтобы функция принимала различные несвязанные строковые типы без функции, преобразованный в этих типах. Класс содержит указатель, не являющийся владельцем, для непрерывной последовательности символьных данных и длину, указывающую количество символов в последовательности. Никаких предположений относительно того, завершается ли последовательность символом NULL, не выполняется.

Стандартная библиотека определяет несколько специализаций на основе типа элементов:

- `string_view`
- `wstring_view`
- `u16string_view`
- `u32string_view`

В этом документе термин «string_view» обычно относится к любому из этих определений типов.

String_view описывает минимальный общий интерфейс, необходимый для чтения строковых данных. Он предоставляет постоянный доступ к базовым данным. Он не делает копий (за исключением `copy` функции). Данные могут не содержать значений NULL ("\ 0") в любой позиции. String_view не имеет контроля над временем существования объекта. Это обязанность вызывающего объекта, гарантирующая, что базовые строковые данные являются допустимыми.

Функция, принимающая параметр типа string_view, может быть создана для работы с любым типом, подобным строковым, без создания функции в шаблон или ограничения функции на определенное подмножество строковых типов. Единственное требование заключается в том, что для string_view существует неявное преобразование из строкового типа. Все стандартные строковые типы неявно преобразуются в string_view, содержащую один и тот же тип элемента. Иными словами, объект `std::string` преобразуется в, `string_view` но не в `wstring_view` .

В следующем примере показана функция, не относящаяся к шаблону `f` , которая принимает параметр типа `wstring_view` . Его можно вызвать с аргументами типа `std::wstring` , `wchar_t*` и `winrt::hstring` .

```cpp
// compile with: /std:c++17
// string_view that uses elements of wchar_t
void f(wstring_view);

// pass a std::wstring:
const std::wstring& s { L"Hello" };
f(s);

// pass a C-style null-terminated string (string_view is not null-terminated):
const wchar_t* ns = L"Hello";
f(ns);

// pass a C-style character array of len characters (excluding null terminator):
const wchar_t* cs { L"Hello" };
size_t len { 5 };
f({cs,len});

// pass a WinRT string
winrt::hstring hs { L"Hello" };
f(hs);
```

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType, class Traits = char_traits<CharType>>
class basic_string_view;
```

### <a name="parameters"></a>Параметры

*CharType*\
Тип символов, которые хранятся в string_view. Стандартная библиотека C++ предоставляет следующие определения типов для специализаций этого шаблона.

- [string_view](../standard-library/string-view-typedefs.md#string_view) для элементов типа **`char`**
- [wstring_view](../standard-library/string-view-typedefs.md#wstring_view), для **`wchar_t`**
- [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) для **`char16_t`**
- [u32string_view](../standard-library/string-view-typedefs.md#u32string_view) для **`char32_t`** .

*Traits*\
По умолчанию используется [char_traits](char-traits-struct.md) <>*CharType* .

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_string_view](#basic_string_view)|Конструирует string_view, который пуст или указывает на все или часть данных какого-либо другого объекта строки или на массив символов в стиле C.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|**const_iterator**|Итератор произвольного доступа, который может считывать **`const`** элементы.|
|**const_pointer**|`using const_pointer = const value_type*;`|
|**const_reference**|`using const_reference = const value_type&;`|
|**const_reverse_iterator**|`using const_reverse_iterator = std::reverse_iterator<const_iterator>;`|
|**difference_type**|`using difference_type = ptrdiff_t;`|
|**итераци**|`using iterator = const_iterator;`|
|**npos**|`static constexpr size_type npos = size_type(-1);`|
|**вид**|`using pointer = value_type*;`|
|**reference**|`using reference = value_type&;`|
|**reverse_iterator**|`using reverse_iterator = const_reverse_iterator;`|
|**size_type**|`using size_type = size_t;`|
|**traits_type**|`using traits_type = Traits;`|
|**value_type**|`using value_type = CharType;`|

### <a name="member-operators"></a>Операторы членов

|Оператор|Описание|
|-|-|
|[operator=](#op_eq)|Присваивает string_view или преобразуемый строковый объект другому string_viewу.|
|[operator\[\]](#op_at)|Возвращает элемент по указанному индексу.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[at](#at)|Возвращает const_reference элементу в указанном расположении.|
|[back](#back)|Возвращает const_reference последнему элементу.|
|[begin](#begin)|Возвращает итератор const, обращающийся к первому элементу. (string_views являются неизменяемыми.)|
|[cbegin](#cbegin)|То же, что и [Begin](#begin).|
|[cend](#cend)|Возвращает константный итератор, указывающий на один за последним элементом.|
|[copy](#copy)|Копирует не более указанного числа символов из индексированной позиции в исходном string_view в целевой массив символов. (Не рекомендуется. Вместо этого используйте _Copy_s.)|
|[_Copy_s](#_copy_s)|Безопасная функция копирования CRT.|
|[равенств](#compare)|Сравнивает string_view с указанным string_view, чтобы определить, равны ли они или если один из них лексикографически меньше другого.|
|[crbegin](#crbegin)|То же, что и [rbegin](#rbegin).|
|[crend](#crend)|То же, что и [rend](#rend).|
|[data](#data)|Возвращает необработанный указатель на последовательность символов, не являющийся владельцем.|
|[empty](#empty)|Проверяет, содержит ли string_view символы.|
|[end](#end)|То же, что и [cend](#cend).|
|[ends_with](#ends_with)<sup>c++ 20</sup>|Проверьте, заканчивается ли представление строки указанным суффиксом.|
|[find](#find)|Выполняет поиск в прямом направлении для первого вхождения подстроки, совпадающей с заданной последовательностью символов.|
|[find_first_not_of](#find_first_not_of)|Выполняет поиск первого символа, который не является ни одним элементом указанного string_view или преобразуемого строкового объекта.|
|[find_first_of](#find_first_of)|Выполняет поиск первого символа, соответствующего любому элементу указанного string_view или преобразуемого строкового объекта.|
|[find_last_not_of](#find_last_not_of)|Выполняет поиск последнего символа, не любого элемента указанного string_view или преобразуемого строкового объекта.|
|[find_last_of](#find_last_of)|Выполняет поиск последнего символа, который является элементом указанного string_view или преобразуемого строкового объекта.|
|[front](#front)|Возвращает const_reference первому элементу.|
|[length](#length)|Возвращает текущее количество элементов.|
|[max_size](#max_size)|Возвращает максимальное число символов, которое может содержать string_view.|
|[rbegin](#rbegin)|Возвращает константный итератор, который обращается к первому элементу в обращенном string_view.|
|[remove_prefix](#remove_prefix)|Перемещает указатель вперед на указанное число элементов.|
|[remove_suffix](#remove_suffix)|Уменьшает размер представления по заданному числу элементов, начиная с обратного.|
|[rend](#rend)|Возвращает константный итератор, указывающий на один за последним элементом в обращенном string_view.|
|[rfind](#rfind)|Выполняет поиск в string_view в обратную строку для первого вхождения подстроки, совпадающей с заданной последовательностью символов.|
|[size](#size)|Возвращает текущее количество элементов.|
|[starts_with](#starts_with)<sup>c++ 20</sup>|Проверьте, начинается ли строковое представление с заданным префиксом.|
|[substr](#substr)|Возвращает подстроку указанной длины, начиная с указанного индекса.|
|[swap](#swap)|Обмен содержимым двух string_views.|

## <a name="remarks"></a>Комментарии

Если функция должна создать последовательность, длина которой превышает [max_size](#max_size) элементов, функция выдает сообщение об ошибке длины, создавая объект типа [length_error](../standard-library/length-error-class.md).

## <a name="requirements"></a>Требования

[std: c++ 17](../build/reference/std-specify-language-standard-version.md) или более поздней версии.

**Заголовок:**\<string_view>

**Пространство имен:** std

## <a name="basic_string_viewat"></a><a name="at"></a> basic_string_view:: at

Возвращает const_reference символу по указанному индексу (от 0).

```cpp
constexpr const_reference at(size_type offset) const;
```

### <a name="parameters"></a>Параметры

*offset*\
Индекс элемента, на который должна указывать ссылка.

### <a name="return-value"></a>Возвращаемое значение

Const_reference символу в позиции, указанной в индексе параметра.

### <a name="remarks"></a>Комментарии

Первый элемент имеет нулевой индекс, и следующие элементы индексируются последовательно положительными целыми числами, поэтому string_view length *n* содержит *n*-й элемент, индексируемый по числу *n –* 1. **при** вызове метод вызывает исключение для недопустимых индексов, в отличие от [оператора \[ \] ](#op_at).

В общем случае рекомендуется не использовать **для таких** последовательностей, как `std::vector` и string_view. Недопустимый индекс, переданный в последовательность, — это логическая ошибка, которая должна быть обнаружена и исправлена во время разработки. Если программе не известно, что ее индексы являются допустимыми, то следует протестировать их, а не вызывать в () и использовать исключения для защиты от неосторожного программирования.

Дополнительные сведения см. в разделе [basic_string_view::operator \[ \] ](#op_at) .

### <a name="example"></a>Пример

```cpp
// basic_string_view_at.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>

int main()
{
    using namespace std;

    const string_view  str1("Hello world");
    string_view::const_reference refStr2 = str1.at(8); // 'r'
}
```

## <a name="basic_string_viewback"></a><a name="back"></a> basic_string_view:: назад

Возвращает const_reference последнему элементу.

```cpp
constexpr const_reference back() const;
```

### <a name="return-value"></a>Возвращаемое значение

Const_reference к последнему элементу в string_view.

### <a name="remarks"></a>Комментарии

Создает исключение, если string_view пуст.

Помните, что после изменения string_view, например путем вызова метода `remove_suffix` , элемент, возвращаемый этой функцией, больше не является последним элементом в базовых данных.

### <a name="example"></a>Пример

Объект `string_view` , созданный с помощью строкового литерала C, не включает завершающее значение null. В следующем примере `back` возвращается значение, `'p'` а не `'\0'` .

```cpp
char c[] = "Help"; // char[5]
string_view sv{ c };
cout << sv.size(); // size() == 4
cout << sv.back() << endl; // p
```

Внедренные значения NULL обрабатываются как любые другие символы:

```cpp
string_view e = "embedded\0nulls"sv;
cout << boolalpha << (e.back() == 's'); // true
```

## <a name="basic_string_viewbasic_string_view"></a><a name="basic_string_view"></a> basic_string_view:: basic_string_view

Конструирует string_view.

```cpp
constexpr basic_string_view() noexcept;
constexpr basic_string_view(const basic_string_view&) noexcept = default;
constexpr basic_string_view(const charT* str);
constexpr basic_string_view(const charT* str, size_type len);
```

### <a name="parameters"></a>Параметры

*str*\
Указатель на символьные значения.

*len*\
Число символов, включаемых в представление.

### <a name="remarks"></a>Комментарии

В конструкторах с параметром charT * предполагается, что входные данные завершаются нулем, но завершающее значение NULL не включено в string_view.

Можно также создать string_view с литералом. См. [оператор «ОКП»](string-view-operators.md#op_sv).

## <a name="basic_string_viewbegin"></a><a name="begin"></a> basic_string_view:: Begin

То же, что и [cbegin](#cbegin).

```cpp
constexpr const_iterator begin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает const_iterator, обращающийся к первому элементу.

## <a name="basic_string_viewcbegin"></a><a name="cbegin"></a> basic_string_view:: cbegin

Возвращает const_iterator, который обращается к первому элементу в диапазоне.

```cpp
constexpr const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**`const`** Итератор произвольного доступа, указывающий на первый элемент диапазона, или расположение непосредственно за концом пустого диапазона (для пустого диапазона `cbegin() == cend()` ).

## <a name="basic_string_viewcend"></a><a name="cend"></a> basic_string_view:: cend

Возвращает const_iterator, который обращается к расположению сразу за последним элементом в диапазоне.

```cpp
constexpr const_iterator cend() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**`const`** Итератор произвольного доступа, указывающий сразу за концом диапазона.

### <a name="remarks"></a>Комментарии

Значение, возвращаемое, `cend` не должно быть разыменовано.

## <a name="basic_string_viewcompare"></a><a name="compare"></a> basic_string_view:: Compare

Выполняет сравнение с учетом регистра с заданным string_view (или преобразуемым строковым типом), чтобы определить, равны ли два объекта, или если один из них лексикографически меньше другого. [ \<string_view> Операторы](string-view-operators.md) используют эту функцию члена для сравнения.

```cpp
constexpr int compare(basic_string_view strv) const noexcept;
constexpr int compare(size_type pos, size_type num, basic_string_view strv) const;
constexpr int compare(size_type pos, size_type num, basic_string_view strv, size_type offset, size_type num2) const;
constexpr int compare(const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr, size_type num2) const;
```

### <a name="parameters"></a>Параметры

*стрв*\
String_view, который необходимо сравнить с этим string_viewом.

*POS*\
Индекс этого string_view, с которого начинается сравнение.

*блока*\
Максимальное число символов из этого string_view для сравнения.

*NUM2*\
Максимальное число сравниваемых символов из *стрв* .

*offset*\
Индекс *стрв* , с которого начинается сравнение.

*ptr*\
Строка C, сравниваемая с этим string_viewом.

### <a name="return-value"></a>Возвращаемое значение

- Отрицательное значение, если оно `string_view` меньше *стрв* или *ptr*
- Нуль, если две последовательности символов равны
- Положительное значение, если оно `string_view` больше *стрв* или *ptr*

### <a name="remarks"></a>Комментарии

`compare`Функции-члены выполняют сравнение с учетом регистра либо всей последовательности символов, либо ее части.

### <a name="example"></a>Пример

```cpp
// basic_string_view_compare.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>
#include <string>

using namespace std;

string to_alpha(int result)
{
   if (result < 0) return " less than ";
   else if (result == 0) return " equal to ";
   else return " greater than ";
}

int main()
{
   // The first member function compares
   // two string_views
   string_view sv_A("CAB");
   string_view sv_B("CAB");
   cout << "sv_A is " << sv_A << endl;
   cout << "sv_B is " << sv_B << endl;
   int comp1 = sv_A.compare(sv_B);
   cout << "sv_A is" << to_alpha(comp1) << "sv_B.\n";

   // The second member function compares part of
   // an operand string_view to another string_view
   string_view sv_C("AACAB");
   string_view sv_D("CAB");
   cout << "sv_C is: " << sv_C << endl;
   cout << "sv_D is: " << sv_D << endl;
   int comp2a = sv_C.compare(2, 3, sv_D);
   cout << "The last three characters of sv_C are"
       << to_alpha(comp2a) << "sv_D.\n";

   int comp2b = sv_C.compare(0, 3, sv_D);
   cout << "The first three characters of sv_C are"
       << to_alpha(comp2b) << "sv_D.\n";

   // The third member function compares part of
   // an operand string_view to part of another string_view
   string_view sv_E("AACAB");
   string_view sv_F("DCABD");
   cout << "sv_E: " << sv_E << endl;
   cout << "sv_F is: " << sv_F << endl;
   int comp3a = sv_E.compare(2, 3, sv_F, 1, 3);
   cout << "The three characters from position 2 of sv_E are"
       << to_alpha(comp3a)
       << "the 3 characters of sv_F from position 1.\n";

   // The fourth member function compares
   // an operand string_view to a C string
   string_view sv_G("ABC");
   const char* cs_A = "DEF";
   cout << "sv_G is: " << sv_G << endl;
   cout << "cs_A is: " << cs_A << endl;
   int comp4a = sv_G.compare(cs_A);
   cout << "sv_G is" << to_alpha(comp4a) << "cs_A.\n";

   // The fifth member function compares part of
   // an operand string_view to a C string
   string_view sv_H("AACAB");
   const char* cs_B = "CAB";
   cout << "sv_H is: " << sv_H << endl;
   cout << "cs_B is: " << cs_B << endl;
   int comp5a = sv_H.compare(2, 3, cs_B);
   cout << "The last three characters of sv_H are"
      << to_alpha(comp5a) << "cs_B.\n";

   // The sixth member function compares part of
   // an operand string_view to part of an equal length of
   // a C string
   string_view sv_I("AACAB");
   const char* cs_C = "ACAB";
   cout << "sv_I is: " << sv_I << endl;
   cout << "cs_C: " << cs_C << endl;
   int comp6a = sv_I.compare(1, 3, cs_C, 3);
   cout << "The 3 characters from position 1 of sv_I are"
      << to_alpha(comp6a) << "the first 3 characters of cs_C.\n";
}
```

```Output
sv_A is CAB
sv_B is CAB
sv_A is equal to sv_B.
sv_C is: AACAB
sv_D is: CAB
The last three characters of sv_C are equal to sv_D.
The first three characters of sv_C are less than sv_D.
sv_E: AACAB
sv_F is: DCABD
The three characters from position 2 of sv_E are equal to the 3 characters of sv_F from position 1.
sv_G is: ABC
cs_A is: DEF
sv_G is less than cs_A.
sv_H is: AACAB
cs_B is: CAB
The last three characters of sv_H are equal to cs_B.
sv_I is: AACAB
cs_C: ACAB
The 3 characters from position 1 of sv_I are equal to the first 3 characters of cs_C.
```

## <a name="basic_string_viewcopy"></a><a name="copy"></a> basic_string_view:: Copy

Копирует не более указанного числа символов из индексированной позиции в исходном string_view в целевой массив символов. Вместо этого рекомендуется использовать безопасную функцию [basic_string_view:: _Copy_s](#_copy_s) .

```cpp
size_type copy(charT* ptr, size_type count, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*ptr*\
Целевой массив символов, в который должны быть скопированы элементы.

*count*\
Число символов, которые будут копироваться не более чем из исходного string_view.

*offset*\
Начальное расположение в исходном string_view, из которого должны быть сделаны копии.

### <a name="return-value"></a>Возвращаемое значение

Число скопированных символов.

### <a name="remarks"></a>Комментарии

Символ NULL не добавляется в конец копии.

## <a name="basic_string_view_copy_s"></a><a name="_copy_s"></a> basic_string_view:: _Copy_s

Вместо [копирования](#copy)используется безопасная функция копирования CRT.

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Параметры

*dest*\
Целевой массив символов, в который должны быть скопированы элементы.

*dest_size*\
Размер *dest*.

_ *Подсчитайте* количество символов, которые будут копироваться не чаще, из исходной строки.

*_Off*\
Начальная позиция в исходной строке, из которой должны быть сделаны копии.

### <a name="return-value"></a>Возвращаемое значение

Число скопированных символов.

### <a name="remarks"></a>Комментарии

Символ NULL не добавляется в конец копии.

Дополнительные сведения см. [в разделе c-Runtime-Library/Security-Features-in-CRT](../c-runtime-library/security-features-in-the-crt.md).

## <a name="basic_string_viewcrbegin"></a><a name="crbegin"></a> basic_string_view:: crbegin

Возвращает const_reverse_iterator, который обращается к первому элементу в обращенном string_view.

```cpp
constexpr const_reverse_iterator crbegin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Const_reverse_iterator, которая обращается к первому элементу в обращенном string_view.

## <a name="basic_string_viewcrend"></a><a name="crend"></a> basic_string_view:: crend

То же, что и [rend](#rend).

```cpp
constexpr const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает const_reverse_iterator, исходящие за один за концом обращенного string_view.

## <a name="basic_string_viewdata"></a><a name="data"></a> basic_string_view::d ATA

Возвращает необработанный указатель, не являющийся владельцем, для последовательности символов константы объекта, который использовался для создания string_view.

```cpp
constexpr value_type *data() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на константу для первого элемента последовательности символов.

### <a name="remarks"></a>Комментарии

Указатель не может изменить символы.

Последовательность символов string_view не обязательно завершается нулем. Возвращаемый тип для `data` не является допустимой строкой C, так как не добавляется символ null. Символ null "\ 0" не имеет особого смысла в объекте типа string_view и может быть частью string_view объекта так же, как любой другой символ.

## <a name="basic_string_viewempty"></a><a name="empty"></a> basic_string_view:: Empty

Проверяет, содержит ли string_view символы.

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если объект string_view не содержит символов; **`false`** , если у него есть хотя бы один символ.

### <a name="remarks"></a>Комментарии

Функция-член эквивалентна [размеру](#size)() = = 0.

## <a name="basic_string_viewend"></a><a name="end"></a> basic_string_view:: end

Возвращает const_iterator произвольного доступа, указывающий на один за последним элементом.

```cpp
constexpr const_iterator end() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает const_iterator произвольного доступа, указывающий на один за последним элементом.

### <a name="remarks"></a>Комментарии

`end` используется для проверки того, достиг ли const_iterator конца string_view. Значение, возвращаемое, `end` не должно быть разыменовано.

## <a name="basic_string_viewends_with"></a><a name="ends_with"></a> basic_string_view:: ends_with

Проверьте, заканчивается ли представление строки с помощью указанного суффикса.

```cpp
bool ends_with(const CharType c) const noexcept;
bool ends_with(const CharType* const x) const noexcept;
bool ends_with(const basic_string_view sv) const noexcept;
```

### <a name="parameters"></a>Параметры

*c*\
Искомый суффикс одиночных символов.

*sv*\
Строковое представление, содержащее суффикс для поиска. \
Можно передать `std::basic_string` , который преобразует в строковое представление.

*x*\
Строка символов, завершающаяся нулем, содержащая суффикс для поиска.

### <a name="return-value"></a>Возвращаемое значение

`true` значение, если строковое представление заканчивается указанным суффиксом; `false` в противном случае — значение.

### <a name="remarks"></a>Комментарии

`ends_with()` Новое в C++ 20. Чтобы использовать его, укажите параметр компилятора [/std: c + + Latest](../build/reference/std-specify-language-standard-version.md) .

См. [starts_with](#starts_with) , чтобы проверить, начинается ли представление строки с указанного префикса.

### <a name="example"></a>Пример

```cpp
// Requires /std:c++latest
#include <string>
#include <iostream>

int main()
{
    std::cout << std::boolalpha; // so booleans show as 'true'/'false'  
    std::cout << std::string_view("abcdefg").ends_with('g') << '\n';
    std::cout << std::string_view("abcdefg").ends_with("eFg") << '\n';

    std::basic_string<char> str2 = "efg";
    std::cout << std::string_view("abcdefg").ends_with(str2);

    return 0;
}
```

```Output
true
false
true
```

## <a name="basic_string_viewfind"></a><a name="find"></a> basic_string_view:: Find

Выполняет поиск `string_view` в прямом направлении для первого вхождения символа или подстроки, соответствующей указанной последовательности символов.

```cpp
constexpr size_type find(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*str*\
Объект, `string_view` для которого ищется функция-член.

*чвал*\
Значение символа, для которого следует искать функцию-член.

*offset*\
Индекс, с которого начинается поиск.

*ptr*\
Строка C, для которой ищется функция-член.

*count*\
Число символов в *ptr*, считая вперед от первого символа.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `npos`.

## <a name="basic_string_viewfind_first_not_of"></a><a name="find_first_not_of"></a> basic_string_view:: find_first_not_of

Выполняет поиск первого символа, который не является элементом указанного string_view или преобразуемого строкового объекта.

```cpp
constexpr size_type find_first_not_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*str*\
String_view, для которого ищется функция-член.

*чвал*\
Значение символа, для которого следует искать функцию-член.

*offset*\
Индекс, с которого начинается поиск.

*ptr*\
Строка C, для которой ищется функция-член.

*count*\
Число символов, считая от первого символа в строке C, для которой ищется функция-член.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `npos`.

## <a name="basic_string_viewfind_first_of"></a><a name="find_first_of"></a> basic_string_view:: find_first_of

Выполняет поиск первого символа, соответствующего любому элементу указанного string_view.

```cpp
constexpr size_type find_first_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(const charT* str, size_type offset, size_type count) const;
constexpr size_type find_first_of(const charT* str, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*чвал*\
Значение символа, для которого следует искать функцию-член.

*offset*\
Индекс, с которого начинается поиск.

*ptr*\
Строка C, для которой ищется функция-член.

*count*\
Число символов, считая от первого символа в строке C, для которой ищется функция-член.

*str*\
String_view, для которого ищется функция-член.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `npos`.

## <a name="basic_string_viewfind_last_not_of"></a><a name="find_last_not_of"></a> basic_string_view:: find_last_not_of

Выполняет поиск последнего символа, который не является ни одним элементом указанного string_view.

```cpp
constexpr size_type find_last_not_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Параметры

*str*\
String_view, для которого ищется функция-член.

*чвал*\
Значение символа, для которого следует искать функцию-член.

*offset*\
Индекс, по которому будет завершен Поиск.

*ptr*\
Строка C, для которой ищется функция-член.

*count*\
Число символов, считая от первого символа до знака *ptr*.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `string_view::npos`.

## <a name="basic_string_viewfind_last_of"></a><a name="find_last_of"></a> basic_string_view:: find_last_of

Выполняет поиск последнего символа, соответствующего любому элементу указанного string_view.

```cpp
constexpr size_type find_last_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Параметры

*str*\
String_view, для которого ищется функция-член.

*чвал*\
Значение символа, для которого следует искать функцию-член.

*offset*\
Индекс, по которому будет завершен Поиск.

*ptr*\
Строка C, для которой ищется функция-член.

*count*\
Число символов, считая от первого символа в строке C, для которой ищется функция-член.

### <a name="return-value"></a>Возвращаемое значение

Индекс последнего символа искомой подстроки, если он был успешно найден; в противном случае — `npos`.

## <a name="basic_string_viewfront"></a><a name="front"></a> basic_string_view:: Front

Возвращает const_reference первому элементу.

```cpp
constexpr const_reference front() const;
```

### <a name="return-value"></a>Возвращаемое значение

Const_reference к первому элементу.

### <a name="remarks"></a>Комментарии

Создает исключение, если string_view пуст.

## <a name="basic_string_viewlength"></a><a name="length"></a> basic_string_view:: Length

Возвращает текущее количество элементов.

```cpp
constexpr size_type length() const noexcept;
```

### <a name="remarks"></a>Комментарии

Функция-член такая же, как [size](#size).

## <a name="basic_string_viewmax_size"></a><a name="max_size"></a> basic_string_view:: max_size

Возвращает максимальное число символов, которое может содержать string_view.

```cpp
constexpr size_type max_size() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное число символов, которое может содержать string_view.

### <a name="remarks"></a>Комментарии

Исключение типа [length_error](../standard-library/length-error-class.md) возникает, когда операция создает string_view с длиной больше `max_size()` .

## <a name="basic_string_viewoperator"></a><a name="op_eq"></a> basic_string_view::operator=

Присваивает string_view или преобразуемый строковый объект другому string_viewу.

```cpp
constexpr basic_string_view& operator=(const basic_string_view&) noexcept = default;
```

### <a name="example"></a>Пример

```cpp
   string_view s = "Hello";
   string_view s2 = s;
```

## <a name="basic_string_viewoperator"></a><a name="op_at"></a> basic_string_view::operator[]

Предоставляет const_reference символу с указанным индексом.

```cpp
constexpr const_reference operator[](size_type offset) const;
```

### <a name="parameters"></a>Параметры

*offset*\
Индекс элемента, на который должна указывать ссылка.

### <a name="return-value"></a>Возвращаемое значение

Const_reference символу в позиции, указанной в индексе параметра.

### <a name="remarks"></a>Комментарии

Первый элемент имеет нулевой индекс, а следующие элементы последовательно индексируются положительными целыми числами, поэтому string_view length *n* содержит *n*-й элемент, индексируемый по числу *n* – 1.

`operator[]` работает быстрее, чем функция-член [в](#at) для предоставления доступа для чтения к элементам string_view.

`operator[]` не проверяет, является ли допустимым индекс, переданный в качестве аргумента. Недопустимый индекс, переданный в, `operator[]` приводит к неопределенному поведению.

Возвращаемая ссылка может быть недействительной, если базовые строковые данные изменяются или удаляются объектом-владельцем.

При компиляции с [ \_ \_ \_ уровнем отладки итератора](../standard-library/iterator-debug-level.md) , установленным в значение 1 или 2, возникнет ошибка времени выполнения при попытке доступа к элементу за пределами string_view. Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

## <a name="basic_string_viewrbegin"></a><a name="rbegin"></a> basic_string_view:: rbegin

Возвращает константный итератор к первому элементу в обращенном string_view.

```cpp
constexpr const_reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает итератор произвольного доступа к первому элементу в обращенном string_viewе, что привело к последнему элементу в соответствующем необращенном string_view.

### <a name="remarks"></a>Комментарии

`rbegin` используется с обратным string_view так же, как [Begin](#begin) используется с string_view. `rbegin` может использоваться для обратной инициализации итерации.

## <a name="basic_string_viewremove_prefix"></a><a name="remove_prefix"></a> basic_string_view:: remove_prefix

Перемещает указатель вперед на указанное число элементов.

```cpp
constexpr void remove_prefix(size_type n);
```

### <a name="remarks"></a>Комментарии

Оставляет базовые данные без изменений. Перемещает указатель string_view вперед на n элементов и задает `size` для элемента закрытых данных размер-n.

## <a name="basic_string_viewremove_suffix"></a><a name="remove_suffix"></a> basic_string_view:: remove_suffix

Уменьшает размер представления по заданному числу элементов, начиная с обратного.

```cpp
constexpr void remove_suffix(size_type n);
```

### <a name="remarks"></a>Комментарии

Оставляет базовые данные и указатель на него без изменений. Задает `size` для элемента закрытых данных размер-n.

## <a name="basic_string_viewrend"></a><a name="rend"></a> basic_string_view:: rend

Возвращает константный итератор, указывающий на один за последним элементом в обращенном string_view.

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Константный реверсивный итератор произвольного доступа, указывающий на один за последним элементом в обращенном string_view.

### <a name="remarks"></a>Комментарии

`rend` используется с обратным string_view точно так же, как [End](#end) используется с string_view. `rend` можно использовать для проверки того, достиг ли обратный итератор конца string_view. Значение, возвращаемое, `rend` не должно быть разыменовано.

## <a name="basic_string_viewrfind"></a><a name="rfind"></a> basic_string_view:: рфинд

Ищет в string_view в обратную строку, совпадающую с указанной последовательностью символов.

```cpp
constexpr size_type rfind(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type rfind(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type rfind(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type rfind(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Параметры

*чвал*\
Значение символа, для которого следует искать функцию-член.

*offset*\
Индекс, с которого начинается поиск.

*ptr*\
Строка C, для которой ищется функция-член.

*count*\
Число символов, считая от первого символа в строке C, для которой ищется функция-член.

*str*\
String_view, для которого ищется функция-член.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа подстроки после успешного выполнения; в противном случае — значение `npos` .

## <a name="basic_string_viewsize"></a><a name="size"></a> basic_string_view:: size

Возвращает количество элементов в string_view.

```cpp
constexpr size_type size() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Длина string_view.

### <a name="remarks"></a>Комментарии

String_view может изменить ее длину, например на `remove_prefix` и `remove_suffix` . Так как это не изменяет базовые строковые данные, размер string_view не обязательно должен быть равен размеру базовых данных.

## <a name="basic_string_viewstarts_with"></a><a name="starts_with"></a> basic_string_view:: starts_with

Проверьте, начинается ли строковое представление с указанного префикса.

```cpp
bool starts_with(const CharType c) const noexcept;
bool starts_with(const CharType* const x) const noexcept;
bool starts_with(const basic_string_view sv) const noexcept;
```

### <a name="parameters"></a>Параметры

*c*\
Искомый префикс одного символа.

*sv*\
Строковое представление, содержащее префикс для поиска. \
Можно передать `std::basic_string` , который преобразует в строковое представление.

*x*\
Строка символов, завершающаяся нулем, содержащая префикс для поиска.

### <a name="return-value"></a>Возвращаемое значение

`true` значение, если строка начинается с указанного префикса; `false` в противном случае — значение.

### <a name="remarks"></a>Комментарии

`starts_with()` Новое в C++ 20. Чтобы использовать его, укажите параметр компилятора [/std: c + + Latest](../build/reference/std-specify-language-standard-version.md) .

См. [ends_with](#ends_with) , чтобы проверить, заканчивается ли строка суффиксом.

### <a name="example"></a>Пример

```cpp
// Requires /std:c++latest
#include <string>
#include <iostream>

int main()
{
    std::cout << std::boolalpha; // so booleans show as 'true'/'false'  
    std::cout << std::string_view("abcdefg").starts_with('b') << '\n';
    std::cout << std::string_view("abcdefg").starts_with("aBc") << '\n';

    std::basic_string<char> str2 = "abc";
    std::cout << std::string_view("abcdefg").starts_with(str2);

    return 0;
}
```

```Output
false
false
true
```

## <a name="basic_string_viewsubstr"></a><a name="substr"></a> basic_string_view:: substr

Возвращает string_view, представляющий указанное количество символов из указанной позиции (не более).

```cpp
constexpr basic_string_view substr(size_type offset = 0, size_type count = npos) const;
```

### <a name="parameters"></a>Параметры

*offset*\
Индекс, указывающий элемент в позиции, из которой выполняется копия, со значением по умолчанию 0.

*count*\
Число символов, включаемых в подстроку, если они есть.

### <a name="return-value"></a>Возвращаемое значение

Объект string_view, представляющий указанную подпоследовательность элементов.

## <a name="basic_string_viewswap"></a><a name="swap"></a> basic_string_view:: swap

Обменивает два string_views, иными словами, указатели на базовые строковые данные и значения размера.

```cpp
constexpr void swap(basic_string_view& sv) noexcept;
```

### <a name="parameters"></a>Параметры

*sv*\
Источник string_view, значения указателей и размеров которых должны быть заменены на string_view назначения.

## <a name="see-also"></a>См. также раздел

[\<string_view>](../standard-library/string-view.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
