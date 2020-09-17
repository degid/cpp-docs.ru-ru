---
title: Функции &lt;utility&gt;
ms.date: 11/04/2016
f1_keywords:
- utility/std::exchange
- utility/std::forward
- utility/std::make_pair
- utility/std::move
- utility/std::swap
ms.assetid: b1df38cd-3a59-4098-9c81-83342eb719a4
helpviewer_keywords:
- std::exchange [C++]
- std::forward [C++]
- std::make_pair [C++]
- std::move [C++]
- std::swap [C++]
ms.openlocfilehash: 3e92d6dc9f6966efda0e26fb28cf14652be880c7
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075595"
---
# <a name="ltutilitygt-functions"></a>Функции &lt;utility&gt;

## <a name="as_const"></a><a name="asconst"></a>as_const

```cpp
template <class T> constexpr add_const_t<T>& as_const(T& t) noexcept;
template <class T> void as_const(const T&&) = delete;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение *T*.

## <a name="declval"></a><a name="declval"></a>деклвал

```cpp
template <class T> add_rvalue_reference_t<T> declval() noexcept;  // as unevaluated operand
```

## <a name="exchange"></a><a name="exchange"></a>сообщения

**(C++14)** Назначает новое значение объекту и возвращает его старое значение.

```cpp
template <class T, class Other = T>
    T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>Параметры

*val*\
Объект, который будет получать значение new_val.

*new_val*\
Объект, значение которого копируется или перемещается в val.

### <a name="remarks"></a>Примечания

В случае со сложными типами `exchange` не копирует старое значение, если доступен конструктор перемещения, не копирует новое значение, если оно является временным или переносится, и принимает любой тип в качестве нового значения, используя любой доступный оператор назначения с конвертацией. Функция Exchange отличается от [std:: Swap](../standard-library/algorithm-functions.md#swap) тем, что левый аргумент не перемещается или не копируется в правый аргумент.

### <a name="example"></a>Пример

В следующем примере показано, как использовать `exchange`. В реальной ситуации `exchange` наиболее полезен с большими объектами, копирование которых является дорогостоящим:

```cpp
#include <utility>
#include <iostream>

using namespace std;

struct C
{
   int i;
   //...
};

int main()
{
   // Use brace initialization
   C c1{ 1 };
   C c2{ 2 };
   C result = exchange(c1, c2);
   cout << "The old value of c1 is: " << result.i << endl;
   cout << "The new value of c1 after exchange is: " << c1.i << endl;

   return 0;
}
```

```Output
The old value of c1 is: 1
The new value of c1 after exchange is: 2
```

## <a name="forward"></a><a name="forward"></a>переадресован

Условно приводит свой аргумент к ссылке rvalue, если аргумент представляет собой rvalue или ссылку rvalue. Это восстанавливает присущие rvalue характеристики аргумента для функции пересылки для обеспечения точной пересылки.

```cpp
template <class Type>    // accepts lvalues
    constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
    constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>Параметры

*Type*\
Тип значения, переданного в *аргументе arg*, который может отличаться от типа *аргумента*. Как правило, определяется аргументом шаблона функции пересылки.

*Arg*\
Аргумент для приведения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку rvalue на *аргумент arg* , если значение, переданное в *аргументе arg* , изначально является rvalue или ссылкой на rvalue; в противном случае возвращает *аргумент arg* , не изменяя его тип.

### <a name="remarks"></a>Примечания

Необходимо указать явный аргумент шаблона для вызова `forward`.

`forward` не пересылает аргумент. Вместо этого путем условного приведения аргумента к ссылке rvalue, как если бы он изначально был rvalue или ссылкой rvalue, `forward` позволяет компилятору выполнять разрешение перегрузки с использованием сведений об исходном типе пересылаемого аргумента. Видимый тип аргумента для функции пересылки может отличаться от исходного типа, например, если rvalue используется в качестве аргумента функции и привязан к имени параметра; Если имя делает его левосторонним значением, то есть фактическое значение в качестве rvalue — `forward` восстанавливает rvalue-rvalue характеристики аргумента.

Восстановление rvalue-rvalue характеристики исходного значения аргумента для разрешения перегрузки называется *идеальной пересылкой*. Точная пересылка позволяет шаблонной функции принимать аргумент любого ссылочного типа и восстановить его присущие rvalue характеристики, когда это необходимо для правильного разрешения перегрузки. С помощью точной пересылки можно сохранять семантику перемещения для значений rvalue и избегать необходимости предоставления перегрузок функциям, которые отличаются только ссылочным типом их аргументов.

## <a name="from_chars"></a><a name="from_chars"></a>from_chars

```cpp
from_chars_result from_chars(const char* first, const char* last, see below& value, int base = 10);

from_chars_result from_chars(const char* first, const char* last, float& value, chars_format fmt = chars_format::general);

from_chars_result from_chars(const char* first, const char* last, double& value, chars_format fmt = chars_format::general);

from_chars_result from_chars(const char* first, const char* last, long double& value, chars_format fmt = chars_format::general);
```

## <a name="get"></a><a name="get"></a>Получить

Получает элемент из объекта `pair` по позиции индекса или по типу.

```cpp
// get reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&
    get(pair<T1, T2>& Pr) noexcept;

// get reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1& get(pair<T1, T2>& Pr) noexcept;

// get reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2& get(pair<T1, T2>& Pr) noexcept;

// get const reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr const tuple_element_t<Index, pair<T1, T2>>&
    get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr const T1& get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr const T2& get(const pair<T1, T2>& Pr) noexcept;

// get rvalue reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&&
    get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1&& get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2&& get(pair<T1, T2>&& Pr) noexcept;
```

### <a name="parameters"></a>Параметры

*index*\
Индекс (с нуля) выбранного элемента.

\ *T1*
Тип первого элемента пары.

*T2*\
Тип второго элемента пары.

\ная *Цена*
Пара для выбора элемента.

### <a name="remarks"></a>Примечания

Каждая функция шаблона возвращает ссылку на элемент аргумента `pair` .

Для индексированных перегрузок, если значение *индекса* равно 0, функции возвращают `pr.first` и если значение *индекса* равно 1, функции возвращают `pr.second`. Тип `RI` — это тип возвращаемого элемента.

Для перегрузок, у которых нет параметра index, возвращаемый элемент выводится аргументом типа. Вызов `get<T>(Tuple)` приведет к ошибке компилятора, если *Цена* содержит больше или меньше одного элемента типа t.

### <a name="example"></a>Пример

```cpp
#include <utility>
#include <iostream>
using namespace std;
int main()
{

    typedef pair<int, double> MyPair;

    MyPair c0(9, 3.14);

    // get elements by index
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0) << endl;

    // get elements by type (C++14)
    MyPair c1(1, 0.27);
    cout << " " << get<int>(c1);
    cout << " " << get<double>(c1) << endl;
}
```

```Output
9 3.14
1 0.27
```

## <a name="index_sequence"></a><a name="index_sequence"></a>index_sequence

```cpp
template<size_t... I>
    using index_sequence = integer_sequence<size_t, I...>;
```

## <a name="index_sequence_for"></a><a name="index_sequence_for"></a>index_sequence_for

```cpp
template<class... T>
    using index_sequence_for = make_index_sequence<sizeof...(T)>;
```

## <a name="make_index_sequence"></a><a name="make_index_sequence"></a>make_index_sequence

```cpp
template<size_t N>
    using make_index_sequence = make_integer_sequence<size_t, N>;
```

## <a name="make_integer_sequence"></a><a name="make_integer_sequence"></a>make_integer_sequence

```cpp
template<class T, T N>
    using make_integer_sequence = integer_sequence<T, see below >;
```

## <a name="make_pair"></a><a name="make_pair"></a>make_pair

Функция шаблона, которую можно использовать для построения объектов типа `pair`, где типы компонентов автоматически выбираются на основе типов данных, переданных в качестве параметров.

```cpp
template <class T, class U>
    pair<T, U> make_pair(T& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T& Val1, U&& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U&& Val2);
```

### <a name="parameters"></a>Параметры

*Val1*\
Значение, которое инициализирует первый элемент `pair`.

*Val2*\
Значение, которое инициализирует второй элемент `pair`.

### <a name="return-value"></a>Возвращаемое значение

Созданный объект пары: `pair`<`T`,`U`> (`Val1`, `Val2`).

### <a name="remarks"></a>Примечания

`make_pair` преобразует объект типа [reference_wrapper Class](../standard-library/reference-wrapper-class.md) в типы ссылки, а убывающие массивы и функции — в указатели.

В возвращенном объекте `pair``T` определяется следующим образом:

- Если тип ввода `T` имеет значение `reference_wrapper<X>`, возвращаемый тип `T` имеет значение `X&`.

- В противном случае возвращаемый тип `T` имеет значение `decay<T>::type`. Если [класс Decay](../standard-library/decay-class.md) не поддерживается, возвращаемый тип `T` совпадает с типом входных данных `T`.

Возвращаемый тип `U` аналогичным образом определяется по типу ввода `U`.

Одно из преимуществ `make_pair` заключается в том, что типы сохраняемых объектов определяются компилятором автоматически, и их не нужно указывать явно. Не используйте явные аргументы шаблона, такие как `make_pair<int, int>(1, 2)`, при использовании `make_pair`, так как он является подробным и добавляет сложные ссылки rvalue, которые могут вызвать сбой компиляции. В данном случае правильный синтаксис — `make_pair(1, 2)`

Вспомогательная функция `make_pair` также предоставляет возможность передать два значения в функцию, которой в качестве параметра ввода требуется пара.

### <a name="example"></a>Пример

Пример использования вспомогательной функции `make_pair` для объявления и инициализации пары см. в разделе [Структура pair](../standard-library/pair-structure.md).

## <a name="move"></a><a name="move"></a>поместить

Безусловно приводит свой аргумент к ссылке rvalue, тем самым указывая, что его можно переместить, если его тип допускает перемещения.

```cpp
template <class Type>
    constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>Параметры

*Type*\
Тип, выведенный из типа аргумента, переданного в *arg*, вместе с правилами свертывания ссылок.

*Arg*\
Аргумент для приведения. Хотя тип *аргумента* выглядит как ссылка rvalue, `move` также принимает аргументы lvalue, так как ссылки lvalue могут быть привязаны к ссылкам rvalue.

### <a name="return-value"></a>Возвращаемое значение

`Arg` используется в качестве ссылки rvalue вне зависимости от того, является ли его тип ссылочным.

### <a name="remarks"></a>Примечания

*Тип* аргумента шаблона не предназначен для явного указания, но должен быть выведен из типа значения, переданного в *аргументе arg*. Тип *типа* в дальнейшем корректируется в соответствии с правилами свертывания ссылок.

`move` не перемещает свой аргумент. Вместо этого путем безусловного приведения аргумента, который может быть левосторонним значением, к ссылке rvalue, он позволяет компилятору впоследствии перемещаться, а не копировать, значение, передаваемое в *аргументе arg* , если его тип — "перемещение". Если его тип не поддерживает перемещение, он копируется.

Если значение, передаваемое в *аргументе arg* , является левосторонним значением, то есть может быть занято имя или его адрес — оно становится недействительным при перемещении. Не следует обращаться к значению, переданному в *аргументе arg* , по его имени или адресу после перемещения.

## <a name="move_if_noexcept"></a><a name="moveif"></a>move_if_noexcept

```cpp
template <class T> constexpr conditional_t< !is_nothrow_move_constructible_v<T> && is_copy_constructible_v<T>, const T&, T&&> move_if_noexcept(T& x) noexcept;
```

## <a name="swap"></a><a name="swap"></a>позиции

Обменивает элементы двух типов или объектов [структуры пары](../standard-library/pair-structure.md) .

```cpp
template <class T>
    void swap(T& left, T& right) noexcept(see below );
template <class T, size_t N>
    void swap(T (&left)[N], T (&right)[N]) noexcept(is_nothrow_swappable_v<T>);
template <class T, class U>
    void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа или типа `pair`.

*right*\
Объект типа или типа `pair`.

### <a name="remarks"></a>Примечания

Одно из преимуществ `swap` заключается в том, что типы сохраняемых объектов определяются компилятором автоматически, и их не нужно указывать явно. Не используйте явные аргументы шаблона, такие как `swap<int, int>(1, 2)`, при использовании `swap`, так как он является подробным и добавляет сложные ссылки rvalue, которые могут вызвать сбой компиляции.

## <a name="to_chars"></a><a name="to_chars"></a>to_chars

```cpp
to_chars_result to_chars(char* first, char* last, see below value, int base = 10);
to_chars_result to_chars(char* first, char* last, float value);
to_chars_result to_chars(char* first, char* last, double value);
to_chars_result to_chars(char* first, char* last, long double value);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt, int precision);
```

### <a name="remarks"></a>Примечания

Преобразует значение в символьную строку, заполняя `[first, last)`диапазона, где `[first, last)` должен быть допустимым диапазоном.
