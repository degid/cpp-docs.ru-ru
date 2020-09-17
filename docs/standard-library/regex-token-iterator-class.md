---
title: Класс regex_token_iterator
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_token_iterator
- regex/std::regex_token_iterator::regex_type
- regex/std::regex_token_iterator::value_type
- regex/std::regex_token_iterator::iterator_category
- regex/std::regex_token_iterator::difference_type
- regex/std::regex_token_iterator::pointer
- regex/std::regex_token_iterator::reference
- regex/std::regex_token_iterator::operator==
- regex/std::regex_token_iterator::operator!=
- regex/std::regex_token_iterator::operator*
- regex/std::regex_token_iterator::operator->
- regex/std::regex_token_iterator::operator++
helpviewer_keywords:
- std::regex_token_iterator [C++]
- std::regex_token_iterator [C++], regex_type
- std::regex_token_iterator [C++], value_type
- std::regex_token_iterator [C++], iterator_category
- std::regex_token_iterator [C++], difference_type
- std::regex_token_iterator [C++], pointer
- std::regex_token_iterator [C++], reference
ms.assetid: a213ba48-8e4e-4b6b-871a-2637acf05f15
ms.openlocfilehash: 5ada2ad69cbcac15e09968045e54095dfb2623d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366404"
---
# <a name="regex_token_iterator-class"></a>Класс regex_token_iterator

Класс итератора для подстрок соответствия.

## <a name="syntax"></a>Синтаксис

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_token_iterator
```

## <a name="parameters"></a>Параметры

*BidIt*\
Тип итератора для подстрок соответствия.

*Elem*\
Тип элементов для обеспечения соответствия.

*RXtraits*\
Класс характеристик для элементов.

## <a name="remarks"></a>Примечания

Шаблон класса описывает постоянный объект итератора вперед. По существу, он содержит объект `regex_iterator` , который использует для поиска соответствий регулярного выражения в последовательности символов. Он извлекает объекты типа `sub_match<BidIt>` , представляющие подстроки соответствия, идентифицируемые значениями индекса в хранимом векторе `subs` , для каждого совпадения регулярного выражения.

Значение индекса -1 обозначает, что последовательность символов начинается сразу после окончания предыдущего совпадения регулярного выражения или в начале последовательности символов, если нет предыдущего совпадения регулярного выражения, и продолжается до (но не включает) первого символа текущего совпадения регулярного выражения или до конца последовательности символов, если нет текущего совпадения. Любое другое значение индекса `idx` определяет содержимое группы записи, содержащейся в `it.match[idx]`.

### <a name="members"></a>Участники

|Участник|Значение по умолчанию|
|-|-|
|`private regex_iterator<BidIt, Elem, RXtraits> it`||
|`private vector<int> subs`||
|`private int pos`||

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[regex_token_iterator](#regex_token_iterator)|Формирует итератор.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[difference_type](#difference_type)|Тип разницы итератора.|
|[iterator_category](#iterator_category)|Тип категории итератора.|
|[pointer](#pointer)|Тип указателя на совпадение.|
|[reference](#reference)|Тип ссылки на подстроку соответствия.|
|[regex_type](#regex_type)|Тип регулярного выражения для сопоставления.|
|[Value_type](#value_type)|Тип подстроки соответствия.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператора!](#op_neq)|Сравнивает итераторы на неравенство.|
|[оператор](#op_star)|Обращается к заданной подстроке соответствия.|
|[оператор](#op_add_add)|Увеличивает значение итератора.|
|[оператора](#op_eq_eq)|Сравнивает итераторы на равенство.|
|[operator->](#op_arrow)|Обращается к заданной подстроке соответствия.|

## <a name="requirements"></a>Требования

**Заголовок:** \<regex>

**Пространство имен:** std

## <a name="example"></a>Пример

```cpp
#include <regex>
#include <iostream>

typedef std::regex_token_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "aaxaayaaz";
    Myiter::regex_type rx("(a)a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

// show whole match
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefix before match
    next = Myiter(pat, pat + strlen(pat), rx, -1);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show (a) submatch only
    next = Myiter(pat, pat + strlen(pat), rx, 1);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefixes and submatches
    std::vector<int> vec;
    vec.push_back(-1);
    vec.push_back(1);
    next = Myiter(pat, pat + strlen(pat), rx, vec);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefixes and whole matches
    int arr[] = {-1, 0};
    next = Myiter(pat, pat + strlen(pat), rx, arr);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == aa
match == aa
match == aa

match ==
match == x
match == y
match == z

match == a
match == a
match == a

match ==
match == a
match == x
match == a
match == y
match == a
match == z

match ==
match == aa
match == x
match == aa
match == y
match == aa
match == z
```

## <a name="regex_token_iteratordifference_type"></a><a name="difference_type"></a>regex_token_iterator::difference

Тип разницы итератора.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `std::ptrdiff_t`.

## <a name="regex_token_iteratoriterator_category"></a><a name="iterator_category"></a>regex_token_iterator::iterator_category

Тип категории итератора.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `std::forward_iterator_tag`.

## <a name="regex_token_iteratoroperator"></a><a name="op_neq"></a>regex_token_iterator::operator!

Сравнивает итераторы на неравенство.

```cpp
bool operator!=(const regex_token_iterator& right);
```

### <a name="parameters"></a>Параметры

*right*\
Итератор для сравнения.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение `!(*this == right)`.

## <a name="regex_token_iteratoroperator"></a><a name="op_star"></a>regex_token_iterator::operator

Обращается к заданной подстроке соответствия.

```cpp
const sub_match<BidIt>& operator*();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает объект `sub_match<BidIt>` , представляющий группу записи, указанную значением индекса `subs[pos]`.

## <a name="regex_token_iteratoroperator"></a><a name="op_add_add"></a>regex_token_iterator::operator

Увеличивает значение итератора.

```cpp
regex_token_iterator& operator++();

regex_token_iterator& operator++(int);
```

### <a name="remarks"></a>Примечания

Если сохраненный итератор `it` является итератором конца последовательности, то первый оператор задает для сохраненного значения `pos` значение `subs.size()` (образуя, тем самым, итератор конца последовательности). В противном случае оператор увеличивает сохраненное значение `pos`. Если результат равен значению `subs.size()`, он задает сохраненное значение `pos` равным нулю и увеличивает значение сохраненного итератора `it`. Если при увеличении сохраненного итератора он остается неравным итератору конца последовательности, оператор не больше ничего не делает. В противном случае, если предыдущее совпадение остановилось в конце последовательности символов, оператор задает для сохраненного значения `pos` значение `subs.size()`. В противном случае оператор многократно увеличивает сохраненное значение `pos` до `pos == subs.size()` или `subs[pos] == -1` (поэтому следующее разыменование итератора возвратит завершающую часть последовательности символов, если одно из значений индекса равно -1). Во всех случаях оператор возвращает объект.

Второй оператор создает копию объекта, увеличивает объект, а затем возвращает копию.

## <a name="regex_token_iteratoroperator"></a><a name="op_eq_eq"></a>regex_token_iterator::operator

Сравнивает итераторы на равенство.

```cpp
bool operator==(const regex_token_iterator& right);
```

### <a name="parameters"></a>Параметры

*right*\
Итератор для сравнения.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение `it == right.it && subs == right.subs && pos == right.pos`.

## <a name="regex_token_iteratoroperator-gt"></a><a name="op_arrow"></a>regex_token_iterator::operator-&gt;

Обращается к заданной подстроке соответствия.

```cpp
const sub_match<BidIt> * operator->();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает указатель на объект `sub_match<BidIt>` , представляющий группу записи, указанную значением индекса `subs[pos]`.

## <a name="regex_token_iteratorpointer"></a><a name="pointer"></a>regex_token_iterator::pointer

Тип указателя на совпадение.

```cpp
typedef sub_match<BidIt> *pointer;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для `sub_match<BidIt>*`, где `BidIt` — параметр шаблона.

## <a name="regex_token_iteratorreference"></a><a name="reference"></a>regex_token_iterator::reference

Тип ссылки на подстроку соответствия.

```cpp
typedef sub_match<BidIt>& reference;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для `sub_match<BidIt>&`, где `BidIt` — параметр шаблона.

## <a name="regex_token_iteratorregex_token_iterator"></a><a name="regex_token_iterator"></a>regex_token_iterator::regex_token_iterator

Формирует итератор.

```cpp
regex_token_iterator();

regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, int submatch = 0,
    regex_constants::match_flag_type f = regex_constants::match_default);

regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, const vector<int> submatches,
    regex_constants::match_flag_type f = regex_constants::match_default);

template <std::size_t N>
regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, const int (&submatches)[N],
    regex_constants::match_flag_type f = regex_constants::match_default);
```

### <a name="parameters"></a>Параметры

*first*\
Начало последовательности для сопоставления.

*last*\
Конец последовательности для сопоставления.

*Повторно*\
Регулярное выражение для соответствий.

*F*\
Флаги для соответствий.

### <a name="remarks"></a>Примечания

Первый конструктор создает итератор конца последовательности.

Второй конструктор создает объект, сохраненный итератор `it` которого инициализируется `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`, сохраненный вектор `subs` которого содержит строго одно целочисленное значение, со значением `submatch`, сохраненное значение `pos` которого равно нулю. Примечание. Получившийся объект извлекает подстроку соответствия, определяемую по значению индекса `submatch` , для каждого успешного совпадения с регулярным выражением.

Третий конструктор создает объект, сохраненный итератор `it` которого инициализируется `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`, сохраненный вектор `subs` которого содержит копию аргумента конструктора `submatches`и сохраненное значение `pos` которого равно нулю.

Четвертый конструктор создает объект, сохраненный итератор `it` которого инициализируется `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`, сохраненный вектор `subs` которого содержит значения `N` , на которые указывает аргумент конструктора `submatches`, и сохраненное значение которого `pos` равно нулю.

## <a name="regex_token_iteratorregex_type"></a><a name="regex_type"></a>regex_token_iterator::regex_type

Тип регулярного выражения для сопоставления.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Примечания

Typedef является синонимом `basic_regex<Elem, RXtraits>`.

## <a name="regex_token_iteratorvalue_type"></a><a name="value_type"></a>regex_token_iterator::value_type

Тип подстроки соответствия.

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для `sub_match<BidIt>`, где `BidIt` — параметр шаблона.

## <a name="see-also"></a>См. также раздел

[\<regex>](../standard-library/regex.md)\
[класс regex_constants](../standard-library/regex-constants-class.md)\
[regex_error класс](../standard-library/regex-error-class.md)\
[\<функции regex>](../standard-library/regex-functions.md)\
[класс regex_iterator](../standard-library/regex-iterator-class.md)\
[\<операторы regex>](../standard-library/regex-operators.md)\
[класс regex_traits](../standard-library/regex-traits-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)
