---
title: Класс integer_sequence
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::index_sequence
- type_traits/std::make_index_sequence
- type_traits/std::integer_sequence
- type_traits/std::make_integer_sequence
- type_traits/std::index_sequence_for
helpviewer_keywords:
- std::index_sequence
- std::make_index_sequence
- std::integer_sequence
- std::make_integer_sequence
- std::index_sequence_for
ms.assetid: 2cfdddee-819d-478e-bb78-c8a9c2696803
ms.openlocfilehash: 4d927be4fdd41ab75ca78a0e0e7ab0282e4fbf6a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843876"
---
# <a name="integer_sequence-class"></a>Класс integer_sequence

Представляет последовательность целых чисел. Может использоваться для вывода и расширения пакетов параметров в Variadic типах, таких как std:: Tuple \<T...> , которые передаются в качестве аргументов функции.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, T... Vals>
struct integer_sequence
```

### <a name="parameters"></a>Параметры

*T*\
Тип значений. Это должен быть целочисленный тип: bool, char, char16_t, char32_t, wchar_t или целочисленный тип со знаком или без знака.

*валс*\
Пакет параметров, не являющихся типами, представляющий последовательность значений целочисленного типа T.

## <a name="members"></a>Элементы

|Имя|Описание|
|-|-|
|`static size_t size() noexcept`|Число элементов в последовательности.|
|`typedef T value_type`|Тип каждого элемента последовательности. Должен быть целочисленным типом.|

## <a name="remarks"></a>Примечания

Пакет параметров, который передается непосредственно в функцию, может быть распакован без использования специальных вспомогательных методов библиотеки. Когда пакет параметров входит в тип, передаваемый в функцию, и вам необходимы индексы для доступа к элементам, то самым простым способом распаковать его будет использование `integer_sequence` и связанных с ним псевдонимов типа `make_integer_sequence`, `index_sequence`, `make_index_sequence` и `index_sequence_for`.

## <a name="example"></a>Пример

Следующий пример основан на исходном предложении [N3658](https://wg21.link/n3658). В нем продемонстрирован способ использования `integer_sequence` для создания `std::tuple` из `std::array<T,N>`, и способ использования `integer_sequence` для получения элементов кортежа.

В функции `a2t``index_sequence` является псевдонимом `integer_sequence` на основе целочисленного типа `size_t`. `make_index_sequence` — это псевдоним, который во время компиляции создает `index_sequence`, отсчитываемый от нуля, с тем же количеством элементов, как у массива, переданного вызывающим объектом. `a2t` передает `index_sequence` по значению в `a2t_`, где выражение `a[I]...` распаковывает `I`, а затем элементы передаются в `make_tuple`, который использует их как отдельные аргументы. Например, если последовательность содержит три элемента, то `make_tuple` вызывается как make_tuple(a[0], a[1], a[2]). Сами элементы массива, конечно, могут быть любого типа.

Функция Apply принимает значение [std:: Tuple](../standard-library/tuple-class.md)и создает `integer_sequence` с помощью `tuple_size` вспомогательного класса. Обратите внимание, что [std::d ecay_t](../standard-library/decay-class.md) является обязательным, так как [tuple_size](../standard-library/tuple-size-class-tuple.md) не работает со ссылочными типами. Функция `apply_` распаковывает элементы кортежа и пересылает их как отдельные аргументы при вызове функции. В этом примере функция представляет из себя простое лямбда-выражение, которое выводит значения.

```cpp
#include <stddef.h>
#include <iostream>
#include <tuple>
#include <utility>
#include <array>
#include <string>

using namespace std;

// Create a tuple from the array and the index_sequence
template<typename Array, size_t... I>
auto a2t_(const Array& a, index_sequence<I...>)
{
    return make_tuple(a[I]...);
}

// Create an index sequence for the array, and pass it to the
// implementation function a2t_
template<typename T, size_t N>
auto a2t(const array<T, N>& a)
{
    return a2t_(a, make_index_sequence<N>());
}

// Call function F with the tuple members as separate arguments.
template<typename F, typename Tuple = tuple<T...>, size_t... I>
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)
{
    return forward<F>(f)(get<I>(forward<Tuple>(args))...);
}

// Create an index_sequence for the tuple, and pass it with the
// function object and the tuple to the implementation function apply_
template<typename F, typename Tuple = tuple<T...>>
decltype(auto) apply(F&& f, Tuple&& args)
{
    using Indices = make_index_sequence<tuple_size<decay_t<Tuple>>::value >;
    return apply_(forward<F>(f), forward<Tuple>(args), Indices());
}

int main()
{
    const array<string, 3> arr { "Hello", "from", "C++14" };

    //Create a tuple given a array
    auto tup = a2t(arr);

    // Extract the tuple elements
    apply([](const string& a, const string& b, const string& c) {cout << a << " " << b << " " << c << endl; }, tup);

    char c;
    cin >> c;
}
```

Чтобы сделать `index_sequence` для пакета параметров, используйте `index_sequence_for` \<T...> псевдоним для`make_index_sequence`\<sizeof...(T)>

## <a name="requirements"></a>Требования

Заголовок: \<type_traits\>

Пространство имен: std

## <a name="see-also"></a>См. также раздел

[Шаблоны с многоточием и Variadic](../cpp/ellipses-and-variadic-templates.md)
