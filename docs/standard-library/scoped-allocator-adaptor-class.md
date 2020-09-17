---
title: Класс scoped_allocator_adaptor
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::scoped_allocator_adaptor
- scoped_allocator/std::scoped_allocator_adaptor::rebind Struct
- scoped_allocator/std::scoped_allocator_adaptor::allocate
- scoped_allocator/std::scoped_allocator_adaptor::construct
- scoped_allocator/std::scoped_allocator_adaptor::deallocate
- scoped_allocator/std::scoped_allocator_adaptor::destroy
- scoped_allocator/std::scoped_allocator_adaptor::inner_allocator
- scoped_allocator/std::scoped_allocator_adaptor::max_size
- scoped_allocator/std::scoped_allocator_adaptor::outer_allocator
- scoped_allocator/std::scoped_allocator_adaptor::select_on_container_copy_construction
helpviewer_keywords:
- std::scoped_allocator_adaptor
- std::scoped_allocator_adaptor::allocate
- std::scoped_allocator_adaptor::construct
- std::scoped_allocator_adaptor::deallocate
- std::scoped_allocator_adaptor::destroy
- std::scoped_allocator_adaptor::inner_allocator
- std::scoped_allocator_adaptor::max_size
- std::scoped_allocator_adaptor::outer_allocator
- std::scoped_allocator_adaptor::select_on_container_copy_construction
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
ms.openlocfilehash: b08cf1858cb0f9bf4dc6201edc2502d48754ff77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373402"
---
# <a name="scoped_allocator_adaptor-class"></a>Класс scoped_allocator_adaptor

Представляет вложенные распределители.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Outer, class... Inner>
class scoped_allocator_adaptor;
```

## <a name="remarks"></a>Примечания

Шаблон класса инкапсулирует гнездо одного или нескольких разлесть. Каждый из этих классов имеет внешний распределитель типа `outer_allocator_type`, синоним `Outer`, который представляет собой общедоступную базу объекта `scoped_allocator_adaptor`. `Outer` используется для выделения памяти, которая будет использоваться контейнером. Можно получить ссылку на этот базовый объект распределителя, вызвав метод `outer_allocator`.

Остальная часть вложения имеет тип `inner_allocator_type`. Внутренний распределитель используется для выделения памяти для элементов в контейнере. Для получения ссылки на сохраненный объект этого типа вызовите `inner_allocator`. Если `Inner...` не пустой, `inner_allocator_type` имеет тип `scoped_allocator_adaptor<Inner...>`, а `inner_allocator` назначает объект-член. В противном случае `inner_allocator_type` имеет тип `scoped_allocator_adaptor<Outer>`, а `inner_allocator` назначает целый объект.

Вложение ведет себя так, как будто имеет произвольную глубину, реплицируя свой самый внутренний инкапсулированный распределитель так, как нужно.

Несколько концепций, которые не являются частью видимого интерфейса помощи в описании поведения этого шаблона класса. *Внешний распределитель* преобразует все вызовы, адресованные методам construct и destroy. Он эффективно определяется рекурсивной функцией `OUTERMOST(X)`, где `OUTERMOST(X)` — один из следующих объектов.

- Если `X.outer_allocator()` имеет правильный формат, `OUTERMOST(X)` равен `OUTERMOST(X.outer_allocator())`.

- В противном случае `OUTERMOST(X)` является `X`.

В целях демонстрации определено три типа:

|Тип|Описание|
|----------|-----------------|
|`Outermost`|Тип параметра `OUTERMOST(*this)`.|
|`Outermost_traits`|`allocator_traits<Outermost>`|
|`Outer_traits`|`allocator_traits<Outer>`|

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|----------|-----------------|
|[scoped_allocator_adaptor](#scoped_allocator_adaptor)|Формирует объект `scoped_allocator_adaptor`.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|----------|-----------------|
|`const_pointer`|Этот тип является синонимом `const_pointer`, связанного с распределителем `Outer`.|
|`const_void_pointer`|Этот тип является синонимом `const_void_pointer`, связанного с распределителем `Outer`.|
|`difference_type`|Этот тип является синонимом `difference_type`, связанного с распределителем `Outer`.|
|`inner_allocator_type`|Этот тип является синонимом типа вложенного адаптера `scoped_allocator_adaptor<Inner...>`.|
|`outer_allocator_type`|Этот тип является синонимом типа базового распределителя `Outer`.|
|`pointer`|Этот тип является синонимом `pointer`, связанного с распределителем `Outer`.|
|`propagate_on_container_copy_assignment`|Тип содержит значение true только в том случае, если `Outer_traits::propagate_on_container_copy_assignment` или `inner_allocator_type::propagate_on_container_copy_assignment` имеет значение true.|
|`propagate_on_container_move_assignment`|Тип содержит значение true только в том случае, если `Outer_traits::propagate_on_container_move_assignment` или `inner_allocator_type::propagate_on_container_move_assignment` имеет значение true.|
|`propagate_on_container_swap`|Тип содержит значение true только в том случае, если `Outer_traits::propagate_on_container_swap` или `inner_allocator_type::propagate_on_container_swap` имеет значение true.|
|`size_type`|Этот тип является синонимом `size_type`, связанного с распределителем `Outer`.|
|`value_type`|Этот тип является синонимом `value_type`, связанного с распределителем `Outer`.|
|`void_pointer`|Этот тип является синонимом `void_pointer`, связанного с распределителем `Outer`.|

### <a name="structs"></a>Структуры

|Имя|Описание|
|----------|-----------------|
|[scoped_allocator_adaptor::rebind Struct](#rebind_struct)|Определяет тип `Outer::rebind\<Other>::other` как синоним для `scoped_allocator_adaptor\<Other, Inner...>`.|

### <a name="methods"></a>Методы

|Имя|Описание|
|----------|-----------------|
|[Выделить](#allocate)|Выделяет память, используя распределитель `Outer`.|
|[Конструкции](#construct)|Создает объект.|
|[Освобождения](#deallocate)|Освобождает объекты, используя внешний распределитель.|
|[Уничтожить](#destroy)|Удаляет указанный объект.|
|[inner_allocator](#inner_allocator)|Извлекает ссылку на сохраненный объект типа `inner_allocator_type`.|
|[max_size](#max_size)|Определяет максимальное число объектов, которые могут быть распределены внешним распределителем.|
|[outer_allocator](#outer_allocator)|Извлекает ссылку на сохраненный объект типа `outer_allocator_type`.|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Создает новый объект `scoped_allocator_adaptor` с каждым сохраненным объектом распределителя, который инициализируется вызовом метода `select_on_container_copy_construction` для каждого соответствующего распределителя.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператора](#op_as)||
|[оператора](#op_eq_eq)||
|[оператора!](#op_noeq)||

## <a name="requirements"></a>Требования

**Заголовок:** \<scoped_allocator>

**Пространство имен:** std

## <a name="scoped_allocator_adaptorallocate"></a><a name="allocate"></a>scoped_allocator_adaptor::

Выделяет память, используя распределитель `Outer`.

```cpp
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```

### <a name="parameters"></a>Параметры

*Рассчитывать*\
Количество элементов, для которых необходимо выделить достаточный объем памяти.

*Подсказка*\
Указатель, который может помочь объекту распределителя, найдя адрес объекта, который был выделен до этого запроса.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает значение `Outer_traits::allocate(outer_allocator(), count)`. Вторая функция-член возвращает значение `Outer_traits::allocate(outer_allocator(), count, hint)`.

## <a name="scoped_allocator_adaptorconstruct"></a><a name="construct"></a>scoped_allocator_adaptor::строительство

Создает объект.

```cpp
template <class Ty, class... Atypes>
void construct(Ty* ptr, Atypes&&... args);

template <class Ty1, class Ty2, class... Atypes1, class... Atypes2>
void construct(pair<Ty1, Ty2>* ptr, piecewise_construct_t,
    tuple<Atypes1&&...>
first, tuple<Atypes1&&...> second);

template <class Ty1, class Ty2>
void construct(pair<Ty1, Ty2>* ptr);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr,
    class Uy1&& first, class Uy2&& second);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr, const pair<Uy1, Uy2>& right);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr, pair<Uy1, Uy2>&& right);
```

### <a name="parameters"></a>Параметры

*Ptr*\
Указатель на место в памяти, где необходимо создать объект.

*Args*\
Список аргументов.

*first*\
Объект первого типа в паре.

*Второй*\
Объект второго типа в паре.

*right*\
Существующий объект, который необходимо переместить или копировать.

### <a name="remarks"></a>Примечания

Первый метод строит объект на *ptr,* позвонив, `Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)`где `xargs...` находится один из следующих.

- Если `uses_allocator<Ty, inner_allocator_type>` имеет значение false, то `xargs...` равно `args...`.

- Если `uses_allocator<Ty, inner_allocator_type>` имеет значение true и `is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` имеет значение true, то `xargs...` равно `allocator_arg, inner_allocator(), args...`.

- Если `uses_allocator<Ty, inner_allocator_type>` имеет значение true и `is_constructible<Ty, args..., inner_allocator()>` имеет значение true, то `xargs...` равно `args..., inner_allocator()`.

Второй метод строит парный объект на *ptr,* `Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)`вызывая , `xargs...` где `first...` изменен, как в приведенном выше списке, и `Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)`, где `xargs...` `second...` изменен, как в приведенном выше списке.

Третий метод работает так же, как `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)`.

Четвертый метод работает так же, как `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))`.

Пятый метод работает так же, как `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))`.

Шестой метод работает так же, как `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))`.

## <a name="scoped_allocator_adaptordeallocate"></a><a name="deallocate"></a>scoped_allocator_adaptor::dраспределение

Освобождает объекты, используя внешний распределитель.

```cpp
void deallocate(pointer ptr, size_type count);
```

### <a name="parameters"></a>Параметры

*Ptr*\
Указатель на начальное расположение освобождаемых объектов.

*Рассчитывать*\
Количество освобождаемых объектов.

## <a name="scoped_allocator_adaptordestroy"></a><a name="destroy"></a>scoped_allocator_adaptor::dэсстрой

Удаляет указанный объект.

```cpp
template <class Ty>
void destroy(Ty* ptr)
```

### <a name="parameters"></a>Параметры

*Ptr*\
Указатель на уничтожаемый объект.

### <a name="return-value"></a>Возвращаемое значение

`Outermost_traits::destroy(OUTERMOST(*this), ptr)`

## <a name="scoped_allocator_adaptorinner_allocator"></a><a name="inner_allocator"></a>scoped_allocator_adaptor::inner_allocator

Извлекает ссылку на сохраненный объект типа `inner_allocator_type`.

```cpp
inner_allocator_type& inner_allocator() noexcept;
const inner_allocator_type& inner_allocator() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на сохраненный объект типа `inner_allocator_type`.

## <a name="scoped_allocator_adaptormax_size"></a><a name="max_size"></a>scoped_allocator_adaptor::max_size

Определяет максимальное число объектов, которые могут быть распределены внешним распределителем.

```cpp
size_type max_size();
```

### <a name="return-value"></a>Возвращаемое значение

`Outer_traits::max_size(outer_allocator())`

## <a name="a-nameop_as--scoped_allocator_adaptoroperator"></a><a name="op_as">scoped_allocator_adaptor:оператор

```cpp
scoped_allocator_adaptor& operator=(const scoped_allocator_adaptor&) = default;
scoped_allocator_adaptor& operator=(scoped_allocator_adaptor&&) = default;
```

## <a name="a-nameop_eq_eq--scoped_allocator_adaptoroperator"></a><a name="op_eq_eq">scoped_allocator_adaptor::operator

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator==(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="a-nameop_noeq--scoped_allocator_adaptoroperator"></a><a name="op_noeq">scoped_allocator_adaptor::operator!

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator!=(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="scoped_allocator_adaptorouter_allocator"></a><a name="outer_allocator"></a>scoped_allocator_adaptor::outer_allocator

Извлекает ссылку на сохраненный объект типа `outer_allocator_type`.

```cpp
outer_allocator_type& outer_allocator() noexcept;
const outer_allocator_type& outer_allocator() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на сохраненный объект типа `outer_allocator_type`.

## <a name="scoped_allocator_adaptorrebind-struct"></a><a name="rebind_struct"></a>scoped_allocator_adaptor::rebind Struct

Определяет тип `Outer::rebind\<Other>::other` как синоним для `scoped_allocator_adaptor\<Other, Inner...>`.

struct rebind' typedef Other_traits::rebind\<Other>\<Other_alloc; typedef scoped_allocator_adaptor Other_alloc, Inner...> other;

## <a name="scoped_allocator_adaptorscoped_allocator_adaptor-constructor"></a><a name="scoped_allocator_adaptor"></a>scoped_allocator_adaptor::scoped_allocator_adaptor конструктор

Формирует объект `scoped_allocator_adaptor`. Также включает в себя деструктор.

```cpp
scoped_allocator_adaptor();

scoped_allocator_adaptor(const scoped_allocator_adaptor& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(
const scoped_allocator_adaptor<Outer2, Inner...>& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(
scoped_allocator_adaptor<Outer2, Inner...>&& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(Outer2&& al,
    const Inner&... rest) noexcept;

~scoped_allocator_adaptor();
```

### <a name="parameters"></a>Параметры

*right*\
Существующий `scoped_allocator_adaptor`.

*Аль*\
Существующий распределитель, который следует использовать как внешний распределитель.

*Остальные*\
Список распределителей, которые следует использовать как внутренние распределители.

### <a name="remarks"></a>Примечания

Первый конструктор по умолчанию создает сохраненные объекты распределителя. Каждый из следующих трех конструкторов строит свои сохраненные объекты-разлктора из соответствующих объектов в *правой.* Последний конструктор создает сохраненные объекты распределителя из соответствующих аргументов в списке.

## <a name="scoped_allocator_adaptorselect_on_container_copy_construction"></a><a name="select_on_container_copy_construction"></a>scoped_allocator_adaptor::select_on_container_copy_construction

Создает новый объект `scoped_allocator_adaptor` с каждым сохраненным объектом распределителя, который инициализируется вызовом метода `select_on_container_copy_construction` для каждого соответствующего распределителя.

```cpp
scoped_allocator_adaptor select_on_container_copy_construction();
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод фактически возвращает `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())`. Результатом является `scoped_allocator_adaptor` новый объект с каждым сохраненным объектом разлесть инициализированы, позвонив `al.select_on_container_copy_construction()` на соответствующий аллокатор *al*.

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
