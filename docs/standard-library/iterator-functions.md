---
title: Функции &lt;iterator&gt;
ms.date: 11/04/2016
f1_keywords:
- xutility/std::advance
- xutility/std::back_inserter
- xutility/std::begin
- xutility/std::cbegin
- xutility/std::cend
- xutility/std::distance
- xutility/std::end
- xutility/std::front_inserter
- xutility/std::inserter
- xutility/std::make_checked_array_iterator
- xutility/std::make_move_iterator
- xutility/std::make_unchecked_array_iterator
- xutility/std::next
- xutility/std::prev
ms.assetid: 4a57c9a3-7e36-411f-8655-e0be2eec88e7
helpviewer_keywords:
- std::advance [C++]
- std::back_inserter [C++]
- std::begin [C++]
- std::cbegin [C++]
- std::cend [C++]
- std::distance [C++]
- std::end [C++]
- std::front_inserter [C++]
- std::inserter [C++]
- std::make_checked_array_iterator [C++]
- std::make_move_iterator [C++]
- std::make_unchecked_array_iterator [C++]
- std::next [C++]
- std::prev [C++]
ms.openlocfilehash: 615ebeedc87563eeac46c462304072ff1979040c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222320"
---
# <a name="ltiteratorgt-functions"></a>Функции &lt;iterator&gt;

## <a name="advance"></a><a name="advance"></a> advance

Увеличивает итератор на указанное количество позиций.

```cpp
template <class InputIterator, class Distance>
    void advance(InputIterator& InIt, Distance Off);
```

### <a name="parameters"></a>Параметры

*Ini*\
Итератор, который должен увеличен, должен удовлетворять требованиям для итератора ввода.

*Off*\
Целочисленный тип, который можно преобразовать в тип отличия итератора, указывающий число приращений позиции итератора, необходимо сдвинуть вперед.

### <a name="remarks"></a>Примечания

Диапазон сдвижения должен быть несингулярным, а итераторы должны поддерживать удаление ссылок или находиться за пределами диапазона.

Если объект `InputIterator` удовлетворяет требованиям для типа двунаправленного итератора, то параметр *Off* может быть отрицательным. Если `InputIterator` параметр имеет тип итератора ввода или перенаправления, значение *Off* должно быть неотрицательным.

Функция аванса имеет постоянную сложность, если `InputIterator` удовлетворяет требованиям для итератора произвольного доступа; в противном случае она имеет линейную сложность, и это потенциально дорого.

### <a name="example"></a>Пример

```cpp
// iterator_advance.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   list<int> L;
   for ( i = 1 ; i < 9 ; ++i )
   {
      L.push_back ( i );
   }
   list <int>::iterator L_Iter, LPOS = L.begin ( );

   cout << "The list L is: ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;

   cout << "The iterator LPOS initially points to the first element: "
        << *LPOS << "." << endl;

   advance ( LPOS , 4 );
   cout << "LPOS is advanced 4 steps forward to point"
        << " to the fifth element: "
        << *LPOS << "." << endl;

   advance ( LPOS , -3 );
   cout << "LPOS is moved 3 steps back to point to the "
        << "2nd element: " << *LPOS << "." << endl;
}
```

```Output
The list L is: ( 1 2 3 4 5 6 7 8 ).
The iterator LPOS initially points to the first element: 1.
LPOS is advanced 4 steps forward to point to the fifth element: 5.
LPOS is moved 3 steps back to point to the 2nd element: 2.
```

## <a name="back_inserter"></a><a name="back_inserter"></a> back_inserter

Создает итератор, может вставлять элементы с обратной стороны указанного контейнера.

```cpp
template <class Container>
back_insert_iterator<Container> back_inserter(Container& _Cont);
```

### <a name="parameters"></a>Параметры

*_Cont*\
Контейнер, в который будет выполняться вставка с обратной стороны.

### <a name="return-value"></a>Возвращаемое значение

Объект, `back_insert_iterator` связанный с объектом контейнера *_Cont*.

### <a name="remarks"></a>Примечания

В стандартной библиотеке C++ аргумент должен ссылаться на один из трех контейнеров последовательности, которые имеют функцию-член `push_back`: [класс deque](../standard-library/deque-class.md), [класс list](../standard-library/list-class.md) или [класс vector](../standard-library/vector-class.md).

### <a name="example"></a>Пример

```cpp
// iterator_back_inserter.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 0 ; i < 3 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;
   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   // Insertions can be done with template function
   back_insert_iterator<vector<int> > backiter ( vec );
*backiter = 30;
   backiter++;
*backiter = 40;

   // Alternatively, insertions can be done with the
   // back_insert_iterator member function
   back_inserter ( vec ) = 500;
   back_inserter ( vec ) = 600;

   cout << "After the insertions, the vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
```

```Output
The initial vector vec is: ( 0 1 2 ).
After the insertions, the vector vec is: ( 0 1 2 30 40 500 600 ).
```

## <a name="begin"></a><a name="begin"></a> begin

Извлекает итератор для первого элемента в указанном контейнере.

```cpp
template <class Container>
auto begin(Container& cont)  `
   -> decltype(cont.begin());

template <class Container>
auto begin(const Container& cont)   `
   -> decltype(cont.begin());

template <class Ty, class Size>
Ty *begin(Ty (& array)[Size]);
```

### <a name="parameters"></a>Параметры

*cont*\
Контейнер.

*array*\
Массив объектов перечисления `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Первые две функции шаблона возвращают `cont.begin()`. Первая функция не является константой; вторая является константой.

Третья функция шаблона возвращает *массив*.

### <a name="example"></a>Пример

Рекомендуется использовать эту же функцию шаблона вместо члена контейнера `begin()`, если требуется более стандартное поведение.

```cpp
// cl.exe /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <functional>
#include <iostream>
#include <iterator>
#include <vector>

template <typename C> void reverse_sort(C& c) {
    using std::begin;
    using std::end;

    std::sort(begin(c), end(c), std::greater<>());
}

template <typename C> void print(const C& c) {
    for (const auto& e : c) {
        std::cout << e << " ";
    }

    std::cout << "\n";
}

int main() {
    std::vector<int> v = { 11, 34, 17, 52, 26, 13, 40, 20, 10, 5, 16, 8, 4, 2, 1 };

    print(v);
    reverse_sort(v);
    print(v);

    std::cout << "--\n";

    int arr[] = { 23, 70, 35, 106, 53, 160, 80, 40, 20, 10, 5, 16, 8, 4, 2, 1 };

    print(arr);
    reverse_sort(arr);
    print(arr);
}
```

```Output
11 34 17 52 26 13 40 20 10 5 16 8 4 2 1
52 40 34 26 20 17 16 13 11 10 8 5 4 2 1
--
23 70 35 106 53 160 80 40 20 10 5 16 8 4 2 1
160 106 80 70 53 40 35 23 20 16 10 8 5 4 2 1
```

Функция `reverse_sort` поддерживает контейнеры любого типа, кроме обычных массивов, поскольку она обращается к версиям `begin()`, не являющимся членами. Если `reverse_sort` было написано для использования члена контейнера `begin()`, выполните следующие действия.

```cpp
template <typename C>
void reverse_sort(C& c) {
    using std::begin;
    using std::end;

    std::sort(c.begin(), c.end(), std::greater<>());

}
```

Тогда отправка массива в данный контейнер вызовет следующую ошибку компилятора:

```Output
error C2228: left of '.begin' must have class/struct/union
```

## <a name="cbegin"></a><a name="cbegin"></a> cbegin

Извлекает итератор const для первого элемента в указанном контейнере.

```cpp
template <class Container>
auto cbegin(const Container& cont)
   -> decltype(cont.begin());
```

### <a name="parameters"></a>Параметры

*cont*\
Контейнер или initializer_list.

### <a name="return-value"></a>Возвращаемое значение

Константа `cont.begin()`.

### <a name="remarks"></a>Примечания

Эта функция работает со всеми контейнерами стандартной библиотеки С++ и с [initializer_list](../standard-library/initializer-list-class.md).

Эту функцию-член можно использовать вместо функции шаблона `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере рекомендуется использовать `Container` изменяемый (не- **`const`** ) контейнер или `initializer_list` любой тип, который поддерживает `begin()` и `cbegin()` .

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a><a name="cend"></a> cend

Извлекает итератор const для элемента, следующего за последним элементом в указанном контейнере.

```cpp
template <class Container>
auto cend(const Container& cont)
   -> decltype(cont.end());
```

### <a name="parameters"></a>Параметры

*cont*\
Контейнер или initializer_list.

### <a name="return-value"></a>Возвращаемое значение

Константа `cont.end()`.

### <a name="remarks"></a>Примечания

Эта функция работает со всеми контейнерами стандартной библиотеки С++ и с [initializer_list](../standard-library/initializer-list-class.md).

Эту функцию-член можно использовать вместо функции шаблона [end()](../standard-library/iterator-functions.md#end), чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере рекомендуется использовать `Container` изменяемый (не- **`const`** ) контейнер или `initializer_list` любой тип, который поддерживает `end()` и `cend()` .

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

## <a name="crbegin"></a><a name="crbegin"></a> crbegin

```cpp
template <class C> constexpr auto crbegin(const C& c) -> decltype(std::rbegin(c));
```

## <a name="crend"></a><a name="crend"></a> crend

```cpp
template <class C> constexpr auto crend(const C& c) -> decltype(std::rend(c));
```

## <a name="data"></a><a name="data"></a> data

```cpp
template <class C> constexpr auto data(C& c) -> decltype(c.data());
template <class C> constexpr auto data(const C& c) -> decltype(c.data());
template <class T, size_t N> constexpr T* data(T (&array)[N]) noexcept;
template <class E> constexpr const E* data(initializer_list<E> il) noexcept;
```

## <a name="distance"></a><a name="distance"></a> distance

Указывает количество приращений между позициями, которые адресуют два итератора.

```cpp
template <class InputIterator>
typename iterator_traits<InputIterator>::difference_type distance(InputIterator first, InputIterator last);
```

### <a name="parameters"></a>Параметры

*first*\
Первый итератор, для которого нужно определить расстояние до второго.

*last*\
Второй итератор, для которого нужно определить расстояние от первого.

### <a name="return-value"></a>Возвращаемое значение

Количество раз, которое *первое* должно быть увеличено до того, как оно равно *последнему*.

### <a name="remarks"></a>Примечания

Функция Distance имеет постоянную сложность, если `InputIterator` удовлетворяет требованиям для итератора произвольного доступа; в противном случае она имеет линейную сложность и, возможно, является дорогостоящей.

### <a name="example"></a>Пример

```cpp
// iterator_distance.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   list<int> L;
   for ( i = -1 ; i < 9 ; ++i )
   {
      L.push_back ( 2 * i );
   }
   list <int>::iterator L_Iter, LPOS = L.begin ( );

   cout << "The list L is: ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;

   cout << "The iterator LPOS initially points to the first element: "
        << *LPOS << "." << endl;

   advance ( LPOS , 7 );
   cout << "LPOS is advanced 7 steps forward to point "
        << " to the eighth element: "
        << *LPOS << "." << endl;

   list<int>::difference_type Ldiff ;
   Ldiff = distance ( L.begin ( ) , LPOS );
   cout << "The distance from L.begin( ) to LPOS is: "
        << Ldiff << "." << endl;
}
```

```Output
The list L is: ( -2 0 2 4 6 8 10 12 14 16 ).
The iterator LPOS initially points to the first element: -2.
LPOS is advanced 7 steps forward to point  to the eighth element: 12.
The distance from L.begin( ) to LPOS is: 7.
```

## <a name="empty"></a><a name="empty"></a> empty

```cpp
template <class C> constexpr auto empty(const C& c) -> decltype(c.empty());
template <class T, size_t N> constexpr bool empty(const T (&array)[N]) noexcept;
template <class E> constexpr bool empty(initializer_list<E> il) noexcept;
```

## <a name="end"></a><a name="end"></a> end

Извлекает итератор для элемента, следующего за последним элементом в указанном контейнере.

```cpp
template <class Container>
auto end(Container& cont)
   -> decltype(cont.end());

template <class Container>
auto end(const Container& cont)
   -> decltype(cont.end());

template <class Ty, class Size>
Ty *end(Ty (& array)[Size]);
```

### <a name="parameters"></a>Параметры

*cont*\
Контейнер.

*array*\
Массив объектов перечисления `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Первые две функции шаблона возвращают `cont.end()` (первая не является константой, вторая является константой).

Третья функция шаблона возвращает `array + Size`.

### <a name="remarks"></a>Примечания

Пример кода см. в разделе [begin](../standard-library/iterator-functions.md#begin).

## <a name="front_inserter"></a><a name="front_inserter"></a> front_inserter

Создает итератор, может вставлять элементы с передней стороны указанного контейнера.

```cpp
template <class Container>
front_insert_iterator<Container> front_inserter(Container& _Cont);
```

### <a name="parameters"></a>Параметры

*_Cont*\
Объект-контейнер, для которого выполняется вставка элемента в переднюю часть.

### <a name="return-value"></a>Возвращаемое значение

Объект, `front_insert_iterator` связанный с объектом контейнера *_Cont*.

### <a name="remarks"></a>Примечания

Функция-член [front_insert_iterator](../standard-library/front-insert-iterator-class.md#front_insert_iterator) класса front_insert_iterator также может использоваться.

В стандартной библиотеке C++ аргумент должен ссылаться на один из двух контейнеров последовательности, которые имеют функцию-член `push_back`: [класс deque](../standard-library/deque-class.md) или "класс list".

### <a name="example"></a>Пример

```cpp
// iterator_front_inserter.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for ( i = -1 ; i < 9 ; ++i )
   {
      L.push_back ( i );
   }

   cout << "The list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;

   // Using the template function to insert an element
   front_insert_iterator< list < int> > Iter(L);
*Iter = 100;

   // Alternatively, you may use the front_insert member function
   front_inserter ( L ) = 200;

   cout << "After the front insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
```

```Output
The list L is:
( -1 0 1 2 3 4 5 6 7 8 ).
After the front insertions, the list L is:
( 200 100 -1 0 1 2 3 4 5 6 7 8 ).
```

## <a name="inserter"></a><a name="inserter"></a> inserter

Вспомогательная функция шаблона, позволяющая использовать `inserter(_Cont, _Where)` вместо `insert_iterator<Container>(_Cont, _Where)` .

```cpp
template <class Container>
insert_iterator<Container>
inserter(
    Container& _Cont,
    typename Container::iterator _Where);
```

### <a name="parameters"></a>Параметры

*_Cont*\
Контейнер, в который будут добавляться новые элементы.

*_Where*\
Итератор, обнаруживающий точку вставки.

### <a name="remarks"></a>Примечания

Функция шаблона возвращает [insert_iterator](../standard-library/insert-iterator-class.md#insert_iterator) `<Container>(_Cont, _Where)` .

### <a name="example"></a>Пример

```cpp
// iterator_inserter.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for (i = 2 ; i < 5 ; ++i )
   {
      L.push_back ( 10 * i );
   }

   cout << "The list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;

   // Using the template version to insert an element
   insert_iterator<list <int> > Iter( L, L.begin ( ) );
*Iter = 1;

   // Alternatively, using the member function to insert an element
   inserter ( L, L.end ( ) ) = 500;

   cout << "After the insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
```

```Output
The list L is:
( 20 30 40 ).
After the insertions, the list L is:
( 1 20 30 40 500 ).
```

## <a name="make_checked_array_iterator"></a><a name="make_checked_array_iterator"></a> make_checked_array_iterator

Создает [checked_array_iterator](../standard-library/checked-array-iterator-class.md), который может использоваться другими алгоритмами.

> [!NOTE]
> Эта функция — расширение Майкрософт для стандартной библиотеки C++. Код, реализованный с помощью этой функции, нельзя перенести в стандартные среды сборки C, не поддерживающие это расширение Microsoft.

```cpp
template <class Iter>
checked_array_iterator<Iter>
    make_checked_array_iterator(
Iter Ptr,
    size_t Size,
    size_t Index = 0);
```

### <a name="parameters"></a>Параметры

*Ptr*\
Указатель на массив назначения.

*Size*\
Размер массива назначения.

*Index*\
Необязательный индекс массива.

### <a name="return-value"></a>Возвращаемое значение

Экземпляр `checked_array_iterator`.

### <a name="remarks"></a>Примечания

Функция `make_checked_array_iterator` задается в пространстве имен `stdext`.

Эта функция принимает необработанный указатель, который в обычном случае вызывает проблемы, связанные с выходом за границы, и помещает его в оболочку класса [checked_array_iterator](../standard-library/checked-array-iterator-class.md), который выполняет проверку. Так как этот класс помечен как проверенный, стандартная библиотека С++ не выдает предупреждение о нем. Дополнительные сведения и примеры кода см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

В следующем примере создается и заполняется 10 элементами [вектор](../standard-library/vector-class.md). Содержимое вектора копируется в массив с помощью алгоритма копирования, а затем `make_checked_array_iterator` используется для указания назначения. Затем осуществляется проверка на преднамеренное нарушение границ для активации сбоя подтверждения отладки.

```cpp
// make_checked_array_iterator.cpp
// compile with: /EHsc /W4 /MTd

#include <algorithm>
#include <iterator> // stdext::make_checked_array_iterator
#include <memory> // std::make_unique
#include <iostream>
#include <vector>
#include <string>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    const size_t dest_size = 10;
    // Old-school but not exception safe, favor make_unique<int[]>
    // int* dest = new int[dest_size];
    unique_ptr<int[]> updest = make_unique<int[]>(dest_size);
    int* dest = updest.get(); // get a raw pointer for the demo

    vector<int> v;

    for (int i = 0; i < dest_size; ++i) {
        v.push_back(i);
    }
    print("vector v: ", v);

    copy(v.begin(), v.end(), stdext::make_checked_array_iterator(dest, dest_size));

    cout << "int array dest: ";
    for (int i = 0; i < dest_size; ++i) {
        cout << dest[i] << " ";
    }
    cout << endl;

    // Add another element to the vector to force an overrun.
    v.push_back(10);
    // The next line causes a debug assertion when it executes.
    copy(v.begin(), v.end(), stdext::make_checked_array_iterator(dest, dest_size));
}
```

## <a name="make_move_iterator"></a><a name="make_move_iterator"></a> make_move_iterator

Создает `move iterator`, содержащий предоставленный итератор в качестве итератора `stored`.

```cpp
template <class Iterator>
move_iterator<Iterator>
make_move_iterator(const Iterator& _It);
```

### <a name="parameters"></a>Параметры

*_It*\
Итератор, хранящийся в новом итераторе перемещения.

### <a name="remarks"></a>Примечания

Функция шаблона возвращает `move_iterator` `<Iterator>(_It)`.

## <a name="make_unchecked_array_iterator"></a><a name="make_unchecked_array_iterator"></a>make_unchecked_array_iterator

Создает [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md), который может использоваться другими алгоритмами.

> [!NOTE]
> Эта функция — расширение Майкрософт для стандартной библиотеки C++. Код, реализованный с помощью этой функции, нельзя перенести в стандартные среды сборки C, не поддерживающие это расширение Microsoft.

```cpp
template <class Iter>
unchecked_array_iterator<Iter>
    make_unchecked_array_iterator(Iter Ptr);
```

### <a name="parameters"></a>Параметры

*Ptr*\
Указатель на массив назначения.

### <a name="return-value"></a>Возвращаемое значение

Экземпляр `unchecked_array_iterator`.

### <a name="remarks"></a>Примечания

Функция `make_unchecked_array_iterator` задается в пространстве имен `stdext`.

Эта функция принимает необработанный указатель и помещает его в класс, который не выполняет проверки, и поэтому оптимизирует к минимуму, но также подавляет предупреждения компилятора, например [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Соответственно, это целевой способ работы с предупреждениями непроверенных указателей без их глобального подавления или возникновения стоимости проверки. Дополнительные сведения и примеры кода см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

В следующем примере создается и заполняется 10 элементами [вектор](../standard-library/vector-class.md). Содержимое вектора копируется в массив с помощью алгоритма копирования, а затем `make_unchecked_array_iterator` используется для указания назначения.

```cpp
// make_unchecked_array_iterator.cpp
// compile with: /EHsc /W4 /MTd

#include <algorithm>
#include <iterator> // stdext::make_unchecked_array_iterator
#include <iostream>
#include <vector>
#include <string>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    const size_t dest_size = 10;
    int *dest = new int[dest_size];
    vector<int> v;

    for (int i = 0; i < dest_size; ++i) {
        v.push_back(i);
    }
    print("vector v: ", v);

    // COMPILER WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode
    // (it performs no checking, so an overrun will trigger undefined behavior)
    copy(v.begin(), v.end(), stdext::make_unchecked_array_iterator(dest));

    cout << "int array dest: ";
    for (int i = 0; i < dest_size; ++i) {
        cout << dest[i] << " ";
    }
    cout << endl;

    delete[] dest;
}
```

## <a name="next"></a><a name="next"></a> next

Выполняет итерацию заданное число раз и возвращает новую позицию итератора.

```cpp
template <class InputIterator>
InputIterator next(
    InputIterator first,
    typename iterator_traits<InputIterator>::difference_type _Off = 1);
```

### <a name="parameters"></a>Параметры

*first*\
Текущая позиция.

*_Off*\
Количество раз для прохода.

### <a name="return-value"></a>Возвращаемое значение

Возвращает новую точку итератора после прохода *_Off* раз.

### <a name="remarks"></a>Примечания

Функция шаблона возвращает `next` приращение *_Off* раз

## <a name="prev"></a><a name="prev"></a> prev

Выполняет обратную итерацию заданное число раз и возвращает новую позицию итератора.

```cpp
template <class BidirectionalIterator>
BidirectionalIterator prev(
    BidirectionalIterator first,
    typename iterator_traits<BidirectionalIterator>::difference_type _Off = 1);
```

### <a name="parameters"></a>Параметры

*first*\
Текущая позиция.

*_Off*\
Количество раз для прохода.

### <a name="remarks"></a>Примечания

Функция-шаблон возвращает `next`, уменьшенный `off` раз.

## <a name="rbegin"></a><a name="rbegin"></a> rbegin

```cpp
template <class C> constexpr auto rbegin(C& c) -> decltype(c.rbegin());
template <class C> constexpr auto rbegin(const C& c) -> decltype(c.rbegin());
```

## <a name="rend"></a><a name="rend"></a> rend

```cpp
template <class C> constexpr auto rend(C& c) -> decltype(c.rend());
template <class C> constexpr auto rend(const C& c) -> decltype(c.rend());
```

## <a name="size"></a><a name="size"></a> size

```cpp
template <class C> constexpr auto size(const C& c) -> decltype(c.size());
template <class T, size_t N> constexpr size_t size(const T (&array)[N]) noexcept;
```
