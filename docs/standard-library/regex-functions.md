---
title: Функции &lt;regex&gt;
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_match
- regex/std::regex_replace
- regex/std::regex_search
- regex/std::swap
ms.assetid: 91a8314b-6f7c-4e33-b7d6-d8583dd75585
helpviewer_keywords:
- std::regex_match [C++]
- std::regex_replace [C++]
- std::regex_search [C++]
- std::swap [C++]
- std::swap [C++]
ms.openlocfilehash: fd7087025939a0aacf17153f201e37fc377653f9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842875"
---
# <a name="ltregexgt-functions"></a>Функции &lt;regex&gt;

|Имя|Описание|
|-|-|
|[regex_match](#regex_match)|Проверяет, совпадает ли регулярное выражение со всей целевой строкой.|
|[regex_replace](#regex_replace)|Заменяет соответствующие регулярные выражения.|
|[regex_search](#regex_search)|Поиск соответствия регулярному выражению.|
|[swap](#swap)|Меняет местами `basic_regex` два `match_results` объекта или.|

## <a name="regex_match"></a><a name="regex_match"></a> regex_match

Проверяет, совпадает ли регулярное выражение со всей целевой строкой.

```cpp
// (1)
template <class BidIt, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    BidIt first,
    Bidit last,
    match_results<BidIt, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (2)
template <class BidIt, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    BidIt first,
    Bidit last,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (3)
template <class Elem, class Alloc, class RXtraits, class Alloc2>
bool regex_match(
    const Elem *ptr,
    match_results<const Elem*, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (4)
template <class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const Elem *ptr,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (5)
template <class IOtraits, class IOalloc, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    match_results<typename basic_string<Elem, IOtraits, IOalloc>::const_iterator, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (6)
template <class IOtraits, class IOalloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Параметры

*BidIt*\
Тип итератора для подстрок соответствия. В общих случаях это один из `string::const_iterator` , `wstring::const_iterator` `const char*` или `const wchar_t*` .

*Alloc*\
Класс распределителя результатов соответствия.

*Elem*\
Тип элементов для обеспечения соответствия. В общих случаях это `string` , `wstring` `char*` или `wchar_t*` .

*RXtraits*\
Класс характеристик для элементов.

*Alloc2*\
Класс распределителя регулярного выражения.

*IOtraits*\
Класс характеристик строки.

*иоаллок*\
Класс распределителя строк.

*Метки*\
Флаги для соответствий.

*first*\
Начало последовательности для сопоставления.

*last*\
Конец последовательности для сопоставления.

*друг*\
Результаты сопоставления. Соответствует типу Elem: [smatch](../standard-library/regex-typedefs.md#smatch) для `string` , [wsmatch](../standard-library/regex-typedefs.md#wsmatch) для `wstring` , [cmatch](../standard-library/regex-typedefs.md#cmatch) для `char*` или [wcmatch](../standard-library/regex-typedefs.md#wcmatch) для `wchar_t*` .

*ptr*\
Указатель на начало последовательности для сопоставления. Если *ptr* значение PTR `char*` , используйте `cmatch` и `regex` . Если *ptr* `wchar_t*` затем используется PTR, используйте `wcmatch` и `wregex` .

*re*\
Регулярное выражение для сравнения. Введите `regex` для `string` и `char*` , или `wregex` для `wstring` и `wchar_t*` .

*str*\
Сопоставляемая строка. Соответствует типу *elem*.

### <a name="remarks"></a>Примечания

Каждая функция шаблона возвращает значение true только в том случае, если вся *строка* последовательности операндов в точности соответствует аргументу *Re*регулярного выражения. Используйте [regex_search](../standard-library/regex-functions.md#regex_search) , чтобы сопоставить подстроку в целевой последовательности и `regex_iterator` найти несколько совпадений. Функции, принимающие объект `match_results`, указывают в своих членах, выполнено ли сопоставление успешно и, в этом случае, какие группы захвата в регулярном выражении были определены.

Функции, принимающие объект `match_results`, указывают в своих членах, выполнено ли сопоставление успешно и, в этом случае, какие группы захвата в регулярном выражении были определены.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_match.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

using namespace std;

int main()
{
    // (1) with char*
    // Note how const char* requires cmatch and regex
    const char *first = "abc";
    const char *last = first + strlen(first);
    cmatch narrowMatch;
    regex rx("a(b)c");

    bool found = regex_match(first, last, narrowMatch, rx);
    if (found)
        wcout << L"Regex found in abc" << endl;

    // (2) with std::wstring
    // Note how wstring requires wsmatch and wregex.
    // Note use of const iterators cbegin() and cend().
    wstring target(L"Hello");
    wsmatch wideMatch;
    wregex wrx(L"He(l+)o");

    if (regex_match(target.cbegin(), target.cend(), wideMatch, wrx))
        wcout << L"The matching text is:" << wideMatch.str() << endl;

    // (3) with std::string
    string target2("Drizzle");
    regex rx2(R"(D\w+e)"); // no double backslashes with raw string literal

    found = regex_match(target2.cbegin(), target2.cend(), rx2);
    if (found)
        wcout << L"Regex found in Drizzle" << endl;

    // (4) with wchar_t*
    const wchar_t* target3 = L"2014-04-02";
    wcmatch wideMatch2;

    // LR"(...)" is a  raw wide-string literal. Open and close parens
    // are delimiters, not string elements.
    wregex wrx2(LR"(\d{4}(-|/)\d{2}(-|/)\d{2})");
    if (regex_match(target3, wideMatch2, wrx2))
    {
        wcout << L"Matching text: " << wideMatch2.str() << endl;
    }

     return 0;
}
```

```Output
Regex found in abc
The matching text is: Hello
Regex found in Drizzle
The matching text is: 2014-04-02
```

## <a name="regex_replace"></a><a name="regex_replace"></a> regex_replace

Заменяет соответствующие регулярные выражения.

```cpp
template <class OutIt, class BidIt, class RXtraits, class Alloc, class Elem>
OutIt regex_replace(
    OutIt out,
    BidIt first,
    BidIt last,
    const basic_regex<Elem, RXtraits, Alloc>& re,
    const basic_string<Elem>& fmt,
    match_flag_type flags = match_default);

template <class RXtraits, class Alloc, class Elem>
basic_string<Elem> regex_replace(
    const basic_string<Elem>& str,
    const basic_regex<Elem, RXtraits, Alloc>& re,
    const basic_string<Elem>& fmt,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Параметры

*OutIt*\
Тип итератора для замен.

*BidIt*\
Тип итератора для подстрок соответствия.

*RXtraits*\
Класс характеристик для элементов.

*Alloc*\
Класс распределителя регулярного выражения.

*Elem*\
Тип элементов для обеспечения соответствия.

*Метки*\
Флаги для соответствий.

*first*\
Начало последовательности для сопоставления.

*fmt*\
Формат для замен.

*last*\
Конец последовательности для сопоставления.

*out*\
Итератор вывода.

*re*\
Регулярное выражение для сравнения.

*str*\
Сопоставляемая строка.

### <a name="remarks"></a>Примечания

Первая функция конструирует объект [Regex_iterator класса](../standard-library/regex-iterator-class.md) `iter(first, last, re, flags)` и использует его для разбиения входного диапазона `[first, last)` на ряд `T0 M0 T1 M1...TN-1 MN-1 TN` подстрок, где `Mn` — это n-й элемент, обнаруженный итератором. Если совпадения не найдены, `T0` — это весь входной диапазон, а `N` равно нулю. Если `(flags & format_first_only) != 0`, используется только первое соответствие, `T1` — это весь входной текст, который следует за соответствием, а `N` равно 1. Для каждого `i` в диапазоне `[0, N)` , если `(flags & format_no_copy) == 0` он копирует текст из диапазона в `Ti` итератор. *out* Затем он вызывает `m.format(out, fmt, flags)` , где `m` — `match_results` объект, возвращаемый объектом итератора `iter` для этой подпоследовательности `Mi` . Наконец, при `(flags & format_no_copy) == 0` копировании текста из диапазона в `TN` итератор. *out* Функция *возвращает.*

Вторая функция создает локальную переменную `result` типа `basic_string<charT>` и вызывает `regex_replace(back_inserter(result), str.begin(), str.end(), re, fmt, flags)`. Он возвращает `result`.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_replace.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    char buf[20];
    const char *first = "axayaz";
    const char *last = first + strlen(first);
    std::regex rx("a");
    std::string fmt("A");
    std::regex_constants::match_flag_type fonly =
        std::regex_constants::format_first_only;

    *std::regex_replace(&buf[0], first, last, rx, fmt) = '\0';
    std::cout << "replacement == " << &buf[0] << std::endl;

    *std::regex_replace(&buf[0], first, last, rx, fmt, fonly) = '\0';
    std::cout << "replacement == " << &buf[0] << std::endl;

    std::string str("adaeaf");
    std::cout << "replacement == "
        << std::regex_replace(str, rx, fmt) << std::endl;

    std::cout << "replacement == "
        << std::regex_replace(str, rx, fmt, fonly) << std::endl;

    return (0);
}
```

```Output
replacement == AxAyAz
replacement == Axayaz
replacement == AdAeAf
replacement == Adaeaf
```

## <a name="regex_search"></a><a name="regex_search"></a> regex_search

Поиск соответствия регулярному выражению.

```cpp
template <class BidIt, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    BidIt first,
    Bidit last,
    match_results<BidIt, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class BidIt, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    BidIt first,
    Bidit last,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class Elem, class Alloc, class RXtraits, class Alloc2>
bool regex_search(
    const Elem* ptr,
    match_results<const Elem*, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const Elem* ptr,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class IOtraits, class IOalloc, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    match_results<typename basic_string<Elem, IOtraits, IOalloc>::const_iterator, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class IOtraits, class IOalloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Параметры

*BidIt*\
Тип итератора для подстрок соответствия.

*Alloc*\
Класс распределителя результатов соответствия.

*Elem*\
Тип элементов для обеспечения соответствия.

*RXtraits*\
Класс характеристик для элементов.

*Alloc2*\
Класс распределителя регулярного выражения.

*IOtraits*\
Класс характеристик строки.

*иоаллок*\
Класс распределителя строк.

*Метки*\
Флаги для соответствий.

*first*\
Начало последовательности для сопоставления.

*last*\
Конец последовательности для сопоставления.

*друг*\
Результаты сопоставления.

*ptr*\
Указатель на начало последовательности для сопоставления.

*re*\
Регулярное выражение для сравнения.

*str*\
Сопоставляемая строка.

### <a name="remarks"></a>Примечания

Каждая функция-шаблон возвращает значение true, только если поиск *его аргумента* регулярного выражения в последовательности операндов завершается с ошибкой. Функции, принимающие объект `match_results`, указывают в своих членах успешность выполнения поиска и, в этом случае, какие группы захвата в были распознаны в регулярном выражении.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_search.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    const char *first = "abcd";
    const char *last = first + strlen(first);
    std::cmatch mr;
    std::regex rx("abc");
    std::regex_constants::match_flag_type fl =
        std::regex_constants::match_default;

    std::cout << "search(f, f+1, \"abc\") == " << std::boolalpha
        << regex_search(first, first + 1, rx, fl) << std::endl;

    std::cout << "search(f, l, \"abc\") == " << std::boolalpha
        << regex_search(first, last, mr, rx) << std::endl;
    std::cout << "  matched: \"" << mr.str() << "\"" << std::endl;

    std::cout << "search(\"a\", \"abc\") == " << std::boolalpha
        << regex_search("a", rx) << std::endl;

    std::cout << "search(\"xabcd\", \"abc\") == " << std::boolalpha
        << regex_search("xabcd", mr, rx) << std::endl;
    std::cout << "  matched: \"" << mr.str() << "\"" << std::endl;

    std::cout << "search(string, \"abc\") == " << std::boolalpha
        << regex_search(std::string("a"), rx) << std::endl;

    std::string str("abcabc");
    std::match_results<std::string::const_iterator> mr2;
    std::cout << "search(string, \"abc\") == " << std::boolalpha
        << regex_search(str, mr2, rx) << std::endl;
    std::cout << "  matched: \"" << mr2.str() << "\"" << std::endl;

    return (0);
}
```

```Output
search(f, f+1, "abc") == false
search(f, l, "abc") == true
  matched: "abc"
search("a", "abc") == false
search("xabcd", "abc") == true
  matched: "abc"
search(string, "abc") == false
search(string, "abc") == true
  matched: "abc"
```

## <a name="swap"></a><a name="swap"></a> swap

Меняет местами `basic_regex` два `match_results` объекта или.

```cpp
template <class Elem, class RXtraits>
void swap(
    basic_regex<Elem, RXtraits, Alloc>& left,
    basic_regex<Elem, RXtraits>& right) noexcept;

template <class Elem, class IOtraits, class BidIt, class Alloc>
void swap(
    match_results<BidIt, Alloc>& left,
    match_results<BidIt, Alloc>& right) noexcept;
```

### <a name="parameters"></a>Параметры

*Elem*\
Тип элементов для обеспечения соответствия.

*RXtraits*\
Класс характеристик для элементов.

### <a name="remarks"></a>Примечания

Функции-шаблоны обменивают содержимое своих аргументов в постоянном времени и не создают исключений.

### <a name="example"></a>Пример

```cpp
// std__regex__swap.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    std::regex rx0("c(a*)|(b)");
    std::regex rx1;
    std::cmatch mr0;
    std::cmatch mr1;

    swap(rx0, rx1);
    std::regex_search("xcaaay", mr1, rx1);
    swap(mr0, mr1);

    std::csub_match sub = mr0[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;
    std::cout << "string == " << sub << std::endl;

    return (0);
}
```

```Output
matched == true
length == 3
string == aaa
```

## <a name="see-also"></a>См. также раздел

[\<regex>](../standard-library/regex.md)\
[Класс regex_constants](../standard-library/regex-constants-class.md)\
[Класс regex_error](../standard-library/regex-error-class.md)\
[Класс regex_iterator](../standard-library/regex-iterator-class.md)\
[\<regex> операторы](../standard-library/regex-operators.md)\
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)\
[Класс regex_traits](../standard-library/regex-traits-class.md)\
[\<regex> определения типов](../standard-library/regex-typedefs.md)
