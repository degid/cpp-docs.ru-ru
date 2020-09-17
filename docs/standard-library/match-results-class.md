---
title: Класс match_results
ms.date: 09/10/2018
f1_keywords:
- regex/std::match_results
helpviewer_keywords:
- match_results class
ms.assetid: b504fdca-e5dd-429d-9960-6e27c9167fa6
ms.openlocfilehash: 8ce9ed987baf63f2cc9f095e2955a8165e977193
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212219"
---
# <a name="match_results-class"></a>Класс match_results

Содержит последовательность подстрок соответствия.

## <a name="syntax"></a>Синтаксис

```cpp
template <class BidIt, class Alloc>
class match_results
```

## <a name="parameters"></a>Параметры

*BidIt*\
Тип итератора для подстрок соответствия.

*Alloc*\
Тип распределителя для управления хранилищем.

## <a name="remarks"></a>Примечания

Шаблон класса описывает объект, управляющий неизменяемой последовательностью элементов типа, `sub_match<BidIt>` сформированных поиском регулярных выражений. Каждый элемент указывает на часть последовательности, которая соответствует группе захвата, соответствующей этому элементу.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[match_results](#match_results)|Создает объект.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Тип распределителя для управления хранилищем.|
|[char_type](#char_type)|Тип элемента.|
|[const_iterator](#const_iterator)|Тип постоянного итератора для подстрок соответствия.|
|[const_reference](#const_reference)|Тип постоянной ссылки на элемент.|
|[difference_type](#difference_type)|Тип разницы итератора.|
|[iterator](#iterator)|Тип итератора для подстрок соответствия.|
|[reference](#reference)|Тип ссылки на элемент.|
|[size_type](#size_type)|Тип числа подстрок соответствия.|
|[string_type](#string_type)|Тип строки.|
|[value_type](#value_type)|Тип подстроки соответствия.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[begin](#begin)|Обозначает начало последовательности подстроки соответствия.|
|[empty](#empty)|Проверяет отсутствие подстрок соответствия.|
|[end](#end)|Обозначает конец последовательности частичного соответствия.|
|[format](#format)|Форматирует подстроки соответствия.|
|[get_allocator](#get_allocator)|Возвращает сохраненный распределитель.|
|[length](#length)|Возвращает длину подстроки соответствия.|
|[max_size](#max_size)|Получает максимальное число подстрок соответствия.|
|[position](#position)|Получает начальное смещение подгруппы.|
|[prefix](#prefix)|Получает последовательность перед первой подстрокой соответствия.|
|[size](#size)|Подсчитывает количество подстрок соответствия.|
|[str](#str)|Возвращает подстроку совпадения.|
|[suffix](#suffix)|Получает последовательность после последней подстроки соответствия.|
|[swap](#swap)|Меняет местами два объекта match_results.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator=](#op_eq)|Копирование объекта match_results.|
|[operator\[\]](#op_at)|Доступ к подчиненному объекту.|

## <a name="requirements"></a>Требования

**Заголовок:**\<regex>

**Пространство имен:** std

## <a name="example"></a>Пример

```cpp
// std__regex__match_results.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    std::regex rx("c(a*)|(b)");
    std::cmatch mr;

    std::regex_search("xcaaay", mr, rx);

    std::cout << "prefix: matched == " << std::boolalpha
        << mr.prefix().matched
        << ", value == " << mr.prefix() << std::endl;
    std::cout << "whole match: " << mr.length() << " chars, value == "
        << mr.str() << std::endl;
    std::cout << "suffix: matched == " << std::boolalpha
        << mr.suffix().matched
        << ", value == " << mr.suffix() << std::endl;
    std::cout << std::endl;

    std::string fmt("\"c(a*)|(b)\" matched \"$&\"\n"
        "\"(a*)\" matched \"$1\"\n"
        "\"(b)\" matched \"$2\"\n");
    std::cout << mr.format(fmt) << std::endl;
    std::cout << std::endl;

    // index through submatches
    for (size_t n = 0; n < mr.size(); ++n)
    {
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha
            << mr[n].matched <<
            " at position " << mr.position(n) << std::endl;
        std::cout << "  " << mr.length(n)
            << " chars, value == " << mr[n] << std::endl;
    }
    std::cout << std::endl;

    // iterate through submatches
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)
    {
        std::cout << "next submatch: matched == " << std::boolalpha
            << it->matched << std::endl;
        std::cout << "  " << it->length()
            << " chars, value == " << *it << std::endl;
    }
    std::cout << std::endl;

    // other members
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;

    std::cmatch::allocator_type al = mr.get_allocator();
    std::cmatch::string_type str = std::string("x");
    std::cmatch::size_type maxsiz = mr.max_size();
    std::cmatch::char_type ch = 'x';
    std::cmatch::difference_type dif = mr.begin() - mr.end();
    std::cmatch::const_iterator cit = mr.begin();
    std::cmatch::value_type val = *cit;
    std::cmatch::const_reference cref = val;
    std::cmatch::reference ref = val;

    maxsiz = maxsiz;  // to quiet "unused" warnings
    if (ref == cref)
        ch = ch;
    dif = dif;

    return (0);
}
```

```Output
prefix: matched == true, value == x
whole match: 4 chars, value == caaa
suffix: matched == true, value == y

"c(a*)|(b)" matched "caaa"
"(a*)" matched "aaa"
"(b)" matched ""

submatch[0]: matched == true at position 1
  4 chars, value == caaa
submatch[1]: matched == true at position 2
  3 chars, value == aaa
submatch[2]: matched == false at position 6
  0 chars, value ==

next submatch: matched == true
  4 chars, value == caaa
next submatch: matched == true
  3 chars, value == aaa
next submatch: matched == false
  0 chars, value ==

empty == false
```

## <a name="match_resultsallocator_type"></a><a name="allocator_type"></a>match_results::allocator_type

Тип распределителя для управления хранилищем.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Примечания

Typedef является синонимом для *выделения*аргумента шаблона.

## <a name="match_resultsbegin"></a><a name="begin"></a>match_results::Begin

Обозначает начало последовательности подстроки соответствия.

```cpp
const_iterator begin() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает итератор произвольного доступа, указывающий на первый элемент последовательности (или на место сразу за концом пустой последовательности).

## <a name="match_resultschar_type"></a><a name="char_type"></a>match_results::char_type

Тип элемента.

```cpp
typedef typename iterator_traits<BidIt>::value_type char_type;
```

### <a name="remarks"></a>Примечания

Определение типа является синонимом типа `iterator_traits<BidIt>::value_type`, который является типом элемента искомой последовательности символов.

## <a name="match_resultsconst_iterator"></a><a name="const_iterator"></a>match_results::const_iterator

Тип постоянного итератора для подстрок соответствия.

```cpp
typedef T0 const_iterator;
```

### <a name="remarks"></a>Примечания

Определение типа описывает объект, который можно использовать в качестве постоянного итератора с произвольным доступом для управляемой последовательности.

## <a name="match_resultsconst_reference"></a><a name="const_reference"></a>match_results::const_reference

Тип постоянной ссылки на элемент.

```cpp
typedef const typename Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Примечания

Определение типа описывает объект, который можно использовать в качестве постоянной ссылки на элемент управляемой последовательности.

## <a name="match_resultsdifference_type"></a><a name="difference_type"></a>match_results::difference_type

Тип разницы итератора.

```cpp
typedef typename iterator_traits<BidIt>::difference_type difference_type;
```

### <a name="remarks"></a>Примечания

Определение типа является синонимом типа `iterator_traits<BidIt>::difference_type`; оно описывает объект, который может представлять разницу между любыми двумя итераторами, указывающими на элементы управляемой последовательности.

## <a name="match_resultsempty"></a><a name="empty"></a>match_results::empty

Проверяет отсутствие подстрок соответствия.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает значение true, только если не удалось найти регулярное выражение.

## <a name="match_resultsend"></a><a name="end"></a>match_results::end

Обозначает конец последовательности частичного соответствия.

```cpp
const_iterator end() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает итератор, указывающий на место сразу за концом последовательности.

## <a name="match_resultsformat"></a><a name="format"></a>match_results::format

Форматирует подстроки соответствия.

```cpp
template <class OutIt>
OutIt format(OutIt out,
    const string_type& fmt, match_flag_type flags = format_default) const;

string_type format(const string_type& fmt, match_flag_type flags = format_default) const;
```

### <a name="parameters"></a>Параметры

*OutIt*\
Тип итератора вывода.

*out*\
Поток вывода для записи.

*fmt*\
Строка форматирования.

*Метки*\
Флаги формата.

### <a name="remarks"></a>Примечания

Каждая функция – член создает форматированный текст под элементом управления формата *fmt*. Первая функция – член записывает форматированный текст в последовательность, определенную его аргументом *out* , *и возвращает.* Вторая функция-член возвращает строковый объект, содержащий копию форматированного текста.

Чтобы создать форматированный текст, литеральный текст в строке формата, как правило, копируется в целевую последовательность. Каждая escape-последовательность в строке формата заменяется текстом, который она представляет. Сведениями о копировании и замене управляют флаги формата, передаваемые функции.

## <a name="match_resultsget_allocator"></a><a name="get_allocator"></a>match_results::get_allocator

Возвращает сохраненный распределитель.

```cpp
allocator_type get_allocator() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает копию объекта распределителя, используемого **`*this`** для выделения `sub_match` объектов.

## <a name="match_resultsiterator"></a><a name="iterator"></a>match_results::iterator

Тип итератора для подстрок соответствия.

```cpp
typedef const_iterator iterator;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект, который можно использовать в качестве итератора с произвольным доступом для управляемой последовательности.

## <a name="match_resultslength"></a><a name="length"></a>match_results::length

Возвращает длину подстроки соответствия.

```cpp
difference_type length(size_type sub = 0) const;
```

### <a name="parameters"></a>Параметры

*Директор*\
Индекс подстроки соответствия.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение `(*this)[sub].length()`.

## <a name="match_resultsmatch_results"></a><a name="match_results"></a>match_results::match_results

Создает объект.

```cpp
explicit match_results(const Alloc& alloc = Alloc());

match_results(const match_results& right);
```

### <a name="parameters"></a>Параметры

*Alloc*\
Объект распределителя для сохранения.

*right*\
Копируемый объект match_results.

### <a name="remarks"></a>Примечания

Первый конструктор создает объект `match_results`, который не содержит подстрок совпадения. Второй конструктор конструирует `match_results` объект, который является копией *right*.

## <a name="match_resultsmax_size"></a><a name="max_size"></a>match_results::max_size

Получает максимальное число подстрок соответствия.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает длину самой длинной последовательности, которой объект может управлять.

## <a name="match_resultsoperator"></a><a name="op_eq"></a>match_results::operator=

Копирование объекта match_results.

```cpp
match_results& operator=(const match_results& right);
```

### <a name="parameters"></a>Параметры

*right*\
Копируемый объект match_results.

### <a name="remarks"></a>Примечания

Оператор-член заменяет последовательность, управляемую, на **`*this`** копию последовательности, управляемой *вправо*.

## <a name="match_resultsoperator"></a><a name="op_at"></a>match_results::operator[]

Доступ к подчиненному объекту.

```cpp
const_reference operator[](size_type n) const;
```

### <a name="parameters"></a>Параметры

*\n*\
Индекс подстроки совпадения.

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на элемент *n* управляемой последовательности или ссылку на пустой `sub_match` объект, если `size() <= n` или если группа захвата *n* не была частью совпадения.

## <a name="match_resultsposition"></a><a name="position"></a>match_results::position

Получает начальное смещение подгруппы.

```cpp
difference_type position(size_type sub = 0) const;
```

### <a name="parameters"></a>Параметры

*Директор*\
Индекс подстроки совпадения.

### <a name="remarks"></a>Примечания

Функция-член возвращает `std::distance(prefix().first, (*this)[sub].first)`, то есть расстояние от первого символа в целевой последовательности до первого символа в подстроке соответствия, указанной элементом `n` управляемой последовательности.

## <a name="match_resultsprefix"></a><a name="prefix"></a>match_results::prefix

Получает последовательность перед первой подстрокой соответствия.

```cpp
const_reference prefix() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на объект типа `sub_match<BidIt>` , указывающий на последовательность символов, которая начинается с начала целевой последовательности и заканчивается в `(*this)[0].first`, то есть он указывает на текст, который предшествует сопоставленной части последовательности.

## <a name="match_resultsreference"></a><a name="reference"></a>match_results::reference

Тип ссылки на элемент.

```cpp
typedef const_reference reference;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для типа `const_reference`.

## <a name="match_resultssize"></a><a name="size"></a>match_results::size

Подсчитывает количество подстрок соответствия.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает число, которое на единицу больше, чем количество групп записи в регулярном выражении, использовавшемся для поиска, или значение 0, если поиск не выполнялся.

## <a name="match_resultssize_type"></a><a name="size_type"></a>match_results::size_type

Тип числа подстрок соответствия.

```cpp
typedef typename Alloc::size_type size_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для типа `Alloc::size_type`.

## <a name="match_resultsstr"></a><a name="str"></a>match_results::str

Возвращает подстроку совпадения.

```cpp
string_type str(size_type sub = 0) const;
```

### <a name="parameters"></a>Параметры

*Директор*\
Индекс подстроки совпадения.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение `string_type((*this)[sub])`.

## <a name="match_resultsstring_type"></a><a name="string_type"></a>match_results::string_type

Тип строки.

```cpp
typedef basic_string<char_type> string_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для типа `basic_string<char_type>`.

## <a name="match_resultssuffix"></a><a name="suffix"></a>match_results::suffix

Получает последовательность после последней подстроки соответствия.

```cpp
const_reference suffix() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на объект типа `sub_match<BidIt>` , указывающий на последовательность символов, которая начинается с `(*this)[size() - 1].second` и заканчивается в конце целевой последовательности, то есть он указывает на текст, который следует за сопоставленной частью последовательности.

## <a name="match_resultsswap"></a><a name="swap"></a>match_results::swap

Меняет местами два объекта match_results.

```cpp
void swap(const match_results& right) throw();
```

### <a name="parameters"></a>Параметры

*right*\
Объект match_results для замены.

### <a name="remarks"></a>Примечания

Функция – член меняет местами содержимое **`*this`** и *право* на постоянное время и не создает исключения.

## <a name="match_resultsvalue_type"></a><a name="value_type"></a>match_results::value_type

Тип подстроки соответствия.

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>Примечания

Определение типа является синонимом для типа `sub_match<BidIt>`.

## <a name="see-also"></a>См. также раздел

[\<regex>](../standard-library/regex.md)
