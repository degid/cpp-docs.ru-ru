---
title: utility (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/utility>
- cliext::pair
- cliext::pair::pair
- cliext::pair::first
- cliext::pair::first_type
- cliext::pair::second
- cliext::pair::second_type
- cliext::pair::swap
- cliext::make_pair
- cliext::pair::operator=
- cliext::pair::operator==
- cliext::pair::operator>=
- cliext::pair::operator>
- cliext::pair::operator!=
- cliext::pair::operator<=
- cliext::pair::operator<
helpviewer_keywords:
- <utility> header [STL/CLR]
- utility header [STL/CLR]
- <cliext/utility> header [STL/CLR]
- first member [STL/CLR]
- first_type member [STL/CLR]
- second member [STL/CLR]
- second_type member [STL/CLR]
- swap member [STL/CLR]
- make_pair function [STL/CLR]
- pair class [STL/CLR]
- pair member [STL/CLR]
- operator== member [STL/CLR]
- operator= member [STL/CLR]
- operator>= member [STL/CLR]
- operator> member [STL/CLR]
- operator!= member [STL/CLR]
- operator<= member [STL/CLR]
- operator< member [STL/CLR]
ms.assetid: fb48cb75-d5ef-47ce-b526-bf60dc86c552
ms.openlocfilehash: b21f9ec2ace54281f30f8f32134c7fb3466a1faa
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214858"
---
# <a name="utility-stlclr"></a>utility (STL/CLR)

Включите заголовок STL/CLR, `<cliext/utility>` чтобы определить класс шаблона `pair` и несколько вспомогательных функций шаблона.

## <a name="syntax"></a>Синтаксис

```cpp
#include <utility>
```

## <a name="requirements"></a>Требования

**Заголовок:**\<cliext/utility>

**Пространство имен:** cliext

## <a name="declarations"></a>Объявления

|Class|Описание:|
|-----------|-----------------|
|[pair (STL/CLR)](#pair)|Создание оболочки для пары элементов.|

|Оператор|Описание|
|--------------|-----------------|
|[operator== (pair) (STL/CLR)](#op_eq)|Сравнение пар "равенство".|
|[operator!= (пара) (STL/CLR)](#op_neq)|Сравнение пар "не равно".|
|[operator< (пары) (STL/CLR)](#op_lt)|Сравнение пар "меньше".|
|[operator \< = (пара) (STL/CLR)](#op_lteq)|Сравнение пар "меньше или равно".|
|[operator> (пары) (STL/CLR)](#op_gt)|Пара "больше, чем сравнение".|
|[operator>= (пары) (STL/CLR)](#op_gteq)|Сравнение пар "больше или равно".|

|Компонент|Описание|
|--------------|-----------------|
|[make_pair (STL/CLR)](#make_pair)|Создайте пару из пары значений.|

## <a name="members"></a>Элементы

## <a name="pair-stlclr"></a><a name="pair"></a>пара (STL/CLR)

Класс шаблона описывает объект, который заключает в оболочку пару значений.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    ref class pair;
```

#### <a name="parameters"></a>Параметры

*Значение1*<br/>
Тип первого упакованного значения.

*Value2*<br/>
Тип второго упакованного значения.

## <a name="members"></a>Элементы

|Определение типа|Описание|
|---------------------|-----------------|
|[pair::first_type (STL/CLR)](#first_type)|Тип первого упакованного значения.|
|[pair::second_type (STL/CLR)](#second_type)|Тип второго упакованного значения.|

|Объект Member|Описание|
|-------------------|-----------------|
|[pair::first (STL/CLR)](#first)|Первое сохраненное значение.|
|[pair::second (STL/CLR)](#second)|Второе сохраненное значение.|

|Функция-член|Описание|
|---------------------|-----------------|
|[pair::pair (STL/CLR)](#pair_pair)|Конструирует объект-пару.|
|[pair::swap (STL/CLR)](#swap)|Меняет местами содержимое двух пар.|

|Оператор|Описание|
|--------------|-----------------|
|[pair::operator= (STL/CLR)](#op_as)|Заменяет сохраненную пару значений.|

## <a name="remarks"></a>Примечания

Объект хранит пару значений. Этот класс шаблона используется для объединения двух значений в один объект. Кроме того, объект `cliext::pair` (описанный здесь) хранит только управляемые типы; для хранения пары неуправляемых типов используйте `std::pair` , объявленную в `<utility>` .

## <a name="pairfirst-stlclr"></a><a name="first"></a>пары:: First (STL/CLR)

Первое упакованное значение.

### <a name="syntax"></a>Синтаксис

```cpp
Value1 first;
```

### <a name="remarks"></a>Примечания

Объект сохраняет первое упакованное значение.

### <a name="example"></a>Пример

```cpp
// cliext_pair_first.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairfirst_type-stlclr"></a><a name="first_type"></a>пара:: first_type (STL/CLR)

Тип первого упакованного значения.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Value1 first_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона *value1*.

### <a name="example"></a>Пример

```cpp
// cliext_pair_first_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairoperator-stlclr"></a><a name="op_as"></a>Оператор пары::operator= (STL/CLR)

Заменяет сохраненную пару значений.

### <a name="syntax"></a>Синтаксис

```cpp
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Пара для копирования.

### <a name="remarks"></a>Примечания

Оператор члена копирует *прямо* в объект, а затем возвращает **`*this`** . Он используется для замены сохраненной пары значений копией сохраненной пары значений в *правой*части.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_as.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

// assign to a new pair
    cliext::pair<wchar_t, int> c2;
    c2 = c1;
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);
    return (0);
    }
```

```Output
[x, 3]
[x, 3]
```

## <a name="pairpair-stlclr"></a><a name="pair_pair"></a>пара::p Air (STL/CLR)

Конструирует объект-пару.

### <a name="syntax"></a>Синтаксис

```cpp
pair();
pair(pair<Coll>% right);
pair(pair<Coll>^ right);
pair(Value1 val1, Value2 val2);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Связывание с хранилищем.

*val1*<br/>
Первое значение для хранения.

*val2*<br/>
Второе значение для хранения.

### <a name="remarks"></a>Примечания

Конструктор:

`pair();`

Инициализирует хранимую пару со значениями, сформированными по умолчанию.

Конструктор:

`pair(pair<Value1, Value2>% right);`

Инициализирует хранимую пару `right.` [парой:: First (STL/CLR)](../dotnet/pair-first-stl-clr.md) и `right.` [парой:: Second (STL/CLR)](../dotnet/pair-second-stl-clr.md).

`pair(pair<Value1, Value2>^ right);`

Инициализирует хранимую пару `right->` [парой:: First (STL/CLR)](../dotnet/pair-first-stl-clr.md) и `right>` [парой:: Second (STL/CLR)](../dotnet/pair-second-stl-clr.md).

Конструктор:

`pair(Value1 val1, Value2 val2);`

Инициализирует хранимую пару с помощью *val1* и *val2*.

### <a name="example"></a>Пример

```cpp
// cliext_pair_construct.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
// construct an empty container
    cliext::pair<wchar_t, int> c1;
    System::Console::WriteLine("[{0}, {1}]",
        c1.first == L'\0' ? "\\0" : "??", c1.second);

// construct with a pair of values
    cliext::pair<wchar_t, int> c2(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

// construct by copying another pair
    cliext::pair<wchar_t, int> c3(c2);
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);

// construct by copying a pair handle
    cliext::pair<wchar_t, int> c4(%c3);
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);

    return (0);
    }
```

```Output
[\0, 0]
[x, 3]
[x, 3]
[x, 3]
```

## <a name="pairsecond-stlclr"></a><a name="second"></a>пара:: Second (STL/CLR)

Второе упакованное значение.

### <a name="syntax"></a>Синтаксис

```cpp
Value2 second;
```

### <a name="remarks"></a>Примечания

Объект хранит второе упакованное значение.

### <a name="example"></a>Пример

```cpp
// cliext_pair_second.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairsecond_type-stlclr"></a><a name="second_type"></a>пара:: second_type (STL/CLR)

Тип второго упакованного значения.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Value2 second_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона *value2*.

### <a name="example"></a>Пример

```cpp
// cliext_pair_second_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairswap-stlclr"></a><a name="swap"></a>пары:: Swap (STL/CLR)

Меняет местами содержимое двух пар.

### <a name="syntax"></a>Синтаксис

```cpp
void swap(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Связывание с содержимым для замены.

### <a name="remarks"></a>Примечания

Функция – член меняет местами хранимую пару значений между **`*this`** и *right*.

### <a name="example"></a>Пример

```cpp
// cliext_pair_swap.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
    {
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    cliext::deque<wchar_t> d2(5, L'x');
    Mycoll c2(%d2);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// swap and redisplay
    c1.swap(c2);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
x x x x x
x x x x x
a b c
```

## <a name="make_pair-stlclr"></a><a name="make_pair"></a>make_pair (STL/CLR)

Создайте `pair` из пары значений.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);
```

#### <a name="parameters"></a>Параметры

*Значение1*<br/>
Тип первого упакованного значения.

*Value2*<br/>
Тип второго упакованного значения.

*first*<br/>
Первое значение для переноса.

*second*<br/>
Второе значение для переноса.

### <a name="remarks"></a>Примечания

Функция шаблона возвращает `pair<Value1, Value2>(first, second)`. Он используется для создания `pair<Value1, Value2>` объекта из пары значений.

### <a name="example"></a>Пример

```cpp
// cliext_make_pair.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    c1 = cliext::make_pair(L'y', 4);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    return (0);
    }
```

```Output
[x, 3]
[y, 4]
```

## <a name="operator-pair-stlclr"></a><a name="op_neq"></a>operator!= (пара) (STL/CLR)

Сравнение пар "не равно".

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator!=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Для сравнения — правая пара.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `!(left == right)` . Он используется для проверки, не упорядочивается ли *Left* *так, как если* бы две пары сравнивались по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_ne.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] != [x 3] is {0}",
        c1 != c1);
    System::Console::WriteLine("[x 3] != [x 4] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] != [x 3] is False
[x 3] != [x 4] is True
```

## <a name="operatorlt-pair-stlclr"></a><a name="op_lt"></a>Оператор &lt; (паре) (STL/CLR)

Сравнение пар "меньше".

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator<(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Для сравнения — правая пара.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second` . Он используется для проверки, упорядочивается ли *Left* *справа* , когда две пары сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_lt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] < [x 3] is {0}",
        c1 < c1);
    System::Console::WriteLine("[x 3] < [x 4] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] < [x 3] is False
[x 3] < [x 4] is True
```

## <a name="operatorlt-pair-stlclr"></a><a name="op_lteq"></a>operator &lt; = (пара) (STL/CLR)

Сравнение пар "меньше или равно".

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator<=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Для сравнения — правая пара.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `!(right < left)` . Он используется для проверки, не упорядочен ли *Left* после *right* , когда две пары сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_le.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] <= [x 3] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] <= [x 3] is True
[x 4] <= [x 3] is False
```

## <a name="operator-pair-stlclr"></a><a name="op_eq"></a>operator = = (пара) (STL/CLR)

Сравнение пар "равенство".

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator==(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Для сравнения — правая пара.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `left.first ==` `right.first &&` `left.second ==` `right.second` . Он используется для проверки, упорядочивается ли *Left* так же, как и *справа* , если две пары сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_eq.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] == [x 3] is {0}",
        c1 == c1);
    System::Console::WriteLine("[x 3] == [x 4] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] == [x 3] is True
[x 3] == [x 4] is False
```

## <a name="operatorgt-pair-stlclr"></a><a name="op_gt"></a>Оператор &gt; (паре) (STL/CLR)

Пара "больше, чем сравнение".

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator>(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Для сравнения — правая пара.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `right` `<` `left` . Он используется для проверки, упорядочен ли *Left* после *right* , когда две пары сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_gt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] > [x 3] is {0}",
        c1 > c1);
    System::Console::WriteLine("[x 4] > [x 3] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] > [x 3] is False
[x 4] > [x 3] is True
```

## <a name="operatorgt-pair-stlclr"></a><a name="op_gteq"></a>operator &gt; = (пара) (STL/CLR)

Сравнение пар "больше или равно".

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value1,
    typename Value2>
    bool operator>=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левая пара для сравнения.

*Правильно*<br/>
Для сравнения — правая пара.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `!(left < right)` . Используйте его, чтобы проверить, не упорядочивается ли *Left* перед *right* , когда две пары сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_pair_operator_ge.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] >= [x 3] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] >= [x 3] is True
[x 3] >= [x 4] is False
```
