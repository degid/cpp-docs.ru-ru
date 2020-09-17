---
title: Checked Iterators
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL_THROWS
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
- iterators, checked
- checked iterators
ms.assetid: cfc87df8-e3d9-403b-ab78-e9483247d940
ms.openlocfilehash: 2327638208f30908cd3429ae656ce569f5821195
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684907"
---
# <a name="checked-iterators"></a>Checked Iterators

Проверенные итераторы гарантируют отсутствие перезаписи границ контейнера. Проверенные итераторы применяются и к сборкам выпуска, и к сборкам отладки. Дополнительные сведения об использовании итераторов отладки при компиляции в режиме отладки см. в статье [Поддержка итераторов отладки](../standard-library/debug-iterator-support.md).

## <a name="remarks"></a>Примечания

Дополнительные сведения об отключении предупреждений, создаваемых проверенными итераторами, см. в разделе [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

Для включения или отключения функции проверенных итераторов можно использовать макрос препроцессора на [ \_ \_ \_ уровне отладки итератора](../standard-library/iterator-debug-level.md) . Если _ITERATOR_DEBUG_LEVEL определяется как 1 или 2, ненадежное использование итераторов вызывает ошибку времени выполнения и программа завершается. Если задано значение 0, проверенные итераторы блокируются. По умолчанию значение для _ITERATOR_DEBUG_LEVEL равно 0 для сборок выпуска и 2 для отладочных сборок.

> [!IMPORTANT]
> В более старой документации и исходном коде могут быть ссылки на макрос [_SECURE_SCL](../standard-library/secure-scl.md). Используйте _ITERATOR_DEBUG_LEVEL для управления _SECURE_SCL. Дополнительные сведения см. в разделе [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

Если _ITERATOR_DEBUG_LEVEL определен как 1 или 2, выполняются следующие проверки итератора:

- Проверяются все стандартные итераторы (например [vector::iterator](../standard-library/vector-class.md#iterator)).

- Если итератор вывода является проверенным итератором, то при вызове функций стандартной библиотеки, таких как [std::copy](../standard-library/algorithm-functions.md#copy), будет продемонстрировано поведение проверенного итератора.

- Если итератор вывода является непроверенным итератором, при вызове функций стандартной библиотеки будут отображаться предупреждения компилятора.

- Следующие функции вызовут ошибку во время выполнения при попытке получения доступа к элементу, расположенному за границами контейнера:

:::row:::
   :::column span="":::
      &emsp;&emsp;[`basic_string::operator[]`](../standard-library/basic-string-class.md#op_at)\
      &emsp;&emsp;[`bitset::operator[]`](../standard-library/bitset-class.md#op_at)\
      &emsp;&emsp;[`deque::back`](../standard-library/deque-class.md#back)\
      &emsp;&emsp;[`deque::front`](../standard-library/deque-class.md#front)
   :::column-end:::
   :::column span="":::
      [`deque::operator[]`](../standard-library/deque-class.md#op_at)\
      [`list::back`](../standard-library/list-class.md#back)\
      [`list::front`](../standard-library/list-class.md#front)\
      [`queue::back`](../standard-library/queue-class.md#back)
   :::column-end:::
   :::column span="":::
      [`queue::front`](../standard-library/queue-class.md#front)\
      [`vector::back`](../standard-library/vector-class.md#back)\
      [`vector::front`](../standard-library/vector-class.md#front)\
      [`vector::operator[]`](../standard-library/vector-class.md#op_at)
   :::column-end:::
:::row-end:::

Если _ITERATOR_DEBUG_LEVEL определено как 0:

- Все стандартные итераторы являются непроверенными. Итераторы могут перемещаться за пределы контейнера, что вызывает неопределенное поведение.

- Если итератор вывода является проверенным итератором, то при вызове функций стандартной библиотеки, таких как `std::copy` будет продемонстрировано поведение проверенного итератора.

- Если итератор вывода является непроверенным итератором, то при вызове функций стандартной библиотеки будет продемонстрировано поведение непроверенного итератора.

Проверенный итератор ссылается на итератор, который вызывает `invalid_parameter_handler` при попытке перемещения за границы контейнера. Дополнительные сведения о `invalid_parameter_handler` см. в разделе [Проверка параметров](../c-runtime-library/parameter-validation.md).

Адаптеры итератора, которые поддерживают проверенные итераторы, это [класс checked_array_iterator](../standard-library/checked-array-iterator-class.md) и [класс unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md).

## <a name="examples"></a>Примеры

При компиляции с помощью _ITERATOR_DEBUG_LEVEL, для которого задано значение 1 или 2, при попытке получить доступ к элементу, который находится за пределами контейнера с помощью оператора индексирования определенных классов, возникнет ошибка времени выполнения.

```cpp
// checked_iterators_1.cpp
// cl.exe /Zi /MDd /EHsc /W4

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>
#include <iostream>

using namespace std;

int main()
{
   vector<int> v;
   v.push_back(67);

   int i = v[0];
   cout << i << endl;

   i = v[1]; //triggers invalid parameter handler
}
```

Данная программа напечатает "67", а затем отобразит диалоговое окно сбоя утверждения с дополнительной информацией о сбое.

Аналогично при компиляции с помощью _ITERATOR_DEBUG_LEVEL, для которого задано значение 1 или 2, возникает ошибка времени выполнения при попытке получить доступ к элементу с помощью `front` или `back` в классах контейнеров, если контейнер пуст.

```cpp
// checked_iterators_2.cpp
// cl.exe /Zi /MDd /EHsc /W4
#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>
#include <iostream>

using namespace std;

int main()
{
   vector<int> v;

   int& i = v.front(); // triggers invalid parameter handler
}
```

Данная программа отобразит диалоговое окно сбоя утверждения с дополнительной информацией о сбое.

Следующий код демонстрирует различные сценарии использования итератора с комментариями о каждом. По умолчанию для параметра _ITERATOR_DEBUG_LEVEL задано значение 2 в отладочных сборках, а в розничных сборках — 0.

```cpp
// checked_iterators_3.cpp
// cl.exe /MTd /EHsc /W4

#include <algorithm>
#include <array>
#include <iostream>
#include <iterator>
#include <numeric>
#include <string>
#include <vector>

using namespace std;

template <typename C>
void print(const string& s, const C& c)
{
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    vector<int> v(16);
    iota(v.begin(), v.end(), 0);
    print("v: ", v);

    // OK: vector::iterator is checked in debug mode
    // (i.e. an overrun causes a debug assertion)
    vector<int> v2(16);
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });
    print("v2: ", v2);

    // OK: back_insert_iterator is marked as checked in debug mode
    // (i.e. an overrun is impossible)
    vector<int> v3;
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });
    print("v3: ", v3);

    // OK: array::iterator is checked in debug mode
    // (i.e. an overrun causes a debug assertion)
    array<int, 16> a4;
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });
    print("a4: ", a4);

    // OK: Raw arrays are checked in debug mode
    // (an overrun causes a debug assertion)
    // NOTE: This applies only when raw arrays are given to C++ Standard Library algorithms!
    int a5[16];
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });
    print("a5: ", a5);

    // WARNING C4996: Pointers cannot be checked in debug mode
    // (an overrun causes undefined behavior)
    int a6[16];
    int * p6 = a6;
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });
    print("a6: ", a6);

    // OK: stdext::checked_array_iterator is checked in debug mode
    // (an overrun causes a debug assertion)
    int a7[16];
    int * p7 = a7;
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });
    print("a7: ", a7);

    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode
    // (it performs no checking, so an overrun causes undefined behavior)
    int a8[16];
    int * p8 = a8;
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });
    print("a8: ", a8);
}
```

При компиляции этого кода с помощью `cl.exe /EHsc /W4 /MTd checked_iterators_3.cpp` компилятор выдает предупреждение, но компилирует без ошибок в исполняемый файл:

```Output
algorithm(1026) : warning C4996: 'std::_Transform1': Function call with parameters
that may be unsafe - this call relies on the caller to check that the passed values
are correct. To disable this warning, use -D_SCL_SECURE_NO_WARNINGS. See documentation
on how to use Visual C++ 'Checked Iterators'
```

При запуске из командной строки исполняемый файл создает следующие выходные данные:

```Output
v: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
v2: 0 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30
v3: 0 3 6 9 12 15 18 21 24 27 30 33 36 39 42 45
a4: 0 4 8 12 16 20 24 28 32 36 40 44 48 52 56 60
a5: 0 5 10 15 20 25 30 35 40 45 50 55 60 65 70 75
a6: 0 6 12 18 24 30 36 42 48 54 60 66 72 78 84 90
a7: 0 7 14 21 28 35 42 49 56 63 70 77 84 91 98 105
a8: 0 8 16 24 32 40 48 56 64 72 80 88 96 104 112 120
```

## <a name="see-also"></a>См. также

[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)\
[Поддержка итератора отладки](../standard-library/debug-iterator-support.md)
