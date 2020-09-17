---
title: Класс hash_multimap
ms.date: 10/18/2018
f1_keywords:
- hash_map/stdext::hash_multimap
- hash_map/stdext::hash_multimap::allocator_type
- hash_map/stdext::hash_multimap::const_iterator
- hash_map/stdext::hash_multimap::const_pointer
- hash_map/stdext::hash_multimap::const_reference
- hash_map/stdext::hash_multimap::const_reverse_iterator
- hash_map/stdext::hash_multimap::difference_type
- hash_map/stdext::hash_multimap::iterator
- hash_map/stdext::hash_multimap::key_compare
- hash_map/stdext::hash_multimap::key_type
- hash_map/stdext::hash_multimap::mapped_type
- hash_map/stdext::hash_multimap::pointer
- hash_map/stdext::hash_multimap::reference
- hash_map/stdext::hash_multimap::reverse_iterator
- hash_map/stdext::hash_multimap::size_type
- hash_map/stdext::hash_multimap::value_type
- hash_map/stdext::hash_multimap::begin
- hash_map/stdext::hash_multimap::cbegin
- hash_map/stdext::hash_multimap::cend
- hash_map/stdext::hash_multimap::clear
- hash_map/stdext::hash_multimap::count
- hash_map/stdext::hash_multimap::crbegin
- hash_map/stdext::hash_multimap::crend
- hash_map/stdext::hash_multimap::emplace
- hash_map/stdext::hash_multimap::emplace_hint
- hash_map/stdext::hash_multimap::empty
- hash_map/stdext::hash_multimap::end
- hash_map/stdext::hash_multimap::equal_range
- hash_map/stdext::hash_multimap::erase
- hash_map/stdext::hash_multimap::find
- hash_map/stdext::hash_multimap::get_allocator
- hash_map/stdext::hash_multimap::insert
- hash_map/stdext::hash_multimap::key_comp
- hash_map/stdext::hash_multimap::lower_bound
- hash_map/stdext::hash_multimap::max_size
- hash_map/stdext::hash_multimap::rbegin
- hash_map/stdext::hash_multimap::rend
- hash_map/stdext::hash_multimap::size
- hash_map/stdext::hash_multimap::swap
- hash_map/stdext::hash_multimap::upper_bound
- hash_map/stdext::hash_multimap::value_comp
helpviewer_keywords:
- stdext::hash_multimap
- stdext::hash_multimap::allocator_type
- stdext::hash_multimap::const_iterator
- stdext::hash_multimap::const_pointer
- stdext::hash_multimap::const_reference
- stdext::hash_multimap::const_reverse_iterator
- stdext::hash_multimap::difference_type
- stdext::hash_multimap::iterator
- stdext::hash_multimap::key_compare
- stdext::hash_multimap::key_type
- stdext::hash_multimap::mapped_type
- stdext::hash_multimap::pointer
- stdext::hash_multimap::reference
- stdext::hash_multimap::reverse_iterator
- stdext::hash_multimap::size_type
- stdext::hash_multimap::value_type
- stdext::hash_multimap::begin
- stdext::hash_multimap::cbegin
- stdext::hash_multimap::cend
- stdext::hash_multimap::clear
- stdext::hash_multimap::count
- stdext::hash_multimap::crbegin
- stdext::hash_multimap::crend
- stdext::hash_multimap::emplace
- stdext::hash_multimap::emplace_hint
- stdext::hash_multimap::empty
- stdext::hash_multimap::end
- stdext::hash_multimap::equal_range
- stdext::hash_multimap::erase
- stdext::hash_multimap::find
- stdext::hash_multimap::get_allocator
- stdext::hash_multimap::insert
- stdext::hash_multimap::key_comp
- stdext::hash_multimap::lower_bound
- stdext::hash_multimap::max_size
- stdext::hash_multimap::rbegin
- stdext::hash_multimap::rend
- stdext::hash_multimap::size
- stdext::hash_multimap::swap
- stdext::hash_multimap::upper_bound
- stdext::hash_multimap::value_comp
ms.assetid: f41a6db9-67aa-43a3-a3c5-dbfe9ec3ae7d
ms.openlocfilehash: 089204ac77403923d38f198d53b3ff711e6a4963
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560831"
---
# <a name="hash_multimap-class"></a>Класс hash_multimap

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Класс контейнеров hash_multimap является расширением стандартной библиотеки С++ и используется для хранения и быстрого получения данных из коллекции, в которой каждый элемент — это пара с необязательно уникальным значением ключа сортировки и связанным значением данных.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Key,
    class Type,
    class Traits=hash_compare <Key, less <Key>>,
    class Allocator=allocator <pair  <const Key, Type>>>
class hash_multimap
```

### <a name="parameters"></a>Параметры

*Раздел*\
Тип данных ключа, который необходимо сохранить в hash_multimap.

*Type*\
Тип данных элемента, который необходимо сохранить в hash_multimap.

*Traits*\
Тип, включающий два объекта-функции: одна из признаков *класса,* способная сравнить два значения элемента как ключи сортировки для определения их относительного порядка, и хэш-функции, которая является унарным предикатом, сопоставленным ключевым значениям элементов с целыми числами без знака типа `size_t` . Этот аргумент является необязательным, и в качестве значения по умолчанию используется `hash_compare<Key, less<Key>>`.

*Allocator*\
Тип, представляющий сохраненный объект распределителя, который инкапсулирует сведения о выделении и освобождении памяти для hash_multimap. Этот аргумент является необязательным, и в качестве значения по умолчанию используется `allocator<pair <const Key, Type>>`.

## <a name="remarks"></a>Примечания

hash_multimap:

- Ассоциативный контейнер, который является контейнером переменного размера, поддерживающим эффективное получение значений элементов на основе значения соответствующего ключа.

- Является реверсивным, поскольку предоставляет двунаправленный итератор для получения доступа к его элементам.

- Хэшируется, поскольку его элементы группируются в сегменты на основе значения хэш-функции, применяемой к значениям ключей элементов.

- Множественный, поскольку его элементы не обязательно должны иметь уникальные ключи, т. е. одному значению ключа может соответствовать много значений данных элементов, связанных с ним.

- Является контейнером ассоциативной пары, поскольку его значения элементов отличаются от его значений ключей.

- Шаблон класса, поскольку предоставляемая им функциональность является универсальной и поэтому не зависит от конкретного типа данных, содержащихся в качестве элементов или ключей. Типы данных, используемые для элементов и ключей, вместо этого определяются как параметры в шаблоне класса вместе с функцией и распределителем сравнения.

Главным преимуществом хэширования по сравнению с сортировкой является повышенная эффективность; при успешном хэшировании вставка, удаление и поиск выполняются за константный средний промежуток времени по сравнению со временем, пропорциональным логарифму числа элементов в контейнере, для методов сортировки. Напрямую можно изменить значение элемента в hash_multimap, но не связанное с ним значение ключа. Значения ключей, связанные со старыми элементами, необходимо удалить и вставить новые значения ключей, связанные с новыми элементами.

Выбор типа контейнера должен в общем случае производиться на основе типа поиска и вставки, который требуется приложению. Хэшированные ассоциативные контейнеры оптимизированы для операций поиска, вставки и удаления. Функции-члены, которые явно поддерживают эти операции, эффективны при использовании совместно с правильно разработанной хэш-функцией, в результате чего они имеют постоянное среднее время выполнения и не зависят от числа элементов в контейнере. Правильно разработанная хэш-функция обеспечивает равномерное распределение хэшированных значений и сводит к минимуму количество конфликтов, когда разные значения ключей сопоставляются с одним хэшированным значением. В худшем случае, когда применяется наиболее неоптимальная хэш-функция, количество операций пропорционально количеству элементов в последовательности (линейное время).

Класс hash_multimap рекомендуется использовать в качестве ассоциативного контейнера, если условия, ассоциирующие значения с ключами, удовлетворяются приложением. Модель для этого типа структуры — это упорядоченный список ключевых слов со связанными значениями строк, предоставляющими, например, определения, в которых слова не всегда обладают уникальными определениями. Если же ключевые слова обладают уникальными определениями и ключи уникальны, то hash_multimap будет предпочтительным контейнером. Если же сохранен только список слов, то в качестве контейнера необходимо выбрать набор hash_set. Если допускается многократное использование слов, то подходящей структурой контейнера будет hash_multiset.

Hash_multimap упорядочивает управляемую им последовательность путем вызова сохраненного объекта `Traits` хэша, относящегося к типу [value_compare](../standard-library/value-compare-class.md). Доступ к этому сохраненному объекту можно получить путем вызова функции-члена [key_comp](../standard-library/hash-map-class.md#key_comp). Такой объект функции должен вести себя так же, как объект класса [hash_compare](../standard-library/hash-compare-class.md) `<Key, less<Key>>` . В частности, для всех значений `Key` типа `Key` вызов `Traits (Key)` создает распределение значений типа `size_t`.

В целом, упорядочиваемые элементы должны лишь подлежать сравнению "меньше чем" для установления такого порядка, чтобы, имея любые два элемента, можно было определить, что они равны (ни один не меньше другого) или что один меньше другого. Это приводит к упорядочению неравнозначных элементов. С более технической точки зрения, функция сравнения является бинарным предикатом, который вызывает строгого слабое упорядочение в стандартном математически смысле. Бинарный предикат f (x, y) — это объект функции, имеющий два объекта-аргумента `x` и `y` возвращаемое значение **`true`** или **`false`** . Порядок, накладываемый на hash_multimap, является строгим слабым порядком, если бинарный предикат является нерефлексивным, симметричным и транзитивным и если эквивалентность является транзитивным, где два объекта `x` и `y` определяются как эквивалентные, если используются оба варианта: f (x, y) и f (y, x) **`false`** . Если более строгое условие равенства между ключами заменяет условие эквивалентности, порядок становится общим (т.е. все элементы упорядочиваются относительно друг друга), и сопоставленные ключи будут неотличимы друг от друга.

Фактический порядок элементов в управляемой последовательности зависит от хэш-функции, функции упорядочения и текущего размера хэш-таблицы, хранимой в объекте контейнера. Текущий размер хэш-таблицы определить нельзя, поэтому обычно невозможно предсказать порядок элементов в управляемой последовательности. Вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, которые ранее указывали конкретно на удаленные элементы.

Итератор, предоставляемый классом hash_multimap, является двусторонним итератором, но функции-члены класса [insert](#insert) и [hash_multimap](#hash_multimap) обладают версиями, принимающими в качестве параметров шаблона более слабый итератор ввода, чьи функциональные требования ниже, чем гарантированные классом двунаправленных итераторов. Различные концепции итераторов образуют семейство, связанное уточнениями функциональности. Каждая концепция итератора имеет собственный hash_multimap с требованиями, а алгоритмы, работающие с ними, должны ограничивать свои предположения согласно требованиям, предоставляемым этим типом итератора. Можно предположить, что итератор ввода может быть разыменован для обращения к определенному объекту и инкрементирован до следующего итератора в последовательности. Это минимальный набор hash_multimap функциональных возможностей, но его достаточно, чтобы иметь возможность осмысленно говорить о диапазоне итераторов `[First, Last)`, в контексте функций-членов.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[hash_multimap](#hash_multimap)|Создает список определенного размера или с элементами, обладающими указанным значением или указанным `allocator`, либо в качестве копии другого `hash_multimap`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Тип, представляющий класс `allocator` для объекта `hash_multimap`.|
|[const_iterator](#const_iterator)|Тип, предоставляющий двунаправленный итератор, который может читать **`const`** элемент в `hash_multimap` .|
|[const_pointer](#const_pointer)|Тип, предоставляющий указатель на **`const`** элемент в `hash_multimap` .|
|[const_reference](#const_reference)|Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в, `hash_multimap` для чтения и выполнения **`const`** операций.|
|[const_reverse_iterator](#const_reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может читать любой **`const`** элемент в `hash_multimap` .|
|[difference_type](#difference_type)|Тип целого числа со знаком, пригодный для представления количества элементов в контейнере `hash_multimap` в диапазоне между элементами, на которые указывают итераторы.|
|[iterator](#iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять любой элемент в `hash_multimap`.|
|[key_compare](#key_compare)|Тип, предоставляющий объект функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в контейнере `hash_multimap`.|
|[key_type](#key_type)|Тип, описывающий объект ключа сортировки, составляющий каждый элемент контейнера `hash_multimap`.|
|[mapped_type](#mapped_type)|Тип, который представляет тип данных, хранящийся в контейнере `hash_multimap`.|
|[pointer](#pointer)|Тип, предоставляющий указатель на элемент в `hash_multimap`.|
|[reference](#reference)|Тип, предоставляющий ссылку на элемент, хранящийся в контейнере `hash_multimap`.|
|[reverse_iterator](#reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять элемент в обращенном контейнере `hash_multimap`.|
|[size_type](#size_type)|Целочисленный Typedef без знака, который может представлять число элементов в `hash_multimap`.|
|[value_type](#value_type)|Тип, предоставляющий объект функции, который может сравнить два элемента в качестве ключей сортировки для определения их относительного порядка в контейнере `hash_multimap`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[begin](#begin)|Возвращает итератор, обращающийся к первый элемент в контейнере `hash_multimap`.|
|[cbegin](#cbegin)|Возвращает итератор const, обращающийся к первому элементу в `hash_multimap`.|
|[cend](#cend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в `hash_multimap`.|
|[clear](#clear)|Стирает все элементы в `hash_multimap`.|
|[count](#count)|Возвращает число элементов в контейнере `hash_multimap`, ключи которых соответствуют ключу, заданному параметром.|
|[crbegin](#crbegin)|Возвращает итератор const, который обращается к первому элементу в обращенном контейнере `hash_multimap`.|
|[crend](#crend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в обращенном контейнере `hash_multimap`.|
|[emplace](#emplace)|Вставляет созданный на месте элемент в `hash_multimap`.|
|[emplace_hint](#emplace_hint)|Вставляет созданный на месте элемент в `hash_multimap` с подсказкой о размещении.|
|[empty](#empty)|Проверяет, пуст ли `hash_multimap`.|
|[end](#end)|Возвращает итератор, который обращается к месту, следующему за последним элементом в контейнере `hash_multimap`.|
|[equal_range](#equal_range)|Возвращает итератор, который обращается к месту, следующему за последним элементом в контейнере `hash_multimap`.|
|[erase](#erase)|Удаляет элемент или диапазон элементов с указанных положений в `hash_multimap`.|
|[find](#find)|Возвращает итератор, адресующий расположение элемента в наборе `hash_multimap` с ключом, эквивалентным указанному ключу.|
|[get_allocator](#get_allocator)|Возвращает копию объекта `allocator`, который используется для создания контейнера `hash_multimap`.|
|[insert](#insert)|Вставляет элемент или диапазон элементов в `hash_multimap` в заданной позиции.|
|[key_comp](#key_comp)|Извлекает копию объекта сравнения, который используется для упорядочивания ключей в контейнере `hash_multimap`.|
|[lower_bound](#lower_bound)|Возвращает итератор, указывающий на первый элемент в `hash_multimap` со значением ключа, которое больше или равно указанному ключу.|
|[max_size](#max_size)|Возвращает максимальную длину `hash_multimap`.|
|[rbegin](#rbegin)|Возвращает итератор, который обращается к первому элементу в обращенном контейнере `hash_multimap`.|
|[rend](#rend)|Возвращает итератор, который обращается к месту, следующему за последним элементом в обращенном контейнере `hash_multimap`.|
|[size](#size)|Указывает новый размер `hash_multimap`.|
|[swap](#swap)|Выполняет обмен элементами между двумя объектами `hash_multimap`.|
|[upper_bound](#upper_bound)|Возвращает итератор, указывающий на первый элемент в `hash_multimap` со значением ключа, которое больше указанного ключа.|
|[value_comp](#value_comp)|Извлекает копию объекта сравнения, который используется для упорядочивания значений элементов в наборе `hash_multimap`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[hash_multimap::operator=](#op_eq)|Заменяет элементы `hash_multimap` копией другого `hash_multimap`.|

## <a name="requirements"></a>Требования

**Заголовок:**\<hash_map>

**Пространство имен:** stdext

## <a name="hash_multimapallocator_type"></a><a name="allocator_type"></a> hash_multimap:: allocator_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, представляющий класс распределителя для объекта hash_multimap.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="remarks"></a>Примечания

`allocator_type` является синонимом для параметра-шаблона `Allocator`.

Дополнительные сведения о `Allocator` см. в подразделе "Примечания" документации к разделу [Класс hash_multimap](../standard-library/hash-multimap-class.md).

### <a name="example"></a>Пример

См. пример использования [get_allocator](#get_allocator) в качестве примера использования `allocator_type`.

## <a name="hash_multimapbegin"></a><a name="begin"></a> hash_multimap:: Begin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает итератор, адресующий первый элемент в hash_multimap.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор, адресующий расположение первого элемента в hash_multimap или расположение после пустого hash_multimap.

### <a name="remarks"></a>Примечания

Если возвращаемое значение `begin` присваивается `const_iterator` , то элементы в объекте hash_multimap не могут быть изменены. Если возвращаемое значение `begin` присваивается `iterator` , то элементы в объекте hash_multimap могут быть изменены.

### <a name="example"></a>Пример

```cpp
// hash_multimap_begin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: iterator hm1_Iter;
   hash_multimap <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 0, 0 ) );
   hm1.insert ( Int_Pair ( 1, 1 ) );
   hm1.insert ( Int_Pair ( 2, 4 ) );

   hm1_cIter = hm1.begin ( );
   cout << "The first element of hm1 is " << hm1_cIter -> first
        << "." << endl;

   hm1_Iter = hm1.begin ( );
   hm1.erase ( hm1_Iter );

   // The following 2 lines would err because the iterator is const
   // hm1_cIter = hm1.begin ( );
   // hm1.erase ( hm1_cIter );

   hm1_cIter = hm1.begin( );
   cout << "The first element of hm1 is now " << hm1_cIter -> first
        << "." << endl;
}
```

```Output
The first element of hm1 is 0.
The first element of hm1 is now 1.
```

## <a name="hash_multimapcbegin"></a><a name="cbegin"></a> hash_multimap:: cbegin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает итератор const, адресующий первый элемент в hash_multimap.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Постоянный двунаправленный итератор, адресующий первый элемент в [hash_multimap](../standard-library/hash-multimap-class.md) или расположение после пустого `hash_multimap`.

### <a name="example"></a>Пример

```cpp
// hash_multimap_cbegin.cpp
// compile with: /EHsc
#include <hash_multimap>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 2, 4 ) );

   hm1_cIter = hm1.cbegin ( );
   cout << "The first element of hm1 is "
        << hm1_cIter -> first << "." << endl;
   }
```

```Output
The first element of hm1 is 2.
```

## <a name="hash_multimapcend"></a><a name="cend"></a> hash_multimap:: cend

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает итератор const, адресующий место, следующее за последним элементом в hash_multimap.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор const bidirectional, адресующий место, следующее за последним элементом в [hash_multimap](../standard-library/hash-multimap-class.md). Если `hash_multimap` пуст, то `hash_multimap::cend == hash_multimap::begin`.

### <a name="remarks"></a>Примечания

`cend` используется для проверки того, достиг ли итератор конца своего hash_multimap.

Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_multimap_cend.cpp
// compile with: /EHsc
#include <hash_multimap>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_cIter = hm1.cend( );
   hm1_cIter--;
   cout << "The value of last element of hm1 is "
        << hm1_cIter -> second << "." << endl;
   }
```

```Output
The value of last element of hm1 is 30.
```

## <a name="hash_multimapclear"></a><a name="clear"></a> hash_multimap:: Clear

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Стирает все элементы в объекте hash_multimap.

```cpp
void clear();
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

В следующем примере иллюстрируется использование функции-члена hash_multimap::clear.

```cpp
// hash_multimap_clear.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1;
    hash_multimap<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    hm1.insert(Int_Pair(2, 4));

    i = hm1.size();
    cout << "The size of the hash_multimap is initially "
         << i  << "." << endl;

    hm1.clear();
    i = hm1.size();
    cout << "The size of the hash_multimap after clearing is "
         << i << "." << endl;
}
```

```Output
The size of the hash_multimap is initially 2.
The size of the hash_multimap after clearing is 0.
```

## <a name="hash_multimapconst_iterator"></a><a name="const_iterator"></a> hash_multimap:: const_iterator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать **`const`** элемент в hash_multimap.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_iterator`нельзя использовать для изменения значения элемента.

Объект, `const_iterator` определенный hash_multimap, указывает на объекты [value_type](#value_type), имеющие тип `pair<const Key, Type>` . Значение ключа доступно через первый элемент пары, а значение сопоставленного элемента — через второй элемент пары.

Для разыменования объекта `const_iterator` `cIter` , указывающего на элемент в hash_multimap, используйте `->` оператор.

Чтобы получить доступ к значению ключа для элемента, используйте `cIter->first` , что эквивалентно `(*cIter).first` . Чтобы получить доступ к значению сопоставленной версии элемента, используйте `cIter->second` , что эквивалентно `(*cIter).second` .

### <a name="example"></a>Пример

См. пример для [begin](#begin) в качестве примера использования `const_iterator`.

## <a name="hash_multimapconst_pointer"></a><a name="const_pointer"></a> hash_multimap:: const_pointer

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, предоставляющий указатель на **`const`** элемент в hash_multimap.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Примечания

Тип `const_pointer`нельзя использовать для изменения значения элемента.

В большинстве случаев [итератор](#iterator) должен использоваться для доступа к элементам в объекте hash_multimap.

## <a name="hash_multimapconst_reference"></a><a name="const_reference"></a> hash_multimap:: const_reference

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в hash_multimap для чтения и выполнения **`const`** операций.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_reference const_reference;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multimap_const_ref.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap<int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( hm1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( hm1.begin( ) -> first );

   cout << "The key of first element in the hash_multimap is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( hm1.begin() -> second );

   cout << "The data value of 1st element in the hash_multimap is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the hash_multimap is 1.
The data value of 1st element in the hash_multimap is 10.
```

## <a name="hash_multimapconst_reverse_iterator"></a><a name="const_reverse_iterator"></a> hash_multimap:: const_reverse_iterator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать любой **`const`** элемент в hash_multimap.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_reverse_iterator` не может изменять значение элемента и используется для последовательного прохождения hash_multimap в обратную сторону.

Объект, `const_reverse_iterator` определенный hash_multimap, указывает на объекты [value_type](#value_type), имеющие тип `pair<const Key, Type>` , первый элемент которого является ключом к элементу, а второй элемент — сопоставленная база данных, удерживаемая элементом.

Для разыменования объекта `const_reverse_iterator` `crIter` , указывающего на элемент в hash_multimap, используйте `->` оператор.

Чтобы получить доступ к значению ключа для элемента, используйте `crIter->first` , что эквивалентно `(*crIter).first` . Чтобы получить доступ к значению сопоставленной версии элемента, используйте `crIter->second` , что эквивалентно `(*crIter).second` .

### <a name="example"></a>Пример

См. пример для [rend](#rend) в качестве примера объявления и использования `const_reverse_iterator`.

## <a name="hash_multimapcount"></a><a name="count"></a> hash_multimap:: count

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает число элементов в объекте hash_multimap, ключ которых совпадает с ключом, заданным параметром.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ для сравнения с ключами элементов объекта hash_multimap.

### <a name="return-value"></a>Возвращаемое значение

1, если объект hash_multimap содержит элемент, ключ сортировки которого совпадает с ключом параметра. 0, если объект hash_multimap не содержит но одного элемента с соответствующим ключом.

### <a name="remarks"></a>Примечания

Функция-член возвращает число элементов в диапазоне

**[lower_bound (** `key` **), upper_bound (** `key` **) )**

, имеющий *ключ*значения ключа.

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена hash_multimap::count.

```cpp
// hash_multimap_count.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1;
    hash_multimap<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    hm1.insert(Int_Pair(2, 1));
    hm1.insert(Int_Pair(1, 4));
    hm1.insert(Int_Pair(2, 1));

    // Elements do not need to have unique keys in hash_multimap,
    // so duplicates are allowed and counted
    i = hm1.count(1);
    cout << "The number of elements in hm1 with a sort key of 1 is: "
         << i << "." << endl;

    i = hm1.count(2);
    cout << "The number of elements in hm1 with a sort key of 2 is: "
         << i << "." << endl;

    i = hm1.count(3);
    cout << "The number of elements in hm1 with a sort key of 3 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in hm1 with a sort key of 1 is: 2.
The number of elements in hm1 with a sort key of 2 is: 2.
The number of elements in hm1 with a sort key of 3 is: 0.
```

## <a name="hash_multimapcrbegin"></a><a name="crbegin"></a> hash_multimap:: crbegin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает итератор const, указывающий на первый элемент в обратном hash_multimap.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий первый элемент в обратном [hash_multimap](../standard-library/hash-multimap-class.md) (или адресующий элемент, ранее бывший последним элементом в `hash_multimap` до изменения его порядка на обратный).

### <a name="remarks"></a>Примечания

`crbegin` используется с обратным hash_multimap так же, как [hash_multimap::begin](#begin) используется с `hash_multimap`.

Если возвращаемое значение `crbegin`, то объект `hash_multimap` невозможно изменить.

`crbegin` можно использовать для перебора `hash_multimap` в обратном порядке.

### <a name="example"></a>Пример

```cpp
// hash_multimap_crbegin.cpp
// compile with: /EHsc
#include <hash_multimap>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_crIter = hm1.crbegin( );
   cout << "The first element of the reversed hash_multimap hm1 is "
        << hm1_crIter -> first << "." << endl;
}
```

```Output
The first element of the reversed hash_multimap hm1 is 3.
```

## <a name="hash_multimapcrend"></a><a name="crend"></a> hash_multimap:: crend

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает итератор const, который обращается к месту, следующему за последним элементом в обращенном hash_multimap.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий место после последнего элемента в обратном [hash_multimap](../standard-library/hash-multimap-class.md) (расположение перед первым элементом в `hash_multimap` до изменения его порядка на обратный).

### <a name="remarks"></a>Примечания

`crend` используется с обратным hash_multimap так же, как [hash_multimap::end](#end) используется с hash_multimap.

Если возвращаемое значение `crend`, то объект `hash_multimap` невозможно изменить.

`crend` используется, чтобы проверить, достиг ли обратный итератор конца своего hash_multimap.

Значение, возвращаемое `crend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_multimap_crend.cpp
// compile with: /EHsc
#include <hash_multimap>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_crIter = hm1.crend( );
   hm1_crIter--;
   cout << "The last element of the reversed hash_multimap hm1 is "
        << hm1_crIter -> first << "." << endl;
}
```

```Output
The last element of the reversed hash_multimap hm1 is 3.
```

## <a name="hash_multimapdifference_type"></a><a name="difference_type"></a> hash_multimap::difference_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип целого числа со знаком, пригодный для представления количества элементов в hash_multimap в диапазоне между элементами, на которые указывают итераторы.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Примечания

`difference_type` — тип, возвращаемый при вычитании или приращении через итераторы контейнера. `difference_type` обычно используется для представления количества элементов в диапазоне *[ first,  last)* между итераторами `first` и `last`, включая элемент, на который указывает `first`, и диапазон элементов до элемента, на который указывает `last`, но не включая его.

Обратите внимание, что хотя `difference_type` доступна для всех итераторов, соответствующих требованиям для входного итератора, что включает класс двунаправленных итераторов, поддерживаемых обратными контейнерами, например наборами, вычитание между итераторами поддерживается только итераторами произвольного доступа, предоставляемыми контейнерами произвольного доступа, например векторами.

### <a name="example"></a>Пример

```cpp
// hash_multimap_difference_type.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_map>
#include <algorithm>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(2, 20));
    hm1.insert(Int_Pair(1, 10));
    hm1.insert(Int_Pair(3, 20));

    // The following will insert, because map keys
    // do not need to be unique
    hm1.insert(Int_Pair(2, 30));

    hash_multimap<int, int>::iterator hm1_Iter, hm1_bIter, hm1_eIter;
    hm1_bIter = hm1.begin();
    hm1_eIter = hm1.end();

    // Count the number of elements in a hash_multimap
    hash_multimap<int, int>::difference_type df_count = 0;
    hm1_Iter = hm1.begin();
    while (hm1_Iter != hm1_eIter)
    {
        df_count++;
        hm1_Iter++;
    }

    cout << "The number of elements in the hash_multimap hm1 is: "
         << df_count << "." << endl;

    cout << "The keys of the mapped elements are:";
    for (hm1_Iter= hm1.begin() ; hm1_Iter!= hm1.end();
        hm1_Iter++)
        cout << " " << hm1_Iter-> first;
    cout << "." << endl;

    cout << "The values of the mapped elements are:";
    for (hm1_Iter= hm1.begin() ; hm1_Iter!= hm1.end();
        hm1_Iter++)
        cout << " " << hm1_Iter-> second;
    cout << "." << endl;
}
```

```Output
The number of elements in the hash_multimap hm1 is: 4.
The keys of the mapped elements are: 1 2 2 3.
The values of the mapped elements are: 10 20 30 20.
```

## <a name="hash_multimapemplace"></a><a name="emplace"></a> hash_multimap:: emplace

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Вставляет созданный на месте элемент в hash_multimap.

```cpp
template <class ValTy>
iterator emplace(ValTy&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение, используемое для перемещения, формирует элемент для вставки в [hash_multimap](../standard-library/hash-multimap-class.md).

### <a name="return-value"></a>Возвращаемое значение

Функция-член `emplace` возвращает итератор, указывающий на позицию, где был вставлен новый элемент.

### <a name="remarks"></a>Примечания

[hash_multimap::value_type](#value_type) элемента — это пара, поэтому значением элемента будет упорядоченная пара, первый элемент которой равен значению ключа, а второй — значению данных элемента.

### <a name="example"></a>Пример

```cpp
// hash_multimap_emplace.cpp
// compile with: /EHsc
#include<hash_multimap>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, string> hm1;
    typedef pair<int, string> is1(1, "a");

    hm1.emplace(move(is1));
    cout << "After the emplace, hm1 contains:" << endl
      << " " << hm1.begin()->first
      << " => " << hm1.begin()->second
      << endl;
}
```

```Output
After the emplace insertion, hm1 contains:
1 => a
```

## <a name="hash_multimapemplace_hint"></a><a name="emplace_hint"></a> hash_multimap:: emplace_hint

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Вставляет созданный на месте элемент в hash_multimap с подсказкой о размещении.

```cpp
template <class ValTy>
iterator emplace_hint(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение, используемое для перемещения, создает элемент для вставки в [hash_multimap](../standard-library/hash-multimap-class.md), кроме случаев, когда `hash_multimap` уже содержит этот элемент (или, в более общем смысле, элемент, ключ которого эквивалентно упорядочен).

*_Where*\
Подсказка о месте начала поиска правильной точки вставки.

### <a name="return-value"></a>Возвращаемое значение

Функция-член [hash_multimap::emplace](#emplace) возвращает итератор, который указывает на позицию вставки нового элемента в `hash_multimap`.

### <a name="remarks"></a>Примечания

[hash_multimap::value_type](#value_type) элемента — это пара, поэтому значением элемента будет упорядоченная пара, первый элемент которой равен значению ключа, а второй — значению данных элемента.

Вставка может происходить в постоянном времени, а не в виде логарифмического времени, если точка вставки сразу следует за *_Where*.

### <a name="example"></a>Пример

```cpp
// hash_multimap_emplace_hint.cpp
// compile with: /EHsc
#include<hash_multimap>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, string> hm1;
    typedef pair<int, string> is1(1, "a");

    hm1.emplace(hm1.begin(), move(is1));
    cout << "After the emplace insertion, hm1 contains:" << endl
      << " " << hm1.begin()->first
      << " => " << hm1.begin()->second
      << endl;
}
```

```Output
After the emplace insertion, hm1 contains:
1 => a
```

## <a name="hash_multimapempty"></a><a name="empty"></a> hash_multimap:: Empty

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Проверяет, что hash_multimap пуст.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если hash_multimap пустой; **`false`** если hash_multimap не пуста.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multimap_empty.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1, hm2;

   typedef pair <int, int> Int_Pair;
   hm1.insert ( Int_Pair ( 1, 1 ) );

   if ( hm1.empty( ) )
      cout << "The hash_multimap hm1 is empty." << endl;
   else
      cout << "The hash_multimap hm1 is not empty." << endl;

   if ( hm2.empty( ) )
      cout << "The hash_multimap hm2 is empty." << endl;
   else
      cout << "The hash_multimap hm2 is not empty." << endl;
}
```

```Output
The hash_multimap hm1 is not empty.
The hash_multimap hm2 is empty.
```

## <a name="hash_multimapend"></a><a name="end"></a> hash_multimap:: end

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает итератор, адресующий место, следующее за последним элементом в hash_multimap.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор, адресующий место, которое следует за последним элементом в hash_multimap. Если hash_multimap пуст, то hash_multimap::end == hash_multimap::begin.

### <a name="remarks"></a>Примечания

`end` используется для проверки того, достиг ли итератор конца своего hash_multimap.

Значение, возвращаемое `end`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_multimap_end.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: iterator hm1_Iter;
   hash_multimap <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_cIter = hm1.end( );
   hm1_cIter--;
   cout << "The value of last element of hm1 is "
        << hm1_cIter -> second << "." << endl;

   hm1_Iter = hm1.end( );
   hm1_Iter--;
   hm1.erase ( hm1_Iter );

   // The following 2 lines would err because the iterator is const
   // hm1_cIter = hm1.end ( );
   // hm1_cIter--;
   // hm1.erase ( hm1_cIter );

   hm1_cIter = hm1.end( );
   hm1_cIter--;
   cout << "The value of last element of hm1 is now "
        << hm1_cIter -> second << "." << endl;
}
```

```Output
The value of last element of hm1 is 30.
The value of last element of hm1 is now 20.
```

## <a name="hash_multimapequal_range"></a><a name="equal_range"></a> hash_multimap:: equal_range

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает пару итераторов соответственно на первый элемент в hash_multimap с ключом, который больше, чем указанный ключ, и на первый элемент в hash_multimap с ключом, который больше или равен данному ключу.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ аргумента для сравнения с ключом сортировки элемента из hash_multimap, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Пара итераторов, первый из которых является [lower_bound](#lower_bound) ключа, а второй — [upper_bound](#upper_bound) ключа.

Для доступа к первому итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **сначала** и для разыменования итератора нижней границы используйте \* ( `pr` . **первый**). Для доступа ко второму итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **второй** и для разыменования итератора верхней границы используйте \* ( `pr` . **второй**).

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multimap_equal_range.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef hash_multimap <int, int> IntMMap;
   IntMMap hm1;
   hash_multimap <int, int> :: const_iterator hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   pair <IntMMap::const_iterator, IntMMap::const_iterator> p1, p2;
   p1 = hm1.equal_range( 2 );

   cout << "The lower bound of the element with a key of 2\n"
        << "in the hash_multimap hm1 is: "
        << p1.first -> second << "." << endl;

   cout << "The upper bound of the element with a key of 2\n"
        << "in the hash_multimap hm1 is: "
        << p1.second -> second << "." << endl;

   // Compare the upper_bound called directly
   hm1_RcIter = hm1.upper_bound( 2 );

   cout << "A direct call of upper_bound( 2 ) gives "
        << hm1_RcIter -> second << "," << endl
        << "matching the 2nd element of the pair "
        << "returned by equal_range( 2 )." << endl;

   p2 = hm1.equal_range( 4 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == hm1.end( ) ) && ( p2.second == hm1.end( ) ) )
      cout << "The hash_multimap hm1 doesn't have an element "
           << "with a key less than 4." << endl;
   else
      cout << "The element of hash_multimap hm1 with a key >= 40 is: "
           << p1.first -> first << "." << endl;
}
```

```Output
The lower bound of the element with a key of 2
in the hash_multimap hm1 is: 20.
The upper bound of the element with a key of 2
in the hash_multimap hm1 is: 30.
A direct call of upper_bound( 2 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 2 ).
The hash_multimap hm1 doesn't have an element with a key less than 4.
```

## <a name="hash_multimaperase"></a><a name="erase"></a> hash_multimap:: Erase

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Удаляет элемент или диапазон элементов в объекте hash_multimap с заданных позиций или удаляет элементы, соответствующие заданному ключу.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Параметры

*_Where*\
Положение элемента, удаляемого из объекта hash_multimap.

*first*\
Положение первого элемента, удаляемого из объекта hash_multimap.

*last*\
Положение сразу после последнего элемента, удаляемого из объекта hash_multimap.

*раздел*\
Ключ элементов, удаляемых из объекта hash_multimap.

### <a name="return-value"></a>Возвращаемое значение

Для первых двух функций-членов — двунаправленный итератор, указывающий на первый элемент, оставшийся после удаления элементов, или указатель конца объекта hash_multimap, если такого элемента не существует.

Для третьей функции-члена возвращает число элементов, которые были удалены из объекта hash_multimap.

### <a name="remarks"></a>Примечания

Функции-члены не создают исключений.

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена hash_multimap::erase.

```cpp
// hash_multimap_erase.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1, hm2, hm3;
    hash_multimap<int, int> :: iterator pIter, Iter1, Iter2;
    int i;
    hash_multimap<int, int>::size_type n;
    typedef pair<int, int> Int_Pair;

    for (i = 1; i < 5; i++)
    {
        hm1.insert(Int_Pair (i, i) );
        hm2.insert(Int_Pair (i, i*i) );
        hm3.insert(Int_Pair (i, i-1) );
    }

    // The 1st member function removes an element at a given position
    Iter1 = ++hm1.begin();
    hm1.erase(Iter1);

    cout << "After the 2nd element is deleted, "
         << "the hash_multimap hm1 is:";
    for (pIter = hm1.begin(); pIter != hm1.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 2nd member function removes elements
    // in the range [ first,  last)
    Iter1 = ++hm2.begin();
    Iter2 = --hm2.end();
    hm2.erase(Iter1, Iter2);

    cout << "After the middle two elements are deleted, "
         << "the hash_multimap hm2 is:";
    for (pIter = hm2.begin(); pIter != hm2.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 3rd member function removes elements with a given  key
    hm3.insert(Int_Pair (2, 5));
    n = hm3.erase(2);

    cout << "After the element with a key of 2 is deleted,\n"
         << "the hash_multimap hm3 is:";
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 3rd member function returns the number of elements removed
    cout << "The number of elements removed from hm3 is: "
         << n << "." << endl;

    // The dereferenced iterator can also be used to specify a key
    Iter1 = ++hm3.begin();
    hm3.erase(Iter1);

    cout << "After another element with a key equal to that of the"
         << endl;
    cout  << "2nd element is deleted, "
          << "the hash_multimap hm3 is:";
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;
}
```

```Output
After the 2nd element is deleted, the hash_multimap hm1 is: 1 3 4.
After the middle two elements are deleted, the hash_multimap hm2 is: 1 16.
After the element with a key of 2 is deleted,
the hash_multimap hm3 is: 0 2 3.
The number of elements removed from hm3 is: 2.
After another element with a key equal to that of the
2nd element is deleted, the hash_multimap hm3 is: 0 3.
```

## <a name="hash_multimapfind"></a><a name="find"></a> hash_multimap:: Find

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает итератор, адресующий первое расположение элемента в hash_multimap, ключ которого эквивалентен указанному ключу.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ для сравнения с ключом сортировки элемента из hash_multimap, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Итератор, адресующий первое расположение элемента с указанным ключом или расположение после последнего элемента в hash_multimap, если совпадений для ключа не найдено.

### <a name="remarks"></a>Примечания

Функция-член возвращает итератор, который обращается к элементу в hash_multimap, ключ сортировки которого является `equivalent` ключом аргумента в бинарном предикате, который вызывает упорядочивание на основе отношения сравнения "меньше".

Если возвращаемое значение `find` назначено `const_iterator`, объект hash_multimap изменить нельзя. Если возвращаемое значение `find` присваивается `iterator` , то объект hash_multimap можно изменить.

### <a name="example"></a>Пример

```cpp
// hash_multimap_find.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_map>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1;
    hash_multimap<int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 10));
    hm1.insert(Int_Pair(2, 20));
    hm1.insert(Int_Pair(3, 20));
    hm1.insert(Int_Pair(3, 30));

    hm1_RcIter = hm1.find(2);
    cout << "The element of hash_multimap hm1 with a key of 2 is: "
          << hm1_RcIter -> second << "." << endl;

    hm1_RcIter = hm1.find(3);
    cout << "The first element of hash_multimap hm1 with a key of 3 is: "
          << hm1_RcIter -> second << "." << endl;

    // If no match is found for the key, end() is returned
    hm1_RcIter = hm1.find(4);

    if (hm1_RcIter == hm1.end())
        cout << "The hash_multimap hm1 doesn't have an element "
             << "with a key of 4." << endl;
    else
        cout << "The element of hash_multimap hm1 with a key of 4 is: "
             << hm1_RcIter -> second << "." << endl;

    // The element at a specific location in the hash_multimap can be
    // found using a dereferenced iterator addressing the location
    hm1_AcIter = hm1.end();
    hm1_AcIter--;
    hm1_RcIter = hm1.find(hm1_AcIter -> first);
    cout << "The first element of hm1 with a key matching"
         << endl << "that of the last element is: "
         << hm1_RcIter -> second << "." << endl;

    // Note that the first element with a key equal to
    // the key of the last element is not the last element
    if (hm1_RcIter == --hm1.end())
        cout << "This is the last element of hash_multimap hm1."
             << endl;
    else
        cout << "This is not the last element of hash_multimap hm1."
             << endl;
}
```

```Output
The element of hash_multimap hm1 with a key of 2 is: 20.
The first element of hash_multimap hm1 with a key of 3 is: 20.
The hash_multimap hm1 doesn't have an element with a key of 4.
The first element of hm1 with a key matching
that of the last element is: 20.
This is not the last element of hash_multimap hm1.
```

## <a name="hash_multimapget_allocator"></a><a name="get_allocator"></a> hash_multimap:: get_allocator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает копию объекта-распределителя, используемого для создания hash_multimap.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Распределитель, используемый hash_multimap.

### <a name="remarks"></a>Примечания

Распределители для класса hash_multimap определяют, как этот класс управляет хранилищем. Распределителей по умолчанию в классах контейнеров стандартной библиотеки C++ достаточно для большинства задач программирования. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.

### <a name="example"></a>Пример

```cpp
// hash_multimap_get_allocator.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int>::allocator_type hm1_Alloc;
   hash_multimap <int, int>::allocator_type hm2_Alloc;
   hash_multimap <int, double>::allocator_type hm3_Alloc;
   hash_multimap <int, int>::allocator_type hm4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   hash_multimap <int, int> hm1;
   hash_multimap <int, int> hm2;
   hash_multimap <int, double> hm3;

   hm1_Alloc = hm1.get_allocator( );
   hm2_Alloc = hm2.get_allocator( );
   hm3_Alloc = hm3.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << " before free memory is exhausted: "
        << hm2.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << " before free memory is exhausted: "
        << hm3.max_size( ) <<  "." << endl;

   // The following line creates a hash_multimap hm4
   // with the allocator of hash_multimap hm1.
   hash_multimap <int, int> hm4( less<int>( ), hm1_Alloc );

   hm4_Alloc = hm4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated by the other
   if( hm1_Alloc == hm4_Alloc )
   {
      cout << "The allocators are interchangeable."
           << endl;
   }
   else
   {
      cout << "The allocators are not interchangeable."
           << endl;
   }
}
```

## <a name="hash_multimaphash_multimap"></a><a name="hash_multimap"></a> hash_multimap:: hash_multimap

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Создает hash_multimap, который пуст или является копией части или целого другого hash_multimap.

```cpp
hash_multimap();

explicit hash_multimap(
    const Compare& Comp);

hash_multimap(
    const Compare& Comp,
    const Allocator& Al);

hash_multimap(
    const hash_multimap& Right);

hash_multimap(
    hash_multimap&& Right);

hash_multimap(
    initializer_list<Type> IList);

hash_multimap(
    initializer_list<Type> IList,
    const Compare& Comp);

hash_multimap(
    initializer_list<Type> IList,
    const Compare& Comp,
    const Allocator& Al);

template <class InputIterator>
hash_multimap(
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
hash_multimap(
    InputIterator First,
    InputIterator Last,
    const Compare& Comp);

template <class InputIterator>
hash_multimap(
    InputIterator First,
    InputIterator Last,
    const Compare& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Параметры

*Al*\
Класс распределителя хранилища для данного объекта hash_multimap, значение по умолчанию `Allocator`.

*Соответствовал*\
Функция сравнения типа `const Traits` для использования при упорядочивании элементов в сопоставлении. Значение по умолчанию — `Traits`.

*right*\
Сопоставление, копией которого будет создаваемое сопоставление.

*First*\
Положение первого элемента в диапазоне копируемых элементов.

*last*\
Положение первого элемента после диапазона копируемых элементов.

*Интерфейс*\
Копируемый initializer_list.

### <a name="remarks"></a>Примечания

Все конструкторы хранят тип объекта-распределителя, который управляет хранилищем памяти для hash_multimap и который позже может быть получен путем вызова [get_allocator](#get_allocator). Параметр распределителя часто опускается в объявлениях классов, и для замены альтернативных распределителей используются макросы предварительной обработки.

Все конструкторы выполняют инициализацию своих hash_multimap.

Все конструкторы хранят объект функции типа `Traits`, который используется для установления порядка ключей hash_multimap и затем может быть возвращен путем вызова [key_comp](#key_comp).

Первые три конструктора указывают пустую начальную hash_multimap; второй указывает тип функции сравнения (*comp*), которая будет использоваться при установлении порядка элементов, а третья явно указывает тип распределителя ( `_Al` ) для использования. Ключевое слово **`explicit`** подавляет определенные виды автоматического преобразования типов.

Четвертый конструктор задает копию hash_multimap `Right`.

Следующие три конструктора копируют диапазон `First, Last)` сопоставления с повышением точности при указании типа функции сравнения класса `Traits` и распределителя.

Восьмой конструктор перемещает hash_multimap `Right`.

Последние три конструктора используют initializer_list.

## <a name="hash_multimapinsert"></a><a name="insert"></a> hash_multimap:: INSERT

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Вставляет элемент или диапазон элементов в hash_multimap.

```cpp
iterator insert(
    const value_type& Val);

iterator insert(
    const_iterator Where,
    const value_type& Val);void insert(
    initializer_list<value_type> IList);

template <class InputIterator>
void insert(
    InputIterator First,
    InputIterator Last);

template <class ValTy>
iterator insert(
    ValTy&& Val);

template <class ValTy>
iterator insert(
    const_iterator Where,
    ValTy&& Val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение элемента, вставляемого в hash_multimap, если он уже не содержит этот элемент, или в более общем смысле, если он уже не содержит элемент, ключ которого эквивалентно задан.

*Where*\
Подсказка, где начинать поиск правильной точки вставки.

*First*\
Позиция первого элемента, который следует скопировать из карты.

*last*\
Позиция непосредственно перед последним элементом, который следует скопировать из карты.

### <a name="return-value"></a>Возвращаемое значение

Две первые функции-члена `insert` возвращают итератор, указывающий позицию вставки нового элемента.

Третья функция-член использует initializer_list для вставляемых элементов.

Четвертая функция-член вставляет последовательность значений элемента в карту, соответствующую каждому элементу, указанному итератором, в диапазоне `[First, Last)` . указанного набора.

Последние две функции-члена `insert` аналогичны первым двум, за исключением того, что они перемещают-конструируют вставленное значение.

### <a name="remarks"></a>Примечания

Значение [value_type](#value_type) элемента — это пара, таким образом значение элемента будет упорядоченной парой, в которой первый компонент равен значению ключа, а второй компонент — значению данных элемента.

Вставка может производиться в течение постоянного времени для версии подсказок `insert` , а не логарифмического времени, если точка вставки выполняется непосредственно после. *Where*

## <a name="hash_multimapiterator"></a><a name="iterator"></a> hash_multimap:: итератор

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, предоставляющий двунаправленный итератор, который может считывать или изменять любой элемент в hash_multimap.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Примечания

Объект, `iterator` определенный hash_multimap, указывает на объекты [value_type](#value_type), имеющие тип `pair` \< **const Key, Type**> , первый элемент которого является ключом к элементу, а второй элемент — сопоставленная база данных, удерживаемая элементом.

Для разыменования итератора с именем `Iter` , указывающего на элемент в hash_multimap, используйте `->` оператор.

Чтобы получить доступ к значению ключа для элемента, используйте `Iter->first` , что эквивалентно `(*Iter).first` . Чтобы получить доступ к значению сопоставленной версии элемента, используйте `Iter->second` , что эквивалентно `(*Iter).first` .

Тип `iterator` можно использовать для изменения значения элемента.

### <a name="example"></a>Пример

См. пример объявления и использования `iterator` см. в разделе [begin](#begin).

## <a name="hash_multimapkey_comp"></a><a name="key_comp"></a> hash_multimap:: key_comp

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Извлекает копию объекта сравнения, использованного для упорядочивания ключей в hash_multimap.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект функции, который hash_multimap использует для упорядочения своих элементов.

### <a name="remarks"></a>Примечания

Хранимый объект определяет функцию-член

`bool operator( const Key& left, const Key& right );`

Возвращает значение, **`true`** Если `left` предшествует и не равно `right` в порядке сортировки.

### <a name="example"></a>Пример

```cpp
// hash_multimap_key_comp.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multimap <int, int, hash_compare<int, less<int>>> hm1;
   hash_multimap <int, int, hash_compare<int, less<int>>
      >::key_compare kc1 = hm1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true,\n"
           << "where kc1 is the function object of hm1.\n"
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false,\n"
           << "where kc1 is the function object of hm1.\n"
           << endl;
   }

   hash_multimap <int, int, hash_compare<int, greater<int>>> hm2;
   hash_multimap <int, int, hash_compare<int, greater<int>>
      >::key_compare kc2 = hm2.key_comp( );
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true,\n"
           << "where kc2 is the function object of hm2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false,\n"
           << "where kc2 is the function object of hm2."
           << endl;
   }
}
```

## <a name="hash_multimapkey_compare"></a><a name="key_compare"></a> hash_multimap:: key_compare

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, предоставляющий объект функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в hash_multimap.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Примечания

`key_compare` является синонимом для *характеристик*параметра шаблона.

Дополнительные сведения о *характеристиках* см. в разделе [hash_multimap Class](../standard-library/hash-multimap-class.md) .

### <a name="example"></a>Пример

См. пример для [key_comp](#key_comp) в качестве примера объявления и использования `key_compare`.

## <a name="hash_multimapkey_type"></a><a name="key_type"></a> hash_multimap:: key_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, описывающий объект ключа сортировки, составляющий каждый элемент hash_multimap.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Примечания

`key_type` является синонимом для *ключа*параметра шаблона.

Дополнительные сведения о *ключе*см. в подразделе "Примечания" раздела [hash_multimap Class](../standard-library/hash-multimap-class.md) .

### <a name="example"></a>Пример

См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_compare`.

## <a name="hash_multimaplower_bound"></a><a name="lower_bound"></a> hash_multimap:: lower_bound

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает итератор, указывающий на первый элемент в hash_multimap с ключом, который больше или равен указанному ключу.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ аргумента для сравнения с ключом сортировки элемента из hash_multimap, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

[Итератор](#iterator) или [const_iterator](#const_iterator), адресующий расположение элемента в hash_multimap с ключом, который равен или больше, чем ключ-аргумент, или адресующий расположение после последнего элемента в hash_multimap, если совпадение для ключа не найдено.

Если возвращаемое значение `lower_bound` назначено `const_iterator`, объект hash_multimap изменить нельзя. Если возвращаемое значение `lower_bound` присваивается `iterator` , то объект hash_multimap можно изменить.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multimap_lower_bound.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;
   hash_multimap <int, int> :: const_iterator hm1_AcIter,
      hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_RcIter = hm1.lower_bound( 2 );
   cout << "The element of hash_multimap hm1 with a key of 2 is: "
        << hm1_RcIter -> second << "." << endl;

   hm1_RcIter = hm1.lower_bound( 3 );
   cout << "The first element of hash_multimap hm1 with a key of 3 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   hm1_RcIter = hm1.lower_bound( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_multimap hm1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of hash_multimap hm1 with a key of 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // The element at a specific location in the hash_multimap can be
   // found using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.end( );
   hm1_AcIter--;
   hm1_RcIter = hm1.lower_bound( hm1_AcIter -> first );
   cout << "The first element of hm1 with a key matching"
        << endl << "that of the last element is: "
        << hm1_RcIter -> second << "." << endl;

   // Note that the first element with a key equal to
   // the key of the last element is not the last element
   if ( hm1_RcIter == --hm1.end( ) )
      cout << "This is the last element of hash_multimap hm1."
           << endl;
   else
      cout << "This is not the last element of hash_multimap hm1."
           << endl;
}
```

```Output
The element of hash_multimap hm1 with a key of 2 is: 20.
The first element of hash_multimap hm1 with a key of 3 is: 20.
The hash_multimap hm1 doesn't have an element with a key of 4.
The first element of hm1 with a key matching
that of the last element is: 20.
This is not the last element of hash_multimap hm1.
```

## <a name="hash_multimapmapped_type"></a><a name="mapped_type"></a> hash_multimap:: mapped_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, представляющий тип данных, хранящийся в hash_multimap.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Примечания

`mapped_type` — синоним параметра-шаблона *Type*.

Дополнительные сведения о *типе* см. в разделе [hash_multimap Class](../standard-library/hash-multimap-class.md) .

### <a name="example"></a>Пример

См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_type`.

## <a name="hash_multimapmax_size"></a><a name="max_size"></a> hash_multimap:: max_size

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает максимальную длину hash_multimap.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимально возможная длина hash_multimap.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multimap_max_size.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;
   hash_multimap <int, int> :: size_type i;

   i = hm1.max_size( );
   cout << "The maximum possible length "
        << "of the hash_multimap is " << i << "." << endl;
}
```

## <a name="hash_multimapoperator"></a><a name="op_eq"></a> hash_multimap::operator=

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Заменяет элементы hash_multimap копией другого hash_multimap.

```cpp
hash_multimap& operator=(const hash_multimap& right);

hash_multimap& operator=(hash_multimap&& right);
```

### <a name="parameters"></a>Параметры

*right*\
[Hash_multimap](../standard-library/hash-multimap-class.md), который копируется в `hash_multimap`.

### <a name="remarks"></a>Примечания

После стирания любых существующих элементов в `hash_multimap` , `operator=` копирует или перемещает содержимое *непосредственно* в `hash_multimap` .

### <a name="example"></a>Пример

```cpp
// hash_multimap_operator_as.cpp
// compile with: /EHsc
#include <hash_multimap>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap<int, int> v1, v2, v3;
   hash_multimap<int, int>::iterator iter;

   v1.insert(pair<int, int>(1, 10));

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << iter->second << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter->second << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter->second << " ";
   cout << endl;
}
```

## <a name="hash_multimappointer"></a><a name="pointer"></a> hash_multimap::p оинтер

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, предоставляющий указатель на элемент в hash_multimap.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Примечания

Тип `pointer` можно использовать для изменения значения элемента.

В большинстве случаев [итератор](#iterator) должен использоваться для доступа к элементам в объекте hash_multimap.

## <a name="hash_multimaprbegin"></a><a name="rbegin"></a> hash_multimap:: rbegin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает итератор, адресующий первый элемент в обратном hash_multimap.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий первый элемент в обратном hash_multimap (или адресующий элемент, ранее бывший последним элементом в hash_multimap до изменения его порядка на обратный).

### <a name="remarks"></a>Примечания

`rbegin` используется с обратным hash_multimap так же, как [begin](#begin) используется с hash_multimap.

Если возвращаемое значение `rbegin` назначено `const_reverse_iterator`, объект hash_multimap изменить нельзя. Если возвращаемое значение `rbegin` назначено `reverse_iterator`, объект hash_multimap можно изменить.

`rbegin` можно использовать для прохода по hash_multimap в обратную стороны.

### <a name="example"></a>Пример

```cpp
// hash_multimap_rbegin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: iterator hm1_Iter;
   hash_multimap <int, int> :: reverse_iterator hm1_rIter;
   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_rIter = hm1.rbegin( );
   cout << "The first element of the reversed hash_multimap hm1 is "
        << hm1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a hash_multimap in a forward order
   cout << "The hash_multimap is: ";
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( ); hm1_Iter++)
      cout << hm1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a hash_multimap in a reverse order
   cout << "The reversed hash_multimap is: ";
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( ); hm1_rIter++)
      cout << hm1_rIter -> first << " ";
      cout << "." << endl;

   // A hash_multimap element can be erased by dereferencing its key
   hm1_rIter = hm1.rbegin( );
   hm1.erase ( hm1_rIter -> first );

   hm1_rIter = hm1.rbegin( );
   cout << "After the erasure, the first element\n"
        << "in the reversed hash_multimap is "
        << hm1_rIter -> first << "." << endl;
}
```

```Output
The first element of the reversed hash_multimap hm1 is 3.
The hash_multimap is: 1 2 3 .
The reversed hash_multimap is: 3 2 1 .
After the erasure, the first element
in the reversed hash_multimap is 2.
```

## <a name="hash_multimapreference"></a><a name="reference"></a> hash_multimap:: Reference

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, предоставляющий ссылку на элемент, хранящийся в hash_multimap.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::reference reference;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multimap_reference.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( hm1.begin( ) -> first );

   // The following line would cause an error as the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( hm1.begin( ) -> first );

   cout << "The key of first element in the hash_multimap is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( hm1.begin( ) -> second );

   cout << "The data value of first element in the hash_multimap is "
        << Ref2 << "." << endl;

   //The non-const_reference can be used to modify the
   //data value of the first element
   Ref2 = Ref2 + 5;
   cout << "The modified data value of first element is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the hash_multimap is 1.
The data value of first element in the hash_multimap is 10.
The modified data value of first element is 15.
```

## <a name="hash_multimaprend"></a><a name="rend"></a> hash_multimap:: rend

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает итератор, адресующий место, следующее за последним элементом в обращенном hash_multimap.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий место после последнего элемента в обращенном hash_multimap (место перед первым элементом в hash_multimap до изменения его порядка на обратный).

### <a name="remarks"></a>Примечания

`rend` используется с обращенным hash_multimap так же, как [end](#end) используется с hash_multimap.

Если возвращаемое значение `rend` назначено [const_reverse_iterator](#const_reverse_iterator), то объект hash_multimap изменить нельзя. Если возвращаемое значение `rend` назначено [reverse_iterator](#reverse_iterator), то объект hash_multimap можно изменить.

`rend` используется, чтобы проверить, достиг ли обратный итератор конца своего hash_multimap.

Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_multimap_rend.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;

   hash_multimap <int, int> :: iterator hm1_Iter;
   hash_multimap <int, int> :: reverse_iterator hm1_rIter;
   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_rIter = hm1.rend( );
   hm1_rIter--;
   cout << "The last element of the reversed hash_multimap hm1 is "
        << hm1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a hash_multimap in a forward order
   cout << "The hash_multimap is: ";
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( ); hm1_Iter++)
      cout << hm1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a hash_multimap in a reverse order
   cout << "The reversed hash_multimap is: ";
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( ); hm1_rIter++)
      cout << hm1_rIter -> first << " ";
      cout << "." << endl;

   // A hash_multimap element can be erased by dereferencing its key
   hm1_rIter = --hm1.rend( );
   hm1.erase ( hm1_rIter -> first );

   hm1_rIter = hm1.rend( );
   hm1_rIter--;
   cout << "After the erasure, the last element "
        << "in the reversed hash_multimap is "
        << hm1_rIter -> first << "." << endl;
}
```

```Output
The last element of the reversed hash_multimap hm1 is 1.
The hash_multimap is: 1 2 3 .
The reversed hash_multimap is: 3 2 1 .
After the erasure, the last element in the reversed hash_multimap is 2.
```

## <a name="hash_multimapreverse_iterator"></a><a name="reverse_iterator"></a> hash_multimap:: reverse_iterator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, предоставляющий двунаправленный итератор, который может считывать или изменять элемент в обращенном hash_multimap.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `reverse_iterator` используется для последовательного перебора hash_multimap в обратную сторону.

Объект, `reverse_iterator` определенный hash_multimap, указывает на объекты [value_type](#value_type), имеющие тип `pair` \< **const Key, Type**> . Значение ключа доступно через первый член пары, а значение сопоставленного элемента доступно через второй член пары.

### <a name="example"></a>Пример

См. пример для [rbegin](#rbegin) в качестве примера объявления и использования `reverse_iterator`.

## <a name="hash_multimapsize"></a><a name="size"></a> hash_multimap:: size

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает число элементов в объекте hash_multimap.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая длина hash_multimap.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена hash_multimap::size.

```cpp
// hash_multimap_size.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_multimap<int, int> hm1, hm2;
    hash_multimap<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    i = hm1.size();
    cout << "The hash_multimap length is " << i << "." << endl;

    hm1.insert(Int_Pair(2, 4));
    i = hm1.size();
    cout << "The hash_multimap length is now " << i << "." << endl;
}
```

```Output
The hash_multimap length is 1.
The hash_multimap length is now 2.
```

## <a name="hash_multimapsize_type"></a><a name="size_type"></a> hash_multimap:: size_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип целого числа без знака, который подсчитывает число элементов в hash_multimap.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

См. пример для [size](#size) в качестве примера объявления и использования `size_type`

## <a name="hash_multimapswap"></a><a name="swap"></a> hash_multimap:: swap

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Меняет местами элементы двух hash_multimap.

```cpp
void swap(hash_multimap& right);
```

### <a name="parameters"></a>Параметры

*right*\
Hash_multimap, предоставляющий элементы для обмена местами, или hash_multimap, элементы которого должны обменяться с элементами hash_multimap.

### <a name="remarks"></a>Примечания

Функция-член не делает недействительным ссылки, указатели или итераторы, обозначающие элементы в двух hash_multimap, для которых выполняется обмен элементами.

### <a name="example"></a>Пример

```cpp
// hash_multimap_swap.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1, hm2, hm3;
   hash_multimap <int, int>::iterator hm1_Iter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );
   hm2.insert ( Int_Pair ( 10, 100 ) );
   hm2.insert ( Int_Pair ( 20, 200 ) );
   hm3.insert ( Int_Pair ( 30, 300 ) );

   cout << "The original hash_multimap hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout   << "." << endl;

   // This is the member function version of swap
   hm1.swap( hm2 );

   cout << "After swapping with hm2, hash_multimap hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( hm1, hm3 );

   cout << "After swapping with hm3, hash_multimap hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout   << "." << endl;
}
```

```Output
The original hash_multimap hm1 is: 10 20 30.
After swapping with hm2, hash_multimap hm1 is: 100 200.
After swapping with hm3, hash_multimap hm1 is: 300.
```

## <a name="hash_multimapupper_bound"></a><a name="upper_bound"></a> hash_multimap:: upper_bound

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Возвращает итератор, указывающий на первый элемент в hash_multimap с ключом, который больше указанного ключа.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ аргумента для сравнения с ключом сортировки элемента из hash_multimap, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

[iterator](#iterator) или [const_iterator](#const_iterator), адресующий расположение элемента в hash_multimap с ключом, который больше, чем ключ-аргумент, или адресующий расположение после последнего элемента в hash_multimap, если совпадение для ключа не найдено.

Если возвращаемое значение `upper_bound` назначено `const_iterator`, объект hash_multimap изменить нельзя. Если возвращаемое значение `upper_bound` присваивается `iterator` , то объект hash_multimap можно изменить.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multimap_upper_bound.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1;
   hash_multimap <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );
   hm1.insert ( Int_Pair ( 3, 40 ) );

   hm1_RcIter = hm1.upper_bound( 1 );
   cout << "The 1st element of hash_multimap hm1 with "
        << "a key greater than 1 is: "
        << hm1_RcIter -> second << "." << endl;

   hm1_RcIter = hm1.upper_bound( 2 );
   cout << "The first element of hash_multimap hm1\n"
        << "with a key greater than 2 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   hm1_RcIter = hm1.lower_bound( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_multimap hm1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of hash_multimap hm1 with a key of 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // The element at a specific location in the hash_multimap can be
   // found using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.begin( );
   hm1_RcIter = hm1.upper_bound( hm1_AcIter -> first );
   cout << "The first element of hm1 with a key greater than"
        << endl << "that of the initial element of hm1 is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The 1st element of hash_multimap hm1 with a key greater than 1 is: 20.
The first element of hash_multimap hm1
with a key  greater than 2 is: 30.
The hash_multimap hm1 doesn't have an element with a key of 4.
The first element of hm1 with a key greater than
that of the initial element of hm1 is: 20.
```

## <a name="hash_multimapvalue_comp"></a><a name="value_comp"></a> hash_multimap:: value_comp

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Функция-член возвращает объект функции, который определяет порядок элементов в hash_multimap путем сравнения значений ключа.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект функции сравнения, который hash_multimap использует для упорядочения своих элементов.

### <a name="remarks"></a>Примечания

Для hash_multimap *m*, если два элемента *E1* (*K1*, *D1*) и *e2*(*априорной оценкой K2*, *D2*) являются объектами типа [value_type](#value_type), где *k1* и *априорной оценкой K2* — это ключи типа [key_type](#key_type) , а *D1* и *D2* — их данные типа [mapped_type](#mapped_type), то `m.value_comp()(e1, e2)` он эквивалентен `m.key_comp()(k1, k2)` . Хранимый объект определяет функцию-член

`bool operator( value_type& left, value_type& right);`

Возвращает, **`true`** Если значение ключа `left` предшествует значению ключа в порядке сортировки и не равно ему `right` .

### <a name="example"></a>Пример

```cpp
// hash_multimap_value_comp.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multimap <int, int, hash_compare<int, less<int>>> hm1;
   hash_multimap <int, int, hash_compare<int, less<int>>
      >::value_compare vc1 = hm1.value_comp( );
   hash_multimap <int,int>::iterator Iter1, Iter2;

   Iter1= hm1.insert ( hash_multimap <int, int> :: value_type ( 1, 10 ) );
   Iter2= hm1.insert ( hash_multimap <int, int> :: value_type ( 2, 5 ) );

   if( vc1( *Iter1, *Iter2 ) == true )
   {
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."
           << endl;
   }
   else
   {
      cout << "The element ( 1,10 ) does "
           << "not precede the element ( 2,5 )."
           << endl;
   }

   if( vc1( *Iter2, *Iter1 ) == true )
   {
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."
           << endl;
   }
   else
   {
      cout << "The element ( 2,5 ) does "
           << "not precede the element ( 1,10 )."
           << endl;
   }
}
```

## <a name="hash_multimapvalue_type"></a><a name="value_type"></a> hash_multimap:: value_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [unordered_multimap Class](../standard-library/unordered-multimap-class.md).

Тип, представляющий тип объекта, который хранится в hash_multimap.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="remarks"></a>Примечания

`value_type` объявлен как парный \<const [key_type](#key_type), [mapped_type](#mapped_type)> и непарный, \<key_type, mapped_type> так как ключи ассоциативного контейнера не могут быть изменены с помощью неконстантного итератора или ссылки.

### <a name="example"></a>Пример

```cpp
// hash_multimap_value_type.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef pair <const int, int> cInt2Int;
   hash_multimap <int, int> hm1;
   hash_multimap <int, int> :: key_type key1;
   hash_multimap <int, int> :: mapped_type mapped1;
   hash_multimap <int, int> :: value_type value1;
   hash_multimap <int, int> :: iterator pIter;

   // value_type can be used to pass the correct type
   // explicitly to avoid implicit type conversion
   hm1.insert ( hash_multimap <int, int> :: value_type ( 1, 10 ) );

   // Compare another way to insert objects into a hash_multimap
   hm1.insert ( cInt2Int ( 2, 20 ) );

   // Initializing key1 and mapped1
   key1 = ( hm1.begin( ) -> first );
   mapped1 = ( hm1.begin( ) -> second );

   cout << "The key of first element in the hash_multimap is "
        << key1 << "." << endl;

   cout << "The data value of first element in the hash_multimap is "
        << mapped1 << "." << endl;

   // The following line would cause an error because
   // the value_type is not assignable
   // value1 = cInt2Int ( 4, 40 );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;
}
```

```Output
The key of first element in the hash_multimap is 1.
The data value of first element in the hash_multimap is 10.
The keys of the mapped elements are: 1 2.
The values of the mapped elements are: 10 20.
```

## <a name="see-also"></a>См. также

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
