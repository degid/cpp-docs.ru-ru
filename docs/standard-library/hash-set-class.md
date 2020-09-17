---
title: Класс hash_set
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_set
- hash_set/stdext::hash_set::allocator_type
- hash_set/stdext::hash_set::const_iterator
- hash_set/stdext::hash_set::const_pointer
- hash_set/stdext::hash_set::const_reference
- hash_set/stdext::hash_set::const_reverse_iterator
- hash_set/stdext::hash_set::difference_type
- hash_set/stdext::hash_set::iterator
- hash_set/stdext::hash_set::key_compare
- hash_set/stdext::hash_set::key_type
- hash_set/stdext::hash_set::pointer
- hash_set/stdext::hash_set::reference
- hash_set/stdext::hash_set::reverse_iterator
- hash_set/stdext::hash_set::size_type
- hash_set/stdext::hash_set::value_compare
- hash_set/stdext::hash_set::value_type
- hash_set/stdext::hash_set::begin
- hash_set/stdext::hash_set::cbegin
- hash_set/stdext::hash_set::cend
- hash_set/stdext::hash_set::clear
- hash_set/stdext::hash_set::count
- hash_set/stdext::hash_set::crbegin
- hash_set/stdext::hash_set::crend
- hash_set/stdext::hash_set::emplace
- hash_set/stdext::hash_set::emplace_hint
- hash_set/stdext::hash_set::empty
- hash_set/stdext::hash_set::end
- hash_set/stdext::hash_set::equal_range
- hash_set/stdext::hash_set::erase
- hash_set/stdext::hash_set::find
- hash_set/stdext::hash_set::get_allocator
- hash_set/stdext::hash_set::insert
- hash_set/stdext::hash_set::key_comp
- hash_set/stdext::hash_set::lower_bound
- hash_set/stdext::hash_set::max_size
- hash_set/stdext::hash_set::rbegin
- hash_set/stdext::hash_set::rend
- hash_set/stdext::hash_set::size
- hash_set/stdext::hash_set::swap
- hash_set/stdext::hash_set::upper_bound
- hash_set/stdext::hash_set::value_comp
helpviewer_keywords:
- stdext::hash_set
- stdext::hash_set::allocator_type
- stdext::hash_set::const_iterator
- stdext::hash_set::const_pointer
- stdext::hash_set::const_reference
- stdext::hash_set::const_reverse_iterator
- stdext::hash_set::difference_type
- stdext::hash_set::iterator
- stdext::hash_set::key_compare
- stdext::hash_set::key_type
- stdext::hash_set::pointer
- stdext::hash_set::reference
- stdext::hash_set::reverse_iterator
- stdext::hash_set::size_type
- stdext::hash_set::value_compare
- stdext::hash_set::value_type
- stdext::hash_set::begin
- stdext::hash_set::cbegin
- stdext::hash_set::cend
- stdext::hash_set::clear
- stdext::hash_set::count
- stdext::hash_set::crbegin
- stdext::hash_set::crend
- stdext::hash_set::emplace
- stdext::hash_set::emplace_hint
- stdext::hash_set::empty
- stdext::hash_set::end
- stdext::hash_set::equal_range
- stdext::hash_set::erase
- stdext::hash_set::find
- stdext::hash_set::get_allocator
- stdext::hash_set::insert
- stdext::hash_set::key_comp
- stdext::hash_set::lower_bound
- stdext::hash_set::max_size
- stdext::hash_set::rbegin
- stdext::hash_set::rend
- stdext::hash_set::size
- stdext::hash_set::swap
- stdext::hash_set::upper_bound
- stdext::hash_set::value_comp
ms.assetid: c765c06e-cbb6-48c2-93ca-d15468eb28d7
ms.openlocfilehash: 01076d29a18a2b051695955e9409d8b77d22c313
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561184"
---
# <a name="hash_set-class"></a>Класс hash_set

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Контейнерный класс hash_set является расширением стандартной библиотеки C++ и используется для хранения и быстрого извлечения данных из коллекции, в которой значения элементов уникальны и используются как значения ключа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Key,
    class Traits=hash_compare<Key, less<Key>>,
    class Allocator=allocator<Key>>
class hash_set
```

### <a name="parameters"></a>Параметры

*Раздел*\
Тип данных элемента, который будет сохранен в hash_set.

*Traits*\
Тип, включающий два объекта функции, один из классов Compare, который является бинарным предикатом, способен сравнивать два значения элементов как ключи сортировки для определения их относительного порядка, а также хэш-функцию, которая является унарным предикатом, сопоставленным ключевым значениям для элементов с целыми числами без знака типа `size_t` . Этот аргумент является необязательным, и в качестве значения по умолчанию используется `hash_compare<Key, less<Key> >`.

*Allocator*\
Тип, представляющий сохраненный объект распределителя, который инкапсулирует сведения о выделении и освобождении памяти для hash_set. Этот аргумент является необязательным, и в качестве значения по умолчанию используется `allocator<Key>`.

## <a name="remarks"></a>Примечания

hash_set это:

- Ассоциативный контейнер, который является контейнером переменного размера, поддерживающим эффективное получение значений элементов на основе значения соответствующего ключа. Кроме того, это простой ассоциативный контейнер, поскольку его значения элементов являются значениями его ключей.

- Является реверсивным, поскольку предоставляет двунаправленный итератор для получения доступа к его элементам.

- Хэшируется, поскольку его элементы группируются в сегменты на основе значения хэш-функции, применяемой к значениям ключей элементов.

- Является уникальным, поскольку каждый его элемент должен обладать уникальным ключом. Поскольку hash_set также является простым ассоциативным контейнером, его элементы также уникальны.

- Шаблон класса, поскольку предоставляемые им функции являются универсальными и поэтому не зависят от конкретного типа данных, содержащихся в качестве элементов или ключей. Типы данных, используемые для элементов и ключей, вместо этого определяются как параметры в шаблоне класса вместе с функцией и распределителем сравнения.

Главным преимуществом хэширования по сравнению с сортировкой является повышенная эффективность; при успешном хэшировании вставка, удаление и поиск выполняются за константный средний промежуток времени по сравнению со временем, пропорциональным логарифму числа элементов в контейнере, для методов сортировки. Значение элемента в наборе нельзя изменить напрямую. Вместо этого старые значения необходимо удалить и вставить элементы с новыми значениями.

Выбор типа контейнера должен в общем случае производиться на основе типа поиска и вставки, который требуется приложению. Хэшированные ассоциативные контейнеры оптимизированы для операций поиска, вставки и удаления. Функции-члены, которые явно поддерживают эти операции, эффективны при использовании совместно с правильно разработанной хэш-функцией, в результате чего они имеют постоянное среднее время выполнения и не зависят от числа элементов в контейнере. Правильно разработанная хэш-функция обеспечивает равномерное распределение хэшированных значений и сводит к минимуму количество конфликтов, когда разные значения ключей сопоставляются с одним хэшированным значением. В худшем случае, когда применяется наиболее неоптимальная хэш-функция, количество операций пропорционально количеству элементов в последовательности (линейное время).

hash_set рекомендуется использовать в качестве ассоциативного контейнера, если условия, ассоциирующие значения с ключами, удовлетворяются приложением. Элементы hash_set являются уникальными и используются в качестве своих собственных ключей сортировки. Модель для этого типа структуры — упорядоченный список, например, ключевых слов, в котором слова не должны повторяться. Если допускается многократное использование слов, то подходящей структурой контейнера будет hash_multiset. Если значения вносятся в список уникальных ключевых слов, hash_map является подходящей структурой для размещения этих данных. Если же ключи не являются уникальными, предпочтительным контейнером является hash_multimap.

Hash_set упорядочивает последовательность, которую он контролирует, вызывая хранимый хэш- `Traits` объект типа [value_compare](#value_compare). Доступ к этому сохраненному объекту можно получить путем вызова функции-члена [key_comp](#key_comp). Такой объект функции должен вести себя так же, как объект класса *hash_compare<Key, меньше \<Key> >.* В частности, для всех значений `key` типа Key `key` признак вызова () дает распределение значений типа size_t.

В целом, упорядочиваемые элементы должны лишь подлежать сравнению "меньше чем" для установления такого порядка, чтобы, имея любые два элемента, можно было определить, что они равны (ни один не меньше другого) или что один меньше другого. Это приводит к упорядочению неравнозначных элементов. С более технической точки зрения, функция сравнения является бинарным предикатом, который вызывает строгого слабое упорядочение в стандартном математически смысле. Бинарный предикат *f*( *x*, *y*) — это объект функции, имеющий два объекта-аргумента x и y, а также возвращаемое значение true или false. Упорядочивание в hash_set — это строгое слабое упорядочивание, если двоичный предикат является нерефлексивным, антисимметричным и транзитивным, и если эквивалентность транзитивна, где два объекта *x* и *y* определены как эквивалентные, если и *f*( *x*, *y*), и *f*( *y*, *x*) имеют значение false. Если более строгое условие равенства между ключами заменяет условие эквивалентности, порядок становится общим (т.е. все элементы упорядочиваются относительно друг друга), и сопоставленные ключи будут неотличимы друг от друга.

Фактический порядок элементов в управляемой последовательности зависит от хэш-функции, функции упорядочения и текущего размера хэш-таблицы, хранимой в объекте контейнера. Текущий размер хэш-таблицы определить нельзя, поэтому обычно невозможно предсказать порядок элементов в управляемой последовательности. Вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, которые ранее указывали конкретно на удаленные элементы.

Итератор, предоставляемый классом hash_set, является двунаправленным итератором, но функции-члены класса [insert](#insert) и [hash_set](#hash_set) имеют версии, которые принимают в качестве параметров-шаблонов более слабый итератор ввода, чьи функциональные требования ниже, чем гарантированные классом двунаправленных итераторов. Различные концепции итераторов образуют семейство, связанное уточнениями функциональности. Каждая концепция итератора имеет собственный набор требований, а алгоритмы, работающие с ними, должны ограничивать свои предположения согласно требованиям, предоставляемым этим типом итератора. Можно предположить, что итератор ввода может быть разыменован для обращения к определенному объекту и инкрементирован до следующего итератора в последовательности. Это минимальный набор функций, но его достаточно для осмысленного обсуждения диапазона итераторов [ `first`, `last`) в контексте функций-членов класса.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[hash_set](#hash_set)|Создает контейнер `hash_set`, который является пустым или копией части или целого другого контейнера `hash_set`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Тип, представляющий класс `allocator` для объекта `hash_set`.|
|[const_iterator](#const_iterator)|Тип, предоставляющий двунаправленный итератор, который может читать **`const`** элемент в `hash_set` .|
|[const_pointer](#const_pointer)|Тип, предоставляющий указатель на **`const`** элемент в `hash_set` .|
|[const_reference](#const_reference)|Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в, `hash_set` для чтения и выполнения **`const`** операций.|
|[const_reverse_iterator](#const_reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может читать любой **`const`** элемент в `hash_set` .|
|[difference_type](#difference_type)|Тип целого числа со знаком, пригодный для представления количества элементов в контейнере `hash_set` в диапазоне между элементами, на которые указывают итераторы.|
|[iterator](#iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять любой элемент в `hash_set`.|
|[key_compare](#key_compare)|Тип, предоставляющий объект функции, который может сравнить два ключа сортировки для определения относительного порядка двух элементов в контейнере `hash_set`.|
|[key_type](#key_type)|Тип, описывающий объект, сохраненный как элемент `hash_set` в смысле его возможностей, присущих ключу сортировки.|
|[pointer](#pointer)|Тип, предоставляющий указатель на элемент в `hash_set`.|
|[reference](#reference)|Тип, предоставляющий ссылку на элемент, хранящийся в контейнере `hash_set`.|
|[reverse_iterator](#reverse_iterator)|Тип, предоставляющий двунаправленный итератор, который может считывать или изменять элемент в обращенном контейнере `hash_set`.|
|[size_type](#size_type)|Целочисленный Typedef без знака, который может представлять число элементов в `hash_set`.|
|[value_compare](#value_compare)|Тип, который предоставляет два объекта функции, бинарный предикат сравнения классов, который может сравнить два значения элементов `hash_set` для определения их относительного порядка, и унарный предикат, хэширующий элементы.|
|[value_type](#value_type)|Тип, описывающий объект, сохраненный как элемент `hash_set` в смысле его возможностей, присущих значению.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[begin](#begin)|Возвращает итератор, обращающийся к первому элементу в `hash_set`.|
|[cbegin](#cbegin)|Возвращает итератор const, обращающийся к первому элементу в `hash_set`.|
|[cend](#cend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в `hash_set`.|
|[clear](#clear)|Стирает все элементы в `hash_set`.|
|[count](#count)|Возвращает число элементов в контейнере `hash_set`, ключи которых соответствуют ключу, заданному параметром.|
|[crbegin](#crbegin)|Возвращает итератор const, который обращается к первому элементу в обращенном контейнере `hash_set`.|
|[crend](#crend)|Возвращает итератор const, который обращается к месту, следующему за последним элементом в обращенном контейнере `hash_set`.|
|[emplace](#emplace)|Вставляет созданный на месте элемент в `hash_set`.|
|[emplace_hint](#emplace_hint)|Вставляет созданный на месте элемент в `hash_set` с подсказкой о размещении.|
|[empty](#empty)|Проверяет, пуст ли `hash_set`.|
|[end](#end)|Возвращает итератор, который обращается к месту, следующему за последним элементом в контейнере `hash_set`.|
|[equal_range](#equal_range)|Возвращает пару итераторов соответственно на первый элемент в `hash_set` с ключом, который больше, чем указанный ключ, и на первый элемент в `hash_set` с ключом, который больше или равен данному ключу.|
|[erase](#erase)|Удаляет элемент или диапазон элементов в `hash_set` с заданных позиций или удаляет элементы, соответствующие заданному ключу.|
|[find](#find)|Возвращает итератор, адресующий расположение элемента в наборе `hash_set` с ключом, эквивалентным указанному ключу.|
|[get_allocator](#get_allocator)|Возвращает копию объекта `allocator`, который используется для создания контейнера `hash_set`.|
|[insert](#insert)|Вставляет элемент или диапазон элементов в `hash_set`.|
|[key_comp](#key_comp)|Извлекает копию объекта сравнения, который используется для упорядочивания ключей в контейнере `hash_set`.|
|[lower_bound](#lower_bound)|Возвращает итератор, указывающий на первый элемент в `hash_set` с ключом, который больше или равен указанному ключу.|
|[max_size](#max_size)|Возвращает максимальную длину `hash_set`.|
|[rbegin](#rbegin)|Возвращает итератор, который обращается к первому элементу в обращенном контейнере `hash_set`.|
|[rend](#rend)|Возвращает итератор, который обращается к месту, следующему за последним элементом в обращенном контейнере `hash_set`.|
|[size](#size)|Возвращает количество элементов в контейнере `hash_set`.|
|[swap](#swap)|Выполняет обмен элементами между двумя объектами `hash_set`.|
|[upper_bound](#upper_bound)|Возвращает итератор, указывающий на первый элемент в контейнере `hash_set` с ключом, который больше или равен указанному ключу.|
|[value_comp](#value_comp)|Извлекает копию объекта признаков хэша, используемого для хэширования и упорядочения значений ключей элемента в `hash_set`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[hash_set::operator=](#op_eq)|Заменяет элементы `hash_set` копией другого `hash_set`.|

## <a name="requirements"></a>Требования

**Заголовок:**\<hash_set>

**Пространство имен:** stdext

## <a name="hash_setallocator_type"></a><a name="allocator_type"></a> hash_set:: allocator_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, представляющий класс распределителя для объекта hash_set.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;
```

### <a name="remarks"></a>Примечания

`allocator_type` является синонимом для *распределителя*параметров шаблона.

Дополнительные сведения о *распределителя*см. в подразделе "Примечания" раздела [hash_set Class](../standard-library/hash-set-class.md) .

### <a name="example"></a>Пример

См. пример для [get_allocator](#get_allocator) в качестве примера использования `allocator_type`.

## <a name="hash_setbegin"></a><a name="begin"></a> hash_set:: Begin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает итератор, адресующий первый элемент в hash_set.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор, адресующий первый элемент в hash_set или положение после пустого hash_set.

### <a name="remarks"></a>Примечания

Если возвращаемое значение `begin` присваивается `const_iterator` , то элементы в объекте hash_set не могут быть изменены. Если возвращаемое значение `begin` присваивается `iterator` , то элементы в объекте hash_set могут быть изменены.

### <a name="example"></a>Пример

```cpp
// hash_set_begin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;
   hash_set <int>::const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_Iter = hs1.begin( );
   cout << "The first element of hs1 is " << *hs1_Iter << endl;

   hs1_Iter = hs1.begin( );
   hs1.erase( hs1_Iter );

   // The following 2 lines would err because the iterator is const
   // hs1_cIter = hs1.begin( );
   // hs1.erase( hs1_cIter );

   hs1_cIter = hs1.begin( );
   cout << "The first element of hs1 is now " << *hs1_cIter << endl;
}
```

```Output
The first element of hs1 is 1
The first element of hs1 is now 2
```

## <a name="hash_setcbegin"></a><a name="cbegin"></a> hash_set:: cbegin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает константный итератор, адресующий первый элемент в hash_set.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный двунаправленный итератор, адресующий первый элемент в [hash_set](../standard-library/hash-set-class.md) или положение после пустого `hash_set`.

### <a name="remarks"></a>Примечания

Если возвращенное значение — `cbegin`, элементы в объекте `hash_set` изменить нельзя.

### <a name="example"></a>Пример

```cpp
// hash_set_cbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::const_iterator hs1_cIter;

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

## <a name="hash_setcend"></a><a name="cend"></a> hash_set:: cend

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает константный итератор, который адресует положение после последнего элемента в hash_map.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный двунаправленный итератор, адресующий положение после последнего элемента в [hash_set](../standard-library/hash-set-class.md). Если `hash_set` пуст, то `hash_set::cend == hash_set::begin`.

### <a name="remarks"></a>Примечания

`cend` используется для проверки, достиг ли итератор конца своего `hash_set`. Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_set_cend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_cIter;

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

## <a name="hash_setclear"></a><a name="clear"></a> hash_set:: Clear

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Стирает все элементы в объекте hash_set.

```cpp
void clear();
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_set_clear.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;

   hs1.insert( 1 );
   hs1.insert( 2 );

   cout << "The size of the hash_set is initially " << hs1.size( )
        << "." << endl;

   hs1.clear( );
   cout << "The size of the hash_set after clearing is "
        << hs1.size( ) << "." << endl;
}
```

```Output
The size of the hash_set is initially 2.
The size of the hash_set after clearing is 0.
```

## <a name="hash_setconst_iterator"></a><a name="const_iterator"></a> hash_set:: const_iterator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать **`const`** элемент в hash_set.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_iterator`нельзя использовать для изменения значения элемента.

### <a name="example"></a>Пример

См. пример для [begin](#begin) в качестве примера использования `const_iterator`.

## <a name="hash_setconst_pointer"></a><a name="const_pointer"></a> hash_set:: const_pointer

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, предоставляющий указатель на **`const`** элемент в hash_set.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_pointer const_pointer;
```

### <a name="remarks"></a>Примечания

Тип `const_pointer`нельзя использовать для изменения значения элемента.

В большинстве случаев для доступа к элементам объекта hash_set необходимо использовать [const_iterator](#const_iterator) **`const`** .

## <a name="hash_setconst_reference"></a><a name="const_reference"></a> hash_set:: const_reference

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в hash_set для чтения и выполнения **`const`** операций.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reference const_reference;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_set_const_ref.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;

   hs1.insert( 10 );
   hs1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *hs1.begin( );

   cout << "The first element in the hash_set is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference cannot be used to modify the hash_set
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the hash_set is 10.
```

## <a name="hash_setconst_reverse_iterator"></a><a name="const_reverse_iterator"></a> hash_set:: const_reverse_iterator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать любой **`const`** элемент в hash_set.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `const_reverse_iterator` не может изменять значение элемента и используется для перебора hash_set в обратном порядке.

### <a name="example"></a>Пример

См. пример для [rend](#rend) в качестве примера объявления и использования `const_reverse_iterator`

## <a name="hash_setcount"></a><a name="count"></a> hash_set:: count

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает число элементов в объекте hash_set, ключ которых совпадает с ключом, заданным параметром.

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ для сравнения с ключами элементов объекта hash_set.

### <a name="return-value"></a>Возвращаемое значение

1, если объект hash_set содержит элемент, ключ сортировки которого совпадает с ключом параметра.

0, если объект hash_set не содержит ни одного элемента с совпадающим ключом.

### <a name="remarks"></a>Примечания

Функция-член возвращает число элементов в следующем диапазоне:

\[ lower_bound (*ключ*), upper_bound (*ключ*)).

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена hash_set::count.

```cpp
// hash_set_count.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
    using namespace std;
    using namespace stdext;
    hash_set<int> hs1;
    hash_set<int>::size_type i;

    hs1.insert(1);
    hs1.insert(1);

    // Keys must be unique in hash_set, so duplicates are ignored.
    i = hs1.count(1);
    cout << "The number of elements in hs1 with a sort key of 1 is: "
         << i << "." << endl;

    i = hs1.count(2);
    cout << "The number of elements in hs1 with a sort key of 2 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in hs1 with a sort key of 1 is: 1.
The number of elements in hs1 with a sort key of 2 is: 0.
```

## <a name="hash_setcrbegin"></a><a name="crbegin"></a> hash_set:: crbegin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает константный итератор, адресующий первый элемент в обратном hash_set.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий первый элемент в обратном [hash_set](../standard-library/hash-set-class.md) или элемент, который был последним элементом в `hash_set` до изменения его порядка на противоположный.

### <a name="remarks"></a>Примечания

`crbegin` используется с обратным hash_set так же, как [hash_set::begin](#begin) используется с обычным hash_set.

Если возвращаемое значение `crbegin`, то объект `hash_set` невозможно изменить.

`crbegin` можно использовать для перебора `hash_set` в обратном порядке.

### <a name="example"></a>Пример

```cpp
// hash_set_crbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crbegin( );
   cout << "The first element in the reversed hash_set is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The first element in the reversed hash_set is 30.
```

## <a name="hash_setcrend"></a><a name="crend"></a> hash_set:: crend

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает константный итератор, адресующий положение после последнего элемента в обратном hash_set.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный обратный двунаправленный итератор, адресующий положение после последнего элемента в обратном [hash_set](../standard-library/hash-set-class.md) (положение перед первым элементом в `hash_set` до изменения его порядка на противоположный).

### <a name="remarks"></a>Примечания

`crend` используется с обратным `hash_set` так же, как [hash_set::end](#end) используется с обычным `hash_set`.

Если возвращаемое значение `crend`, то объект `hash_set` невозможно изменить.

`crend` используется, чтобы проверить, достиг ли итератор конца `hash_set`.

### <a name="example"></a>Пример

```cpp
// hash_set_crend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_crIter = hs1.crend( );
   hs1_crIter--;
   cout << "The last element in the reversed hash_set is "
        << *hs1_crIter << "." << endl;
}
```

```Output
The last element in the reversed hash_set is 10.
```

## <a name="hash_setdifference_type"></a><a name="difference_type"></a> hash_set::difference_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Целочисленный тип со знаком, который можно использовать для представления количества элементов в hash_set в диапазоне между элементами, на которые указывают итераторы.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::difference_type difference_type;
```

### <a name="remarks"></a>Примечания

`difference_type` — тип, возвращаемый при вычитании или приращении через итераторы контейнера. `difference_type` обычно используется для представления количества элементов в диапазоне [`first`, `last`) между итераторами `first` и `last`, включает элемент, на который указывает `first`, и диапазон элементов до элемента (не включая этот элемент), на который указывает `last`.

Обратите внимание, что хотя `difference_type` доступно для всех итераторов, соответствующих требованиям итератора ввода, что включает класс двунаправленных итераторов, поддерживаемых обратимыми контейнерами, например наборами, вычитание между итераторами поддерживается только итераторами произвольного доступа, предоставляемыми контейнерами произвольного доступа, например vector или deque.

### <a name="example"></a>Пример

```cpp
// hash_set_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <hash_set>
#include <algorithm>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter, hs1_bIter, hs1_eIter;

   hs1.insert( 20 );
   hs1.insert( 10 );
   hs1.insert( 20 );   // Won't insert as hash_set elements are unique

   hs1_bIter = hs1.begin( );
   hs1_eIter = hs1.end( );

   hash_set <int>::difference_type   df_typ5, df_typ10, df_typ20;

   df_typ5 = count( hs1_bIter, hs1_eIter, 5 );
   df_typ10 = count( hs1_bIter, hs1_eIter, 10 );
   df_typ20 = count( hs1_bIter, hs1_eIter, 20 );

   // The keys, and hence the elements, of a hash_set are unique,
   // so there is at most one of a given value
   cout << "The number '5' occurs " << df_typ5
        << " times in hash_set hs1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in hash_set hs1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in hash_set hs1.\n";

   // Count the number of elements in a hash_set
   hash_set <int>::difference_type  df_count = 0;
   hs1_Iter = hs1.begin( );
   while ( hs1_Iter != hs1_eIter)
   {
      df_count++;
      hs1_Iter++;
   }

   cout << "The number of elements in the hash_set hs1 is: "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in hash_set hs1.
The number '10' occurs 1 times in hash_set hs1.
The number '20' occurs 1 times in hash_set hs1.
The number of elements in the hash_set hs1 is: 2.
```

## <a name="hash_setemplace"></a><a name="emplace"></a> hash_set:: emplace

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Вставляет в hash_set элемент, созданный на месте.

```cpp
template <class ValTy>
pair <iterator, bool>
emplace(
    ValTy&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение элемента для вставки в [hash_set](../standard-library/hash-set-class.md), если `hash_set` уже не содержит этот элемент, или, в более общем случае, элемент, ключ которого эквивалентно упорядочен.

### <a name="return-value"></a>Возвращаемое значение

`emplace`Функция-член возвращает пару, **`bool`** компонент которой возвращает, **`true`** Если была выполнена вставка, и **`false`** Если `hash_set` уже содержал элемент, ключ которого имеет эквивалентное значение в упорядочении, а компонент итератора возвращает адрес, куда был вставлен новый элемент, или место, где элемент уже был найден.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_set_emplace.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set<string> hs3;
   string str1("a");

   hs3.emplace(move(str1));
   cout << "After the emplace insertion, hs3 contains "
      << *hs3.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hs3 contains a.
```

## <a name="hash_setemplace_hint"></a><a name="emplace_hint"></a> hash_set:: emplace_hint

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Вставляет в hash_set элемент, созданный на месте.

```cpp
template <class ValTy>
iterator emplace(
    const_iterator _Where,
    ValTy&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение элемента для вставки в [hash_set](../standard-library/hash-set-class.md), если `hash_set` уже не содержит этот элемент, или, в более общем случае, элемент, ключ которого эквивалентно упорядочен.

*_Where*\
Место начала поиска правильной точки вставки. (Вставка может происходить в нерегулярное время, а не на логарифмическое время, если точка вставки сразу следует за *_Where*).

### <a name="return-value"></a>Возвращаемое значение

Функция-член [hash_set::emplace](#emplace) возвращает итератор, указывающий на позицию вставки нового элемента в `hash_set` или на позицию, где находится существующий элемент с эквивалентным порядком.

### <a name="remarks"></a>Примечания

Вставка может происходить в постоянном времени, а не в виде логарифмического времени, если точка вставки сразу следует за *_Where*.

### <a name="example"></a>Пример

```cpp
// hash_set_emplace_hint.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set<string> hs3;
   string str1("a");

   hs3.insert(hs3.begin(), move(str1));
   cout << "After the emplace insertion, hs3 contains "
      << *hs3.begin() << "." << endl;
}
```

```Output
After the emplace insertion, hs3 contains a.
```

## <a name="hash_setempty"></a><a name="empty"></a> hash_set:: Empty

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Проверяет, что hash_set пуст.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если hash_set пустой; **`false`** если hash_set не пуста.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_set_empty.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1, hs2;
   hs1.insert ( 1 );

   if ( hs1.empty( ) )
      cout << "The hash_set hs1 is empty." << endl;
   else
      cout << "The hash_set hs1 is not empty." << endl;

   if ( hs2.empty( ) )
      cout << "The hash_set hs2 is empty." << endl;
   else
      cout << "The hash_set hs2 is not empty." << endl;
}
```

```Output
The hash_set hs1 is not empty.
The hash_set hs2 is empty.
```

## <a name="hash_setend"></a><a name="end"></a> hash_set:: end

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает итератор, адресующий положение после последнего элемента в hash_set.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Возвращаемое значение

Двунаправленный итератор, адресующий положение после последнего элемента в hash_set. Если hash_set пуст, то hash_set::end == hash_set::begin.

### <a name="remarks"></a>Примечания

`end` используется для проверки того, достиг ли итератор конца hash_set. Значение, возвращаемое `end`, не должно быть подвергнуто удалению ссылки.

### <a name="example"></a>Пример

```cpp
// hash_set_end.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: iterator hs1_Iter;
   hash_set <int> :: const_iterator hs1_cIter;

   hs1.insert( 1 );
   hs1.insert( 2 );
   hs1.insert( 3 );

   hs1_Iter = hs1.end( );
   hs1_Iter--;
   cout << "The last element of hs1 is " << *hs1_Iter << endl;

   hs1.erase( hs1_Iter );

   // The following 3 lines would err because the iterator is const:
   // hs1_cIter = hs1.end( );
   // hs1_cIter--;
   // hs1.erase( hs1_cIter );

   hs1_cIter = hs1.end( );
   hs1_cIter--;
   cout << "The last element of hs1 is now " << *hs1_cIter << endl;
}
```

```Output
The last element of hs1 is 3
The last element of hs1 is now 2
```

## <a name="hash_setequal_range"></a><a name="equal_range"></a> hash_set:: equal_range

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает пару итераторов, указывающих на первый элемент в hash_set с ключом, равным указанному, и на первый элемент в hash_set с ключом, который больше указанного.

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ-аргумент, который будет сравниваться с ключом сортировки элемента из hash_set, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Пара итераторов, первый из которых — [lower_bound](../standard-library/set-class.md#lower_bound) ключа, а второй — [upper_bound](../standard-library/set-class.md#upper_bound) ключа.

Доя получения доступа к первому итератору в паре, возвращаемой функцией-членом, используйте `pr`. во- **первых**, и для разыменования итератора нижней границы используйте \* ( `pr` . **первый**). Для доступа ко второму итератору пары `pr`, возвращаемой функцией-членом, нужно использовать `pr`. **во-вторых**, а для разыменования итератора верхней границы используйте \* ( `pr` . **второй**).

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_set_equal_range.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   typedef hash_set<int> IntHSet;
   IntHSet hs1;
   hash_set <int> :: const_iterator hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   pair <IntHSet::const_iterator, IntHSet::const_iterator> p1, p2;
   p1 = hs1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20 in the hash_set hs1 is: "
        << *(p1.second) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20 in the hash_set hs1 is: "
        << *(p1.first) << "." << endl;

   // Compare the upper_bound called directly
   hs1_RcIter = hs1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *hs1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = hs1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == hs1.end( ) ) && ( p2.second == hs1.end( ) ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key greater than or equal to 40." << endl;
   else
      cout << "The element of hash_set hs1 with a key >= 40 is: "
           << *(p1.first) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20 in the hash_set hs1 is: 30.
The lower bound of the element with a key of 20 in the hash_set hs1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The hash_set hs1 doesn't have an element with a key greater than or equal to 40.
```

## <a name="hash_seterase"></a><a name="erase"></a> hash_set:: Erase

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Удаляет элемент или диапазон элементов в объекте hash_set с заданных позиций или удаляет элементы, соответствующие заданному ключу.

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```

### <a name="parameters"></a>Параметры

*_Where*\
Положение элемента, удаляемого из объекта hash_set.

*first*\
Положение первого элемента, удаляемого из объекта hash_set.

*last*\
Положение сразу после последнего элемента, удаляемого из объекта hash_set.

*раздел*\
Ключ элементов, удаляемых из объекта hash_set.

### <a name="return-value"></a>Возвращаемое значение

Для первых двух функций-членов двунаправленный итератор, указывающий на первый элемент, оставшийся после удаления элементов, или на указатель конца объекта hash_set, если такого элемента не существует. Для третьей функции-члена число элементов, удаленных из объекта hash_set.

### <a name="remarks"></a>Примечания

Функции-члены не создают исключений.

### <a name="example"></a>Пример

В следующем примере демонстрируется использование функции-члена hash_set::erase.

```cpp
// hash_set_erase.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main()
{
    using namespace std;
    using namespace stdext;
    hash_set<int> hs1, hs2, hs3;
    hash_set<int>::iterator pIter, Iter1, Iter2;
    int i;
    hash_set<int>::size_type n;

    for (i = 1; i < 5; i++)
    {
        hs1.insert (i);
        hs2.insert (i * i);
        hs3.insert (i - 1);
    }

    // The 1st member function removes an element at a given position
    Iter1 = ++hs1.begin();
    hs1.erase(Iter1);

    cout << "After the 2nd element is deleted, the hash_set hs1 is:";
    for (pIter = hs1.begin(); pIter != hs1.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 2nd member function removes elements
    // in the range [ first,  last)
    Iter1 = ++hs2.begin();
    Iter2 = --hs2.end();
    hs2.erase(Iter1, Iter2);

    cout << "After the middle two elements are deleted, "
         << "the hash_set hs2 is:";
    for (pIter = hs2.begin(); pIter != hs2.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function removes elements with a given  key
    n = hs3.erase(2);

    cout << "After the element with a key of 2 is deleted, "
         << "the hash_set hs3 is:";
    for (pIter = hs3.begin(); pIter != hs3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;

    // The 3rd member function returns the number of elements removed
    cout << "The number of elements removed from hs3 is: "
         << n << "." << endl;

    // The dereferenced iterator can also be used to specify a key
    Iter1 = ++hs3.begin();
    hs3.erase(Iter1);

    cout << "After another element (unique for hash_set) with a key "
         << endl;
    cout  << "equal to that of the 2nd element is deleted, "
          << "the hash_set hs3 is:";
    for (pIter = hs3.begin(); pIter != hs3.end(); pIter++)
        cout << " " << *pIter;
    cout << "." << endl;
}
```

```Output
After the 2nd element is deleted, the hash_set hs1 is: 1 3 4.
After the middle two elements are deleted, the hash_set hs2 is: 16 4.
After the element with a key of 2 is deleted, the hash_set hs3 is: 0 1 3.
The number of elements removed from hs3 is: 1.
After another element (unique for hash_set) with a key
equal to that of the 2nd element is deleted, the hash_set hs3 is: 0 3.
```

## <a name="hash_setfind"></a><a name="find"></a> hash_set:: Find

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает итератор, адресующий положение элемента в hash_set с ключом, эквивалентным указанному.

```cpp
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ-аргумент для сопоставления с ключом сортировки элемента из hash_set, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Объект `iterator` или `const_iterator` , который обращается к расположению элемента, эквивалентному указанному ключу, или, который обращается к расположению, следующему за последним элементом в hash_set, если совпадение для ключа не найдено.

### <a name="remarks"></a>Примечания

Функция-член возвращает итератор, который обращается к элементу в hash_set, ключ сортировки которого является `equivalent` ключом аргумента в бинарном предикате, который вызывает упорядочивание на основе отношения сравнения "меньше чем".

Если возвращаемое значение `find` назначается `const_iterator` , то объект hash_set изменить нельзя. Если возвращаемое значение `find` присваивается `iterator` , то объект hash_set можно изменить.

### <a name="example"></a>Пример

```cpp
// hash_set_find.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_AcIter, hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_RcIter = hs1.find( 20 );
   cout << "The element of hash_set hs1 with a key of 20 is: "
        << *hs1_RcIter << "." << endl;

   hs1_RcIter = hs1.find( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hs1_RcIter == hs1.end( ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_set hs1 with a key of 40 is: "
           << *hs1_RcIter << "." << endl;

   // The element at a specific location in the hash_set can be found
   // by using a dereferenced iterator addressing the location
   hs1_AcIter = hs1.end( );
   hs1_AcIter--;
   hs1_RcIter = hs1.find( *hs1_AcIter );
   cout << "The element of hs1 with a key matching "
        << "that of the last element is: "
        << *hs1_RcIter << "." << endl;
}
```

```Output
The element of hash_set hs1 with a key of 20 is: 20.
The hash_set hs1 doesn't have an element with a key of 40.
The element of hs1 with a key matching that of the last element is: 30.
```

## <a name="hash_setget_allocator"></a><a name="get_allocator"></a> hash_set:: get_allocator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает копию распределителя, использованного для создания hash_set.

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Распределитель, используемый hash_set для управления памятью, которая является *распределителем*параметров шаблона.

Дополнительные сведения о *распределителя*см. в подразделе "Примечания" раздела [hash_set Class](../standard-library/hash-set-class.md) .

### <a name="remarks"></a>Примечания

Распределители для класса hash_set определяют, как класс управляет памятью. Распределителей по умолчанию в классах контейнеров стандартной библиотеки C++ достаточно для большинства задач программирования. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.

### <a name="example"></a>Пример

```cpp
// hash_set_get_allocator.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   // The following lines declare objects
   // that use the default allocator.
   hash_set <int, hash_compare <int, less<int> > > hs1;
   hash_set <int,  hash_compare <int, greater<int> > > hs2;
   hash_set <double, hash_compare <double,
      less<double> >, allocator<double> > hs3;

   hash_set <int, hash_compare <int,
      greater<int> > >::allocator_type hs2_Alloc;
   hash_set <double>::allocator_type hs3_Alloc;
   hs2_Alloc = hs2.get_allocator( );

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << hs1.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << hs3.max_size( ) <<  "." << endl;

   // The following lines create a hash_set hs4
   // with the allocator of hash_set hs1.
   hash_set <int>::allocator_type hs4_Alloc;
   hash_set <int> hs4;
   hs4_Alloc = hs2.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated by the other
   if( hs2_Alloc == hs4_Alloc )
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

## <a name="hash_sethash_set"></a><a name="hash_set"></a> hash_set:: hash_set

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Создает контейнер `hash_set`, который является пустым или копией части или целого другого контейнера `hash_set`.

```cpp
hash_set();

explicit hash_set(
    const Traits& Comp);

hash_set(
    const Traits& Comp,
    const Allocator& Al);

hash_set(
    const hash_set<Key, Traits, Allocator>& Right);

hash_set(
    hash_set&& Right);

hash_set(
    initializer_list<Type> IList);

hash_set(
    initializer_list<Type> IList,
    const Compare& Comp);

hash_set(
    initializer_list<value_type> IList,
    const Compare& Comp,
    const Allocator& Al);

template <class InputIterator>
hash_set(
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
hash_set(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp);

template <class InputIterator>
hash_set(
    InputIterator First,
    InputIterator Last,
    const Traits& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>Параметры

*Al*\
Класс распределителя памяти для использования с этим объектом `hash_set`. Значение по умолчанию — `Allocator`.

*Соответствовал*\
Функция сравнения типа `const Traits`, используемая для упорядочивания элементов в `hash_set`. Значение по умолчанию — `hash_compare`.

*right*\
`hash_set`, копией которого будет создаваемый `hash_set`.

*First*\
Положение первого элемента в диапазоне копируемых элементов.

*last*\
Положение первого элемента после диапазона копируемых элементов.

### <a name="remarks"></a>Примечания

Все конструкторы хранят тип объекта-распределителя, управляющего памятью для `hash_set`. Позже этот объект можно получить путем вызова [hash_set::get_allocator](#get_allocator). Параметр-распределитель часто не указывается в объявлениях класса и в макросах предварительной обработки, используемых для замены альтернативных распределителей.

Все конструкторы инициализируют свои объекты hash_set.

Все конструкторы хранят объект-функцию типа `Traits`, используемую для установления порядка ключей `hash_set`. Позже эту функцию можно получить путем вызова [hash_set::key_comp](#key_comp). Более подробные сведения по `Traits` см. в разделе [Класс hash_set](../standard-library/hash-set-class.md).

Первый конструктор создает пустой начальный `hash_set`. Второй указывает тип функции сравнения ( `Comp`) для использования при определении порядка элементов. Третий явно указывает тип распределителя ( `Al`) для использования. Ключевое слово **`explicit`** подавляет некоторые виды автоматического преобразования типов.

Четвертый и пятый конструкторы указывают копию `hash_set` `Right`.

Шестой, седьмой и восьмой конструкторы используют для создания элементов объект initializer_list.

Последние конструкторы копирую диапазон [ `First`, `Last`) `hash_set` с повышением точности при указании типа функции сравнения класса Traits и распределителя.

Восьмой контейнер перемещает `hash_set` `Right`.

Фактический порядок элементов в контейнере `hash_set` зависит от функции хэша, функции упорядочивания и текущего размера хэш-таблицы и, в общем случае, не может быть предсказан, как в случае с контейнером типа набор, где он определяется только функцией упорядочивания.

## <a name="hash_setinsert"></a><a name="insert"></a> hash_set:: INSERT

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Вставляет элемент или диапазон элементов в `hash_set`.

```cpp
pair<iterator, bool> insert(
    const value_type& Val);

iterator insert(
    iterator Where,
    const value_type& Val);

void insert(
    initializer_list<value_type> IList)
template <class InputIterator>
void insert(
    InputIterator First,
    InputIterator Last);
```

### <a name="parameters"></a>Параметры

*val*\
Значение элемента для вставки в `hash_set`, кроме случая, когда `hash_set` уже содержит этот элемент или, в более общем смысле, элемент, чей ключ имеет эквивалентный порядок.

*Where*\
Место начала поиска правильной точки вставки. (Вставка может происходить в амортизированном константном времени вместо логарифмического времени, если точка вставки следует сразу за `_Where`.)

*First*\
Позиция первого элемента для копирования из `hash_set`.

*last*\
Позиция сразу после последнего элемента для копирования из `hash_set`.

*Интерфейс*\
Объект initializer_list, из которого копируются элементы.

### <a name="return-value"></a>Возвращаемое значение

Первая `insert` функция-член возвращает пару, **`bool`** компонент которой возвращает, **`true`** Если была выполнена вставка, и **`false`** Если `hash_set` уже содержал элемент, ключ которого имел эквивалентное значение в упорядочении, а компонент итератора возвращает адрес, куда был вставлен новый элемент, или место, где элемент уже был найден.

Для доступа к компоненту-итератору пары `pr`, возвращаемой этой функцией-членом, используйте `pr.first`, а для его разыменования — `*(pr.first)`. Для доступа к **`bool`** компоненту пары, `pr` возвращаемой этой функцией-членом, используйте `pr.second` , и для разыменования этой функции используйте `*(pr.second)` .

Вторая функция-член `insert` возвращает итератор, указывающий на позицию, где новый элемент был вставлен в `hash_set`.

### <a name="remarks"></a>Примечания

Третья функция-член вставляет элементы из объекта initializer_list.

Третья функция-член вставляет последовательность значений элементов в `hash_set` в соответствии с каждым элементом, адресованным итератором в диапазоне [ `First`, `Last`) указанного `hash_set`.

## <a name="hash_setiterator"></a><a name="iterator"></a> hash_set:: итератор

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать или изменять любой элемент в hash_set.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;
```

### <a name="remarks"></a>Примечания

Тип `iterator` можно использовать для изменения значения элемента.

### <a name="example"></a>Пример

См. пример объявления и использования `iterator` см. в разделе [begin](#begin).

## <a name="hash_setkey_comp"></a><a name="key_comp"></a> hash_set:: key_comp

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Извлекает копию объекта признаков хэша, которая используется для хэширования и упорядочивания ключевых значений элементов в hash_set.

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект-функцию, которую hash_set использует для упорядочивания своих элементов, что является *характеристиками*параметров шаблона.

Дополнительные сведения о *характеристиках* см. в разделе [hash_set Class](../standard-library/hash-set-class.md) .

### <a name="remarks"></a>Примечания

Сохраненный объект определяет функцию-член:

`bool operator( const Key& _xVal, const Key& _yVal );`

Возвращает значение, **`true`** Если `_xVal` предшествует и не равно `_yVal` в порядке сортировки.

Обратите внимание, что и [key_compare](#key_compare), и [value_compare](#value_compare) — синонимы параметра-шаблона *Traits*. Оба типа предоставляются для классов hash_set и hash_multiset, где они идентичны, для совместимости с классами hash_map и hash_multimap, где они различаются.

### <a name="example"></a>Пример

```cpp
// hash_set_key_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_set <int, hash_compare < int, less<int> > >hs1;
   hash_set<int, hash_compare < int, less<int> > >::key_compare kc1
          = hs1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of hs1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of hs1."
        << endl;
   }

   hash_set <int, hash_compare < int, greater<int> > > hs2;
   hash_set<int, hash_compare < int, greater<int> > >::key_compare
         kc2 = hs2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if(result2 == true)
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of hs2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of hs2."
           << endl;
   }
}
```

## <a name="hash_setkey_compare"></a><a name="key_compare"></a> hash_set:: key_compare

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, который предоставляет объект-функцию, которая может сравнить два ключа сортировки для определения относительного порядка двух элементов в hash_set.

```cpp
typedef Traits key_compare;
```

### <a name="remarks"></a>Примечания

`key_compare` является синонимом для *характеристик*параметра шаблона.

Дополнительные сведения о *характеристиках* см. в разделе [hash_set Class](../standard-library/hash-set-class.md) .

Обратите внимание, что `key_compare` и, и [value_compare](#value_compare) являются синонимами *Traits*для признаков параметра шаблона. Оба типа предоставляются для классов set и multiset, где они идентичны, для совместимости с классами map и multimap, где они различаются.

### <a name="example"></a>Пример

См. пример для [key_comp](#key_comp) в качестве примера объявления и использования `key_compare`.

## <a name="hash_setkey_type"></a><a name="key_type"></a> hash_set:: key_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, описывающий объект, который хранится в качестве элемента hash_set в смысле его возможностей как ключа сортировки.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Примечания

`key_type` является синонимом для *ключа*параметра шаблона.

Дополнительные сведения о *ключе*см. в подразделе "Примечания" раздела [hash_set Class](../standard-library/hash-set-class.md) .

Обратите внимание, что и `key_type`, и [value_type](#value_type) — синонимы для параметра-шаблона *Key*. Оба типа предоставляются для классов hash_set и hash_multiset, где они идентичны, для совместимости с классами hash_map и hash_multimap, где они различаются.

### <a name="example"></a>Пример

См. пример для [value_type](#value_type) в качестве примера объявления и использования `key_type`.

## <a name="hash_setlower_bound"></a><a name="lower_bound"></a> hash_set:: lower_bound

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает итератор, указывающий на первый элемент в hash_set с ключом, который больше указанного ключа или равен ему.

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ-аргумент, который будет сравниваться с ключом сортировки элемента из hash_set, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Объект `iterator` или `const_iterator` , который обращается к расположению элемента в hash_set с ключом, который равен или больше, чем ключ аргумента, или к месту последнего элемента в hash_set, если совпадение для ключа не найдено.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_set_lower_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_AcIter, hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_RcIter = hs1.lower_bound( 20 );
   cout << "The element of hash_set hs1 with a key of 20 is: "
        << *hs1_RcIter << "." << endl;

   hs1_RcIter = hs1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( hs1_RcIter == hs1.end( ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of hash_set hs1 with a key of 40 is: "
           << *hs1_RcIter << "." << endl;

   // An element at a specific location in the hash_set can be found
   // by using a dereferenced iterator that addresses the location
   hs1_AcIter = hs1.end( );
   hs1_AcIter--;
   hs1_RcIter = hs1.lower_bound( *hs1_AcIter );
   cout << "The element of hs1 with a key matching "
        << "that of the last element is: "
        << *hs1_RcIter << "." << endl;
}
```

```Output
The element of hash_set hs1 with a key of 20 is: 20.
The hash_set hs1 doesn't have an element with a key of 40.
The element of hs1 with a key matching that of the last element is: 30.
```

## <a name="hash_setmax_size"></a><a name="max_size"></a> hash_set:: max_size

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает максимальную длину hash_set.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимально возможная длина hash_set.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_set_max_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::size_type i;

   i = hs1.max_size( );
   cout << "The maximum possible length "
        << "of the hash_set is " << i << "." << endl;
}
```

## <a name="hash_setoperator"></a><a name="op_eq"></a> hash_set::operator=

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Заменяет элементы hash_set копией другого hash_set.

```cpp
hash_set& operator=(const hash_set& right);

hash_set& operator=(hash_set&& right);
```

### <a name="parameters"></a>Параметры

*right*\
[Hash_set](../standard-library/hash-set-class.md), который будет копироваться в `hash_set`.

### <a name="remarks"></a>Примечания

После стирания любых существующих элементов в `hash_set` , `operator=` копирует или перемещает содержимое *непосредственно* в `hash_set` .

### <a name="example"></a>Пример

```cpp
// hash_set_operator_as.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set<int> v1, v2, v3;
   hash_set<int>::iterator iter;

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

## <a name="hash_setpointer"></a><a name="pointer"></a> hash_set::p оинтер

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, предоставляющий указатель на элемент в hash_set.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::pointer pointer;
```

### <a name="remarks"></a>Примечания

Тип `pointer` можно использовать для изменения значения элемента.

В большинстве случаев для доступа к элементам в объекте hash_set следует использовать [iterator](#iterator).

## <a name="hash_setrbegin"></a><a name="rbegin"></a> hash_set:: rbegin

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает итератор, адресующий первый элемент в обратном hash_set.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий первый элемент в обратном hash_set или элемент, который был последним элементов в hash_set до изменения его порядка на противоположный.

### <a name="remarks"></a>Примечания

`rbegin` используется с обратным hash_set так же, как [begin](#begin) используется с обычным hash_set.

Если возвращенное значение `rbegin` назначается `const_reverse_iterator`, то объект hash_set изменить нельзя. Если возвращенное значение `rbegin` назначается `reverse_iterator`, то объект hash_set можно изменить.

`rbegin` можно использовать для перебора hash_set в обратном порядке.

### <a name="example"></a>Пример

```cpp
// hash_set_rbegin.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;
   hash_set <int>::reverse_iterator hs1_rIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_rIter = hs1.rbegin( );
   cout << "The first element in the reversed hash_set is "
        << *hs1_rIter << "." << endl;

   // begin can be used to start an iteration
   // through a hash_set in a forward order
   cout << "The hash_set is: ";
   for ( hs1_Iter = hs1.begin( ) ; hs1_Iter != hs1.end( );
         hs1_Iter++ )
      cout << *hs1_Iter << " ";
   cout << endl;

   // rbegin can be used to start an iteration
   // through a hash_set in a reverse order
   cout << "The reversed hash_set is: ";
   for ( hs1_rIter = hs1.rbegin( ) ; hs1_rIter != hs1.rend( );
         hs1_rIter++ )
      cout << *hs1_rIter << " ";
   cout << endl;

   // A hash_set element can be erased by dereferencing to its key
   hs1_rIter = hs1.rbegin( );
   hs1.erase ( *hs1_rIter );

   hs1_rIter = hs1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed hash_set is "<< *hs1_rIter << "."
        << endl;
}
```

```Output
The first element in the reversed hash_set is 30.
The hash_set is: 10 20 30
The reversed hash_set is: 30 20 10
After the erasure, the first element in the reversed hash_set is 20.
```

## <a name="hash_setreference"></a><a name="reference"></a> hash_set:: Reference

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, который предоставляет ссылку на элемент, хранящийся в hash_set.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reference reference;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_set_reference.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;

   hs1.insert( 10 );
   hs1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   int &Ref1 = *hs1.begin( );

   cout << "The first element in the hash_set is "
        << Ref1 << "." << endl;

   // The value of the 1st element of the hash_set can be changed
   // by operating on its (non-const) reference
   Ref1 = Ref1 + 5;

   cout << "The first element in the hash_set is now "
        << *hs1.begin() << "." << endl;
}
```

```Output
The first element in the hash_set is 10.
The first element in the hash_set is now 15.
```

## <a name="hash_setrend"></a><a name="rend"></a> hash_set:: rend

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает итератор, адресующий положение после последнего элемента в обратном hash_set.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Возвращаемое значение

Обратный двунаправленный итератор, адресующий положение после последнего элемента в обратном hash_set (положение перед первым элементом hash_set до изменения его порядка на противоположный).

### <a name="remarks"></a>Примечания

`rend` используется с обратным hash_set так же, как [end](#end) используется с обычным hash_set.

Если возвращенное значение `rend` назначается `const_reverse_iterator`, то объект hash_set изменить нельзя. Если возвращенное значение `rend` назначается `reverse_iterator`, то объект hash_set можно изменить. Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.

`rend` можно использовать для проверки, достиг ли обратный итератор конца своего объекта hash_set.

### <a name="example"></a>Пример

```cpp
// hash_set_rend.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;
   hash_set <int>::reverse_iterator hs1_rIter;
   hash_set <int>::const_reverse_iterator hs1_crIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_rIter = hs1.rend( );
   hs1_rIter--;
   cout << "The last element in the reversed hash_set is "
        << *hs1_rIter << "." << endl;

   // end can be used to terminate an iteration
   // through a hash_set in a forward order
   cout << "The hash_set is: ";
   for ( hs1_Iter = hs1.begin( ) ; hs1_Iter != hs1.end( );
         hs1_Iter++ )
      cout << *hs1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an iteration
   // through a hash_set in a reverse order
   cout << "The reversed hash_set is: ";
   for ( hs1_rIter = hs1.rbegin( ) ; hs1_rIter != hs1.rend( );
         hs1_rIter++ )
      cout << *hs1_rIter << " ";
   cout << "." << endl;

   hs1_rIter = hs1.rend( );
   hs1_rIter--;
   hs1.erase ( *hs1_rIter );

   hs1_rIter = hs1.rend( );
   hs1_rIter--;
   cout << "After the erasure, the last element in the "
        << "reversed hash_set is " << *hs1_rIter << "."
        << endl;
}
```

```Output
The last element in the reversed hash_set is 10.
The hash_set is: 10 20 30 .
The reversed hash_set is: 30 20 10 .
After the erasure, the last element in the reversed hash_set is 20.
```

## <a name="hash_setreverse_iterator"></a><a name="reverse_iterator"></a> hash_set:: reverse_iterator

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, предоставляющий двунаправленный итератор, который может читать или изменять элементы в обратном hash_set.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип `reverse_iterator` используется для перебора hash_set в обратном порядке.

### <a name="example"></a>Пример

См. пример для [rbegin](#rbegin) в качестве примера объявления и использования `reverse_iterator`.

## <a name="hash_setsize"></a><a name="size"></a> hash_set:: size

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает количество элементов в объекте hash_set.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая длина объекта hash_set.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_set_size.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: size_type i;

   hs1.insert( 1 );
   i = hs1.size( );
   cout << "The hash_set length is " << i << "." << endl;

   hs1.insert( 2 );
   i = hs1.size( );
   cout << "The hash_set length is now " << i << "." << endl;
}
```

```Output
The hash_set length is 1.
The hash_set length is now 2.
```

## <a name="hash_setsize_type"></a><a name="size_type"></a> hash_set:: size_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Беззнаковый целочисленный тип, который может представлять количество элементов в объекте hash_set.

```cpp
typedef list<typename Traits::value_type, typename Traits::allocator_type>::size_type size_type;
```

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

См. пример для [size](#size) в качестве примера объявления и использования `size_type`

## <a name="hash_setswap"></a><a name="swap"></a> hash_set:: swap

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Выполняет обмен элементами между двумя объектами hash_set.

```cpp
void swap(hash_set& right);
```

### <a name="parameters"></a>Параметры

*right*\
Объект-аргумент hash_set, содержащий элементы, которые нужно поменять местами с объектами в целевом объекте hash_set.

### <a name="remarks"></a>Примечания

Функция-член не делает недействительными никакие ссылки, указатели или итераторы, обозначающие элементы в двух объектах hash_set, которые меняются элементами.

### <a name="example"></a>Пример

```cpp
// hash_set_swap.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1, hs2, hs3;
   hash_set <int>::iterator hs1_Iter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );
   hs2.insert( 100 );
   hs2.insert( 200 );
   hs3.insert( 300 );

   cout << "The original hash_set hs1 is:";
   for ( hs1_Iter = hs1.begin( ); hs1_Iter != hs1.end( );
         hs1_Iter++ )
         cout << " " << *hs1_Iter;
   cout   << "." << endl;

   // This is the member function version of swap
   hs1.swap( hs2 );

   cout << "After swapping with hs2, list hs1 is:";
   for ( hs1_Iter = hs1.begin( ); hs1_Iter != hs1.end( );
         hs1_Iter++ )
         cout << " " << *hs1_Iter;
   cout  << "." << endl;

   // This is the specialized template version of swap
   swap( hs1, hs3 );

   cout << "After swapping with hs3, list hs1 is:";
   for ( hs1_Iter = hs1.begin( ); hs1_Iter != hs1.end( );
         hs1_Iter++ )
         cout << " " << *hs1_Iter;
   cout   << "." << endl;
}
```

```Output
The original hash_set hs1 is: 10 20 30.
After swapping with hs2, list hs1 is: 200 100.
After swapping with hs3, list hs1 is: 300.
```

## <a name="hash_setupper_bound"></a><a name="upper_bound"></a> hash_set:: upper_bound

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Возвращает итератор, указывающий на первый элемент в hash_set, ключ которого больше указанного ключа.

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>Параметры

*раздел*\
Ключ-аргумент, который будет сравниваться с ключом сортировки элемента из hash_set, в котором выполняется поиск.

### <a name="return-value"></a>Возвращаемое значение

Объект `iterator` или `const_iterator` , который обращается к расположению элемента в hash_set с ключом, который равен или больше, чем ключ аргумента, или к месту последнего элемента в hash_set, если совпадение для ключа не найдено.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

```cpp
// hash_set_upper_bound.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int> :: const_iterator hs1_AcIter, hs1_RcIter;

   hs1.insert( 10 );
   hs1.insert( 20 );
   hs1.insert( 30 );

   hs1_RcIter = hs1.upper_bound( 20 );
   cout << "The first element of hash_set hs1 with a key greater "
        << "than 20 is: " << *hs1_RcIter << "." << endl;

   hs1_RcIter = hs1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( hs1_RcIter == hs1.end( ) )
      cout << "The hash_set hs1 doesn't have an element "
           << "with a key greater than 30." << endl;
   else
      cout << "The element of hash_set hs1 with a key > 40 is: "
           << *hs1_RcIter << "." << endl;

   // An element at a specific location in the hash_set can be found
   // by using a dereferenced iterator addressing the location
   hs1_AcIter = hs1.begin( );
   hs1_RcIter = hs1.upper_bound( *hs1_AcIter );
   cout << "The first element of hs1 with a key greater than "
        << endl << "that of the initial element of hs1 is: "
        << *hs1_RcIter << "." << endl;
}
```

```Output
The first element of hash_set hs1 with a key greater than 20 is: 30.
The hash_set hs1 doesn't have an element with a key greater than 30.
The first element of hs1 with a key greater than
that of the initial element of hs1 is: 20.
```

## <a name="hash_setvalue_comp"></a><a name="value_comp"></a> hash_set:: value_comp

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Извлекает копию объекта сравнения, используемого для упорядочивания элементов в объекте hash_set.

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект-функцию, которую hash_set использует для упорядочивания своих элементов, что является параметром шаблона *Compare*.

Дополнительные сведения о *сравнении*см. в подразделе "Примечания" раздела [hash_set Class](../standard-library/hash-set-class.md) .

### <a name="remarks"></a>Примечания

Сохраненный объект определяет функцию-член:

`bool operator( const Key& _xVal, const Key& _yVal );`

Возвращает значение, **`true`** Если `_xVal` предшествует и не равно `_yVal` в порядке сортировки.

Обратите внимание, что и [value_compare](../standard-library/set-class.md#value_compare) , и [key_compare](../standard-library/set-class.md#key_compare) являются синонимами для параметра шаблона *Compare*. Оба типа предоставляются для классов hash_set и hash_multiset, где они идентичны, для совместимости с классами hash_map и hash_multimap, где они различаются.

### <a name="example"></a>Пример

```cpp
// hash_set_value_comp.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;

   hash_set <int, hash_compare < int, less<int> > > hs1;
   hash_set <int, hash_compare < int, less<int> >  >::value_compare
      vc1 = hs1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of hs1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of hs1."
           << endl;
   }

   hash_set <int, hash_compare < int, greater<int> > > hs2;
   hash_set<int, hash_compare < int, greater<int> > >::value_compare
      vc2 = hs2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of hs2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of hs2."
           << endl;
   }
}
```

## <a name="hash_setvalue_compare"></a><a name="value_compare"></a> hash_set:: value_compare

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, который предоставляет два объекта-функции — бинарный предикат класса compare, который сравнивает значения двух элементов объекта hash_set для определения их относительного порядка, и унарный предикат, хэширующий элементы.

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Примечания

`value_compare` является синонимом для *характеристик*параметра шаблона.

Дополнительные сведения о *характеристиках* см. в разделе [hash_set Class](../standard-library/hash-set-class.md) .

Обратите внимание, что оба [key_compare](#key_compare) и `value_compare` являются синонимами для *Traits*признаков параметра шаблона. Оба типа предоставляются для классов hash_set и hash_multiset, где они идентичны, для совместимости с классами hash_map и hash_multimap, где они различаются.

### <a name="example"></a>Пример

См. пример для [value_comp](#value_comp) в качестве примера объявления и использования `value_compare`.

## <a name="hash_setvalue_type"></a><a name="value_type"></a> hash_set:: value_type

> [!NOTE]
> Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).

Тип, описывающий объект, хранящийся в качестве элемента объекта hash_set в смысле его возможностей как значения.

```cpp
typedef Key value_type;
```

### <a name="example"></a>Пример

```cpp
// hash_set_value_type.cpp
// compile with: /EHsc
#include <hash_set>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_set <int> hs1;
   hash_set <int>::iterator hs1_Iter;

   hash_set <int> :: value_type hsvt_Int;   // Declare value_type
   hsvt_Int = 10;             // Initialize value_type

   hash_set <int> :: key_type hskt_Int;   // Declare key_type
   hskt_Int = 20;             // Initialize key_type

   hs1.insert( hsvt_Int );         // Insert value into hs1
   hs1.insert( hskt_Int );         // Insert key into hs1

   // A hash_set accepts key_types or value_types as elements
   cout << "The hash_set has elements:";
   for ( hs1_Iter = hs1.begin( ) ; hs1_Iter != hs1.end( ); hs1_Iter++)
      cout << " " << *hs1_Iter;
   cout << "." << endl;
}
```

```Output
The hash_set has elements: 10 20.
```

## <a name="see-also"></a>См. также

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
