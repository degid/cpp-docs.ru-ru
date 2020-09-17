---
title: Класс concurrent_unordered_map
ms.date: 11/04/2016
f1_keywords:
- concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::at
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::hash_function
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::insert
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::key_eq
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::swap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::unsafe_erase
helpviewer_keywords:
- concurrent_unordered_map class
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
ms.openlocfilehash: eb2493c3e3303a80c9825620aae0c2ef5270a71a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230341"
---
# <a name="concurrent_unordered_map-class"></a>Класс concurrent_unordered_map

Класс `concurrent_unordered_map` представляет собой безопасный в отношении параллелизма контейнер, управляющий последовательностью элементов типа `std::pair<const K, _Element_type>` переменной длины. Последовательность представлена таким образом, что позволяет параллельно-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename K,
    typename _Element_type,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<std::pair<const K,
    _Element_type>>
>,
typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<std::pair<const K,
    _Element_type>>> class concurrent_unordered_map : public details::_Concurrent_hash<details::_Concurrent_unordered_map_traits<K,
    _Element_type,
details::_Hash_compare<K,
    _Hasher,
key_equality>,
    _Allocator_type,
false>>;
```

### <a name="parameters"></a>Параметры

*Занят*<br/>
Тип ключа.

*_Element_type*<br/>
Сопоставленный тип.

*_Hasher*<br/>
Тип объекта хэш-функции. Этот аргумент является необязательным, и значением по умолчанию является `std::hash<K>`.

*key_equality*<br/>
Тип объекта функции сравнения на предмет равенства. Этот аргумент является необязательным, и значением по умолчанию является `std::equal_to<K>`.

*_Allocator_type*<br/>
Тип, представляющий сохраненный объект распределителя, который инкапсулирует сведения о выделении и освобождении памяти для параллельной неупорядоченной схемы. Этот аргумент является необязательным, и значение по умолчанию — `std::allocator<std::pair<K` , `_Element_type>>` .

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`allocator_type`|Тип распределителя для управления хранилищем.|
|`const_iterator`|Тип постоянного итератора для управляемой последовательности.|
|`const_local_iterator`|Тип постоянного итератора блока для управляемой последовательности.|
|`const_pointer`|Тип постоянного указателя на элемент.|
|`const_reference`|Тип постоянной ссылки на элемент.|
|`difference_type`|Тип расстояния со знаком между двумя элементами.|
|`hasher`|Тип хэш-функции.|
|`iterator`|Тип итератора для управляемой последовательности.|
|`key_equal`|Тип функции сравнения.|
|`key_type`|Тип ключа упорядочения.|
|`local_iterator`|Тип итератора блока для управляемой последовательности.|
|`mapped_type`|Тип сопоставленного значения, связанного с каждым ключом.|
|`pointer`|Тип указателя на элемент.|
|`reference`|Тип ссылки на элемент.|
|`size_type`|Тип беззнакового расстояния между двумя элементами.|
|`value_type`|Тип элемента.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[concurrent_unordered_map](#ctor)|Перегружен. Конструирует параллельную неупорядоченную карту.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[at](#at)|Перегружен. Находит элемент в `concurrent_unordered_map` с указанным значением ключа. Этот метод является типобезопасным в режиме параллелизма.|
|[hash_function](#hash_function)|Получает сохраненный объект хэш-функции.|
|[insert](#insert)|Перегружен. Добавляет элементы в `concurrent_unordered_map` объект.|
|[key_eq](#key_eq)|Возвращает сохраненный объект функции сравнения равенства.|
|[swap](#swap)|Меняет местами содержимое двух объектов `concurrent_unordered_map`. Этот метод не является типобезопасным в режиме параллелизма.|
|[unsafe_erase](#unsafe_erase)|Перегружен. Удаляет элементы из `concurrent_unordered_map` указанных позиций. Этот метод не является типобезопасным в режиме параллелизма.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор\[\]](#operator_at)|Перегружен. Находит или вставляет элемент с указанным ключом. Этот метод является типобезопасным в режиме параллелизма.|
|[operator=](#operator_eq)|Перегружен. Присваивает `concurrent_unordered_map` этому объекту содержимое другого объекта. Этот метод не является типобезопасным в режиме параллелизма.|

## <a name="remarks"></a>Примечания

Подробные сведения о `concurrent_unordered_map` классе см. в разделе [Parallel Containers and Objects](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_Traits`

`_Concurrent_hash`

`concurrent_unordered_map`

## <a name="requirements"></a>Требования

**Заголовок:** concurrent_unordered_map.h

**Пространство имен:** concurrency

## <a name="at"></a><a name="at"></a>в

Находит элемент в `concurrent_unordered_map` с указанным значением ключа. Этот метод является типобезопасным в режиме параллелизма.

```cpp
mapped_type& at(const key_type& KVal);

const mapped_type& at(const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*квал*<br/>
Значение ключа, которое необходимо найти.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на значение данных найденного элемента.

### <a name="remarks"></a>Примечания

Если значение ключа аргумента не найдено, функция создает объект класса `out_of_range`.

## <a name="begin"></a><a name="begin"></a>начале

Возвращает итератор, указывающий на первый элемент в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```cpp
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор на первый элемент в параллельном контейнере.

## <a name="cbegin"></a><a name="cbegin"></a>cbegin

Возвращает константный итератор, указывающий на первый элемент в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный итератор для первого элемента в параллельном контейнере.

## <a name="cend"></a><a name="cend"></a>cend

Возвращает константный итератор, указывающий на расположение, следующее за последним элементом в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный итератор к расположению, следующему за последним элементом в параллельном контейнере.

## <a name="clear"></a><a name="clear"></a>открытым

Стирает все элементы в параллельном контейнере. Эта функция не является типобезопасным.

```cpp
void clear();
```

## <a name="concurrent_unordered_map"></a><a name="ctor"></a>concurrent_unordered_map

Конструирует параллельную неупорядоченную карту.

```cpp
explicit concurrent_unordered_map(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_map(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_map(_Iterator _Begin,
    _Iterator _End,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_map(
    const concurrent_unordered_map& _Umap);

concurrent_unordered_map(
    const concurrent_unordered_map& _Umap,
    const allocator_type& _Allocator);

concurrent_unordered_map(
    concurrent_unordered_map&& _Umap);
```

### <a name="parameters"></a>Параметры

*_Iterator*<br/>
Тип итератора ввода.

*_Number_of_buckets*<br/>
Начальное число сегментов для этой неупорядоченной схемы.

*_Hasher*<br/>
Хэш-функция для этой неупорядоченной схемы.

*key_equality*<br/>
Функция сравнения на равенство для этой неупорядоченной схемы.

*_Allocator*<br/>
Распределитель для этой неупорядоченной схемы.

*_Begin*<br/>
Положение первого элемента в диапазоне копируемых элементов.

*_End*<br/>
Положение первого элемента после диапазона копируемых элементов.

*_Umap*<br/>
Исходный объект `concurrent_unordered_map` для копирования или перемещения элементов.

### <a name="remarks"></a>Примечания

Все конструкторы хранят объект распределителя `_Allocator` и инициализируют неупорядоченную карту.

Первый конструктор указывает пустую начальную карту и явно указывает количество сегментов, хэш-функции, функции равенства и типа распределителя для использования.

Второй конструктор указывает распределитель для неупорядоченной схемы.

Третий конструктор указывает значения, предоставляемые диапазоном итератора [ `_Begin` , `_End` ).

Четвертый и пятый конструкторы указывают копию параллельной неупорядоченной таблицы `_Umap` .

Последний конструктор задает перемещение параллельной неупорядоченной таблицы `_Umap` .

## <a name="count"></a><a name="count"></a>расчета

Подсчитывает количество элементов, соответствующих указанному ключу. Эта функция является потенциальной в режиме параллелизма.

```cpp
size_type count(const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*квал*<br/>
Ключ, который нужно найти.

### <a name="return-value"></a>Возвращаемое значение

Количество раз, когда ключ отображается в контейнере.

## <a name="empty"></a><a name="empty"></a>указано

Проверяет отсутствие элементов. Данный метод безопасен в режиме параллелизма.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если параллельный контейнер пуст; **`false`** в противном случае —.

### <a name="remarks"></a>Примечания

При наличии параллельных вставок независимо от того, является ли параллельный контейнер пустым, может измениться сразу после вызова этой функции, прежде чем возвращаемое значение будет считаться четным.

## <a name="end"></a><a name="end"></a>конце

Возвращает итератор, указывающий на расположение, следующее за последним элементом в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```cpp
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор на расположение, на котором заканчивается последний элемент в параллельном контейнере.

## <a name="equal_range"></a><a name="equal_range"></a>equal_range

Находит диапазон, соответствующий указанному ключу. Эта функция является потенциальной в режиме параллелизма.

```cpp
std::pair<iterator,
    iterator> equal_range(
    const key_type& KVal);

std::pair<const_iterator,
    const_iterator> equal_range(
    const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*квал*<br/>
Искомое значение ключа.

### <a name="return-value"></a>Возвращаемое значение

[Пара](../../../standard-library/pair-structure.md) , в которой первый элемент является итератором на начало, а второй элемент — итератором на конец диапазона.

### <a name="remarks"></a>Примечания

Одновременные вставки могут привести к вставке дополнительных ключей после итератора begin и перед конечным итератором.

## <a name="find"></a><a name="find"></a>Найдено

Определяет элемент, соответствующий указанному ключу. Эта функция является потенциальной в режиме параллелизма.

```cpp
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*квал*<br/>
Искомое значение ключа.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на расположение первого элемента, совпадающего с предоставленным ключом, или итератор, `end()` Если такого элемента не существует.

## <a name="get_allocator"></a><a name="get_allocator"></a>get_allocator

Возвращает сохраненный объект распределителя для этого параллельного контейнера. Данный метод безопасен в режиме параллелизма.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект распределителя для этого параллельного контейнера.

## <a name="hash_function"></a><a name="hash_function"></a>hash_function

Получает сохраненный объект хэш-функции.

```cpp
hasher hash_function() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект хэш-функции.

## <a name="insert"></a><a name="insert"></a>Вставляет

Добавляет элементы в `concurrent_unordered_map` объект.

```cpp
std::pair<iterator,
    bool> insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
std::pair<iterator,
    bool> insert(
    V&& value);

template<class V>
typename std::enable_if<!std::is_same<const_iterator,
    typename std::remove_reference<V>::type>::value,
    iterator>::type insert(
    const_iterator _Where,
    V&& value);
```

### <a name="parameters"></a>Параметры

*_Iterator*<br/>
Тип итератора, используемый для вставки.

*3,3*<br/>
Тип значения, вставляемого в карту.

*value*<br/>
Вставляемое значение.

*_Where*<br/>
Начальное расположение для поиска точки вставки.

*first*<br/>
Начало вставляемого диапазона.

*last*<br/>
Конец вставляемого диапазона.

### <a name="return-value"></a>Возвращаемое значение

Пара, содержащая итератор и логическое значение. Дополнительные сведения см. в разделе "Примечания".

### <a name="remarks"></a>Примечания

Первая функция – член определяет, существует ли элемент X в последовательности, ключ которой имеет эквивалентное упорядочение `value` . В противном случае он создает такой элемент X и инициализирует его с помощью `value` . Затем функция определяет итератор `where` , обозначающий X. Если произошла Вставка, функция возвращает значение `std::pair(where, true)` . В противном случае возвращается значение `std::pair(where, false)`.

Вторая функция-член возвращает инструкцию INSERT ( `value` ), используя в `_Where` качестве начальной позиции в управляемой последовательности для поиска точки вставки.

Третья функция-член вставляет последовательность значений элементов из диапазона [ `first` , `last` ).

Последние две функции-члена ведут себя так же, как первые два, за исключением того, что `value` используется для создания вставленного значения.

## <a name="key_eq"></a><a name="key_eq"></a>key_eq

Возвращает сохраненный объект функции сравнения равенства.

```cpp
key_equal key_eq() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект функции сравнения равенства.

## <a name="load_factor"></a><a name="load_factor"></a>load_factor

Выполняет вычисление и возвращает текущий коэффициент загрузки контейнера. Коэффициент загрузки — это количество элементов в контейнере, деленное на количество сегментов.

```cpp
float load_factor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Коэффициент загрузки для контейнера.

## <a name="max_load_factor"></a><a name="max_load_factor"></a>max_load_factor

Возвращает или задает максимальный коэффициент загрузки контейнера. Максимальный коэффициент загрузки — это наибольшее число элементов, чем может быть в любом контейнере, прежде чем контейнер будет расти до размера внутренней таблицы.

```cpp
float max_load_factor() const;

void max_load_factor(float _Newmax);
```

### <a name="parameters"></a>Параметры

`_Newmax`

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает сохраненный коэффициент максимальной нагрузки. Вторая функция-член не возвращает значение, но вызывает исключение [out_of_range](../../../standard-library/out-of-range-class.md) , если указанный коэффициент загрузки является недопустимым.

## <a name="max_size"></a><a name="max_size"></a>max_size

Возвращает максимальный размер параллельного контейнера, определяемого распределителем. Данный метод безопасен в режиме параллелизма.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное число элементов, которые могут быть вставлены в этот параллельный контейнер.

### <a name="remarks"></a>Примечания

Это значение верхней границы может быть выше, чем на самом деле может храниться в контейнере.

## <a name="operator"></a><a name="operator_at"></a>operator []

Находит или вставляет элемент с указанным ключом. Этот метод является типобезопасным в режиме параллелизма.

```cpp
mapped_type& operator[](const key_type& kval);

mapped_type& operator[](key_type&& kval);
```

### <a name="parameters"></a>Параметры

*квал*<br/>
Значение ключа для

поиска или вставки.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на значение данных найденного или вставленного элемента.

### <a name="remarks"></a>Примечания

Если значение ключа аргумента не найдено, он вставляется вместе со значением по умолчанию для такого типа данных.

`operator[]` может использоваться для вставки элементов в сопоставление `m` с помощью `m[key] = DataValue;`, где `DataValue` — значение `mapped_type` элемента со значением ключа `key`.

При использовании `operator[]` для вставки элементов возвращаемая ссылка не отображает, меняет ли вставка уже существующий элемент или создает новый. Функции-члены `find` и [INSERT](#insert) можно использовать, чтобы определить, существует ли элемент с указанным ключом перед вставкой.

## <a name="operator"></a><a name="operator_eq"></a>Оператор =

Присваивает `concurrent_unordered_map` этому объекту содержимое другого объекта. Этот метод не является типобезопасным в режиме параллелизма.

```cpp
concurrent_unordered_map& operator= (const concurrent_unordered_map& _Umap);

concurrent_unordered_map& operator= (concurrent_unordered_map&& _Umap);
```

### <a name="parameters"></a>Параметры

*_Umap*<br/>
Исходный объект `concurrent_unordered_map`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `concurrent_unordered_map` объект.

### <a name="remarks"></a>Примечания

После удаления всех существующих элементов в параллельном векторе `operator=` либо копирует, либо перемещает содержимое `_Umap` в параллельный вектор.

## <a name="rehash"></a><a name="rehash"></a>rehash

Повторно создает хэш-таблицу.

```cpp
void rehash(size_type _Buckets);
```

### <a name="parameters"></a>Параметры

*_Buckets*<br/>
Необходимое количество сегментов.

### <a name="remarks"></a>Примечания

Функция-член устанавливает число сегментов не менее `_Buckets` и при необходимости перестраивает хэш-таблицу. Число сегментов должно быть степенью числа 2. Если не является степенью числа 2, она будет округляться до следующей самой крупной степени 2.

Он вызывает исключение [out_of_range](../../../standard-library/out-of-range-class.md) , если количество сегментов недопустимо (0 или больше максимального количества сегментов).

## <a name="size"></a><a name="size"></a>изменять

Возвращает число элементов в этом параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в контейнере.

### <a name="remarks"></a>Примечания

При наличии параллельных вставок число элементов в параллельном контейнере может измениться сразу после вызова этой функции даже до чтения возвращаемого значения.

## <a name="swap"></a><a name="swap"></a>позиции

Меняет местами содержимое двух объектов `concurrent_unordered_map`. Этот метод не является типобезопасным в режиме параллелизма.

```cpp
void swap(concurrent_unordered_map& _Umap);
```

### <a name="parameters"></a>Параметры

*_Umap*<br/>
Объект `concurrent_unordered_map` для обмена.

## <a name="unsafe_begin"></a><a name="unsafe_begin"></a>unsafe_begin

Возвращает итератор, который является первым элементом в этом контейнере для определенного контейнера.

```cpp
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс контейнера.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало контейнера.

## <a name="unsafe_bucket"></a><a name="unsafe_bucket"></a>unsafe_bucket

Возвращает индекс контейнера, сопоставляемый с указанным ключом в этом контейнере.

```cpp
size_type unsafe_bucket(const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*квал*<br/>
Искомый ключ элемента.

### <a name="return-value"></a>Возвращаемое значение

Индекс контейнера для ключа в этом контейнере.

## <a name="unsafe_bucket_count"></a><a name="unsafe_bucket_count"></a>unsafe_bucket_count

Возвращает текущее количество контейнеров в этом контейнере.

```cpp
size_type unsafe_bucket_count() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее число контейнеров в этом контейнере.

## <a name="unsafe_bucket_size"></a><a name="unsafe_bucket_size"></a>unsafe_bucket_size

Возвращает количество элементов в определенном контейнере этого контейнера.

```cpp
size_type unsafe_bucket_size(size_type _Bucket);
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Контейнер для поиска.

### <a name="return-value"></a>Возвращаемое значение

Текущее число контейнеров в этом контейнере.

## <a name="unsafe_cbegin"></a><a name="unsafe_cbegin"></a>unsafe_cbegin

Возвращает итератор, который является первым элементом в этом контейнере для определенного контейнера.

```cpp
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс контейнера.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало контейнера.

## <a name="unsafe_cend"></a><a name="unsafe_cend"></a>unsafe_cend

Возвращает итератор в позицию, которая завершилась после последнего элемента в определенном контейнере.

```cpp
const_local_iterator unsafe_cend(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс контейнера.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало контейнера.

## <a name="unsafe_end"></a><a name="unsafe_end"></a>unsafe_end

Возвращает итератор, который является последним элементом в этом контейнере для определенного контейнера.

```cpp
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс контейнера.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на конец контейнера.

## <a name="unsafe_erase"></a><a name="unsafe_erase"></a>unsafe_erase

Удаляет элементы из `concurrent_unordered_map` указанных позиций. Этот метод не является типобезопасным в режиме параллелизма.

```cpp
iterator unsafe_erase(
    const_iterator _Where);

iterator unsafe_erase(
    const_iterator _Begin,
    const_iterator _End);

size_type unsafe_erase(
    const key_type& KVal);
```

### <a name="parameters"></a>Параметры

*_Where*<br/>
Положение итератора для удаления.

*_Begin*<br/>
Положение первого элемента в диапазоне элементов для удаления.

*_End*<br/>
Положение первого элемента за пределами диапазона элементов для удаления.

*квал*<br/>
Значение ключа для удаления.

### <a name="return-value"></a>Возвращаемое значение

Первые две функции-члена возвращают итератор, который обозначает первый элемент, находящийся за всеми удаленными элементами, или `concurrent_unordered_map::end`(), если такой элемент не существует. Третья функция-член возвращает число элементов, которые она удаляет.

### <a name="remarks"></a>Примечания

Первая функция-член удаляет элемент управляемой последовательности, указанный параметром `_Where`. Вторая функция-член удаляет элементы в диапазоне [ `_Begin` , `_End` ).

Третья функция-член удаляет элементы в диапазоне, разделенном `concurrent_unordered_map::equal_range` (квал).

## <a name="unsafe_max_bucket_count"></a><a name="unsafe_max_bucket_count"></a>unsafe_max_bucket_count

Возвращает максимальное число контейнеров в этом контейнере.

```cpp
size_type unsafe_max_bucket_count() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное число контейнеров в этом контейнере.

## <a name="see-also"></a>См. также статью

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)
