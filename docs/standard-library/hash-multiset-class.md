---
title: Класс hash_multiset
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_multiset
- hash_set/stdext::hash_multiset::allocator_type
- hash_set/stdext::hash_multiset::const_iterator
- hash_set/stdext::hash_multiset::const_pointer
- hash_set/stdext::hash_multiset::const_reference
- hash_set/stdext::hash_multiset::const_reverse_iterator
- hash_set/stdext::hash_multiset::difference_type
- hash_set/stdext::hash_multiset::iterator
- hash_set/stdext::hash_multiset::key_compare
- hash_set/stdext::hash_multiset::key_type
- hash_set/stdext::hash_multiset::pointer
- hash_set/stdext::hash_multiset::reference
- hash_set/stdext::hash_multiset::reverse_iterator
- hash_set/stdext::hash_multiset::size_type
- hash_set/stdext::hash_multiset::value_compare
- hash_set/stdext::hash_multiset::value_type
- hash_set/stdext::hash_multiset::begin
- hash_set/stdext::hash_multiset::cbegin
- hash_set/stdext::hash_multiset::cend
- hash_set/stdext::hash_multiset::clear
- hash_set/stdext::hash_multiset::count
- hash_set/stdext::hash_multiset::crbegin
- hash_set/stdext::hash_multiset::crend
- hash_set/stdext::hash_multiset::emplace
- hash_set/stdext::hash_multiset::emplace_hint
- hash_set/stdext::hash_multiset::empty
- hash_set/stdext::hash_multiset::end
- hash_set/stdext::hash_multiset::equal_range
- hash_set/stdext::hash_multiset::erase
- hash_set/stdext::hash_multiset::find
- hash_set/stdext::hash_multiset::get_allocator
- hash_set/stdext::hash_multiset::insert
- hash_set/stdext::hash_multiset::key_comp
- hash_set/stdext::hash_multiset::lower_bound
- hash_set/stdext::hash_multiset::max_size
- hash_set/stdext::hash_multiset::rbegin
- hash_set/stdext::hash_multiset::rend
- hash_set/stdext::hash_multiset::size
- hash_set/stdext::hash_multiset::swap
- hash_set/stdext::hash_multiset::upper_bound
- hash_set/stdext::hash_multiset::value_comp
helpviewer_keywords:
- stdext::hash_multiset
- stdext::hash_multiset::allocator_type
- stdext::hash_multiset::const_iterator
- stdext::hash_multiset::const_pointer
- stdext::hash_multiset::const_reference
- stdext::hash_multiset::const_reverse_iterator
- stdext::hash_multiset::difference_type
- stdext::hash_multiset::iterator
- stdext::hash_multiset::key_compare
- stdext::hash_multiset::key_type
- stdext::hash_multiset::pointer
- stdext::hash_multiset::reference
- stdext::hash_multiset::reverse_iterator
- stdext::hash_multiset::size_type
- stdext::hash_multiset::value_compare
- stdext::hash_multiset::value_type
- stdext::hash_multiset::begin
- stdext::hash_multiset::cbegin
- stdext::hash_multiset::cend
- stdext::hash_multiset::clear
- stdext::hash_multiset::count
- stdext::hash_multiset::crbegin
- stdext::hash_multiset::crend
- stdext::hash_multiset::emplace
- stdext::hash_multiset::emplace_hint
- stdext::hash_multiset::empty
- stdext::hash_multiset::end
- stdext::hash_multiset::equal_range
- stdext::hash_multiset::erase
- stdext::hash_multiset::find
- stdext::hash_multiset::get_allocator
- stdext::hash_multiset::insert
- stdext::hash_multiset::key_comp
- stdext::hash_multiset::lower_bound
- stdext::hash_multiset::max_size
- stdext::hash_multiset::rbegin
- stdext::hash_multiset::rend
- stdext::hash_multiset::size
- stdext::hash_multiset::swap
- stdext::hash_multiset::upper_bound
- stdext::hash_multiset::value_comp
ms.assetid: 0580397a-a76e-40ad-aea2-5c6f3a9d0a21
ms.openlocfilehash: d4722a9c535207b21098db4e33810340d99e6b6a
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561444"
---
# <a name="hash_multiset-class"></a>Класс hash_multiset

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Контейнерный класс hash_multiset является расширением стандартной библиотеки C++. Он используется для хранения и быстрого извлечения данных из коллекции, в которой значения хранящихся элементов выступают в роли ключевых значений и не обязательно должны быть уникальными.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Key, class Traits =hash_compare<Key, less <Key>>, class Allocator =allocator <Key>>
class hash_multiset
```

### <a name="parameters"></a>Параметры

*Раздел*\
Тип данных элемента, который необходимо сохранить в hash_multiset.

*Traits*\
Тип, включающий два объекта функции, один из классов Compare, который является бинарным предикатом, способен сравнивать два значения элементов как ключи сортировки для определения их относительного порядка, а также хэш-функцию, которая является унарным предикатом, сопоставленным ключевым значениям для элементов с целыми числами без знака типа `size_t` . Этот аргумент является необязательным, и в качестве значения по умолчанию используется `hash_compare<Key, less<Key> >`.

*Allocator*\
Тип, представляющий сохраненный объект распределителя, который инкапсулирует сведения о выделении и освобождении памяти для hash_multiset. Этот аргумент является необязательным, и в качестве значения по умолчанию используется `allocator<Key>`.

## <a name="remarks"></a>Примечания

hash_multiset представляет собой следующее:

- Ассоциативный контейнер, который является контейнером переменного размера, поддерживающим эффективное получение значений элементов на основе значения соответствующего ключа. Кроме того, это простой ассоциативный контейнер, поскольку его значения элементов являются значениями его ключей.

- Является реверсивным, поскольку предоставляет двунаправленный итератор для получения доступа к его элементам.

- Хэшируется, поскольку его элементы группируются в сегменты на основе значения хэш-функции, применяемой к значениям ключей элементов.

- Является уникальным, поскольку каждый его элемент должен обладать уникальным ключом. Поскольку hash_multiset также является простым ассоциативным контейнером, его элементы также уникальны.

- Шаблон класса, поскольку предоставляемые им функции являются универсальными и поэтому не зависят от конкретного типа данных, содержащихся в качестве элементов или ключей. Типы данных, используемые для элементов и ключей, вместо этого определяются как параметры в шаблоне класса вместе с функцией и распределителем сравнения.

Главным преимуществом хэширования по сравнению с сортировкой является большая эффективность: успешное хэширование выполняет вставки, удаления и поиск с постоянным средним временем, в то время как время для методик сортировки пропорционально логарифму числа элементов в контейнере. Значение элемента в наборе нельзя изменить напрямую. Вместо этого старые значения необходимо удалить и вставить элементы с новыми значениями.

Выбор типа контейнера должен в общем случае производиться на основе типа поиска и вставки, который требуется приложению. Хэшированные ассоциативные контейнеры оптимизированы для операций поиска, вставки и удаления. Функции-члены, которые явно поддерживают эти операции, эффективны при использовании совместно с правильно разработанной хэш-функцией, в результате чего они имеют постоянное среднее время выполнения и не зависят от числа элементов в контейнере. Правильно разработанная хэш-функция обеспечивает равномерное распределение хэшированных значений и сводит к минимуму количество конфликтов, когда разные значения ключей сопоставляются с одним хэшированным значением. В худшем случае, когда применяется наиболее неоптимальная хэш-функция, количество операций пропорционально количеству элементов в последовательности (линейное время).

hash_multiset рекомендуется использовать в качестве ассоциативного контейнера, если условия, ассоциирующие значения с ключами, удовлетворяются приложением. Элементы hash_multiset могут быть множественными и служить своими собственными ключами сортировки, поэтому ключи не являются уникальными. Модель для этого типа структуры — упорядоченный список, например, ключевых слов, в котором слова могут встречаться несколько раз. Если бы множественные вхождения слов не допускались, hash_set был бы соответствующей структурой контейнера. Если бы уникальные определения вносились в список уникальных ключевых слов в качестве значений, hash_map был бы соответствующей структурой для размещения этих данных. Если бы вместо этого определения не были уникальны, hash_multimap был бы рекомендуемым контейнером.

Объект hash_multiset упорядочивает управляемую им последовательность путем вызова хранимого объекта хэш-признаков типа [value_compare](#value_compare). Доступ к этому сохраненному объекту можно получить путем вызова функции-члена [key_comp](#key_comp). Такой объект функции должен вести себя так же, как объект класса `hash_compare<Key, less<Key> >` . В частности, для всех *ключей* значений типа `Key` вызов `Trait(Key)` Возвращает распределение значений типа `size_t` .

В целом, упорядочиваемые элементы должны лишь подлежать сравнению "меньше чем" для установления такого порядка, чтобы, имея любые два элемента, можно было определить, что они равны (ни один не меньше другого) или что один меньше другого. Это приводит к упорядочению неравнозначных элементов. С более технической точки зрения, функция сравнения является бинарным предикатом, который вызывает строгого слабое упорядочение в стандартном математически смысле. Бинарный предикат *f*( *x*, *y*) — это объект функции, имеющий два объекта-аргумента x и y, а также возвращаемое значение true или false. Порядок в объекте hash_multiset — строгое слабое упорядочивание, если бинарный предикат является нерефлексивным, антисимметричным и транзитивным и если эквивалентность транзитивна, когда два объекта — x и y определяются как эквивалентные, когда и *f*( *x*, *y*), и *f*( *y*, *x*) имеют значение false. Если более строгое условие равенства между ключами заменяет условие эквивалентности, порядок становится общим (т.е. все элементы упорядочиваются относительно друг друга), и сопоставленные ключи будут неотличимы друг от друга.

Фактический порядок элементов в управляемой последовательности зависит от хэш-функции, функции упорядочения и текущего размера хэш-таблицы, хранимой в объекте контейнера. Текущий размер хэш-таблицы определить нельзя, поэтому обычно невозможно предсказать порядок элементов в управляемой последовательности. Вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, которые ранее указывали конкретно на удаленные элементы.

Итератор, предоставляемый классом hash_multiset — это двунаправленный итератор, но функции-члены класса insert и hash_multiset имеют версии, которые принимают в качестве параметра-шаблона более слабый итератор ввода, функциональные требования которого ниже, чем гарантируемые классом двунаправленных итераторов. Различные концепции итераторов образуют семейство, связанное уточнениями функциональности. Каждая концепция итератора имеет собственный hash_multiset с требованиями, а алгоритмы, работающие с ними, должны ограничивать свои предположения согласно требованиям, предоставляемым этим типом итератора. Можно предположить, что итератор ввода может быть разыменован для обращения к определенному объекту и инкрементирован до следующего итератора в последовательности. Это минимальный набор функций hash_multiset, но его достаточно для осмысленного обсуждения диапазона итераторов [ `first`, `last`) в контексте функций-членов класса.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[hash_multiset](#hash_multiset)|Создает контейнер `hash_multiset`, который является пустым или копией части или целого другого контейнера `hash_multiset`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Тип, представляющий класс `allocator` для объекта `hash_multiset`.|
|[const_iterator](#const_iterator)|Тип, предоставляющий двунаправленный итератор, который может читать **`const`** элемент в `hash_multiset` .|
|[const_pointer](#const_pointer)|Тип, предоставляющий указатель на **`const`** элемент в `hash_multiset` .|
|[const_reference](#const_reference)|Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в, `hash_multiset` для чтения и выполнения **`const`** операций.|
|[const_reverse_iterator](#const_reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может читать любой **`const`** элемент в `hash_multiset` .|
|[difference_type](#difference_type)|Целочисленный тип со знаком, предоставляющий разницу между двумя итераторами, которые обращаются к элементам в одном и том же `hash_multiset`.|
|[iterator](#iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять любой элемент в `hash_multiset`.|
|[key_compare](#key_compare)|Тип, предоставляющий объект функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в контейнере `hash_multiset`.|
|[key_type](#key_type)|Тип, описывающий объект, сохраненный как элемент `hash_set` в смысле его возможностей, присущих ключу сортировки.|
|[pointer](#pointer)|Тип, предоставляющий указатель на элемент в `hash_multiset`.|
|[reference](#reference)|Тип, предоставляющий ссылку на элемент, хранящийся в контейнере `hash_multiset`.|
|[reverse_iterator](#reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять элемент в обращенном контейнере `hash_multiset`.|
|[size_type](#size_type)|Целочисленный Typedef без знака, который может представлять число элементов в `hash_multiset`.|
|[value_compare](#value_compare)|Тип, который предоставляет два объекта функции, бинарный предикат сравнения классов, который может сравнить два значения элементов `hash_multiset` для определения их относительного порядка, и унарный предикат, хэширующий элементы.|
|[value_type](#value_type)|Тип, описывающий объект, сохраненный как элемент `hash_multiset` в смысле его возможностей, присущих значению.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[begin](#begin)|Возвращает итератор, обращающийся к первому элементу в `hash_multiset`.|
|[cbegin](#cbegin)|Возвращает итератор const, обращающийся к первому элементу в `hash_multiset`.|
|[cend](#cend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в `hash_multiset`.|
|[clear](#clear)|Стирает все элементы в `hash_multiset`.|
|[count](#count)|Возвращает число элементов в контейнере `hash_multiset`, ключи которых соответствуют ключу, заданному параметром.|
|[crbegin](#crbegin)|Возвращает итератор const, который обращается к первому элементу в обращенном контейнере `hash_multiset`.|
|[crend](#crend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в обращенном контейнере `hash_multiset`.|
|[emplace](#emplace)|Вставляет созданный на месте элемент в `hash_multiset`.|
|[emplace_hint](#emplace_hint)|Вставляет созданный на месте элемент в `hash_multiset` с подсказкой о размещении.|
|[empty](#empty)|Проверяет, пуст ли `hash_multiset`.|
|[end](#end)|Возвращает итератор, который обращается к месту, следующему за последним элементом в контейнере `hash_multiset`.|
|[equal_range](#equal_range)|Возвращает пару итераторов соответственно на первый элемент в `hash_multiset` с ключом, который больше, чем указанный ключ, и на первый элемент в `hash_multiset` с ключом, который больше или равен данному ключу.|
|[erase](#erase)|Удаляет элемент или диапазон элементов в `hash_multiset` с заданных позиций или удаляет элементы, соответствующие заданному ключу.|
|[find](#find)|Возвращает итератор, адресующий расположение элемента в наборе `hash_multiset` с ключом, эквивалентным указанному ключу.|
|[get_allocator](#get_allocator)|Возвращает копию объекта `allocator`, который используется для создания контейнера `hash_multiset`.|
|[insert](#insert)|Вставляет элемент или диапазон элементов в `hash_multiset`.|
|[key_comp](#key_compare)|Извлекает копию объекта сравнения, который используется для упорядочивания ключей в контейнере `hash_multiset`.|
|[lower_bound](#lower_bound)|Возвращает итератор, указывающий на первый элемент в `hash_multiset` с ключом, который больше или равен указанному ключу.|
|[max_size](#max_size)|Возвращает максимальную длину `hash_multiset`.|
|[rbegin](#rbegin)|Возвращает итератор, который обращается к первому элементу в обращенном контейнере `hash_multiset`.|
|[rend](#rend)|Возвращает итератор, который обращается к месту, следующему за последним элементом в обращенном контейнере `hash_multiset`.|
|[size](#size)|Возвращает количество элементов в контейнере `hash_multiset`.|
|[swap](#swap)|Выполняет обмен элементами между двумя объектами `hash_multiset`.|
|[upper_bound](#upper_bound)|Возвращает итератор, указывающий на первый элемент в контейнере `hash_multiset` с ключом, который больше или равен указанному ключу.|
|[value_comp](#value_comp)|Извлекает копию объекта признаков хэша, используемого для хэширования и упорядочения значений ключей элемента в `hash_multiset`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[hash_multiset::operator=](#op_eq)|Заменяет элементы объекта hash_multiset копией другого объекта hash_multiset.|

## <a name="requirements"></a>Требования

**Заголовок:**\<hash_set>

**Пространство имен:** stdext

## <a name="hash_multisetallocator_type"></a><a name="allocator_type"></a> hash_multiset:: allocator_type

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий класс распределителя для объекта hash_multiset.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="example"></a>Пример

См. пример для [get_allocator](#get_allocator) в качестве примера использования `allocator_type`

## <a name="hash_multisetbegin"></a><a name="begin"></a> hash_multiset:: Begin

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает итератор, адресующий первый элемент в объекте hash_multiset.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор, адресующий первый элемент в объекте hash_multiset или положение после пустого объекта hash_multiset.

### <a name="remarks"></a>Примечания

Если возвращаемое значение `begin` присваивается `const_iterator` , то элементы в объекте hash_multiset не могут быть изменены. Если возвращаемое значение `begin` присваивается `iterator` , то элементы в объекте hash_multiset могут быть изменены.

### <a name="example"></a>Пример

```cpp
// hash_multiset_begin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;
   hash_multiset <int>::const_iterator hms1_cIter;

   hms1.insert( 1 );
   hms1.insert( 2 );
   hms1.insert( 3 );

   hms1_Iter = hms1.begin( );
   cout << "The first element of hms1 is " << *hms1_Iter << endl;

   hms1_Iter = hms1.begin( );
   hms1.erase( hms1_Iter );

   // The following 2 lines would err because the iterator is const
   // hms1_cIter = hms1.begin( );
   // hms1.erase( hms1_cIter );

   hms1_cIter = hms1.begin( );
   cout << "The first element of hms1 is now " << *hms1_cIter << endl;
}
```

```Output
The first element of hms1 is 1
The first element of hms1 is now 2
```

## <a name="hash_multisetcbegin"></a><a name="cbegin"></a> hash_multiset:: cbegin

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает константный итератор, адресующий первый элемент в объекте hash_multiset.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный двунаправленный итератор, адресующий первый элемент в [hash_multiset](../standard-library/hash-multiset-class.md) или положение после пустого `hash_multiset`.

### <a name="remarks"></a>Примечания

Если возвращенное значение — `cbegin`, элементы в объекте `hash_multiset` изменить нельзя.

### <a name="example"></a>Пример

```cpp
// hash_multiset_cbegin.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int>::const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_cIter = hs1.cbegin( );
   cout << "The first element of hs1 is " << *hs1_cIter << endl;
}
```

```Output
The first element of hs1 is 1
```

## <a name="hash_multisetcend"></a><a name="cend"></a> hash_multiset:: cend

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает константный итератор, адресующий положение после последнего элемента в hash_multiset.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный двунаправленный итератор, адресующий положение после последнего элемента в [hash_multiset](../standard-library/hash-multiset-class.md). Если `hash_multiset` пуст, то `hash_multiset::cend == hash_multiset::begin`.

### <a name="remarks"></a>Примечания

`cend` используется для проверки, достиг ли итератор конца своего `hash_multiset`. Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_multiset_cend.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int> :: const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_cIter = hs1.cend( );
   hs1_cIter--;
   cout << "The last element of hs1 is " << *hs1_cIter << endl;
}
```

```Output
The last element of hs1 is 3
```

## <a name="hash_multisetclear"></a><a name="clear"></a> hash_multiset:: Clear

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Удаляет все элементы объекта hash_multiset.

```cpp
void clear();
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multiset_clear.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;

   hms1.insert( 1 );
   hms1.insert( 2 );

   cout << "The size of the hash_multiset is initially " << hms1.size( )
        << "." << endl;

   hms1.clear( );
   cout << "The size of the hash_multiset after clearing is "
        << hms1.size( ) << "." << endl;
}
```

```Output
The size of the hash_multiset is initially 2.
The size of the hash_multiset after clearing is 0.
```

## <a name="hash_multisetconst_iterator"></a><a name="const_iterator"></a> hash_multiset:: const_iterator

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать **`const`** элемент в hash_multiset.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_iterator`нельзя использовать для изменения значения элемента.

### <a name="example"></a>Пример

См. пример для [begin](#begin) в качестве примера использования `const_iterator`.

## <a name="hash_multisetconst_pointer"></a><a name="const_pointer"></a> hash_multiset:: const_pointer

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий указатель на **`const`** элемент в hash_multiset.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Примечания

Тип `const_pointer`нельзя использовать для изменения значения элемента.

В большинстве случаев для доступа к элементам объекта hash_multiset необходимо использовать [const_iterator](#const_iterator) **`const`** .

## <a name="hash_multisetconst_reference"></a><a name="const_reference"></a> hash_multiset:: const_reference

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в hash_multiset для чтения и выполнения **`const`** операций.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_reference const_reference;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multiset_const_reference.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;

   hms1.insert( 10 );
   hms1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *hms1.begin( );

   cout << "The first element in the hash_multiset is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference cannot be used to modify the hash_multiset
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the hash_multiset is 10.
```

## <a name="hash_multisetconst_reverse_iterator"></a><a name="const_reverse_iterator"></a> hash_multiset:: const_reverse_iterator

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать любой **`const`** элемент в hash_multiset.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_reverse_iterator` не может изменять значение элемента и используется для перебора объекта hash_multiset в обратном порядке.

### <a name="example"></a>Пример

См. пример для [rend](#rend) в качестве примера объявления и использования `const_reverse_iterator`.

## <a name="hash_multisetcount"></a><a name="count"></a> hash_multiset:: count

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает число элементов в объекте hash_multiset, ключ которых совпадает с ключом, заданным параметром.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ для сравнения с ключами элементов объекта hash_multiset.

### <a name="return-value"></a>Возвращаемое значение

Число элементов в объекте hash_multiset с ключом, заданным параметром.

### <a name="remarks"></a>Примечания

Функция-член возвращает число элементов в следующем диапазоне:

\[ lower_bound (*ключ*), upper_bound (*ключ*)).

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена hash_multiset::count.

```cpp
// hash_multiset_count.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_multiset<int> hms1;
    hash_multiset<int>::size_type i;

    hms1.insert(1);
    hms1.insert(1);

    // Keys do not need to be unique in hash_multiset,
    // so duplicates may exist.
    i = hms1.count(1);
    cout << "The number of elements in hms1 with a sort key of 1 is: "
         << i << "." << endl;

    i = hms1.count(2);
    cout << "The number of elements in hms1 with a sort key of 2 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in hms1 with a sort key of 1 is: 2.
The number of elements in hms1 with a sort key of 2 is: 0.
```

## <a name="hash_multisetcrbegin"></a><a name="crbegin"></a> hash_multiset:: crbegin

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает константный итератор, адресующий первый элемент в обратном hash_multiset.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий первый элемент в обратном [hash_multiset](../standard-library/hash-multiset-class.md), или адресующий то, что было последним элементом в `hash_multiset` до изменения его порядка на противоположный.

### <a name="remarks"></a>Примечания

`crbegin` используется с обратным `hash_multiset` так же, как [hash_multiset::begin](#begin) используется с обычным `hash_multiset`.

Если возвращаемое значение `crbegin`, то объект `hash_multiset` невозможно изменить.

`crbegin` можно использовать для перебора `hash_multiset` в обратном порядке.

### <a name="example"></a>Пример

```cpp
// hash_multiset_crbegin.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crbegin( );
   cout << "The first element in the reversed hash_multiset is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The first element in the reversed hash_multiset is 30.
```

## <a name="hash_multisetcrend"></a><a name="crend"></a> hash_multiset:: crend

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает константный итератор, адресующий положение после последнего элемента в обратном hash_multiset.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий положение после последнего элемента в обратном [hash_multiset](../standard-library/hash-multiset-class.md) (положение, которое предшествовало первому элементу `hash_multiset` до изменения его порядка на противоположный).

### <a name="remarks"></a>Примечания

`crend` используется с обратным `hash_multiset` так же, как [hash_multiset::end](#end) используется с обычным `hash_multiset`.

Если возвращаемое значение `crend`, то объект `hash_multiset` невозможно изменить.

`crend` можно использовать для проверки того, достиг ли обратный итератор конца своего объекта hash_multiset.

### <a name="example"></a>Пример

```cpp
// hash_multiset_crend.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hs1;
   hash_multiset <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crend( );
   hs1_crIter--;
   cout << "The last element in the reversed hash_multiset is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The last element in the reversed hash_multiset is 10.
```

## <a name="hash_multisetdifference_type"></a><a name="difference_type"></a> hash_multiset::difference_type

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Целочисленный тип со знаком, который предоставляет разницу между двумя итераторами, адресующими элементы внутри одного и того же hash_multiset.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Примечания

`difference_type` — тип, возвращаемый при вычитании или приращении через итераторы контейнера. `difference_type` обычно используется для представления количества элементов в диапазоне [`first`, `last`) между итераторами `first` и `last`, включает элемент, на который указывает `first`, и диапазон элементов до элемента (не включая этот элемент), на который указывает `last`.

Обратите внимание, что хотя `difference_type` доступен для всех итераторов, соответствующих требованиям итератора ввода, что включает класс двунаправленных итераторов, поддерживаемых обратимыми контейнерами, например, наборами. Вычитание между итераторами поддерживается только итераторами произвольного доступа, предоставляемыми контейнерами произвольного доступа, например vector или deque.

### <a name="example"></a>Пример

```cpp
// hash_multiset_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_set>
#include <algorithm>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter, hms1_bIter, hms1_eIter;

   hms1.insert( 20 );
   hms1.insert( 10 );

   // hash_multiset elements need not be unique
   hms1.insert( 20 );

   hms1_bIter = hms1.begin( );
   hms1_eIter = hms1.end( );

   hash_multiset <int>::difference_type   df_typ5, df_typ10,
        df_typ20;

   df_typ5 = count( hms1_bIter, hms1_eIter, 5 );
   df_typ10 = count( hms1_bIter, hms1_eIter, 10 );
   df_typ20 = count( hms1_bIter, hms1_eIter, 20 );

   // The keys & hence the elements of a hash_multiset
   // need not be unique and may occur multiple times
   cout << "The number '5' occurs " << df_typ5
        << " times in hash_multiset hms1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in hash_multiset hms1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in hash_multiset hms1.\n";

   // Count the number of elements in a hash_multiset
   hash_multiset <int>::difference_type  df_count = 0;
   hms1_Iter = hms1.begin( );
   while ( hms1_Iter != hms1_eIter)
   {
      df_count++;
      hms1_Iter++;
   }

   cout << "The number of elements in the hash_multiset hms1 is "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in hash_multiset hms1.
The number '10' occurs 1 times in hash_multiset hms1.
The number '20' occurs 2 times in hash_multiset hms1.
The number of elements in the hash_multiset hms1 is 3.
```

## <a name="hash_multisetemplace"></a><a name="emplace"></a> hash_multiset:: emplace

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Вставляет в hash_multiset созданный на месте объект.

```cpp
template <class ValTy>
iterator insert(ValTy&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение элемента для вставки в [hash_multiset](../standard-library/hash-multiset-class.md), кроме случая, когда `hash_multiset` уже содержит этот элемент или, в более общем смысле, элемент, значение ключа которого имеет эквивалентный порядок.

### <a name="return-value"></a>Возвращаемое значение

Функция-член `emplace` возвращает итератор, указывающий на позицию, где был вставлен новый элемент.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multiset_emplace.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset<string> hms3;
   string str1("a");

   hms3.emplace(move(str1));
   cout << "After the emplace insertion, hms3 contains "
      << *hms3.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hms3 contains a.
```

## <a name="hash_multisetemplace_hint"></a><a name="emplace_hint"></a> hash_multiset:: emplace_hint

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Вставляет созданный на месте элемент в hash_multiset с использованием признака размещения.

```cpp
template <class ValTy>
iterator insert(
    const_iterator where,
    ValTy&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение элемента для вставки в [hash_multiset](../standard-library/hash-multiset-class.md), кроме случая, когда `hash_multiset` уже содержит этот элемент или, в более общем смысле, элемент, значение ключа которого имеет эквивалентный порядок.

*которому*\
Место начала поиска правильной точки вставки. (Вставка может производиться в нерегулярное время, а не на логарифмическое время, если точка вставки непосредственно следует за *точкой.)*

### <a name="return-value"></a>Возвращаемое значение

Функция-член [hash_multiset::emplace](#emplace) возвращает итератор, указывающий на позицию вставки нового элемента в `hash_multiset`.

### <a name="remarks"></a>Примечания

Вставка может выполняться в нерегулярном времени, а не в виде логарифмического времени, если точка вставки непосредственно соответствует *месту*.

### <a name="example"></a>Пример

```cpp
// hash_multiset_emplace_hint.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset<string> hms1;
   string str1("a");

   hms1.insert(hms1.begin(), move(str1));
   cout << "After the emplace insertion, hms1 contains "
      << *hms1.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hms1 contains a.
```

## <a name="hash_multisetempty"></a><a name="empty"></a> hash_multiset:: Empty

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Проверяет объект hash_multiset на пустоту.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если hash_multiset пустой; **`false`** если hash_multiset не пуста.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multiset_empty.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1, hms2;
   hms1.insert ( 1 );

   if ( hms1.empty( ) )
      cout << "The hash_multiset hms1 is empty." << endl;
   else
      cout << "The hash_multiset hms1 is not empty." << endl;

   if ( hms2.empty( ) )
      cout << "The hash_multiset hms2 is empty." << endl;
   else
      cout << "The hash_multiset hms2 is not empty." << endl;
}
```

```Output
The hash_multiset hms1 is not empty.
The hash_multiset hms2 is empty.
```

## <a name="hash_multisetend"></a><a name="end"></a> hash_multiset:: end

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает итератор, адресующий положение после последнего элемента в hash_multiset.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор, адресующий положение после последнего элемента в hash_multiset. Если hash_multiset пусто, то hash_multiset::end == hash_multiset::begin.

### <a name="remarks"></a>Примечания

`end` используется для проверки того, достиг ли итератор конца hash_multiset. Значение, возвращаемое `end`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_multiset_end.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: iterator hms1_Iter;
   hash_multiset <int> :: const_iterator hms1_cIter;

   hms1.insert( 1 );
   hms1.insert( 2 );
   hms1.insert( 3 );

   hms1_Iter = hms1.end( );
   hms1_Iter--;
   cout << "The last element of hms1 is " << *hms1_Iter << endl;

   hms1.erase( hms1_Iter );

   // The following 3 lines would err because the iterator is const
   // hms1_cIter = hms1.end( );
   // hms1_cIter--;
   // hms1.erase( hms1_cIter );

   hms1_cIter = hms1.end( );
   hms1_cIter--;
   cout << "The last element of hms1 is now " << *hms1_cIter << endl;
}
```

```Output
The last element of hms1 is 3
The last element of hms1 is now 2
```

## <a name="hash_multisetequal_range"></a><a name="equal_range"></a> hash_multiset:: equal_range

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает пару итераторов — итератор, указывающий на первый элемент в hash_multiset, ключ которого больше указанного ключа, и на первый элемент в hash_multiset, ключ которого равен указанному ключу или больше него.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Аргумент-ключ для сравнения с ключом сортировки элемента из объекта hash_multiset, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Пара итераторов, первый из которых — [lower_bound](#lower_bound) ключа, а второй — [upper_bound](#upper_bound) ключа.

Для доступа к первому итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **сначала** и для разыменования итератора нижней границы используйте \* ( `pr` . **первый**). Для доступа ко второму итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **второй** и для разыменования итератора верхней границы используйте \* ( `pr` . **второй**).

### <a name="example"></a>Пример

```cpp
// hash_multiset_equal_range.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef hash_multiset<int> IntHSet;
   IntHSet hms1;
   hash_multiset <int> :: const_iterator hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   pair <IntHSet::const_iterator, IntHSet::const_iterator> p1, p2;
   p1 = hms1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20\nin the hash_multiset hms1 is: "
        << *(p1.second) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20\nin the hash_multiset hms1 is: "
        << *(p1.first) << "." << endl;

   // Compare the upper_bound called directly
   hms1_RcIter = hms1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *hms1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = hms1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == hms1.end( ) )
      && ( p2.second == hms1.end( ) ) )
      cout << "The hash_multiset hms1 doesn't have an element "
           << "with a key less than 40." << endl;
   else
      cout << "The element of hash_multiset hms1"
           << "with a key >= 40 is: "
           << *(p1.first) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20
in the hash_multiset hms1 is: 30.
The lower bound of the element with a key of 20
in the hash_multiset hms1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The hash_multiset hms1 doesn't have an element with a key less than 40.
```

## <a name="hash_multiseterase"></a><a name="erase"></a> hash_multiset:: Erase

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Удаляет элемент или диапазон элементов в объекте hash_multiset с заданных позиций или удаляет элементы, соответствующие заданному ключу.

```cpp
iterator erase(iterator where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Параметры

*которому*\
Положение элемента, удаляемого из объекта hash_multiset.

*first*\
Положение первого элемента, удаляемого из объекта hash_multiset.

*last*\
Положение сразу после последнего элемента, удаляемого из объекта hash_multiset.

*раздел*\
Ключ элементов, удаляемых из объекта hash_multiset.

### <a name="return-value"></a>Возвращаемое значение

Для первых двух функций-членов двунаправленный итератор, указывающий на первый элемент, оставшийся после удаления элементов, или указатель конца объекта hash_multiset, если такого элемента не существует. Для третьей функции-члена число элементов, удаленных из объекта hash_multiset.

### <a name="remarks"></a>Примечания

Функции-члены не создают исключений.

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена hash_multiset::erase.

```cpp
// hash_multiset_erase.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_multiset<int> hms1, hms2, hms3;
    hash_multiset<int> :: iterator pIter, Iter1, Iter2;
    int i;
    hash_multiset<int>::size_type n;

    for (i = 1; i < 5; i++)
    {
        hms1.insert(i);
        hms2.insert(i * i);
        hms3.insert(i - 1);
    }

    // The 1st member function removes an element at a given position
    Iter1 = ++hms1.begin();
    hms1.erase(Iter1);

    cout << "After the 2nd element is deleted,\n"
         << "the hash_multiset hms1 is:" ;
    for (pIter = hms1.begin(); pIter != hms1.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 2nd member function removes elements
    // in the range [ first,  last)
    Iter1 = ++hms2.begin();
    Iter2 = --hms2.end();
    hms2.erase(Iter1, Iter2);

    cout << "After the middle two elements are deleted,\n"
         << "the hash_multiset hms2 is:" ;
    for (pIter = hms2.begin(); pIter != hms2.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function removes elements with a given  key
    n = hms3.erase(2);

    cout << "After the element with a key of 2 is deleted,\n"
         << "the hash_multiset hms3 is:" ;
    for (pIter = hms3.begin(); pIter != hms3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function returns the number of elements removed
    cout << "The number of elements removed from hms3 is: "
         << n << "." << endl;

    // The dereferenced iterator can also be used to specify a key
    Iter1 = ++hms3.begin();
    hms3.erase(Iter1);

    cout << "After another element with a key "
         << "equal to that of the 2nd element\n"
         << "is deleted, the hash_multiset hms3 is:" ;
    for (pIter = hms3.begin(); pIter != hms3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;
}
```

```Output
After the 2nd element is deleted,
the hash_multiset hms1 is: 1 3 4.
After the middle two elements are deleted,
the hash_multiset hms2 is: 16 4.
After the element with a key of 2 is deleted,
the hash_multiset hms3 is: 0 1 3.
The number of elements removed from hms3 is: 1.
After another element with a key equal to that of the 2nd element
is deleted, the hash_multiset hms3 is: 0 3.
```

## <a name="hash_multisetfind"></a><a name="find"></a> hash_multiset:: Find

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает итератор, адресующий положение элемента в объекте hash_multiset, ключ которого эквивалентен указанному ключу.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ-аргумент для сопоставления с ключом сортировки элемента объекта hash_multiset, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

[Iterator](#iterator) или [const_iterator](#const_iterator), адресующий положение элемента, эквивалентного указанному ключу, или адресующий положение после последнего элемента в hash_multiset, если соответствие для ключа не найдено.

### <a name="remarks"></a>Примечания

Функция-член возвращает итератор, который обращается к элементу в hash_multiset, ключ сортировки которого является `equivalent` ключом аргумента в бинарном предикате, который вызывает упорядочивание на основе отношения сравнения "меньше чем".

Если возвращаемое значение `find` назначается `const_iterator` , то объект hash_multiset изменить нельзя. Если возвращаемое значение `find` присваивается `iterator` , то объект hash_multiset можно изменить.

### <a name="example"></a>Пример

```cpp
// hash_multiset_find.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_RcIter = hms1.find( 20 );
   cout << "The element of hash_multiset hms1 with a key of 20 is: "
        << *hms1_RcIter << "." << endl;

   hms1_RcIter = hms1.find( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hms1_RcIter == hms1.end( ) )
      cout << "The hash_multiset hms1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_multiset hms1 with a key of 40 is: "
           << *hms1_RcIter << "." << endl;

   // The element at a specific location in the hash_multiset can be found
   // by using a dereferenced iterator addressing the location
   hms1_AcIter = hms1.end( );
   hms1_AcIter--;
   hms1_RcIter = hms1.find( *hms1_AcIter );
   cout << "The element of hms1 with a key matching "
        << "that of the last element is: "
        << *hms1_RcIter << "." << endl;
}
```

```Output
The element of hash_multiset hms1 with a key of 20 is: 20.
The hash_multiset hms1 doesn't have an element with a key of 40.
The element of hms1 with a key matching that of the last element is: 30.
```

## <a name="hash_multisetget_allocator"></a><a name="get_allocator"></a> hash_multiset:: get_allocator

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает копию объекта-распределителя, использующегося для создания объекта hash_multiset.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Распределитель, используемый объектом hash_multiset для управления памятью. Является параметром-шаблоном класса `Allocator`.

Более подробную информацию по `Allocator` см. в подразделе "Примечания" раздела [Класс hash_multiset](../standard-library/hash-multiset-class.md).

### <a name="remarks"></a>Примечания

Распределители для класса hash_multiset определяют, как класс управляет памятью. Распределителей по умолчанию в классах контейнеров стандартной библиотеки C++ достаточно для большинства задач программирования. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.

### <a name="example"></a>Пример

```cpp
// hash_multiset_get_allocator.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   // The following lines declare objects
   // that use the default allocator.
   hash_multiset <int, hash_compare <int, less<int> > > hms1;
   hash_multiset <int, hash_compare <int, greater<int> > > hms2;
   hash_multiset <double, hash_compare <double,
      less<double> >, allocator<double> > hms3;

   hash_multiset <int, hash_compare <int,
      greater<int> > >::allocator_type hms2_Alloc;
   hash_multiset <double>::allocator_type hms3_Alloc;
   hms2_Alloc = hms2.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << hms1.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << hms3.max_size( ) <<  "." << endl;

   // The following lines create a hash_multiset hms4
   // with the allocator of hash_multiset hms1.
   hash_multiset <int>::allocator_type hms4_Alloc;
   hash_multiset <int> hms4;
   hms4_Alloc = hms2.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated by the other
   if( hms2_Alloc == hms4_Alloc )
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

## <a name="hash_multisethash_multiset"></a><a name="hash_multiset"></a> hash_multiset:: hash_multiset

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Создает контейнер `hash_multiset`, который является пустым или копией части или целого другого контейнера `hash_multiset`.

```cpp
hash_multiset();

explicit hash_multiset(
    const Traits& Comp);

hash_multiset(
    const Traits& Comp,
    const Allocator& Al);

hash_multiset(
    const hash_multiset<Key, Traits, Allocator>& Right);

hash_multiset(
    hash_multiset&& Right
};
hash_multiset (initializer_list<Type> IList);

hash_multiset(
    initializer_list<Tu[e> IList, const Compare& Comp):
hash_multiset(
    initializer_list<Type> IList, const Compare& Comp, const Allocator& Al);

template <class InputIterator>
hash_multiset(
    InputIterator first,
    InputIterator last);

template <class InputIterator>
hash_multiset(
    InputIterator first,
    InputIterator last,
    const Traits& Comp);

template <class InputIterator>
hash_multiset(
    InputIterator first,
    InputIterator last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Параметры

*Al*\
Класс распределителя памяти для использования с этим объектом `hash_multiset`. Значение по умолчанию — `Allocator`.

*Соответствовал*\
Функция сравнения типа `const Traits`, используемая для упорядочивания элементов в `hash_multiset`. Значение по умолчанию — `hash_compare`.

*right*\
`hash_multiset`, копией которого будет создаваемый `hash_multiset`.

*first*\
Положение первого элемента в диапазоне копируемых элементов.

*last*\
Положение первого элемента после диапазона копируемых элементов.

*Интерфейс*\
Список initializer_list с элементами, которые необходимо скопировать.

### <a name="remarks"></a>Примечания

Все конструкторы сохраняют тип объекта-распределителя, управляющего памятью для `hash_multiset`. Затем этот тип можно получить с помощью вызова [hash_multiset::get_allocator](#get_allocator). Параметр-распределитель часто не указывается в объявлениях класса и в макросах предварительной обработки, используемых для замены альтернативных распределителей.

Все конструкторы инициализируют свои объекты hash_multiset.

Все конструкторы сохраняют объект-функцию типа `Traits`, которая используется для установления порядка ключей `hash_multiset`. Затем эту функцию можно получить с помощью вызова [hash_multiset::key_comp](#key_comp). Более подробную информацию по `Traits` см. в разделе [Класс hash_multiset](../standard-library/hash-multiset-class.md).

Первые три конструктора указывают пустой начальный `hash_multiset` , второй задает тип функции сравнения (*comp*), используемой при установлении порядка элементов, а третий явно указывает тип распределителя (*Al*) для использования. Ключевое слово **`explicit`** подавляет определенные виды автоматического преобразования типов.

Четвертый конструктор перемещает `hash_multiset` `Right`.

Пятый, шестой и седьмой конструкторы используют объект initializer_list.

Последние три конструктора копирую диапазон [ `first`, `last`) `hash_multiset` с увеличением точности при указании типа функции сравнения класса Compare и распределителя.

Фактический порядок элементов в хэшированном контейнере-наборе зависит от функции хэширования, функции упорядочивания и текущего размера хэш-таблицы и, в общем случае, не может быть предсказан, как в случае с контейнером-набором, где он зависит только от функции упорядочивания.

## <a name="hash_multisetinsert"></a><a name="insert"></a> hash_multiset:: INSERT

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Вставляет элемент или диапазон элементов в объект hash_multiset.

```cpp
iterator insert(
    const Type& value);

iterator insert(
    iterator where,
    const Type& Al);

void insert(
    initializer_list<Type> IList);

iterator insert(
    const Type& value);

iterator insert(
    Iterator where,
    const Type& value);

template <class InputIterator>
void insert(
    InputIterator first,
    InputIterator last);

template <class ValTy>
iterator insert(
    ValTy&& value);

template <class ValTy>
iterator insert(
    const_iterator where,
    ValTy&& value);
```

### <a name="parameters"></a>Параметры

*value*\
Значение элемента, вставляемого в объект hash_multiset, кроме случая, когда объект hash_multiset уже содержит этот элемент, или, более общими словами, элемент, ключ которого эквивалентно упорядочен.

*которому*\
Место начала поиска правильной точки вставки. (Вставка может производиться в нерегулярное время, а не на логарифмическое время, если точка вставки непосредственно следует за *точкой.)*

*first*\
Положение первого элемента для копирования из объекта hash_multiset.

*last*\
Положение сразу после последнего элемента для копирования из объекта hash_multiset.

*Интерфейс*\
Объект initializer_list, содержащий элементы для копирования.

### <a name="return-value"></a>Возвращаемое значение

Первые две функции-члена вставки возвращают итератор, который указывает на положение вставки нового элемента.

Следующие три функции-члена используют объект initializer_list.

Третья функция-член вставляет последовательность значений элементов в объект hash_multiset в соответствии с каждым элементом, адресованным итератором в диапазоне [ `first`, `last`) указанного объекта hash_multiset.

### <a name="remarks"></a>Примечания

Вставка может производиться в периодической константе для указания версии инструкции INSERT, а не логарифмического времени, если точка вставки непосредственно следует за *точкой.*

## <a name="hash_multisetiterator"></a><a name="iterator"></a> hash_multiset:: итератор

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать или изменять любой элемент в объекте hash_multiset.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Примечания

Тип `iterator` можно использовать для изменения значения элемента.

### <a name="example"></a>Пример

См. пример для [Begin](#begin) в качестве примера объявления и использования `iterator` .

## <a name="hash_multisetkey_comp"></a><a name="key_comp"></a> hash_multiset:: key_comp

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Извлекает копию объекта сравнения, использующегося для упорядочивания ключей в объекте hash_multiset.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает hash_multisetные *признаки*параметров шаблона, которые содержат объекты-функции, используемые для хэширования и упорядочивания элементов контейнера.

Дополнительные сведения о *характеристиках* см. в разделе [hash_multiset Class](../standard-library/hash-multiset-class.md) .

### <a name="remarks"></a>Примечания

Хранимый объект определяет функцию-член:

`bool operator<(const Key& _xVal, const Key& _yVal);`

Возвращает значение, **`true`** Если `_xVal` предшествует и не равно `_yVal` в порядке сортировки.

Обратите внимание, что и [key_compare](#key_compare), и [value_compare](#value_compare) — синонимы параметра-шаблона *Traits*. Оба типа предоставлены для классов hash_set и hash_multiset, где они идентичны, для совместимости с классами hash_map и hash_multimap, где они различаются.

### <a name="example"></a>Пример

```cpp
// hash_multiset_key_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multiset <int, hash_compare < int, less<int> > >hms1;
   hash_multiset<int, hash_compare < int, less<int> > >::key_compare kc1
          = hms1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of hms1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of hms1."
        << endl;
   }

   hash_multiset <int, hash_compare < int, greater<int> > > hms2;
   hash_multiset<int, hash_compare < int, greater<int> > >::key_compare
         kc2 = hms2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of hms2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of hms2."
           << endl;
   }
}
```

## <a name="hash_multisetkey_compare"></a><a name="key_compare"></a> hash_multiset:: key_compare

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий два объекта-функции — бинарный предикат класса compare, который может сравнивать два значения элементов объекта hash_multiset для определения их относительного порядка, и унарный предикат, который хэширует элементы.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Примечания

`key_compare` является синонимом для *характеристик*параметра шаблона.

Дополнительные сведения о *характеристиках* см. в разделе [hash_multiset Class](../standard-library/hash-multiset-class.md) .

Обратите внимание, что и `key_compare`, и value_compare — синонимы параметра-шаблона *Traits*. Оба типа предоставляются для классов hash_set и hash_multiset, где они идентичны, для совместимости с классами hash_map и hash_multimap, где они различаются.

### <a name="example"></a>Пример

См. пример для [key_comp](#key_comp) в качестве примера объявления и использования `key_compare`.

## <a name="hash_multisetkey_type"></a><a name="key_type"></a> hash_multiset:: key_type

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий объект-функцию, которая может сравнивать ключи сортировки для определения относительного порядка двух элементов объекта hash_multiset.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Примечания

`key_type` является синонимом для *ключа*параметра шаблона.

Обратите внимание, что и `key_type`, и [value_type](../standard-library/hash-set-class.md#value_type) — синонимы для параметра-шаблона *Key*. Оба типа предоставляются для классов set и multiset, где они идентичны, для совместимости с классами map и multimap, где они различаются.

Дополнительные сведения о *ключе*см. в подразделе "Примечания" раздела [hash_multiset Class](../standard-library/hash-multiset-class.md) .

### <a name="example"></a>Пример

См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_type`.

## <a name="hash_multisetlower_bound"></a><a name="lower_bound"></a> hash_multiset:: lower_bound

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает итератор, указывающий на первый элемент объекта hash_multiset с ключом, который больше указанного ключа или равен ему.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Аргумент-ключ для сравнения с ключом сортировки элемента из объекта hash_multiset, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

[Iterator](#iterator) или [const_iterator](#const_iterator), адресующий положение первого элемента объекта hash_multiset с ключом, который больше ключа-аргумента или равен ему, или адресующий положение после последнего элемента в hash_multiset, если соответствие для ключа не найдено.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multiset_lower_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main() {
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_RcIter = hms1.lower_bound( 20 );
   cout << "The element of hash_multiset hms1 with a key of 20 is: "
        << *hms1_RcIter << "." << endl;

   hms1_RcIter = hms1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hms1_RcIter == hms1.end( ) )
      cout << "The hash_multiset hms1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_multiset hms1 with a key of 40 is: "
           << *hms1_RcIter << "." << endl;

   // An element at a specific location in the hash_multiset can be found
   // by using a dereferenced iterator that addresses the location
   hms1_AcIter = hms1.end( );
   hms1_AcIter--;
   hms1_RcIter = hms1.lower_bound( *hms1_AcIter );
   cout << "The element of hms1 with a key matching "
        << "that of the last element is: "
        << *hms1_RcIter << "." << endl;
}
```

## <a name="hash_multisetmax_size"></a><a name="max_size"></a> hash_multiset:: max_size

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает максимальную длину объекта hash_multiset.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимально возможная длина объекта hash_multiset.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multiset_max_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::size_type i;

   i = hms1.max_size( );
   cout << "The maximum possible length "
        << "of the hash_multiset is " << i << "." << endl;
}
```

## <a name="hash_multisetoperator"></a><a name="op_eq"></a> hash_multiset::operator=

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Заменяет элементы объекта hash_multiset копией другого объекта hash_multiset.

```cpp
hash_multiset& operator=(const hash_multiset& right);

hash_multiset& operator=(hash_multiset&& right);
```

### <a name="parameters"></a>Параметры

*right*\
Объект [hash_multiset](../standard-library/hash-multiset-class.md), копируемый в `hash_multiset`.

### <a name="remarks"></a>Примечания

После стирания любых существующих элементов в `hash_multiset` , `operator=` копирует или перемещает содержимое *непосредственно* в `hash_multiset` .

### <a name="example"></a>Пример

```cpp
// hash_multiset_operator_as.cpp
// compile with: /EHsc
#include <hash_multiset>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset<int> v1, v2, v3;
   hash_multiset<int>::iterator iter;

   v1.insert(10);

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << iter << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << iter << " ";
   cout << endl;
}
```

## <a name="hash_multisetpointer"></a><a name="pointer"></a> hash_multiset::p оинтер

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий указатель на элемент в объекте hash_multiset.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Примечания

Тип `pointer` можно использовать для изменения значения элемента.

В большинстве случаев для доступа к элементам в объекте-мультинаборе следует использовать [iterator](#iterator).

## <a name="hash_multisetrbegin"></a><a name="rbegin"></a> hash_multiset:: rbegin

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает итератор, адресующий первый элемент в обратном hash_multiset.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий первый элемент в обратном hash_multiset или элемент, который был последним в hash_multiset до изменения его порядка на противоположный.

### <a name="remarks"></a>Примечания

`rbegin` используется с обратным hash_multiset так же, как [begin](#begin) используется с обычным hash_multiset.

Если возвращенное значение `rbegin` назначается `const_reverse_iterator`, то объект hash_multiset изменить нельзя. Если возвращенное значение `rbegin` назначается `reverse_iterator`, то объект hash_multiset можно изменить.

`rbegin` можно использовать для перебора hash_multiset в обратном направлении.

### <a name="example"></a>Пример

```cpp
// hash_multiset_rbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;
   hash_multiset <int>::reverse_iterator hms1_rIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_rIter = hms1.rbegin( );
   cout << "The first element in the reversed hash_multiset is "
        << *hms1_rIter << "." << endl;

   // begin can be used to start an iteration
   // through a hash_multiset in a forward order
   cout << "The hash_multiset is: ";
   for ( hms1_Iter = hms1.begin( ) ; hms1_Iter != hms1.end( );
         hms1_Iter++ )
      cout << *hms1_Iter << " ";
   cout << endl;

   // rbegin can be used to start an iteration
   // through a hash_multiset in a reverse order
   cout << "The reversed hash_multiset is: ";
   for ( hms1_rIter = hms1.rbegin( ) ; hms1_rIter != hms1.rend( );
         hms1_rIter++ )
      cout << *hms1_rIter << " ";
   cout << endl;

   // A hash_multiset element can be erased by dereferencing to its key
   hms1_rIter = hms1.rbegin( );
   hms1.erase ( *hms1_rIter );

   hms1_rIter = hms1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed hash_multiset is "<< *hms1_rIter << "."
        << endl;
}
```

```Output
The first element in the reversed hash_multiset is 30.
The hash_multiset is: 10 20 30
The reversed hash_multiset is: 30 20 10
After the erasure, the first element in the reversed hash_multiset is 20.
```

## <a name="hash_multisetreference"></a><a name="reference"></a> hash_multiset:: Reference

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий ссылку на элемент, хранящийся в объекте hash_multiset.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::reference reference;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multiset_reference.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;

   hms1.insert( 10 );
   hms1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   int &Ref1 = *hms1.begin( );

   cout << "The first element in the hash_multiset is "
        << Ref1 << "." << endl;

   // The value of the 1st element of the hash_multiset can be
   // changed by operating on its (non const) reference
   Ref1 = Ref1 + 5;

   cout << "The first element in the hash_multiset is now "
        << *hms1.begin() << "." << endl;
}
```

```Output
The first element in the hash_multiset is 10.
The first element in the hash_multiset is now 15.
```

## <a name="hash_multisetrend"></a><a name="rend"></a> hash_multiset:: rend

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает итератор, адресующий положение после последнего элемента в обратном hash_multiset.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий положение после последнего элемента в обратном hash_multiset (положение перед первым элементом в hash_multiset до изменения его порядка на противоположный).

### <a name="remarks"></a>Примечания

`rend` используется с обратным hash_multiset так же, как [end](#end) используется с обычным hash_multiset.

Если возвращенное значение `rend` назначается `const_reverse_iterator`, то объект hash_multiset изменить нельзя. Если возвращенное значение `rend` назначается `reverse_iterator`, то объект hash_multiset можно изменить. Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.

`rend` можно использовать для проверки того, достиг ли обратный итератор конца своего объекта hash_multiset.

### <a name="example"></a>Пример

```cpp
// hash_multiset_rend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;
   hash_multiset <int>::reverse_iterator hms1_rIter;
   hash_multiset <int>::const_reverse_iterator hms1_crIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_rIter = hms1.rend( );
   hms1_rIter--;
   cout << "The last element in the reversed hash_multiset is "
        << *hms1_rIter << "." << endl;

   // end can be used to terminate an iteration
   // through a hash_multiset in a forward order
   cout << "The hash_multiset is: ";
   for ( hms1_Iter = hms1.begin( ) ; hms1_Iter != hms1.end( );
         hms1_Iter++ )
      cout << *hms1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an iteration
   // through a hash_multiset in a reverse order
   cout << "The reversed hash_multiset is: ";
   for ( hms1_rIter = hms1.rbegin( ) ; hms1_rIter != hms1.rend( );
         hms1_rIter++ )
      cout << *hms1_rIter << " ";
   cout << "." << endl;

   hms1_rIter = hms1.rend( );
   hms1_rIter--;
   hms1.erase ( *hms1_rIter );

   hms1_rIter = hms1.rend( );
   hms1_rIter--;
   cout << "After the erasure, the last element in the "
        << "reversed hash_multiset is " << *hms1_rIter << "."
        << endl;
}
```

```Output
The last element in the reversed hash_multiset is 10.
The hash_multiset is: 10 20 30 .
The reversed hash_multiset is: 30 20 10 .
After the erasure, the last element in the reversed hash_multiset is 20.
```

## <a name="hash_multisetreverse_iterator"></a><a name="reverse_iterator"></a> hash_multiset:: reverse_iterator

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать или изменять элементы в обратном hash_multiset.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `reverse_iterator` используется для перебора hash_multiset в обратном порядке.

### <a name="example"></a>Пример

См. пример для [rbegin](#rbegin) в качестве примера объявления и использования `reverse_iterator`.

## <a name="hash_multisetsize"></a><a name="size"></a> hash_multiset:: size

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает количество элементов в объекте hash_multiset.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая длина объекта hash_multiset.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multiset_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: size_type i;

   hms1.insert( 1 );
   i = hms1.size( );
   cout << "The hash_multiset length is " << i << "." << endl;

   hms1.insert( 2 );
   i = hms1.size( );
   cout << "The hash_multiset length is now " << i << "." << endl;
}
```

```Output
The hash_multiset length is 1.
The hash_multiset length is now 2.
```

## <a name="hash_multisetsize_type"></a><a name="size_type"></a> hash_multiset:: size_type

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Беззнаковый целочисленный тип, который может представлять количество элементов в объекте hash_multiset.

```cpp
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

См. пример для [size](#size) в качестве примера объявления и использования `size_type`

## <a name="hash_multisetswap"></a><a name="swap"></a> hash_multiset:: swap

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Обменивает местами элементы двух объектов hash_multiset.

```cpp
void swap(hash_multiset& right);
```

### <a name="parameters"></a>Параметры

*right*\
Аргумент-объект hash_multiset, предоставляющий элементы, которые должны быть обменены местами с элементами целевого объектаhash_multiset.

### <a name="remarks"></a>Примечания

Функция-член не делает недействительными никакие ссылки, указатели или итераторы, обозначающие элементы в двух объектах hash_multisets, элементы которых меняются местами.

### <a name="example"></a>Пример

```cpp
// hash_multiset_swap.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1, hms2, hms3;
   hash_multiset <int>::iterator hms1_Iter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );
   hms2.insert( 100 );
   hms2.insert( 200 );
   hms3.insert( 300 );

   cout << "The original hash_multiset hms1 is:";
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );
         hms1_Iter++ )
         cout << " " << *hms1_Iter;
   cout   << "." << endl;

   // This is the member function version of swap
   hms1.swap( hms2 );

   cout << "After swapping with hms2, list hms1 is:";
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );
         hms1_Iter++ )
         cout << " " << *hms1_Iter;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( hms1, hms3 );

   cout << "After swapping with hms3, list hms1 is:";
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );
         hms1_Iter++ )
         cout << " " << *hms1_Iter;
   cout   << "." << endl;
}
```

```Output
The original hash_multiset hms1 is: 10 20 30.
After swapping with hms2, list hms1 is: 200 100.
After swapping with hms3, list hms1 is: 300.
```

## <a name="hash_multisetupper_bound"></a><a name="upper_bound"></a> hash_multiset:: upper_bound

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Возвращает итератор, указывающий на первый элемент объекта hash_multiset с ключом, который больше указанного ключа.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Аргумент-ключ для сравнения с ключом сортировки элемента из объекта hash_multiset, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

[Iterator](#iterator) или [const_iterator](#const_iterator), адресующий положение первого элемента в hash_multiset с ключом, который больше ключа-аргумента, или адресующий положение после последнего элемента в hash_multiset, если соответствие для ключа не найдено.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_multiset_upper_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;

   hms1.insert( 10 );
   hms1.insert( 20 );
   hms1.insert( 30 );

   hms1_RcIter = hms1.upper_bound( 20 );
   cout << "The first element of hash_multiset hms1" << endl
        << "with a key greater than 20 is: "
        << *hms1_RcIter << "." << endl;

   hms1_RcIter = hms1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( hms1_RcIter == hms1.end( ) )
      cout << "The hash_multiset hms1 doesn't have an element\n"
           << "with a key greater than 30." << endl;
   else
      cout << "The element of hash_multiset hms1"
           << "with a key > 40 is: "
           << *hms1_RcIter << "." << endl;

   // An element at a specific location in the hash_multiset can be
   // found by using a dereferenced iterator addressing the location
   hms1_AcIter = hms1.begin( );
   hms1_RcIter = hms1.upper_bound( *hms1_AcIter );
   cout << "The first element of hms1 with a key greater than "
        << endl << "that of the initial element of hms1 is: "
        << *hms1_RcIter << "." << endl;
}
```

```Output
The first element of hash_multiset hms1
with a key greater than 20 is: 30.
The hash_multiset hms1 doesn't have an element
with a key greater than 30.
The first element of hms1 with a key greater than
that of the initial element of hms1 is: 20.
```

## <a name="hash_multisetvalue_comp"></a><a name="value_comp"></a> hash_multiset:: value_comp

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Извлекает копию объекта сравнения, используемого для упорядочивания значений элементов в объекте hash_multiset.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает hash_multisetные *признаки*параметров шаблона, которые содержат объекты-функции, используемые для хэширования и упорядочивания элементов контейнера.

Дополнительные сведения о *характеристиках* см. в разделе [hash_multiset Class](../standard-library/hash-multiset-class.md) .

### <a name="remarks"></a>Примечания

Хранимый объект определяет функцию-член:

**bool operator**( **constKey&**`_xVal`, **const Key&** *_yVal*);

Возвращает значение, **`true`** Если `_xVal` предшествует и не равно `_yVal` в порядке сортировки.

Обратите внимание, что и [key_compare](#key_compare), и [value_compare](#value_compare) — синонимы параметра-шаблона *Traits*. Оба типа предоставлены для классов hash_set и hash_multiset, где они идентичны, для совместимости с классами hash_map и hash_multimap, где они различаются.

### <a name="example"></a>Пример

```cpp
// hash_multiset_value_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_multiset <int, hash_compare < int, less<int> > > hms1;
   hash_multiset <int, hash_compare < int, less<int> > >::value_compare
      vc1 = hms1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of hms1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of hms1."
           << endl;
   }

   hash_multiset <int, hash_compare < int, greater<int> > > hms2;
   hash_multiset<int, hash_compare < int, greater<int> > >::
           value_compare vc2 = hms2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of hms2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of hms2."
           << endl;
   }
}
```

```Output
vc1( 2,3 ) returns value of true, where vc1 is the function object of hms1.
vc2( 2,3 ) returns value of false, where vc2 is the function object of hms2.
```

## <a name="hash_multisetvalue_compare"></a><a name="value_compare"></a> hash_multiset:: value_compare

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, предоставляющий два объекта-функции — бинарный предикат класса compare, который может сравнивать два значения элементов объекта hash_multiset для определения их относительного порядка, и унарный предикат, который хэширует элементы.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Примечания

`value_compare` является синонимом для *характеристик*параметра шаблона.

Дополнительные сведения о *характеристиках* см. в разделе [hash_multiset Class](../standard-library/hash-multiset-class.md) .

Обратите внимание, что оба [key_compare](#key_compare) и `value_compare` являются синонимами для *Traits*признаков параметра шаблона. Оба типа предоставляются для классов set и multiset, где они идентичны, для совместимости с классами map и multimap, где они различаются.

### <a name="example"></a>Пример

См. пример для [value_comp](#value_comp) в качестве примера объявления и использования `value_compare`.

## <a name="hash_multisetvalue_type"></a><a name="value_type"></a> hash_multiset:: value_type

> [!NOTE]
> Этот API устарел. Альтернатива — [класс unordered_multiset](../standard-library/unordered-multiset-class.md).

Тип, описывающий объект, хранящийся как элемент в hash_multiset в смысле его возможностей, присущих значению.

```cpp
typedef Key value_type;
```

### <a name="example"></a>Пример

```cpp
// hash_multiset_value_type.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multiset <int> hms1;
   hash_multiset <int>::iterator hms1_Iter;

   // Declare value_type
   hash_multiset <int> :: value_type hmsvt_Int;

   hmsvt_Int = 10;   // Initialize value_type

   // Declare key_type
   hash_multiset <int> :: key_type hmskt_Int;
   hmskt_Int = 20;             // Initialize key_type

   hms1.insert( hmsvt_Int );         // Insert value into s1
   hms1.insert( hmskt_Int );         // Insert key into s1

   // A hash_multiset accepts key_types or value_types as elements
   cout << "The hash_multiset has elements:";
   for ( hms1_Iter = hms1.begin() ; hms1_Iter != hms1.end( );
         hms1_Iter++)
      cout << " " << *hms1_Iter;
      cout << "." << endl;
}
```

```Output
The hash_multiset has elements: 10 20.
```

## <a name="see-also"></a>См. также

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
