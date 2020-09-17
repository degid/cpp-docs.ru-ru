---
title: hash_multimap (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::hash_multimap
- cliext::hash_multimap::begin
- cliext::hash_multimap::bucket_count
- cliext::hash_multimap::clear
- cliext::hash_multimap::const_iterator
- cliext::hash_multimap::const_reference
- cliext::hash_multimap::const_reverse_iterator
- cliext::hash_multimap::count
- cliext::hash_multimap::difference_type
- cliext::hash_multimap::empty
- cliext::hash_multimap::end
- cliext::hash_multimap::equal_range
- cliext::hash_multimap::erase
- cliext::hash_multimap::find
- cliext::hash_multimap::generic_container
- cliext::hash_multimap::generic_iterator
- cliext::hash_multimap::generic_reverse_iterator
- cliext::hash_multimap::generic_value
- cliext::hash_multimap::hash_delegate
- cliext::hash_multimap::hash_multimap
- cliext::hash_multimap::hasher
- cliext::hash_multimap::insert
- cliext::hash_multimap::iterator
- cliext::hash_multimap::key_comp
- cliext::hash_multimap::key_compare
- cliext::hash_multimap::key_type
- cliext::hash_multimap::load_factor
- cliext::hash_multimap::lower_bound
- cliext::hash_multimap::make_value
- cliext::hash_multimap::mapped_type
- cliext::hash_multimap::max_load_factor
- cliext::hash_multimap::operator=
- cliext::hash_multimap::rbegin
- cliext::hash_multimap::reference
- cliext::hash_multimap::rehash
- cliext::hash_multimap::rend
- cliext::hash_multimap::reverse_iterator
- cliext::hash_multimap::size
- cliext::hash_multimap::size_type
- cliext::hash_multimap::swap
- cliext::hash_multimap::to_array
- cliext::hash_multimap::upper_bound
- cliext::hash_multimap::value_comp
- cliext::hash_multimap::value_compare
- cliext::hash_multimap::value_type
helpviewer_keywords:
- hash_multimap class [STL/CLR]
- <cliext/hash_map> header [STL/CLR]
- <hash_map> header [STL/CLR]
- begin member [STL/CLR]
- begin member [STL/CLR]
- bucket_count member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- count member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- equal_range member [STL/CLR]
- erase member [STL/CLR]
- find member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- hash_delegate member [STL/CLR]
- hash_multimap member [STL/CLR]
- hasher member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- load_factor member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- mapped_type member [STL/CLR]
- max_load_factor member [STL/CLR]
- operator= member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rehash member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: cd78687b-8a05-48e0-9d22-8b8194ae3b0b
ms.openlocfilehash: 7faba79dfcd585e9f397c6ecd0bf594a5fb6c501
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221410"
---
# <a name="hash_multimap-stlclr"></a>hash_multimap (STL/CLR)

Класс шаблона описывает объект, управляющий последовательностью элементов различной длины с двунаправленным доступом. Контейнер используется `hash_multimap` для управления последовательностью элементов в виде хэш-таблицы, каждой записи таблицы, в которой хранится двунаправленный связанный список узлов, и каждого узла, в котором хранится один элемент. Элемент состоит из ключа, для упорядочивания последовательности и сопоставленного значения, которое передается вместе с.

В описании ниже `GValue` используется то же самое:

`Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`

где:

`GKey`совпадает с *ключом* , если только второй не является ссылочным типом, в этом случае`Key^`

`GMapped`совпадает с *сопоставлением* , если только второй не является ссылочным типом, в этом случае`Mapped^`

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Key,
    typename Mapped>
    ref class hash_multimap
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>Параметры

*Key*<br/>
Тип ключа для элемента в управляемой последовательности.

*Mapped*<br/>
Тип дополнительного компонента элемента в управляемой последовательности.

## <a name="requirements"></a>Требования

**Заголовок:**\<cliext/hash_map>

**Пространство имен:** cliext

## <a name="declarations"></a>Объявления

|Определение типа|Описание|
|---------------------|-----------------|
|[hash_multimap::const_iterator (STL/CLR)](#const_iterator)|Тип постоянного итератора для управляемой последовательности.|
|[hash_multimap::const_reference (STL/CLR)](#const_reference)|Тип постоянной ссылки на элемент.|
|[hash_multimap::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Тип постоянного обратного итератора для управляемой последовательности.|
|[hash_multimap::difference_type (STL/CLR)](#difference_type)|Тип (возможно, со знаком) расстояния между двумя элементами.|
|[hash_multimap::generic_container (STL/CLR)](#generic_container)|Тип универсального интерфейса для контейнера.|
|[hash_multimap::generic_iterator (STL/CLR)](#generic_iterator)|Тип итератора для универсального интерфейса для контейнера.|
|[hash_multimap::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Тип реверсивного итератора для универсального интерфейса контейнера.|
|[hash_multimap::generic_value (STL/CLR)](#generic_value)|Тип элемента для универсального интерфейса контейнера.|
|[hash_multimap::hasher (STL/CLR)](#hasher)|Делегат хеширования для ключа.|
|[hash_multimap::iterator (STL/CLR)](#iterator)|Тип итератора для управляемой последовательности.|
|[hash_multimap::key_compare (STL/CLR)](#key_compare)|Делегат упорядочения для двух ключей.|
|[hash_multimap::key_type (STL/CLR)](#key_type)|Тип ключа упорядочения.|
|[hash_multimap::mapped_type (STL/CLR)](#mapped_type)|Тип сопоставленного значения, связанного с каждым ключом.|
|[hash_multimap::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|
|[hash_multimap::reverse_iterator (STL/CLR)](#reverse_iterator)|Тип обратного итератора для управляемой последовательности.|
|[hash_multimap::size_type (STL/CLR)](#size_type)|Тип (неотрицательного) расстояния между двумя элементами.|
|[hash_multimap::value_compare (STL/CLR)](#value_compare)|Делегат упорядочивания для двух значений элементов.|
|[hash_multimap::value_type (STL/CLR)](#value_type)|Тип элемента.|

|Функция-член|Описание|
|---------------------|-----------------|
|[hash_multimap::begin (STL/CLR)](#begin)|Задает начало управляемой последовательности.|
|[hash_multimap::bucket_count (STL/CLR)](#bucket_count)|Подсчитывает количество сегментов.|
|[hash_multimap::clear (STL/CLR)](#clear)|Удаляет все элементы.|
|[hash_multimap::count (STL/CLR)](#count)|Подсчитывает число элементов, соответствующих указанному ключу.|
|[hash_multimap::empty (STL/CLR)](#empty)|Проверяет отсутствие элементов.|
|[hash_multimap::end (STL/CLR)](#end)|Задает конец управляемой последовательности.|
|[hash_multimap::equal_range (STL/CLR)](#equal_range)|Находит диапазон, соответствующий указанному ключу.|
|[hash_multimap::erase (STL/CLR)](#erase)|Удаляет элементы в указанных позициях.|
|[hash_multimap::find (STL/CLR)](#find)|Определяет элемент, соответствующий указанному ключу.|
|[hash_multimap::hash_delegate (STL/CLR)](#hash_delegate)|Копирует делегат хеширования для ключа.|
|[hash_multimap::hash_multimap (STL/CLR)](#hash_multimap)|Создает объект контейнера.|
|[hash_multimap::insert (STL/CLR)](#insert)|Добавляет элементы.|
|[hash_multimap::key_comp (STL/CLR)](#key_comp)|Копирует делегат упорядочения для двух ключей.|
|[hash_multimap::load_factor (STL/CLR)](#load_factor)|Подсчитывает среднее число элементов в блоке.|
|[hash_multimap::lower_bound (STL/CLR)](#lower_bound)|Находит начало диапазона, совпадающее с указанным ключом.|
|[hash_multimap::make_value (STL/CLR)](#make_value)|Конструирует объект значения.|
|[hash_multimap::max_load_factor (STL/CLR)](#max_load_factor)|Возвращает или задает максимальное количество элементов в блоке.|
|[hash_multimap::rbegin (STL/CLR)](#rbegin)|Задает начало обратной управляемой последовательности.|
|[hash_multimap::rehash (STL/CLR)](#rehash)|Повторно создает хэш-таблицу.|
|[hash_multimap::rend (STL/CLR)](#rend)|Задает конец обратной управляемой последовательности.|
|[hash_multimap::size (STL/CLR)](#size)|Подсчитывает количество элементов.|
|[hash_multimap::swap (STL/CLR)](#swap)|Меняет местами содержимое двух контейнеров.|
|[hash_multimap::to_array (STL/CLR)](#to_array)|Копирует управляемую последовательность в новый массив.|
|[hash_multimap::upper_bound (STL/CLR)](#upper_bound)|Находит конец диапазона, соответствующий указанному ключу.|
|[hash_multimap::value_comp (STL/CLR)](#value_comp)|Копирует делегат упорядочения для двух значений элементов.|

|Оператор|Описание|
|--------------|-----------------|
|[hash_multimap::operator= (STL/CLR)](#op)|Заменяет управляемую последовательность.|

## <a name="interfaces"></a>Интерфейсы

|Интерфейс|Описание|
|---------------|-----------------|
|<xref:System.ICloneable>|Дублировать объект.|
|<xref:System.Collections.IEnumerable>|Последовательное упорядочение элементов.|
|<xref:System.Collections.ICollection>|Поддержка группы элементов.|
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательность через типизированные элементы.|
|<xref:System.Collections.Generic.ICollection%601>|Поддержание группы типизированных элементов.|
|ихаш\<Key, Value>|Поддержание универсального контейнера.|

## <a name="remarks"></a>Примечания

Объект выделяет и освобождает хранилище для последовательности, которую он контролирует как отдельные узлы в двунаправленном связанном списке. Для ускорения доступа объект также поддерживает массив указателей различной длины в список (хэш-таблицу), эффективно управляя всем списком в виде последовательности подсписков или контейнеров. Он вставляет элементы в контейнер, который сохраняется в порядке, изменяя связи между узлами, не копируя содержимое одного узла в другой. Это означает, что можно свободно вставлять и удалять элементы без нарушения работы остальных элементов.

Объект упорядочивает каждый контейнер, управляющий, путем вызова сохраненного объекта делегата типа [hash_set:: key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md). При создании hash_set можно указать сохраненный объект делегата; Если объект делегата не указан, по умолчанию используется сравнение `operator<=(key_type, key_type)` .

Доступ к сохраненному объекту делегата осуществляется путем вызова функции-члена [hash_set:: key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md) `()` . Такой объект-делегат должен определять эквивалентное упорядочение между ключами типа [hash_set:: key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md). Это означает, что для любых двух ключей `X` и `Y` :

`key_comp()(X, Y)`Возвращает один и тот же логический результат при каждом вызове.

Если `key_comp()(X, Y) && key_comp()(Y, X)` имеет значение true, то `X` и `Y` говорят, что они имеют эквивалентное упорядочение.

Любое правило упорядочивания, которое ведет себя как `operator<=(key_type, key_type)` , `operator>=(key_type, key_type)` или `operator==(key_type, key_type)` определяет порядок екивалент.

Обратите внимание, что контейнер гарантирует, что все элементы, ключи которых имеют эквивалентное упорядочение (и какой хэш для одного и того же целого значения) являются смежными внутри контейнера. В отличие от класса шаблона [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md), объект класса шаблона не `hash_multimap` требует уникальности ключей для всех элементов. (Два или более ключа могут иметь эквивалентное упорядочение.)

Объект определяет, какой сегмент должен содержать заданный ключ упорядочения, вызывая хранимый объект делегата типа [hash_set:: hashing (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md). Доступ к этому сохраненному объекту осуществляется путем вызова функции [-члена hash_set:: hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` для получения целочисленного значения, которое зависит от значения ключа. При создании hash_set можно указать сохраненный объект делегата; Если объект делегата не указан, по умолчанию используется функция `System::Object::hash_value(key_type)` . Это означает, что для любых ключей `X` и `Y` :

`hash_delegate()(X)`Возвращает один и тот же целочисленный результат при каждом вызове.

Если `X` и `Y` имеют эквивалентное упорядочение, то `hash_delegate()(X)` должен возвращать тот же самый целочисленный результат, что и `hash_delegate()(Y)` .

Каждый элемент содержит отдельный ключ и сопоставленное значение. Последовательность представляется способом, который позволяет выполнять поиск, вставку и удаление произвольного элемента с несколькими операциями, не зависящими от числа элементов в последовательности (постоянное время) — по крайней мере, в лучших случаях. Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.

Однако, если Хэшированные значения не распределяются равномерно, хэш-таблица может быть десформирована. В экстремальной — для хэш-функции, которая всегда возвращает одно и то же значение--Уточняющий запрос, вставка и удаление пропорциональны количеству элементов в последовательности (линейное время). Контейнер пытается выбрать разумную хэш-функцию, среднее значение размера контейнера и размер таблицы хэша (общее количество контейнеров), но можно переопределить любой из этих вариантов или все эти варианты. См., например, функции [hash_set:: max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) и [hash_set:: rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md).

Hash_multimap поддерживает двунаправленные итераторы. Это означает, что можно пошагово перейти к смежным элементам с помощью итератора, который обозначает элемент в управляемой последовательности. Специальный головной узел соответствует итератору, возвращенному [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md) `()` . Можно уменьшить этот итератор, чтобы достичь последнего элемента в управляемой последовательности, если он есть. Вы можете увеличить hash_multimap итератора, чтобы достичь головного узла, а затем сравнить его со значением `end()` . Но нельзя разыменование итератора, возвращаемого методом `end()` .

Обратите внимание, что нельзя ссылаться на элемент hash_multimap напрямую, используя его числовое значение, для которого требуется итератор произвольного доступа.

Итератор hash_multimap сохраняет обработчик для связанного с ним узла hash_multimap, который, в свою очередь, хранит маркер связанного с ним контейнера. Итераторы можно использовать только со связанными объектами контейнера. Итератор hash_multimap остается действительным до тех пор, пока связанный с ним hash_multimap узел связан с некоторыми hash_multimap. Более того, допустимый итератор — дереференкабле — вы можете использовать его для доступа к значению элемента, которое он определяет, или изменять его значение, если оно не равно `end()` .

При стирании или удалении элемента вызывается деструктор для его сохраненного значения. При уничтожении контейнера удаляются все элементы. Таким образом, контейнер, тип элемента которого является ссылочным классом, гарантирует, что контейнер не будет находиться ни в одной из элементов. Однако обратите внимание, что контейнер дескрипторов не *уничтожает свои* элементы.

## <a name="members"></a>Элементы

## <a name="hash_multimapbegin-stlclr"></a><a name="begin"></a>hash_multimap:: Begin (STL/CLR)

Задает начало управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator begin();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает двунаправленный итератор, который обозначает первый элемент управляемой последовательности или сразу за концом пустой последовательности. Используется для получения итератора, который задает начало управляемой последовательности с параметром `current`, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_begin.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_multimap::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = [{0} {1}]",
        it->first, it->second);
    ++it;
    System::Console::WriteLine("*++begin() = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*begin() = [a 1]
*++begin() = [b 2]
```

## <a name="hash_multimapbucket_count-stlclr"></a><a name="bucket_count"></a>hash_multimap:: bucket_count (STL/CLR)

Подсчитывает количество сегментов.

### <a name="syntax"></a>Синтаксис

```cpp
int bucket_count();
```

### <a name="remarks"></a>Примечания

Функции элементов возвращают текущее количество контейнеров. Он используется для определения размера хэш-таблицы.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_bucket_count.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1 = gcnew Myhash_multimap;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_multimapclear-stlclr"></a><a name="clear"></a>hash_multimap:: Clear (STL/CLR)

Удаляет все элементы.

### <a name="syntax"></a>Синтаксис

```cpp
void clear();
```

### <a name="remarks"></a>Примечания

Функция-член фактически вызывает [hash_multimap:: Erase (STL/CLR)](../dotnet/hash-multimap-erase-stl-clr.md) `(` [hash_multimap:: Begin (STL/CLR)](../dotnet/hash-multimap-begin-stl-clr.md) `(),` [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md) `())` . Он используется, чтобы гарантировать, что управляемая последовательность пуста.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_clear.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));

    // display contents " [a 1] [b 2]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0
[a 1] [b 2]
size() = 0
```

## <a name="hash_multimapconst_iterator-stlclr"></a><a name="const_iterator"></a>hash_multimap:: const_iterator (STL/CLR)

Тип постоянного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает объект неопределенного типа `T2` , который может выступать в качестве постоянного двунаправленного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_const_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_multimap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("[{0} {1}] ", cit->first, cit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapconst_reference-stlclr"></a><a name="const_reference"></a>hash_multimap:: const_reference (STL/CLR)

Тип постоянной ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Примечания

Тип описывает константную ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_const_reference.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_multimap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myhash_multimap::const_reference cref = *cit;
        System::Console::Write("[{0} {1}] ", cref->first, cref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>hash_multimap:: const_reverse_iterator (STL/CLR)

Тип константного реверсивного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает объект неопределенного типа `T4` , который может служить в качестве постоянного реверсивного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Myhash_multimap::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("[{0} {1}] ", crit->first, crit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="hash_multimapcount-stlclr"></a><a name="count"></a>hash_multimap:: count (STL/CLR)

Определяет количество элементов, соответствующих заданному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Функция – член возвращает количество элементов в управляемой последовательности, имеющих эквивалентное упорядочение с *ключом*. Используется для определения количества элементов в управляемой последовательности, ключ которых в данный момент совпадает с заданным ключом.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_count.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="hash_multimapdifference_type-stlclr"></a><a name="difference_type"></a>hash_multimap::d ifference_type (STL/CLR)

Типы расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Примечания

Тип описывает возможное число отрицательных элементов.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_difference_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_multimap::difference_type diff = 0;
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Myhash_multimap::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
begin()-end() = -3
```

## <a name="hash_multimapempty-stlclr"></a><a name="empty"></a>hash_multimap:: Empty (STL/CLR)

Проверяет отсутствие элементов.

### <a name="syntax"></a>Синтаксис

```cpp
bool empty();
```

### <a name="remarks"></a>Примечания

Эта функция-член возвращает значение true для пустой управляемой последовательности. Он эквивалентен [hash_multimap:: size (STL/CLR)](../dotnet/hash-multimap-size-stl-clr.md) `() == 0` . Он используется для проверки того, является ли hash_multimap пустым.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_empty.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="hash_multimapend-stlclr"></a><a name="end"></a>hash_multimap:: end (STL/CLR)

Задает конец управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator end();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает двунаправленный итератор, указывающий сразу за концом управляемой последовательности. Он используется для получения итератора, который обозначает конец управляемой последовательности. его состояние не изменяется при изменении длины управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_end.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect last two items
    Myhash_multimap::iterator it = c1.end();
    --it;
    --it;
    System::Console::WriteLine("*-- --end() = [{0} {1}]",
        it->first, it->second);
    ++it;
    System::Console::WriteLine("*--end() = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*-- --end() = [b 2]
*--end() = [c 3]
```

## <a name="hash_multimapequal_range-stlclr"></a><a name="equal_range"></a>hash_multimap:: equal_range (STL/CLR)

Находит диапазон, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Функция-член возвращает пару итераторов `cliext::pair<iterator, iterator>(` [hash_multimap:: lower_bound (STL/CLR)](../dotnet/hash-multimap-lower-bound-stl-clr.md) `(key),` [hash_multimap:: upper_bound (STL/CLR)](../dotnet/hash-multimap-upper-bound-stl-clr.md) `(key))` . Он используется для определения диапазона элементов, находящихся в настоящий момент в управляемой последовательности, соответствующей указанному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_equal_range.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
typedef Myhash_multimap::pair_iter_iter Pairii;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

    // display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("[{0} {1}] ",
            pair1.first->first, pair1.first->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
equal_range(L'x') empty = True
[b 2]
```

## <a name="hash_multimaperase-stlclr"></a><a name="erase"></a>hash_multimap:: Erase (STL/CLR)

Удаляет элементы в указанных позициях.

### <a name="syntax"></a>Синтаксис

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
bool erase(key_type key)
```

#### <a name="parameters"></a>Параметры

*first*<br/>
Начало диапазона для стирания.

*key*<br/>
Значение ключа для стирания.

*last*<br/>
Конец диапазона для стирания.

*where*<br/>
Элемент для стирания.

### <a name="remarks"></a>Примечания

Первая функция-член удаляет элемент управляемой *последовательности, на который указывает, и*возвращает итератор, который обозначает первый элемент, оставшийся после удаления элемента, или [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md) , `()` Если такого элемента не существует. Он используется для удаления одного элемента.

Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [ `first` , `last` ) и возвращает итератор, который обозначает первый элемент, оставшийся после удаления элементов, или значение, `end()` Если такого элемента не существует. Он используется для удаления непрерывных или более смежных элементов.

Третья функция-член удаляет любой элемент управляемой последовательности, ключ которой имеет эквивалентное упорядочение к *ключу*, и возвращает количество удаленных элементов. Он используется для удаления и подсчета всех элементов, соответствующих указанному ключу.

Каждый элемент очистки принимает время пропорционально логарифму числа элементов в управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_erase.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    cliext::hash_multimap<wchar_t, int> c1;
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'a', 1));
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'b', 2));
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (cliext::hash_multimap<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase an element and reinspect
    cliext::hash_multimap<wchar_t, int>::iterator it =
        c1.erase(c1.begin());
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",
        it->first, it->second);

    // add elements and display " b c d e"
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'd', 4));
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'e', 5));
    for each (cliext::hash_multimap<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase all but end
    it = c1.end();
    it = c1.erase(c1.begin(), --it);
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",
        it->first, it->second);
    System::Console::WriteLine("size() = {0}", c1.size());

    // erase end
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
erase(begin()) = [b 2]
[b 2] [c 3] [d 4] [e 5]
erase(begin(), end()-1) = [e 5]
size() = 1
erase(L'x') = 0
erase(L'e') = 1
```

## <a name="hash_multimapfind-stlclr"></a><a name="find"></a>hash_multimap:: Find (STL/CLR)

Определяет элемент, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Если хотя бы один элемент в управляемой последовательности имеет эквивалентное упорядочение с *ключом*, функция – член возвращает итератор, обозначающий один из этих элементов. в противном случае возвращается [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md) `()` . Его можно использовать для поиска элемента, находящегося в управляемой последовательности, соответствующей указанному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_find.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());

    Myhash_multimap::iterator it = c1.find(L'b');
    System::Console::WriteLine("find {0} = [{1} {2}]",
        L'b', it->first, it->second);

    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
find A = False
find b = [b 2]
find C = False
```

## <a name="hash_multimapgeneric_container-stlclr"></a><a name="generic_container"></a>hash_multimap:: generic_container (STL/CLR)

Тип универсального интерфейса для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::
    IHash<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Примечания

Тип описывает универсальный интерфейс для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_generic_container.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multimap::generic_container^ gc1 = %c1;
    for each (Myhash_multimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(Myhash_multimap::make_value(L'd', 4));
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(Myhash_multimap::make_value(L'e', 5));
    for each (Myhash_multimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3] [d 4] [e 5]
```

## <a name="hash_multimapgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>hash_multimap:: generic_iterator (STL/CLR)

Тип итератора для использования с универсальным интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает универсальный итератор, который можно использовать с универсальным интерфейсом для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_generic_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multimap::generic_container^ gc1 = %c1;
    for each (Myhash_multimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multimap::generic_iterator gcit = gc1->begin();
    Myhash_multimap::generic_value gcval = *gcit;
    System::Console::Write("[{0} {1}] ", gcval->first, gcval->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="hash_multimapgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>hash_multimap:: generic_reverse_iterator (STL/CLR)

Тип реверсивного итератора для использования с универсальным интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает универсальный обратный итератор, который можно использовать с универсальным интерфейсом для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multimap::generic_container^ gc1 = %c1;
    for each (Myhash_multimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multimap::generic_reverse_iterator gcit = gc1->rbegin();
    Myhash_multimap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3]
```

## <a name="hash_multimapgeneric_value-stlclr"></a><a name="generic_value"></a>hash_multimap:: generic_value (STL/CLR)

Тип элемента для использования с универсальным интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Примечания

Тип описывает объект типа `GValue` , описывающий сохраненное значение элемента для использования с универсальным интерфейсом для данного класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_generic_value.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multimap::generic_container^ gc1 = %c1;
    for each (Myhash_multimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multimap::generic_iterator gcit = gc1->begin();
    Myhash_multimap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="hash_multimaphash_delegate-stlclr"></a><a name="hash_delegate"></a>hash_multimap:: hash_delegate (STL/CLR)

Определяет элемент, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
hasher^ hash_delegate();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает делегат, используемый для преобразования значения ключа в целое число. Он используется для хэширования ключа.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_hash_delegate.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_multimaphash_multimap-stlclr"></a><a name="hash_multimap"></a>hash_multimap:: hash_multimap (STL/CLR)

Создает объект контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
hash_multimap();
explicit hash_multimap(key_compare^ pred);
hash_multimap(key_compare^ pred, hasher^ hashfn);
hash_multimap(hash_multimap<Key, Mapped>% right);
hash_multimap(hash_multimap<Key, Mapped>^ right);
template<typename InIter>
    hash_multimaphash_multimap(InIter first, InIter last);
template<typename InIter>
    hash_multimap(InIter first, InIter last,
        key_compare^ pred);
template<typename InIter>
    hash_multimap(InIter first, InIter last,
        key_compare^ pred, hasher^ hashfn);
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right);
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred, hasher^ hashfn);
```

#### <a name="parameters"></a>Параметры

*first*<br/>
Начало диапазона для вставки.

*хашфн*<br/>
Хэш-функция для сопоставления ключей с сегментами.

*last*<br/>
Конец диапазона для вставки.

*Возможен*<br/>
Упорядочение предиката для управляемой последовательности.

*Правильно*<br/>
Объект или диапазон для вставки.

### <a name="remarks"></a>Примечания

Конструктор:

`hash_multimap();`

инициализирует управляемую последовательность без элементов, с предикатом упорядочения по умолчанию `key_compare()` и с хэш-функцией по умолчанию. Он используется для указания пустой начальной управляемой последовательности с предикатом упорядочения по умолчанию и хэш-функцией.

Конструктор:

`explicit hash_multimap(key_compare^ pred);`

инициализирует управляемую последовательность без элементов, с помощью предиката порядка " *пред*" и с хэш-функцией по умолчанию. Он используется для указания пустой начальной управляемой последовательности с указанным предикатом упорядочения и хэш-функцией по умолчанию.

Конструктор:

`hash_multimap(key_compare^ pred, hasher^ hashfn);`

инициализирует управляемую последовательность без элементов, с помощью предиката порядка " *пред*" и хэш-функции *хашфн*. Он используется для указания пустой начальной управляемой последовательности с указанным предикатом упорядочения и хэш-функцией.

Конструктор:

`hash_multimap(hash_multimap<Key, Mapped>% right);`

инициализирует управляемую последовательность с помощью последовательности [ `right.begin()` , `right.end()` ), с предикатом упорядочения по умолчанию и с хэш-функцией по умолчанию. Он используется для указания начальной управляемой последовательности, которая является копией последовательности, управляемой объектом hash_multimap *right*, с предикатом упорядочения по умолчанию и хэш-функцией.

Конструктор:

`hash_multimap(hash_multimap<Key, Mapped>^ right);`

инициализирует управляемую последовательность с помощью последовательности [ `right->begin()` , `right->end()` ), с предикатом упорядочения по умолчанию и с хэш-функцией по умолчанию. Он используется для указания начальной управляемой последовательности, которая является копией последовательности, управляемой объектом hash_multimap *right*, с предикатом упорядочения по умолчанию и хэш-функцией.

Конструктор:

`template<typename InIter> hash_multimap(InIter first, InIter last);`

инициализирует управляемую последовательность с помощью последовательности [ `first` , `last` ), с предикатом упорядочения по умолчанию и с хэш-функцией по умолчанию. Он используется для того, чтобы управляемая последовательность была копией другой последовательности с предикатом упорядочения по умолчанию и хэш-функцией.

Конструктор:

`template<typename InIter> hash_multimap(InIter first, InIter last, key_compare^ pred);`

инициализирует управляемую последовательность с помощью последовательности [ `first` , `last` ), с помощью предиката порядка " *пред*" и с хэш-функцией по умолчанию. Он используется для того, чтобы управляемая последовательность была копией другой последовательности с указанным предикатом упорядочения и хэш-функцией по умолчанию.

Конструктор:

`template<typename InIter> hash_multimap(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`

инициализирует управляемую последовательность с помощью последовательности [ `first` , `last` ), с помощью предиката порядка " *пред*" и хэш-функции *хашфн*. Он используется для того, чтобы управляемая последовательность была копией другой последовательности с указанным предикатом упорядочения и хэш-функцией.

Конструктор:

`hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right);`

инициализирует управляемую последовательность с последовательностью, обозначенной *справа*перечислителем, с предикатом упорядочивания по умолчанию и с хэш-функцией по умолчанию. Он используется для того, чтобы управляемая последовательность была копией другой последовательности, описываемой перечислителем, с предикатом упорядочения по умолчанию и хэш-функцией.

Конструктор:

`hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

инициализирует управляемую последовательность с помощью последовательности, обозначенной *правым*перечислителем, с помощью предиката упорядочения *пред*и с хэш-функцией по умолчанию. Он используется для того, чтобы управляемая последовательность была копией другой последовательности, описываемой перечислителем, с указанным предикатом упорядочения и хэш-функцией по умолчанию.

Конструктор:

`hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`

инициализирует управляемую последовательность с помощью последовательности, обозначенной *правым*перечислителем, с помощью предиката упорядочения *пред*и с помощью хэш-функции *хашфн*. Он используется для того, чтобы управляемая последовательность была копией другой последовательности, описываемой перечислителем, с указанным предикатом упорядочения и хэш-функцией.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_construct.cpp
// compile with: /clr
#include <cliext/hash_map>

int myfun(wchar_t key)
    { // hash a key
    return (key ^ 0xdeadbeef);
    }

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
// construct an empty container
    Myhash_multimap c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an ordering rule
    Myhash_multimap c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (Myhash_multimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an ordering rule and hash function
    Myhash_multimap c2h(cliext::greater_equal<wchar_t>(),
        gcnew Myhash_multimap::hasher(&myfun));
    System::Console::WriteLine("size() = {0}", c2h.size());

    c2h.insert(c1.begin(), c1.end());
    for each (Myhash_multimap::value_type elem in c2h)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an iterator range
    Myhash_multimap c3(c1.begin(), c1.end());
    for each (Myhash_multimap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Myhash_multimap c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (Myhash_multimap::value_type elem in c4)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule and hash function
    Myhash_multimap c4h(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>(),
        gcnew Myhash_multimap::hasher(&myfun));
    for each (Myhash_multimap::value_type elem in c4h)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an enumeration
    Myhash_multimap c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Myhash_multimap::value_type>^)%c3);
    for each (Myhash_multimap::value_type elem in c5)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Myhash_multimap c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Myhash_multimap::value_type>^)%c3,
                cliext::greater_equal<wchar_t>());
    for each (Myhash_multimap::value_type elem in c6)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule and hash function
    Myhash_multimap c6h(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Myhash_multimap::value_type>^)%c3,
                cliext::greater_equal<wchar_t>(),
                gcnew Myhash_multimap::hasher(&myfun));
    for each (Myhash_multimap::value_type elem in c6h)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct by copying another container
    Myhash_multimap c7(c4);
    for each (Myhash_multimap::value_type elem in c7)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct by copying a container handle
    Myhash_multimap c8(%c3);
    for each (Myhash_multimap::value_type elem in c8)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
[a 1] [b 2] [c 3]
size() = 0
[a 1] [b 2] [c 3]
size() = 0
[c 3] [b 2] [a 1]

[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]

[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]

[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
```

## <a name="hash_multimaphasher-stlclr"></a><a name="hasher"></a>hash_multimap:: hashing (STL/CLR)

Делегат хеширования для ключа.

### <a name="syntax"></a>Синтаксис

```cpp
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>
    hasher;
```

### <a name="remarks"></a>Примечания

Тип описывает делегат, который преобразует значение ключа в целое число.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_hasher.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_multimapinsert-stlclr"></a><a name="insert"></a>hash_multimap:: Insert (STL/CLR)

Добавляет элементы.

### <a name="syntax"></a>Синтаксис

```cpp
iterator insert(value_type val);
iterator insert(iterator where, value_type val);
template<typename InIter>
    void insert(InIter first, InIter last);
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);
```

#### <a name="parameters"></a>Параметры

*first*<br/>
Начало диапазона для вставки.

*last*<br/>
Конец диапазона для вставки.

*Правильно*<br/>
Перечисление для вставки.

*Val*<br/>
Значение ключа для вставки.

*where*<br/>
Место вставки в контейнере (только указание).

### <a name="remarks"></a>Примечания

Каждая из функций-членов вставляет последовательность, указанную оставшимися операндами.

Первая функция члена вставляет элемент со значением *Val*и возвращает итератор, указывающий на вновь вставленный элемент. Он используется для вставки одного элемента.

Вторая функция-член вставляет элемент со значением *Val*, использование *WHERE* в качестве подсказки (для повышения производительности) и возвращает итератор, указывающий на вновь вставленный элемент. Он используется для вставки одного элемента, который может быть рядом с знакомым элементом.

Третья функция-член вставляет последовательность [ `first` , `last` ). Он используется для вставки одного или нескольких элементов, скопированных из другой последовательности.

Четвертая функция с членом вставляет последовательность, обозначенную *справа*. Он используется для вставки последовательности, описанной перечислителем.

Каждая Вставка элемента занимает время пропорционально логарифму числа элементов в управляемой последовательности. Вставка может происходить в неизменном времени, однако при наличии подсказки, которая обозначает элемент, смежный с точкой вставки.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_insert.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
    Myhash_multimap::iterator it =
        c1.insert(Myhash_multimap::make_value(L'x', 24));
    System::Console::WriteLine("insert([L'x' 24]) = [{0} {1}]",
        it->first, it->second);

    it = c1.insert(Myhash_multimap::make_value(L'b', 2));
    System::Console::WriteLine("insert([L'b' 2]) = [{0} {1}]",
        it->first, it->second);

    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value with hint
    it = c1.insert(c1.begin(), Myhash_multimap::make_value(L'y', 25));
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",
        it->first, it->second);
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an iterator range
    Myhash_multimap c2;
    it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (Myhash_multimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an enumeration
    Myhash_multimap c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::
            IEnumerable<Myhash_multimap::value_type>^)%c1);
    for each (Myhash_multimap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
insert([L'x' 24]) = [x 24]
insert([L'b' 2]) = [b 2]
[a 1] [b 2] [b 2] [c 3] [x 24]
insert(begin(), [L'y' 25]) = [y 25]
[a 1] [b 2] [b 2] [c 3] [x 24] [y 25]
[a 1] [b 2] [b 2] [c 3] [x 24]
[a 1] [b 2] [b 2] [c 3] [x 24] [y 25]
```

## <a name="hash_multimapiterator-stlclr"></a><a name="iterator"></a>hash_multimap:: iterator (STL/CLR)

Тип итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает объект неопределенного типа `T1` , который может использоваться в качестве двунаправленного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_multimap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("[{0} {1}] ", it->first, it->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapkey_comp-stlclr"></a><a name="key_comp"></a>hash_multimap:: key_comp (STL/CLR)

Копирует делегат упорядочения для двух ключей.

### <a name="syntax"></a>Синтаксис

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Примечания

Функция – член возвращает делегат упорядочивания, используемый для упорядочивания управляемой последовательности. Используется для сравнения двух ключей.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_key_comp.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_multimap c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="hash_multimapkey_compare-stlclr"></a><a name="key_compare"></a>hash_multimap:: key_compare (STL/CLR)

Делегат упорядочения для двух ключей.

### <a name="syntax"></a>Синтаксис

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>Примечания

Тип является синонимом делегата, который определяет порядок ключевых аргументов.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_key_compare.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_multimap c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="hash_multimapkey_type-stlclr"></a><a name="key_type"></a>hash_multimap:: key_type (STL/CLR)

Тип ключа упорядочения.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для *ключа*параметра шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_key_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using key_type
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myhash_multimap::key_type val = it->first;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_multimapload_factor-stlclr"></a><a name="load_factor"></a>hash_multimap:: load_factor (STL/CLR)

Подсчитывает среднее число элементов в блоке.

### <a name="syntax"></a>Синтаксис

```cpp
float load_factor();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает `(float)` [hash_multimap:: size (STL/CLR)](../dotnet/hash-multimap-size-stl-clr.md) `() /` [hash_multimap:: bucket_count (STL/CLR)](../dotnet/hash-multimap-bucket-count-stl-clr.md) `()` . Он используется для определения среднего размера контейнера.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_load_factor.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1 = gcnew Myhash_multimap;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_multimaplower_bound-stlclr"></a><a name="lower_bound"></a>hash_multimap:: lower_bound (STL/CLR)

Находит начало диапазона, совпадающее с указанным ключом.

### <a name="syntax"></a>Синтаксис

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Функция-член определяет первый элемент `X` в управляемой последовательности, который хэшируется в тот же контейнер, что и *ключ* , и имеет эквивалентное упорядочение к *ключу*. Если такого элемента не существует, он возвращает [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md) `()` ; в противном случае возвращается итератор, который обозначает `X` . Он используется для поиска начала последовательности элементов, находящихся в управляемой последовательности, соответствующей указанному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_lower_bound.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    Myhash_multimap::iterator it = c1.lower_bound(L'a');
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",
        it->first, it->second);
    it = c1.lower_bound(L'b');
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
lower_bound(L'x')==end() = True
*lower_bound(L'a') = [a 1]
*lower_bound(L'b') = [b 2]
```

## <a name="hash_multimapmake_value-stlclr"></a><a name="make_value"></a>hash_multimap:: make_value (STL/CLR)

Конструирует объект значения.

### <a name="syntax"></a>Синтаксис

```cpp
static value_type make_value(key_type key, mapped_type mapped);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Используемое значение ключа.

*управляем*<br/>
Сопоставленное значение для поиска.

### <a name="remarks"></a>Примечания

Функция-член возвращает `value_type` объект, ключ которого является *ключом* , а сопоставленное значение *сопоставлено*. Он используется для составления объекта, подходящего для использования с несколькими другими функциями элементов.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_make_value.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapmapped_type-stlclr"></a><a name="mapped_type"></a>hash_multimap:: mapped_type (STL/CLR)

Тип сопоставленного значения, связанного с каждым ключом.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Mapped mapped_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом *сопоставленного*параметра шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_mapped_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using mapped_type
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in mapped_type object
        Myhash_multimap::mapped_type val = it->second;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
1 2 3
```

## <a name="hash_multimapmax_load_factor-stlclr"></a><a name="max_load_factor"></a>hash_multimap:: max_load_factor (STL/CLR)

Возвращает или задает максимальное количество элементов в блоке.

### <a name="syntax"></a>Синтаксис

```cpp
float max_load_factor();
void max_load_factor(float new_factor);
```

#### <a name="parameters"></a>Параметры

*new_factor*<br/>
Новый максимальный коэффициент нагрузки для хранения.

### <a name="remarks"></a>Примечания

Первая функция – член возвращает текущий сохраненный фактор максимальной нагрузки. Он используется для определения максимального среднего размера контейнера.

Вторая функция – член заменяет максимальный коэффициент загрузки хранилища на *new_factor*. Автоматическая повторная хэширование не происходит до последующей вставки.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_max_load_factor.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1 = gcnew Myhash_multimap;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_multimapoperator-stlclr"></a><a name="op"></a>hash_multimap::operator= (STL/CLR)

Заменяет управляемую последовательность.

### <a name="syntax"></a>Синтаксис

```cpp
hash_multimap<Key, Mapped>% operator=(hash_multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Контейнер для копирования.

### <a name="remarks"></a>Примечания

Оператор члена копирует *прямо* в объект, а затем возвращает **`*this`** . Он используется для замены управляемой последовательности копией управляемой последовательности в *правой части*.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_operator_as.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Myhash_multimap c2;
    c2 = c1;
// display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
```

## <a name="hash_multimaprbegin-stlclr"></a><a name="rbegin"></a>hash_multimap:: rbegin (STL/CLR)

Задает начало обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает обратный итератор, обозначающий последний элемент управляемой последовательности или сразу за началом пустой последовательности. Таким образом, он задает для обратной последовательности параметр `beginning`. Используется для получения итератора, который задает начало управляемой последовательности с параметром `current`, отображаемой в обратном порядке, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_rbegin.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Myhash_multimap::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = [{0} {1}]",
        rit->first, rit->second);
    ++rit;
    System::Console::WriteLine("*++rbegin() = [{0} {1}]",
        rit->first, rit->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*rbegin() = [c 3]
*++rbegin() = [b 2]
```

## <a name="hash_multimapreference-stlclr"></a><a name="reference"></a>hash_multimap:: Reference (STL/CLR)

Тип ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Примечания

Тип описывает ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_reference.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_multimap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myhash_multimap::reference ref = *it;
        System::Console::Write("[{0} {1}] ", ref->first, ref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="hash_multimaprehash-stlclr"></a><a name="rehash"></a>hash_multimap:: rehash (STL/CLR)

Повторно создает хэш-таблицу.

### <a name="syntax"></a>Синтаксис

```cpp
void rehash();
```

### <a name="remarks"></a>Примечания

Функция-член перестраивает таблицу хэширования, гарантируя, что [hash_multimap:: load_factor (STL/CLR)](../dotnet/hash-multimap-load-factor-stl-clr.md) `() <=` [hash_multimap:: max_load_factor (STL/CLR)](../dotnet/hash-multimap-max-load-factor-stl-clr.md). В противном случае размер хэш-таблицы увеличивается только по мере необходимости после вставки. (Размер не уменьшается автоматически.) Он используется для корректировки размера хэш-таблицы.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_rehash.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1 = gcnew Myhash_multimap;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_multimaprend-stlclr"></a><a name="rend"></a>hash_multimap:: rend (STL/CLR)

Задает конец обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает обратный итератор, указывающий сразу за начало управляемой последовательности. Таким образом, он задает для обратной последовательности параметр `end`. Используется для получения итератора, который задает конец управляемой последовательности с параметром `current`, отображаемой в обратном порядке, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_rend.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Myhash_multimap::reverse_iterator rit = c1.rend();
    --rit;
    --rit;
    System::Console::WriteLine("*-- --rend() = [{0} {1}]",
        rit->first, rit->second);
    ++rit;
    System::Console::WriteLine("*--rend() = [{0} {1}]",
        rit->first, rit->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*-- --rend() = [b 2]
*--rend() = [a 1]
```

## <a name="hash_multimapreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>hash_multimap:: reverse_iterator (STL/CLR)

Тип обратного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает объект неопределенного типа `T3` , который может служить в качестве реверсивного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Myhash_multimap::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("[{0} {1}] ", rit->first, rit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="hash_multimapsize-stlclr"></a><a name="size"></a>hash_multimap:: size (STL/CLR)

Подсчитывает количество элементов.

### <a name="syntax"></a>Синтаксис

```cpp
size_type size();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает длину управляемой последовательности. Он используется для определения количества элементов, находящихся в настоящий момент в управляемой последовательности. Если вас интересует только то, имеет ли последовательность ненулевой размер, см. раздел [hash_multimap:: Empty (STL/CLR)](../dotnet/hash-multimap-empty-stl-clr.md) `()` .

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_size.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(Myhash_multimap::make_value(L'd', 4));
    c1.insert(Myhash_multimap::make_value(L'e', 5));
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="hash_multimapsize_type-stlclr"></a><a name="size_type"></a>hash_multimap:: size_type (STL/CLR)

Тип расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Примечания

Тип описывает неотрицательное число элементов.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_size_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_multimap::size_type diff = 0;
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
```

## <a name="hash_multimapswap-stlclr"></a><a name="swap"></a>hash_multimap:: Swap (STL/CLR)

Меняет местами содержимое двух контейнеров.

### <a name="syntax"></a>Синтаксис

```cpp
void swap(hash_multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Контейнер для обмена содержимым.

### <a name="remarks"></a>Примечания

Функция – член меняет местами управляемые последовательности между **`this`** и *вправо*. Это происходит в постоянном времени и не создает исключений. Он используется в качестве быстрого способа обмена содержимым двух контейнеров.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_swap.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Myhash_multimap c2;
    c2.insert(Myhash_multimap::make_value(L'd', 4));
    c2.insert(Myhash_multimap::make_value(L'e', 5));
    c2.insert(Myhash_multimap::make_value(L'f', 6));
    for each (Myhash_multimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    for each (Myhash_multimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[d 4] [e 5] [f 6]
[d 4] [e 5] [f 6]
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapto_array-stlclr"></a><a name="to_array"></a>hash_multimap:: to_array (STL/CLR)

Копирует управляемую последовательность в новый массив.

### <a name="syntax"></a>Синтаксис

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Примечания

Функция члена возвращает массив, содержащий управляемую последовательность. Он используется для получения копии управляемой последовательности в виде массива.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_to_array.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // copy the container and modify it
    cli::array<Myhash_multimap::value_type>^ a1 = c1.to_array();

    c1.insert(Myhash_multimap::make_value(L'd', 4));
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (Myhash_multimap::value_type elem in a1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapupper_bound-stlclr"></a><a name="upper_bound"></a>hash_multimap:: upper_bound (STL/CLR)

Находит конец диапазона, соответствующий указанному ключу.

### <a name="syntax"></a>Синтаксис

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Параметры

*key*<br/>
Искомое значение ключа.

### <a name="remarks"></a>Примечания

Функция-член определяет последний элемент `X` в управляемой последовательности, который хэшируется в тот же контейнер, что и *ключ* , и имеет эквивалентное упорядочение к *ключу*. Если такого элемента не существует или если `X` является последним элементом управляемой последовательности, возвращается [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md) `()` ; в противном случае возвращается итератор, обозначающий первый элемент за пределами `X` . Он используется для поиска конца последовательности элементов, находящихся в управляемой последовательности, соответствующей указанному ключу.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_upper_bound.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    Myhash_multimap::iterator it = c1.upper_bound(L'a');
    System::Console::WriteLine("*upper_bound(L'a') = [{0} {1}]",
        it->first, it->second);
    it = c1.upper_bound(L'b');
    System::Console::WriteLine("*upper_bound(L'b') = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
upper_bound(L'x')==end() = True
*upper_bound(L'a') = [b 2]
*upper_bound(L'b') = [c 3]
```

## <a name="hash_multimapvalue_comp-stlclr"></a><a name="value_comp"></a>hash_multimap:: value_comp (STL/CLR)

Копирует делегат упорядочения для двух значений элементов.

### <a name="syntax"></a>Синтаксис

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Примечания

Функция – член возвращает делегат упорядочивания, используемый для упорядочивания управляемой последовательности. Он используется для сравнения двух значений элементов.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_value_comp.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Myhash_multimap::make_value(L'a', 1),
            Myhash_multimap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Myhash_multimap::make_value(L'a', 1),
            Myhash_multimap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Myhash_multimap::make_value(L'b', 2),
            Myhash_multimap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = True
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="hash_multimapvalue_compare-stlclr"></a><a name="value_compare"></a>hash_multimap:: value_compare (STL/CLR)

Делегат упорядочивания для двух значений элементов.

### <a name="syntax"></a>Синтаксис

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>Примечания

Тип является синонимом делегата, который определяет порядок аргументов его значения.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_value_compare.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Myhash_multimap::make_value(L'a', 1),
            Myhash_multimap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Myhash_multimap::make_value(L'a', 1),
            Myhash_multimap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Myhash_multimap::make_value(L'b', 2),
            Myhash_multimap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = True
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="hash_multimapvalue_type-stlclr"></a><a name="value_type"></a>hash_multimap:: value_type (STL/CLR)

Тип элемента.

### <a name="syntax"></a>Синтаксис

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `generic_value`.

### <a name="example"></a>Пример

```cpp
// cliext_hash_multimap_value_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using value_type
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myhash_multimap::value_type val = *it;
        System::Console::Write("[{0} {1}] ", val->first, val->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```
