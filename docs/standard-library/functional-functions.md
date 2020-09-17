---
title: Функции &lt;functional&gt;
ms.date: 02/21/2019
f1_keywords:
- functional/std::bind
- functional/std::bind1st
- functional/std::bind2nd
- functional/std::bit_and
- functional/std::bit_not
- functional/std::bit_or
- functional/std::bit_xor
- functional/std::cref
- type_traits/std::cref
- functional/std::mem_fn
- functional/std::mem_fun_ref
- functional/std::not1
- functional/std::not2
- functional/std::not_fn
- functional/std::ptr_fun
- functional/std::ref
- functional/std::swap
helpviewer_keywords:
- std::bind [C++]
- std::bind1st
- std::bind2nd
- std::bit_and [C++]
- std::bit_not [C++]
- std::bit_or [C++]
- std::bit_xor [C++]
- std::cref [C++]
ms.assetid: c34d0b45-50a7-447a-9368-2210d06339a4
ms.openlocfilehash: 5e3aa35395c8fd5a42d7127d0b6072a3edf4ace5
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838091"
---
# <a name="ltfunctionalgt-functions"></a>Функции &lt;functional&gt;

Эти функции являются устаревшими в C++ 11 и удалены в C++ 17:

[bind1st](#bind1st)\
[bind2nd](#bind2nd)\
[mem_fun](#mem_fun)\
[mem_fun_ref](#mem_fun_ref)\
[ptr_fun](#ptr_fun)

Эти функции являются устаревшими в C++ 17:

[not1](#not1)\
[not2](#not2)

## <a name="bind"></a><a name="bind"></a> выполняется

Привязывает аргументы к вызываемому объекту.

```cpp
template <class FT, class T1, class T2, ..., class TN>
    unspecified bind(FT fn, T1 t1, T2 t2, ..., TN tN);

template <class RTy, class FT, class T1, class T2, ..., class TN>
    unspecified bind(FT fn, T1 t1, T2 t2, ..., TN tN);
```

### <a name="parameters"></a>Параметры

*фэй*\
Тип объекта для вызова.

*КОД*\
Тип N-го аргумента вызова.

*FN*\
Объект для вызова.

*Код*\
N-й аргумент вызова.

### <a name="remarks"></a>Примечания

Типы `FT, T1, T2, ..., TN` должны быть Copy-конструируемым и `INVOKE(fn, t1, ..., tN)` должны быть допустимыми выражениями для некоторых значений `w1, w2, ..., wN` .

Первая шаблонная функция возвращает пересылающую оболочку вызова `g` со слабым типом результата. Результатом `g(u1, u2, ..., uM)` является `INVOKE(f, v1, v2, ..., vN,` [invoke_result](../standard-library/invoke-result-class.md) `<FT cv (V1, V2, ..., VN)>::type)` , где `cv` — Квалификаторы ОПС, `g` а значения и типы связанных аргументов `v1, v2, ..., vN` определяются, как указано ниже. Его можно использовать для привязки к вызываемому объекту, чтобы создать вызываемый объект с адаптированным списком аргументов.

Вторая шаблонная функция возвращает пересылающую оболочку вызова `g` с вложенным типом `result_type`, который является синонимом для `RTy`. Эффект `g(u1, u2, ..., uM)` — `INVOKE(f, v1, v2, ..., vN, RTy)`, где `cv` — CV-квалификаторы `g`, а значения и типы привязанных аргументов `v1, v2, ..., vN` определяются следующим образом. Его можно использовать для привязки к вызываемому объекту, чтобы создать вызываемый объект с адаптированным списком аргументов и заданным типом возвращаемого значения.

Значения привязанных аргументов `v1, v2, ..., vN` и их соответствующие типы `V1, V2, ..., VN` зависят от типа соответствующего аргумента `ti` типа `Ti` в вызове функции `bind` и CV-квалификаторах `cv` оболочки вызова `g` следующим образом:

если `ti` имеет тип `reference_wrapper<T>`, аргумент `vi` имеет значение `ti.get()`, и его тип `Vi` — `T&`;

Если `std::is_bind_expression<Ti>::value` аргумент имеет значение, **`true`** `vi` `ti(u1, u2, ..., uM)` а его тип — `Vi` `result_of<Ti` `cv` `(U1&, U2&, ..., UN&>::type` ;

Если значение `j` `std::is_placeholder<Ti>::value` не равно нулю, аргумент `vi` имеет `uj` тип `Vi` `Uj&` ;

в противном случае аргумент `vi` имеет `ti` тип и `Vi` имеет значение `Ti` `cv` `&` .

Например, в случае функции `f(int, int)` выражение `bind(f, _1, 0)` возвращает пересылающую оболочку вызова `cw`, чтобы `cw(x)` вызывал `f(x, 0)`. Выражение `bind(f, 0, _1)` возвращает пересылающую оболочку вызова `cw`, чтобы `cw(x)` вызывал `f(0, x)`.

Число аргументов в вызове `bind` и аргументе `fn` должно равняться числу аргументов, которые могут быть переданы в вызываемый объект `fn` . Например, `bind(cos, 1.0)` является правильным, и и, и, `bind(cos)` и `bind(cos, _1, 0.0)` являются неправильными.

Число аргументов в вызове функции, отправляемом в оболочку вызова, возвращаемом методом `bind`, должен быть не меньше наивысшего нумерованного значения `is_placeholder<PH>::value` для всех аргументов-местозаполнителей в вызове в `bind`. Например, `bind(cos, _2)(0.0, 1.0)` является правильным (и возвращает `cos(1.0)` ) и `bind(cos, _2)(0.0)` является неправильным.

### <a name="example"></a>Пример

```cpp
// std__functional__bind.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

void product(double x, double y)
{
    std::cout << x << "*" << y << " == " << x * y << std::endl;
}

int main()
{
    double arg[] = { 1, 2, 3 };

    std::for_each(&arg[0], arg + 3, square);
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(square, _1));

    return (0);
}
```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```

## <a name="bind1st"></a><a name="bind1st"></a> bind1st

Вспомогательная функция шаблона, которая создает адаптер для преобразования объекта бинарной функции в объект унарной функции. Он привязывает первый аргумент бинарной функции к указанному значению. Не рекомендуется использовать в C++ 11, удалено в C++ 17.

```cpp
template <class Operation, class Type>
    binder1st <Operation> bind1st (const Operation& func, const Type& left);
```

### <a name="parameters"></a>Параметры

*func*\
Объект бинарной функции, который необходимо преобразовать в объект унарной функции.

*left*\
Значение, к которому необходимо привязать первый аргумент объекта бинарной функции.

### <a name="return-value"></a>Возвращаемое значение

Объект унарной функции, полученный в результате привязки первого аргумента объекта бинарной функции к значению *Left*.

### <a name="remarks"></a>Примечания

Связыватели функций — это разновидность адаптера функций. Поскольку они возвращают объекты функций, их можно использовать в определенных типах композиций функций для создания более сложных и мощных выражений.

Если *Func* является объектом типа `Operation` и `c` является константой, то он совпадает с `bind1st( func, c )` конструктором класса [binder1st](../standard-library/binder1st-class.md) `binder1st<Operation>(func, c)` и более удобен в использовании.

### <a name="example"></a>Пример

```cpp
// functional_bind1st.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan5: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 5);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( " ;
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind1st(less<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare: counting the number of integers > 5 in the vector
    // with a user defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan5());
    cout << "The number of elements in v1 greater than 5 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind2nd(less<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 5 is: 4.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bind2nd"></a><a name="bind2nd"></a> bind2nd

Вспомогательная функция шаблона, которая создает адаптер для преобразования объекта бинарной функции в объект унарной функции. Он привязывает второй аргумент бинарной функции к указанному значению. Не рекомендуется использовать в C++ 11, удалено в C++ 17.

```cpp
template <class Operation, class Type>
    binder2nd <Operation> bind2nd(const Operation& func, const Type& right);
```

### <a name="parameters"></a>Параметры

*func*\
Объект бинарной функции, который необходимо преобразовать в объект унарной функции.

*right*\
Значение, к которому необходимо привязать второй аргумент объекта бинарной функции.

### <a name="return-value"></a>Возвращаемое значение

Объект унарной функции результат привязки второго аргумента объекта бинарной функции к *правому*.

### <a name="remarks"></a>Примечания

Связыватели функций — это разновидность адаптера функций. Поскольку они возвращают объекты функций, их можно использовать в определенных типах композиций функций для создания более сложных и мощных выражений.

Если *Func* является объектом типа `Operation` и `c` является константой, то то `bind2nd(func, c)` же самое, что и конструктор класса [binder2nd](../standard-library/binder2nd-class.md) `binder2nd<Operation>(func, c)` , и более удобный для использования.

### <a name="example"></a>Пример

```cpp
// functional_bind2nd.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan15: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 15);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare counting the number of integers > 15 in the vector
    // with a user-defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan15());
    cout << "The number of elements in v1 greater than 15 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind1st(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 15 is: 2.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bit_and"></a><a name="bit_and"></a> bit_and

Стандартный объект функции, который выполняет побитовую операцию AND (Binary `operator&` ) в своих аргументах.

```cpp
template <class Type = void>
struct bit_and : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
};

// specialized transparent functor for operator&
template <>
struct bit_and<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const  ->
        decltype(std::forward<T>(Left) & std::forward<U>(Right));
};
```

### <a name="parameters"></a>Параметры

*Тип*, *T*, *U*\
Любой тип, поддерживающий `operator&`, принимающий операнды указанного или выводимого типа.

*Слева*\
Левый операнд побитовой операции И. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа *Type*. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue для выводимого типа *T*.

*right*\
Правый операнд побитовой операции И. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа *Type*. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue для выводимого типа *U*.

### <a name="return-value"></a>Возвращаемое значение

Результат `Left & Right`. Специализированный шаблон выполняет точную пересылку результата типа, возвращаемого `operator&`.

### <a name="remarks"></a>Примечания

Функтор `bit_and` ограничен целочисленными типами для основных типов данных или определяемыми пользователем типами, которые реализуют бинарную `operator&`.

## <a name="bit_not"></a><a name="bit_not"></a> bit_not

Стандартный объект функции, который выполняет операцию побитового дополнения (NOT) `operator~` для аргумента. Добавлено в C++ 14.

```cpp
template <class Type = void>
struct bit_not : public unary_function<Type, Type>
{
    Type operator()(const Type& Right) const;
};

// specialized transparent functor for operator~
template <>
struct bit_not<void>
{
    template <class Type>
    auto operator()(Type&& Right) const -> decltype(~std::forward<Type>(Right));
};
```

### <a name="parameters"></a>Параметры

*Type*\
Тип, поддерживающий унарный `operator~`.

*right*\
Операнд побитовой операции дополнения. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа *Type*. Специализированный шаблон выполняет точную переадресацию ссылочного аргумента lvalue или rvalue *типа*выводимого типа.

### <a name="return-value"></a>Возвращаемое значение

Результат `~ Right`. Специализированный шаблон выполняет точную пересылку результата типа, возвращаемого `operator~`.

### <a name="remarks"></a>Примечания

Функтор `bit_not` ограничен целочисленными типами для основных типов данных или определяемыми пользователем типами, которые реализуют бинарную `operator~`.

## <a name="bit_or"></a><a name="bit_or"></a> bit_or

Стандартный объект функции, который выполняет побитовую операцию OR ( `operator|` ) для своих аргументов.

```cpp
template <class Type = void>
struct bit_or : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
};

// specialized transparent functor for operator|
template <>
struct bit_or<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        -> decltype(std::forward<T>(Left) | std::forward<U>(Right));
};
```

### <a name="parameters"></a>Параметры

*Тип*, *T*, *U*\
Любой тип, поддерживающий `operator|`, принимающий операнды указанного или выводимого типа.

*Слева*\
Левый операнд побитовой операции ИЛИ. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа *Type*. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue для выводимого типа *T*.

*right*\
Правый операнд побитовой операции ИЛИ. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа *Type*. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue для выводимого типа *U*.

### <a name="return-value"></a>Возвращаемое значение

Результат `Left | Right`. Специализированный шаблон выполняет точную пересылку результата типа, возвращаемого `operator|`.

### <a name="remarks"></a>Примечания

Функтор `bit_or` ограничен целочисленными типами для основных типов данных или определяемыми пользователем типами, которые реализуют `operator|`.

## <a name="bit_xor"></a><a name="bit_xor"></a> bit_xor

Стандартный объект функции, который выполняет побитовую операцию XOR (Binary `operator^` ) для своих аргументов.

```cpp
template <class Type = void>
struct bit_xor : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
};

// specialized transparent functor for operator^
template <>
struct bit_xor<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        -> decltype(std::forward<T>(Left) ^ std::forward<U>(Right));
};
```

### <a name="parameters"></a>Параметры

*Тип*, *T*, *U*\
Любой тип, поддерживающий `operator^`, принимающий операнды указанного или выводимого типа.

*Слева*\
Левый операнд побитовой операции "исключающее ИЛИ". Неспециализированный шаблон принимает ссылочный аргумент lvalue типа *Type*. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue для выводимого типа *T*.

*right*\
Правый операнд побитовой операции "исключающее ИЛИ". Неспециализированный шаблон принимает ссылочный аргумент lvalue типа *Type*. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue для выводимого типа *U*.

### <a name="return-value"></a>Возвращаемое значение

Результат `Left ^ Right`. Специализированный шаблон выполняет точную пересылку результата типа, возвращаемого `operator^`.

### <a name="remarks"></a>Примечания

Функтор `bit_xor` ограничен целочисленными типами для основных типов данных или определяемыми пользователем типами, которые реализуют бинарную `operator^`.

## <a name="cref"></a><a name="cref"></a> cref

Создает конструкцию `reference_wrapper` из аргумента.

```cpp
template <class Ty>
reference_wrapper<const Ty> cref(const Ty& arg);

template <class Ty>
reference_wrapper<const Ty> cref(const reference_wrapper<Ty>& arg);
```

### <a name="parameters"></a>Параметры

*Ty*\
Тип аргумента, для которого создается оболочка.

*АРГ*\
Аргумент для создания оболочки.

### <a name="remarks"></a>Примечания

Первая функция возвращает `reference_wrapper<const Ty>(arg.get())`. Используется для создания оболочки для константной ссылки. Вторая функция возвращает `reference_wrapper<const Ty>(arg)`. Используется для восстановления константной ссылки из ссылки в оболочке.

### <a name="example"></a>Пример

```cpp
// std__functional__cref.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    int i = 1;

    std::cout << "i = " << i << std::endl;
    std::cout << "cref(i) = " << std::cref(i) << std::endl;
    std::cout << "cref(neg)(i) = "
        << std::cref(&neg)(i) << std::endl;

    return (0);
    }
```

```Output
i = 1
cref(i) = 1
cref(neg)(i) = -1
```

## <a name="invoke"></a><a name="invoke"></a> вызвать

Вызывает любой вызываемый объект с заданными аргументами. Добавлено в C++ 17.

```cpp
template <class Callable, class... Args>
invoke_result_t<Callable, Args...>
    invoke(Callable&& fn, Args&&... args) noexcept(/* specification */);
```

### <a name="parameters"></a>Параметры

*Предназначен*\
Тип объекта для вызова.

*Args*\
Типы аргументов вызова.

*FN*\
Объект для вызова.

*args*\
Аргументы вызова.

*Описание*\
**`noexcept`** Спецификация `std::is_nothrow_invocable_v<Callable, Args>)` .

### <a name="remarks"></a>Примечания

Вызывает вызываемый объект *fn* с помощью *аргументов*параметров. Фактически, `INVOKE(std::forward<Callable>(fn), std::forward<Args>(args)...)` когда псевдо-функция `INVOKE(f, t1, t2, ..., tN)` означает одно из следующих действий:

- `(t1.*f)(t2, ..., tN)`, если `f` — это указатель на функцию-член класса `T`, а `t1` — это объект типа `T`, ссылка на объект типа `T` или ссылка на объект типа, производного от `T`. То есть, если `std::is_base_of<T, std::decay_t<decltype(t1)>>::value` имеет значение true.

- `(t1.get().*f)(t2, ..., tN)` Если `f` является указателем на функцию-член класса `T` и `std::decay_t<decltype(t1)>` является специализацией `std::reference_wrapper` .

- `((*t1).*f)(t2, ..., tN)` Если `f` является указателем на функцию-член класса `T` и `t1` не является одним из предыдущих типов.

- `t1.*f`, если N == 1, а `f` — это указатель на данные-член класса `T` и `t1` — это объект типа `T`, ссылка на объект типа `T` или ссылка на объект типа, производного от `T`.  То есть, если `std::is_base_of<T, std::decay_t<decltype(t1)>>::value` имеет значение true.

- `t1.get().*f` Если N = = 1 и `f` является указателем на данные члена класса `T` и `std::decay_t<decltype(t1)>` является специализацией `std::reference_wrapper` .

- `(*t1).*f` Если N = = 1 и `f` является указателем на данные члена класса `T` и не является `t1` одним из предыдущих типов.

- `f(t1, t2, ..., tN)` — во всех остальных случаях.

Сведения о типе результата вызываемого объекта см. в разделе [invoke_result](invoke-result-class.md). Для предикатов на вызываемых типах см. раздел [классы is_invocable, is_invocable_r, is_nothrow_invocable is_nothrow_invocable_r](is-invocable-classes.md).

### <a name="example"></a>Пример

```cpp
// functional_invoke.cpp
// compile using: cl /EHsc /std:c++17 functional_invoke.cpp
#include <functional>
#include <iostream>

struct Demo
{
    int n_;

    Demo(int const n) : n_{n} {}

    void operator()( int const i, int const j ) const
    {
        std::cout << "Demo operator( " << i << ", "
            << j << " ) is " << i * j << "\n";
    }

    void difference( int const i ) const
    {
        std::cout << "Demo.difference( " << i << " ) is "
            << n_ - i << "\n";
    }
};

void divisible_by_3(int const i)
{
    std::cout << i << ( i % 3 == 0 ? " is" : " isn't" )
        << " divisible by 3.\n";
}

int main()
{
    Demo d{ 42 };
    Demo * pd{ &d };
    auto pmf = &Demo::difference;
    auto pmd = &Demo::n_;

    // Invoke a function object, like calling d( 3, -7 )
    std::invoke( d, 3, -7 );

    // Invoke a member function, like calling
    // d.difference( 29 ) or (d.*pmf)( 29 )
    std::invoke( &Demo::difference, d, 29 );
    std::invoke( pmf, pd, 13 );

    // Invoke a data member, like access to d.n_ or d.*pmd
    std::cout << "d.n_: " << std::invoke( &Demo::n_, d ) << "\n";
    std::cout << "pd->n_: " << std::invoke( pmd, pd ) << "\n";

    // Invoke a stand-alone (free) function
    std::invoke( divisible_by_3, 42 );

    // Invoke a lambda
    auto divisible_by_7 = []( int const i ) {
        std::cout << i << ( i % 7 == 0 ? " is" : " isn't" )
            << " divisible by 7.\n";
        };
    std::invoke( divisible_by_7, 42 );
}
```

```Output
Demo operator( 3, -7 ) is -21
Demo.difference( 29 ) is 13
Demo.difference( 13 ) is 29
d.n_: 42
pd->n_: 42
42 is divisible by 3.
42 is divisible by 7.
```

## <a name="mem_fn"></a><a name="mem_fn"></a> mem_fn

Создает простую оболочку вызова.

```cpp
template <class RTy, class Ty>
unspecified mem_fn(RTy Ty::*pm);
```

### <a name="parameters"></a>Параметры

*рти*\
Тип возвращаемого значения функции в оболочке.

*Ty*\
Тип указателя функции-члена.

### <a name="remarks"></a>Примечания

Функция шаблона возвращает простую оболочку вызова `cw` с нестрогим типом результата, так что выражение `cw(t, a2, ..., aN)` является таким же, как `INVOKE(pm, t, a2, ..., aN)` . Исключения не вызываются.

Возвращаемая оболочка вызова является производной от `std::unary_function<cv Ty*, RTy>` (и определяет вложенный тип `result_type` как синоним для *РТИ* и вложенный тип `argument_type` как синоним для `cv Ty*` ) только в том случае, если тип *Ty* является указателем на функцию-член с квалификатором ОПС `cv` , который не принимает аргументов.

Возвращаемая оболочка вызова является производной от `std::binary_function<cv Ty*, T2, RTy>` (и определяет вложенный тип `result_type` как синоним для *РТИ*, вложенный тип `first argument_type` как синоним для `cv Ty*` , а вложенный тип `second argument_type` как синоним), `T2` только если тип *Ty* является указателем на функцию-член с квалификатором ОПС `cv` , принимающим один аргумент типа `T2` .

### <a name="example"></a>Пример

```cpp
// std__functional__mem_fn.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

class Funs
    {
public:
    void square(double x)
        {
        std::cout << x << "^2 == " << x * x << std::endl;
        }

    void product(double x, double y)
        {
        std::cout << x << "*" << y << " == " << x * y << std::endl;
        }
    };

int main()
    {
    Funs funs;

    std::mem_fn(&Funs::square)(funs, 3.0);
    std::mem_fn(&Funs::product)(funs, 3.0, 2.0);

    return (0);
    }
```

```Output
3^2 == 9
3*2 == 6
```

## <a name="mem_fun"></a><a name="mem_fun"></a> mem_fun

Вспомогательные функции шаблона, которые используются для создания адаптеров объекта-функции для функций-членов при инициализации с аргументами указателя. Не рекомендуется использовать в C++ 11 для [mem_fn](#mem_fn) и [привязывать](#bind)и удалять в c++ 17.

```cpp
template <class Result, class Type>
mem_fun_t<Result, Type> mem_fun (Result(Type::* pMem)());

template <class Result, class Type, class Arg>
mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pMem)(Arg));

template <class Result, class Type>
const_mem_fun_t<Result, Type> mem_fun(Result (Type::* pMem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pMem)(Arg) const);
```

### <a name="parameters"></a>Параметры

*Виртуаль*\
Указатель на функцию-член класса `Type` для преобразования в объект функции.

### <a name="return-value"></a>Возвращаемое значение

**`const`** Объект или **non_const** функции типа `mem_fun_t` или `mem_fun1_t` .

### <a name="example"></a>Пример

```cpp
// functional_mem_fun.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class StoreVals
{
    int val;
public:
    StoreVals() { val = 0; }
    StoreVals(int j) { val = j; }

    bool display() { cout << val << " "; return true; }
    int squareval() { val *= val; return val; }
    int lessconst(int k) {val -= k; return val; }
};

int main( )
{
    vector<StoreVals *> v1;

    StoreVals sv1(5);
    v1.push_back(&sv1);
    StoreVals sv2(10);
    v1.push_back(&sv2);
    StoreVals sv3(15);
    v1.push_back(&sv3);
    StoreVals sv4(20);
    v1.push_back(&sv4);
    StoreVals sv5(25);
    v1.push_back(&sv5);

    cout << "The original values stored are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun calling member function through a pointer
    // square each value in the vector using squareval ()
    for_each(v1.begin(), v1.end(), mem_fun<int, StoreVals>(&StoreVals::squareval));
    cout << "The squared values are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun1 calling member function through a pointer
    // subtract 5 from each value in the vector using lessconst ()
    for_each(v1.begin(), v1.end(),
        bind2nd (mem_fun1<int, StoreVals,int>(&StoreVals::lessconst), 5));
    cout << "The squared values less 5 are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;
}
```

## <a name="mem_fun_ref"></a><a name="mem_fun_ref"></a> mem_fun_ref

Вспомогательные функции шаблона, которые используются для создания адаптеров объекта-функции для функций-членов при инициализации с помощью ссылочных аргументов. Не рекомендуется использовать в C++ 11, удалено в C++ 17.

```cpp
template <class Result, class Type>
mem_fun_ref_t<Result, Type> mem_fun_ref(Result (Type::* pMem)());

template <class Result, class Type, class Arg>
mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (Type::* pMem)(Arg));

template <class Result, class Type>
const_mem_fun_ref_t<Result, Type> mem_fun_ref(Result Type::* pMem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (T::* pMem)(Arg) const);
```

### <a name="parameters"></a>Параметры

*Виртуаль*\
Указатель на функцию-член класса `Type` для преобразования в объект функции.

### <a name="return-value"></a>Возвращаемое значение

**`const`** `non_const` Объект функции или типа `mem_fun_ref_t` или `mem_fun1_ref_t` .

### <a name="example"></a>Пример

```cpp
// functional_mem_fun_ref.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class NumVals
   {
   int val;
   public:
   NumVals ( ) { val = 0; }
   NumVals ( int j ) { val = j; }

   bool display ( ) { cout << val << " "; return true; }
   bool isEven ( ) { return ( bool )  !( val %2 ); }
   bool isPrime( )
   {
      if (val < 2) { return true; }
      for (int i = 2; i <= val / i; ++i)
      {
         if (val % i == 0) { return false; }
      }
      return true;
   }
};

int main( )
{
   vector <NumVals> v1 ( 13 ), v2 ( 13 );
   vector <NumVals>::iterator v1_Iter, v2_Iter;
   int i, k;

   for ( i = 0; i < 13; i++ ) v1 [ i ] = NumVals ( i+1 );
   for ( k = 0; k < 13; k++ ) v2 [ k ] = NumVals ( k+1 );

   cout << "The original values stored in v1 are: " ;
   for_each( v1.begin( ), v1.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the primes in the vector using isPrime ( )
   v1_Iter = remove_if ( v1.begin( ),  v1.end( ),
      mem_fun_ref ( &NumVals::isPrime ) );
   cout << "With the primes removed, the remaining values in v1 are: " ;
   for_each( v1.begin( ), v1_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   cout << "The original values stored in v2 are: " ;
   for_each( v2.begin( ), v2.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the even numbers in the vector v2 using isEven ( )
   v2_Iter = remove_if ( v2.begin( ),  v2.end( ),
      mem_fun_ref ( &NumVals::isEven ) );
   cout << "With the even numbers removed, the remaining values are: " ;
   for_each( v2.begin( ),  v2_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;
}
```

```Output
The original values stored in v1 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the primes removed, the remaining values in v1 are: 4 6 8 9 10 12
The original values stored in v2 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the even numbers removed, the remaining values are: 1 3 5 7 9 11 13
```

## <a name="not1"></a><a name="not1"></a> not1

Возвращает дополнение унарного предиката. Нерекомендуемый для [not_fn](#not_fn) в c++ 17.

```cpp
template <class UnaryPredicate>
unary_negate<UnaryPredicate> not1(const UnaryPredicate& predicate);
```

### <a name="parameters"></a>Параметры

*предикат*\
Унарный предикат, знак которого должен быть изменен.

### <a name="return-value"></a>Возвращаемое значение

Унарный предикат, который является отрицанием измененного унарного предиката.

### <a name="remarks"></a>Примечания

Если объект создается `unary_negate` из унарного предиката `predicate(x)` , то возвращается значение `!predicate(x)` .

### <a name="example"></a>Пример

```cpp
// functional_not1.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 7; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    // Count the elements greater than 10
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    vector<int>::iterator::difference_type result2;
    // Use the negator to count the elements less than or equal to 10
    result2 = count_if(v1.begin(), v1.end(),
        not1(bind2nd(greater<int>(), 10)));

    cout << "The number of elements in v1 not greater than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
```

## <a name="not2"></a><a name="not2"></a> not2

Возвращает дополнение бинарного предиката. Нерекомендуемый для [not_fn](#not_fn) в c++ 17.

```cpp
template <class BinaryPredicate>
binary_negate<BinaryPredicate> not2(const BinaryPredicate& func);
```

### <a name="parameters"></a>Параметры

*func*\
Бинарный предикат, знак которого должен быть изменен.

### <a name="return-value"></a>Возвращаемое значение

Бинарный предикат, который является отрицанием измененного бинарного предиката.

### <a name="remarks"></a>Примечания

Если объект создается `binary_negate` из бинарного предиката `binary_predicate(x, y)` , возвращается значение `!binary_predicate(x, y)` .

### <a name="example"></a>Пример

```cpp
// functional_not2.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <cstdlib>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   v1.push_back( 6262 );
   v1.push_back( 6262 );
   for ( i = 0 ; i < 5 ; i++ )
   {
      v1.push_back( rand( ) );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use default binary predicate less<int>( )
   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order,
   // use the binary_negate helper function not2
   sort( v1.begin( ), v1.end( ), not2(less<int>( ) ) );
   cout << "Resorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = ( 6262 6262 41 18467 6334 26500 19169 )
Sorted vector v1 = ( 41 6262 6262 6334 18467 19169 26500 )
Resorted vector v1 = ( 26500 19169 18467 6334 6262 6262 41 )
```

## <a name="not_fn"></a><a name="not_fn"></a> not_fn

`not_fn`Шаблон функции принимает вызываемый объект и возвращает вызываемый объект. Если возвращаемый вызываемый объект впоследствии вызывается с некоторыми аргументами, он передается в исходный вызываемый объект и логически инвертирует результат. Он сохраняет квалификацию квалификатора const и значение категории значений для упакованного вызываемого объекта. `not_fn` является новым в c++ 17 и заменяет устаревшие,, `std::not1` `std::not2` `std::unary_negate` и `std::binary_negate` .

```cpp
template <class Callable>
/* unspecified */ not_fn(Callable&& func);
```

### <a name="parameters"></a>Параметры

*func*\
Вызываемый объект, используемый для создания оболочки перенаправленного вызова.

### <a name="remarks"></a>Примечания

Функция шаблона Возвращает оболочку вызова, например `return call_wrapper(std::forward<Callable>(func))` , на основе этого класса, предназначенного только для демонстрации:

```cpp
class call_wrapper
{
   using FD = decay_t<Callable>;
   explicit call_wrapper(Callable&& func);

public:
   call_wrapper(call_wrapper&&) = default;
   call_wrapper(call_wrapper const&) = default;

   template<class... Args>
     auto operator()(Args&&...) & -> decltype(!declval<invoke_result_t<FD&(Args...)>>());

   template<class... Args>
     auto operator()(Args&&...) const& -> decltype(!declval<invoke_result_t<FD const&(Args...)>>());

   template<class... Args>
     auto operator()(Args&&...) && -> decltype(!declval<invoke_result_t<FD(Args...)>>());

   template<class... Args>
     auto operator()(Args&&...) const&& -> decltype(!declval<invoke_result_t<FD const(Args...)>>());

private:
  FD fd;
};
```

Явный конструктор для вызываемого объекта *Func* требует тип `std::decay_t<Callable>` для удовлетворения требований `MoveConstructible` , и `is_constructible_v<FD, Callable>` должен иметь значение true. Он инициализирует вызываемый оберткой объект `fd` из `std::forward<Callable>(func)` и создает все исключения, созданные конструкцией `fd` .

Обертка предоставляет операторы вызова, различающиеся ссылочной категорией lvalue или rvalue и квалификатором const, как показано ниже:

```cpp
template<class... Args> auto operator()(Args&&... args) & -> decltype(!declval<invoke_result_t<FD&(Args...)>>());
template<class... Args> auto operator()(Args&&... args) const& -> decltype(!declval<invoke_result_t<FD const&(Args...)>>());
template<class... Args> auto operator()(Args&&... args) && -> decltype(!declval<invoke_result_t<FD(Args...)>>());
template<class... Args> auto operator()(Args&&... args) const&& -> decltype(!declval<invoke_result_t<FD const(Args...)>>());
```

Первые два — те же, что и `return !std::invoke(fd, std::forward<Args>(args)...)` . Второй — то же, что и `return !std::invoke(std::move(fd), std::forward<Args>(args)...)` .

### <a name="example"></a>Пример

```cpp
// functional_not_fn_.cpp
// compile with: /EHsc /std:c++17
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main()
{
    std::vector<int> v1 = { 99, 6264, 41, 18467, 6334, 26500, 19169 };
    auto divisible_by_3 = [](int i){ return i % 3 == 0; };

    std::cout << "Vector v1 = ( " ;
    for (const auto& item : v1)
    {
        std::cout << item << " ";
    }
    std::cout << ")" << std::endl;

    // Count the number of vector elements divisible by 3.
    int divisible =
        std::count_if(v1.begin(), v1.end(), divisible_by_3);
    std::cout << "Elements divisible by three: "
        << divisible << std::endl;

    // Count the number of vector elements not divisible by 3.
    int not_divisible =
        std::count_if(v1.begin(), v1.end(), std::not_fn(divisible_by_3));
    std::cout << "Elements not divisible by three: "
        << not_divisible << std::endl;
}
```

```Output
Vector v1 = ( 99 6264 41 18467 6334 26500 19169 )
Elements divisible by three: 2
Elements not divisible by three: 5
```

## <a name="ptr_fun"></a><a name="ptr_fun"></a> ptr_fun

Вспомогательные функции шаблона, которые используются для преобразования указателей на унарные и бинарные функции соответственно в унарные и бинарные адаптируемые функции. Не рекомендуется использовать в C++ 11, удалено в C++ 17.

```cpp
template <class Arg, class Result>
pointer_to_unary_function<Arg, Result, Result (*)(Arg)> ptr_fun(Result (*pfunc)(Arg));

template <class Arg1, class Arg2, class Result>
pointer_to_binary_function<Arg1, Arg2, Result, Result (*)(Arg1, Arg2)> ptr_fun(Result (*pfunc)(Arg1, Arg2));
```

### <a name="parameters"></a>Параметры

*pFunc*\
Указатель на унарную или бинарную функцию, который должен быть преобразован в адаптируемую функцию.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-шаблон возвращает унарную функцию [pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md)  < `Arg` , **result**> ( \* `pfunc` ).

Вторая функция-шаблон возвращает двоичную функцию [pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md) \<**Arg1**, **Arg2**, **Result**> ( \* `pfunc` ).

### <a name="remarks"></a>Примечания

Указатель функции — это объект функции. Он может быть передан любому алгоритму, ожидающему функции в качестве параметра, но он не адаптируется. Сведения о вложенных типах необходимы для использования с адаптером, например для привязки значения к нему или для его отрицания. Преобразование указателей на унарные и бинарные функции с помощью вспомогательной функции `ptr_fun` позволяет адаптерам функций работать с такими указателями.

### <a name="example"></a>Пример

[!code-cpp[functional_ptr_fun#1](../standard-library/codesnippet/CPP/functional-functions_1.cpp)]

## <a name="ref"></a><a name="ref"></a> ЗНАЧ

Создает `reference_wrapper` из аргумента.

```cpp
template <class Ty>
    reference_wrapper<Ty> ref(Ty& arg);

template <class Ty>
    reference_wrapper<Ty> ref(reference_wrapper<Ty>& arg);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `arg`, а именно `reference_wrapper<Ty>(arg)`.

### <a name="example"></a>Пример

В приведенном ниже примере определяются две функции: одна из них привязана к строковой переменной, а другая — к ссылке строковой переменной, вычисленной с помощью вызова `ref`. Когда значение переменной меняется, первая функция продолжает использовать старое значение, а вторая использует новое значение.

```cpp
#include <algorithm>
#include <functional>
#include <iostream>
#include <iterator>
#include <ostream>
#include <string>
#include <vector>
using namespace std;
using namespace std;
using namespace std::placeholders;

bool shorter_than(const string& l, const string& r) {
    return l.size() < r.size();
}

int main() {
    vector<string> v_original;
    v_original.push_back("tiger");
    v_original.push_back("cat");
    v_original.push_back("lion");
    v_original.push_back("cougar");

    copy(v_original.begin(), v_original.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    string s("meow");

    function<bool (const string&)> f = bind(shorter_than, _1, s);
    function<bool (const string&)> f_ref = bind(shorter_than, _1, ref(s));

    vector<string> v;

    // Remove elements that are shorter than s ("meow")

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Now change the value of s.
    // f_ref, which is bound to ref(s), will use the
    // new value, while f is still bound to the old value.

    s = "kitty";

    // Remove elements that are shorter than "meow" (f is bound to old value of s)

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Remove elements that are shorter than "kitty" (f_ref is bound to ref(s))

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f_ref), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;
}
```

```Output
tiger cat lion cougar
tiger lion cougar
tiger lion cougar
tiger cougar
```

## <a name="swap"></a><a name="swap"></a> swap

Меняет местами два объекта `function`.

```cpp
template <class FT>
    void swap(function<FT>& f1, function<FT>& f2);
```

### <a name="parameters"></a>Параметры

*ФТ*\
Тип, управляемый объектами функции.

*справоч*\
Первый объект функции.

*F2*\
Второй объект функции.

### <a name="remarks"></a>Примечания

Функция возвращает `f1.swap(f2)`.

### <a name="example"></a>Пример

```cpp
// std__functional__swap.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "val == " << fn0(3) << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << std::endl;

    swap(fn0, fn1);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
empty == true

empty == true
empty == false
val == -3
```
