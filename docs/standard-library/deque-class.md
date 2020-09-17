---
title: Класс deque
ms.date: 11/04/2016
f1_keywords:
- deque/std::deque
- deque/std::deque::allocator_type
- deque/std::deque::const_iterator
- deque/std::deque::const_pointer
- deque/std::deque::const_reference
- deque/std::deque::const_reverse_iterator
- deque/std::deque::difference_type
- deque/std::deque::iterator
- deque/std::deque::pointer
- deque/std::deque::reference
- deque/std::deque::reverse_iterator
- deque/std::deque::size_type
- deque/std::deque::value_type
- deque/std::deque::assign
- deque/std::deque::at
- deque/std::deque::back
- deque/std::deque::begin
- deque/std::deque::cbegin
- deque/std::deque::cend
- deque/std::deque::clear
- deque/std::deque::crbegin
- deque/std::deque::crend
- deque/std::deque::emplace
- deque/std::deque::emplace_back
- deque/std::deque::emplace_front
- deque/std::deque::empty
- deque/std::deque::end
- deque/std::deque::erase
- deque/std::deque::front
- deque/std::deque::get_allocator
- deque/std::deque::insert
- deque/std::deque::max_size
- deque/std::deque::pop_back
- deque/std::deque::pop_front
- deque/std::deque::push_back
- deque/std::deque::push_front
- deque/std::deque::rbegin
- deque/std::deque::rend
- deque/std::deque::resize
- deque/std::deque::shrink_to_fit
- deque/std::deque::size
- deque/std::deque::swap
helpviewer_keywords:
- std::deque [C++]
- std::deque [C++], allocator_type
- std::deque [C++], const_iterator
- std::deque [C++], const_pointer
- std::deque [C++], const_reference
- std::deque [C++], const_reverse_iterator
- std::deque [C++], difference_type
- std::deque [C++], iterator
- std::deque [C++], pointer
- std::deque [C++], reference
- std::deque [C++], reverse_iterator
- std::deque [C++], size_type
- std::deque [C++], value_type
- std::deque [C++], assign
- std::deque [C++], at
- std::deque [C++], back
- std::deque [C++], begin
- std::deque [C++], cbegin
- std::deque [C++], cend
- std::deque [C++], clear
- std::deque [C++], crbegin
- std::deque [C++], crend
- std::deque [C++], emplace
- std::deque [C++], emplace_back
- std::deque [C++], emplace_front
- std::deque [C++], empty
- std::deque [C++], end
- std::deque [C++], erase
- std::deque [C++], front
- std::deque [C++], get_allocator
- std::deque [C++], insert
- std::deque [C++], max_size
- std::deque [C++], pop_back
- std::deque [C++], pop_front
- std::deque [C++], push_back
- std::deque [C++], push_front
- std::deque [C++], rbegin
- std::deque [C++], rend
- std::deque [C++], resize
- std::deque [C++], shrink_to_fit
- std::deque [C++], size
- std::deque [C++], swap
ms.assetid: 64842ee5-057a-4063-8c16-4267a0332584
ms.openlocfilehash: 1edcabf526d0f3aa2ba52ba3fd0fc656c5ae6b9c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838554"
---
# <a name="deque-class"></a>Класс deque

Упорядочивает элементы заданного типа в линейном порядке и, подобно векторам, обеспечивает быстрый произвольный доступ к любому элементу и эффективную вставку и удаление в конце контейнера. Однако в отличие от объекта vector класс `deque` также поддерживает эффективную вставку и удаление в передней части контейнера.

## <a name="syntax"></a>Синтаксис

```unstlib
template <class Type, class Allocator =allocator<Type>>
class deque
```

### <a name="parameters"></a>Параметры

*Type*\
Тип данных элементов, сохраняемых в объекте deque.

*Allocator*\
Тип, представляющий сохраненный объект распределителя, содержащий сведения о распределении и отмене распределения памяти для deque. Этот аргумент является необязательным, а значение по умолчанию — **распределителе \<Type> **.

## <a name="remarks"></a>Примечания

Выбор типа контейнера должен в общем случае производиться на основе типа поиска и вставки, который требуется приложению. [Векторы](../standard-library/vector-class.md) должны быть предпочтительными контейнерами для управления последовательностью, когда произвольный доступ к любому элементу имеет уровень Premium, а вставки или удаления элементов требуются только в конце последовательности. Производительность контейнера list выше, если эффективные вставки и удаления (в константном времени) в любом расположении в последовательности имеют больший приоритет. Таким операциям в середине последовательности требуются копии элементов и присвоения, пропорциональные количеству элементов в последовательности (линейное время).

Перераспределение объекта deque происходит, когда функция-член должна вставить или удалить элементы последовательности:

- Если элемент вставляется в пустую последовательность или элемент удаляется, чтобы оставить после себя пустую последовательность, то итераторы, ранее возвращенные [begin](#begin) и [end](#end), становятся недействительными.

- Если элемент вставляется в первую позицию deque, то все итераторы, но не ссылки, которые определяют существующие элементы, становятся недействительными.

- Если элемент вставляется в последнюю позицию очереди, то [end](#end) и все итераторы, но не ссылки, которые определяют существующие элементы, становятся недействительными.

- Если элемент удаляется в передней части объекта deque, только этот итератор и ссылки на удаленный элемент становятся недействительными.

- Если последний элемент удаляется из конца объекта deque, только этот итератор последнего элемента и ссылки на удаленный элемент становятся недействительными.

В противном случае вставка или удаление элемента делает недействительными все итераторы и ссылки.

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[deque](#deque)|Создает документ `deque`. Предусмотрено несколько конструкторов для настройки содержимого новых служб `deque` различными способами: пусто; загружено с указанным числом пустых элементов; содержимое перемещено или скопировано из другого объекта `deque` ; содержимое скопировано или перемещено с помощью итератора, а один элемент копируется в `deque` `count` время. Некоторые конструкторы позволяют использовать настраиваемый `allocator` для создания элементов.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[allocator_type](#allocator_type)|Тип, представляющий класс `allocator` для объекта `deque`.|
|[const_iterator](#const_iterator)|Тип, предоставляющий итератор произвольного доступа, который может получать доступ к элементам и считывать их в `deque` виде **`const`**|
|[const_pointer](#const_pointer)|Тип, предоставляющий указатель на элемент в `deque` как `const.`.|
|[const_reference](#const_reference)|Тип, предоставляющий ссылку на элемент в `deque` для считывания и выполнения других операций в качестве `const.`.|
|[const_reverse_iterator](#const_reverse_iterator)|Тип, предоставляющий итератор произвольного доступа, который может получать доступ к элементам и считывать их в `deque` виде **`const`** . Объект deque просматривается в обратном порядке. Дополнительные сведения см. в статье [Класс reverse_iterator](../standard-library/reverse-iterator-class.md).|
|[difference_type](#difference_type)|Тип, предоставляющий разницу между двумя итераторами произвольного доступа, ссылающимися на элементы в одном и том же `deque`.|
|[iterator](#iterator)|Тип, предоставляющий итератор произвольного доступа, который может считывать или изменять любой элемент в `deque`.|
|[pointer](#pointer)|Тип, предоставляющий указатель на элемент в `deque`.|
|[reference](#reference)|Тип, предоставляющий ссылку на элемент, хранящийся в контейнере `deque`.|
|[reverse_iterator](#reverse_iterator)|Тип, предоставляющий итератор произвольного доступа, который может считывать или изменять элемент в `deque`. Объект deque просматривается в обратном порядке.|
|[size_type](#size_type)|Тип, считающий количество элементов в `deque`.|
|[value_type](#value_type)|Тип, который представляет тип данных, хранящийся в контейнере `deque`.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[assign](#assign)|Удаляет элементы из `deque` и копирует новую последовательность элементов в целевой объект `deque`.|
|[at](#at)|Возвращает ссылку на элемент в заданном положении в `deque`.|
|[back](#back)|Возвращает ссылку на последний элемент в `deque`.|
|[begin](#begin)|Возвращает итератор произвольного доступа, указывающий на первый элемент в `deque`.|
|[cbegin](#cbegin)|Возвращает константный итератор, который указывает на первый элемент в `deque`.|
|[cend](#cend)|Возвращает итератор произвольного доступа **`const`** , указывающий на место сразу за концом `deque` .|
|[clear](#clear)|Стирает все элементы в `deque`.|
|[crbegin](#crbegin)|Возвращает константный итератор произвольного доступа, указывающий на первый элемент в `deque`, просматриваемый в обратном порядке.|
|[crend](#crend)|Возвращает константный итератор произвольного доступа, указывающий на первый элемент в `deque`, просматриваемый в обратном порядке.|
|[emplace](#emplace)|Вставляет элемент, созданный на месте, в указанное положение в `deque`.|
|[emplace_back](#emplace_back)|Добавляет элемент, созданный на месте, в конец `deque`.|
|[emplace_front](#emplace_front)|Добавляет элемент, созданный на месте, в начало `deque`.|
|[empty](#empty)|Возвращает **`true`** , если `deque` содержит нулевые элементы и **`false`** содержит один или несколько элементов.|
|[end](#end)|Возвращает итератор произвольного доступа, который указывает на позицию, следующую за концом `deque`.|
|[erase](#erase)|Удаляет элемент или диапазон элементов с указанных позиций в `deque`.|
|[front](#front)|Возвращает ссылку на первый элемент в `deque`.|
|[get_allocator](#get_allocator)|Возвращает копию объекта `allocator`, который используется для создания `deque`.|
|[insert](#insert)|Вставляет элемент, несколько элементов или диапазон элементов в `deque` в заданной позиции.|
|[max_size](#max_size)|Возвращает максимально возможную длину `deque`.|
|[pop_back](#pop_back)|Удаляет элемент в конце `deque`.|
|[pop_front](#pop_front)|Удаляет элемент в начале `deque`.|
|[push_back](#push_back)|Добавляет элемент в конец `deque`.|
|[push_front](#push_front)|Добавляет элемент в начало `deque`.|
|[rbegin](#rbegin)|Возвращает итератор произвольного доступа, указывающий на первый элемент в обратном `deque`.|
|[rend](#rend)|Возвращает итератор произвольного доступа, указывающий на расположение после последнего элемента в обратном `deque`.|
|[resize](#resize)|Указывает новый размер `deque`.|
|[shrink_to_fit](#shrink_to_fit)|Удаляет лишнюю емкость.|
|[size](#size)|Возвращает количество элементов в контейнере `deque`.|
|[swap](#swap)|Выполняет обмен элементами между двумя объектами `deque`.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator&#91;&#93;](#op_at)|Возвращает ссылку на элемент `deque` в указанной позиции.|
|[operator=](#op_eq)|Заменяет элементы `deque` копией другого `deque`.|

## <a name="allocator_type"></a><a name="allocator_type"></a> allocator_type

Тип, представляющий класс allocator для объекта deque.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Примечания

`allocator_type` является синонимом для параметра-шаблона `Allocator`.

### <a name="example"></a>Пример

См. пример для [get_allocator](#get_allocator).

## <a name="assign"></a><a name="assign"></a> assign

Удаляет элементы из очереди и копирует новый набор элементов в целевую очередь.

```cpp
template <class InputIterator>
void assign(
    InputIterator First,
    InputIterator Last);

void assign(
    size_type Count,
    const Type& Val);

void assign(initializer_list<Type> IList);
```

### <a name="parameters"></a>Параметры

*First*\
Положение первого элемента в диапазоне элементов, копируемых из очереди аргументов.

*Last*\
Положение первого элемента за пределами диапазона элементов, копируемых из очереди аргументов.

*Count*\
Количество копий элемента, вставляемых в очередь.

*Val*\
Значение элемента, вставляемого в очередь.

*IList*\
Объект initializer_list, вставляемый в очередь.

### <a name="remarks"></a>Примечания

После удаления любых существующих элементов в целевой очереди `assign` либо вставляет указанный диапазон элементов из исходной очереди или какой-либо другой очереди в целевую очередь, либо вставляет копии нового элемента указанного значения в целевую очередь.

### <a name="example"></a>Пример

```cpp
// deque_assign.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
#include <initializer_list>

int main()
{
    using namespace std;
    deque <int> c1, c2;
    deque <int>::const_iterator cIter;

    c1.push_back(10);
    c1.push_back(20);
    c1.push_back(30);
    c2.push_back(40);
    c2.push_back(50);
    c2.push_back(60);

    deque<int> d1{ 1, 2, 3, 4 };
    initializer_list<int> iList{ 5, 6, 7, 8 };
    d1.assign(iList);

    cout << "d1 = ";
    for (int i : d1)
        cout << i;
    cout << endl;

    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;

    c1.assign(++c2.begin(), c2.end());
    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;

    c1.assign(7, 4);
    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;
}
```

```Output
d1 = 5678c1 =102030c1 =5060c1 =4444444
```

## <a name="at"></a><a name="at"></a> at

Возвращает ссылку на элемент в заданном положении в очереди.

```cpp
reference at(size_type pos);

const_reference at(size_type pos) const;
```

### <a name="parameters"></a>Параметры

*pos*\
Нижний индекс (или номер позиции) элемента, на который включается ссылка в очереди.

### <a name="return-value"></a>Возвращаемое значение

Если значение *pos* превышает размер deque, `at` вызывается исключение.

### <a name="return-value"></a>Возвращаемое значение

Если возвращаемое значение `at` присвоено `const_reference`, то объект очереди нельзя изменить. Если возвращаемое значение `at` присвоено `reference`, то объект очереди можно изменить.

### <a name="example"></a>Пример

```cpp
// deque_at.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const int& i = c1.at( 0 );
   int& j = c1.at( 1 );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="back"></a><a name="back"></a> back

Возвращает ссылку на последний элемент очереди.

```cpp
reference back();
const_reference back() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последний элемент очереди. Если очередь пуста, возвращаемое значение не определено.

### <a name="remarks"></a>Примечания

Если возвращаемое значение `back` присвоено `const_reference`, то объект очереди нельзя изменить. Если возвращаемое значение `back` присвоено `reference`, то объект очереди можно изменить.

При компиляции с помощью [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), для которого задано значение 1 или 2, возникнет ошибка времени выполнения при попытке доступа к элементу в пустой очереди.  Дополнительные сведения см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// deque_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 11 );

   int& i = c1.back( );
   const int& ii = c1.front( );

   cout << "The last integer of c1 is " << i << endl;
   i--;
   cout << "The next-to-last integer of c1 is " << ii << endl;
}
```

```Output
The last integer of c1 is 11
The next-to-last integer of c1 is 10
```

## <a name="begin"></a><a name="begin"></a> begin

Возвращает итератор, адресующий первый элемент в очереди.

```cpp
const_iterator begin() const;
iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор произвольного доступа, адресующий первый элемент в очереди или расположение после пустой очереди.

### <a name="remarks"></a>Примечания

Если возвращаемое значение `begin` присвоено `const_iterator`, то объект очереди нельзя изменить. Если возвращаемое значение `begin` присваивается `iterator` , то объект deque можно изменить.

### <a name="example"></a>Пример

```cpp
// deque_begin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::const_iterator c1_cIter;

   c1.push_back( 1 );
   c1.push_back( 2 );

   c1_Iter = c1.begin( );
   cout << "The first element of c1 is " << *c1_Iter << endl;

*c1_Iter = 20;
   c1_Iter = c1.begin( );
   cout << "The first element of c1 is now " << *c1_Iter << endl;

   // The following line would be an error because iterator is const
   // *c1_cIter = 200;
}
```

```Output
The first element of c1 is 1
The first element of c1 is now 20
```

## <a name="cbegin"></a><a name="cbegin"></a> cbegin

Возвращает **`const`** итератор, который обращается к первому элементу в диапазоне.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`const`** Итератор произвольного доступа, указывающий на первый элемент диапазона, или расположение непосредственно за концом пустого диапазона (для пустого диапазона `cbegin() == cend()` ).

### <a name="remarks"></a>Примечания

Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.

Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере рекомендуется использовать `Container` изменяемый (не- **`const`** ) контейнер любого типа, который поддерживает `begin()` и `cbegin()` .

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a><a name="cend"></a> cend

Возвращает **`const`** итератор, который обращается к расположению сразу за последним элементом в диапазоне.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор произвольного доступа, который указывает на место сразу после конца диапазона.

### <a name="remarks"></a>Примечания

`cend` используется для проверки того, прошел ли итератор конец диапазона.

Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере рекомендуется использовать `Container` изменяемый (не- **`const`** ) контейнер любого типа, который поддерживает `end()` и `cend()` .

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.

## <a name="clear"></a><a name="clear"></a> clear

Стирает все элементы в очереди.

```cpp
void clear();
```

### <a name="example"></a>Пример

```cpp
// deque_clear.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   cout << "The size of the deque is initially " << c1.size( ) << endl;
   c1.clear( );
   cout << "The size of the deque after clearing is " << c1.size( ) << endl;
}
```

```Output
The size of the deque is initially 3
The size of the deque after clearing is 0
```

## <a name="const_iterator"></a><a name="const_iterator"></a> const_iterator

Тип, предоставляющий итератор произвольного доступа, который может получать доступ к **`const`** элементу в deque и считывать его.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_iterator`нельзя использовать для изменения значения элемента.

### <a name="example"></a>Пример

См. пример для [back](#back).

## <a name="const_pointer"></a><a name="const_pointer"></a> const_pointer

Предоставляет указатель на **`const`** элемент в deque.

```cpp
typedef typename Allocator::const_pointer const_pointer;
```

### <a name="remarks"></a>Примечания

Тип `const_pointer`нельзя использовать для изменения значения элемента. Для доступа к элементу очереди чаще используется [iterator](#iterator).

## <a name="const_reference"></a><a name="const_reference"></a> const_reference

Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в deque для чтения и выполнения **`const`** операций.

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Примечания

Тип `const_reference`нельзя использовать для изменения значения элемента.

### <a name="example"></a>Пример

```cpp
// deque_const_ref.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const deque <int> c2 = c1;
   const int &i = c2.front( );
   const int &j = c2.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;

   // The following line would cause an error as c2 is const
   // c2.push_back( 30 );
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="const_reverse_iterator"></a><a name="const_reverse_iterator"></a> const_reverse_iterator

Тип, предоставляющий итератор произвольного доступа, который может читать любой **`const`** элемент в deque.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_reverse_iterator` не может изменять значение элемента и используется для последовательного прохождения через очередь в обратную сторону.

### <a name="example"></a>Пример

См. пример объявления и использования итератора в разделе [rbegin](#rbegin).

## <a name="crbegin"></a><a name="crbegin"></a> crbegin

Возвращает константный итератор первому элементу в очереди в обратную сторону.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный итератор произвольного доступа, указывающий на первый элемент в обращенном объекте [deque](../standard-library/deque-class.md) или на элемент, который был последним в `deque` до обращения.

### <a name="remarks"></a>Примечания

Если возвращаемое значение `crbegin`, то объект `deque` невозможно изменить.

### <a name="example"></a>Пример

```cpp
// deque_crbegin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::iterator v1_Iter;
   deque <int>::const_reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   v1_Iter = v1.begin( );
   cout << "The first element of deque is "
        << *v1_Iter << "." << endl;

   v1_rIter = v1.crbegin( );
   cout << "The first element of the reversed deque is "
        << *v1_rIter << "." << endl;
}
```

```Output
The first element of deque is 1.
The first element of the reversed deque is 2.
```

## <a name="crend"></a><a name="crend"></a> crend

Возвращает константный итератор, который указывает на расположение после последнего элемента в очереди в обратную сторону.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный итератор произвольного доступа, адресующий расположение после последнего элемента в обращенном объекте [deque](../standard-library/deque-class.md) (расположение перед первым элементом в необращенной очереди).

### <a name="remarks"></a>Примечания

`crend` используется с обращенной `deque` точно так же, как [array::cend](../standard-library/array-class-stl.md#cend) используется с `deque`.

Если возвращается значение `crend` (уменьшенное соответствующим образом), объект `deque` изменить нельзя.

`crend` можно использовать, чтобы проверить, достиг ли обратный итератор конца очереди.

Значение, возвращаемое `crend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// deque_crend.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::const_reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )
      cout << *v1_rIter << endl;
}
```

```Output
2
1
```

## <a name="deque"></a><a name="deque"></a> deque

Создает очередь определенного размера или с элементами определенного значения, или с определенным распределителем, или в качестве копии какой-либо другой очереди или ее части.

```cpp
deque();

explicit deque(const Allocator& Al);
explicit deque(size_type Count);
deque(size_type Count, const Type& Val);

deque(
    size_type Count,
    const Type& Val,
    const Allocator& Al);

deque(const deque& Right);

template <class InputIterator>
deque(InputIterator First,  InputIterator Last);

template <class InputIterator>
deque(
   InputIterator First,
   InputIterator Last,
   const Allocator& Al);

deque(initializer_list<value_type> IList, const Allocator& Al);
```

### <a name="parameters"></a>Параметры

*Al*\
Класс распределителя для использования с данным объектом.

*Count*\
Количество элементов в создаваемой очереди.

*Val*\
Значение элементов в создаваемой очереди.

*Right*\
Очередь, для которой создаваемая очередь станет копией.

*First*\
Положение первого элемента в диапазоне копируемых элементов.

*last*\
Положение первого элемента за пределами диапазона копируемых элементов.

*IList*\
Копируемый initializer_list.

### <a name="remarks"></a>Примечания

Все конструкторы хранят объект распределителя (*Al*) и инициализируют deque.

Первые два конструктора указывают пустую начальную deque; второй также указывает тип распределителя ( `_Al` ) для использования.

Третий конструктор задает повторение указанного числа (`count`) элементов со значением по умолчанию для класса `Type`.

Четвертый и пятый конструкторы указывают повторение элементов (*Count*) значения `val` .

Шестой конструктор задает копию *правого*deque.

Седьмой и восьмой конструкторы копируют диапазон `[First, Last)` очереди.

Седьмой конструктор перемещает *право*deque.

Восьмой конструктор копирует содержимое initializer_list.

Ни один из конструкторов не выполняет промежуточные перераспределения.

### <a name="example"></a>Пример

```cpp
/ compile with: /EHsc
#include <deque>
#include <iostream>
#include <forward_list>

int main()
{
    using namespace std;

    forward_list<int> f1{ 1, 2, 3, 4 };

    f1.insert_after(f1.begin(), { 5, 6, 7, 8 });

    deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;

    // Create an empty deque c0
    deque <int> c0;

    // Create a deque c1 with 3 elements of default value 0
    deque <int> c1(3);

    // Create a deque c2 with 5 elements of value 2
    deque <int> c2(5, 2);

    // Create a deque c3 with 3 elements of value 1 and with the
    // allocator of deque c2
    deque <int> c3(3, 1, c2.get_allocator());

    // Create a copy, deque c4, of deque c2
    deque <int> c4(c2);

    // Create a deque c5 by copying the range c4[ first,  last)
    c4_Iter = c4.begin();
    c4_Iter++;
    c4_Iter++;
    deque <int> c5(c4.begin(), c4_Iter);

    // Create a deque c6 by copying the range c4[ first,  last) and
    // c2 with the allocator of deque
    c4_Iter = c4.begin();
    c4_Iter++;
    c4_Iter++;
    c4_Iter++;
    deque <int> c6(c4.begin(), c4_Iter, c2.get_allocator());

    // Create a deque c8 by copying the contents of an initializer_list
    // using brace initialization
    deque<int> c8({ 1, 2, 3, 4 });

    initializer_list<int> iList{ 5, 6, 7, 8 };
    deque<int> c9( iList);

    cout << "c1 = ";
    for (int i : c1)
        cout << i << " ";
    cout << endl;

    cout << "c2 = ";
    for (int i : c2)
        cout << i << " ";
    cout << endl;

    cout << "c3 = ";
    for (int i : c3)
        cout << i << " ";
    cout << endl;

    cout << "c4 = ";
    for (int i : c4)
        cout << i << " ";
    cout << endl;

    cout << "c5 = ";
    for (int i : c5)
        cout << i << " ";
    cout << endl;

    cout << "c6 = ";
    for (int i : c6)
        cout << i << " ";
    cout << endl;

    // Move deque c6 to deque c7
    deque <int> c7(move(c6));
    deque <int>::iterator c7_Iter;

    cout << "c7 =";
    for (int i : c7)
        cout << i << " ";
    cout << endl;

    cout << "c8 = ";
    for (int i : c8)
        cout << i << " ";
    cout << endl;

    cout << "c9 = ";
    for (int i : c9)
        cout << i << " ";
    cout << endl;

    int x = 3;
}
// deque_deque.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
    using namespace std;
   deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;

    // Create an empty deque c0
    deque <int> c0;

    // Create a deque c1 with 3 elements of default value 0
    deque <int> c1( 3 );

    // Create a deque c2 with 5 elements of value 2
    deque <int> c2( 5, 2 );

    // Create a deque c3 with 3 elements of value 1 and with the
    // allocator of deque c2
    deque <int> c3( 3, 1, c2.get_allocator( ) );

    // Create a copy, deque c4, of deque c2
    deque <int> c4( c2 );

    // Create a deque c5 by copying the range c4[ first,  last)
    c4_Iter = c4.begin( );
    c4_Iter++;
    c4_Iter++;
    deque <int> c5( c4.begin( ), c4_Iter );

    // Create a deque c6 by copying the range c4[ first,  last) and
    // c2 with the allocator of deque
    c4_Iter = c4.begin( );
   c4_Iter++;
   c4_Iter++;
   c4_Iter++;
   deque <int> c6( c4.begin( ), c4_Iter, c2.get_allocator( ) );

    // Create a deque c8 by copying the contents of an initializer_list
    // using brace initialization
    deque<int> c8({ 1, 2, 3, 4 });

        initializer_list<int> iList{ 5, 6, 7, 8 };
    deque<int> c9( iList);

    cout << "c1 = ";
    for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
        cout << *c1_Iter << " ";
    cout << endl;

    cout << "c2 = ";
    for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )
        cout << *c2_Iter << " ";
    cout << endl;

    cout << "c3 = ";
    for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )
        cout << *c3_Iter << " ";
    cout << endl;

    cout << "c4 = ";
    for ( c4_Iter = c4.begin( ); c4_Iter != c4.end( ); c4_Iter++ )
        cout << *c4_Iter << " ";
    cout << endl;

    cout << "c5 = ";
    for ( c5_Iter = c5.begin( ); c5_Iter != c5.end( ); c5_Iter++ )
        cout << *c5_Iter << " ";
    cout << endl;

    cout << "c6 = ";
    for ( c6_Iter = c6.begin( ); c6_Iter != c6.end( ); c6_Iter++ )
        cout << *c6_Iter << " ";
    cout << endl;

    // Move deque c6 to deque c7
    deque <int> c7( move(c6) );
    deque <int>::iterator c7_Iter;

    cout << "c7 =" ;
    for ( c7_Iter = c7.begin( ) ; c7_Iter != c7.end( ) ; c7_Iter++ )
        cout << " " << *c7_Iter;
    cout << endl;

    cout << "c8 = ";
    for (int i : c8)
        cout << i << " ";
    cout << endl;

    cout << "c9 = ";
    or (int i : c9)
        cout << i << " ";
    cout << endl;
}
```

## <a name="difference_type"></a><a name="difference_type"></a> difference_type

Тип, предоставляющий разницу между двумя итераторами, ссылающимися на элементы в одной и той же очереди.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Примечания

`difference_type` также можно описать как число элементов между двумя указателями.

### <a name="example"></a>Пример

```cpp
// deque_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <deque>
#include <algorithm>

int main( )
{
   using namespace std;

   deque <int> c1;
   deque <int>::iterator c1_Iter, c2_Iter;

   c1.push_back( 30 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 10 );
   c1.push_back( 30 );
   c1.push_back( 20 );

   c1_Iter = c1.begin( );
   c2_Iter = c1.end( );

   deque <int>::difference_type df_typ1, df_typ2, df_typ3;

   df_typ1 = count( c1_Iter, c2_Iter, 10 );
   df_typ2 = count( c1_Iter, c2_Iter, 20 );
   df_typ3 = count( c1_Iter, c2_Iter, 30 );
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";
}
```

```Output
The number '10' is in c1 collection 1 times.
The number '20' is in c1 collection 2 times.
The number '30' is in c1 collection 3 times.
```

## <a name="emplace"></a><a name="emplace"></a> emplace

Вставляет элемент, созданный на месте, в указанное положение в очереди.

```cpp
iterator emplace(
    const_iterator _Where,
    Type&& val);
```

### <a name="parameters"></a>Параметры

*_Where*\
Позиция в объекте [deque](../standard-library/deque-class.md), куда вставляется первый элемент.

*val*\
Значение элемента, вставляемого в `deque`.

### <a name="return-value"></a>Возвращаемое значение

Функция возвращает итератор, указывающий на положение вставки нового элемента в очередь.

### <a name="remarks"></a>Примечания

Любая операция вставки может быть ресурсоемкой. Факторы производительности при работе с объектом `deque` рассматриваются в разделе `deque`.

### <a name="example"></a>Пример

```cpp
// deque_emplace.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::iterator Iter;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );

   cout << "v1 =" ;
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

   vv1.emplace( vv1.begin(), move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      {
      cout << "vv1[0] =";
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )
         cout << " " << *Iter;
      cout << endl;
      }
}
```

```Output
v1 = 10 20 30
vv1[0] = 10 20 30
```

## <a name="emplace_back"></a><a name="emplace_back"></a> emplace_back

Добавляет элемент, созданный на месте, в конец очереди.

```cpp
void emplace_back(Type&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Элемент, добавляемый в конец объекта [deque](../standard-library/deque-class.md).

### <a name="example"></a>Пример

```cpp
// deque_emplace_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;

   v1.push_back( 1 );
   if ( v1.size( ) != 0 )
      cout << "Last element: " << v1.back( ) << endl;

   v1.push_back( 2 );
   if ( v1.size( ) != 0 )
      cout << "New last element: " << v1.back( ) << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

   vv1.emplace_back( move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      cout << "Moved last element: " << vv1[0].back( ) << endl;
}
```

```Output
Last element: 1
New last element: 2
Moved last element: 2
```

## <a name="emplace_front"></a><a name="emplace_front"></a> emplace_front

Добавляет элемент, созданный на месте, в конец очереди.

```cpp
void emplace_front(Type&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Элемент, добавляемый в начало [deque](../standard-library/deque-class.md).

### <a name="example"></a>Пример

```cpp
// deque_emplace_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;

   v1.push_back( 1 );
   if ( v1.size( ) != 0 )
      cout << "Last element: " << v1.back( ) << endl;

   v1.push_back( 2 );
   if ( v1.size( ) != 0 )
      cout << "New last element: " << v1.back( ) << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

   vv1.emplace_front( move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      cout << "Moved last element: " << vv1[0].back( ) << endl;
}
```

```Output
Last element: 1
New last element: 2
Moved last element: 2
```

## <a name="empty"></a><a name="empty"></a> empty

Проверяет, пуста ли очередь.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если deque пусто; **`false`** Если deque не является пустым.

### <a name="example"></a>Пример

```cpp
// deque_empty.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   if ( c1.empty( ) )
      cout << "The deque is empty." << endl;
   else
      cout << "The deque is not empty." << endl;
}
```

```Output
The deque is not empty.
```

## <a name="end"></a><a name="end"></a> end

Возвращает итератор, адресующий расположение за последним элементом в очереди.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает итератор произвольного доступа, адресующий расположение за последним элементом в очереди. Если очередь пуста, то deque::end == deque::begin.

### <a name="remarks"></a>Примечания

`end` используется для проверки того, достиг ли итератор конца его deque.

### <a name="example"></a>Пример

```cpp
// deque_end.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_Iter = c1.end( );
   c1_Iter--;
   cout << "The last integer of c1 is " << *c1_Iter << endl;

   c1_Iter--;
   *c1_Iter = 400;
   cout << "The new next-to-last integer of c1 is " << *c1_Iter << endl;

   // If a const iterator had been declared instead with the line:
   // deque <int>::const_iterator c1_Iter;
   // an error would have resulted when inserting the 400

   cout << "The deque is now:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
}
```

```Output
The last integer of c1 is 30
The new next-to-last integer of c1 is 400
The deque is now: 10 400 30
```

## <a name="erase"></a><a name="erase"></a> erase

Удаляет элемент или диапазон элементов с указанных позиций в очереди.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);
```

### <a name="parameters"></a>Параметры

*_Where*\
Положение элемента, удаляемого из очереди.

*first*\
Положение первого элемента, удаленного из очереди.

*last*\
Положение после последнего элемента, удаленного из очереди.

### <a name="return-value"></a>Возвращаемое значение

Итератор произвольного доступа, указывающий на первый элемент, оставшийся после удаленных элементов, или на указатель конца очереди, если такого элемента не существует.

### <a name="remarks"></a>Примечания

`erase` никогда не создает исключений.

### <a name="example"></a>Пример

```cpp
// deque_erase.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator Iter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 40 );
   c1.push_back( 50 );
   cout << "The initial deque is: ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
   c1.erase( c1.begin( ) );
   cout << "After erasing the first element, the deque becomes:  ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
   Iter = c1.begin( );
   Iter++;
   c1.erase( Iter, c1.end( ) );
   cout << "After erasing all elements but the first, deque becomes: ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
}
```

```Output
The initial deque is: 10 20 30 40 50
After erasing the first element, the deque becomes:  20 30 40 50
After erasing all elements but the first, deque becomes: 20
```

## <a name="front"></a><a name="front"></a> front

Возвращает ссылку на первый элемент в очереди.

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если очередь пуста, возвращаемое значение не определено.

### <a name="remarks"></a>Примечания

Если возвращаемое значение `front` присвоено `const_reference`, то объект очереди нельзя изменить. Если возвращаемое значение `front` присвоено `reference`, то объект очереди можно изменить.

При компиляции с помощью [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), для которого задано значение 1 или 2, возникнет ошибка времени выполнения при попытке доступа к элементу в пустой очереди.  Дополнительные сведения см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// deque_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 11 );

   int& i = c1.front( );
   const int& ii = c1.front( );

   cout << "The first integer of c1 is " << i << endl;
   i++;
   cout << "The second integer of c1 is " << ii << endl;
}
```

```Output
The first integer of c1 is 10
The second integer of c1 is 11
```

## <a name="get_allocator"></a><a name="get_allocator"></a> get_allocator

Возвращает копию объекта распределителя, использованного для создания очереди.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Распределитель, используемый очередью.

### <a name="remarks"></a>Примечания

Распределители для класса очереди определяют, как этот класс управляет хранилищем. Распределителей по умолчанию в классах контейнеров стандартной библиотеки C++ достаточно для большинства задач программирования. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.

### <a name="example"></a>Пример

```cpp
// deque_get_allocator.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   // The following lines declare objects that use the default allocator.
   deque <int> c1;
   deque <int, allocator<int> > c2 = deque <int, allocator<int> >( allocator<int>( ) );

   // c3 will use the same allocator class as c1
   deque <int> c3( c1.get_allocator( ) );

   deque <int>::allocator_type xlst = c1.get_allocator( );
   // You can now call functions on the allocator class used by c1
}
```

## <a name="insert"></a><a name="insert"></a> insert

Вставляет один элемент, несколько элементов или диапазон элементов в указанное положение в очереди.

```cpp
iterator insert(
    const_iterator Where,
    const Type& Val);

iterator insert(
    const_iterator Where,
    Type&& Val);

void insert(
    iterator Where,
    size_type Count,
    const Type& Val);

template <class InputIterator>
void insert(
    iterator Where,
    InputIterator First,
    InputIterator Last);

iterator insert(
    iterator Where,initializer_list<Type>
IList);
```

### <a name="parameters"></a>Параметры

*Where*\
Положение в целевой очереди, куда вставляется первый элемент.

*val*\
Значение элемента, вставляемого в очередь.

*Count*\
Количество элементов, вставляемых в очередь.

*First*\
Положение первого элемента в диапазоне элементов в копируемой очереди аргументов.

*last*\
Положение первого элемента за пределами диапазона элементов в копируемой очереди аргументов.

*Интерфейс*\
Объект initializer_list, содержащий вставляемые элементы.

### <a name="return-value"></a>Возвращаемое значение

Две первые функции вставки возвращают итератор, указывающий на положение вставки нового элемента в очередь.

### <a name="remarks"></a>Примечания

Любая операция вставки может быть ресурсоемкой.

## <a name="iterator"></a><a name="iterator"></a> iterator

Тип, предоставляющий итератор произвольного доступа, который может читать или изменять любой элемент в очереди.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Примечания

Тип `iterator` можно использовать для изменения значения элемента.

### <a name="example"></a>Пример

См. пример для [begin](#begin).

## <a name="max_size"></a><a name="max_size"></a> max_size

Возвращает максимальную длину очереди.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимально возможная длина очереди.

### <a name="example"></a>Пример

```cpp
// deque_max_size.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::size_type i;

   i = c1.max_size( );
   cout << "The maximum possible length of the deque is " << i << "." << endl;
}
```

## <a name="operator"></a><a name="op_at"></a> operator[]

Возвращает ссылку на элемент очереди в указанной позиции.

```cpp
reference operator[](size_type pos);

const_reference operator[](size_type pos) const;
```

### <a name="parameters"></a>Параметры

*pos*\
Положение элемента очереди, на который должна быть ссылка.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент, позиция которого указана в аргументе. Если заданная позиция больше размера очереди, результат не определен.

### <a name="remarks"></a>Примечания

Если возвращаемое значение `operator[]` присвоено `const_reference`, то объект очереди нельзя изменить. Если возвращаемое значение `operator[]` присвоено `reference`, то объект очереди можно изменить.

При компиляции с помощью [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), для которого задано значение 1 или 2, возникнет ошибка времени выполнения при попытке доступа к элементу за пределами очереди.  Дополнительные сведения см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).

### <a name="example"></a>Пример

```cpp
// deque_op_ref.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   cout << "The first integer of c1 is " << c1[0] << endl;
   int& i = c1[1];
   cout << "The second integer of c1 is " << i << endl;
}
```

```Output
The first integer of c1 is 10
The second integer of c1 is 20
```

## <a name="operator"></a><a name="op_eq"></a> operator=

Заменяет элементы этой очереди с помощью элементов из другой очереди.

```cpp
deque& operator=(const deque& right);

deque& operator=(deque&& right);
```

### <a name="parameters"></a>Параметры

*right*\
Очередь, предоставляющая новое содержимое.

### <a name="remarks"></a>Примечания

Первое переопределение копирует элементы в этот deque с *правого*края, источника назначения. Второе переопределение перемещает элементы в deque из *right*.

Элементы, содержащиеся в этой очереди перед выполнением оператора, удаляются.

### <a name="example"></a>Пример

```cpp
// deque_operator_as.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
using namespace std;

typedef deque<int> MyDeque;

template<typename MyDeque> struct S;

template<typename MyDeque> struct S<MyDeque&> {
  static void show( MyDeque& d ) {
    MyDeque::const_iterator iter;
    for (iter = d.cbegin(); iter != d.cend(); iter++)
       cout << *iter << " ";
    cout << endl;
  }
};

template<typename MyDeque> struct S<MyDeque&&> {
  static void show( MyDeque&& d ) {
    MyDeque::const_iterator iter;
    for (iter = d.cbegin(); iter != d.cend(); iter++)
       cout << *iter << " ";
cout << " via unnamed rvalue reference " << endl;
  }
};

int main( )
{
   MyDeque d1, d2;

   d1.push_back(10);
   d1.push_back(20);
   d1.push_back(30);
   d1.push_back(40);
   d1.push_back(50);

   cout << "d1 = " ;
   S<MyDeque&>::show( d1 );

   d2 = d1;
   cout << "d2 = ";
   S<MyDeque&>::show( d2 );

   cout << "     ";
   S<MyDeque&&>::show ( move< MyDeque& > (d1) );
}
```

## <a name="pointer"></a><a name="pointer"></a> pointer

Предоставляет указатель на элемент в объекте [deque](../standard-library/deque-class.md).

```unstlib
typedef typename Allocator::pointer pointer;
```

### <a name="remarks"></a>Примечания

Тип `pointer` можно использовать для изменения значения элемента. Для доступа к элементу очереди чаще используется [iterator](#iterator).

## <a name="pop_back"></a><a name="pop_back"></a> pop_back

Удаляет элемент в конце очереди.

```cpp
void pop_back();
```

### <a name="remarks"></a>Примечания

Последний элемент не должен быть пустым. `pop_back` никогда не создает исключений.

### <a name="example"></a>Пример

```cpp
// deque_pop_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 1 );
   c1.push_back( 2 );
   cout << "The first element is: " << c1.front( ) << endl;
   cout << "The last element is: " << c1.back( ) << endl;

   c1.pop_back( );
   cout << "After deleting the element at the end of the deque, the "
      "last element is: " << c1.back( ) << endl;
}
```

```Output
The first element is: 1
The last element is: 2
After deleting the element at the end of the deque, the last element is: 1
```

## <a name="pop_front"></a><a name="pop_front"></a> pop_front

Удаляет элемент в начале очереди.

```cpp
void pop_front();
```

### <a name="remarks"></a>Примечания

Первый элемент не должен быть пустым. `pop_front` никогда не создает исключений.

### <a name="example"></a>Пример

```cpp
// deque_pop_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 1 );
   c1.push_back( 2 );
   cout << "The first element is: " << c1.front( ) << endl;
   cout << "The second element is: " << c1.back( ) << endl;

   c1.pop_front( );
   cout << "After deleting the element at the beginning of the "
      "deque, the first element is: " << c1.front( ) << endl;
}
```

```Output
The first element is: 1
The second element is: 2
After deleting the element at the beginning of the deque, the first element is: 2
```

## <a name="push_back"></a><a name="push_back"></a> push_back

Добавляет элемент в конец очереди.

```cpp
void push_back(const Type& val);

void push_back(Type&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Элемент, добавляемый в конец очереди.

### <a name="remarks"></a>Примечания

При создании исключения очередь не изменяется, а исключение создается снова.

## <a name="push_front"></a><a name="push_front"></a> push_front

Добавляет элемент в начало очереди.

```cpp
void push_front(const Type& val);
void push_front(Type&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Элемент, добавляемый в начало очереди.

### <a name="remarks"></a>Примечания

При создании исключения очередь не изменяется, а исключение создается снова.

### <a name="example"></a>Пример

```cpp
// deque_push_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_front( 1 );
   if ( c1.size( ) != 0 )
      cout << "First element: " << c1.front( ) << endl;

   c1.push_front( 2 );
   if ( c1.size( ) != 0 )
      cout << "New first element: " << c1.front( ) << endl;

// move initialize a deque of strings
   deque <string> c2;
   string str("a");

   c2.push_front( move( str ) );
   cout << "Moved first element: " << c2.front( ) << endl;
}
```

```Output
First element: 1
New first element: 2
Moved first element: a
```

## <a name="rbegin"></a><a name="rbegin"></a> rbegin

Возвращает итератор, указывающий на первый элемент в обращенной очереди.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный итератор произвольного доступа, указывающий на первый элемент в обращенной очереди или на последний элемент в необращенной очереди.

### <a name="remarks"></a>Примечания

`rbegin` используется с обращенной очередью точно так же, как [begin](#begin) используется с очередью.

Если возвращаемое значение `rbegin` присвоено `const_reverse_iterator`, то объект очереди нельзя изменить. Если возвращаемое значение `rbegin` присвоено `reverse_iterator`, то объект очереди можно изменить.

`rbegin` можно использовать для последовательного прохождения по очереди в обратную сторону.

### <a name="example"></a>Пример

```cpp
// deque_rbegin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::reverse_iterator c1_rIter;

   // If the following line had replaced the line above, an error
   // would have resulted in the line modifying an element
   // (commented below) because the iterator would have been const
   // deque <int>::const_reverse_iterator c1_rIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_rIter = c1.rbegin( );
   cout << "Last element in the deque is " << *c1_rIter << "." << endl;

   cout << "The deque contains the elements: ";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << *c1_Iter << " ";
   cout << "in that order.";
   cout << endl;

   // rbegin can be used to iterate through a deque in reverse order
   cout << "The reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;

   c1_rIter = c1.rbegin( );
   *c1_rIter = 40;  // This would have caused an error if a
                    // const_reverse iterator had been declared as
                    // noted above
   cout << "Last element in deque is now " << *c1_rIter << "." << endl;
}
```

```Output
Last element in the deque is 30.
The deque contains the elements: 10 20 30 in that order.
The reversed deque is: 30 20 10
Last element in deque is now 40.
```

## <a name="reference"></a><a name="reference"></a> IsReference

Тип, предоставляющий ссылку на элемент, хранящийся в очереди.

```cpp
typedef typename Allocator::reference reference;
```

### <a name="example"></a>Пример

```cpp
// deque_reference.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const int &i = c1.front( );
   int &j = c1.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="rend"></a><a name="rend"></a> rend

Возвращает итератор, адресующий расположение после последнего элемента в обращенной очереди.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный итератор произвольного доступа, адресующий расположение после последнего элемента в обращенной очереди (расположение перед первым элементом в необращенной очереди).

### <a name="remarks"></a>Примечания

`rend` используется с обращенной очередью точно так же, как [end](#end) используется с очередью.

Если возвращаемое значение `rend` присвоено `const_reverse_iterator`, то объект очереди нельзя изменить. Если возвращаемое значение `rend` присвоено `reverse_iterator`, то объект очереди можно изменить.

`rend` можно использовать, чтобы проверить, достиг ли обратный итератор конца очереди.

Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// deque_rend.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;

   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::reverse_iterator c1_rIter;
   // If the following line had replaced the line above, an error
   // would have resulted in the line modifying an element
   // (commented below) because the iterator would have been const
   // deque <int>::const_reverse_iterator c1_rIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_rIter = c1.rend( );
   c1_rIter --; // Decrementing a reverse iterator moves it forward
                // in the deque (to point to the first element here)
   cout << "The first element in the deque is: " << *c1_rIter << endl;

   cout << "The deque is: ";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << *c1_Iter << " ";
   cout << endl;

   // rend can be used to test if an iteration is through all of
   // the elements of a reversed deque
   cout << "The reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;

   c1_rIter = c1.rend( );
   c1_rIter--; // Decrementing the reverse iterator moves it backward
               // in the reversed deque (to the last element here)
   *c1_rIter = 40; // This modification of the last element would
                   // have caused an error if a const_reverse
                   // iterator had been declared (as noted above)
   cout << "The modified reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;
}
```

```Output
The first element in the deque is: 10
The deque is: 10 20 30
The reversed deque is: 30 20 10
The modified reversed deque is: 30 20 40
```

## <a name="resize"></a><a name="resize"></a> resize

Указывает новый размер очереди.

```cpp
void resize(size_type _Newsize);

void resize(size_type _Newsize, Type val);
```

### <a name="parameters"></a>Параметры

*_Newsize*\
Новый размер очереди.

*val*\
Значение новых элементов, добавляемых в очередь, если новый размер больше исходного. Если значение не задано, новым элементам назначается значение по умолчанию для класса.

### <a name="remarks"></a>Примечания

Если размер deque меньше запрошенного размера, *_Newsize*элементы добавляются в deque до тех пор, пока не достигнет запрошенного размера.

Если размер deque больше запрошенного размера, элементы, ближайшие к концу deque, удаляются до тех пор, пока deque не достигнет размера *_Newsize*.

Если текущий размер очереди совпадает с запрошенным, никакие действия не выполняются.

[size](#size) — это текущий размер очереди.

### <a name="example"></a>Пример

```cpp
// deque_resize.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1.resize( 4,40 );
   cout << "The size of c1 is: " << c1.size( ) << endl;
   cout << "The value of the last element is " << c1.back( ) << endl;

   c1.resize( 5 );
   cout << "The size of c1 is now: " << c1.size( ) << endl;
   cout << "The value of the last element is now " << c1.back( ) << endl;

   c1.resize( 2 );
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;
   cout << "The value of the last element is now " << c1.back( ) << endl;
}
```

```Output
The size of c1 is: 4
The value of the last element is 40
The size of c1 is now: 5
The value of the last element is now 0
The reduced size of c1 is: 2
The value of the last element is now 20
```

## <a name="reverse_iterator"></a><a name="reverse_iterator"></a> reverse_iterator

Тип, предоставляющий итератор произвольного доступа, который может читать или изменять любой элемент в обращенной очереди.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `reverse_iterator` используется для итерации по очереди.

### <a name="example"></a>Пример

См. пример для rbegin.

## <a name="shrink_to_fit"></a><a name="shrink_to_fit"></a> shrink_to_fit

Удаляет лишнюю емкость.

```cpp
void shrink_to_fit();
```

### <a name="remarks"></a>Примечания

Переносимого способа определения, уменьшает ли `shrink_to_fit` хранилище, используемое объектом [deque](../standard-library/deque-class.md), не существует.

### <a name="example"></a>Пример

```cpp
// deque_shrink_to_fit.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   //deque <int>::iterator Iter;

   v1.push_back( 1 );
   v1.push_back( 2 );
   cout << "Current size of v1 = "
      << v1.size( ) << endl;
   v1.shrink_to_fit();
   cout << "Current size of v1 = "
      << v1.size( ) << endl;
}
```

```Output
Current size of v1 = 1
Current size of v1 = 1
```

## <a name="size"></a><a name="size"></a> size

Возвращает число элементов в очереди.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая длина очереди.

### <a name="example"></a>Пример

```cpp
// deque_size.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::size_type i;

   c1.push_back( 1 );
   i = c1.size( );
   cout << "The deque length is " << i << "." << endl;

   c1.push_back( 2 );
   i = c1.size( );
   cout << "The deque length is now " << i << "." << endl;
}
```

```Output
The deque length is 1.
The deque length is now 2.
```

## <a name="size_type"></a><a name="size_type"></a> size_type

Тип, который подсчитывает количество элементов в очереди.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="example"></a>Пример

См. пример для [size](#size).

## <a name="swap"></a><a name="swap"></a> swap

Меняет местами элементы двух объектов deque.

```cpp
void swap(deque<Type, Allocator>& right);

friend void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right) template <class Type, class Allocator>
void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*right*\
Очередь, предоставляющая элементы для обмена местами, или очередь, элементы которой должны быть заменены на элементы очереди `left`.

*left*\
Объект deque, элементы которого должны быть заменены элементами deque *right*.

### <a name="example"></a>Пример

```cpp
// deque_swap.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2, c3;
   deque <int>::iterator c1_Iter;

   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 3 );
   c2.push_back( 10 );
   c2.push_back( 20 );
   c3.push_back( 100 );

   cout << "The original deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   c1.swap( c2 );

   cout << "After swapping with c2, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   swap( c1,c3 );

   cout << "After swapping with c3, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   swap<>(c1, c2);
   cout << "After swapping with c2, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;
}
```

```Output
The original deque c1 is: 1 2 3
After swapping with c2, deque c1 is: 10 20
After swapping with c3, deque c1 is: 100
After swapping with c2, deque c1 is: 1 2 3
```

## <a name="value_type"></a><a name="value_type"></a> value_type

Тип, представляющий тип данных, хранящихся в очереди.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Примечания

`value_type` является синонимом для параметра-шаблона `Type`.

### <a name="example"></a>Пример

```cpp
// deque_value_type.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
int main( )
{
   using namespace std;
   deque<int>::value_type AnInt;
   AnInt = 44;
   cout << AnInt << endl;
}
```

```Output
44
```

## <a name="see-also"></a>См. также раздел

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
