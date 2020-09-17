---
title: Класс hash_map
ms.date: 11/04/2016
f1_keywords:
- hash_map/stdext::hash_map
- hash_map/stdext::hash_map::allocator_type
- hash_map/stdext::hash_map::const_iterator
- hash_map/stdext::hash_map::const_pointer
- hash_map/stdext::hash_map::const_reference
- hash_map/stdext::hash_map::const_reverse_iterator
- hash_map/stdext::hash_map::difference_type
- hash_map/stdext::hash_map::iterator
- hash_map/stdext::hash_map::key_compare
- hash_map/stdext::hash_map::key_type
- hash_map/stdext::hash_map::mapped_type
- hash_map/stdext::hash_map::pointer
- hash_map/stdext::hash_map::reference
- hash_map/stdext::hash_map::reverse_iterator
- hash_map/stdext::hash_map::size_type
- hash_map/stdext::hash_map::value_type
- hash_map/stdext::hash_map::at
- hash_map/stdext::hash_map::begin
- hash_map/stdext::hash_map::cbegin
- hash_map/stdext::hash_map::cend
- hash_map/stdext::hash_map::clear
- hash_map/stdext::hash_map::count
- hash_map/stdext::hash_map::crbegin
- hash_map/stdext::hash_map::crend
- hash_map/stdext::hash_map::emplace
- hash_map/stdext::hash_map::emplace_hint
- hash_map/stdext::hash_map::empty
- hash_map/stdext::hash_map::end
- hash_map/stdext::hash_map::equal_range
- hash_map/stdext::hash_map::erase
- hash_map/stdext::hash_map::find
- hash_map/stdext::hash_map::get_allocator
- hash_map/stdext::hash_map::insert
- hash_map/stdext::hash_map::key_comp
- hash_map/stdext::hash_map::lower_bound
- hash_map/stdext::hash_map::max_size
- hash_map/stdext::hash_map::rbegin
- hash_map/stdext::hash_map::rend
- hash_map/stdext::hash_map::size
- hash_map/stdext::hash_map::swap
- hash_map/stdext::hash_map::upper_bound
- hash_map/stdext::hash_map::value_comp
helpviewer_keywords:
- stdext::hash_map
- stdext::hash_map::allocator_type
- stdext::hash_map::const_iterator
- stdext::hash_map::const_pointer
- stdext::hash_map::const_reference
- stdext::hash_map::const_reverse_iterator
- stdext::hash_map::difference_type
- stdext::hash_map::iterator
- stdext::hash_map::key_compare
- stdext::hash_map::key_type
- stdext::hash_map::mapped_type
- stdext::hash_map::pointer
- stdext::hash_map::reference
- stdext::hash_map::reverse_iterator
- stdext::hash_map::size_type
- stdext::hash_map::value_type
- stdext::hash_map::at
- stdext::hash_map::begin
- stdext::hash_map::cbegin
- stdext::hash_map::cend
- stdext::hash_map::clear
- stdext::hash_map::count
- stdext::hash_map::crbegin
- stdext::hash_map::crend
- stdext::hash_map::emplace
- stdext::hash_map::emplace_hint
- stdext::hash_map::empty
- stdext::hash_map::end
- stdext::hash_map::equal_range
- stdext::hash_map::erase
- stdext::hash_map::find
- stdext::hash_map::get_allocator
- stdext::hash_map::insert
- stdext::hash_map::key_comp
- stdext::hash_map::lower_bound
- stdext::hash_map::max_size
- stdext::hash_map::rbegin
- stdext::hash_map::rend
- stdext::hash_map::size
- stdext::hash_map::swap
- stdext::hash_map::upper_bound
- stdext::hash_map::value_comp
ms.assetid: 40879dfc-51ba-4a59-9f9e-26208de568a8
ms.openlocfilehash: 67f891ae7e0b9eab10b1cceda8736661a24641bb
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560653"
---
# <a name="hash_map-class"></a>Класс hash_map

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Быстро сохраняет и возвращает данные из коллекции, в которой каждый элемент является парой, содержащей уникальный ключ сортировки и связанное с ним значение.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Key,
    class Type,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<pair <const Key, Type>>>
class hash_map
```

### <a name="parameters"></a>Параметры

*Раздел*\
Тип данных ключа для сохранения в hash_map.

*Type*\
Тип данных элемента для сохранения в hash_map.

*Traits*\
Тип, который включает два объекта-функции, один из классов compare, который может сравнить значения двух элементов как ключей сортировки, чтобы определить их относительный порядок, и хэш-функцию, которая является унарным предикатом, который сопоставляет значения ключей элементов с целыми числами без знака типа `size_t`. Этот аргумент является необязательным, и hash_compare<`Key` `Key` значение по умолчанию меньше<> > .

*Allocator*\
Тип, представляющий сохраненный объект распределителя, который инкапсулирует сведения о выделении и освобождении памяти для hash_map. Этот аргумент является необязательным, а значение по умолчанию — распределитель \<pair <const `Key`, `Type`>>.

## <a name="remarks"></a>Примечания

hash_map:

- Ассоциативный контейнер, который является контейнером переменного размера, поддерживающим эффективное получение значений элементов на основе значения соответствующего ключа.

- Является реверсивным, поскольку предоставляет двунаправленный итератор для получения доступа к его элементам.

- Хэшируется, поскольку его элементы группируются в сегменты на основе значения хэш-функции, применяемой к значениям ключей элементов.

- Является уникальным, поскольку каждый его элемент должен обладать уникальным ключом.

- Является контейнером ассоциативной пары, поскольку его значения данных элементов отличаются от его значений ключей.

- Шаблон класса, поскольку предоставляемая им функциональность является универсальной и поэтому не зависит от конкретного типа данных, содержащихся в качестве элементов или ключей. Типы данных, используемые для элементов и ключей, вместо этого определяются как параметры в шаблоне класса вместе с функцией и распределителем сравнения.

Главным преимуществом хэширования по сравнению с сортировкой является повышенная эффективность; при успешном хэшировании вставка, удаление и поиск выполняются за константный средний промежуток времени по сравнению со временем, пропорциональным логарифму числа элементов в контейнере, для методов сортировки. Значение элемента в hash_map, но не связанное с ним значение ключа можно изменить напрямую. Значения ключей, связанные со старыми элементами, необходимо удалить и вставить новые значения ключей, связанные с новыми элементами.

Выбор типа контейнера должен в общем случае производиться на основе типа поиска и вставки, который требуется приложению. Хэшированные ассоциативные контейнеры оптимизированы для операций поиска, вставки и удаления. Функции-члены, которые явно поддерживают эти операции, эффективны при использовании совместно с правильно разработанной хэш-функцией, в результате чего они имеют постоянное среднее время выполнения и не зависят от числа элементов в контейнере. Правильно разработанная хэш-функция обеспечивает равномерное распределение хэшированных значений и сводит к минимуму количество конфликтов, когда разные значения ключей сопоставляются с одним хэшированным значением. В худшем случае, когда применяется наиболее неоптимальная хэш-функция, количество операций пропорционально количеству элементов в последовательности (линейное время).

Класс hash_map должен быть используемым ассоциативным контейнером, если условия, связывающие значения с ключами, удовлетворяются приложением. Модель этого типа структуры представляет собой упорядоченный список уникальных ключевых слов со связанными строковыми значениями, предоставляющими, к примеру, определения. Если вместо этого для слов существует несколько правильных определений и ключи не являются уникальными, предпочтительным контейнером будет hash_multimap. Если же сохранен только список слов, то в качестве контейнера необходимо выбрать набор hash_set. Если допускается многократное использование слов, то подходящей структурой контейнера будет hash_multiset.

Hash_map упорядочивает последовательность, которую он контролирует, вызывая хранимый объект признаков *хэша класса* [value_compare](../standard-library/value-compare-class.md). Доступ к этому сохраненному объекту можно получить путем вызова функции-члена [key_comp](#key_comp). Такой объект функции должен вести себя так же, как объект класса [hash_compare](../standard-library/hash-compare-class.md)<Key, меньше \<Key>>. В частности, для всех значений *ключа* типа *Key*вызов `Traits` ( `Key` ) дает распределение значений типа `size_t` .

В целом, упорядочиваемые элементы должны лишь подлежать сравнению "меньше чем" для установления такого порядка, чтобы, имея любые два элемента, можно было определить, что они равны (ни один не меньше другого) или что один меньше другого. Это приводит к упорядочению неравнозначных элементов. С более технической точки зрения, функция сравнения является бинарным предикатом, который вызывает строгого слабое упорядочение в стандартном математически смысле. Бинарный предикат f (x y) — это объект функции, имеющий два объекта-аргумента `x` и `y` возвращаемое значение **`true`** или **`false`** . Порядок, заданный для hash_map, является строгим слабым порядком, если бинарный предикат является нерефлексивным, антисимметричным и переходящим и если эквивалентность является переходящей, где два объекта x и y определяются как эквивалентные, когда оба параметра f(x,y) и f(y,x) имеют значение false. Если более строгое условие равенства между ключами заменяет условие эквивалентности, порядок становится общим (т.е. все элементы упорядочиваются относительно друг друга), и сопоставленные ключи будут неотличимы друг от друга.

Фактический порядок элементов в управляемой последовательности зависит от хэш-функции, функции упорядочения и текущего размера хэш-таблицы, хранимой в объекте контейнера. Текущий размер хэш-таблицы определить нельзя, поэтому обычно невозможно предсказать порядок элементов в управляемой последовательности. Вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, которые ранее указывали конкретно на удаленные элементы.

Итератор, предоставляемый классом hash_map, является двусторонним итератором, но функции — члены класса [insert](#insert) и [hash_map](#hash_map) обладают версиями, принимающими в качестве параметров шаблона более слабый итератор ввода, чьи функциональные требования ниже, чем гарантированные классом двунаправленных итераторов. Различные концепции итераторов образуют семейство, связанное уточнениями функциональности. Каждая концепция итератора имеет собственный набор требований, а алгоритмы, работающие с ними, должны ограничивать свои предположения согласно требованиям, предоставляемым этим типом итератора. Можно предположить, что итератор ввода может быть разыменован для обращения к определенному объекту и инкрементирован до следующего итератора в последовательности. Это минимальный набор функциональных возможностей, но его достаточно, чтобы иметь возможность осмысленно говорить о диапазоне итераторов `[First, Last)`, в контексте функций — членов класса.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[hash_map](#hash_map)|Создает контейнер `hash_map`, который является пустым или копией части или целого другого контейнера `hash_map`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Тип, представляющий класс `allocator` для объекта `hash_map`.|
|[const_iterator](#const_iterator)|Тип, предоставляющий двунаправленный итератор, который может читать **`const`** элемент в `hash_map` .|
|[const_pointer](#const_pointer)|Тип, предоставляющий указатель на **`const`** элемент в `hash_map` .|
|[const_reference](#const_reference)|Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в, `hash_map` для чтения и выполнения **`const`** операций.|
|[const_reverse_iterator](#const_reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может читать любой **`const`** элемент в `hash_map` .|
|[difference_type](#difference_type)|Тип целого числа со знаком, пригодный для представления количества элементов в контейнере `hash_map` в диапазоне между элементами, на которые указывают итераторы.|
|[iterator](#iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять любой элемент в `hash_map`.|
|[key_compare](#key_compare)|Тип, предоставляющий объект функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в контейнере `hash_map`.|
|[key_type](#key_type)|Тип описывает объект ключа сортировки, составляющий каждый элемент `hash_map`.|
|[mapped_type](#mapped_type)|Тип, который представляет тип данных, хранящийся в контейнере `hash_map`.|
|[pointer](#pointer)|Тип, предоставляющий указатель на элемент в `hash_map`.|
|[reference](#reference)|Тип, предоставляющий ссылку на элемент, хранящийся в контейнере `hash_map`.|
|[reverse_iterator](#reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять элемент в обращенном контейнере `hash_map`.|
|[size_type](#size_type)|Целочисленный Typedef без знака, который может представлять число элементов в `hash_map`.|
|[value_type](#value_type)|Тип, предоставляющий объект функции, который может сравнить два элемента в качестве ключей сортировки для определения их относительного порядка в контейнере `hash_map`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[at](#at)|Находит элемент в `hash_map` с указанным значением ключа.|
|[begin](#begin)|Возвращает итератор, обращающийся к первый элемент в контейнере `hash_map`.|
|[cbegin](#cbegin)|Возвращает итератор const, обращающийся к первому элементу в `hash_map`.|
|[cend](#cend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в `hash_map`.|
|[clear](#clear)|Стирает все элементы в `hash_map`.|
|[count](#count)|Возвращает число элементов в контейнере `hash_map`, ключи которых соответствуют ключу, заданному параметром.|
|[crbegin](#crbegin)|Возвращает итератор const, который обращается к первому элементу в обращенном контейнере `hash_map`.|
|[crend](#crend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в обращенном контейнере `hash_map`.|
|[emplace](#emplace)|Вставляет созданный на месте элемент в `hash_map`.|
|[emplace_hint](#emplace_hint)|Вставляет созданный на месте элемент в `hash_map` с подсказкой о размещении.|
|[empty](#empty)|Проверяет, пуст ли `hash_map`.|
|[end](#end)|Возвращает итератор, который обращается к месту, следующему за последним элементом в контейнере `hash_map`.|
|[equal_range](#equal_range)|Возвращает пару итераторов соответственно на первый элемент в наборе `hash_map` с ключом, который больше, чем указанный ключ, и на первый элемент в наборе `hash_map` с ключом, который больше или равен данному ключу.|
|[erase](#erase)|Удаляет элемент или диапазон элементов с указанных положений в `hash_map`.|
|[find](#find)|Возвращает итератор, адресующий расположение элемента в наборе `hash_map` с ключом, эквивалентным указанному ключу.|
|[get_allocator](#get_allocator)|Возвращает копию объекта `allocator`, который используется для создания контейнера `hash_map`.|
|[insert](#insert)|Вставляет элемент или диапазон элементов в `hash_map`.|
|[key_comp](#key_comp)|Возвращает итератор, указывающий на первый элемент в `hash_map` с ключом, который больше или равен указанному ключу.|
|[lower_bound](#lower_bound)|Возвращает итератор, указывающий на первый элемент в `hash_map` с ключом, который больше или равен указанному ключу.|
|[max_size](#max_size)|Возвращает максимальную длину `hash_map`.|
|[rbegin](#rbegin)|Возвращает итератор, который обращается к первому элементу в обращенном контейнере `hash_map`.|
|[rend](#rend)|Возвращает итератор, который обращается к месту, следующему за последним элементом в обращенном контейнере `hash_map`.|
|[size](#size)|Возвращает количество элементов в контейнере `hash_map`.|
|[swap](#swap)|Выполняет обмен элементами между двумя объектами `hash_map`.|
|[upper_bound](#upper_bound)|Возвращает итератор, указывающий на первый элемент в `hash_map` со значением ключа, которое больше указанного ключа.|
|[value_comp](#value_comp)|Извлекает копию объекта сравнения, который используется для упорядочивания значений элементов в наборе `hash_map`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator&#91;&#93;](#op_at)|Вставляет элемент в `hash_map` с заданным значением ключа.|
|[hash_map::operator=](#op_eq)|Заменяет элементы `hash_map` копией другого `hash_map`.|

## <a name="requirements"></a>Требования

**Заголовок:**\<hash_map>

**Пространство имен:** stdext

## <a name="hash_mapallocator_type"></a><a name="allocator_type"></a> hash_map:: allocator_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, представляющий класс распределителя для объекта hash_map.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="example"></a>Пример

См. пример использования [get_allocator](#get_allocator) в качестве примера использования `allocator_type`.

## <a name="hash_mapat"></a><a name="at"></a> hash_map:: at

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Находит элемент в hash_map с указанным значением ключа.

```cpp
Type& at(const Key& key);

const Type& at(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Значение ключа элемента, который требуется найти.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на значение данных найденного элемента.

### <a name="remarks"></a>Примечания

Если значение ключа аргумента не найдено, функция создает объект класса [out_of_range Class](../standard-library/out-of-range-class.md).

### <a name="example"></a>Пример

```cpp
// hash_map_at.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef pair <const int, int> cInt2Int;
   hash_map <int, int> hm1;

   // Insert data values
   hm1.insert ( cInt2Int ( 1, 10 ) );
   hm1.insert ( cInt2Int ( 2, 20 ) );
   hm1.insert ( cInt2Int ( 3, 30 ) );

   cout  << "The values of the mapped elements are:";
   for ( int i = 1 ; i <= hm1.size() ; i++ )
      cout << " " << hm1.at(i);
   cout << "." << endl;
}
```

## <a name="hash_mapbegin"></a><a name="begin"></a> hash_map:: Begin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает итератор, адресующий первый элемент в hash_map.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор, адресующий расположение первого элемента в hash_map или расположение после пустого hash_map.

### <a name="example"></a>Пример

```cpp
// hash_map_begin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: const_iterator hm1_cIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 0, 0 ) );
   hm1.insert ( Int_Pair ( 1, 1 ) );
   hm1.insert ( Int_Pair ( 2, 4 ) );

   hm1_cIter = hm1.begin ( );
   cout << "The first element of hm1 is "
        << hm1_cIter -> first << "." << endl;

   hm1_Iter = hm1.begin ( );
   hm1.erase ( hm1_Iter );

   // The following 2 lines would err because the iterator is const
   // hm1_cIter = hm1.begin ( );
   // hm1.erase ( hm1_cIter );

   hm1_cIter = hm1.begin( );
   cout << "The first element of hm1 is now "
        << hm1_cIter -> first << "." << endl;
}
```

```Output
The first element of hm1 is 0.
The first element of hm1 is now 1.
```

## <a name="hash_mapcbegin"></a><a name="cbegin"></a> hash_map:: cbegin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает итератор const, адресующий первый элемент в hash_map.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Постоянный двунаправленный итератор, адресующий первый элемент в [hash_map](../standard-library/hash-map-class.md) или расположение после пустого `hash_map`.

### <a name="example"></a>Пример

```cpp
// hash_map_cbegin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_iterator hm1_cIter;
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

## <a name="hash_mapcend"></a><a name="cend"></a> hash_map:: cend

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает итератор const, который обращается к месту, следующему за последним элементом в hash_map.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор const, адресующий место, следующее за последним элементом в [hash_map](../standard-library/hash-map-class.md). Если `hash_map` пуст, то `hash_map::cend == hash_map::begin`.

### <a name="remarks"></a>Примечания

`cend` используется для проверки, достиг ли итератор конца своего `hash_map`.

Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_map_cend.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_iterator hm1_cIter;
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

## <a name="hash_mapclear"></a><a name="clear"></a> hash_map:: Clear

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Стирает все элементы в объекте hash_map.

```cpp
void clear();
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена hash_map::clear.

```cpp
// hash_map_clear.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1;
    hash_map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    hm1.insert(Int_Pair(2, 4));

    i = hm1.size();
    cout << "The size of the hash_map is initially "
         << i << "." << endl;

    hm1.clear();
    i = hm1.size();
    cout << "The size of the hash_map after clearing is "
         << i << "." << endl;
}
```

```Output
The size of the hash_map is initially 2.
The size of the hash_map after clearing is 0.
```

## <a name="hash_mapconst_iterator"></a><a name="const_iterator"></a> hash_map:: const_iterator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать **`const`** элемент в hash_map.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_iterator`нельзя использовать для изменения значения элемента.

Объект, `const_iterator` определенный hash_map, указывает на элементы, которые являются объектами [value_type](#value_type), то есть тип `pair< const Key, Type >` , первый элемент которого является ключом элемента, а второй элемент — сопоставленная база данных, удерживаемая элементом.

Для разыменования объекта `const_iterator` `cIter` , указывающего на элемент в hash_map, используйте `->` оператор.

Чтобы получить доступ к значению ключа для элемента, используйте `cIter->first` , что эквивалентно `(*cIter).first` . Чтобы получить доступ к значению сопоставленной версии элемента, используйте `cIter->second` , что эквивалентно `(*cIter).second` .

### <a name="example"></a>Пример

См. пример для [begin](#begin) в качестве примера использования `const_iterator`.

## <a name="hash_mapconst_pointer"></a><a name="const_pointer"></a> hash_map:: const_pointer

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, предоставляющий указатель на **`const`** элемент в hash_map.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Примечания

Тип `const_pointer`нельзя использовать для изменения значения элемента.

В большинстве случаев [iterator](#iterator) должен использоваться для доступа к элементам в объекте hash_map.

## <a name="hash_mapconst_reference"></a><a name="const_reference"></a> hash_map:: const_reference

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в hash_map для чтения и выполнения **`const`** операций.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_reference const_reference;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_map_const_ref.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map<int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( hm1.begin( ) -> first );

   // The following line would cause an error because the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( hm1.begin( ) -> first );

   cout << "The key of the first element in the hash_map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( hm1.begin( ) -> second );

   cout << "The data value of the first element in the hash_map is "
        << Ref2 << "." << endl;
}
```

```Output
The key of the first element in the hash_map is 1.
The data value of the first element in the hash_map is 10.
```

## <a name="hash_mapconst_reverse_iterator"></a><a name="const_reverse_iterator"></a> hash_map:: const_reverse_iterator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать любой **`const`** элемент в hash_map.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse)iterator const_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_reverse_iterator` не может изменять значение элемента и используется для последовательного прохождения через hash_map в обратном направлении.

Объект, `const_reverse_iterator` определенный hash_map, указывает на элементы, которые являются объектами [value_type](#value_type), то есть тип `pair` \< **const Key, Type**> , первый элемент которого является ключом элемента, а второй элемент — сопоставленная база данных, удерживаемая элементом.

Для разыменования `const_reverse_iterator` `crIter`, указывающего на элемент в hash_map, используйте оператор **->**.

Чтобы получить значение ключа элемента, используйте `crIter` -> **first**, который эквивалентен (\* `crIter`) **.first**. Для получения доступа к значению сопоставленных данных элемента используйте `crIter` -> **second**, что эквивалентно (\* `crIter`). **сначала**.

### <a name="example"></a>Пример

См. пример для [rend](#rend) в качестве примера объявления и использования `const_reverse_iterator`.

## <a name="hash_mapcount"></a><a name="count"></a> hash_map:: count

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает число элементов в объекте hash_map, ключ которого совпадает с ключом, заданным параметром.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Значение ключа для сравнения с ключами элементов объекта hash_map.

### <a name="return-value"></a>Возвращаемое значение

1, если объект hash_map содержит элемент, ключ сортировки которого совпадает с ключом параметра. 0, если объект hash_map не содержит ни одного элемента с соответствующим ключом.

### <a name="remarks"></a>Примечания

Функция-член возвращает количество элементов *x* в диапазоне

\[ lower_bound (*ключ*), upper_bound (*ключ*))

— 0 или 1 для hash_map, который является уникальным ассоциативным контейнером.

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена hash_map::count.

```cpp
// hash_map_count.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1;
    hash_map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair (1, 1));
    hm1.insert(Int_Pair (2, 1));
    hm1.insert(Int_Pair (1, 4));
    hm1.insert(Int_Pair (2, 1));

    // Keys must be unique in hash_map, so duplicates are ignored
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
The number of elements in hm1 with a sort key of 1 is: 1.
The number of elements in hm1 with a sort key of 2 is: 1.
The number of elements in hm1 with a sort key of 3 is: 0.
```

## <a name="hash_mapcrbegin"></a><a name="crbegin"></a> hash_map:: crbegin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает итератор const, указывающий на первый элемент в обратном hash_map.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий первый элемент в обратном [hash_map](../standard-library/hash-map-class.md) (или адресующий элемент, ранее бывший последним элементом в `hash_map` до изменения его порядка на обратный).

### <a name="remarks"></a>Примечания

`crbegin` используется с обратным hash_map точно так же, как [begin](#begin) используется с `hash_map`.

Если возвращаемое значение `crbegin`, то объект `hash_map` невозможно изменить.

`crbegin` можно использовать для перебора `hash_map` в обратном порядке.

### <a name="example"></a>Пример

```cpp
// hash_map_crbegin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_crIter = hm1.crbegin( );
   cout << "The first element of the reversed hash_map hm1 is "
        << hm1_crIter -> first << "." << endl;
}
```

```Output
The first element of the reversed hash_map hm1 is 3.
```

## <a name="hash_mapcrend"></a><a name="crend"></a> hash_map:: crend

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает итератор const, который обращается к месту, следующему за последним элементом в обращенном hash_map.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий место после последнего элемента в обратном [hash_map](../standard-library/hash-map-class.md) (расположение перед первым элементом в `hash_map` до изменения его порядка на обратный).

### <a name="remarks"></a>Примечания

`crend` используется с обратным `hash_map` точно так же, как [hash_map::end](#end) используется с `hash_map`.

Если возвращаемое значение `crend`, то объект `hash_map` невозможно изменить.

`crend` используется, чтобы проверить, достиг ли итератор конца `hash_map`.

Значение, возвращаемое `crend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_map_crend.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_crIter = hm1.crend( );
   hm1_crIter--;
   cout << "The last element of the reversed hash_map hm1 is "
        << hm1_crIter -> first << "." << endl;
}
```

```Output
The last element of the reversed hash_map hm1 is 3.
```

## <a name="hash_mapdifference_type"></a><a name="difference_type"></a> hash_map::difference_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип целого числа со знаком, пригодный для представления количества элементов в hash_map в диапазоне между элементами, на которые указывают итераторы.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;
```

### <a name="example"></a>Пример

```cpp
// hash_map_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_map>
#include <algorithm>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 3, 20 ) );

   // The following won't insert, because map keys are unique
   hm1.insert ( Int_Pair ( 2, 30 ) );

   hash_map <int, int>::iterator hm1_Iter, hm1_bIter, hm1_eIter;
   hm1_bIter = hm1.begin( );
   hm1_eIter = hm1.end( );

   // Count the number of elements in a hash_map
   hash_map <int, int>::difference_type  df_count = 0;
   hm1_Iter = hm1.begin( );
   while ( hm1_Iter != hm1_eIter)
   {
      df_count++;
      hm1_Iter++;
   }

   cout << "The number of elements in the hash_map hm1 is: "
        << df_count << "." << endl;

   cout  << "The keys of the mapped elements are:";
   for ( hm1_Iter= hm1.begin( ) ; hm1_Iter!= hm1.end( ) ;
         hm1_Iter++)
      cout << " " << hm1_Iter-> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( hm1_Iter= hm1.begin( ) ; hm1_Iter!= hm1.end( ) ;
         hm1_Iter++)
      cout << " " << hm1_Iter-> second;
   cout << "." << endl;
}
```

```Output
The number of elements in the hash_map hm1 is: 3.
The keys of the mapped elements are: 1 2 3.
The values of the mapped elements are: 10 20 20.
```

## <a name="hash_mapemplace"></a><a name="emplace"></a> hash_map:: emplace

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Вставляет созданный на месте элемент в hash_map.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение, используемое для перемещения, создает элемент для вставки в [hash_map](../standard-library/hash-map-class.md), кроме случаев, когда `hash_map` уже содержит этот элемент (или, в более общем смысле, элемент, ключ которого эквивалентно упорядочен).

### <a name="return-value"></a>Возвращаемое значение

Функция-член `emplace` возвращает пару, компонент bool которой возвращает значение true, если была осуществлена вставка, и false, если `hash_map` уже содержал элемент, ключ которого имел эквивалентное значение порядка, и компонент итератора которой возвращает адрес нового вставленного элемента или адрес местонахождения элемента, если он уже существовал.

Для доступа к компоненту итератора пары `pr`, возвращенной этой функцией-членом, используйте `pr.first` и разыменуйте ее с помощью `*(pr.first)`. Для доступа к **`bool`** компоненту пары, `pr` возвращаемой этой функцией-членом, используйте `pr.second` , и для разыменования этой функции используйте `*(pr.second)` .

### <a name="remarks"></a>Примечания

[hash_map::value_type](#value_type) элемента — это пара, поэтому значением элемента будет упорядоченная пара, первый элемент которой равен значению ключа, а второй — значению данных элемента.

### <a name="example"></a>Пример

```cpp
// hash_map_emplace.cpp
// compile with: /EHsc
#include<hash_map>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, string> hm1;
    typedef pair<int, string> is1(1, "a");

    hm1.emplace(move(is1));
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

## <a name="hash_mapemplace_hint"></a><a name="emplace_hint"></a> hash_map:: emplace_hint

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Вставляет созданный на месте элемент в hash_map с подсказкой о размещении.

```cpp
template <class ValTy>
iterator emplace_hint(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение, используемое для перемещения, создает элемент для вставки в [hash_map](../standard-library/hash-map-class.md), кроме случаев, когда `hash_map` уже содержит этот элемент (или, в более общем смысле, элемент, ключ которого эквивалентно упорядочен).

*_Where*\
Подсказка о месте начала поиска правильной точки вставки.

### <a name="return-value"></a>Возвращаемое значение

Функция-член [hash_multimap::emplace](../standard-library/hash-multimap-class.md#emplace) возвращает итератор, который указывает на позицию вставки нового элемента в `hash_map` или место, где находится существующий элемент с эквивалентным упорядочением.

### <a name="remarks"></a>Примечания

[hash_map::value_type](#value_type) элемента — это пара, поэтому значением элемента будет упорядоченная пара, первый элемент которой равен значению ключа, а второй — значению данных элемента.

Вставка может происходить в постоянном времени, а не в виде логарифмического времени, если точка вставки сразу следует за *_Where*.

### <a name="example"></a>Пример

```cpp
// hash_map_emplace_hint.cpp
// compile with: /EHsc
#include<hash_map>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, string> hm1;
    typedef pair<int, string> is1(1, "a");

    hm1.emplace(hm1.begin(), move(is1));
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

## <a name="hash_mapempty"></a><a name="empty"></a> hash_map:: Empty

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Проверяет, что hash_map пуст.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если hash_map пустой; **`false`** если hash_map не пуста.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_map_empty.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2;

   typedef pair <int, int> Int_Pair;
   hm1.insert ( Int_Pair ( 1, 1 ) );

   if ( hm1.empty( ) )
      cout << "The hash_map hm1 is empty." << endl;
   else
      cout << "The hash_map hm1 is not empty." << endl;

   if ( hm2.empty( ) )
      cout << "The hash_map hm2 is empty." << endl;
   else
      cout << "The hash_map hm2 is not empty." << endl;
}
```

```Output
The hash_map hm1 is not empty.
The hash_map hm2 is empty.
```

## <a name="hash_mapend"></a><a name="end"></a> hash_map:: end

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает итератор, который обращается к месту, следующему за последним элементом в hash_map.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор, адресующий расположение после последнего элемента в hash_map. Если hash_map является пустым, то hash_map::end == hash_map::begin.

### <a name="remarks"></a>Примечания

`end` используется для проверки того, достиг ли итератор конца hash_map.

Значение, возвращаемое `end`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_map_end.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: const_iterator hm1_cIter;
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

## <a name="hash_mapequal_range"></a><a name="equal_range"></a> hash_map:: equal_range

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает пару итераторов соответственно на первый элемент в hash_map с ключом, который больше, чем указанный ключ, и на первый элемент в hash_map с ключом, который больше или равен данному ключу.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Значение ключа аргумента для сравнения с ключом сортировки элемента из hash_map, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Пара итераторов, первый из которых является [lower_bound](#lower_bound) ключа, а второй — [upper_bound](#upper_bound) ключа.

Для доступа к первому итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **сначала** и для разыменования итератора нижней границы используйте \* ( `pr` . **первый**). Для доступа ко второму итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **второй** и для разыменования итератора верхней границы используйте \* ( `pr` . **второй**).

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_map_equal_range.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef hash_map <int, int> IntMap;
   IntMap hm1;
   hash_map <int, int> :: const_iterator hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   pair <IntMap::const_iterator, IntMap::const_iterator> p1, p2;
   p1 = hm1.equal_range( 2 );

   cout << "The lower bound of the element with "
        << "a key of 2 in the hash_map hm1 is: "
        << p1.first -> second << "." << endl;

   cout << "The upper bound of the element with "
        << "a key of 2 in the hash_map hm1 is: "
        << p1.second -> second << "." << endl;

   // Compare the upper_bound called directly
   hm1_RcIter = hm1.upper_bound( 2 );

   cout << "A direct call of upper_bound( 2 ) gives "
        << hm1_RcIter -> second << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 2 )." << endl;

   p2 = hm1.equal_range( 4 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == hm1.end( ) ) && ( p2.second == hm1.end( ) ) )
      cout << "The hash_map hm1 doesn't have an element "
             << "with a key less than 40." << endl;
   else
      cout << "The element of hash_map hm1 with a key >= 40 is: "
           << p1.first -> first << "." << endl;
}
```

```Output
The lower bound of the element with a key of 2 in the hash_map hm1 is: 20.
The upper bound of the element with a key of 2 in the hash_map hm1 is: 30.
A direct call of upper_bound( 2 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 2 ).
The hash_map hm1 doesn't have an element with a key less than 40.
```

## <a name="hash_maperase"></a><a name="erase"></a> hash_map:: Erase

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Удаляет элемент или диапазон элементов в объекте hash_map с заданных позиций или удаляет элементы, соответствующие заданному ключу.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Параметры

*_Where*\
Положение элемента, удаляемого из объекта hash_map.

*first*\
Положение первого элемента, удаляемого из объекта hash_map.

*last*\
Положение сразу после последнего элемента, удаляемого из объекта hash_map.

*раздел*\
Значение ключа элементов, удаляемых из объекта hash_map.

### <a name="return-value"></a>Возвращаемое значение

Для первых двух функций-членов двунаправленный итератор, указывающий на первый элемент, оставшийся после удаления элементов, или на указатель конца объекта hash_map, если такого элемента не существует.

Для третьей функции-члена возвращает число элементов, которые были удалены из объекта hash_map.

### <a name="remarks"></a>Примечания

Функции-члены не создают исключений.

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена hash_map::erase.

```cpp
// hash_map_erase.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1, hm2, hm3;
    hash_map<int, int> :: iterator pIter, Iter1, Iter2;
    int i;
    hash_map<int, int>::size_type n;
    typedef pair<int, int> Int_Pair;

    for (i = 1; i < 5; i++)
    {
        hm1.insert(Int_Pair (i, i));
        hm2.insert(Int_Pair (i, i*i));
        hm3.insert(Int_Pair (i, i-1));
    }

    // The 1st member function removes an element at a given position
    Iter1 = ++hm1.begin();
    hm1.erase(Iter1);

    cout << "After the 2nd element is deleted, the hash_map hm1 is:";
    for (pIter = hm1.begin(); pIter != hm1.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 2nd member function removes elements
    // in the range [ first,  last)
    Iter1 = ++hm2.begin();
    Iter2 = --hm2.end();
    hm2.erase(Iter1, Iter2);

    cout << "After the middle two elements are deleted, "
         << "the hash_map hm2 is:";
    for (pIter = hm2.begin(); pIter != hm2.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 3rd member function removes elements with a given  key
    n = hm3.erase(2);

    cout << "After the element with a key of 2 is deleted,\n"
         << "the hash_map hm3 is:";
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;

    // The 3rd member function returns the number of elements removed
    cout << "The number of elements removed from hm3 is: "
         << n << "." << endl;

    // The dereferenced iterator can also be used to specify a key
    Iter1 = ++hm3.begin();
    hm3.erase(Iter1);

    cout << "After another element with a key equal to that"
         << endl;
    cout  << "of the 2nd element is deleted, "
          << "the hash_map hm3 is:";
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)
        cout << " " << pIter -> second;
    cout << "." << endl;
}
```

```Output
After the 2nd element is deleted, the hash_map hm1 is: 1 3 4.
After the middle two elements are deleted, the hash_map hm2 is: 1 16.
After the element with a key of 2 is deleted,
the hash_map hm3 is: 0 2 3.
The number of elements removed from hm3 is: 1.
After another element with a key equal to that
of the 2nd element is deleted, the hash_map hm3 is: 0 3.
```

## <a name="hash_mapfind"></a><a name="find"></a> hash_map:: Find

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает итератор, адресующий расположение элемента в hash_map с ключом, эквивалентным указанному ключу.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Значение ключа, с которым сравнивается ключ сортировки элемента из hash_map, по которой выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Итератор, адресующий расположение элемента с указанным ключом или расположение после последнего элемента в hash_map, если совпадений для ключа не найдено.

### <a name="remarks"></a>Примечания

`find` Возвращает итератор, который обращается к элементу в hash_map, ключ сортировки которого эквивалентен ключу аргумента в бинарном предикате, который вызывает упорядочивание на основе отношения сравнения "меньше".

Если возвращаемое значение `find` назначается [const_iterator](#const_iterator), то объект hash_map изменить нельзя. Если возвращаемое значение `find` назначается [итератору](#iterator), то объект hash_map можно изменить.

### <a name="example"></a>Пример

```cpp
// hash_map_find.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_RcIter = hm1.find( 2 );
   cout << "The element of hash_map hm1 with a key of 2 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   hm1_RcIter = hm1.find( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_map hm1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of hash_map hm1 with a key of 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // The element at a specific location in the hash_map can be found
   // using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.end( );
   hm1_AcIter--;
   hm1_RcIter = hm1.find( hm1_AcIter -> first );
   cout << "The element of hm1 with a key matching "
        << "that of the last element is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The element of hash_map hm1 with a key of 2 is: 20.
The hash_map hm1 doesn't have an element with a key of 4.
The element of hm1 with a key matching that of the last element is: 30.
```

## <a name="hash_mapget_allocator"></a><a name="get_allocator"></a> hash_map:: get_allocator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает копию объекта-распределителя, используемого для создания hash_map.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Распределитель, используемый hash_map.

### <a name="remarks"></a>Примечания

Распределители для класса hash_map определяют, как этот класс управляет хранилищем. Распределителей по умолчанию в классах контейнеров стандартной библиотеки C++ достаточно для большинства задач программирования. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.

### <a name="example"></a>Пример

```cpp
// hash_map_get_allocator.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int>::allocator_type hm1_Alloc;
   hash_map <int, int>::allocator_type hm2_Alloc;
   hash_map <int, double>::allocator_type hm3_Alloc;
   hash_map <int, int>::allocator_type hm4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   hash_map <int, int> hm1;
   hash_map <int, int> hm2;
   hash_map <int, double> hm3;

   hm1_Alloc = hm1.get_allocator( );
   hm2_Alloc = hm2.get_allocator( );
   hm3_Alloc = hm3.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << hm2.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << hm3.max_size( ) <<  "." << endl;

   // The following line creates a hash_map hm4
   // with the allocator of hash_map hm1.
   hash_map <int, int> hm4( less<int>( ), hm1_Alloc );

   hm4_Alloc = hm4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated with the other
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

## <a name="hash_maphash_map"></a><a name="hash_map"></a> hash_map:: hash_map

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Создает hash_map, который пуст или является копией части или целого другого hash_map.

```cpp
hash_map();

explicit hash_map(
    const Traits& Comp);

hash_map(
    const Traits& Comp,
    const Allocator& Al);

hash_map(
    const hash_map& Right);

hash_map(
    hash_map&& Right);

hash_map(
    initializer_list<Type> IList);hash_map(initializer_list<Type> IList,
    const key_compare& Comp);

hash_map(
    initializer_list<Type> IList,
    const key_compare& Comp,
    const allocator_type& Al);

template <class InputIterator>
hash_map(
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
hash_map(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
hash_map(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al
```

### <a name="parameters"></a>Параметры

*Al*\
Класс распределителя хранилища, используемый для данного объекта hash_map, который по умолчанию имеет значение `Allocator` .

*Соответствовал*\
Функция сравнения типа const `Traits` используется для упорядочения элементов в hash_map, чье значение по умолчанию — `hash_compare`.

*right*\
hash_map, для которой создаваемая схема должна стать копией.

*First*\
Положение первого элемента в диапазоне копируемых элементов.

*last*\
Положение первого элемента после диапазона копируемых элементов.

*Интерфейс*\
initializer_list

### <a name="remarks"></a>Примечания

Все конструкторы хранят тип объекта-распределителя, который управляет хранилищем памяти для hash_map и который позже может быть получен путем вызова [get_allocator](#get_allocator). Параметр-распределитель часто не указывается в объявлениях класса и в макросах предварительной обработки, используемых для замены альтернативных распределителей.

Все конструкторы выполняют инициализацию своих hash_map.

Все конструкторы хранят объект функции типа `Traits`, который используется для установления порядка ключей hash_map и затем может быть возвращен путем вызова [key_comp](#key_comp).

Первые три конструктора указывают пустую начальную hash_map, Кроме того, вторая указывает тип функции сравнения (*comp*), которая будет использоваться при установлении порядка элементов, а третья явно указывает тип распределителя (*Al*) для использования. Ключевое слово **`explicit`** подавляет определенные виды автоматического преобразования типов.

Четвертый конструктор задает копию hash_map *right*.

Следующие три конструктора копируют диапазон `[First, Last)` hash_map с повышением точности при указании типа функции сравнения класса `Traits` и распределителя.

Последний конструктор перемещает hash_map *вправо*.

## <a name="hash_mapinsert"></a><a name="insert"></a> hash_map:: INSERT

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Вставляет элемент или диапазон элементов в hash_map.

```cpp
pair <iterator, bool> insert(
    const value_type& val);

iterator insert(
    const_iterator _Where,
    const value_type& val);

template <class InputIterator>
void insert(
    InputIterator first,
    InputIterator last);

template <class ValTy>
pair <iterator, bool>
insert(
    ValTy&& val);

template <class ValTy>
iterator insert(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение элемента для вставки в hash_map, кроме случаев, когда hash_map уже содержит этот элемент (или, в более общем смысле, элемент, ключ которого эквивалентно упорядочен).

*_Where*\
Подсказка о месте начала поиска правильной точки вставки.

*first*\
Позиция первого элемента, который следует скопировать из hash_map.

*last*\
Позиция непосредственно перед последним элементом, который следует скопировать из hash_map.

### <a name="return-value"></a>Возвращаемое значение

Первая `insert` функция-член возвращает пару, компонент bool которой возвращает значение true, если была произведена вставка, и значение false, если hash_map уже содержал элемент, ключ которого имел эквивалентное значение в упорядочении, а компонент итератора возвращает адрес, куда был вставлен новый элемент, или место, где элемент уже был найден.

Для доступа к компоненту итератора пары `pr`, возвращенной этой функцией-членом, используйте `pr`. во- **первых**, и для их разыменования используйте \* ( `pr` . **первый**). Для доступа к **`bool`** компоненту пары `pr` , возвращаемой этой функцией-членом, используйте `pr` . **во-вторых**, и для разыменования, используйте \* ( `pr` . **второй**).

Вторая `insert` функция члена, версия подсказки, возвращает итератор, указывающий на позицию вставки нового элемента в hash_map.

Последние две `insert` функции члена ведут себя так же, как первые два, за исключением того, что они перемещают конструкцию вставленного значения.

### <a name="remarks"></a>Примечания

[value_type](../standard-library/map-class.md#value_type) элемента — это pair, поэтому значением элемента будет упорядоченная пара, первый компонент которой равен значению ключа, а второй — значению данных элемента.

Вставка может выполняться в периодической константе для указания версии подсказки INSERT, а не логарифмического времени, если точка вставки сразу же следует за *_Where*.

Четвертая функция-член вставляет последовательность значений элемента в hash_map, соответствующую каждому элементу, указанному итератором, в диапазоне *[First, Last)* указанного набора.

### <a name="example"></a>Пример

```cpp
// hash_map_insert.cpp
// compile with: /EHsc
#include<hash_map>
#include<iostream>
#include <string>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int>::iterator hm1_pIter, hm2_pIter;

    hash_map<int, int> hm1, hm2;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 10));
    hm1.insert(Int_Pair(2, 20));
    hm1.insert(Int_Pair(3, 30));
    hm1.insert(Int_Pair(4, 40));

    cout << "The original elements (Key => Value) of hm1 are:";
    for (hm1_pIter = hm1.begin(); hm1_pIter != hm1.end(); hm1_pIter++)
        cout << endl << " " << hm1_pIter -> first << " => "
             << hm1_pIter->second;
    cout << endl;

    pair< hash_map<int,int>::iterator, bool > pr;
    pr = hm1.insert(Int_Pair(1, 10));

    if (pr.second == true)
    {
        cout << "The element 10 was inserted in hm1 successfully."
            << endl;
    }
    else
    {
        cout << "The element 10 already exists in hm1\n"
            << "with a key value of "
            << "((pr.first) -> first) = " << (pr.first)->first
            << "." << endl;
    }

    // The hint version of insert
    hm1.insert(--hm1.end(), Int_Pair(5, 50));

    cout << "After the insertions, the elements of hm1 are:";
    for (hm1_pIter = hm1.begin(); hm1_pIter != hm1.end(); hm1_pIter++)
        cout << endl << hm1_pIter -> first << " => "
             << hm1_pIter->second;
    cout << endl;

    hm2.insert(Int_Pair(10, 100));

    // The templatized version inserting a range
    hm2.insert( ++hm1.begin(), --hm1.end() );

    cout << "After the insertions, the elements of hm2 are:";
    for (hm2_pIter = hm2.begin(); hm2_pIter != hm2.end(); hm2_pIter++)
        cout << endl << hm2_pIter -> first << " => "
             << hm2_pIter->second;
    cout << endl;

    // The templatized versions move constructing elements
    hash_map<int, string> hm3, hm4;
    pair<int, string> is1(1, "a"), is2(2, "b");

    hm3.insert(move(is1));
    cout << "After the move insertion, hm3 contains:" << endl
      << hm3.begin()->first
      << " => " << hm3.begin()->second
      << endl;

    hm4.insert(hm4.begin(), move(is2));
    cout << "After the move insertion, hm4 contains:" << endl
      << hm4.begin()->first
      << " => " << hm4.begin()->second
      << endl;
}
```

```Output
The original elements (Key => Value) of hm1 are:
1 => 10
2 => 20
3 => 30
4 => 40
The element 10 already exists in hm1
with a key value of ((pr.first) -> first) = 1.
After the insertions, the elements of hm1 are:
1 => 10
2 => 20
3 => 30
4 => 40
5 => 50
After the insertions, the elements of hm2 are:
2 => 20
10 => 100
3 => 30
4 => 40
After the move insertion, hm3 contains:
1 => a
After the move insertion, hm4 contains:
2 => b
```

## <a name="hash_mapiterator"></a><a name="iterator"></a> hash_map:: итератор

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, предоставляющий двунаправленный итератор, который может считывать или изменять любой элемент в hash_map.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Примечания

Объект, `iterator` определенный hash_map, указывает на элементы, которые являются объектами [value_type](#value_type), то есть тип `pair<const Key, Type>` , первый элемент которого является ключом элемента, а второй элемент — сопоставленная база данных, удерживаемая элементом.

Для разыменования итератора с именем `Iter` , указывающего на элемент в multimap, используйте `->` оператор.

Чтобы получить доступ к значению ключа для элемента, используйте `Iter->first` , что эквивалентно `(*Iter).first` . Чтобы получить доступ к значению сопоставленной версии элемента, используйте `Iter->second` , что эквивалентно `(*Iter).second` .

Тип `iterator` можно использовать для изменения значения элемента.

### <a name="example"></a>Пример

См. пример для [Begin](#begin) в качестве примера объявления и использования `iterator` .

## <a name="hash_mapkey_comp"></a><a name="key_comp"></a> hash_map:: key_comp

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Извлекает копию объекта сравнения, который используется для упорядочивания ключей в hash_map.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект функции, который hash_map использует для упорядочения своих элементов.

### <a name="remarks"></a>Примечания

Хранимый объект определяет функцию-член

`bool operator( const Key& left, const Key&right );`

, который возвращает, **`true`** Если `left` предшествует и не равно `right` в порядке сортировки.

### <a name="example"></a>Пример

```cpp
// hash_map_key_comp.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_map <int, int, hash_compare<int, less<int> > > hm1;
   hash_map <int, int, hash_compare<int, less<int> > >::key_compare
      kc1 = hm1.key_comp( ) ;

   // Operator stored in kc1 tests order & returns bool value
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true,"
           << "\n where kc1 is the function object of hm1"
           << " of type key_compare." << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false"
           << "\n where kc1 is the function object of hm1"
           << " of type key_compare." << endl;
   }

   hash_map <int, int, hash_compare<int, greater<int> > > hm2;
   hash_map <int, int, hash_compare<int, greater<int> > >
      ::key_compare kc2 = hm2.key_comp( );

   // Operator stored in kc2 tests order & returns bool value
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true,"
           << "\n where kc2 is the function object of hm2"
           << " of type key_compare." << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false,"
           << "\n where kc2 is the function object of hm2"
           << " of type key_compare." << endl;
   }
}
```

## <a name="hash_mapkey_compare"></a><a name="key_compare"></a> hash_map:: key_compare

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, предоставляющий объект функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в схеме.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Примечания

`key_compare` является синонимом для параметра-шаблона `Traits`.

Дополнительные сведения о `Traits` см. в разделе [Класс hash_map](../standard-library/hash-map-class.md).

### <a name="example"></a>Пример

См. пример для [key_comp](#key_comp) в качестве примера объявления и использования `key_compare`.

## <a name="hash_mapkey_type"></a><a name="key_type"></a> hash_map:: key_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип описывает объект ключа сортировки, составляющий каждый элемент в hash_map.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Примечания

`key_type` является синонимом для параметра-шаблона `Key`.

Дополнительные сведения о `Key` см. в подразделе "Примечания" раздела [Класс hash_map](../standard-library/hash-map-class.md).

### <a name="example"></a>Пример

См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_type`.

## <a name="hash_maplower_bound"></a><a name="lower_bound"></a> hash_map:: lower_bound

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает итератор, указывающий на первый элемент в hash_map со значением ключа, которое больше или равно значению указанного ключа.

```cpp
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Значение ключа аргумента для сравнения с ключом сортировки элемента из hash_map, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

[iterator](#iterator) или [const_iterator](#const_iterator), адресующий расположение элемента в hash_map с ключом, который равен или больше, чем ключ аргумента, или адресующий расположение после последнего элемента в hash_map, если совпадение для ключа не найдено.

Если возвращаемое значение `lower_bound` назначено `const_iterator`, объект hash_map изменить нельзя. Если возвращаемое значение `lower_bound` присваивается `iterator` , то объект hash_map можно изменить.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_map_lower_bound.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_RcIter = hm1.lower_bound( 2 );
   cout << "The first element of hash_map hm1 with a key of 2 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end( ) is returned
   hm1_RcIter = hm1. lower_bound ( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_map hm1 doesn't have an element "
           << "with a key of 4." << endl;
   else
      cout << "The element of hash_map hm1 with a key of 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // An element at a specific location in the hash_map can be
   // found using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.end( );
   hm1_AcIter--;
   hm1_RcIter = hm1. lower_bound ( hm1_AcIter -> first );
   cout << "The element of hm1 with a key matching "
        << "that of the last element is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The first element of hash_map hm1 with a key of 2 is: 20.
The hash_map hm1 doesn't have an element with a key of 4.
The element of hm1 with a key matching that of the last element is: 30.
```

## <a name="hash_mapmapped_type"></a><a name="mapped_type"></a> hash_map:: mapped_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, представляющий тип данных, хранящийся в hash_map.

```cpp
typedef Type mapped_type;
```

### <a name="remarks"></a>Примечания

Тип `mapped_type` является синонимом для параметра-шаблона `Type`.

Дополнительные сведения о `Type` см. в разделе [Класс hash_map](../standard-library/hash-map-class.md).

### <a name="example"></a>Пример

См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_type`.

## <a name="hash_mapmax_size"></a><a name="max_size"></a> hash_map:: max_size

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает максимальную длину hash_map.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимально возможная длина hash_map.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_map_max_size.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: size_type i;

   i = hm1.max_size( );
   cout << "The maximum possible length "
        << "of the hash_map is " << i << "."
        << endl << "(Magnitude is machine specific.)";
}
```

## <a name="hash_mapoperator"></a><a name="op_at"></a> hash_map::operator[]

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Вставляет элемент в `hash_map` с заданным значением ключа.

```cpp
Type& operator[](const Key& key);

Type& operator[](Key&& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключевое значение элемента для вставки.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на значение данных вставленного элемента.

### <a name="remarks"></a>Примечания

Если значение ключа аргумента не найдено, он вставляется вместе со значением по умолчанию для такого типа данных.

`operator[]` может использоваться для вставки элементов в `hash_map m` с помощью

`m[ key] = DataValue`;

где значение типа данных — это значение `mapped_type` элемента с ключевым значением *Key*.

При использовании `operator[]` для вставки элементов возвращаемая ссылка не указывает, меняет ли вставка уже существующий элемент или создает новый. Функции-члены [find](../standard-library/map-class.md#find) и [insert](../standard-library/map-class.md#insert) можно использовать для определения наличия элемента с указанным ключом перед вставкой.

### <a name="example"></a>Пример

```cpp
// hash_map_op_ref.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef pair <const int, int> cInt2Int;
   hash_map <int, int> hm1;
   hash_map <int, int> :: iterator pIter;

   // Insert a data value of 10 with a key of 1
   // into a hash_map using the operator[] member function
   hm1[ 1 ] = 10;

   // Compare other ways to insert objects into a hash_map
   hm1.insert ( hash_map <int, int> :: value_type ( 2, 20 ) );
   hm1.insert ( cInt2Int ( 3, 30 ) );

   cout  << "The keys of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

   // If the key already exists, operator[]
   // changes the value of the datum in the element
   hm1[ 2 ] = 40;

   // operator[] will also insert the value of the data
   // type's default constructor if the value is unspecified
   hm1[5];

   cout  << "The keys of the mapped elements are now:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> first;
   cout << "." << endl;

   cout  << "The values of the mapped elements are now:";
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )
      cout << " " << pIter -> second;
   cout << "." << endl;

   // operator[] will also insert by moving a key
   hash_map <string, int> hm2;
   string str("a");
   hm2[move(str)] = 1;
   cout << "The moved key is " << hm2.begin()->first
      << ", with value " << hm2.begin()->second << endl;
}
```

## <a name="hash_mapoperator"></a><a name="op_eq"></a> hash_map::operator=

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Заменяет элементы hash_map копией другого hash_map.

```cpp
hash_map& operator=(const hash_map& right);

hash_map& operator=(hash_map&& right);
```

### <a name="parameters"></a>Параметры

*right*\
[Класс hash_map](../standard-library/hash-map-class.md), который копируется в `hash_map`.

### <a name="remarks"></a>Примечания

После стирания любых существующих элементов в `hash_map` , `operator=` копирует или перемещает содержимое *непосредственно* в `hash_map` .

### <a name="example"></a>Пример

```cpp
// hash_map_operator_as.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map<int, int> v1, v2, v3;
   hash_map<int, int>::iterator iter;

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

## <a name="hash_mappointer"></a><a name="pointer"></a> hash_map::p оинтер

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, предоставляющий указатель на элемент в hash_map.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Примечания

Тип `pointer` можно использовать для изменения значения элемента.

В большинстве случаев [iterator](#iterator) должен использоваться для доступа к элементам в объекте hash_map.

## <a name="hash_maprbegin"></a><a name="rbegin"></a> hash_map:: rbegin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает итератор, адресующий первый элемент в обратном hash_map.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий первый элемент в обратном hash_map или адресующий элемент, ранее бывший последним элементом в hash_map до изменения его порядка на обратный.

### <a name="remarks"></a>Примечания

`rbegin` используется с обратным hash_map точно так же, как [begin](#begin) используется с hash_map.

Если возвращаемое значение `rbegin` назначено для [const_reverse_iterator](#const_reverse_iterator), то объект hash_map изменить нельзя. Если возвращаемое значение `rbegin` назначено для [reverse_iterator](#reverse_iterator), то объект hash_map изменить можно.

`rbegin` можно использовать для прохода по hash_map в обратную сторону.

### <a name="example"></a>Пример

```cpp
// hash_map_rbegin.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: reverse_iterator hm1_rIter;
   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_rIter = hm1.rbegin( );
   cout << "The first element of the reversed hash_map hm1 is "
        << hm1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a hash_map in a forward order
   cout << "The hash_map is: ";
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( ); hm1_Iter++)
      cout << hm1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a hash_map in a reverse order
   cout << "The reversed hash_map is: ";
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( ); hm1_rIter++)
      cout << hm1_rIter -> first << " ";
      cout << "." << endl;

   // A hash_map element can be erased by dereferencing to its key
   hm1_rIter = hm1.rbegin( );
   hm1.erase ( hm1_rIter -> first );

   hm1_rIter = hm1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed hash_map is "
        << hm1_rIter -> first << "." << endl;
}
```

```Output
The first element of the reversed hash_map hm1 is 3.
The hash_map is: 1 2 3 .
The reversed hash_map is: 3 2 1 .
After the erasure, the first element in the reversed hash_map is 2.
```

## <a name="hash_mapreference"></a><a name="reference"></a> hash_map:: Reference

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, предоставляющий ссылку на элемент, хранящийся в hash_map.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::reference reference;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_map_reference.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );

   // Declare and initialize a const_reference &Ref1
   // to the key of the first element
   const int &Ref1 = ( hm1.begin( ) -> first );

   // The following line would cause an error as the
   // non-const_reference cannot be used to access the key
   // int &Ref1 = ( hm1.begin( ) -> first );

   cout << "The key of first element in the hash_map is "
        << Ref1 << "." << endl;

   // Declare and initialize a reference &Ref2
   // to the data value of the first element
   int &Ref2 = ( hm1.begin( ) -> second );

   cout << "The data value of first element in the hash_map is "
        << Ref2 << "." << endl;

   // The non-const_reference can be used to modify the
   // data value of the first element
   Ref2 = Ref2 + 5;
   cout << "The modified data value of first element is "
        << Ref2 << "." << endl;
}
```

```Output
The key of first element in the hash_map is 1.
The data value of first element in the hash_map is 10.
The modified data value of first element is 15.
```

## <a name="hash_maprend"></a><a name="rend"></a> hash_map:: rend

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает итератор, адресующий расположение после последнего элемента в обратном hash_map.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий место после последнего элемента в обратном hash_map (расположение перед первым элементом в hash_map до изменения его порядка на обратный).

### <a name="remarks"></a>Примечания

`rend` используется с обратным hash_map точно так же, как [end](#end) используется с hash_map.

Если возвращаемое значение `rend` назначено для [const_reverse_iterator](#const_reverse_iterator), то объект hash_map изменить нельзя. Если возвращаемое значение `rend` назначено для [reverse_iterator](#reverse_iterator), то объект hash_map изменить можно.

`rend` используется, чтобы проверить, достиг ли обратный итератор конца hash_map.

Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_map_rend.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;

   hash_map <int, int> :: iterator hm1_Iter;
   hash_map <int, int> :: reverse_iterator hm1_rIter;
   hash_map <int, int> :: const_reverse_iterator hm1_crIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_rIter = hm1.rend( );
   hm1_rIter--;
   cout << "The last element of the reversed hash_map hm1 is "
        << hm1_rIter -> first << "." << endl;

   // begin can be used to start an iteration
   // through a hash_map in a forward order
   cout << "The hash_map is: ";
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( );
   hm1_Iter++)
      cout << hm1_Iter -> first << " ";
      cout << "." << endl;

   // rbegin can be used to start an iteration
   // through a hash_map in a reverse order
   cout << "The reversed hash_map is: ";
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( );
      hm1_rIter++)
      cout << hm1_rIter -> first << " ";
      cout << "." << endl;

   // A hash_map element can be erased by dereferencing to its key
   hm1_rIter = --hm1.rend( );
   hm1.erase ( hm1_rIter -> first );

   hm1_rIter = hm1.rend( );
   hm1_rIter--;
   cout << "After the erasure, the last element "
        << "in the reversed hash_map is "
        << hm1_rIter -> first << "." << endl;
}
```

```Output
The last element of the reversed hash_map hm1 is 1.
The hash_map is: 1 2 3 .
The reversed hash_map is: 3 2 1 .
After the erasure, the last element in the reversed hash_map is 2.
```

## <a name="hash_mapreverse_iterator"></a><a name="reverse_iterator"></a> hash_map:: reverse_iterator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, предоставляющий двунаправленный итератор, который может считывать или изменять элемент в обращенном hash_map.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `reverse_iterator` не может изменять значение элемента и используется для последовательного прохождения через hash_map в обратном направлении.

Объект, `reverse_iterator` определенный hash_map, указывает на элементы, которые являются объектами [value_type](#value_type), то есть **парой \<const Key, Type> **типа, первый элемент которой является ключом элемента, а второй элемент — сопоставленная база данных, удерживаемая элементом.

Для разыменования `reverse_iterator` `rIter`, указывающего на элемент в hash_map, используйте оператор ->.

Для получения доступа к значению ключа для элемента используйте `rIter` -> **first**, что эквивалентно (\* `rIter`). **сначала**. Для получения доступа к значению сопоставленных данных элемента используйте `rIter` -> **second**, что эквивалентно (\* `rIter`). **сначала**.

### <a name="example"></a>Пример

См. пример для [rbegin](#rbegin) в качестве примера объявления и использования `reverse_iterator`.

## <a name="hash_mapsize"></a><a name="size"></a> hash_map:: size

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает число элементов в hash_map.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая длина hash_map.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

В следующем примере иллюстрируется использование функции-члена hash_map::size.

```cpp
// hash_map_size.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_map<int, int> hm1, hm2;
    hash_map<int, int>::size_type i;
    typedef pair<int, int> Int_Pair;

    hm1.insert(Int_Pair(1, 1));
    i = hm1.size();
    cout << "The hash_map length is " << i << "." << endl;

    hm1.insert(Int_Pair(2, 4));
    i = hm1.size();
    cout << "The hash_map length is now " << i << "." << endl;
}
```

```Output
The hash_map length is 1.
The hash_map length is now 2.
```

## <a name="hash_mapsize_type"></a><a name="size_type"></a> hash_map:: size_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип целого числа без знака, который может представлять число элементов в hash_map.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

См. пример для [size](#size) в качестве примера объявления и использования `size_type`

## <a name="hash_mapswap"></a><a name="swap"></a> hash_map:: swap

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Меняет местами элементы двух hash_map.

```cpp
void swap(hash_map& right);
```

### <a name="parameters"></a>Параметры

*right*\
hash_map аргументов, предоставляющий элементы, которые следует поменять местами с целевой hash_map.

### <a name="remarks"></a>Примечания

Функция-член не делает недействительным ссылки, указатели или итераторы, обозначающие элементы в двух hash_map, для которых выполняется обмен элементами.

### <a name="example"></a>Пример

```cpp
// hash_map_swap.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   hash_map <int, int>::iterator hm1_Iter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );
   hm2.insert ( Int_Pair ( 10, 100 ) );
   hm2.insert ( Int_Pair ( 20, 200 ) );
   hm3.insert ( Int_Pair ( 30, 300 ) );

   cout << "The original hash_map hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout   << "." << endl;

   // This is the member function version of swap
   // hm2 is said to be the argument hash_map;
   // hm1 is said to be the target hash_map
   hm1.swap( hm2 );

   cout << "After swapping with hm2, hash_map hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( hm1, hm3 );

   cout << "After swapping with hm3, hash_map hm1 is:";
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )
      cout << " " << hm1_Iter -> second;
   cout   << "." << endl;
}
```

```Output
The original hash_map hm1 is: 10 20 30.
After swapping with hm2, hash_map hm1 is: 100 200.
After swapping with hm3, hash_map hm1 is: 300.
```

## <a name="hash_mapupper_bound"></a><a name="upper_bound"></a> hash_map:: upper_bound

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает итератор, указывающий на первый элемент в hash_map со значением ключа, которое больше указанного ключа.

```cpp
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Значение ключа аргумента для сравнения со значением ключа сортировки элемента из hash_map, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

[iterator](#iterator) или [const_iterator](#const_iterator), адресующий расположение элемента в hash_map с ключом, который больше, чем ключ аргумента, или адресующий расположение после последнего элемента в hash_map, если совпадение для ключа не найдено.

Если для `const_iterator` назначено возвращаемое значение, объект hash_map изменить нельзя. Если возвращаемое значение присвоено `iterator` , то объект hash_map можно изменить.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_map_upper_bound.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1;
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;
   typedef pair <int, int> Int_Pair;

   hm1.insert ( Int_Pair ( 1, 10 ) );
   hm1.insert ( Int_Pair ( 2, 20 ) );
   hm1.insert ( Int_Pair ( 3, 30 ) );

   hm1_RcIter = hm1.upper_bound( 2 );
   cout << "The first element of hash_map hm1 with a key "
        << "greater than 2 is: "
        << hm1_RcIter -> second << "." << endl;

   // If no match is found for the key, end is returned
   hm1_RcIter = hm1. upper_bound ( 4 );

   if ( hm1_RcIter == hm1.end( ) )
      cout << "The hash_map hm1 doesn't have an element "
           << "with a key greater than 4." << endl;
   else
      cout << "The element of hash_map hm1 with a key > 4 is: "
           << hm1_RcIter -> second << "." << endl;

   // The element at a specific location in the hash_map can be found
   // using a dereferenced iterator addressing the location
   hm1_AcIter = hm1.begin( );
   hm1_RcIter = hm1. upper_bound ( hm1_AcIter -> first );
   cout << "The 1st element of hm1 with a key greater than that\n"
        << "of the initial element of hm1 is: "
        << hm1_RcIter -> second << "." << endl;
}
```

```Output
The first element of hash_map hm1 with a key greater than 2 is: 30.
The hash_map hm1 doesn't have an element with a key greater than 4.
The 1st element of hm1 with a key greater than that
of the initial element of hm1 is: 20.
```

## <a name="hash_mapvalue_comp"></a><a name="value_comp"></a> hash_map:: value_comp

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Возвращает объект функции, который определяет порядок элементов в hash_map путем сравнения их значений ключей.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект функции сравнения, который hash_map использует для упорядочения своих элементов.

### <a name="remarks"></a>Примечания

Для hash_map *m*, если два элемента *E1* (*K1*, *D1*) и *e2* (*априорной оценкой K2*, *D2*) являются объектами типа [value_type](#value_type), где *k1* и *априорной оценкой K2* — это ключи типа [key_type](#key_type) , а *D1* и *D2* — их данные типа [mapped_type](#mapped_type), то `m.value_comp()(e1, e2)` он эквивалентен `m.key_comp()(k1, k2)` . Хранимый объект определяет функцию-член

`bool operator(value_type& left, value_type& right);`

Возвращает, **`true`** Если значение ключа `left` предшествует значению ключа в порядке сортировки и не равно ему `right` .

### <a name="example"></a>Пример

```cpp
// hash_map_value_comp.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_map <int, int, hash_compare<int, less<int> > > hm1;
   hash_map <int, int, hash_compare<int, less<int> > >
   ::value_compare vc1 = hm1.value_comp( );
   pair< hash_map<int,int>::iterator, bool > pr1, pr2;

   pr1= hm1.insert ( hash_map <int, int> :: value_type ( 1, 10 ) );
   pr2= hm1.insert ( hash_map <int, int> :: value_type ( 2, 5 ) );

   if( vc1( *pr1.first, *pr2.first ) == true )
   {
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."
           << endl;
   }
   else
   {
      cout << "The element ( 1,10 ) does not precede the element ( 2,5 )."
           << endl;
   }

   if( vc1 ( *pr2.first, *pr1.first ) == true )
   {
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."
           << endl;
   }
   else
   {
      cout << "The element ( 2,5 ) does not precede the element ( 1,10 )."
           << endl;
   }
}
```

## <a name="hash_mapvalue_type"></a><a name="value_type"></a> hash_map:: value_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_map](../standard-library/unordered-map-class.md).

Тип, представляющий тип объекта, который хранится в hash_map.

```cpp
typedef pair<const Key, Type> value_type;
```

### <a name="remarks"></a>Примечания

`value_type` объявляется `pair<const key_type, mapped_type>` как, а не из- `pair<key_type, mapped_type>` за того, что ключи ассоциативного контейнера не могут быть изменены с помощью неконстантного итератора или ссылки.

### <a name="example"></a>Пример

```cpp
// hash_map_value_type.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef pair <const int, int> cInt2Int;
   hash_map <int, int> hm1;
   hash_map <int, int> :: key_type key1;
   hash_map <int, int> :: mapped_type mapped1;
   hash_map <int, int> :: value_type value1;
   hash_map <int, int> :: iterator pIter;

   // value_type can be used to pass the correct type
   // explicitly to avoid implicit type conversion
   hm1.insert ( hash_map <int, int> :: value_type ( 1, 10 ) );

   // Compare other ways to insert objects into a hash_map
   hm1.insert ( cInt2Int ( 2, 20 ) );
   hm1[ 3 ] = 30;

   // Initializing key1 and mapped1
   key1 = ( hm1.begin( ) -> first );
   mapped1 = ( hm1.begin( ) -> second );

   cout << "The key of first element in the hash_map is "
        << key1 << "." << endl;

   cout << "The data value of first element in the hash_map is "
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
The key of first element in the hash_map is 1.
The data value of first element in the hash_map is 10.
The keys of the mapped elements are: 1 2 3.
The values of the mapped elements are: 10 20 30.
```

## <a name="see-also"></a>См. также

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
