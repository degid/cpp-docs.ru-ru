---
title: Класс forward_list
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::forward_list
- forward_list/std::forward_list::allocator_type
- forward_list/std::forward_list::const_iterator
- forward_list/std::forward_list::const_pointer
- forward_list/std::forward_list::const_reference
- forward_list/std::forward_list::difference_type
- forward_list/std::forward_list::iterator
- forward_list/std::forward_list::pointer
- forward_list/std::forward_list::reference
- forward_list/std::forward_list::size_type
- forward_list/std::forward_list::value_type
- forward_list/std::forward_list::assign
- forward_list/std::forward_list::before_begin
- forward_list/std::forward_list::begin
- forward_list/std::forward_list::cbefore_begin
- forward_list/std::forward_list::cbegin
- forward_list/std::forward_list::cend
- forward_list/std::forward_list::clear
- forward_list/std::forward_list::emplace_after
- forward_list/std::forward_list::emplace_front
- forward_list/std::forward_list::empty
- forward_list/std::forward_list::end
- forward_list/std::forward_list::erase_after
- forward_list/std::forward_list::front
- forward_list/std::forward_list::get_allocator
- forward_list/std::forward_list::insert_after
- forward_list/std::forward_list::max_size
- forward_list/std::forward_list::merge
- forward_list/std::forward_list::pop_front
- forward_list/std::forward_list::push_front
- forward_list/std::forward_list::remove
- forward_list/std::forward_list::remove_if
- forward_list/std::forward_list::resize
- forward_list/std::forward_list::reverse
- forward_list/std::forward_list::sort
- forward_list/std::forward_list::splice_after
- forward_list/std::forward_list::swap
- forward_list/std::forward_list::unique
helpviewer_keywords:
- std::forward_list
- std::forward_list::allocator_type
- std::forward_list::const_iterator
- std::forward_list::const_pointer
- std::forward_list::const_reference
- std::forward_list::difference_type
- std::forward_list::iterator
- std::forward_list::pointer
- std::forward_list::reference
- std::forward_list::size_type
- std::forward_list::value_type
- std::forward_list::assign
- std::forward_list::before_begin
- std::forward_list::begin
- std::forward_list::cbefore_begin
- std::forward_list::cbegin
- std::forward_list::cend
- std::forward_list::clear
- std::forward_list::emplace_after
- std::forward_list::emplace_front
- std::forward_list::empty
- std::forward_list::end
- std::forward_list::erase_after
- std::forward_list::front
- std::forward_list::get_allocator
- std::forward_list::insert_after
- std::forward_list::max_size
- std::forward_list::merge
- std::forward_list::pop_front
- std::forward_list::push_front
- std::forward_list::remove
- std::forward_list::remove_if
- std::forward_list::resize
- std::forward_list::reverse
- std::forward_list::sort
- std::forward_list::splice_after
- std::forward_list::swap
- std::forward_list::unique
ms.openlocfilehash: 16471f0986d58e38fed436b2921ce3f8a3e89325
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835783"
---
# <a name="forward_list-class"></a>Класс forward_list

Описывает объект, управляющий последовательностью элементов переменной длины. Последовательность хранится в виде однонаправленного связного списка узлов, каждый из которых содержит член типа `Type`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type,
    class Allocator = allocator<Type>>
class forward_list
```

### <a name="parameters"></a>Параметры

Введите * \
Тип данных элементов, сохраняемых в forward_list.

*Allocator*\
Сохраненный объект распределителя, содержащий сведения о распределении и отмене распределения памяти для списка forward_list. Это необязательный параметр. Значение по умолчанию — распределитель<`Type`>.

## <a name="remarks"></a>Примечания

`forward_list`Объект выделяет и освобождает хранилище для последовательности, управление которой осуществляется с помощью сохраненного объекта *распределителя* классов, основанного на [классе распределителя](../standard-library/allocator-class.md) (обычно известном как `std::allocator)` . Дополнительные сведения см. в статье [Распределители](../standard-library/allocators.md). Объект распределителя должен иметь тот же внешний интерфейс, что и объект типа `allocator` .

> [!NOTE]
> Сохраненный объект распределителя не копируется, когда назначается объект контейнера.

Итераторы, указатели и ссылки могут стать недопустимыми, если элементы их управляемой последовательности удаляются c помощью `forward_list`. Операции вставки и срезов, выполняемые над управляемой последовательностью с помощью `forward_list`, не делают итераторы недействительными.

Дополнения к управляемой последовательности могут возникнуть при вызове метода [forward_list::insert_after](#insert_after), который является единственной функцией-членом, вызывающей конструктор `Type(const  T&)`. `forward_list` также может вызывать конструкторы перемещения. Если такое выражение создает исключение, объект-контейнер не вставляет новые элементы и повторно создает исключение. Таким словами, объект типа остается `forward_list` в известном состоянии при возникновении таких исключений.

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[forward_list](#forward_list)|Создает объект типа `forward_list`.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[allocator_type](#allocator_type)|Тип, представляющий класс распределителя для объекта прямого списка.|
|[const_iterator](#const_iterator)|Тип, предоставляющий константный итератор для прямого списка.|
|[const_pointer](#const_pointer)|Тип, предоставляющий указатель на **`const`** элемент в прямом списке.|
|[const_reference](#const_reference)|Тип, предоставляющий константную ссылку на элемент в прямом списке.|
|[difference_type](#difference_type)|Тип целого числа со знаком, который можно использовать для представления количества элементов в прямом списке в диапазоне между элементами, на которые указывают итераторы.|
|[iterator](#iterator)|Тип, предоставляющий итератор для прямого списка.|
|[pointer](#pointer)|Тип, предоставляющий указатель на элемент в прямом списке.|
|[reference](#reference)|Тип, предоставляющий ссылку на элемент в прямом списке.|
|[size_type](#size_type)|Тип, представляющий беззнаковое расстояние между двумя элементами.|
|[value_type](#value_type)|Тип, представляющий тип элемента, хранящегося в прямом списке.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[assign](#assign)|Удаляет элементы из прямого списка и копирует новый набор элементов в целевой прямой список.|
|[before_begin](#before_begin)|Возвращает итератор, указывающий на позицию перед первым элементом в прямом списке.|
|[begin](#begin)|Возвращает итератор, указывающий на первый элемент в прямом списке.|
|[cbefore_begin](#cbefore_begin)|Возвращает константный итератор, указывающий на позицию перед первым элементом в прямом списке.|
|[cbegin](#cbegin)|Возвращает константный итератор, обращающийся к первому элементу в прямом списке.|
|[cend](#cend)|Возвращает константный итератор, адресующий расположение после последнего элемента в прямом списке.|
|[clear](#clear)|Удаляет все элементы прямого списка.|
|[emplace_after](#emplace_after)|Создает с перемещением новый элемент после указанной позиции.|
|[emplace_front](#emplace_front)|Добавляет элемент, созданный на месте, в начало списка.|
|[empty](#empty)|Проверяет, пуст ли прямой список.|
|[end](#end)|Возвращает итератор, адресующий расположение после последнего элемента в прямом списке.|
|[erase_after](#erase_after)|Удаляет элементы из прямого списка после указанной позиции.|
|[front](#front)|Возвращает ссылку на первый элемент в прямом списке.|
|[get_allocator](#get_allocator)|Возвращает копию объекта объекта распределителя, использованного для создания прямого списка.|
|[insert_after](#insert_after)|Добавляет элементы в прямой список после указанной позиции.|
|[max_size](#max_size)|Возвращает максимальную длину прямого списка.|
|[AutoMerge](#merge)|Удаляет элементы из списка аргументов, вставляет их в целевой прямой список и сортирует новый объединенный набор элементов по возрастанию или в ином указанном порядке.|
|[pop_front](#pop_front)|Удаляет элемент в начале прямого списка.|
|[push_front](#push_front)|Добавляет элемент в начало прямого списка.|
|[remove](#remove)|Удаляет из прямого списка элементы, совпадающие с заданным значением.|
|[remove_if](#remove_if)|Удаляет из прямого списка элементы, для которых выполняется заданный предикат.|
|[resize](#resize)|Указывает новый размер прямого списка.|
|[reverse](#reverse)|Изменяет порядок следования элементов в прямом списке на обратный.|
|[sort](#sort)|Упорядочивает элементы по возрастанию или по порядку, указанному предикатом.|
|[splice_after](#splice_after)|Восстанавливает ссылки между узлами.|
|[swap](#swap)|Меняет местами элементы двух прямых списков.|
|[unique](#unique)|Удаляет смежные элементы, которые прошли заданный тест.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator=](#op_eq)|Заменяет элементы прямого списка копией другого прямого списка.|

## <a name="allocator_type"></a><a name="allocator_type"></a> allocator_type

Тип, представляющий класс распределителя для объекта прямого списка.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Примечания

`allocator_type` — синоним параметра-шаблона Allocator.

## <a name="assign"></a><a name="assign"></a> назначать

Удаляет элементы из прямого списка и копирует новый набор элементов в целевой прямой список.

```cpp
void assign(
    size_type Count,
    const Type& Val);

void assign(
    initializer_list<Type> IList);

template <class InputIterator>
void assign(InputIterator First, InputIterator Last);
```

### <a name="parameters"></a>Параметры

*first*\
Начало диапазона замены.

*last*\
Конец диапазона замены.

*count*\
Число элементов для присвоения.

*val*\
Значение, присваиваемое каждому элементу.

*Type*\
Тип значения.

*Интерфейс*\
Копируемый initializer_list.

### <a name="remarks"></a>Примечания

Если forward_list имеет целочисленный тип, первая функция-член ведет себя так же, как `assign((size_type)First, (Type)Last)`. В противном случае первая функция – член заменяет последовательность, управляемую **`*this`** с помощью последовательности [ `First, Last)` , которая не должна перекрывать начальную управляемую последовательность.

Вторая функция-член заменяет последовательность, управляемую, на **`*this`** повторение `Count` элементов value `Val` .

Третья функция-член копирует элементы initializer_list в forward_list.

## <a name="before_begin"></a><a name="before_begin"></a> before_begin

Возвращает итератор, указывающий на позицию перед первым элементом в прямом списке.

```cpp
const_iterator before_begin() const;
iterator before_begin();
```

### <a name="return-value"></a>Возвращаемое значение

Прямой итератор, указывающий непосредственно перед первым элементом последовательности (или только перед концом пустой последовательности).

### <a name="remarks"></a>Примечания

## <a name="begin"></a><a name="begin"></a> begin

Возвращает итератор, указывающий на первый элемент в прямом списке.

```cpp
const_iterator begin() const;
iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Прямой итератор, указывающий на первый элемент последовательности (или на место сразу за концом пустой последовательности).

### <a name="remarks"></a>Примечания

## <a name="cbefore_begin"></a><a name="cbefore_begin"></a> cbefore_begin

Возвращает константный итератор, указывающий на позицию перед первым элементом в прямом списке.

```cpp
const_iterator cbefore_begin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Прямой итератор, указывающий непосредственно перед первым элементом последовательности (или только перед концом пустой последовательности).

### <a name="remarks"></a>Примечания

## <a name="cbegin"></a><a name="cbegin"></a> cbegin

Возвращает **`const`** итератор, который обращается к первому элементу в диапазоне.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`const`** Итератор прямого доступа, указывающий на первый элемент диапазона, или расположение непосредственно за концом пустого диапазона (для пустого диапазона `cbegin() == cend()` ).

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

Итератор прямого доступа, который указывает на позицию непосредственно за концом диапазона.

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

Удаляет все элементы прямого списка.

```cpp
void clear();
```

### <a name="remarks"></a>Примечания

Функция-член вызывает `erase_after(before_begin(), end()).`

## <a name="const_iterator"></a><a name="const_iterator"></a> const_iterator

Тип, предоставляющий константный итератор для прямого списка.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Примечания

`const_iterator` описывает объект, который можно использовать в качестве постоянного прямого итератора для управляемой последовательности. Он описан здесь как синоним для типа, определяемого реализацией.

## <a name="const_pointer"></a><a name="const_pointer"></a> const_pointer

Тип, предоставляющий указатель на **`const`** элемент в прямом списке.

```cpp
typedef typename Allocator::const_pointer
    const_pointer;
```

### <a name="remarks"></a>Примечания

## <a name="const_reference"></a><a name="const_reference"></a> const_reference

Тип, предоставляющий константную ссылку на элемент в прямом списке.

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Примечания

## <a name="difference_type"></a><a name="difference_type"></a> difference_type

Тип целого числа со знаком, который можно использовать для представления количества элементов в прямом списке в диапазоне между элементами, на которые указывают итераторы.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Примечания

`difference_type` описывает объект, который может представлять разницу между адресами любых двух элементов в управляемой последовательности.

## <a name="emplace_after"></a><a name="emplace_after"></a> emplace_after

Создает с перемещением новый элемент после указанной позиции.

```cpp
template <class T>
iterator emplace_after(const_iterator Where, Type&& val);
```

### <a name="parameters"></a>Параметры

*Where*\
Позиция в конечном прямом списке, где создается новый элемент.

*val*\
Аргумент конструктора.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на новый вставленный элемент.

### <a name="remarks"></a>Примечания

Эта функция члена вставляет элемент с аргументами конструктора *Val* сразу после элемента, на который указывает, *где* в управляемой последовательности. Его поведение в противном случае такое же, как [forward_list::insert_after](#insert_after).

## <a name="emplace_front"></a><a name="emplace_front"></a> emplace_front

Добавляет элемент, созданный на месте, в начало списка.

```cpp
template <class Type>
    void emplace_front(Type&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Элемент, добавляемый в начало прямого списка.

### <a name="remarks"></a>Примечания

Эта функция-член вставляет элемент с помощью аргументов конструктора `_ val` в конце управляемой последовательности.

При создании исключения контейнер не изменяется, а исключение создается снова.

## <a name="empty"></a><a name="empty"></a> empty

Проверяет, пуст ли прямой список.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если прямой список пуст; в противном случае — **`false`** .

## <a name="end"></a><a name="end"></a> end

Возвращает итератор, адресующий расположение после последнего элемента в прямом списке.

```cpp
const_iterator end() const;
iterator end();
```

### <a name="return-value"></a>Возвращаемое значение

Прямой итератор, который указывает на позицию непосредственно за концом последовательности.

## <a name="erase_after"></a><a name="erase_after"></a> erase_after

Удаляет элементы из прямого списка после указанной позиции.

```cpp
iterator erase_after(const_iterator Where);
iterator erase_after(const_iterator first, const_iterator last);
```

### <a name="parameters"></a>Параметры

*Where*\
Позиция в конечном прямом списке, где элемент удален.

*first*\
Начало диапазона для удаления.

*last*\
Конец диапазона для удаления.

### <a name="return-value"></a>Возвращаемое значение

Итератор, который обозначает первый элемент, находящийся за всеми удаленными элементами, или [forward_list::end](#end), если такой элемент не существует.

### <a name="remarks"></a>Примечания

Первая функция члена удаляет элемент управляемой последовательности сразу после *WHERE*.

Вторая функция-член удаляет элементы управляемой последовательности в диапазоне `( first,  last)` (конечные точки не включаются).

Удаление элементов `N` приводит к вызовам деструктора `N`. Происходит [перераспределение](../standard-library/forward-list-class.md), поэтому итераторы и ссылки становятся недействительными только для удаленных элементов.

Функции-члены не создают исключений.

## <a name="forward_list"></a><a name="forward_list"></a> forward_list

Создает объект типа `forward_list`.

```cpp
forward_list();
explicit forward_list(const Allocator& Al);
explicit forward_list(size_type Count);
forward_list(size_type Count, const Type& Val);
forward_list(size_type Count, const Type& Val, const Allocator& Al);
forward_list(const forward_list& Right);
forward_list(const forward_list& Right, const Allocator& Al);
forward_list(forward_list&& Right);
forward_list(forward_list&& Right, const Allocator& Al);
forward_list(initializer_list<Type> IList, const Alloc& Al);
template <class InputIterator>
forward_list(InputIterator First, InputIterator Last);
template <class InputIterator>
forward_list(InputIterator First, InputIterator Last, const Allocator& Al);
```

### <a name="parameters"></a>Параметры

*Al*\
Класс распределителя для использования с данным объектом.

*Count*\
Количество элементов в создаваемом списке.

*val*\
Значение элементов в создаваемом списке.

*right*\
Список, для которого создаваемый список станет копией.

*First*\
Положение первого элемента в диапазоне копируемых элементов.

*last*\
Положение первого элемента после диапазона копируемых элементов.

*Интерфейс*\
Копируемый initializer_list.

### <a name="remarks"></a>Примечания

Все конструкторы сохраняют [allocator](../standard-library/allocator-class.md) и инициализируют управляемую последовательность. Объект распределителя — это аргумент *Al*, если он есть. Для конструктора копии это `right.get_allocator()`. В противном случае значение равно `Allocator()`.

Первые два конструктора определяют пустую исходную управляемую последовательность.

Третий конструктор указывает повторение *количества элементов value* `Type()` .

Четвертый и пятый конструкторы указывают повторение элементов *Count* в значении *Val*.

Шестой конструктор задает копию последовательности, управляемой по *правому краю*. Если `InputIterator` имеет целочисленный тип, следующие два конструктора определяют повторение `(size_type)First` элементов со значением `(Type)Last`. В противном случае два следующих конструктора определяют последовательность `[First, Last)`.

Девятый и десятый конструкторы совпадают с шестым, но со ссылкой [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md).

Последний конструктор определяет начальную управляемую последовательность с объектом класса `initializer_list<Type>`.

## <a name="front"></a><a name="front"></a> front

Возвращает ссылку на первый элемент в прямом списке.

```cpp
reference front();
const_reference front() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на первый элемент управляемой последовательности, который должен быть не пустым.

## <a name="get_allocator"></a><a name="get_allocator"></a> get_allocator

Возвращает копию объекта объекта распределителя, использованного для создания прямого списка.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект [allocator](../standard-library/allocator-class.md).

## <a name="insert_after"></a><a name="insert_after"></a> insert_after

Добавляет элементы в прямой список после указанной позиции.

```cpp
iterator insert_after(const_iterator Where, const Type& Val);
void insert_after(const_iterator Where, size_type Count, const Type& Val);
void insert_after(const iterator Where, initializer_list<Type> IList);
iterator insert_after(const_iterator Where, Type&& Val);
template <class InputIterator>
    void insert_after(const_iterator Where, InputIterator First, InputIterator Last);
```

### <a name="parameters"></a>Параметры

*Where*\
Положение в целевом прямом списке, куда вставляется первый элемент.

*Count*\
Число элементов для вставки.

*First*\
Начало диапазона вставки.

*last*\
Конец диапазона вставки.

*val*\
Элемент, добавляемый в прямой список.

*Интерфейс*\
initializer_list для вставки.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на новый вставленный элемент (только первая и последняя функция-член).

### <a name="remarks"></a>Примечания

Каждая из функций-членов вставляет — сразу после элемента, на который указывает, *где* в управляемой последовательности — последовательность, указанная оставшимися операндами.

Первая функция члена вставляет элемент, имеющий значение *Val* , и возвращает итератор, который обозначает вновь вставленный элемент.

Вторая функция-член вставляет повторение элементов *Count* в значении *Val*.

Если `InputIterator` имеет целочисленный тип, первая функция-член ведет себя так же, как `insert(it, (size_type)First, (Type)Last)`. В противном случае она вставляет последовательность `[First, Last)`, которая не должна перекрывать начальную управляемую последовательность.

Четвертая функция-член вставляет последовательность, указанную объектом класса `initializer_list<Type>`.

Последняя функция-член идентична первой, но со ссылкой [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md).

Вставка элементов `N` приводит к вызовам конструктора `N`. Происходит [перераспределение](../standard-library/forward-list-class.md), но никакие итераторы и ссылки не становятся недействительными.

При создании исключения во время вставки одного или более элементов контейнер не изменяется, а исключение создается снова.

## <a name="iterator"></a><a name="iterator"></a> iterator

Тип, предоставляющий итератор для прямого списка.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Примечания

`iterator` описывает объект, который можно использовать в качестве прямого итератора для управляемой последовательности. Он описан здесь как синоним для типа, определяемого реализацией.

## <a name="max_size"></a><a name="max_size"></a> max_size

Возвращает максимальную длину прямого списка.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина самой длинной последовательности, которой может управлять объект.

### <a name="remarks"></a>Примечания

## <a name="merge"></a><a name="merge"></a> AutoMerge

Объединяет две отсортированные последовательности в одну отсортированную последовательность в линейном времени. Удаляет элементы из списка аргументов и вставляет их в этот `forward_list`. Два списка должны быть отсортированы одним и тем же объектом функции сравнения перед вызовом в `merge`. Объединенный список будут отсортирован этим объектом функции сравнения.

```cpp
void merge(forward_list& right);
template <class Predicate>
    void merge(forward_list& right, Predicate comp);
```

### <a name="parameters"></a>Параметры

*right*\
Прямой список, из которого следует выполнять слияние.

*comp*\
Объект функции сравнения, используемый для сортировки элементов.

### <a name="remarks"></a>Примечания

`forward_list::merge` Удаляет элементы из и `forward_list` `right` вставляет их в `forward_list` . Обе последовательности должны быть упорядочены по одному и тому же предикату, описанному ниже. Объединенная последовательность также упорядочивается этим объектом функции сравнения.

Для итераторов `Pi` и `Pj`, обозначающих элементы в позициях `i` и `j`, первая функция-член упорядочивает `!(*Pj < *Pi)` каждый раз, когда `i < j`. (Элементы сортируются по `ascending` порядку.) Вторая функция члена накладывает порядок в `! comp(*Pj, *Pi)` каждом случае `i < j` .

Никакие пары элементов в исходной управляемой последовательности не переставляются в результирующей управляемой последовательности. Если пара элементов в результирующей управляемой последовательности равна ( `!(*Pi < *Pj) && !(*Pj < *Pi)`), элемент из исходного управляемой последовательности появляется перед элементом из последовательности, управляемой `right`.

Исключение возникает только в том случае, если `comp` создает исключение. В этом случае управляемая последовательность остается в неопределенном порядке, и исключение создается снова.

## <a name="operator"></a><a name="op_eq"></a> operator=

Заменяет элементы прямого списка копией другого прямого списка.

```cpp
forward_list& operator=(const forward_list& right);
forward_list& operator=(initializer_list<Type> IList);
forward_list& operator=(forward_list&& right);
```

### <a name="parameters"></a>Параметры

*right*\
Прямой список, копируемый в прямой список.

*Интерфейс*\
Список инициализаторов, заключенных в скобки, который ведет себя так же, как последовательность элементов типа `Type`.

### <a name="remarks"></a>Примечания

Первый оператор-член заменяет управляемую последовательность копией последовательности, управляемой *вправо*.

Второй оператор член заменяет управляемую последовательность из объекта класса `initializer_list<Type>`.

Третий оператор член идентичен первому, но со ссылкой [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="pointer"></a><a name="pointer"></a> pointer

Тип, предоставляющий указатель на элемент в прямом списке.

```cpp
typedef typename Allocator::pointer pointer;
```

## <a name="pop_front"></a><a name="pop_front"></a> pop_front

Удаляет элемент в начале прямого списка.

```cpp
void pop_front();
```

### <a name="remarks"></a>Примечания

Первый элемент прямого списка не должен быть пустым.

Функция-член никогда не создает исключений.

## <a name="push_front"></a><a name="push_front"></a> push_front

Добавляет элемент в начало прямого списка.

```cpp
void push_front(const Type& val);
void push_front(Type&& val);
```

### <a name="parameters"></a>Параметры

*val*\
Элемент, добавляемый в начало прямого списка.

### <a name="remarks"></a>Примечания

При создании исключения контейнер не изменяется, а исключение создается снова.

## <a name="reference"></a><a name="reference"></a> IsReference

Тип, предоставляющий ссылку на элемент в прямом списке.

```cpp
typedef typename Allocator::reference reference;
```

## <a name="remove"></a><a name="remove"></a> отменит

Удаляет из прямого списка элементы, совпадающие с заданным значением.

```cpp
void remove(const Type& val);
```

### <a name="parameters"></a>Параметры

*val*\
Значение, которое должен иметь элемент для удаления этого элемента из списка.

### <a name="remarks"></a>Примечания

Функция-член удаляет из управляемой последовательности все элементы, обозначенные итератором `P`, для которого `*P ==  val`.

Функция-член никогда не создает исключений.

## <a name="remove_if"></a><a name="remove_if"></a> remove_if

Удаляет из прямого списка элементы, для которых выполняется заданный предикат.

```cpp
template <class Predicate>
    void remove_if(Predicate pred);
```

### <a name="parameters"></a>Параметры

*pred*\
Унарный предикат, который в случае совпадения с элементом приводит к удалению этого элемента из списка.

### <a name="remarks"></a>Примечания

Функция-член удаляет из управляемой последовательности все элементы, обозначенные итератором `P`, для которого `pred(*P)` — true.

Исключение возникает только в том случае, если " *пред* " создает исключение. В этом случае управляемая последовательность остается в неопределенном состоянии, и исключение создается снова.

## <a name="resize"></a><a name="resize"></a> resize

Указывает новый размер прямого списка.

```cpp
void resize(size_type _Newsize);
void resize(size_type _Newsize, const Type& val);
```

### <a name="parameters"></a>Параметры

*_Newsize*\
Число элементов в прямом списке с измененным размером.

*val*\
Значение, используемое для заполнения.

### <a name="remarks"></a>Примечания

Функция-член гарантирует, что число элементов в списке исходя этого будет *_Newsize*. Если необходимо, чтобы управляемая последовательность была длиннее, первая функция члена добавляет элементы со значением `Type()` , а вторая функция – добавляет элементы со значением *Val*. Чтобы сделать управляемую последовательность более короткой, обе функции-члены вызывают `erase_after(begin() + _Newsize - 1, end())`.

## <a name="reverse"></a><a name="reverse"></a> reverse

Изменяет порядок следования элементов в прямом списке на обратный.

```cpp
void reverse();
```

## <a name="size_type"></a><a name="size_type"></a> size_type

Тип, представляющий беззнаковое расстояние между двумя элементами.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="remarks"></a>Примечания

Целочисленный тип без знака описывает объект, который может представлять длину любой управляемой последовательности.

## <a name="sort"></a><a name="sort"></a> sort

Упорядочивает элементы по возрастанию или по порядку, указанному предикатом.

```cpp
void sort();
template <class Predicate>
void sort(Predicate pred);
```

### <a name="parameters"></a>Параметры

*pred*\
Предикат упорядочения.

### <a name="remarks"></a>Примечания

Обе функции-члена упорядочивают элементы в управляемой последовательности по предикату, описанному ниже.

Для итераторов `Pi` и `Pj`, обозначающих элементы в позициях `i` и `j`, первая функция-член упорядочивает `!(*Pj < *Pi)` каждый раз, когда `i < j`. (Элементы сортируются по `ascending` порядку.) Функция шаблона элемента накладывает порядок в `! pred(*Pj, *Pi)` каждом случае `i < j` . Никакие упорядоченные пары элементов в исходной управляемой последовательности не переставляются в результирующей управляемой последовательности. (Порядок сортировки стабилен.)

Исключение возникает только в том случае, если " *пред* " создает исключение. В этом случае управляемая последовательность остается в неопределенном порядке, и исключение создается снова.

## <a name="splice_after"></a><a name="splice_after"></a> splice_after

Удаляет элементы из исходного объекта forward_list и вставляет их в целевой объект forward_list.

```cpp
// insert the entire source forward_list
void splice_after(const_iterator Where, forward_list& Source);
void splice_after(const_iterator Where, forward_list&& Source);

// insert one element of the source forward_list
void splice_after(const_iterator Where, forward_list& Source, const_iterator Iter);
void splice_after(const_iterator Where, forward_list&& Source, const_iterator Iter);

// insert a range of elements from the source forward_list
void splice_after(
    const_iterator Where,
    forward_list& Source,
    const_iterator First,
    const_iterator Last);

void splice_after(
    const_iterator Where,
    forward_list&& Source,
    const_iterator First,
    const_iterator Last);
```

### <a name="parameters"></a>Параметры

*Where*\
Позиция в целевом объекте forward_list, после которого будут вставлены элементы.

*Source*\
Исходный объект forward_list, который необходимо вставить в целевой forward_list.

*Iter*\
Элемент, который будет вставлен из исходного объекта forward_list.

*First*\
Первый элемент в диапазоне, который будет вставлен из исходного объекта forward_list.

*last*\
Первая позиция за пределами диапазона, в которой будут вставлены элементы из исходного объекта forward_list.

### <a name="remarks"></a>Примечания

Первая пара функций элементов вставляет последовательность, управляемую *источником* , сразу после элемента в управляемой последовательности, *на которую указывает.* Он также удаляет все элементы из *источника*. ( `&Source` не должно быть равно **`this`** .)

Вторая пара функций элементов удаляет элемент сразу после *iter* в последовательности, управляемой *источником* , и вставляет его сразу после элемента в управляемой последовательности, на которую указывает, *где*. (Если `Where == Iter || Where == ++Iter`, изменения не происходят.)

Третья пара функций-членов (присоединение по диапазону) вставляет поддиапазон, обозначенный `(First, Last)` из последовательности, управляемой *источником* , непосредственно после элемента в управляемой последовательности, на которую *Where*указывает. Он также удаляет исходный поддиапазон из последовательности, управляемой *источником*. (Если `&Source == this` значение, диапазон `(First, Last)` не должен включать элемент, на который указывает, *где*.)

Если срез с диапазоном вставляет `N` элементов и `&Source != this`, объект класса [iterator](#iterator) увеличивается `N` раз.

Никакие итераторы, указатели или ссылки, которые обозначают соединенные элементы, не становятся недействительными.

### <a name="example"></a>Пример

```cpp
// forward_list_splice_after.cpp
// compile with: /EHsc /W4
#include <forward_list>
#include <iostream>

using namespace std;

template <typename S> void print(const S& s) {
    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{
    forward_list<int> c1{ 10, 11 };
    forward_list<int> c2{ 20, 21, 22 };
    forward_list<int> c3{ 30, 31 };
    forward_list<int> c4{ 40, 41, 42, 43 };

    forward_list<int>::iterator where_iter;
    forward_list<int>::iterator first_iter;
    forward_list<int>::iterator last_iter;

    cout << "Beginning state of lists:" << endl;
    cout << "c1 = ";
    print(c1);
    cout << "c2 = ";
    print(c2);
    cout << "c3 = ";
    print(c3);
    cout << "c4 = ";
    print(c4);

    where_iter = c2.begin();
    ++where_iter; // start at second element
    c2.splice_after(where_iter, c1);
    cout << "After splicing c1 into c2:" << endl;
    cout << "c1 = ";
    print(c1);
    cout << "c2 = ";
    print(c2);

    first_iter = c3.begin();
    c2.splice_after(where_iter, c3, first_iter);
    cout << "After splicing the first element of c3 into c2:" << endl;
    cout << "c3 = ";
    print(c3);
    cout << "c2 = ";
    print(c2);

    first_iter = c4.begin();
    last_iter = c4.end();
    // set up to get the middle elements
    ++first_iter;
    c2.splice_after(where_iter, c4, first_iter, last_iter);
    cout << "After splicing a range of c4 into c2:" << endl;
    cout << "c4 = ";
    print(c4);
    cout << "c2 = ";
    print(c2);
}
```

```Output
Beginning state of lists:c1 = (10) (11)c2 = (20) (21) (22)c3 = (30) (31)c4 = (40) (41) (42) (43)After splicing c1 into c2:c1 =c2 = (20) (21) (10) (11) (22)After splicing the first element of c3 into c2:c3 = (30)c2 = (20) (21) (31) (10) (11) (22)After splicing a range of c4 into c2:c4 = (40) (41)c2 = (20) (21) (42) (43) (31) (10) (11) (22)
```

## <a name="swap"></a><a name="swap"></a> swap

Меняет местами элементы двух прямых списков.

```cpp
void swap(forward_list& right);
```

### <a name="parameters"></a>Параметры

*right*\
Прямой список, предоставляющий элементы для обмена.

### <a name="remarks"></a>Примечания

Функция – член меняет местами управляемые последовательности между **`*this`** и *вправо*. Если `get_allocator() ==  right.get_allocator()`, она делает это в константном времени, не создает исключения и не делает недействительными ссылки, указатели или итераторы, которые указывают элементы в двух управляемых последовательностях. В противном случае она выполняет ряд назначений элементов и вызовов конструктора, пропорционально количеству элементов в двух управляемых последовательностях.

## <a name="unique"></a><a name="unique"></a> unique

Удаляет все, кроме первого элемента из каждой последовательной группы равных элементов.

```cpp
void unique();
template <class BinaryPredicate>
void unique(BinaryPredicate comp);
```

### <a name="parameters"></a>Параметры

*comp*\
Двоичный предикат, используемый для сравнения последовательных элементов.

### <a name="remarks"></a>Примечания

Сохраняет первый из каждого уникального элемента и удаляет остальные. Элементы должны быть отсортированы, чтобы элементы с одинаковым значением находились в списке рядом друг с другом.

Первая функция-член удаляет из управляемой последовательности каждый элемент, равный предшествующему элементу. Для итераторов `Pi` и `Pj`, указывающих элементы в позициях `i` и `j`, вторая функция-член удаляет каждый элемент, для которого `i + 1 == j &&  comp(*Pi, *Pj)`.

Для управляемой последовательности с длиной `N` (> 0) предикат `comp(*Pi, *Pj)` вычисляется `N - 1` раз.

Исключение возникает только в том случае, если `comp` создает исключение. В этом случае управляемая последовательность остается в неопределенном состоянии, и исключение создается снова.

## <a name="value_type"></a><a name="value_type"></a> value_type

Тип, представляющий тип элемента, хранящегося в прямом списке.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Type`.
