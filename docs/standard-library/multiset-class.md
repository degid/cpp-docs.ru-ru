---
title: Класс multiset
description: Справочник по API для класса библиотеки стандартных шаблонов C++ (STL) `multiset` , который используется для хранения и извлечения данных из коллекции, в которой значения содержащихся в них элементов не должны быть уникальными и в которых они используются в качестве ключевых значений, в соответствии с которыми данные автоматически упорядочиваются.
ms.date: 9/9/2020
f1_keywords:
- set/std::multiset
- set/std::multiset::allocator_type
- set/std::multiset::const_iterator
- set/std::multiset::const_pointer
- set/std::multiset::const_reference
- set/std::multiset::const_reverse_iterator
- set/std::multiset::difference_type
- set/std::multiset::iterator
- set/std::multiset::key_compare
- set/std::multiset::key_type
- set/std::multiset::pointer
- set/std::multiset::reference
- set/std::multiset::reverse_iterator
- set/std::multiset::size_type
- set/std::multiset::value_compare
- set/std::multiset::value_type
- set/std::multiset::begin
- set/std::multiset::cbegin
- set/std::multiset::cend
- set/std::multiset::clear
- set/std::multiset::contains
- set/std::multiset::count
- set/std::multiset::crbegin
- set/std::multiset::crend
- set/std::multiset::emplace
- set/std::multiset::emplace_hint
- set/std::multiset::empty
- set/std::multiset::end
- set/std::multiset::equal_range
- set/std::multiset::erase
- set/std::multiset::find
- set/std::multiset::get_allocator
- set/std::multiset::insert
- set/std::multiset::key_comp
- set/std::multiset::lower_bound
- set/std::multiset::max_size
- set/std::multiset::rbegin
- set/std::multiset::rend
- set/std::multiset::size
- set/std::multiset::swap
- set/std::multiset::upper_bound
- set/std::multiset::value_comp
helpviewer_keywords:
- std::multiset [C++]
- std::multiset [C++], allocator_type
- std::multiset [C++], const_iterator
- std::multiset [C++], const_pointer
- std::multiset [C++], const_reference
- std::multiset [C++], const_reverse_iterator
- std::multiset [C++], difference_type
- std::multiset [C++], iterator
- std::multiset [C++], key_compare
- std::multiset [C++], key_type
- std::multiset [C++], pointer
- std::multiset [C++], reference
- std::multiset [C++], reverse_iterator
- std::multiset [C++], size_type
- std::multiset [C++], value_compare
- std::multiset [C++], value_type
- std::multiset [C++], begin
- std::multiset [C++], cbegin
- std::multiset [C++], cend
- std::multiset [C++], clear
- std::multiset [C++], contains
- std::multiset [C++], count
- std::multiset [C++], crbegin
- std::multiset [C++], crend
- std::multiset [C++], emplace
- std::multiset [C++], emplace_hint
- std::multiset [C++], empty
- std::multiset [C++], end
- std::multiset [C++], equal_range
- std::multiset [C++], erase
- std::multiset [C++], find
- std::multiset [C++], get_allocator
- std::multiset [C++], insert
- std::multiset [C++], key_comp
- std::multiset [C++], lower_bound
- std::multiset [C++], max_size
- std::multiset [C++], rbegin
- std::multiset [C++], rend
- std::multiset [C++], size
- std::multiset [C++], swap
- std::multiset [C++], upper_bound
- std::multiset [C++], value_comp
ms.assetid: 630e8c10-0ce9-4ad9-8d79-9e91a600713f
ms.openlocfilehash: e857a4f6369b9aa939b5dcba17e02efaf81600b0
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040955"
---
# <a name="multiset-class"></a>Класс multiset

Класс multiset в стандартной библиотеке C++ используется для хранения и извлечения данных из коллекции, в которой значения содержащихся элементов не обязательно должны быть уникальными и в котором они выступают в качестве ключевых значений, в соответствии с которыми данные автоматически упорядочиваются. Значение ключа элемента в `multiset` не может быть изменено напрямую. Вместо этого старые значения необходимо удалить и вставить элементы с новыми значениями.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Key, class Compare =less <Key>, class Allocator =allocator <Key>>
class multiset
```

### <a name="parameters"></a>Параметры

*Раздел*\
Тип данных элемента для сохранения в `multiset`.

*Равенств*\
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в `multiset` . Бинарный предикат **less** \<Key> является значением по умолчанию.

В C++ 14 можно включить разнородный Уточняющий запрос, указав `std::less<>` предикат или `std::greater<>` , не имеющий параметров типа. Дополнительные сведения см. [в разделе разнородный Уточняющий запрос в ассоциативных контейнерах](../standard-library/stl-containers.md#sequence_containers) .

*Allocator*\
Тип, представляющий сохраненный объект распределителя, который инкапсулирует сведения о `multiset` выделении и освобождении памяти. Значение по умолчанию — `allocator<Key>`.

## <a name="remarks"></a>Примечания

Класс стандартной библиотеки C++ `multiset` :

- Ассоциативный контейнер, который является контейнером переменного размера, поддерживающим эффективное получение значений элементов на основе значения соответствующего ключа.

- Реверсивный, поскольку он предоставляет двунаправленные итераторы для получения доступа к его элементам.

- Сортированный, поскольку его элементы упорядочены по значениям ключей в контейнере в соответствии с заданной функцией сравнения.

- Несколько в том смысле, что его элементы не обязательно должны иметь уникальные ключи, чтобы одно ключевое значение имело множество связанных с ним значений элементов.

- Простой ассоциативный контейнер, поскольку его значения элементов являются значениями его ключей.

- Шаблон класса, поскольку предоставляемая им функциональность является универсальной и поэтому не зависит от конкретного типа данных, содержащихся в качестве элементов. Тип данных, подлежащий использованию, вместо этого определяется как параметры в шаблоне класса вместе с функцией и распределителем сравнения.

Итератор, предоставляемый `multiset` классом, является двунаправленным итератором, но функции-члены класса [INSERT](#insert) и [мультинабор](#multiset) имеют версии, которые принимают в качестве параметров шаблона более слабый итератор ввода, чьи функциональные требования более минимальны, чем гарантированные классом двунаправленных итераторов. Различные концепции итераторов образуют семейство, связанное уточнениями функциональности. Каждая концепция итератора имеет собственный набор требований, а алгоритмы, работающие с ними, должны ограничивать свои предположения согласно требованиям, предоставляемым этим типом итератора. Можно предположить, что итератор ввода может быть разыменован для обращения к определенному объекту и инкрементирован до следующего итератора в последовательности. Это минимальный набор функций, но его достаточно, чтобы осмысленного говорить о диапазоне итераторов [ `First`, `Last`) в контексте функций-членов класса.

Выбор типа контейнера должен в общем случае производиться на основе типа поиска и вставки, который требуется приложению. Ассоциативные контейнеры оптимизированы для операций поиска, вставки и удаления. Функции-члены, которые явно поддерживают эти операции, являются эффективными, и их выполнение выполняется в среднем пропорционально логарифму числа элементов в контейнере. Вставка элементов сделает недействительными итераторы, а удаление элементов сделает недействительными только те итераторы, которые указывали на удаленные элементы.

`multiset`Должен быть ассоциативным контейнером выбора, если условия, связывающие значения с их ключами, удовлетворяются приложением. Элементы класса `multiset` могут быть кратными и служить их собственными ключами сортировки, поэтому ключи не уникальны. Модель для этого типа структуры — упорядоченный список, например, ключевых слов, в котором слова могут встречаться несколько раз. Если бы множественных вхождения слов не допускались, набор был бы соответствующей структурой контейнера. Если бы уникальные определения вносились в список уникальных ключевых слов в качестве значений, сопоставление было бы подходящей структурой для размещения этих данных. Если вместо этого определения не являются уникальными, то будет `multimap` являться контейнером выбора.

`multiset`Упорядочивает последовательность, которую он управляет, вызывая сохраненный объект функции типа *Compare*. Хранимый объект — это функция сравнения, доступ к которой можно получить вызовом функции-члена [key_comp](#key_comp). Как правило, элементы должны быть просто менее сравнимы, чтобы установить этот порядок: так что при наличии любых двух элементов можно определить, что они эквивалентны (в смысле, что ни одно из них не меньше другого) или что один меньше другого. Это приводит к упорядочению неравнозначных элементов. С более технической точки зрения, функция сравнения является бинарным предикатом, который вызывает строгого слабое упорядочение в стандартном математически смысле. Бинарный предикат *f*(*x*, *y*) — это объект функции, имеющий два объекта-аргумента *x* и *y* , а также возвращаемое значение **`true`** или **`false`** . Порядок, накладываемый на набор, является строгим слабым порядком, если бинарный предикат является нерефлексивным, антисимметричным и транзитивным и если эквивалентность является транзитивным, где два объекта x и y определяются как эквивалентные при значении *f*(*x, y*) и *f*(*y, x*). Если более строгое условие равенства между ключами заменяет условие эквивалентности, порядок становится общим (т.е. все элементы упорядочиваются относительно друг друга), и сопоставленные ключи будут неотличимы друг от друга.

В C++ 14 можно включить разнородный Уточняющий запрос, указав `std::less<>` предикат или `std::greater<>` , не имеющий параметров типа. Дополнительные сведения см. [в разделе разнородный Уточняющий запрос в ассоциативных контейнерах](../standard-library/stl-containers.md#sequence_containers) .

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[multiset](#multiset)|Создает `multiset`, который является пустым или копией части или целого заданного `multiset`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Typedef для класса `allocator` для объекта `multiset`.|
|[const_iterator](#const_iterator)|Typedef для двунаправленного итератора, который может читать **`const`** элемент в `multiset` .|
|[const_pointer](#const_pointer)|Typedef для указателя на **`const`** элемент в `multiset` .|
|[const_reference](#const_reference)|Typedef для ссылки на **`const`** элемент, хранящийся в, `multiset` для чтения и выполнения **`const`** операций.|
|[const_reverse_iterator](#const_reverse_iterator)|Typedef для двунаправленного итератора, который может читать любой **`const`** элемент в `multiset` .|
|[difference_type](#difference_type)|Целочисленный Typedef со знаком для числа элементов в `multiset` в диапазоне между элементами, на которые указывают итераторы.|
|[iterator](#iterator)|Typedef для двунаправленного итератора, который может считывать или изменять любой элемент в `multiset`.|
|[key_compare](#key_compare)|Typedef для объекта функции, который может сравнивать два ключа для определения относительного порядка двух элементов в `multiset`.|
|[key_type](#key_type)|Typedef для объекта функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в `multiset`.|
|[pointer](#pointer)|Typedef для указателя на элемент в `multiset`.|
|[reference](#reference)|Typedef для ссылки на элемент, сохраненный в `multiset`.|
|[reverse_iterator](#reverse_iterator)|Typedef для двунаправленного итератора, который может считывать или изменять элемент в обратном `multiset`.|
|[size_type](#size_type)|Целочисленный Typedef без знака, который может представлять число элементов в `multiset`.|
|[value_compare](#value_compare)|Typedef для объекта функции, который может сравнить два элемента как ключи сортировки для определения их относительного порядка в `multiset`.|
|[value_type](#value_type)|Typedef, описывающий объект, хранящийся в виде элемента, как `multiset` в смысле его возможностей, присущих значению.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[begin](#begin)|Возвращает итератор, указывающий на первый элемент в `multiset`.|
|[cbegin](#cbegin)|Возвращает итератор const, обращающийся к первому элементу в `multiset`.|
|[cend](#cend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в `multiset`.|
|[clear](#clear)|Стирает все элементы в `multiset`.|
|[содержит](#contains)<sup>c++ 20</sup>|Проверьте, существует ли элемент с указанным ключом в `multiset` .|
|[count](#count)|Возвращает число элементов в `multiset`, ключи которых соответствуют ключу, заданному в виде параметра.|
|[crbegin](#crbegin)|Возвращает итератор const, который обращается к первому элементу в обращенном контейнере `multiset`.|
|[crend](#crend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в обращенном контейнере `multiset`.|
|[emplace](#emplace)|Вставляет созданный на месте элемент в `multiset`.|
|[emplace_hint](#emplace_hint)|Вставляет созданный на месте элемент в `multiset` с подсказкой о размещении.|
|[empty](#empty)|Проверяет, пуст ли `multiset`.|
|[end](#end)|Возвращает итератор, указывающий на место после завершающего элемента в `multiset`.|
|[equal_range](#equal_range)|Возвращает пару итераторов. Первый итератор в паре указывает на первый элемент в `multiset` с ключом, который больше указанного ключа. Второй итератор в паре указывает на первый элемент в `multiset` с ключом, который больше или равен заданному ключу.|
|[erase](#erase)|Удаляет элемент или диапазон элементов в `multiset` с заданных позиций или удаляет элементы, соответствующие заданному ключу.|
|[find](#find)|Возвращает итератор, указывающий на первое расположение элемента в `multiset`, имеющего ключ, равный указанному ключу.|
|[get_allocator](#get_allocator)|Возвращает копию объекта `allocator`, который используется для создания `multiset`.|
|[insert](#insert)|Вставляет элемент или диапазон элементов в `multiset`.|
|[key_comp](#key_comp)|Предоставляет объект функции, который может сравнивать два ключа сортировки для определения относительного порядка двух элементов в `multiset`.|
|[lower_bound](#lower_bound)|Возвращает итератор, указывающий на первый элемент в `multiset` с ключом, который больше или равен указанному ключу.|
|[max_size](#max_size)|Возвращает максимальную длину `multiset`.|
|[rbegin](#rbegin)|Возвращает итератор, указывающий на первый элемент в обратном `multiset`.|
|[rend](#rend)|Возвращает итератор, указывающий на местоположение, расположенное после завершающего элемента в обратном `multiset`.|
|[size](#size)|Возвращает количество элементов в `multiset`.|
|[swap](#swap)|Выполняет обмен элементами между двумя объектами `multiset`.|
|[upper_bound](#upper_bound)|Возвращает итератор, указывающий на первый элемент в `multiset` с ключом, который больше указанного ключа.|
|[value_comp](#value_comp)|Извлекает копию объекта сравнения, который используется для упорядочивания значений элементов в `multiset`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator=](#op_eq)|Заменяет элементы `multiset` копией другого `multiset`.|

## <a name="requirements"></a>Требования

**Заголовок:**\<set>

**Пространство имен:** std

## <a name="multisetallocator_type"></a><a name="allocator_type"></a> мультинабор:: allocator_type

Тип, который представляет класс распределителя для объекта-мультинабора.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Комментарии

`allocator_type` является синонимом для параметра-шаблона `Allocator`.

Более подробную информацию по `Allocator` см. в разделе "Примечания" в документации к [классу multiset](../standard-library/multiset-class.md).

### <a name="example"></a>Пример

См. пример для [get_allocator](#get_allocator) в качестве примера использования `allocator_type`

## <a name="multisetbegin"></a><a name="begin"></a> мультинабор:: Begin

Возвращает итератор, адресующий первый элемент в мультинаборе.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор, адресующий первый элемент в мультинаборе или положение перед пустым мультинабором.

### <a name="example"></a>Пример

```cpp
// multiset_begin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::const_iterator ms1_cIter;

   ms1.insert( 1 );
   ms1.insert( 2 );
   ms1.insert( 3 );

   ms1_Iter = ms1.begin( );
   cout << "The first element of ms1 is " << *ms1_Iter << endl;

   ms1_Iter = ms1.begin( );
   ms1.erase( ms1_Iter );

   // The following 2 lines would err as the iterator is const
   // ms1_cIter = ms1.begin( );
   // ms1.erase( ms1_cIter );

   ms1_cIter = ms1.begin( );
   cout << "The first element of ms1 is now " << *ms1_cIter << endl;
}
```

```Output
The first element of ms1 is 1
The first element of ms1 is now 2
```

## <a name="multisetcbegin"></a><a name="cbegin"></a> мультинабор:: cbegin

Возвращает **`const`** итератор, который обращается к первому элементу в диапазоне.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`const`** Итератор двунаправленного доступа, указывающий на первый элемент диапазона, или расположение непосредственно за концом пустого диапазона (для пустого диапазона `cbegin() == cend()` ).

### <a name="remarks"></a>Комментарии

С возвращаемым значением `cbegin` элементы в диапазоне нельзя изменять.

Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере рекомендуется использовать `Container` изменяемый (не- **`const`** ) контейнер любого типа, который поддерживает `begin()` и `cbegin()` .

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="multisetcend"></a><a name="cend"></a> мультинабор:: cend

Возвращает **`const`** итератор, который обращается к расположению сразу за последним элементом в диапазоне.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`const`** Итератор двунаправленного доступа, указывающий на сразу за концом диапазона.

### <a name="remarks"></a>Комментарии

`cend` используется для проверки того, прошел ли итератор конец диапазона.

Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере рекомендуется использовать `Container` изменяемый (не- **`const`** ) контейнер любого типа, который поддерживает `end()` и `cend()` .

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Значение, возвращаемое, `cend` не должно быть разыменовано.

## <a name="multisetclear"></a><a name="clear"></a> мультинабор:: Clear

Удаляет все элементы мультинабора.

```cpp
void clear();
```

### <a name="example"></a>Пример

```cpp
// multiset_clear.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 1 );
   ms1.insert( 2 );

   cout << "The size of the multiset is initially "
        << ms1.size( ) << "." << endl;

   ms1.clear( );
   cout << "The size of the multiset after clearing is "
        << ms1.size( ) << "." << endl;
}
```

```Output
The size of the multiset is initially 2.
The size of the multiset after clearing is 0.
```

## <a name="multisetconst_iterator"></a><a name="const_iterator"></a> мультинабор:: const_iterator

Тип, предоставляющий двунаправленный итератор, который может читать **`const`** элемент в Мультинаборе.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Комментарии

Тип `const_iterator` нельзя использовать для изменения значения элемента.

### <a name="example"></a>Пример

См. пример для [begin](#begin) в качестве примера использования `const_iterator`.

## <a name="multisetconst_pointer"></a><a name="const_pointer"></a> мультинабор:: const_pointer

Тип, предоставляющий указатель на **`const`** элемент в Мультинаборе.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Комментарии

Тип `const_pointer` нельзя использовать для изменения значения элемента.

В большинстве случаев для доступа к элементам в объекте-мультинаборе следует использовать [iterator](#iterator).

## <a name="multisetconst_reference"></a><a name="const_reference"></a> мультинабор:: const_reference

Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в Мультинаборе для чтения и выполнения **`const`** операций.

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="example"></a>Пример

```cpp
// multiset_const_ref.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 10 );
   ms1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *ms1.begin( );

   cout << "The first element in the multiset is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference can't be used to modify the multiset
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the multiset is 10.
```

## <a name="multisetconst_reverse_iterator"></a><a name="const_reverse_iterator"></a> мультинабор:: const_reverse_iterator

Тип, предоставляющий двунаправленный итератор, который может читать любой **`const`** элемент в Мультинаборе.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Комментарии

Тип `const_reverse_iterator` не может изменять значение элемента и используется для перебора мультинабора в обратную.

### <a name="example"></a>Пример

См. пример для [rend](#rend) в качестве примера объявления и использования `const_reverse_iterator`.

## <a name="multisetcontains"></a><a name="contains"></a> мультинабор:: содержит

Проверьте, существует ли элемент с указанным ключом в `multiset` .

```cpp
bool contains(const Key& key) const;
template<class K> bool contains(const K& key) const;
```

### <a name="parameters"></a>Параметры

*Занят*\
Тип ключа.

*раздел*\
Искомое значение ключа элемента.

### <a name="return-value"></a>Возвращаемое значение

`true` значение, если элемент найден в контейнере; `false` в противном случае — значение.

### <a name="remarks"></a>Комментарии

`contains()` Новое в C++ 20. Чтобы использовать его, укажите параметр компилятора [/std: c + + Latest](../build/reference/std-specify-language-standard-version.md) .

`template<class K> bool contains(const K& key) const` принимает участие в разрешении перегрузки только в `key_compare` том случае, если является прозрачным. Дополнительные сведения см. [в разделе разнородный Уточняющий запрос в ассоциативных контейнерах](https://docs.microsoft.com/cpp/standard-library/stl-containers#heterogeneous-lookup-in-associative-containers-c14) .

### <a name="example"></a>Пример

```cpp
// Requires /std:c++latest
#include <set>
#include <iostream>

int main()
{
    std::multiset<int> theMultiSet = {1, 2};

    std::cout << std::boolalpha; // so booleans show as 'true' or 'false'
    std::cout << theMultiSet.contains(2) << '\n';
    std::cout << theMultiSet.contains(3) << '\n';
    
    return 0;
}
```

```Output
true
false
```

## <a name="multisetcount"></a><a name="count"></a> мультинабор:: count

Возвращает число элементов в объекте multiset, ключ которых совпадает с ключом, заданным параметром.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ элементов для сопоставления из multiset.

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в multiset, ключ сортировки которых совпадает с ключом параметра.

### <a name="remarks"></a>Комментарии

Функция-член возвращает количество элементов *x* в диапазоне

\[ lower_bound (*ключ*), upper_bound (*ключ*))

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена multiset::count.

```cpp
// multiset_count.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;
    multiset<int> ms1;
    multiset<int>::size_type i;

    ms1.insert(1);
    ms1.insert(1);
    ms1.insert(2);

    // Elements don't need to be unique in multiset,
    // so duplicates are allowed and counted.
    i = ms1.count(1);
    cout << "The number of elements in ms1 with a sort key of 1 is: "
         << i << "." << endl;

    i = ms1.count(2);
    cout << "The number of elements in ms1 with a sort key of 2 is: "
         << i << "." << endl;

    i = ms1.count(3);
    cout << "The number of elements in ms1 with a sort key of 3 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in ms1 with a sort key of 1 is: 2.
The number of elements in ms1 with a sort key of 2 is: 1.
The number of elements in ms1 with a sort key of 3 is: 0.
```

## <a name="multisetcrbegin"></a><a name="crbegin"></a> мультинабор:: crbegin

Возвращает константный итератор, указывающий на первый элемент в обратном мультинаборе.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, указывающий на первый элемент в обратном мультинаборе или указывающий на элемент, ранее бывший последним элементом в мультинаборе до изменения его порядка на обратный.

### <a name="remarks"></a>Комментарии

`crbegin` используется с обратным мультинабором точно так же, как begin используется с обычным мультинабором.

Если возвращено значение `crbegin` , то объект мультинабора нельзя изменить.

`crbegin` можно использовать для перебора мультинабора в обратном порядке.

### <a name="example"></a>Пример

```cpp
// multiset_crbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_crIter = ms1.crbegin( );
   cout << "The first element in the reversed multiset is "
        << *ms1_crIter << "." << endl;
}
```

```Output
The first element in the reversed multiset is 30.
```

## <a name="multisetcrend"></a><a name="crend"></a> мультинабор:: crend

Возвращает константный итератор, который адресует положение после последнего элемента в обратном мультинаборе.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, который адресует положение после последнего элемента в обратном мультинаборе (положение, которое предшествовало первому элементу мультинабора до изменения его порядка на противоположный).

### <a name="remarks"></a>Комментарии

`crend` используется с обратным мультинабором точно так же, как [end](#end) — с обычным мультинабором.

Если возвращено значение `crend` , то объект мультинабора нельзя изменить.

`crend` можно использовать для проверки, достиг ли обратный итератор конца своего мультинабора.

Значение, возвращаемое, `crend` не должно быть разыменовано.

### <a name="example"></a>Пример

```cpp
// multiset_crend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   multiset <int> ms1;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_crIter = ms1.crend( ) ;
   ms1_crIter--;
   cout << "The last element in the reversed multiset is "
        << *ms1_crIter << "." << endl;
}
```

## <a name="multisetdifference_type"></a><a name="difference_type"></a> мультинабор::difference_type

Целочисленный тип со знаком, который можно использовать для представления количества элементов в мультинаборе в диапазоне между элементами, на которые указывают итераторы.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Комментарии

`difference_type` — тип, возвращаемый при вычитании или приращении через итераторы контейнера. `difference_type` обычно используется для представления количества элементов в диапазоне [`first`, `last`) между итераторами `first` и `last`, включает элемент, на который указывает `first`, и диапазон элементов до элемента (не включая этот элемент), на который указывает `last`.

Несмотря на то, `difference_type` что доступен для всех итераторов, удовлетворяющих требованиям итератора ввода, который включает класс двунаправленных итераторов, поддерживаемых обратимыми контейнерами, такими как Set, вычитание между итераторами поддерживается только итераторами произвольного доступа, предоставляемыми контейнером произвольного доступа, например вектором.

### <a name="example"></a>Пример

```cpp
// multiset_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <set>
#include <algorithm>

int main( )
{
   using namespace std;

   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter, ms1_bIter, ms1_eIter;

   ms1.insert( 20 );
   ms1.insert( 10 );
   ms1.insert( 20 );

   ms1_bIter = ms1.begin( );
   ms1_eIter = ms1.end( );

   multiset <int>::difference_type   df_typ5, df_typ10, df_typ20;

   df_typ5 = count( ms1_bIter, ms1_eIter, 5 );
   df_typ10 = count( ms1_bIter, ms1_eIter, 10 );
   df_typ20 = count( ms1_bIter, ms1_eIter, 20 );

   // The keys, and hence the elements, of a multiset aren't unique
   cout << "The number '5' occurs " << df_typ5
        << " times in multiset ms1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in multiset ms1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in multiset ms1.\n";

   // Count the number of elements in a multiset
   multiset <int>::difference_type  df_count = 0;
   ms1_Iter = ms1.begin( );
   while ( ms1_Iter != ms1_eIter)
   {
      df_count++;
      ms1_Iter++;
   }

   cout << "The number of elements in the multiset ms1 is: "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in multiset ms1.
The number '10' occurs 1 times in multiset ms1.
The number '20' occurs 2 times in multiset ms1.
The number of elements in the multiset ms1 is: 3.
```

## <a name="multisetemplace"></a><a name="emplace"></a> мультинабор:: emplace

Вставляет созданный элемент на место (операции копирования или перемещения не выполняются) с указанием о размещении.

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Параметры

*args*\
Аргументы, которые передаются для создания элемента, который вставляется в мультинабор.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на вновь вставленный элемент.

### <a name="remarks"></a>Комментарии

Эта функция не делает недействительными никакие ссылки на элементы контейнера, но она может сделать недействительными все итераторы к контейнеру.

Во время назначения места при возникновении исключения состояние контейнера не изменяется.

### <a name="example"></a>Пример

```cpp
// multiset_emplace.cpp
// compile with: /EHsc
#include <set>
#include <string>
#include <iostream>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: ";

    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{
    multiset<string> s1;

    s1.emplace("Anna");
    s1.emplace("Bob");
    s1.emplace("Carmine");

    cout << "multiset modified, now contains ";
    print(s1);
    cout << endl;

    s1.emplace("Bob");

    cout << "multiset modified, now contains ";
    print(s1);
    cout << endl;
}
```

## <a name="multisetemplace_hint"></a><a name="emplace_hint"></a> мультинабор:: emplace_hint

Вставляет созданный элемент на место (операции копирования или перемещения не выполняются) с указанием о размещении.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Параметры

*args*\
Аргументы, которые передаются для создания элемента, который вставляется в мультинабор.

*которому*\
Место начала поиска правильной точки вставки. (Если точка непосредственно перед *точкой, то*Вставка может выполняться в периодической константе вместо логарифмического времени.)

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на вновь вставленный элемент.

### <a name="remarks"></a>Комментарии

Эта функция не делает недействительными никакие ссылки на элементы контейнера, но она может сделать недействительными все итераторы к контейнеру.

Во время назначения места при возникновении исключения состояние контейнера не изменяется.

Пример кода см. в разделе [set::emplace_hint](../standard-library/set-class.md#emplace_hint).

## <a name="multisetempty"></a><a name="empty"></a> мультинабор:: Empty

Проверяет, что мультинабор пустой.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если мультинабор пуст; **`false`** Если мультинабор не пуст.

### <a name="example"></a>Пример

```cpp
// multiset_empty.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
   using namespace std;
   multiset <int> ms1, ms2;
   ms1.insert ( 1 );

   if ( ms1.empty( ) )
      cout << "The multiset ms1 is empty." << endl;
   else
      cout << "The multiset ms1 is not empty." << endl;

   if ( ms2.empty( ) )
      cout << "The multiset ms2 is empty." << endl;
   else
      cout << "The multiset ms2 is not empty." << endl;
}
```

```Output
The multiset ms1 is not empty.
The multiset ms2 is empty.
```

## <a name="multisetend"></a><a name="end"></a> мультинабор:: end

Возврат итератора после конца.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор после конца. Если мультинабор пуст, то `multiset::end() == multiset::begin()`.

### <a name="remarks"></a>Комментарии

**end** используется для проверки, прошел ли итератор через конец своего мультинабора.

Значение, возвращаемое функцией **End** , не должно быть разыменовано.

Пример кода см. в разделе [multiset::find](#find).

## <a name="multisetequal_range"></a><a name="equal_range"></a> мультинабор:: equal_range

Возвращает пару итераторов, на первый элемент мультинабора с ключом, который больше указанного ключа, и на первый элемент мультинабора с ключом, который равен ключу или больше него.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ-аргумент для сравнения с ключом сортировки элемента мультинабора, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Пара итераторов, первый из которых является [lower_bound](#lower_bound) ключа, а второй — [upper_bound](#upper_bound) ключа.

Для доступа к первому итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. во- **первых**, и для разыменования итератора нижней границы используйте \* ( `pr` . **первый**). Для доступа ко второму итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **во-вторых**, а для разыменования итератора верхней границы используйте \* ( `pr` . **второй**).

### <a name="example"></a>Пример

```cpp
// multiset_equal_range.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   typedef multiset<int, less<int> > IntSet;
   IntSet ms1;
   multiset <int> :: const_iterator ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   pair <IntSet::const_iterator, IntSet::const_iterator> p1, p2;
   p1 = ms1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20 in the multiset ms1 is: "
        << *( p1.second ) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20 in the multiset ms1 is: "
        << *( p1.first ) << "." << endl;

   // Compare the upper_bound called directly
   ms1_RcIter = ms1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *ms1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = ms1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == ms1.end( ) ) && ( p2.second == ms1.end( ) ) )
      cout << "The multiset ms1 doesn't have an element "
              << "with a key less than 40." << endl;
   else
      cout << "The element of multiset ms1 with a key >= 40 is: "
                << *( p1.first ) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20 in the multiset ms1 is: 30.
The lower bound of the element with a key of 20 in the multiset ms1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The multiset ms1 doesn't have an element with a key less than 40.
```

## <a name="multiseterase"></a><a name="erase"></a> мультинабор:: Erase

Удаляет элемент или диапазон элементов в мультинаборе с указанных позиций или удаляет элементы, которые соответствуют указанному ключу.

```cpp
iterator erase(
    const_iterator Where);

iterator erase(
    const_iterator First,
    const_iterator Last);

size_type erase(
    const key_type& Key);
```

### <a name="parameters"></a>Параметры

*Where*\
Положение удаляемого элемента.

*First*\
Положение первого удаляемого элемента.

*last*\
Позиция после последнего элемента для удаления.

*Раздел*\
Значение ключа удаляемых элементов.

### <a name="return-value"></a>Возвращаемое значение

Для первых двух функций-членов это двунаправленный итератор, который обозначает первый элемент, остающийся после любых удаляемых элементов, или элемент, который находится в конце мультинабора, если таких элементов нет.

Третья функция-член возвращает количество элементов, удаленных из мультинабора.

### <a name="remarks"></a>Комментарии

Пример кода см. в разделе [set::erase](../standard-library/set-class.md#erase).

## <a name="multisetfind"></a><a name="find"></a> мультинабор:: Find

Возвращает итератор, ссылающийся на элемент в мультинаборе, ключ которого эквивалентен заданному ключу.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Значение ключа, с которым сравнивается ключ сортировки элемента из мультинабора, по которому выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Итератор, который ссылается на положение элемента с указанным ключом, или на положение после последнего элемента в мультинаборе ( `multiset::end()`), если соответствие для ключа не найдено.

### <a name="remarks"></a>Комментарии

Функция-член возвращает итератор, который ссылается на элемент в Мультинаборе, ключ которого эквивалентен *ключу* аргумента в бинарном предикате, который вызывает упорядочивание на основе отношения сравнения "меньше".

Если возвращаемое значение `find` назначается `const_iterator` , то объект мультинабора нельзя изменить. Если возвращаемое значение `find` назначается `iterator` , то объект мультинабора можно изменить

### <a name="example"></a>Пример

```cpp
// compile with: /EHsc /W4 /MTd
#include <set>
#include <iostream>
#include <vector>
#include <string>

using namespace std;

template <typename T> void print_elem(const T& t) {
    cout << "(" << t << ") ";
}

template <typename T> void print_collection(const T& t) {
    cout << t.size() << " elements: ";

    for (const auto& p : t) {
        print_elem(p);
    }
    cout << endl;
}

template <typename C, class T> void findit(const C& c, T val) {
    cout << "Trying find() on value " << val << endl;
    auto result = c.find(val);
    if (result != c.end()) {
        cout << "Element found: "; print_elem(*result); cout << endl;
    } else {
        cout << "Element not found." << endl;
    }
}

int main()
{
    multiset<int> s1({ 40, 45 });
    cout << "The starting multiset s1 is: " << endl;
    print_collection(s1);

    vector<int> v;
    v.push_back(43);
    v.push_back(41);
    v.push_back(46);
    v.push_back(42);
    v.push_back(44);
    v.push_back(44); // attempt a duplicate

    cout << "Inserting the following vector data into s1: " << endl;
    print_collection(v);

    s1.insert(v.begin(), v.end());

    cout << "The modified multiset s1 is: " << endl;
    print_collection(s1);
    cout << endl;
    findit(s1, 45);
    findit(s1, 6);
}
```

## <a name="multisetget_allocator"></a><a name="get_allocator"></a> мультинабор:: get_allocator

Возвращает копию распределителя, который использовался для создания мультинабора.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Распределитель, использованный мультинабором.

### <a name="remarks"></a>Комментарии

Распределители для класса multiset определяют, как класс управляет памятью. Распределителей по умолчанию в классах контейнеров стандартной библиотеки C++ достаточно для большинства задач программирования. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.

### <a name="example"></a>Пример

```cpp
// multiset_get_allocator.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int>::allocator_type ms1_Alloc;
   multiset <int>::allocator_type ms2_Alloc;
   multiset <double>::allocator_type ms3_Alloc;
   multiset <int>::allocator_type ms4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   multiset <int> ms1;
   multiset <int, allocator<int> > ms2;
   multiset <double, allocator<double> > ms3;

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << ms2.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << ms3.max_size( ) <<  "." << endl;

   // The following lines create a multiset ms4
   // with the allocator of multiset ms1
   ms1_Alloc = ms1.get_allocator( );
   multiset <int> ms4( less<int>( ), ms1_Alloc );
   ms4_Alloc = ms4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated with the other
   if( ms1_Alloc == ms4_Alloc )
   {
      cout << "Allocators are interchangeable."
           << endl;
   }
   else
   {
      cout << "Allocators are not interchangeable."
           << endl;
   }
}
```

## <a name="multisetinsert"></a><a name="insert"></a> мультинабор:: INSERT

Вставляет элемент или диапазон элементов в мультинабор.

```cpp
// (1) single element
pair<iterator, bool> insert(
    const value_type& Val);

// (2) single element, perfect forwarded
template <class ValTy>
pair<iterator, bool>
insert(
    ValTy&& Val);

// (3) single element with hint
iterator insert(
    const_iterator Where,
    const value_type& Val);

// (4) single element, perfect forwarded, with hint
template <class ValTy>
iterator insert(
    const_iterator Where,
    ValTy&& Val);

// (5) range
template <class InputIterator>
void insert(
    InputIterator First,
    InputIterator Last);

// (6) initializer list
void insert(
    initializer_list<value_type>
IList);
```

### <a name="parameters"></a>Параметры

*val*\
Значение элемента, вставляемого в мультинабор.

*Where*\
Место начала поиска правильной точки вставки. (Если точка непосредственно перед *точкой, то*Вставка может выполняться в периодической константе вместо логарифмического времени.)

*валти*\
Параметр шаблона, указывающий тип аргумента, который мультинабор может использовать для создания элемента [value_type](../standard-library/map-class.md#value_type)и идеального перенаправления *Val* в качестве аргумента.

*First*\
Позиция первого элемента, который следует скопировать.

*last*\
Позиция непосредственно перед последним элементом, который следует скопировать.

*InputIterator*\
Аргумент функции-шаблона, который соответствует требованиям [итератора ввода](../standard-library/input-iterator-tag-struct.md), указывающего на элементы типа, которые можно использовать для создания объектов [value_type](../standard-library/map-class.md#value_type).

*Интерфейс*\
[Initializer_list](../standard-library/initializer-list.md) , из которого копируются элементы.

### <a name="return-value"></a>Возвращаемое значение

Одноэлементные функции-члены (1) и (2) возвращают итератор в позиции, где был вставлен новый элемент.

Одноэлементные функции-члены с подсказкой (3) и (4) возвращают итератор, указывающий на позицию, где был вставлен новый элемент.

### <a name="remarks"></a>Комментарии

Эта функция не делает никакие указатели или ссылки недействительными, но она может сделать недействительными все итераторы контейнера.

При вставке всего одного элемента при возникновении исключения состояние контейнера не изменяется. Если во время вставки нескольких элементов вызывается исключение, контейнер остается в неопределенном, но допустимом состоянии.

[value_type](../standard-library/map-class.md#value_type) контейнера — это определение типа, принадлежащее контейнеру и, для набора, `multiset<V>::value_type` имеет тип `const V`.

Функция-член с диапазоном (5) вставляет последовательность значений элементов в мультинабор, соответствующий каждому элементу, адресованному итератором в диапазоне `[First, Last)`. Следовательно, `Last` не вставляется. Контейнер функции-члена `end()` ссылается на позицию сразу после последнего элемента в контейнере. Например, оператор `s.insert(v.begin(), v.end());` пытается вставить все элементы `v` в `s`.

Функция-член списка инициализатора (6) использует [initializer_list](../standard-library/initializer-list.md) для копирования элементов в мультинабор.

Для вставки элемента, созданного на месте (то есть без выполнения операций копирования или перемещения) см. разделы [multiset::emplace](#emplace) и [multiset::emplace_hint](#emplace_hint).

### <a name="example"></a>Пример

```cpp
// multiset_insert.cpp
// compile with: /EHsc
#include <set>
#include <iostream>
#include <string>
#include <vector>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: ";

    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{

    // insert single values
    multiset<int> s1;
    // call insert(const value_type&) version
    s1.insert({ 1, 10 });
    // call insert(ValTy&&) version
    s1.insert(20);

    cout << "The original multiset values of s1 are:" << endl;
    print(s1);

    // intentionally attempt a duplicate, single element
    s1.insert(1);
    cout << "The modified multiset values of s1 are:" << endl;
    print(s1);
    cout << endl;

    // single element, with hint
    s1.insert(s1.end(), 30);
    cout << "The modified multiset values of s1 are:" << endl;
    print(s1);
    cout << endl;

    // The templatized version inserting a jumbled range
    multiset<int> s2;
    vector<int> v;
    v.push_back(43);
    v.push_back(294);
    v.push_back(41);
    v.push_back(330);
    v.push_back(42);
    v.push_back(45);

    cout << "Inserting the following vector data into s2:" << endl;
    print(v);

    s2.insert(v.begin(), v.end());

    cout << "The modified multiset values of s2 are:" << endl;
    print(s2);
    cout << endl;

    // The templatized versions move-constructing elements
    multiset<string>  s3;
    string str1("blue"), str2("green");

    // single element
    s3.insert(move(str1));
    cout << "After the first move insertion, s3 contains:" << endl;
    print(s3);

    // single element with hint
    s3.insert(s3.end(), move(str2));
    cout << "After the second move insertion, s3 contains:" << endl;
    print(s3);
    cout << endl;

    multiset<int> s4;
    // Insert the elements from an initializer_list
    s4.insert({ 4, 44, 2, 22, 3, 33, 1, 11, 5, 55 });
    cout << "After initializer_list insertion, s4 contains:" << endl;
    print(s4);
    cout << endl;
}
```

## <a name="multisetiterator"></a><a name="iterator"></a> мультинабор:: итератор

Тип, предоставляющий константный [двунаправленный итератор](../standard-library/bidirectional-iterator-tag-struct.md), который может читать любой элемент в мультинаборе.

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Пример

См. пример для [Begin](#begin) в качестве примера объявления и использования `iterator` .

## <a name="multisetkey_comp"></a><a name="key_comp"></a> мультинабор:: key_comp

Извлекает копию объекта сравнения, использованного для упорядочивания ключей в мультинаборе.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект-функцию, которую мультинабор использует для упорядочивания своих элементов, который является параметром-шаблоном `Compare`.

Более подробную информацию по `Compare` см. в разделе "Примечания" в документации к [классу multiset](../standard-library/multiset-class.md).

### <a name="remarks"></a>Комментарии

Сохраненный объект определяет функцию-член:

**bool operator**( **const Key&** *x*, **const Key&** *y*);

которая возвращает true если *x* строго предшествует *y* в порядке сортировки.

И [key_compare](#key_compare) , и [value_compare](#value_compare) являются синонимами для параметра шаблона `Compare` . Оба типа предоставляются для классов Set и мультинаборов, где они идентичны, для совместимости с классами Map и multimap, где они отличаются.

### <a name="example"></a>Пример

```cpp
// multiset_key_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   multiset <int, less<int> > ms1;
   multiset <int, less<int> >::key_compare kc1 = ms1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of s1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of ms1."
           << endl;
   }

   multiset <int, greater<int> > ms2;
   multiset <int, greater<int> >::key_compare kc2 = ms2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of ms2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of ms2."
           << endl;
   }
}
```

```Output
kc1( 2,3 ) returns value of true, where kc1 is the function object of s1.
kc2( 2,3 ) returns value of false, where kc2 is the function object of ms2.
```

## <a name="multisetkey_compare"></a><a name="key_compare"></a> мультинабор:: key_compare

Тип, который предоставляет объект-функцию, которая может сравнить два ключа сортировки для определения относительного порядка двух элементов в мультинаборе.

```cpp
typedef Compare key_compare;
```

### <a name="remarks"></a>Комментарии

`key_compare` является синонимом для параметра-шаблона `Compare`.

Более подробную информацию по `Compare` см. в разделе "Примечания" в документации к [классу multiset](../standard-library/multiset-class.md).

### <a name="example"></a>Пример

См. пример для [key_comp](#key_comp) в качестве примера объявления и использования `key_compare`.

## <a name="multisetkey_type"></a><a name="key_type"></a> мультинабор:: key_type

Тип, который предоставляет объект-функцию, которая может сравнивать ключи сортировки для определения относительного порядка двух элементов в мультинаборе.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Комментарии

`key_type` является синонимом для параметра-шаблона `Key`.

Более подробную информацию по `Key` см. в разделе "Примечания" в документации к [классу multiset](../standard-library/multiset-class.md).

### <a name="example"></a>Пример

См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_type`.

## <a name="multisetlower_bound"></a><a name="lower_bound"></a> мультинабор:: lower_bound

Возвращает итератор, указывающий на первый элемент в мультинаборе с ключом, который равен указанному ключу или больше него.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ-аргумент для сравнения с ключом сортировки элемента мультинабора, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Объект `iterator` или `const_iterator` , который обращается к расположению элемента в Мультинаборе с ключом, который равен ключу аргумента или больше него, либо обращается к расположению, следующему за последним элементом в Мультинаборе, если совпадение для ключа не найдено.

### <a name="example"></a>Пример

```cpp
// multiset_lower_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: const_iterator ms1_AcIter, ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_RcIter = ms1.lower_bound( 20 );
   cout << "The element of multiset ms1 with a key of 20 is: "
        << *ms1_RcIter << "." << endl;

   ms1_RcIter = ms1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( ms1_RcIter == ms1.end( ) )
      cout << "The multiset ms1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of multiset ms1 with a key of 40 is: "
           << *ms1_RcIter << "." << endl;

   // The element at a specific location in the multiset can be
   // found using a dereferenced iterator addressing the location
   ms1_AcIter = ms1.end( );
   ms1_AcIter--;
   ms1_RcIter = ms1.lower_bound( *ms1_AcIter );
   cout << "The element of ms1 with a key matching "
        << "that of the last element is: "
        << *ms1_RcIter << "." << endl;
}
```

```Output
The element of multiset ms1 with a key of 20 is: 20.
The multiset ms1 doesn't have an element with a key of 40.
The element of ms1 with a key matching that of the last element is: 30.
```

## <a name="multisetmax_size"></a><a name="max_size"></a> мультинабор:: max_size

Возвращает максимальную длину мультинабора.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальная возможная длина мультинабора.

### <a name="example"></a>Пример

```cpp
// multiset_max_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::size_type i;

   i = ms1.max_size( );
   cout << "The maximum possible length "
        << "of the multiset is " << i << "." << endl;
}
```

## <a name="multisetmultiset"></a><a name="multiset"></a> мультинабор:: мультинабор

Создает мультинабор, который пуст или является копией всего или части другого мультинабора.

```cpp
multiset();

explicit multiset (
    const Compare& Comp);

multiset (
    const Compare& Comp,
    const Allocator& Al);

multiset(
    const multiset& Right);

multiset(
    multiset&& Right);

multiset(
    initializer_list<Type> IList);

multiset(
    initializer_list<Type> IList,
    const Compare& Comp);

multiset(
    initializer_list<Type> IList,
    const Compare& Comp,
    const Allocator& Al);

template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last,
    const Compare& Comp);

template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last,
    const Compare& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Параметры

*Al*\
Класс распределителя памяти, который будет использоваться для этого объекта-мультинабора. Значение по умолчанию — `Allocator`.

*Соответствовал*\
Функция сравнения типа `const Compare`, которая используется для упорядочивания элементов в мультинаборе. Значение по умолчанию — `Compare`.

*right*\
Мультинабор, копией которого будет создаваемый мультинабор.

*First*\
Положение первого элемента в диапазоне копируемых элементов.

*last*\
Положение первого элемента после диапазона копируемых элементов.

*Интерфейс*\
Объект initializer_list, из которого копируются элементы.

### <a name="remarks"></a>Комментарии

Все конструкторы сохраняют тип объекта-распределителя, который управляет памятью для мультинабора и который позже можно получить с помощью вызова [get_allocator](#get_allocator). Параметр-распределитель часто не указывается в объявлениях класса и в макросах предварительной обработки, используемых для замены альтернативных распределителей.

Все конструкторы инициализируют свои мультинаборы.

Все конструкторы сохраняют объект-функцию типа Compare, которая используется для определения порядка ключей в мультинаборе и которую позже можно получить с помощью вызова [key_comp](#key_comp).

Первые три конструктора указывают пустой начальный Мультинабор, второй задает тип функции сравнения (*comp*), которая будет использоваться при установлении порядка элементов, а третий явно указывает тип распределителя (*Al*) для использования. Ключевое слово **`explicit`** подавляет определенные виды автоматического преобразования типов.

Четвертый конструктор указывает копию *правого*мультинабора.

Пятый конструктор задает копию мультинабора, перемещая ее *вправо*.

В шестом, седьмом и восьмом конструкторах указывается initializer_list, из которого копируются элементы.

Следующий три конструктора копируют диапазон `[First, Last)` мультинабора с повышением точности при указании типа функции сравнения и распределителя.

### <a name="example"></a>Пример

```cpp
// multiset_ctor.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;
    //multiset <int>::iterator ms1_Iter, ms2_Iter, ms3_Iter;
    multiset <int>::iterator ms4_Iter, ms5_Iter, ms6_Iter, ms7_Iter;

    // Create an empty multiset ms0 of key type integer
    multiset <int> ms0;

    // Create an empty multiset ms1 with the key comparison
    // function of less than, then insert 4 elements
    multiset <int, less<int> > ms1;
    ms1.insert(10);
    ms1.insert(20);
    ms1.insert(20);
    ms1.insert(40);

    // Create an empty multiset ms2 with the key comparison
    // function of greater than, then insert 2 elements
    multiset <int, less<int> > ms2;
    ms2.insert(10);
    ms2.insert(20);

    // Create a multiset ms3 with the
    // allocator of multiset ms1
    multiset <int>::allocator_type ms1_Alloc;
    ms1_Alloc = ms1.get_allocator();
    multiset <int> ms3(less<int>(), ms1_Alloc);
    ms3.insert(30);

    // Create a copy, multiset ms4, of multiset ms1
    multiset <int> ms4(ms1);

    // Create a multiset ms5 by copying the range ms1[ first,  last)
    multiset <int>::const_iterator ms1_bcIter, ms1_ecIter;
    ms1_bcIter = ms1.begin();
    ms1_ecIter = ms1.begin();
    ms1_ecIter++;
    ms1_ecIter++;
    multiset <int> ms5(ms1_bcIter, ms1_ecIter);

    // Create a multiset ms6 by copying the range ms4[ first,  last)
    // and with the allocator of multiset ms2
    multiset <int>::allocator_type ms2_Alloc;
    ms2_Alloc = ms2.get_allocator();
    multiset <int> ms6(ms4.begin(), ++ms4.begin(), less<int>(), ms2_Alloc);

    cout << "ms1 =";
    for (auto i : ms1)
        cout << " " << i;
    cout << endl;

    cout << "ms2 =";
    for (auto i : ms2)
        cout << " " << i;
   cout << endl;

   cout << "ms3 =";
   for (auto i : ms3)
       cout << " " << i;
    cout << endl;

    cout << "ms4 =";
    for (auto i : ms4)
        cout << " " << i;
    cout << endl;

    cout << "ms5 =";
    for (auto i : ms5)
        cout << " " << i;
    cout << endl;

    cout << "ms6 =";
    for (auto i : ms6)
        cout << " " << i;
    cout << endl;

    // Create a multiset by moving ms5
    multiset<int> ms7(move(ms5));
    cout << "ms7 =";
    for (auto i : ms7)
        cout << " " << i;
    cout << endl;

    // Create a multiset with an initializer_list
    multiset<int> ms8({1, 2, 3, 4});
    cout << "ms8=";
    for (auto i : ms8)
        cout << " " << i;
    cout << endl;
}
```

## <a name="multisetoperator"></a><a name="op_eq"></a> мультинабор::operator=

Заменяет элементы этого `multiset` элементами из другого `multiset`.

```cpp
multiset& operator=(const multiset& right);

multiset& operator=(multiset&& right);
```

### <a name="parameters"></a>Параметры

*right*\
`multiset`, из которого копируются или перемещаются элементы.

### <a name="remarks"></a>Комментарии

`operator=` копирует или перемещает элементы *непосредственно* в это `multiset` , в зависимости от используемого ссылочного типа (lvalue или rvalue). Элементы, которые находились в этом `multiset` перед выполнением `operator=`, игнорируются.

### <a name="example"></a>Пример

```cpp
// multiset_operator_as.cpp
// compile with: /EHsc
#include <multiset>
#include <iostream>

int main( )
   {
   using namespace std;
   multiset<int> v1, v2, v3;
   multiset<int>::iterator iter;

   v1.insert(10);

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << *iter << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << *iter << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << *iter << " ";
   cout << endl;
   }
```

## <a name="multisetpointer"></a><a name="pointer"></a> мультинабор::p оинтер

Тип, который предоставляет указатель на элемент в мультинаборе.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Комментарии

Тип **pointer** можно использовать для изменения значения элемента.

В большинстве случаев для доступа к элементам в объекте-мультинаборе следует использовать [iterator](#iterator).

## <a name="multisetrbegin"></a><a name="rbegin"></a> мультинабор:: rbegin

Возвращает итератор, который указывает на первый элемент в обратном мультинаборе.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, указывающий на первый элемент в обратном мультинаборе или указывающий на элемент, ранее бывший последним элементом в мультинаборе до изменения его порядка на обратный.

### <a name="remarks"></a>Комментарии

`rbegin` используется с обратным мультинабором точно так же, как rbegin используется с обычным мультинабором.

Если возвращаемое значение `rbegin` присваивается `const_reverse_iterator` , то объект мультинабора нельзя изменить. Если возвращаемое значение `rbegin` присваивается `reverse_iterator`, то объект мультинабора можно изменить.

`rbegin` можно использовать для перебора мультинабора в обратном порядке.

### <a name="example"></a>Пример

```cpp
// multiset_rbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::reverse_iterator ms1_rIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_rIter = ms1.rbegin( );
   cout << "The first element in the reversed multiset is "
        << *ms1_rIter << "." << endl;

   // begin can be used to start an iteration
   // through a multiset in a forward order
   cout << "The multiset is:";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << endl;

   // rbegin can be used to start an iteration
   // through a multiset in a reverse order
   cout << "The reversed multiset is:";
   for ( ms1_rIter = ms1.rbegin( ) ; ms1_rIter != ms1.rend( ); ms1_rIter++ )
      cout << " " << *ms1_rIter;
   cout << endl;

   // A multiset element can be erased by dereferencing to its key
   ms1_rIter = ms1.rbegin( );
   ms1.erase ( *ms1_rIter );

   ms1_rIter = ms1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed multiset is "<< *ms1_rIter << "."
        << endl;
}
```

```Output
The first element in the reversed multiset is 30.
The multiset is: 10 20 30
The reversed multiset is: 30 20 10
After the erasure, the first element in the reversed multiset is 20.
```

## <a name="multisetreference"></a><a name="reference"></a> мультинабор:: Reference

Тип, который предоставляет ссылку на элемент, хранящийся в мультинаборе.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="example"></a>Пример

```cpp
// multiset_ref.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 10 );
   ms1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   const int &Ref1 = *ms1.begin( );

   cout << "The first element in the multiset is "
        << Ref1 << "." << endl;
}
```

```Output
The first element in the multiset is 10.
```

## <a name="multisetrend"></a><a name="rend"></a> мультинабор:: rend

Возвращает итератор, который адресует положение после последнего элемента в обратном мультинаборе.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, который адресует положение после последнего элемента в обратном мультинаборе (положение перед первым элементом в мультинаборе до изменения его порядка на противоположный).

### <a name="remarks"></a>Комментарии

`rend` используется с обратным мультинабором точно так же, как [end](#end) — с обычным мультинабором.

Если возвращаемое значение `rend` присваивается `const_reverse_iterator` , то объект мультинабора нельзя изменить. Если возвращаемое значение `rend` присваивается `reverse_iterator`, то объект мультинабора можно изменить.

`rend` можно использовать для проверки, достиг ли обратный итератор конца своего мультинабора.

Значение, возвращаемое, `rend` не должно быть разыменовано.

### <a name="example"></a>Пример

```cpp
// multiset_rend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::reverse_iterator ms1_rIter;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_rIter = ms1.rend( ) ;
   ms1_rIter--;
   cout << "The last element in the reversed multiset is "
        << *ms1_rIter << "." << endl;

   // end can be used to terminate an iteration
   // through a multiset in a forward order
   cout << "The multiset is: ";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << *ms1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an iteration
   // through a multiset in a reverse order
   cout << "The reversed multiset is: ";
   for ( ms1_rIter = ms1.rbegin( ) ; ms1_rIter != ms1.rend( ); ms1_rIter++ )
      cout << *ms1_rIter << " ";
   cout << "." << endl;

   ms1_rIter = ms1.rend( );
   ms1_rIter--;
   ms1.erase ( *ms1_rIter );

   ms1_rIter = ms1.rend( );
   --ms1_rIter;
   cout << "After the erasure, the last element in the "
        << "reversed multiset is " << *ms1_rIter << "." << endl;
}
```

## <a name="multisetreverse_iterator"></a><a name="reverse_iterator"></a> мультинабор:: reverse_iterator

Тип, предоставляющий двунаправленный итератор, который может читать или изменять элементы в обратном мультинаборе.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Комментарии

Тип `reverse_iterator` используется для прохода по мультинабору в обратную.

### <a name="example"></a>Пример

См. пример для [rbegin](#rbegin) в качестве примера объявления и использования `reverse_iterator`.

## <a name="multisetsize"></a><a name="size"></a> мультинабор:: размер

Возвращает количество элементов в мультинаборе.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая длина мультинабора.

### <a name="example"></a>Пример

```cpp
// multiset_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: size_type i;

   ms1.insert( 1 );
   i = ms1.size( );
   cout << "The multiset length is " << i << "." << endl;

   ms1.insert( 2 );
   i = ms1.size( );
   cout << "The multiset length is now " << i << "." << endl;
}
```

```Output
The multiset length is 1.
The multiset length is now 2.
```

## <a name="multisetsize_type"></a><a name="size_type"></a> мультинабор:: size_type

Целочисленный беззнаковый тип, который может представлять количество элементов в мультинаборе.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>Пример

См. пример для [size](#size) в качестве примера объявления и использования `size_type`

## <a name="multisetswap"></a><a name="swap"></a> мультинабор:: swap

Меняет местами элементы двух мультинаборов.

```cpp
void swap(
    multiset<Key, Compare, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*right*\
Мультинабор-аргумент, который предоставляет элементы для обмена с элементами целевого мультинабора.

### <a name="remarks"></a>Комментарии

Функция-член не делает недействительными никакие ссылки, указатели или итераторы, которые обозначают элементы в двух мультинаборах, элементы которых обмениваются.

### <a name="example"></a>Пример

```cpp
// multiset_swap.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1, ms2, ms3;
   multiset <int>::iterator ms1_Iter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );
   ms2.insert( 100 );
   ms2.insert( 200 );
   ms3.insert( 300 );

   cout << "The original multiset ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;

   // This is the member function version of swap
   ms1.swap( ms2 );

   cout << "After swapping with ms2, list ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;

   // This is the specialized template version of swap
   swap( ms1, ms3 );

   cout << "After swapping with ms3, list ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout   << "." << endl;
}
```

```Output
The original multiset ms1 is: 10 20 30.
After swapping with ms2, list ms1 is: 100 200.
After swapping with ms3, list ms1 is: 300.
```

## <a name="multisetupper_bound"></a><a name="upper_bound"></a> мультинабор:: upper_bound

Возвращает итератор к первому элементу в мультинаборе, который больше, чем указанный ключ.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ-аргумент для сравнения с ключом сортировки элемента мультинабора, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

**iterator** или `const_iterator`, который адресует положение элемента в мультинаборе с ключом, который больше ключа-аргумента, или адресует положение после последнего элемента в мультинаборе, если соответствие для ключа не найдено.

### <a name="example"></a>Пример

```cpp
// multiset_upper_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: const_iterator ms1_AcIter, ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_RcIter = ms1.upper_bound( 20 );
   cout << "The first element of multiset ms1 with a key greater "
           << "than 20 is: " << *ms1_RcIter << "." << endl;

   ms1_RcIter = ms1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( ms1_RcIter == ms1.end( ) )
      cout << "The multiset ms1 doesn't have an element "
              << "with a key greater than 30." << endl;
   else
      cout << "The element of multiset ms1 with a key > 40 is: "
           << *ms1_RcIter << "." << endl;

   // The element at a specific location in the multiset can be
   // found using a dereferenced iterator addressing the location
   ms1_AcIter = ms1.begin( );
   ms1_RcIter = ms1.upper_bound( *ms1_AcIter );
   cout << "The first element of ms1 with a key greater than"
        << endl << "that of the initial element of ms1 is: "
        << *ms1_RcIter << "." << endl;
}
```

```Output
The first element of multiset ms1 with a key greater than 20 is: 30.
The multiset ms1 doesn't have an element with a key greater than 30.
The first element of ms1 with a key greater than
that of the initial element of ms1 is: 20.
```

## <a name="multisetvalue_comp"></a><a name="value_comp"></a> мультинабор:: value_comp

Получает копию объекта сравнения, используемого для упорядочивания значений элементов в мультинаборе.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект-функцию, которую мультинабор использует для упорядочивания своих элементов, который является параметром-шаблоном `Compare`.

Более подробную информацию по `Compare` см. в разделе "Примечания" в документации к [классу multiset](../standard-library/multiset-class.md).

### <a name="remarks"></a>Комментарии

Сохраненный объект определяет функцию-член:

**логический оператор**( **&константы ** `_xVal` , **ключ const&** `_yVal` );

который возвращает значение true, если `_xVal` предшествует и не равно `_yVal` в порядке сортировки.

И [key_compare](#key_compare) , и [value_compare](#value_compare) являются синонимами для параметра шаблона `Compare` . Оба типа предоставляются для классов Set и мультинаборов, где они идентичны, для совместимости с классами Map и multimap, где они отличаются.

### <a name="example"></a>Пример

```cpp
// multiset_value_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   multiset <int, less<int> > ms1;
   multiset <int, less<int> >::value_compare vc1 = ms1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of ms1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of ms1."
           << endl;
   }

   set <int, greater<int> > ms2;
   set<int, greater<int> >::value_compare vc2 = ms2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of ms2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of ms2."
           << endl;
   }
}
```

```Output
vc1( 2,3 ) returns value of true, where vc1 is the function object of ms1.
vc2( 2,3 ) returns value of false, where vc2 is the function object of ms2.
```

## <a name="multisetvalue_compare"></a><a name="value_compare"></a> мультинабор:: value_compare

Тип, предоставляющий объект-функцию, которая может сравнить два ключа сортировки для определения их относительного порядка в мультинаборе.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Комментарии

`value_compare` является синонимом для параметра-шаблона `Compare`.

Как [key_compare](#key_compare) , так и `value_compare` являются синонимами для параметра шаблона `Compare` . Оба типа предоставляются для классов Set и мультинаборов, где они идентичны, для совместимости с классами Map и multimap, где они отличаются.

Более подробную информацию по `Compare` см. в разделе "Примечания" в документации к [классу multiset](../standard-library/multiset-class.md).

### <a name="example"></a>Пример

См. пример для [value_comp](#value_comp) в качестве примера объявления и использования `value_compare`.

## <a name="multisetvalue_type"></a><a name="value_type"></a> мультинабор:: value_type

Тип, описывающий объект, который хранится как элемент в мультинаборе в смысле его возможностей, присущих значению.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Комментарии

`value_type` является синонимом для параметра-шаблона `Key`.

Как [key_type](#key_type) , так и `value_type` являются синонимами для параметра шаблона `Key` . Оба типа предоставляются для классов Set и мультинаборов, где они идентичны, для совместимости с классами Map и multimap, где они отличаются.

Более подробную информацию по `Key` см. в подразделе "Примечания" данного раздела.

### <a name="example"></a>Пример

```cpp
// multiset_value_type.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;

   multiset <int> :: value_type svt_Int;   // Declare value_type
   svt_Int = 10;             // Initialize value_type

   multiset <int> :: key_type skt_Int;   // Declare key_type
   skt_Int = 20;             // Initialize key_type

   ms1.insert( svt_Int );         // Insert value into s1
   ms1.insert( skt_Int );         // Insert key into s1

   // A multiset accepts key_types or value_types as elements
   cout << "The multiset has elements:";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;
}
```

```Output
The multiset has elements: 10 20.
```

## <a name="see-also"></a>См. также раздел

[Контейнера](../cpp/containers-modern-cpp.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
