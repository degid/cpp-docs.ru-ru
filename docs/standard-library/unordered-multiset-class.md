---
title: Класс unordered_multiset
description: Справочник по API для класса контейнера стандартной библиотеки C++ `unordered_multiset` , который описывает объект, используемый для хранения и извлечения данных из коллекции, в которой значения содержащихся в них элементов не должны быть уникальными и в которых они используются в качестве ключевых значений. Данные не упорядочиваются автоматически.
ms.date: 9/10/2020
f1_keywords:
- unordered_set/std::unordered_multiset
- unordered_set/std::unordered_multiset::allocator_type
- unordered_set/std::unordered_multiset::const_iterator
- unordered_set/std::unordered_multiset::const_local_iterator
- unordered_set/std::unordered_multiset::const_pointer
- unordered_set/std::unordered_multiset::const_reference
- unordered_set/std::unordered_multiset::difference_type
- unordered_set/std::unordered_multiset::hasher
- unordered_set/std::unordered_multiset::iterator
- unordered_set/std::unordered_multiset::key_equal
- unordered_set/std::unordered_multiset::key_type
- unordered_set/std::unordered_multiset::local_iterator
- unordered_set/std::unordered_multiset::pointer
- unordered_set/std::unordered_multiset::reference
- unordered_set/std::unordered_multiset::size_type
- unordered_set/std::unordered_multiset::value_type
- unordered_set/std::unordered_multiset::begin
- unordered_set/std::unordered_multiset::bucket
- unordered_set/std::unordered_multiset::bucket_count
- unordered_set/std::unordered_multiset::bucket_size
- unordered_set/std::unordered_multiset::cbegin
- unordered_set/std::unordered_multiset::cend
- unordered_set/std::unordered_multiset::clear
- unordered_set/std::unordered_multiset::contains
- unordered_set/std::unordered_multiset::count
- unordered_set/std::unordered_multiset::emplace
- unordered_set/std::unordered_multiset::emplace_hint
- unordered_set/std::unordered_multiset::empty
- unordered_set/std::unordered_multiset::end
- unordered_set/std::unordered_multiset::equal_range
- unordered_set/std::unordered_multiset::erase
- unordered_set/std::unordered_multiset::find
- unordered_set/std::unordered_multiset::get_allocator
- unordered_set/std::unordered_multiset::hash
- unordered_set/std::unordered_multiset::insert
- unordered_set/std::unordered_multiset::key_eq
- unordered_set/std::unordered_multiset::load_factor
- unordered_set/std::unordered_multiset::max_bucket_count
- unordered_set/std::unordered_multiset::max_load_factor
- unordered_set/std::unordered_multiset::max_size
- unordered_set/std::unordered_multiset::rehash
- unordered_set/std::unordered_multiset::size
- unordered_set/std::unordered_multiset::swap
- unordered_set/std::unordered_multiset::unordered_multiset
- unordered_set/std::unordered_multiset::operator=
- unordered_set/std::unordered_multiset::hash_function
helpviewer_keywords:
- std::unordered_multiset
- std::unordered_multiset::allocator_type
- std::unordered_multiset::const_iterator
- std::unordered_multiset::const_local_iterator
- std::unordered_multiset::const_pointer
- std::unordered_multiset::const_reference
- std::unordered_multiset::difference_type
- std::unordered_multiset::hasher
- std::unordered_multiset::iterator
- std::unordered_multiset::key_equal
- std::unordered_multiset::key_type
- std::unordered_multiset::local_iterator
- std::unordered_multiset::pointer
- std::unordered_multiset::reference
- std::unordered_multiset::size_type
- std::unordered_multiset::value_type
- std::unordered_multiset::begin
- std::unordered_multiset::bucket
- std::unordered_multiset::bucket_count
- std::unordered_multiset::bucket_size
- std::unordered_multiset::cbegin
- std::unordered_multiset::cend
- std::unordered_multiset::clear
- std::unordered_multiset::contains
- std::unordered_multiset::count
- std::unordered_multiset::emplace
- std::unordered_multiset::emplace_hint
- std::unordered_multiset::empty
- std::unordered_multiset::end
- std::unordered_multiset::equal_range
- std::unordered_multiset::erase
- std::unordered_multiset::find
- std::unordered_multiset::get_allocator
- std::unordered_multiset::hash
- std::unordered_multiset::insert
- std::unordered_multiset::key_eq
- std::unordered_multiset::load_factor
- std::unordered_multiset::max_bucket_count
- std::unordered_multiset::max_load_factor
- std::unordered_multiset::max_size
- std::unordered_multiset::rehash
- std::unordered_multiset::size
- std::unordered_multiset::swap
- std::unordered_multiset::unordered_multiset
- std::unordered_multiset::operator=
- std::unordered_multiset::allocator_type
- std::unordered_multiset::const_iterator
- std::unordered_multiset::const_local_iterator
- std::unordered_multiset::const_pointer
- std::unordered_multiset::const_reference
- std::unordered_multiset::difference_type
- std::unordered_multiset::hasher
- std::unordered_multiset::iterator
- std::unordered_multiset::key_equal
- std::unordered_multiset::key_type
- std::unordered_multiset::local_iterator
- std::unordered_multiset::pointer
- std::unordered_multiset::reference
- std::unordered_multiset::size_type
- std::unordered_multiset::value_type
- std::unordered_multiset::begin
- std::unordered_multiset::bucket
- std::unordered_multiset::bucket_count
- std::unordered_multiset::bucket_size
- std::unordered_multiset::cbegin
- std::unordered_multiset::cend
- std::unordered_multiset::clear
- std::unordered_multiset::count
- std::unordered_multiset::emplace
- std::unordered_multiset::emplace_hint
- std::unordered_multiset::empty
- std::unordered_multiset::end
- std::unordered_multiset::equal_range
- std::unordered_multiset::erase
- std::unordered_multiset::find
- std::unordered_multiset::get_allocator
- std::unordered_multiset::hash_function
- std::unordered_multiset::insert
- std::unordered_multiset::key_eq
- std::unordered_multiset::load_factor
- std::unordered_multiset::max_bucket_count
- std::unordered_multiset::max_load_factor
- std::unordered_multiset::max_size
- std::unordered_multiset::rehash
- std::unordered_multiset::size
- std::unordered_multiset::swap
ms.assetid: 70c8dfc5-492a-4af2-84f5-1aa9cb04b71c
ms.openlocfilehash: 8252ecc7051c1bad2ca1e7683ea32206dd0f10f4
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042034"
---
# <a name="unordered_multiset-class"></a>Класс unordered_multiset

Шаблон класса описывает объект, управляющий последовательностью элементов типа с различной длиной `const Key` . Последовательность слабо упорядочена хэш-функцией, которая разделяет последовательность в упорядоченный набор подпоследовательностей, называемых блоками. В каждом блоке функция сравнения определяет, упорядочена ли каждая пара элементов соответствующим образом. Каждый элемент используется в качестве ключа сортировки и в качестве значения. Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента несколькими операциями, которые могут не зависеть от числа элементов в последовательности (постоянное время), по крайней мере, когда все блоки имеют примерно одинаковую длину. В худшем случае, когда все элементы находятся в одном блоке, количество операций пропорционально количеству элементов в последовательности (линейное время). Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Key,
    class Hash = std::hash<Key>,
    class Pred = std::equal_to<Key>,
    class Alloc = std::allocator<Key>>
class unordered_multiset;
```

### <a name="parameters"></a>Параметры

*Раздел*\
Тип ключа.

*Функции*\
Тип объекта хэш-функции.

*pred*\
Тип объекта функции сравнения на предмет равенства.

*Alloc*\
Класс распределителя.

## <a name="members"></a>Элементы

|Определение типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Тип распределителя для управления хранилищем.|
|[const_iterator](#const_iterator)|Тип постоянного итератора для управляемой последовательности.|
|[const_local_iterator](#const_local_iterator)|Тип постоянного итератора блока для управляемой последовательности.|
|[const_pointer](#const_pointer)|Тип постоянного указателя на элемент.|
|[const_reference](#const_reference)|Тип постоянной ссылки на элемент.|
|[difference_type](#difference_type)|Тип расстояния со знаком между двумя элементами.|
|[Hasher](#hasher)|Тип хэш-функции.|
|[iterator](#iterator)|Тип итератора для управляемой последовательности.|
|[key_equal](#key_equal)|Тип функции сравнения.|
|[key_type](#key_type)|Тип ключа упорядочения.|
|[local_iterator](#local_iterator)|Тип итератора блока для управляемой последовательности.|
|[pointer](#pointer)|Тип указателя на элемент.|
|[reference](#reference)|Тип ссылки на элемент.|
|[size_type](#size_type)|Тип беззнакового расстояния между двумя элементами.|
|[value_type](#value_type)|Тип элемента.|

|Функция-член|Описание|
|-|-|
|[begin](#begin)|Задает начало управляемой последовательности.|
|[период](#bucket)|Получает номер блока для значения ключа.|
|[bucket_count](#bucket_count)|Получает количество блоков.|
|[bucket_size](#bucket_size)|Получает размер блока.|
|[cbegin](#cbegin)|Задает начало управляемой последовательности.|
|[cend](#cend)|Задает конец управляемой последовательности.|
|[clear](#clear)|Удаляет все элементы.|
|[содержит](#contains)<sup>c++ 20</sup>|Проверяет, существует ли элемент с указанным ключом.|
|[count](#count)|Определяет количество элементов, соответствующих заданному ключу.|
|[emplace](#emplace)|Добавляет элемент, созданный на месте.|
|[emplace_hint](#emplace_hint)|Добавляет элемент, созданный на месте, с подсказкой.|
|[empty](#empty)|Проверяет отсутствие элементов.|
|[end](#end)|Задает конец управляемой последовательности.|
|[equal_range](#equal_range)|Находит диапазон, соответствующий указанному ключу.|
|[erase](#erase)|Удаляет элементы в указанных позициях.|
|[find](#find)|Определяет элемент, соответствующий указанному ключу.|
|[get_allocator](#get_allocator)|Возвращает сохраненный объект распределителя.|
|[hash_function](#hash)|Получает сохраненный объект хэш-функции.|
|[insert](#insert)|Добавляет элементы.|
|[key_eq](#key_eq)|Получает сохраненный объект функции сравнения.|
|[load_factor](#load_factor)|Подсчитывает среднее число элементов в блоке.|
|[max_bucket_count](#max_bucket_count)|Получает максимальное количество блоков.|
|[max_load_factor](#max_load_factor)|Возвращает или задает максимальное количество элементов в блоке.|
|[max_size](#max_size)|Возвращает максимальный размер управляемой последовательности.|
|[rehash](#rehash)|Повторно создает хэш-таблицу.|
|[size](#size)|Подсчитывает количество элементов.|
|[swap](#swap)|Меняет местами содержимое двух контейнеров.|
|[unordered_multiset](#unordered_multiset)|Создает объект контейнера.|

|Оператор|Описание|
|-|-|
|[unordered_multiset::operator=](#op_eq)|Копирует хэш-таблицу.|

## <a name="remarks"></a>Комментарии

Объект упорядочивает управляемую им последовательность путем вызова двух сохраненных объектов — объекта функции сравнения типа [unordered_multiset::key_equal](#key_equal) и объекта хэш-функции типа [unordered_multiset::hasher](#hasher). Доступ к первому сохраненному объекту осуществляется путем вызова функции члена [unordered_multiset:: key_eq](#key_eq) `()` ; доступ к второму сохраненному объекту осуществляется путем вызова функции члена [unordered_multiset:: hash_function](#hash) `()` . В частности, для всех значений `X` и `Y` типа `Key` вызов `key_eq()(X, Y)` возвращает значение true, только если два значения аргументов имеют соответствующий порядок; вызов `hash_function()(keyval)` создает распределение значений типа `size_t`. В отличие от [класса Unordered_set Class](../standard-library/unordered-set-class.md), объект типа не `unordered_multiset` гарантирует, что `key_eq()(X, Y)` всегда имеет значение false для любого из двух элементов управляемой последовательности. (Ключи не обязательно должны быть уникальными.)

Объект также хранит максимальный коэффициент нагрузки, который определяет максимальное желаемое среднее количество элементов в блоке. Если вставка элемента приводит к превышению максимального коэффициента загрузки [unordered_multiset:: load_factor](#load_factor) `()` , контейнер увеличивает количество сегментов и перестраивает хэш-таблицу по мере необходимости.

Фактический порядок элементов в управляемой последовательности зависит от хэш-функции, функции сравнения, порядка вставки, максимального коэффициента нагрузки и текущего числа блоков. Обычно невозможно предсказать порядок элементов в управляемой последовательности. Однако всегда можно сохранять уверенность, что любое подмножество элементов, имеющих соответствующий порядок, будет расположено по соседству в управляемой последовательности.

Объект выделяет и освобождает хранилище для управляемой им последовательности с помощью сохраненного объекта распределителя типа [unordered_multiset::allocator_type](#allocator_type). Такой объект распределителя должен иметь тот же внешний интерфейс, что и объект типа `allocator` . Обратите внимание, что сохраненный объект распределителя не копируется, когда назначается объект контейнера.

## <a name="requirements"></a>Требования

**Заголовок:**\<unordered_set>

**Пространство имен:** std

## <a name="unordered_multisetallocator_type"></a><a name="allocator_type"></a> unordered_multiset:: allocator_type

Тип распределителя для управления хранилищем.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Комментарии

Этот тип является синонимом для параметра шаблона `Alloc`.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_allocator_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
typedef std::allocator<std::pair<const char, int> > Myalloc;
int main()
{
    Myset c1;

    Myset::allocator_type al = c1.get_allocator();
    std::cout << "al == std::allocator() is "
        << std::boolalpha << (al == Myalloc()) << std::endl;

    return (0);
}
```

```Output
al == std::allocator() is true
```

## <a name="unordered_multisetbegin"></a><a name="begin"></a> unordered_multiset:: Begin

Задает начало управляемой последовательности или сегмента.

```cpp
iterator begin();

const_iterator begin() const;

local_iterator begin(size_type nbucket);

const_local_iterator begin(size_type nbucket) const;
```

### <a name="parameters"></a>Параметры

*нбуккет*\
Номер сегмента.

### <a name="remarks"></a>Комментарии

Первые две функции-члены возвращают прямой итератор, указывающий на первый элемент последовательности (или на место сразу за концом пустой последовательности). Последние две функции-члена возвращают прямой итератор, указывающий на первый элемент контейнера *нбуккет* (или сразу за концом пустого контейнера).

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_begin.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect first two items "[c] [b]"
    Myset::iterator it2 = c1.begin();
    std::cout << "[" << *it2 << "] ";
    ++it2;
    std::cout << "[" << *it2 << "] ";
    std::cout << std::endl;

    // inspect bucket containing 'a'
    Myset::const_local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << "[" << *lit << "] ";

    return (0);
}
```

```Output
[c] [b] [a]
[c] [b]
[a]
```

## <a name="unordered_multisetbucket"></a><a name="bucket"></a> unordered_multiset:: контейнер

Получает номер блока для значения ключа.

```cpp
size_type bucket(const Key& keyval) const;
```

### <a name="parameters"></a>Параметры

*кэйвал*\
Значение ключа для сопоставления.

### <a name="remarks"></a>Комментарии

Функция-член возвращает номер контейнера, который в настоящий момент соответствует значению ключа `keyval`.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_bucket.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // display buckets for keys
    Myset::size_type bs = c1.bucket('a');
    std::cout << "bucket('a') == " << bs << std::endl;
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)
        << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
bucket('a') == 7
bucket_size(7) == 1
```

## <a name="unordered_multisetbucket_count"></a><a name="bucket_count"></a> unordered_multiset:: bucket_count

Получает количество блоков.

```cpp
size_type bucket_count() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает текущее число блоков.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_bucket_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect current parameters
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    // change max_load_factor and redisplay
    c1.max_load_factor(0.10f);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    // rehash and redisplay
    c1.rehash(100);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 4

bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 0.1

bucket_count() == 128
load_factor() == 0.0234375
max_bucket_count() == 128
max_load_factor() == 0.1
```

## <a name="unordered_multisetbucket_size"></a><a name="bucket_size"></a> unordered_multiset:: bucket_size

Получает размер сегмента.

```cpp
size_type bucket_size(size_type nbucket) const;
```

### <a name="parameters"></a>Параметры

*нбуккет*\
Номер сегмента.

### <a name="remarks"></a>Комментарии

Функции элементов возвращают размер сегмента *нбуккет*.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_bucket_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // display buckets for keys
    Myset::size_type bs = c1.bucket('a');
    std::cout << "bucket('a') == " << bs << std::endl;
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)
        << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
bucket('a') == 7
bucket_size(7) == 1
```

## <a name="unordered_multisetcbegin"></a><a name="cbegin"></a> unordered_multiset:: cbegin

Возвращает **`const`** итератор, который обращается к первому элементу в диапазоне.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`const`** Итератор прямого доступа, указывающий на первый элемент диапазона, или расположение непосредственно за концом пустого диапазона (для пустого диапазона `cbegin() == cend()` ).

### <a name="remarks"></a>Комментарии

Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.

Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере рекомендуется использовать `Container` изменяемый (не- **`const`** ) контейнер любого типа, который поддерживает `begin()` и `cbegin()` .

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator

auto i2 = Container.cbegin();
// i2 is Container<T>::const_iterator
```

## <a name="unordered_multisetcend"></a><a name="cend"></a> unordered_multiset:: cend

Возвращает **`const`** итератор, который обращается к расположению сразу за последним элементом в диапазоне.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`const`** Итератор прямого доступа, указывающий на место сразу за концом диапазона.

### <a name="remarks"></a>Комментарии

`cend` используется для проверки того, прошел ли итератор конец диапазона.

Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере рекомендуется использовать `Container` изменяемый (не- **`const`** ) контейнер любого типа, который поддерживает `end()` и `cend()` .

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator

auto i2 = Container.cend();
// i2 is Container<T>::const_iterator
```

Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.

## <a name="unordered_multisetclear"></a><a name="clear"></a> unordered_multiset:: Clear

Удаляет все элементы.

```cpp
void clear();
```

### <a name="remarks"></a>Комментарии

Функция-член вызывает [unordered_multiset::erase](#erase)`(` [unordered_multiset::begin](#begin)`(),` [unordered_multiset::end](#end)`())`.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_clear.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert('d');
    c1.insert('e');

    // display contents "[e] [d] "
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
size == 0
empty() == true

[e] [d]
size == 2
empty() == false
```

## <a name="unordered_multisetconst_iterator"></a><a name="const_iterator"></a> unordered_multiset:: const_iterator

Тип постоянного итератора для управляемой последовательности.

```cpp
typedef T1 const_iterator;
```

### <a name="remarks"></a>Комментарии

Тип описывает объект, который можно использовать в качестве постоянного прямого итератора для управляемой последовательности. Он описан здесь как синоним для типа `T1`, определяемого реализацией.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_const_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="unordered_multisetconst_local_iterator"></a><a name="const_local_iterator"></a> unordered_multiset:: const_local_iterator

Тип постоянного итератора блока для управляемой последовательности.

```cpp
typedef T5 const_local_iterator;
```

### <a name="remarks"></a>Комментарии

Этот тип описывает объект, который можно использовать в качестве постоянного прямого итератора для блока. Он описан здесь как синоним для типа `T5`, определяемого реализацией.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_const_local_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect bucket containing 'a'
    Myset::const_local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << "[" << *lit << "] ";

    return (0);
}
```

```Output
[c] [b] [a]
[a]
```

## <a name="unordered_multisetconst_pointer"></a><a name="const_pointer"></a> unordered_multiset:: const_pointer

Тип постоянного указателя на элемент.

```cpp
typedef Alloc::const_pointer const_pointer;
```

### <a name="remarks"></a>Комментарии

Этот тип описывает объект, который можно использовать в качестве постоянного указателя на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_const_pointer.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Myset::const_pointer p = &*it;
        std::cout << "[" << *p << "] ";
        }
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="unordered_multisetconst_reference"></a><a name="const_reference"></a> unordered_multiset:: const_reference

Тип постоянной ссылки на элемент.

```cpp
typedef Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Комментарии

Тип описывает объект, который можно использовать в качестве постоянной ссылки на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_const_reference.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Myset::const_reference ref = *it;
        std::cout << "[" << ref << "] ";
        }
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="unordered_multisetcontains"></a><a name="contains"></a> unordered_multiset:: Contains

Проверяет, существует ли элемент с указанным ключом в `unordered_multiset` .

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

`template<class K> bool contains(const K& key) const` принимает участие в разрешении перегрузки только в `key_compare` том случае, если является прозрачным.

### <a name="example"></a>Пример

```cpp
// Requires /std:c++latest
#include <unordered_set>
#include <iostream>

int main()
{
    std::unordered_multiset<int> theUnorderedMultiset = { 1, 2, 3 };

    std::cout << std::boolalpha; // so booleans show as 'true' or 'false'
    std::cout << theUnorderedMultiset.contains(1) << '\n';
    std::cout << theUnorderedMultiset.contains(4) << '\n';

    return 0;
}
```

```Output
true
false
```

## <a name="unordered_multisetcount"></a><a name="count"></a> unordered_multiset:: count

Определяет количество элементов, соответствующих заданному ключу.

```cpp
size_type count(const Key& keyval) const;
```

### <a name="parameters"></a>Параметры

*кэйвал*\
Искомое значение ключа.

### <a name="remarks"></a>Комментарии

Функция – член возвращает количество элементов в диапазоне, ограниченном [unordered_multiset:: equal_range](#equal_range) `(keyval)` .

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    std::cout << "count('A') == " << c1.count('A') << std::endl;
    std::cout << "count('b') == " << c1.count('b') << std::endl;
    std::cout << "count('C') == " << c1.count('C') << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
count('A') == 0
count('b') == 1
count('C') == 0
```

## <a name="unordered_multisetdifference_type"></a><a name="difference_type"></a> unordered_multiset::difference_type

Тип расстояния со знаком между двумя элементами.

```cpp
typedef T3 difference_type;
```

### <a name="remarks"></a>Комментарии

Тип целого числа со знаком описывает объект, который может представлять разницу между адресами любых двух элементов в управляемой последовательности. Он описан здесь как синоним для типа `T3`, определяемого реализацией.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_difference_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // compute positive difference
    Myset::difference_type diff = 0;
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        ++diff;
    std::cout << "end()-begin() == " << diff << std::endl;

    // compute negative difference
    diff = 0;
    for (Myset::const_iterator it = c1.end();
        it != c1.begin(); --it)
        --diff;
    std::cout << "begin()-end() == " << diff << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
end()-begin() == 3
begin()-end() == -3
```

## <a name="unordered_multisetemplace"></a><a name="emplace"></a> unordered_multiset:: emplace

Вставляет элемент, созданный на месте (операции копирования или перемещения не выполняются).

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>Параметры

*args*\
Аргументы, передаваемые для создания элемента, который будет вставлен в объект unordered_multiset.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на вновь вставленный элемент.

### <a name="remarks"></a>Комментарии

Эта функция не делает недействительными никакие ссылки на элементы контейнера, но она может сделать недействительными все итераторы к контейнеру.

Если во время вставки возникает исключение, но оно произошло не в хэш-функции контейнера, контейнер не изменяется. Если исключение вызывается в хэш-функции, результат не определен.

Пример кода см. в разделе [multiset::emplace](../standard-library/multiset-class.md#emplace).

## <a name="unordered_multisetemplace_hint"></a><a name="emplace_hint"></a> unordered_multiset:: emplace_hint

Вставляет созданный элемент на место (операции копирования или перемещения не выполняются) с указанием о размещении.

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>Параметры

*args*\
Аргументы, передаваемые для создания элемента, который будет вставлен в объект unordered_multiset.

*которому*\
Подсказка о месте начала поиска правильной точки вставки.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на вновь вставленный элемент.

### <a name="remarks"></a>Комментарии

Эта функция не делает недействительными никакие ссылки на элементы контейнера, но она может сделать недействительными все итераторы к контейнеру.

Если во время вставки возникает исключение, но оно произошло не в хэш-функции контейнера, контейнер не изменяется. Если исключение вызывается в хэш-функции, результат не определен.

Пример кода см. в разделе [set::emplace_hint](../standard-library/set-class.md#emplace_hint).

## <a name="unordered_multisetempty"></a><a name="empty"></a> unordered_multiset:: Empty

Проверяет отсутствие элементов.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Комментарии

Эта функция-член возвращает значение true для пустой управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_empty.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert('d');
    c1.insert('e');

    // display contents "[e] [d]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
size == 0
empty() == true

[e] [d]
size == 2
empty() == false
```

## <a name="unordered_multisetend"></a><a name="end"></a> unordered_multiset:: end

Задает конец управляемой последовательности.

```cpp
iterator end();
const_iterator end() const;
local_iterator end(size_type nbucket);
const_local_iterator end(size_type nbucket) const;
```

### <a name="parameters"></a>Параметры

*нбуккет*\
Номер сегмента.

### <a name="remarks"></a>Комментарии

Первые две функции-члены возвращают прямой итератор, указывающий на место сразу за концом последовательности. Последние две функции-члена возвращают прямой итератор, указывающий сразу за концом сегмента *нбуккет*.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_end.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect last two items "[a] [b]"
    Myset::iterator it2 = c1.end();
    --it2;
    std::cout << "[" << *it2 << "] ";
    --it2;
    std::cout << "[" << *it2 << "] ";
    std::cout << std::endl;

    // inspect bucket containing 'a'
    Myset::const_local_iterator lit = c1.end(c1.bucket('a'));
    --lit;
    std::cout << "[" << *lit << "] ";

    return (0);
}
```

```Output
[c] [b] [a]
[a] [b]
[a]
```

## <a name="unordered_multisetequal_range"></a><a name="equal_range"></a> unordered_multiset:: equal_range

Находит диапазон, соответствующий указанному ключу.

```cpp
std::pair<iterator, iterator>
    equal_range(const Key& keyval);

std::pair<const_iterator, const_iterator>
    equal_range(const Key& keyval) const;
```

### <a name="parameters"></a>Параметры

*кэйвал*\
Искомое значение ключа.

### <a name="remarks"></a>Комментарии

Функция-член возвращает пару итераторов `X` , что `[X.first, X.second)` разделяет только те элементы управляемой последовательности, которые имеют эквивалентное упорядочение с помощью *кэйвал*. Если таких элементов не существует, оба итератора имеют значение `end()`.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_equal_range.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // display results of failed search
    std::pair<Myset::iterator, Myset::iterator> pair1 =
        c1.equal_range('x');
    std::cout << "equal_range('x'):";
    for (; pair1.first != pair1.second; ++pair1.first)
        std::cout << "[" << *pair1.first << "] ";
    std::cout << std::endl;

    // display results of successful search
    pair1 = c1.equal_range('b');
    std::cout << "equal_range('b'):";
    for (; pair1.first != pair1.second; ++pair1.first)
        std::cout << "[" << *pair1.first << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
equal_range('x'):
equal_range('b'): [b]
```

## <a name="unordered_multiseterase"></a><a name="erase"></a> unordered_multiset:: Erase

Удаляет элемент или диапазон элементов в объекте unordered_multiset с заданных позиций или удаляет элементы, соответствующие заданному ключу.

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

Для первых двух функций-членов двунаправленный итератор, указывающий на первый элемент, оставшийся после удаления элементов, или на последний элемент объекта unordered_multiset, если такого элемента не существует.

Для третьей функции-члена возвращает число элементов, которые были удалены из объекта unordered_multiset.

### <a name="remarks"></a>Комментарии

Пример кода см. в разделе [set::erase](../standard-library/set-class.md#erase).

## <a name="unordered_multisetfind"></a><a name="find"></a> unordered_multiset:: Find

Определяет элемент, соответствующий указанному ключу.

```cpp
const_iterator find(const Key& keyval) const;
```

### <a name="parameters"></a>Параметры

*кэйвал*\
Искомое значение ключа.

### <a name="remarks"></a>Комментарии

Функция – член возвращает [unordered_multiset:: equal_range](#equal_range) `(keyval).first` .

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_find.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // try to find and fail
    std::cout << "find('A') == "
        << std::boolalpha << (c1.find('A') != c1.end()) << std::endl;

    // try to find and succeed
    Myset::iterator it = c1.find('b');
    std::cout << "find('b') == "
        << std::boolalpha << (it != c1.end())
        << ": [" << *it << "] " << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
find('A') == false
find('b') == true: [b]
```

## <a name="unordered_multisetget_allocator"></a><a name="get_allocator"></a> unordered_multiset:: get_allocator

Возвращает сохраненный объект распределителя.

```cpp
Alloc get_allocator() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает сохраненный объект распределителя.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_get_allocator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
typedef std::allocator<std::pair<const char, int> > Myalloc;
int main()
{
    Myset c1;

    Myset::allocator_type al = c1.get_allocator();
    std::cout << "al == std::allocator() is "
        << std::boolalpha << (al == Myalloc()) << std::endl;

    return (0);
}
```

```Output
al == std::allocator() is true
```

## <a name="unordered_multisethash_function"></a><a name="hash"></a> unordered_multiset:: hash_function

Получает сохраненный объект хэш-функции.

```cpp
Hash hash_function() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает сохраненный объект хэш-функции.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_hash_function.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    Myset::hasher hfn = c1.hash_function();
    std::cout << "hfn('a') == " << hfn('a') << std::endl;
    std::cout << "hfn('b') == " << hfn('b') << std::endl;

    return (0);
}
```

```Output
hfn('a') == 1630279
hfn('b') == 1647086
```

## <a name="unordered_multisethasher"></a><a name="hasher"></a> unordered_multiset:: hash

Тип хэш-функции.

```cpp
typedef Hash hasher;
```

### <a name="remarks"></a>Комментарии

Этот тип является синонимом для параметра шаблона `Hash`.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_hasher.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    Myset::hasher hfn = c1.hash_function();
    std::cout << "hfn('a') == " << hfn('a') << std::endl;
    std::cout << "hfn('b') == " << hfn('b') << std::endl;

    return (0);
}
```

```Output
hfn('a') == 1630279
hfn('b') == 1647086
```

## <a name="unordered_multisetinsert"></a><a name="insert"></a> unordered_multiset:: INSERT

Вставляет элемент или диапазон элементов в unordered_multiset.

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
Значение элемента, вставляемого в unordered_multiset.

*Where*\
Место начала поиска правильной точки вставки.

*валти*\
Параметр шаблона, указывающий тип аргумента, который unordered_multiset может использовать для создания элемента [value_type](../standard-library/map-class.md#value_type), и идеальное перенаправление *Val* в качестве аргумента.

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

Если исключение вызывается во время вставки одного элемента, но оно не вызывается в хэш-функции контейнера, состояние контейнера не изменяется. Если исключение вызывается в хэш-функции, результат не определен. Если во время вставки нескольких элементов вызывается исключение, контейнер остается в неопределенном, но допустимом состоянии.

[value_type](../standard-library/map-class.md#value_type) контейнера — это определение типа, принадлежащее контейнеру и, для набора, `unordered_multiset<V>::value_type` имеет тип `const V`.

Функция-член Range (5) вставляет последовательность значений элементов в unordered_multiset, соответствующую каждому элементу, адресованному итератором в диапазоне. `[First, Last)` следовательно, *last* не вставляется. Контейнер функции-члена `end()` ссылается на позицию сразу после последнего элемента в контейнере. Например, оператор `m.insert(v.begin(), v.end());` пытается вставить все элементы `v` в `m`.

Функция — член списка инициализаторов (6) использует [initializer_list](../standard-library/initializer-list.md) для копирования элементов в unordered_multiset.

Сведения о вставке элемента, созданного на месте (т. е. без выполнения операций копирования или перемещения), см. в описании функций [unordered_multiset::emplace](#emplace) и [unordered_multiset::emplace_hint](#emplace_hint).

Пример кода см. в разделе [multiset::insert](../standard-library/multiset-class.md#insert).

## <a name="unordered_multisetiterator"></a><a name="iterator"></a> unordered_multiset:: итератор

Тип, предоставляющий [прямой итератор](../standard-library/forward-iterator-tag-struct.md) константы, может считывать элементы в объекте unordered_multiset.

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Пример

Пример объявления и использования **итератора** см. в разделе [begin](../standard-library/multiset-class.md#begin).

## <a name="unordered_multisetkey_eq"></a><a name="key_eq"></a> unordered_multiset:: key_eq

Получает сохраненный объект функции сравнения.

```cpp
Pred key_eq() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает сохраненный объект функции сравнения.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_key_eq.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    Myset::key_equal cmpfn = c1.key_eq();
    std::cout << "cmpfn('a', 'a') == "
        << std::boolalpha << cmpfn('a', 'a') << std::endl;
    std::cout << "cmpfn('a', 'b') == "
        << std::boolalpha << cmpfn('a', 'b') << std::endl;

    return (0);
}
```

```Output
cmpfn('a', 'a') == true
cmpfn('a', 'b') == false
```

## <a name="unordered_multisetkey_equal"></a><a name="key_equal"></a> unordered_multiset:: key_equal

Тип функции сравнения.

```cpp
typedef Pred key_equal;
```

### <a name="remarks"></a>Комментарии

Этот тип является синонимом для параметра шаблона `Pred`.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_key_equal.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    Myset::key_equal cmpfn = c1.key_eq();
    std::cout << "cmpfn('a', 'a') == "
        << std::boolalpha << cmpfn('a', 'a') << std::endl;
    std::cout << "cmpfn('a', 'b') == "
        << std::boolalpha << cmpfn('a', 'b') << std::endl;

    return (0);
}
```

```Output
cmpfn('a', 'a') == true
cmpfn('a', 'b') == false
```

## <a name="unordered_multisetkey_type"></a><a name="key_type"></a> unordered_multiset:: key_type

Тип ключа упорядочения.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Комментарии

Этот тип является синонимом для параметра шаблона `Key`.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_key_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // add a value and reinspect
    Myset::key_type key = 'd';
    Myset::value_type val = key;
    c1.insert(val);

    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
[d] [c] [b] [a]
```

## <a name="unordered_multisetload_factor"></a><a name="load_factor"></a> unordered_multiset:: load_factor

Подсчитывает среднее число элементов в блоке.

```cpp
float load_factor() const;
```

### <a name="remarks"></a>Комментарии

Функция – член возвращает `(float)` [unordered_multiset:: size](#size) `() / (float)` [unordered_multiset:: bucket_count](#bucket_count) `()` , среднее число элементов на сегмент.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_load_factor.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect current parameters
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    // change max_load_factor and redisplay
    c1.max_load_factor(0.10f);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    // rehash and redisplay
    c1.rehash(100);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    return (0);
}
```

## <a name="unordered_multisetlocal_iterator"></a><a name="local_iterator"></a> unordered_multiset:: local_iterator

Тип итератора контейнера.

```cpp
typedef T4 local_iterator;
```

### <a name="remarks"></a>Комментарии

Этот тип описывает объект, который можно использовать в качестве прямого итератора для контейнера. Он описан здесь как синоним для типа `T4`, определяемого реализацией.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_local_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect bucket containing 'a'
    Myset::local_iterator lit = c1.begin(c1.bucket('a'));
    std::cout << "[" << *lit << "] ";

    return (0);
}
```

```Output
[c] [b] [a]
[a]
```

## <a name="unordered_multisetmax_bucket_count"></a><a name="max_bucket_count"></a> unordered_multiset:: max_bucket_count

Получает максимальное количество блоков.

```cpp
size_type max_bucket_count() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает максимальное количество блоков, которое разрешено в настоящее время.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_max_bucket_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect current parameters
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    // change max_load_factor and redisplay
    c1.max_load_factor(0.10f);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    // rehash and redisplay
    c1.rehash(100);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 4

bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 0.1

bucket_count() == 128
load_factor() == 0.0234375
max_bucket_count() == 128
max_load_factor() == 0.1
```

## <a name="unordered_multisetmax_load_factor"></a><a name="max_load_factor"></a> unordered_multiset:: max_load_factor

Возвращает или задает максимальное количество элементов в блоке.

```cpp
float max_load_factor() const;

void max_load_factor(float factor);
```

### <a name="parameters"></a>Параметры

*многофакторной*\
Новый коэффициент максимальной нагрузки.

### <a name="remarks"></a>Комментарии

Первая функция-член возвращает сохраненный коэффициент максимальной нагрузки. Вторая функция – член заменяет хранимую максимальную степень нагрузки на *Коэффициент*.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_max_load_factor.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect current parameters
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    // change max_load_factor and redisplay
    c1.max_load_factor(0.10f);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    // rehash and redisplay
    c1.rehash(100);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_bucket_count() == "
        << c1.max_bucket_count() << std::endl;
    std::cout << "max_load_factor() == "
        << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 4

bucket_count() == 8
load_factor() == 0.375
max_bucket_count() == 8
max_load_factor() == 0.1

bucket_count() == 128
load_factor() == 0.0234375
max_bucket_count() == 128
max_load_factor() == 0.1
```

## <a name="unordered_multisetmax_size"></a><a name="max_size"></a> unordered_multiset:: max_size

Возвращает максимальный размер управляемой последовательности.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает длину самой длинной последовательности, которой объект может управлять.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_max_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    std::cout << "max_size() == " << c1.max_size() << std::endl;

    return (0);
}
```

```Output
max_size() == 4294967295
```

## <a name="unordered_multisetoperator"></a><a name="op_eq"></a> unordered_multiset::operator=

Копирует хэш-таблицу.

```cpp
unordered_multiset& operator=(const unordered_multiset& right);

unordered_multiset& operator=(unordered_multiset&& right);
```

### <a name="parameters"></a>Параметры

*right*\
[unordered_multiset](../standard-library/unordered-multiset-class.md) копируется в `unordered_multiset`.

### <a name="remarks"></a>Комментарии

После стирания любых существующих элементов в `unordered_multiset` `operator=` копирует или перемещает содержимое *непосредственно* в `unordered_multiset` .

### <a name="example"></a>Пример

```cpp
// unordered_multiset_operator_as.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

int main( )
{
    using namespace std;
    unordered_multiset<int> v1, v2, v3;
    unordered_multiset<int>::iterator iter;

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

## <a name="unordered_multisetpointer"></a><a name="pointer"></a> unordered_multiset::p оинтер

Тип указателя на элемент.

```cpp
typedef Alloc::pointer pointer;
```

### <a name="remarks"></a>Комментарии

Этот тип описывает объект, который можно использовать в качестве указателя на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_pointer.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Myset::key_type key = *it;
        Myset::pointer p = &key;
        std::cout << "[" << *p << "] ";
        }
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="unordered_multisetreference"></a><a name="reference"></a> unordered_multiset:: Reference

Тип ссылки на элемент.

```cpp
typedef Alloc::reference reference;
```

### <a name="remarks"></a>Комментарии

Тип описывает объект, который можно использовать в качестве ссылки на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_reference.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::iterator it = c1.begin();
        it != c1.end(); ++it)
        {
        Myset::key_type key = *it;
        Myset::reference ref = key;
        std::cout << "[" << ref << "] ";
        }
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="unordered_multisetrehash"></a><a name="rehash"></a> unordered_multiset:: rehash

Повторно создает хэш-таблицу.

```cpp
void rehash(size_type nbuckets);
```

### <a name="parameters"></a>Параметры

*нбуккетс*\
Требуемое число сегментов.

### <a name="remarks"></a>Комментарии

Функция-член изменяет количество контейнеров, чтобы они были как минимум *нбуккетс* и перестраивает хэш-таблицу по мере необходимости.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_rehash.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect current parameters
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    // change max_load_factor and redisplay
    c1.max_load_factor(0.10f);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;
    std::cout << std::endl;

    // rehash and redisplay
    c1.rehash(100);
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
bucket_count() == 8
load_factor() == 0.375
max_load_factor() == 4

bucket_count() == 8
load_factor() == 0.375
max_load_factor() == 0.1

bucket_count() == 128
load_factor() == 0.0234375
max_load_factor() == 0.1
```

## <a name="unordered_multisetsize"></a><a name="size"></a> unordered_multiset:: size

Подсчитывает количество элементов.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает длину управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // clear the container and reinspect
    c1.clear();
    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;
    std::cout << std::endl;

    c1.insert('d');
    c1.insert('e');

    // display contents "[e] [d]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    std::cout << "size == " << c1.size() << std::endl;
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
size == 0
empty() == true

[e] [d]
size == 2
empty() == false
```

## <a name="unordered_multisetsize_type"></a><a name="size_type"></a> unordered_multiset:: size_type

Тип беззнакового расстояния между двумя элементами.

```cpp
typedef T2 size_type;
```

### <a name="remarks"></a>Комментарии

Целочисленный тип без знака описывает объект, который может представлять длину любой управляемой последовательности. Он описан здесь как синоним для типа `T2`, определяемого реализацией.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_size_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;
    Myset::size_type sz = c1.size();

    std::cout << "size == " << sz << std::endl;

    return (0);
}
```

```Output
size == 0
```

## <a name="unordered_multisetswap"></a><a name="swap"></a> unordered_multiset:: swap

Меняет местами содержимое двух контейнеров.

```cpp
void swap(unordered_multiset& right);
```

### <a name="parameters"></a>Параметры

*right*\
Контейнер для замены.

### <a name="remarks"></a>Комментарии

Функция – член меняет местами управляемые последовательности между **`*this`** и *вправо*. Если [unordered_multiset:: get_allocator](#get_allocator) `() == right.get_allocator()` , он делает это в константном времени, он создает исключение только в результате копирования сохраненного объекта признаков типа `Tr` и не делает недействительными ссылки, указатели или итераторы, обозначающие элементы в двух управляемых последовательностях. В противном случае она выполняет ряд назначений элементов и вызовов конструктора, пропорционально количеству элементов в двух управляемых последовательностях.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_swap.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    Myset c2;

    c2.insert('d');
    c2.insert('e');
    c2.insert('f');

    c1.swap(c2);

    // display contents "[f] [e] [d]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    swap(c1, c2);

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
[f] [e] [d]
[c] [b] [a]
```

## <a name="unordered_multisetunordered_multiset"></a><a name="unordered_multiset"></a> unordered_multiset:: unordered_multiset

Создает объект контейнера.

```cpp
unordered_multiset(
    const unordered_multiset& Right);

explicit unordered_multiset(
    size_type Bucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Comp(),
    const Allocator& Al = Alloc());

unordered_multiset(
    unordered_multiset&& Right);

unordered_set(
    initializer_list<Type> IList);

unordered_set(
    initializer_list<Typ> IList,
    size_type Bucket_count);

unordered_set(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash);

unordered_set(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash,
    const Key& Key);

unordered_set(
    initializer_list<Type> IList,
    size_type Bucket_count,
    const Hash& Hash,
    const Key& Key,
    const Allocator& Al);

template <class InputIterator>
unordered_multiset(
    InputIterator First,
    InputIterator Last,
    size_type Bucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Comp(),
    const Allocator& Al = Alloc());
```

### <a name="parameters"></a>Параметры

*InputIterator*\
Тип итератора.

*Al*\
Объект распределителя для сохранения.

*Соответствовал*\
Объект функции сравнения для сохранения.

*Функции*\
Объект хэш-функции для сохранения.

*Bucket_count*\
Минимальное количество блоков.

*right*\
Контейнер для копирования.

*Интерфейс*\
Объект initializer_list, из которого следует выполнить копирование.

### <a name="remarks"></a>Комментарии

Первый конструктор задает копию последовательности, управляемой по *правому краю*. Второй конструктор определяет управляемую пустую последовательность. Третий конструктор добавляет последовательность значений элементов `[First, Last)`. Четвертый конструктор указывает копию последовательности, перемещая ее *вправо*.

Все конструкторы также инициализируют ряд сохраненных значений. Для конструктора копии значения получаются *справа*. В противном случае:

Минимальное число контейнеров — аргумент, *Bucket_count*, если он есть; в противном случае это значение по умолчанию, описываемое здесь как значение, определяемое реализацией `N0` .

Объект хэш-функции — это *хэш*аргумента, если он есть; в противном случае — значение `Hash()` .

Объект функции сравнения — это аргумент *comp*, если он есть; в противном случае — значение `Comp()` .

Объект распределителя — это аргумент *Al*, если он есть; в противном случае — значение `Alloc()` .

## <a name="unordered_multisetvalue_type"></a><a name="value_type"></a> unordered_multiset:: value_type

Тип элемента.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Комментарии

Тип описывает элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_multiset_value_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // add a value and reinspect
    Myset::key_type key = 'd';
    Myset::value_type val = key;
    c1.insert(val);

    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
[d] [c] [b] [a]
```

## <a name="see-also"></a>См. также раздел

[<unordered_set>](../standard-library/unordered-set.md)\
[Контейнера](../cpp/containers-modern-cpp.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
