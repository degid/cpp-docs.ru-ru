---
title: Класс unordered_set
description: Справочник по API для класса контейнера стандартной библиотеки C++ `unordered_set` , который используется для хранения и извлечения данных из неупорядоченной коллекции.
ms.date: 9/9/2020
f1_keywords:
- unordered_set/std::unordered_set
- unordered_set/std::unordered_set::allocator_type
- unordered_set/std::unordered_set::const_iterator
- unordered_set/std::unordered_set::const_local_iterator
- unordered_set/std::unordered_set::const_pointer
- unordered_set/std::unordered_set::const_reference
- unordered_set/std::unordered_set::difference_type
- unordered_set/std::unordered_set::hasher
- unordered_set/std::unordered_set::iterator
- unordered_set/std::unordered_set::key_equal
- unordered_set/std::unordered_set::key_type
- unordered_set/std::unordered_set::local_iterator
- unordered_set/std::unordered_set::pointer
- unordered_set/std::unordered_set::reference
- unordered_set/std::unordered_set::size_type
- unordered_set/std::unordered_set::value_type
- unordered_set/std::unordered_set::begin
- unordered_set/std::unordered_set::bucket
- unordered_set/std::unordered_set::bucket_count
- unordered_set/std::unordered_set::bucket_size
- unordered_set/std::unordered_set::cbegin
- unordered_set/std::unordered_set::cend
- unordered_set/std::unordered_set::clear
- unordered_set/std::unordered_set::count
- unordered_set/std::unordered_set::contains
- unordered_set/std::unordered_set::emplace
- unordered_set/std::unordered_set::emplace_hint
- unordered_set/std::unordered_set::empty
- unordered_set/std::unordered_set::end
- unordered_set/std::unordered_set::equal_range
- unordered_set/std::unordered_set::erase
- unordered_set/std::unordered_set::find
- unordered_set/std::unordered_set::get_allocator
- unordered_set/std::unordered_set::hash
- unordered_set/std::unordered_set::insert
- unordered_set/std::unordered_set::key_eq
- unordered_set/std::unordered_set::load_factor
- unordered_set/std::unordered_set::max_bucket_count
- unordered_set/std::unordered_set::max_load_factor
- unordered_set/std::unordered_set::max_size
- unordered_set/std::unordered_set::rehash
- unordered_set/std::unordered_set::size
- unordered_set/std::unordered_set::swap
- unordered_set/std::unordered_set::unordered_set
- unordered_set/std::unordered_set::operator=
- unordered_set/std::unordered_set::hash_function
helpviewer_keywords:
- std::unordered_set
- std::unordered_set::allocator_type
- std::unordered_set::const_iterator
- std::unordered_set::const_local_iterator
- std::unordered_set::const_pointer
- std::unordered_set::const_reference
- std::unordered_set::difference_type
- std::unordered_set::hasher
- std::unordered_set::iterator
- std::unordered_set::key_equal
- std::unordered_set::key_type
- std::unordered_set::local_iterator
- std::unordered_set::pointer
- std::unordered_set::reference
- std::unordered_set::size_type
- std::unordered_set::value_type
- std::unordered_set::begin
- std::unordered_set::bucket
- std::unordered_set::bucket_count
- std::unordered_set::bucket_size
- std::unordered_set::cbegin
- std::unordered_set::cend
- std::unordered_set::clear
- std::unordered_set::contains
- std::unordered_set::count
- std::unordered_set::emplace
- std::unordered_set::emplace_hint
- std::unordered_set::empty
- std::unordered_set::end
- std::unordered_set::equal_range
- std::unordered_set::erase
- std::unordered_set::find
- std::unordered_set::get_allocator
- std::unordered_set::hash
- std::unordered_set::insert
- std::unordered_set::key_eq
- std::unordered_set::load_factor
- std::unordered_set::max_bucket_count
- std::unordered_set::max_load_factor
- std::unordered_set::max_size
- std::unordered_set::rehash
- std::unordered_set::size
- std::unordered_set::swap
- std::unordered_set::unordered_set
- std::unordered_set::operator=
- std::unordered_set::allocator_type
- std::unordered_set::const_iterator
- std::unordered_set::const_local_iterator
- std::unordered_set::const_pointer
- std::unordered_set::const_reference
- std::unordered_set::difference_type
- std::unordered_set::hasher
- std::unordered_set::iterator
- std::unordered_set::key_equal
- std::unordered_set::key_type
- std::unordered_set::local_iterator
- std::unordered_set::pointer
- std::unordered_set::reference
- std::unordered_set::size_type
- std::unordered_set::value_type
- std::unordered_set::begin
- std::unordered_set::bucket
- std::unordered_set::bucket_count
- std::unordered_set::bucket_size
- std::unordered_set::cbegin
- std::unordered_set::cend
- std::unordered_set::clear
- std::unordered_set::count
- std::unordered_set::emplace
- std::unordered_set::emplace_hint
- std::unordered_set::empty
- std::unordered_set::end
- std::unordered_set::equal_range
- std::unordered_set::erase
- std::unordered_set::find
- std::unordered_set::get_allocator
- std::unordered_set::hash_function
- std::unordered_set::insert
- std::unordered_set::key_eq
- std::unordered_set::load_factor
- std::unordered_set::max_bucket_count
- std::unordered_set::max_load_factor
- std::unordered_set::max_size
- std::unordered_set::rehash
- std::unordered_set::size
- std::unordered_set::swap
ms.assetid: ac08084e-05a7-48c0-9ae4-d40c529922dd
ms.openlocfilehash: 396465b24e9d7cf0facbe324c7b01479fe8e9b6b
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040045"
---
# <a name="unordered_set-class"></a>Класс unordered_set

Шаблон класса описывает объект, управляющий последовательностью элементов типа с различной длиной `const Key` . Последовательность слабо упорядочена хэш-функцией, которая разделяет последовательность в упорядоченный набор подпоследовательностей, называемых блоками. В каждом контейнере функция сравнения определяет, имеет ли любая пара элементов эквивалентное упорядочение. Каждый элемент используется в качестве ключа сортировки и в качестве значения. Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента несколькими операциями, которые могут не зависеть от числа элементов в последовательности (постоянное время), по крайней мере, когда все блоки имеют примерно одинаковую длину. В худшем случае, когда все элементы находятся в одном блоке, количество операций пропорционально количеству элементов в последовательности (линейное время). При вставке элемента недействительны итераторы, а удаление элемента сделает недействительными только те итераторы, которые указывают на удаленный элемент.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   class Key,
   class Hash = std::hash<Key>,
   class Pred = std::equal_to<Key>,
   class Alloc = std::allocator<Key>>
class unordered_set;
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

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
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

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[begin](#begin)|Задает начало управляемой последовательности.|
|[период](#bucket)|Получает номер блока для значения ключа.|
|[bucket_count](#bucket_count)|Получает количество блоков.|
|[bucket_size](#bucket_size)|Получает размер блока.|
|[cbegin](#cbegin)|Задает начало управляемой последовательности.|
|[cend](#cend)|Задает конец управляемой последовательности.|
|[clear](#clear)|Удаляет все элементы.|
|[содержит](#contains)<sup>c++ 20</sup>|Проверьте, существует ли элемент с указанным ключом в `unordered_set` .|
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
|[unordered_set](#unordered_set)|Создает объект контейнера.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[unordered_set::operator=](#op_eq)|Копирует хэш-таблицу.|

## <a name="remarks"></a>Комментарии

Объект упорядочивает последовательность, которую он управляет, вызывая два сохраненных объекта — объект функции сравнения типа [unordered_set:: key_equal](#key_equal) и объект хэш-функции типа [unordered_set:: hash](#hasher). Доступ к первому сохраненному объекту осуществляется путем вызова функции члена [unordered_set:: key_eq](#key_eq) `()` ; доступ к второму сохраненному объекту осуществляется путем вызова функции члена [unordered_set:: hash_function](#hash) `()` . В частности, для всех значений `X` и `Y` типа `Key` вызов `key_eq()(X, Y)` возвращает значение true, только если два значения аргументов имеют соответствующий порядок; вызов `hash_function()(keyval)` создает распределение значений типа `size_t`. В отличие от [класса Unordered_multiset Class](../standard-library/unordered-multiset-class.md), объект типа `unordered_set` гарантирует, что `key_eq()(X, Y)` всегда имеет значение false для любого из двух элементов управляемой последовательности. (Ключи уникальны).

Объект также хранит максимальный коэффициент нагрузки, который определяет максимальное желаемое среднее количество элементов в блоке. Если вставка элемента приводит к превышению максимального коэффициента загрузки [unordered_set:: load_factor](#load_factor) `()` , контейнер увеличивает количество сегментов и перестраивает хэш-таблицу по мере необходимости.

Фактический порядок элементов в управляемой последовательности зависит от хэш-функции, функции сравнения, порядка вставки, максимального коэффициента нагрузки и текущего числа блоков. В общем случае нельзя прогнозировать порядок элементов в управляемой последовательности. Однако всегда можно сохранять уверенность, что любое подмножество элементов, имеющих соответствующий порядок, будет расположено по соседству в управляемой последовательности.

Объект выделяет и освобождает хранилище для последовательности, управление которой осуществляется с помощью сохраненного объекта распределителя типа [unordered_set:: allocator_type](#allocator_type). Такой объект распределителя должен иметь тот же внешний интерфейс, что и объект типа `allocator` . Сохраненный объект распределителя не копируется при назначении объекта контейнера.

## <a name="unordered_setallocator_type"></a><a name="allocator_type"></a> unordered_set:: allocator_type

Тип распределителя для управления хранилищем.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Комментарии

Этот тип является синонимом для параметра шаблона `Alloc`.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_allocator_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="begin"></a><a name="begin"></a> begin

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
// unordered_set_begin.cpp
// compile using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>

using namespace std;

typedef unordered_set<char> MySet;

int main()
{
    MySet c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents using range-based for
    for (auto it : c1) {
    cout << "[" << it << "] ";
    }

    cout << endl;

    // display contents using explicit for
    for (MySet::const_iterator it = c1.begin(); it != c1.end(); ++it) {
        cout << "[" << *it << "] ";
    }

    cout << std::endl;

    // display first two items
    MySet::iterator it2 = c1.begin();
    cout << "[" << *it2 << "] ";
    ++it2;
    cout << "[" << *it2 << "] ";
    cout << endl;

    // display bucket containing 'a'
    MySet::const_local_iterator lit = c1.begin(c1.bucket('a'));
    cout << "[" << *lit << "] ";

    return (0);
}
```

```Output
[a] [b] [c]
[a] [b] [c]
[a] [b]
[a]
```

## <a name="bucket"></a><a name="bucket"></a> период

Получает номер блока для значения ключа.

```cpp
size_type bucket(const Key& keyval) const;
```

### <a name="parameters"></a>Параметры

*кэйвал*\
Значение ключа для сопоставления.

### <a name="remarks"></a>Комментарии

Функция – член возвращает номер контейнера, который в настоящее время соответствует значению ключа *кэйвал*.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_bucket.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="bucket_count"></a><a name="bucket_count"></a> bucket_count

Получает количество блоков.

```cpp
size_type bucket_count() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает текущее число блоков.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_bucket_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="bucket_size"></a><a name="bucket_size"></a> bucket_size

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
// std__unordered_set__unordered_set_bucket_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="cbegin"></a><a name="cbegin"></a> cbegin

Возвращает **`const`** итератор, который обращается к первому элементу в диапазоне.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`const`** Итератор прямого доступа, указывающий на первый элемент диапазона, или расположение непосредственно за концом пустого диапазона (для пустого диапазона `cbegin() == cend()` ).

### <a name="remarks"></a>Комментарии

С возвращаемым значением `cbegin` элементы в диапазоне нельзя изменять.

Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Обычно используется вместе с ключевым словом вывода типа [auto](../cpp/auto-cpp.md), как показано в следующем примере. В этом примере рекомендуется использовать `Container` изменяемый (не- **`const`** ) контейнер любого типа, который поддерживает `begin()` и `cbegin()` .

```cpp
auto i1 = Container.begin();
// i1 isContainer<T>::iterator
auto i2 = Container.cbegin();

// i2 isContainer<T>::const_iterator
```

## <a name="cend"></a><a name="cend"></a> cend

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
// i1 isContainer<T>::iterator
auto i2 = Container.cend();

// i2 isContainer<T>::const_iterator
```

Значение, возвращаемое, `cend` не должно быть разыменовано.

## <a name="clear"></a><a name="clear"></a> clear

Удаляет все элементы.

```cpp
void clear();
```

### <a name="remarks"></a>Комментарии

Функция члена вызывает [unordered_set:: Erase](#erase) `(` [unordered_set:: Begin](#begin) `(),` [unordered_set:: end](#end) `())` .

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_clear.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="const_iterator"></a><a name="const_iterator"></a> const_iterator

Тип постоянного итератора для управляемой последовательности.

```cpp
typedef T1 const_iterator;
```

### <a name="remarks"></a>Комментарии

Тип описывает объект, который можно использовать в качестве постоянного прямого итератора для управляемой последовательности. Он описан здесь как синоним для типа, определяемого реализацией `T1` .

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_const_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
    std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
```

## <a name="const_local_iterator"></a><a name="const_local_iterator"></a> const_local_iterator

Тип постоянного итератора блока для управляемой последовательности.

```cpp
typedef T5 const_local_iterator;
```

### <a name="remarks"></a>Комментарии

Этот тип описывает объект, который можно использовать в качестве постоянного прямого итератора для блока. Он описан здесь как синоним для типа, определяемого реализацией `T5` .

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_const_local_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="const_pointer"></a><a name="const_pointer"></a> const_pointer

Тип постоянного указателя на элемент.

```cpp
typedef Alloc::const_pointer const_pointer;
```

### <a name="remarks"></a>Комментарии

Этот тип описывает объект, который можно использовать в качестве постоянного указателя на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_const_pointer.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="const_reference"></a><a name="const_reference"></a> const_reference

Тип постоянной ссылки на элемент.

```cpp
typedef Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Комментарии

Тип описывает объект, который можно использовать в качестве постоянной ссылки на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_const_reference.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="contains"></a><a name="contains"></a> содержащих

Проверяет, существует ли элемент с указанным ключом в `unordered_set` .

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
    std::unordered_set<int> theUnorderedSet = { 1, 2 };

    std::cout << std::boolalpha; // so booleans show as 'true' or 'false'
    std::cout << theUnorderedSet.contains(2) << '\n';
    std::cout << theUnorderedSet.contains(3) << '\n';
    
    return 0;
}
```

```Output
true
false
```

## <a name="count"></a><a name="count"></a> расчета

Определяет количество элементов, соответствующих заданному ключу.

```cpp
size_type count(const Key& keyval) const;
```

### <a name="parameters"></a>Параметры

*кэйвал*\
Искомое значение ключа.

### <a name="remarks"></a>Комментарии

Функция – член возвращает количество элементов в диапазоне, ограниченном [unordered_set:: equal_range](#equal_range) `(keyval)` .

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="difference_type"></a><a name="difference_type"></a> difference_type

Тип расстояния со знаком между двумя элементами.

```cpp
typedef T3 difference_type;
```

### <a name="remarks"></a>Комментарии

Тип целого числа со знаком описывает объект, который может представлять разницу между адресами любых двух элементов в управляемой последовательности. Он описан здесь как синоним для типа, определяемого реализацией `T3` .

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_difference_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // compute positive difference
    Myset::difference_type diff = 0;
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    std::cout << "end()-begin() == " << diff << std::endl;

    // compute negative difference
    diff = 0;
    for (Myset::const_iterator it = c1.end(); it != c1.begin(); --it)
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

## <a name="emplace"></a><a name="emplace"></a> emplace

Вставляет элемент, созданный на месте (операции копирования или перемещения не выполняются).

```cpp
template <class... Args>
pair<iterator, bool>
emplace(
Args&&... args);
```

### <a name="parameters"></a>Параметры

*args*\
Аргументы, которые передаются для создания элемента, который будет вставлен в объект unordered_set, если этот объект еще не содержит элемент, ключ которого упорядочен аналогичным образом.

### <a name="return-value"></a>Возвращаемое значение

Объект `pair` , **`bool`** компонент которого возвращает значение true, если была произведена вставка, и значение false, если `unordered_set` уже содержал элемент, ключ которого имеет эквивалентное значение в упорядочении, а компонент итератора возвращает адрес, куда был вставлен новый элемент, или место, где элемент уже был найден.

Для доступа к компоненту итератора пары `pr`, возвращенной этой функцией-членом, используйте `pr.first` и разыменуйте ее с помощью `*(pr.first)`. Для доступа к **`bool`** компоненту пары `pr` , возвращаемой этой функцией-членом, используйте `pr.second` .

### <a name="remarks"></a>Комментарии

Эта функция не делает недействительными никакие итераторы или ссылки.

При вставке, если исключение возникает, но не возникает в хэш-функции контейнера, контейнер не изменяется. Если исключение вызывается в хэш-функции, результат не определен.

Пример кода см. в разделе [Set:: emplace](../standard-library/set-class.md#emplace).

## <a name="emplace_hint"></a><a name="emplace_hint"></a> emplace_hint

Вставляет созданный элемент на место (операции копирования или перемещения не выполняются) с указанием о размещении.

```cpp
template <class... Args>
iterator emplace_hint(
const_iteratorwhere,
Args&&... args);
```

### <a name="parameters"></a>Параметры

*args*\
Аргументы, которые передаются для создания элемента, который будет вставлен в объект unordered_set, если объект unordered_set не содержит этого элемента или, в более общем случае, если этот объект еще не содержит элемента, ключ которого упорядочен аналогичным образом.

*которому*\
Подсказка о месте, с которой начинается поиск нужной точки вставки.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на вновь вставленный элемент.

Если не удалось вставить элемент, так как он уже существует, возвращается итератор на существующий элемент.

### <a name="remarks"></a>Комментарии

Эта функция не делает недействительными никакие итераторы или ссылки.

При вставке, если исключение возникает, но не возникает в хэш-функции контейнера, контейнер не изменяется. Если исключение вызывается в хэш-функции, результат не определен.

Пример кода см. в разделе [set::emplace_hint](../standard-library/set-class.md#emplace_hint).

## <a name="empty"></a><a name="empty"></a> empty

Проверяет отсутствие элементов.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Комментарии

Эта функция-член возвращает значение true для пустой управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_empty.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="end"></a><a name="end"></a> end

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
// std__unordered_set__unordered_set_end.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // inspect last two items "[a] [b] "
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

## <a name="equal_range"></a><a name="equal_range"></a> equal_range

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
// std__unordered_set__unordered_set_equal_range.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="erase"></a><a name="erase"></a> erase

Удаляет элемент или диапазон элементов в объекте unordered_set с заданных позиций или удаляет элементы, соответствующие заданному ключу.

```cpp
iterator erase(const_iterator Where);

iterator erase(const_iterator First, const_iterator Last);

size_type erase(const key_type& Key);
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

Для первых двух функций-членов двунаправленный итератор, указывающий на первый элемент, оставшийся после удаления элементов, или на последний элемент объекта unordered_set, если такого элемента не существует.

Для третьей функции-члена возвращает число элементов, которые были удалены из объекта unordered_set.

### <a name="remarks"></a>Комментарии

Пример кода см. в разделе [set::erase](../standard-library/set-class.md#erase).

## <a name="find"></a><a name="find"></a> Найдено

Определяет элемент, соответствующий указанному ключу.

```cpp
const_iterator find(const Key& keyval) const;
```

### <a name="parameters"></a>Параметры

*кэйвал*\
Искомое значение ключа.

### <a name="remarks"></a>Комментарии

Функция – член возвращает [unordered_set:: equal_range](#equal_range) `(keyval).first` .

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_find.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="get_allocator"></a><a name="get_allocator"></a> get_allocator

Возвращает сохраненный объект распределителя.

```cpp
Alloc get_allocator() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает сохраненный объект распределителя.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_get_allocator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="hash_function"></a><a name="hash"></a> hash_function

Получает сохраненный объект хэш-функции.

```cpp
Hash hash_function() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает сохраненный объект хэш-функции.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_hash_function.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="hasher"></a><a name="hasher"></a> Hasher

Тип хэш-функции.

```cpp
typedef Hash hasher;
```

### <a name="remarks"></a>Комментарии

Этот тип является синонимом для параметра шаблона `Hash`.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_hasher.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="insert"></a><a name="insert"></a> insert

Вставляет элемент или диапазон элементов в unordered_set.

```cpp
// (1) single element
pair<iterator, bool> insert(const value_type& Val);

// (2) single element, perfect forwarded
template <class ValTy>
pair<iterator, bool> insert(ValTy&& Val);

// (3) single element with hint
iterator insert(const_iterator Where, const value_type& Val);

// (4) single element, perfect forwarded, with hint
template <class ValTy>
iterator insert(const_iterator Where, ValTy&& Val);

// (5) range
template <class InputIterator>
void insert(InputIterator First, InputIterator Last);

// (6) initializer list
void insert(initializer_list<value_type> IList);
```

### <a name="parameters"></a>Параметры

*val*\
Значение элемента, вставляемого в unordered_set, если оно уже не содержит элемент, ключ которого эквивалентно упорядочен.

*Where*\
Место начала поиска правильной точки вставки.

*валти*\
Параметр шаблона, указывающий тип аргумента, который unordered_set может использовать для создания элемента [value_type](../standard-library/map-class.md#value_type), и идеальное перенаправление *Val* в качестве аргумента.

*First*\
Позиция первого элемента, который следует скопировать.

*last*\
Позиция непосредственно перед последним элементом, который следует скопировать.

*InputIterator*\
Аргумент функции-шаблона, который соответствует требованиям [итератора ввода](../standard-library/input-iterator-tag-struct.md), указывающего на элементы типа, которые можно использовать для создания объектов [value_type](../standard-library/map-class.md#value_type).

*Интерфейс*\
[Initializer_list](../standard-library/initializer-list.md) , из которого копируются элементы.

### <a name="return-value"></a>Возвращаемое значение

Одноэлементные функции-члены (1) и (2) возвращают [пару](../standard-library/pair-structure.md) , компонент которой **`bool`** имеет значение true, если была произведена вставка, и значение false, если unordered_set уже содержала элемент, ключ которого имел эквивалентное значение в упорядочении. Компонент итератора пары "возвращаемое значение" указывает на вновь вставленный элемент, если **`bool`** компонент имеет значение true, или на существующий элемент, если **`bool`** компонент имеет значение false.

Одноэлементные функции-члены с подсказкой (3) и (4) возвращают итератор, который указывает на позицию, где новый элемент был вставлен, или, если элемент с эквивалентным ключом уже существует, указывает на существующий элемент.

### <a name="remarks"></a>Комментарии

Эта функция не делает никакие итераторы, указатели или ссылки недействительными.

При вставке всего одного элемента, если исключение возникает, но не возникает в хэш-функции контейнера, состояние контейнера не изменяется. Если исключение вызывается в хэш-функции, результат не определен. Если во время вставки нескольких элементов вызывается исключение, контейнер остается в неопределенном, но допустимом состоянии.

Чтобы получить доступ к компоненту итератора `pair` `pr` , возвращаемому функциями-членами с одним элементом, используйте оператор `pr.first` ; для разыменования итератора в возвращенной паре используйте `*pr.first` , предоставив элемент. Чтобы получить доступ к **`bool`** компоненту, используйте `pr.second` . См. пример кода далее в этой статье.

[value_type](../standard-library/map-class.md#value_type) контейнера — это определение типа, принадлежащее контейнеру и, для набора, `unordered_set<V>::value_type` имеет тип `const V`.

Функция-член Range (5) вставляет последовательность значений элементов в unordered_set, соответствующую каждому элементу, адресованному итератором в диапазоне `[First, Last)` , поэтому *последний* не вставляется. Контейнер функции-члена `end()` ссылается на позицию сразу после последнего элемента в контейнере. Например, оператор `s.insert(v.begin(), v.end());` пытается вставить все элементы `v` в `s`. Вставляются только элементы с уникальными значениями в диапазоне. Повторяющиеся значения игнорируются. Чтобы увидеть, какие элементы отклонены, используйте одноэлементные версии `insert`.

Функция-член списка инициализаторов (6) использует [initializer_list](../standard-library/initializer-list.md) для копирования элементов в unordered_set.

Для вставки элемента, созданного на месте (то есть без операций копирования или перемещения) см. разделы [set::emplace](../standard-library/set-class.md#emplace) и [set::emplace_hint](../standard-library/set-class.md#emplace_hint).

Пример кода см. в разделе [Set:: INSERT](../standard-library/set-class.md#insert).

## <a name="iterator"></a><a name="iterator"></a> iterator

Тип, предоставляющий постоянный [прямой итератор](../standard-library/forward-iterator-tag-struct.md) , который может считывать элементы в unordered_set.

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>Пример

См. пример для [Begin](../standard-library/set-class.md#begin) в качестве примера объявления и использования**итератора**.

## <a name="key_eq"></a><a name="key_eq"></a> key_eq

Получает сохраненный объект функции сравнения.

```cpp
Pred key_eq() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает сохраненный объект функции сравнения.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_key_eq.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="key_equal"></a><a name="key_equal"></a> key_equal

Тип функции сравнения.

```cpp
typedef Pred key_equal;
```

### <a name="remarks"></a>Комментарии

Этот тип является синонимом для параметра шаблона `Pred`.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_key_equal.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="key_type"></a><a name="key_type"></a> key_type

Тип ключа упорядочения.

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Комментарии

Этот тип является синонимом для параметра шаблона `Key`.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_key_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // add a value and reinspect
    Myset::key_type key = 'd';
    Myset::value_type val = key;
    c1.insert(val);

    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
[d] [c] [b] [a]
```

## <a name="load_factor"></a><a name="load_factor"></a> load_factor

Подсчитывает среднее число элементов в блоке.

```cpp
float load_factor() const;
```

### <a name="remarks"></a>Комментарии

Функция – член возвращает `(float)` [unordered_set:: size](#size) `() / (float)` [unordered_set:: bucket_count](#bucket_count) `()` , среднее число элементов на сегмент.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_load_factor.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="local_iterator"></a><a name="local_iterator"></a> local_iterator

Тип итератора контейнера.

```cpp
typedef T4 local_iterator;
```

### <a name="remarks"></a>Комментарии

Этот тип описывает объект, который можно использовать в качестве прямого итератора для контейнера. Он описан здесь как синоним для типа, определяемого реализацией `T4` .

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_local_iterator.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="max_bucket_count"></a><a name="max_bucket_count"></a> max_bucket_count

Получает максимальное количество блоков.

```cpp
size_type max_bucket_count() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает максимальное количество блоков, которое разрешено в настоящее время.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_max_bucket_count.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="max_load_factor"></a><a name="max_load_factor"></a> max_load_factor

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
// std__unordered_set__unordered_set_max_load_factor.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="max_size"></a><a name="max_size"></a> max_size

Возвращает максимальный размер управляемой последовательности.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает длину самой длинной последовательности, которой объект может управлять.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_max_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="operator"></a><a name="op_eq"></a> operator=

Копирует хэш-таблицу.

```cpp
unordered_set& operator=(const unordered_set& right);

unordered_set& operator=(unordered_set&& right);
```

### <a name="parameters"></a>Параметры

*right*\
[Unordered_set](../standard-library/unordered-set-class.md) , копируемый в `unordered_set` .

### <a name="remarks"></a>Комментарии

После стирания любых существующих элементов в `unordered_set` `operator=` копирует или перемещает содержимое *непосредственно* в `unordered_set` .

### <a name="example"></a>Пример

```cpp
// unordered_set_operator_as.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

int main( )
{
    using namespace std;
    unordered_set<int> v1, v2, v3;
    unordered_set<int>::iterator iter;

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

## <a name="pointer"></a><a name="pointer"></a> pointer

Тип указателя на элемент.

```cpp
typedef Alloc::pointer pointer;
```

### <a name="remarks"></a>Комментарии

Этот тип описывает объект, который можно использовать в качестве указателя на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_pointer.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="reference"></a><a name="reference"></a> IsReference

Тип ссылки на элемент.

```cpp
typedef Alloc::reference reference;
```

### <a name="remarks"></a>Комментарии

Тип описывает объект, который можно использовать в качестве ссылки на элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_reference.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="rehash"></a><a name="rehash"></a> rehash

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
// std__unordered_set__unordered_set_rehash.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="size"></a><a name="size"></a> size

Подсчитывает количество элементов.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Комментарии

Функция-член возвращает длину управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_size.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="size_type"></a><a name="size_type"></a> size_type

Тип беззнакового расстояния между двумя элементами.

```cpp
typedef T2 size_type;
```

### <a name="remarks"></a>Комментарии

Целочисленный тип без знака описывает объект, который может представлять длину любой управляемой последовательности. Он описан здесь как синоним для типа, определяемого реализацией `T2` .

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_size_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
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

## <a name="swap"></a><a name="swap"></a> swap

Меняет местами содержимое двух контейнеров.

```cpp
void swap(unordered_set& right);
```

### <a name="parameters"></a>Параметры

*right*\
Контейнер для замены.

### <a name="remarks"></a>Комментарии

Функция – член меняет местами управляемые последовательности между **`*this`** и *вправо*. Если [unordered_set:: get_allocator](#get_allocator) `() == right.get_allocator()` , он делает это в константном времени, он создает исключение только в результате копирования сохраненного объекта признаков типа `Tr` и не делает недействительными ссылки, указатели или итераторы, обозначающие элементы в двух управляемых последовательностях. В противном случае она выполняет ряд назначений элементов и вызовов конструктора, пропорционально количеству элементов в двух управляемых последовательностях.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_swap.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    Myset c2;

    c2.insert('d');
    c2.insert('e');
    c2.insert('f');

    c1.swap(c2);

    // display contents "[f] [e] [d] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    swap(c1, c2);

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
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

## <a name="unordered_set"></a><a name="unordered_set"></a> unordered_set

Создает объект контейнера.

```cpp
unordered_set(const unordered_set& Right);

explicit unordered_set(
    size_typebucket_count = N0,
    const Hash& Hash = Hash(),
    const Comp& Comp = Comp(),
    const Allocator& Al = Alloc());

unordered_set(unordered_set&& Right);

unordered_set(initializer_list<Type> IList);

unordered_set(initializer_list<Type> IList, size_typebucket_count);

unordered_set(
    initializer_list<Type> IList,
    size_typebucket_count,
    const Hash& Hash);

unordered_set(
    initializer_list<Type> IList,
    size_typebucket_count,
    const Hash& Hash,
    const Comp& Comp);

unordered_set(
    initializer_list<Type> IList,
    size_typebucket_count,
    const Hash& Hash,
    const Comp& Comp,
    const Allocator& Al);

template <class InputIterator>
unordered_set(
    InputIteratorfirst,
    InputIteratorlast,
    size_typebucket_count = N0,
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

*bucket_count*\
Минимальное количество блоков.

*right*\
Контейнер для копирования.

*Интерфейс*\
Объект initializer_list, содержащий копируемые элементы.

### <a name="remarks"></a>Комментарии

Первый конструктор задает копию последовательности, управляемой по *правому краю*. Второй конструктор определяет управляемую пустую последовательность. Третий конструктор указывает копию последовательности, перемещая *правый* четвертый через восьмые конструкторы. Используйте initializer_list, чтобы указать копируемые элементы. Девятый конструктор добавляет последовательность значений элементов `[first, last)`.

Все конструкторы также инициализируют ряд сохраненных значений. Для конструктора копии значения получаются *справа*. В противном случае:

Минимальное число контейнеров — аргумент, *bucket_count*, если он есть; в противном случае это значение по умолчанию, описываемое здесь как значение, определяемое реализацией `N0` .

Объект хэш-функции — это *хэш*аргумента, если он есть; в противном случае это `Hash()` .

Объект функции сравнения — это аргумент *comp*, если он есть; в противном случае это `Comp()` .

Объект распределителя — это аргумент *Al*, если он есть; в противном случае это `Alloc()` .

## <a name="value_type"></a><a name="value_type"></a> value_type

Тип элемента.

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Комментарии

Тип описывает элемент управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// std__unordered_set__unordered_set_value_type.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents "[c] [b] [a] "
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    // add a value and reinspect
    Myset::key_type key = 'd';
    Myset::value_type val = key;
    c1.insert(val);

    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)
        std::cout << "[" << *it << "] ";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
[d] [c] [b] [a]
```
