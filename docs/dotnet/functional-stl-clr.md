---
title: functional (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/functional>
- cliext::binary_delegate
- cliext::binary_delegate_noreturn
- cliext::binary_negate
- cliext::bind1st
- cliext::bind2nd
- cliext::binder1st
- cliext::binder2nd
- cliext::divides
- cliext::equal_to
- cliext::greater
- cliext::greater_equal
- cliext::less
- cliext::less_equal
- cliext::logical_and
- cliext::logical_not
- cliext::logical_or
- cliext::minus
- cliext::modulus
- cliext::multiplies
- cliext::negate
- cliext::not_equal_to
- cliext::not1
- cliext::not2
- cliext::plus
- cliext::unary_delegate
- cliext::unary_delegate_noreturn
- cliext::unary_negate
helpviewer_keywords:
- <functional> header [STL/CLR]
- <cliext/functional> header [STL/CLR]
- functional functions [STL/CLR]
- binary_delegate function [STL/CLR]
- binary_delegate_noreturn function [STL/CLR]
- binary_negate function [STL/CLR]
- bind1st function [STL/CLR]
- bind2nd function [STL/CLR]
- binder1st function [STL/CLR]
- binder2nd function [STL/CLR]
- divides function [STL/CLR]
- equal_to function [STL/CLR]
- greater function [STL/CLR]
- greater_equal function [STL/CLR]
- less function [STL/CLR]
- less_equal function [STL/CLR]
- logical_and function [STL/CLR]
- logical_not function [STL/CLR]
- logical_or function [STL/CLR]
- minus function [STL/CLR]
- modulus function [STL/CLR]
- multiplies function [STL/CLR]
- negate function [STL/CLR]
- not_equal_to function [STL/CLR]
- not1 function [STL/CLR]
- not2 function [STL/CLR]
- plus function [STL/CLR]
- unary_delegate function [STL/CLR]
- unary_delegate_noreturn function [STL/CLR]
- unary_negate function [STL/CLR]
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
ms.openlocfilehash: 9349de8c42bbed72384ea2b61b39bdea82172f9d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221436"
---
# <a name="functional-stlclr"></a>functional (STL/CLR)

Включите заголовок STL/CLR, `<cliext/functional>` чтобы определить несколько классов шаблонов и связанных шаблонов и делегатов и функций.

## <a name="syntax"></a>Синтаксис

```
#include <functional>
```

## <a name="requirements"></a>Требования

**Заголовок:**\<cliext/functional>

**Пространство имен:** cliext

## <a name="declarations"></a>Объявления

|Делегат|Описание|
|--------------|-----------------|
|[binary_delegate (STL/CLR)](#binary_delegate)|Делегат с двумя аргументами.|
|[binary_delegate_noreturn (STL/CLR)](#binary_delegate_noreturn)|Возвращаемый делегат с двумя аргументами **`void`** .|
|[unary_delegate (STL/CLR)](#unary_delegate)|Делегат с одним аргументом.|
|[unary_delegate_noreturn (STL/CLR)](#unary_delegate_noreturn)|Возвращаемый делегат с одним аргументом **`void`** .|

|Class|Описание|
|-----------|-----------------|
|[binary_negate (STL/CLR)](#binary_negate)|Функтор для отрицания функтор с двумя аргументами.|
|[binder1st (STL/CLR)](#binder1st)|Функтор для привязки первого аргумента к функтор с двумя аргументами.|
|[binder2nd (STL/CLR)](#binder2nd)|Функтор привязать второй аргумент к функтор с двумя аргументами.|
|[divides (STL/CLR)](#divides)|Разделить функтор.|
|[equal_to (STL/CLR)](#equal_to)|Эквивалентное сравнение функтор.|
|[greater (STL/CLR)](#greater)|Улучшенное сравнение функтор.|
|[greater_equal (STL/CLR)](#greater_equal)|Функтор сравнения "больше или равно".|
|[less (STL/CLR)](#less)|Меньшее функтор сравнения.|
|[less_equal (STL/CLR)](#less_equal)|Функтор сравнения "меньше или равно".|
|[logical_and (STL/CLR)](#logical_and)|Логические и функтор.|
|[logical_not (STL/CLR)](#logical_not)|Логическое не функтор.|
|[logical_or (STL/CLR)](#logical_or)|Логическое или функтор.|
|[minus (STL/CLR)](#minus)|Вычесть функтор.|
|[modulus (STL/CLR)](#modulus)|Функтор модуля.|
|[multiplies (STL/CLR)](#multiplies)|Умножьте функтор.|
|[negate (STL/CLR)](#negate)|Функтор, возвращающий свой аргумент.|
|[not_equal_to (STL/CLR)](#not_equal_to)|Неравенство сравнения функтор.|
|[plus (STL/CLR)](#plus)|Добавьте функтор.|
|[unary_negate (STL/CLR)](#unary_negate)|Функтор для отрицания функтор с одним аргументом.|

|Компонент|Описание|
|--------------|-----------------|
|[bind1st (STL/CLR)](#bind1st)|Создает binder1st для аргумента и функтор.|
|[bind2nd (STL/CLR)](#bind2nd)|Создает binder2nd для аргумента и функтор.|
|[not1 (STL/CLR)](#not1)|Создает unary_negate для функтор.|
|[not2 (STL/CLR)](#not2)|Создает binary_negate для функтор.|

## <a name="members"></a>Элементы

## <a name="binary_delegate-stlclr"></a><a name="binary_delegate"></a>binary_delegate (STL/CLR)

Класс женереик описывает делегат с двумя аргументами. Он используется для указания делегата в терминах его аргументов и возвращаемых типов.

### <a name="syntax"></a>Синтаксис

```cpp
generic<typename Arg1,
    typename Arg2,
    typename Result>
    delegate Result binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>Параметры

*Arg1*<br/>
Тип первого аргумента.

*Arg2*<br/>
Тип второго аргумента.

*Результат*<br/>
Тип возвращаемого значения.

### <a name="remarks"></a>Примечания

Делегат женереик описывает функцию с двумя аргументами.

Обратите внимание, что для:

`binary_delegate<int, int, int> Fun1;`

`binary_delegate<int, int, int> Fun2;`

типы `Fun1` и `Fun2` являются синонимами, а для:

`delegate int Fun1(int, int);`

`delegate int Fun2(int, int);`

они не относятся к одному типу.

### <a name="example"></a>Пример

```cpp
// cliext_binary_delegate.cpp
// compile with: /clr
#include <cliext/functional>

bool key_compare(wchar_t left, wchar_t right)
    {
    return (left < right);
    }

typedef cliext::binary_delegate<wchar_t, wchar_t, bool> Mydelegate;
int main()
    {
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="binary_delegate_noreturn-stlclr"></a><a name="binary_delegate_noreturn"></a>binary_delegate_noreturn (STL/CLR)

Класс женереик описывает делегат с двумя аргументами, который возвращает **`void`** . Он используется для указания делегата в терминах своего аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
generic<typename Arg1,
    typename Arg2>
    delegate void binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>Параметры

*Arg1*<br/>
Тип первого аргумента.

*Arg2*<br/>
Тип второго аргумента.

### <a name="remarks"></a>Примечания

Делегат женереик описывает функцию с двумя аргументами, которая возвращает **`void`** .

Обратите внимание, что для:

`binary_delegate_noreturn<int, int> Fun1;`

`binary_delegate_noreturn<int, int> Fun2;`

типы `Fun1` и `Fun2` являются синонимами, а для:

`delegate void Fun1(int, int);`

`delegate void Fun2(int, int);`

они не относятся к одному типу.

### <a name="example"></a>Пример

```cpp
// cliext_binary_delegate_noreturn.cpp
// compile with: /clr
#include <cliext/functional>

void key_compare(wchar_t left, wchar_t right)
    {
    System::Console::WriteLine("compare({0}, {1}) = {2}",
        left, right, left < right);
    }

typedef cliext::binary_delegate_noreturn<wchar_t, wchar_t> Mydelegate;
int main()
    {
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);

    kcomp(L'a', L'a');
    kcomp(L'a', L'b');
    kcomp(L'b', L'a');
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(a, a) = False
compare(a, b) = True
compare(b, a) = False
```

## <a name="binary_negate-stlclr"></a><a name="binary_negate"></a>binary_negate (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает логическое значение, не хранящееся в хранимом функтор с двумя аргументами. Он используется для указания объекта функции в терминах хранимой функтор.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Fun>
    ref class binary_negate
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    explicit binary_negate(Fun% functor);
    binary_negate(binary_negate<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*Fun*<br/>
Тип хранимого функтор.

## <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|
|stored_function_type|Тип функтор.|

|Член|Описание|
|------------|-----------------|
|binary_negate|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^ ()|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами, в котором хранится еще два аргумента функтор. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал логическое не из хранимого функтор, вызываемого с двумя аргументами.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_binary_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::less<int> less_op;

    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(),
        cliext::binary_negate<cliext::less<int> >(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not2(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
1 0
```

## <a name="bind1st-stlclr"></a><a name="bind1st"></a>bind1st (STL/CLR)

Создает `binder1st` для аргумента и функтор.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Fun,
    typename Arg>
    binder1st<Fun> bind1st(Fun% functor,
        Arg left);
```

#### <a name="template-parameters"></a>Параметры шаблона

*АРГ*<br/>
Тип аргумента.

*Fun*<br/>
Тип функтор.

#### <a name="function-parameters"></a>Параметры функции

*Функтор*<br/>
Функтор, который необходимо заключить в оболочку.

*слева*<br/>
Первый аргумент для упаковки.

### <a name="remarks"></a>Примечания

Функция-шаблон возвращает [binder1st (STL/CLR)](../dotnet/binder1st-stl-clr.md) `<Fun>(functor, left)` . Его можно использовать как удобный способ заключения функтор с двумя аргументами и его первого аргумента в функтор с одним аргументом, который вызывает его с помощью второго аргумента.

### <a name="example"></a>Пример

```cpp
// cliext_bind1st.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        subfrom3);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind1st(sub_op, 3));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
-1 0
-1 0
```

## <a name="bind2nd-stlclr"></a><a name="bind2nd"></a>bind2nd (STL/CLR)

Создает `binder2nd` для аргумента и функтор.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Fun,
    typename Arg>
    binder2nd<Fun> bind2nd(Fun% functor,
        Arg right);
```

#### <a name="template-parameters"></a>Параметры шаблона

*АРГ*<br/>
Тип аргумента.

*Fun*<br/>
Тип функтор.

#### <a name="function-parameters"></a>Параметры функции

*Функтор*<br/>
Функтор, который необходимо заключить в оболочку.

*Правильно*<br/>
Второй аргумент для переноса.

### <a name="remarks"></a>Примечания

Функция-шаблон возвращает [binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md) `<Fun>(functor, right)` . Его можно использовать в качестве удобного способа заключения функтор с двумя аргументами и второго аргумента в функтор с одним аргументом, который вызывает его с помощью первого аргумента.

### <a name="example"></a>Пример

```cpp
// cliext_bind2nd.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        sub4);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind2nd(sub_op, 4));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
0 -1
0 -1
```

## <a name="binder1st-stlclr"></a><a name="binder1st"></a>binder1st (STL/CLR)

Класс шаблона описывает один аргумент функтор, который при вызове возвращает свой хранимый функтор с двумя аргументами, вызываемый с хранимым первым аргументом и переданным вторым аргументом. Он используется для указания объекта функции в терминах хранимой функтор.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Fun>
    ref class binder1st
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef typename Fun:result_type result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        second_argument_type, result_type>
        delegate_type;

    binder1st(Fun% functor, first_argument_type left);
    binder1st(binder1st<Arg>% right);

    result_type operator()(second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*Fun*<br/>
Тип хранимого функтор.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|
|stored_function_type|Тип функтор.|

|Член|Описание|
|------------|-----------------|
|binder1st|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^ ()|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с одним аргументом, в котором хранится функтор с двумя аргументами и первый аргумент. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал результат вызова хранимого функтор с хранимым первым аргументом и переданным вторым аргументом.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_binder1st.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        subfrom3);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind1st(sub_op, 3));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
-1 0
-1 0
```

## <a name="binder2nd-stlclr"></a><a name="binder2nd"></a>binder2nd (STL/CLR)

Класс шаблона описывает один аргумент функтор, который при вызове возвращает свой хранимый функтор с двумя аргументами, вызываемый с помощью предоставляемого первого аргумента и его хранимого второго аргумента. Он используется для указания объекта функции в терминах хранимой функтор.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Fun>
    ref class binder2nd
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef typename Fun:result_type result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        first_argument_type, result_type>
        delegate_type;

    binder2nd(Fun% functor, second_argument_type left);
    binder2nd(binder2nd<Arg>% right);

    result_type operator()(first_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*Fun*<br/>
Тип хранимого функтор.

## <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|
|stored_function_type|Тип функтор.|

|Член|Описание|
|------------|-----------------|
|binder2nd|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^ ()|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с одним аргументом, в котором хранится функтор с двумя аргументами и вторым аргументом. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал результат вызова хранимого функтор с заданным первым аргументом и хранимым вторым аргументом.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_binder2nd.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        sub4);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind2nd(sub_op, 4));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
0 -1
0 -1
```

## <a name="divides-stlclr"></a><a name="divides"></a>деления (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает первый аргумент, деленный на второй. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class divides
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    divides();
    divides(divides<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов и возвращаемое значение.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|divides|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^ ()|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал первый аргумент, деленный на второй.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_divides.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::divides<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
2 3
```

## <a name="equal_to-stlclr"></a><a name="equal_to"></a>equal_to (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает значение true, только если первый аргумент равен второму. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class equal_to
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    equal_to();
    equal_to(equal_to<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|equal_to|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^ ()|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал значение true, только если первый аргумент равен второму.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_equal_to.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::equal_to<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
```

## <a name="greater-stlclr"></a><a name="greater"></a>выше (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает значение true, только если первый аргумент больше второго. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class greater
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    greater();
    greater(greater<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|greater|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал значение true, только если первый аргумент больше второго.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_greater.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 3 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::greater<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
3 3
1 0
```

## <a name="greater_equal-stlclr"></a><a name="greater_equal"></a>greater_equal (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает значение true, только если первый аргумент больше или равен второму. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class greater_equal
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    greater_equal();
    greater_equal(greater_equal<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|greater_equal|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал значение true, только если первый аргумент больше или равен второму.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_greater_equal.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::greater_equal<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
```

## <a name="less-stlclr"></a><a name="less"></a>less (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает значение true, только если первый аргумент меньше второго. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class less
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    less();
    less(less<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|less|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал значение true только в том случае, если первый аргумент меньше второго.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_less.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::less<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
0 1
```

## <a name="less_equal-stlclr"></a><a name="less_equal"></a>less_equal (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает значение true, только если первый аргумент меньше второго или равен ему. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class less_equal
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    less_equal();
    less_equal(less_equal<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|less_equal|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал значение true только в том случае, если первый аргумент меньше второго или равен ему.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_less_equal.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 3 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::less_equal<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
3 3
0 1
```

## <a name="logical_and-stlclr"></a><a name="logical_and"></a>logical_and (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает значение true, только если оба аргумента и второй тест имеют значение true. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class logical_and
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    logical_and();
    logical_and(logical_and<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|logical_and|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал значение true только в том случае, если оба аргумента и второго теста имеют значение true.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_logical_and.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(2);
    c1.push_back(0);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 1 0" and " 1 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::logical_and<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
2 0
3 0
1 0
```

## <a name="logical_not-stlclr"></a><a name="logical_not"></a>logical_not (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает значение true, только если значение аргумента равно false. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class logical_not
    { // wrap operator()
public:
    typedef Arg argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    logical_not();
    logical_not(logical_not<Arg> %right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|argument_type|Тип аргумента функтор.|
|delegate_type|Тип универсального делегата.|
|result_type|Тип результата функтор.|

|Член|Описание|
|------------|-----------------|
|logical_not|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с одним аргументом. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал значение true только в том случае, если его аргумент проверяется как false.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_logical_not.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c3.begin(), cliext::logical_not<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
0 1
```

## <a name="logical_or-stlclr"></a><a name="logical_or"></a>logical_or (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает значение true, только если первый аргумент или второй из них равен true. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class logical_or
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    logical_or();
    logical_or(logical_or<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|logical_or|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал значение true только в том случае, если первый аргумент или второй из них равен true.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_logical_or.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(2);
    c1.push_back(0);
    Myvector c2;
    c2.push_back(0);
    c2.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 2 0" and " 0 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::logical_or<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
2 0
0 0
1 0
```

## <a name="minus-stlclr"></a><a name="minus"></a>"минус" (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает первый аргумент минус второй. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class minus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    minus();
    minus(minus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов и возвращаемое значение.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|minus|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал первый аргумент минус второй.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_minus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::minus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
2 2
```

## <a name="modulus-stlclr"></a><a name="modulus"></a>модуль (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает первый остаток от деления второго аргумента на второй. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class modulus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    modulus();
    modulus(modulus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов и возвращаемое значение.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|остатка от деления|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал первый остаток от деления второго аргумента на второй.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_modulus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(2);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 2" and " 3 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::modulus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 2
3 1
1 0
```

## <a name="multiplies-stlclr"></a><a name="multiplies"></a>умножение (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает первый аргумент, умноженный на второй. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class multiplies
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    multiplies();
    multiplies(multiplies<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов и возвращаемое значение.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|multiplies|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член `operator()` таким образом, что при вызове объекта в качестве функции он возвращает первый аргумент раз в секунду.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_multiplies.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::multiplies<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
8 3
```

## <a name="negate-stlclr"></a><a name="negate"></a>Инвертировать (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает свой аргумент, который имеет отрицательное значение. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class negate
    { // wrap operator()
public:
    typedef Arg argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    negate();
    negate(negate<Arg>% right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|argument_type|Тип аргумента функтор.|
|delegate_type|Тип универсального делегата.|
|result_type|Тип результата функтор.|

|Член|Описание|
|------------|-----------------|
|negate|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с одним аргументом. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал свой аргумент с отрицанием.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(-3);
    Myvector c3(2, 0);

// display initial contents " 4 -3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c3.begin(), cliext::negate<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 -3
-4 3
```

## <a name="not_equal_to-stlclr"></a><a name="not_equal_to"></a>not_equal_to (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает значение true, только если первый аргумент не равен второму. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class not_equal_to
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    not_equal_to();
    not_equal_to(not_equal_to<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|not_equal_to|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал значение true только в том случае, если первый аргумент не равен второму.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_not_equal_to.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not_equal_to<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
0 1
```

## <a name="not1-stlclr"></a><a name="not1"></a>not1 (STL/CLR)

Создает `unary_negate` для функтор.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Fun>
    unary_negate<Fun> not1(Fun% functor);
```

#### <a name="template-parameters"></a>Параметры шаблона

*Fun*<br/>
Тип функтор.

#### <a name="function-parameters"></a>Параметры функции

*Функтор*<br/>
Функтор, который необходимо заключить в оболочку.

### <a name="remarks"></a>Примечания

Функция-шаблон возвращает [unary_negate (STL/CLR)](../dotnet/unary-negate-stl-clr.md) `<Fun>(functor)` . Его можно использовать в качестве удобного способа создания оболочки для одного аргумента функтор в функтор, который доставляет его логическое значение NOT.

### <a name="example"></a>Пример

```cpp
// cliext_not1.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::logical_not<int> not_op;

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::unary_negate<cliext::logical_not<int> >(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::not1(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
1 0
1 0
```

## <a name="not2-stlclr"></a><a name="not2"></a>not2 (STL/CLR)

Создает `binary_negate` для функтор.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Fun>
    binary_negate<Fun> not2(Fun% functor);
```

#### <a name="template-parameters"></a>Параметры шаблона

*Fun*<br/>
Тип функтор.

#### <a name="function-parameters"></a>Параметры функции

*Функтор*<br/>
Функтор, который необходимо заключить в оболочку.

### <a name="remarks"></a>Примечания

Функция-шаблон возвращает [binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md) `<Fun>(functor)` . Его можно использовать в качестве удобного способа создания оболочки функтор с двумя аргументами в функтор, который доставляет его логическое значение NOT.

### <a name="example"></a>Пример

```cpp
// cliext_not2.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::less<int> less_op;

    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(),
        cliext::binary_negate<cliext::less<int> >(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not2(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
1 0
```

## <a name="plus-stlclr"></a><a name="plus"></a>Plus (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает первый аргумент плюс второй. Вы используете объект функции в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Arg>
    ref class plus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    plus();
    plus(plus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргументов и возвращаемое значение.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|delegate_type|Тип универсального делегата.|
|first_argument_type|Тип первого аргумента функтор.|
|result_type|Тип результата функтор.|
|second_argument_type|Тип второго аргумента функтор.|

|Член|Описание|
|------------|-----------------|
|plus|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|Оператор delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с двумя аргументами. Он определяет оператор-член, `operator()` чтобы при вызове объекта в качестве функции он возвращал первый аргумент плюс второй.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_plus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::plus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
6 4
```

## <a name="unary_delegate-stlclr"></a><a name="unary_delegate"></a>unary_delegate (STL/CLR)

Класс женереик описывает делегат с одним аргументом. Он используется для указания делегата в терминах его аргументов и возвращаемых типов.

### <a name="syntax"></a>Синтаксис

```cpp
generic<typename Arg,
    typename Result>
    delegate Result unary_delegate(Arg);
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргумента.

*Результат*<br/>
Тип возвращаемого значения.

### <a name="remarks"></a>Примечания

Делегат женереик описывает функцию с одним аргументом.

Обратите внимание, что для:

`unary_delegare<int, int> Fun1;`

`unary_delegare<int, int> Fun2;`

типы `Fun1` и `Fun2` являются синонимами, а для:

`delegate int Fun1(int);`

`delegate int Fun2(int);`

они не относятся к одному типу.

### <a name="example"></a>Пример

```cpp
// cliext_unary_delegate.cpp
// compile with: /clr
#include <cliext/functional>

int hash_val(wchar_t val)
    {
    return ((val * 17 + 31) % 67);
    }

typedef cliext::unary_delegate<wchar_t, int> Mydelegate;
int main()
    {
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 5
hash(L'b') = 22
```

## <a name="unary_delegate_noreturn-stlclr"></a><a name="unary_delegate_noreturn"></a>unary_delegate_noreturn (STL/CLR)

Класс женереик описывает делегат с одним аргументом, который возвращает **`void`** . Он используется для указания делегата в терминах своего типа аргумента.

### <a name="syntax"></a>Синтаксис

```cpp
generic<typename Arg>
    delegate void unary_delegate_noreturn(Arg);
```

#### <a name="parameters"></a>Параметры

*АРГ*<br/>
Тип аргумента.

### <a name="remarks"></a>Примечания

Делегат женереик описывает функцию с одним аргументом, которая возвращает **`void`** .

Обратите внимание, что для:

`unary_delegare_noreturn<int> Fun1;`

`unary_delegare_noreturn<int> Fun2;`

типы `Fun1` и `Fun2` являются синонимами, а для:

`delegate void Fun1(int);`

`delegate void Fun2(int);`

они не относятся к одному типу.

### <a name="example"></a>Пример

```cpp
// cliext_unary_delegate_noreturn.cpp
// compile with: /clr
#include <cliext/functional>

void hash_val(wchar_t val)
    {
    System::Console::WriteLine("hash({0}) = {1}",
       val, (val * 17 + 31) % 67);
    }

typedef cliext::unary_delegate_noreturn<wchar_t> Mydelegate;
int main()
    {
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);

    myhash(L'a');
    myhash(L'b');
    return (0);
    }
```

```Output
hash(a) = 5
hash(b) = 22
```

## <a name="unary_negate-stlclr"></a><a name="unary_negate"></a>unary_negate (STL/CLR)

Класс шаблона описывает функтор, который при вызове возвращает логическое значение, а не из хранимого функтор одного аргумента. Он используется для указания объекта функции в терминах хранимой функтор.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Fun>
    ref class unary_negate
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::argument_type argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    unary_negate(Fun% functor);
    unary_negate(unary_negate<Fun>% right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Параметры

*Fun*<br/>
Тип хранимого функтор.

### <a name="member-functions"></a>Функции элементов

|Определение типа|Описание|
|---------------------|-----------------|
|argument_type|Тип аргумента функтор.|
|delegate_type|Тип универсального делегата.|
|result_type|Тип результата функтор.|

|Член|Описание|
|------------|-----------------|
|unary_negate|Конструирует функтор.|

|Оператор|Описание:|
|--------------|-----------------|
|operator()|Вычисление требуемой функции.|
|delegate_type ^|Приводит функтор к делегату.|

### <a name="remarks"></a>Примечания

Класс шаблона описывает функтор с одним аргументом, в котором хранится другой функтор с одним аргументом. Он определяет оператор-член, `operator()` так что при вызове объекта в качестве функции он возвращает логическое не значение хранимого функтор, вызванного с аргументом.

Также можно передать объект в качестве аргумента функции, тип которого — `delegate_type^` и будет преобразован соответствующим образом.

### <a name="example"></a>Пример

```cpp
// cliext_unary_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::logical_not<int> not_op;

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::unary_negate<cliext::logical_not<int> >(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::not1(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
1 0
1 0
```
