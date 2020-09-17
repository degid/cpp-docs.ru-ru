---
title: Класс basic_regex
ms.date: 03/27/2019
f1_keywords:
- regex/std::basic_regex
helpviewer_keywords:
- basic_regex class
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
ms.openlocfilehash: 4348941e065680a54f9bd0c9f5b7ab2ff1af5e56
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219226"
---
# <a name="basic_regex-class"></a>Класс basic_regex

Создание оболочки для регулярного выражения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class RXtraits>
class basic_regex
```

## <a name="parameters"></a>Параметры

*Elem*\
Тип элементов для обеспечения соответствия.

*RXtraits*\
Класс характеристик для элементов.

## <a name="remarks"></a>Примечания

Шаблон класса описывает объект, содержащий регулярное выражение. Объекты этого шаблона класса могут передаваться в функции шаблонов [regex_match](../standard-library/regex-functions.md#regex_match), [regex_search](../standard-library/regex-functions.md#regex_search)и [regex_replace](../standard-library/regex-functions.md#regex_replace), а также подходящие аргументы текстовой строки для поиска текста, соответствующего регулярному выражению. Существует две специализации этого шаблона класса с [регулярным выражением](../standard-library/regex-typedefs.md#regex) определений типов для элементов типа **`char`** и [wregex](../standard-library/regex-typedefs.md#wregex) для элементов типа **`wchar_t`** .

Аргумент шаблона *ркстраитс* описывает различные важные свойства синтаксиса регулярных выражений, поддерживаемых шаблоном класса. Класс, указывающий эти признаки регулярных выражений, должен иметь тот же внешний интерфейс, что и объект типа [Regex_traits Class](../standard-library/regex-traits-class.md).

Некоторые функции принимают последовательность операндов, определяющую регулярное выражение. Такую последовательность операндов можно задать несколькими способами:

`ptr`— Завершающая последовательность, заканчивающаяся нулем (например, строка C для *elem* типа **`char`** ), начиная с `ptr` (которая не должна быть пустым указателем), где завершающий элемент является значением `value_type()` и не является частью последовательности операндов

`ptr`, `count` -- последовательность элементов `count`, начиная с `ptr` (это должен быть не пустой указатель)

`str` -- последовательность, заданная объектом `basic_string``str`

`first`, `last` -- последовательность элементов, разделенная итераторами `first` и `last`, в диапазоне `[first, last)`

`right` -- объект `basic_regex``right`

Эти функции членов также принимают аргумент `flags` , который задает различные параметры интерпретации регулярного выражения в дополнение к описаниям, описанным типом *ркстраитс* .

### <a name="members"></a>Элементы

|Член|Значение по умолчанию|
|-|-|
|общедоступная статическая константа flag_type Икасе|regex_constants:: Икасе|
|открытые статические константы flag_type подпрограмм|regex_constants:: подпрограмм|
|Оптимизация общих статических констант flag_type|regex_constants:: OPTIMIZE|
|Общие статические константы flag_type параметры сортировки|regex_constants:: COLLATE|
|Общие статические константы flag_type ECMAScript|regex_constants:: ECMAScript|
|общедоступная статическая константа flag_type Basic|regex_constants:: Basic|
|открытый статический константный flag_type расширен|regex_constants:: Extended|
|общедоступная статическая константа flag_type awk|regex_constants:: awk|
|открытые статические константы flag_type grep|regex_constants:: grep|
|общедоступная статическая константа flag_type egrep|regex_constants:: egrep|
|частные признаки Ркстраитс||

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_regex](#basic_regex)|Конструирует объект регулярного выражения.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[flag_type](#flag_type)|Тип флагов параметров синтаксиса.|
|[locale_type](#locale_type)|Тип сохраненного объекта языкового стандарта.|
|[value_type](#value_type)|Тип элемента.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[assign](#assign)|Присваивает значение объекту регулярного выражения.|
|[flags](#flags)|Возвращает флаги параметров синтаксиса.|
|[getloc](#getloc)|Возвращает сохраненный объект языкового стандарта.|
|[imbue](#imbue)|Изменяет сохраненный объект языкового стандарта.|
|[mark_count](#mark_count)|Возвращает число сопоставленных частей выражения.|
|[swap](#swap)|Меняет местами два объекта регулярного выражения.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator=](#op_eq)|Присваивает значение объекту регулярного выражения.|

## <a name="requirements"></a>Требования

**Заголовок:**\<regex>

**Пространство имен:** std

## <a name="example"></a>Пример

```cpp
// std__regex__basic_regex.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

using namespace std;

int main()
{
    regex::value_type elem = 'x';
    regex::flag_type flag = regex::grep;

    elem = elem;  // to quiet "unused" warnings
    flag = flag;

    // constructors
    regex rx0;
    cout << "match(\"abc\", \"\") == " << boolalpha
        << regex_match("abc", rx0) << endl;

    regex rx1("abcd", regex::ECMAScript);
    cout << "match(\"abc\", \"abcd\") == " << boolalpha
        << regex_match("abc", rx1) << endl;

    regex rx2("abcd", 3);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx2) << endl;

    regex rx3(rx2);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx3) << endl;

    string str("abcd");
    regex rx4(str);
    cout << "match(string(\"abcd\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx4) << endl;

    regex rx5(str.begin(), str.end() - 1);
    cout << "match(string(\"abc\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx5) << endl;
    cout << endl;

    // assignments
    rx0 = "abc";
    rx0 = rx1;
    rx0 = str;

    rx0.assign("abcd", regex::ECMAScript);
    rx0.assign("abcd", 3);
    rx0.assign(rx1);
    rx0.assign(str);
    rx0.assign(str.begin(), str.end() - 1);

    rx0.swap(rx1);

    // mark_count
    cout << "\"abc\" mark_count == "
        << regex("abc").mark_count() << endl;
    cout << "\"(abc)\" mark_count == "
        << regex("(abc)").mark_count() << endl;

    // locales
    regex::locale_type loc = rx0.imbue(locale());
    cout << "getloc == imbued == " << boolalpha
        << (loc == rx0.getloc()) << endl;

    // initializer_list
    regex rx6({ 'a', 'b', 'c' }, regex::ECMAScript);
    cout << "match(\"abc\") == " << boolalpha
        << regex_match("abc", rx6);
    cout << endl;
}
```

```Output
match("abc", "") == false
match("abc", "abcd") == false
match("abc", "abc") == true
match("abc", "abc") == true
match(string("abcd"), "abc") == false
match(string("abc"), "abc") == true

"abc" mark_count == 0
"(abc)" mark_count == 1
getloc == imbued == true
match("abc") == true
```

## <a name="basic_regexassign"></a><a name="assign"></a>basic_regex:: Assign

Присваивает значение объекту регулярного выражения.

```cpp
basic_regex& assign(
    const basic_regex& right);

basic_regex& assign(
    const Elem* ptr,
    flag_type flags = ECMAScript);

basic_regex& assign(
    const Elem* ptr,
    size_type len,
    flag_type flags = ECMAScript);

basic_regex& assign(
    initializer_list<_Elem> IList,
    flag_type flags = regex_constants::ECMAScript);

template <class STtraits, class STalloc>
basic_regex& assign(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags = ECMAScript);

template <class InIt>
basic_regex& assign(
    InIt first, InIt last,
    flag_type flags = ECMAScript);
```

### <a name="parameters"></a>Параметры

*сттраитс*\
Класс признаков для источника строки.

*сталлок*\
Класс распределителя для источника строки.

*Ini*\
Тип итератора ввода для источника диапазона.

*right*\
Копируемый источник регулярного выражения.

*ptr*\
Копируемый указатель на начало последовательности.

*Метки*\
Добавляемые при копировании флаги вариантов синтаксиса.

*>len/TD*\
Копируемый конец последовательности.

*str*\
Копируемая строка.

*first*\
Копируемое начало последовательности.

*last*\
Копируемый конец последовательности.

*Интерфейс*\
Копируемый initializer_list.

### <a name="remarks"></a>Примечания

Все функции элементов заменяют регулярное выражение, содержащееся в, на **`*this`** регулярное выражение, описываемое последовательностью операндов, а затем возвращает **`*this`** .

## <a name="basic_regexbasic_regex"></a><a name="basic_regex"></a>basic_regex:: basic_regex

Конструирует объект регулярного выражения.

```cpp
basic_regex();

explicit basic_regex(
    const Elem* ptr,
    flag_type flags);

explicit basic_regex(
    const Elem* ptr,
    size_type len,
    flag_type flags);

basic_regex(
    const basic_regex& right);

basic_regex(
    initializer_list<Type> IList,
    flag_type flags);

template <class STtraits, class STalloc>
explicit basic_regex(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags);

template <class InIt>
explicit basic_regex(
    InIt first,
    InIt last,
    flag_type flags);
```

### <a name="parameters"></a>Параметры

*сттраитс*\
Класс признаков для источника строки.

*сталлок*\
Класс распределителя для источника строки.

*Ini*\
Тип итератора ввода для источника диапазона.

*right*\
Копируемый источник регулярного выражения.

*ptr*\
Копируемый указатель на начало последовательности.

*Метки*\
Добавляемые при копировании флаги вариантов синтаксиса.

*>len/TD*\
Копируемый конец последовательности.

*str*\
Копируемая строка.

*first*\
Копируемое начало последовательности.

*last*\
Копируемый конец последовательности.

*Интерфейс*\
Копируемый initializer_list.

### <a name="remarks"></a>Примечания

Все последовательности хранят объект типа `RXtraits`, сконструированный по умолчанию.

Первый конструктор создает пустой объект `basic_regex`. Другие конструкторы создают объект `basic_regex`, который содержит регулярное выражение, описанное последовательностью операндов.

Пустой `basic_regex` объект не соответствует ни одной последовательности символов при передаче в [regex_match](../standard-library/regex-functions.md#regex_match), [regex_search](../standard-library/regex-functions.md#regex_search)или [regex_replace](../standard-library/regex-functions.md#regex_replace).

## <a name="basic_regexflag_type"></a><a name="flag_type"></a>basic_regex:: flag_type

Тип флагов параметров синтаксиса.

```cpp
typedef regex_constants::syntax_option_type flag_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).

## <a name="basic_regexflags"></a><a name="flags"></a>basic_regex:: flags

Возвращает флаги параметров синтаксиса.

```cpp
flag_type flags() const;
```

### <a name="remarks"></a>Примечания

Эта функция-член возвращает значение аргумента `flag_type`, переданного в последний вызов одной из функций-членов [basic_regex::assign](#assign), или, если вызовы не выполнялись, возвращает значение, переданное в конструктор.

## <a name="basic_regexgetloc"></a><a name="getloc"></a>basic_regex:: getloc

Возвращает сохраненный объект языкового стандарта.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Примечания

Функция – член возвращает `traits.` [regex_traits:: getloc](../standard-library/regex-traits-class.md#getloc) `()` .

## <a name="basic_regeximbue"></a><a name="imbue"></a>basic_regex:: imbue

Изменяет сохраненный объект языкового стандарта.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Параметры

*Loc*\
Объект языкового стандарта, который необходимо сохранить.

### <a name="remarks"></a>Примечания

Функция члена удаляет **`*this`** и возвращает `traits.` [regex_traits:: imbue](../standard-library/regex-traits-class.md#imbue) `(loc)` .

## <a name="basic_regexlocale_type"></a><a name="locale_type"></a>basic_regex:: locale_type

Тип сохраненного объекта языкового стандарта.

```cpp
typedef typename RXtraits::locale_type locale_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом [regex_traits::locale_type](../standard-library/regex-traits-class.md#locale_type).

## <a name="basic_regexmark_count"></a><a name="mark_count"></a>basic_regex:: mark_count

Возвращает число сопоставленных частей выражения.

```cpp
unsigned mark_count() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает число групп записи в регулярном выражении.

## <a name="basic_regexoperator"></a><a name="op_eq"></a>basic_regex::operator=

Присваивает значение объекту регулярного выражения.

```cpp
basic_regex& operator=(const basic_regex& right);

basic_regex& operator=(const Elem *str);

template <class STtraits, class STalloc>
basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);
```

### <a name="parameters"></a>Параметры

*сттраитс*\
Класс признаков для источника строки.

*сталлок*\
Класс распределителя для источника строки.

*right*\
Копируемый источник регулярного выражения.

*str*\
Копируемая строка.

### <a name="remarks"></a>Примечания

Операторы каждый заменяют регулярное выражение, содержащееся в, на **`*this`** регулярное выражение, описываемое последовательностью операндов, а затем возвращает **`*this`** .

## <a name="basic_regexswap"></a><a name="swap"></a>basic_regex:: swap

Меняет местами два объекта регулярного выражения.

```cpp
void swap(basic_regex& right) throw();
```

### <a name="parameters"></a>Параметры

*right*\
Объект регулярного выражения для замены.

### <a name="remarks"></a>Примечания

Функция – член меняет местами регулярные выражения между **`*this`** и *right*. Она делает это в константном времени и не создает исключений.

## <a name="basic_regexvalue_type"></a><a name="value_type"></a>basic_regex:: value_type

Тип элемента.

```cpp
typedef Elem value_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона *elem*.

## <a name="see-also"></a>См. также раздел

[\<regex>](../standard-library/regex.md)\
[regex_match](../standard-library/regex-functions.md#regex_match)\
[regex_search](../standard-library/regex-functions.md#regex_search)\
[regex_replace](../standard-library/regex-functions.md#regex_replace)\
[регулярные](../standard-library/regex-typedefs.md#regex)\
[wregex](../standard-library/regex-typedefs.md#wregex)\
[Класс regex_traits](../standard-library/regex-traits-class.md)
