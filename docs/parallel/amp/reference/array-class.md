---
title: Класс array
ms.date: 11/04/2016
f1_keywords:
- array
- AMP/array
- AMP/Concurrency::array::array
- AMP/Concurrency::array::copy_to
- AMP/Concurrency::array::data
- AMP/Concurrency::array::get_accelerator_view
- AMP/Concurrency::array::get_associated_accelerator_view
- AMP/Concurrency::array::get_cpu_access_type
- AMP/Concurrency::array::get_extent
- AMP/Concurrency::array::reinterpret_as
- AMP/Concurrency::array::section
- AMP/Concurrency::array::view_as
- AMP/Concurrency::array::rank
- AMP/Concurrency::array::accelerator_view
- AMP/Concurrency::array::associated_accelerator_view
- AMP/Concurrency::array::cpu_access_type
- AMP/Concurrency::array::extent
helpviewer_keywords:
- array class
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
ms.openlocfilehash: efea8dabb69a48e69d68a86110fdf9bc7664948b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127116"
---
# <a name="array-class"></a>Класс array

Представляет контейнер данных, используемый для перемещения данных в ускоритель.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename value_type, int _Rank>
friend class array;
```

### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип элемента данных.

*_Rank*<br/>
Ранг массива.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор массива](#ctor)|Инициализирует новый экземпляр класса `array`.|
|[Деструктор массива ~](#dtor)|Уничтожает объект `array`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[copy_to](#copy_to)|Копирует содержимое массива в другой массив.|
|[data](#data)|Возвращает указатель на необработанные данные массива.|
|[get_accelerator_view](#get_accelerator_view)|Возвращает объект [accelerator_view](accelerator-view-class.md) , представляющий расположение, в котором выделяется массив. Доступ к этому свойству можно получить только в ЦП.|
|[get_associated_accelerator_view](#get_associated_accelerator_view)|Возвращает второй [accelerator_view](accelerator-view-class.md) объект, передаваемый в качестве параметра при вызове промежуточного конструктора для создания экземпляра объекта `array`.|
|[get_cpu_access_type](#get_cpu_access_type)|Возвращает [access_type](concurrency-namespace-enums-amp.md#access_type) массива. Доступ к этому методу можно получить только в ЦП.|
|[get_extent](#get_extent)|Возвращает объект [экстента](extent-class.md) массива.|
|[reinterpret_as](#reinterpret_as)|Возвращает одномерный массив, содержащий все элементы в объекте `array`.|
|[section](#section)|Возвращает подраздел объекта `array`, который находится в указанном источнике и, при необходимости, с указанным экстентом.|
|[view_as](#view_as)|Возвращает объект [array_view](array-view-class.md) , созданный из объекта `array`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор std:: Vector&lt;value_type&gt;](#operator_vec)|Использует `copy(*this, vector)` для неявного преобразования массива в объект std::[vector](../../../standard-library/vector-class.md) .|
|[operator()](#operator_call)|Возвращает значение элемента, заданное параметрами.|
|[operator\[\]](#operator_at)|Возвращает элемент, расположенный по указанному индексу.|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `array` в этот объект.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[Константа Rank](#rank)|Хранит ранг массива.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[accelerator_view](#accelerator_view)|Возвращает объект [accelerator_view](accelerator-view-class.md) , представляющий расположение, в котором выделяется массив. Доступ к этому свойству можно получить только в ЦП.|
|[associated_accelerator_view](#associated_accelerator_view)|Возвращает второй [accelerator_view](accelerator-view-class.md) объект, передаваемый в качестве параметра при вызове промежуточного конструктора для создания экземпляра объекта `array`.|
|[cpu_access_type](#cpu_access_type)|Возвращает [access_type](concurrency-namespace-enums-amp.md#access_type) , который представляет, как ЦП может получить доступ к хранилищу массива.|
|[extent](#extent)|Возвращает экстент, определяющий форму массива.|

## <a name="remarks"></a>Примечания

Тип `array<T,N>` представляет собой сжатый и обычный (неровный) *N*-мерный массив, расположенный в определенном месте, например в ускорителе или ЦП. Тип данных элементов в массиве — `T`, который должен иметь тип, совместимый с целевым ускорителем. Хотя ранг, `N`(массива определяется статически и является частью типа, экстент массива определяется средой выполнения и выражается с помощью класса `extent<N>`.

Массив может иметь любое количество измерений, хотя некоторые функциональные возможности могут быть специализированы для `array` объектов с рангом 1, 2 и 3. Если опустить аргумент измерения, значение по умолчанию — 1.

Данные массива располагаются последовательно в памяти. Элементы, которые отличаются друг от друга в наименее значимом измерении, являются смежными в памяти.

Массивы логически считаются типами значений, поскольку при копировании массива в другой массив выполняется глубокое копирование. Два массива никогда не указывают на одни и те же данные.

Тип `array<T,N>` используется в нескольких сценариях.

- В качестве контейнера данных, который можно использовать в вычислениях в ускорителе.

- В качестве контейнера данных для хранения памяти на ЦП узла (который может использоваться для копирования в другие массивы и обратно).

- В качестве промежуточного объекта, который будет служить быстрым посредником в копиях типа "узел-устройство".

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`array`

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="dtor"></a>~ массив

Уничтожает объект `array`.

```cpp
~array() restrict(cpu);
```

## <a name="accelerator_view"></a>accelerator_view

Возвращает объект [accelerator_view](accelerator-view-class.md) , представляющий расположение, в котором выделяется массив. Доступ к этому свойству можно получить только в ЦП.

```cpp
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;
```

## <a name="ctor"></a>inArray

Инициализирует новый экземпляр [класса Array](array-class.md). Конструктор по умолчанию для `array<T,N>`отсутствует. Все конструкторы выполняются только на ЦП. Они не могут выполняться на целевом объекте Direct3D.

```cpp
explicit array(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

explicit array(
    int _E0) restrict(cpu);

explicit array(
    int _E0,
    int _E1) restrict(cpu);

explicit array(
    int _E0,
    int _E1,
    int _E2) restrict(cpu);

array(
    const Concurrency::extent<_Rank>& _Extent,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

array(
    int _E0,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

array(
    int _E0,
    int _E1,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

array(
    int _E0,
    int _E1,
    int _E2,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

array(
    const Concurrency::extent<_Rank>& _Extent,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

array(
    int _E0,
    accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

array(
    int _E0,
    int _E1,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

array(
    int _E0,
    int _E1,
    int _E2,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first,
    _InputIterator _Src_last) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    _InputIterator _Src_first,
    _InputIterator _Src_last) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    _InputIterator _Src_first) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    _InputIterator _Src_first,
    _InputIterator _Src_last) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    _InputIterator _Src_first) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2,
    _InputIterator _Src_first,
    _InputIterator _Src_last) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2,
    _InputIterator _Src_first) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    _InputIterator _Src_first,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    _InputIterator _Src_first,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av,
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2,
    _InputIterator _Src_first,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0, _InputIterator _Src_first,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1, _InputIterator _Src_first,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2, _InputIterator _Src_first,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

explicit array(
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);

array(
    const array_view<const value_type, _Rank>& _Src,
    accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

array(
    const array_view<const value_type, _Rank>& _Src,
    accelerator_view _Av,
    accelerator_view _Associated_Av) restrict(cpu);

array(const array& _Other) restrict(cpu);

array(array&& _Other) restrict(cpu);
```

### <a name="parameters"></a>Параметры

*_Associated_Av*<br/>
Accelerator_view, указывающий предпочтительное целевое расположение массива.

*_Av*<br/>
Объект [accelerator_view](accelerator-view-class.md) , указывающий расположение массива.

*_Cpu_access_type*<br/>
Требуемый [access_type](concurrency-namespace-enums-amp.md#access_type) для массива ЦП. Этот параметр имеет значение по умолчанию, `access_type_auto` при этом `access_type` ЦП загружается в среду выполнения. Фактический `access_type` ЦП для массива можно запросить с помощью метода `get_cpu_access_type`.

*_Extent*<br/>
Экстент в каждом измерении массива.

*_E0*<br/>
Наиболее важный компонент экстента этого раздела.

*_E1*<br/>
Наиболее важный компонент в области этого раздела.

*_E2*<br/>
Наименее важный компонент экстента этого раздела.

*_InputIterator*<br/>
Тип итератора ввода.

*_Src*<br/>
В объект для копирования.

*_Src_first*<br/>
Начальный итератор в исходный контейнер.

*_Src_last*<br/>
Конечный итератор в исходный контейнер.

*_Other*<br/>
Другой источник данных.

*_Rank*<br/>
Ранг раздела.

*value_type*<br/>
Тип данных копируемых элементов.

## <a name="associated_accelerator_view"></a>associated_accelerator_view

Возвращает второй [accelerator_view](accelerator-view-class.md) объект, передаваемый в качестве параметра при вызове промежуточного конструктора для создания экземпляра объекта `array`.

```cpp
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;
```

## <a name="copy_to"></a>copy_to

Копирует содержимое `array` в другой `array`.

```cpp
void copy_to(
    array<value_type, _Rank>& _Dest) const ;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Объект [array_view](array-view-class.md) , в который производится копирование.

## <a name="cpu_access_type"></a>cpu_access_type

Возвращает access_type ЦП, разрешенный для этого массива.

```cpp
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;
```

## <a name="data"></a>Data

Возвращает указатель на необработанные данные `array`.

```cpp
value_type* data() restrict(amp, cpu);

const value_type* data() const restrict(amp, cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на необработанные данные массива.

## <a name="extent"></a>экстент

Возвращает объект [экстента](extent-class.md) , определяющий форму `array`.

```cpp
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

## <a name="get_accelerator_view"></a>get_accelerator_view

Возвращает объект [accelerator_view](accelerator-view-class.md) , представляющий расположение, в которое выделяется объект `array`. Доступ к этому свойству можно получить только в ЦП.

```cpp
Concurrency::accelerator_view get_accelerator_view() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `accelerator_view`, представляющий расположение, в котором выделяется объект `array`.

## <a name="get_associated_accelerator_view"></a>get_associated_accelerator_view

Возвращает второй [accelerator_view](accelerator-view-class.md) объект, передаваемый в качестве параметра при вызове промежуточного конструктора для создания экземпляра объекта `array`.

```cpp
Concurrency::accelerator_view get_associated_accelerator_view() const ;
```

### <a name="return-value"></a>Возвращаемое значение

Второй [accelerator_view](accelerator-view-class.md) объект, переданный в промежуточный конструктор.

## <a name="get_cpu_access_type"></a>get_cpu_access_type

Возвращает access_type ЦП, допустимый для этого массива.

```cpp
access_type get_cpu_access_type() const restrict(cpu);
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="get_extent"></a>get_extent

Возвращает объект [экстента](extent-class.md) `array`.

```cpp
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Метаданные `extent` для объекта `array`.

## <a name="operator_vec"></a>Оператор std:: Vector&lt;value_type&gt;

Использует `copy(*this, vector)` для неявного преобразования массива в объект std:: Vector.

```cpp
operator std::vector<value_type>() const restrict(cpu);
```

### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип данных элементов вектора.

### <a name="return-value"></a>Возвращаемое значение

Объект типа `vector<T>`, содержащий копию данных, содержащихся в массиве.

## <a name="operator_call"></a>оператор ()

Возвращает значение элемента, заданное параметрами.

```cpp
value_type& operator() (const index<_Rank>& _Index) restrict(amp,cpu);

const value_type& operator() (const index<_Rank>& _Index) cons  t restrict(amp,cpu);

value_type& operator() (int _I0, int _I1) restrict(amp,cpu);

const value_type& operator() (int _I0, int _I1) const restrict(amp,cpu)  ;

value_type& operator() (int _I0, int _I1, int _I2) restrict(amp,cpu);

const value_type& operator() (int _I0, int _I1, int _I2) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator()(int _I) restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator()(int _I) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Расположение элемента.

*_I0*<br/>
Наиболее важный компонент происхождения этого раздела.

*_I1*<br/>
Последующий важный компонент в происхождении этого раздела.

*_I2*<br/>
Наименее важный компонент происхождения этого раздела.

*_I*<br/>
Расположение элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение элемента, заданное параметрами.

## <a name="operator_at"></a>operator []

Возвращает элемент, расположенный по указанному индексу.

```cpp
value_type& operator[](const index<_Rank>& _Index) restrict(amp,cpu);

const value_type& operator[]
    (const index<_Rank>& _Index) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator[](int _i) restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[](int _i) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс.

*_I*<br/>
Индекс.

### <a name="return-value"></a>Возвращаемое значение

Элемент, расположенный по указанному индексу.

## <a name="operator_eq"></a>Оператор =

Копирует содержимое указанного объекта `array`.

```cpp
array& operator= (const array& _Other) restrict(cpu);

array& operator= (array&& _Other) restrict(cpu);

array& operator= (
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект `array`, из которого производится копирование.

*_Src*<br/>
Объект `array`, из которого производится копирование.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот объект `array`.

## <a name="rank"></a>Рейтинг

Хранит ранг `array`.

```cpp
static const int rank = _Rank;
```

## <a name="reinterpret_as"></a>reinterpret_as

Повторно интерпретирует массив с помощью одномерного array_view, который при необходимости может иметь тип значения, отличный от типа исходного массива.

### <a name="syntax"></a>Синтаксис

```cpp
template <typename _Value_type2>
array_view<_Value_type2,1> reinterpret_as() restrict(amp,cpu);

template <typename _Value_type2>
array_view<const _Value_type2, 1> reinterpret_as() const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Value_type2*<br/>
Тип данных возвращаемых данных.

### <a name="return-value"></a>Возвращаемое значение

Array_view или const array_view объект, основанный на массиве, с типом элемента, который снова интерпретируется от T до ElementType, а ранг уменьшился с N до 1.

### <a name="remarks"></a>Примечания

Иногда удобно просматривать многомерный массив, как если бы он был линейным одномерным массивом, возможно, с типом значения, отличным от типа исходного массива. Этот метод можно использовать для достижения этого результата.
**Внимание!** Переинтерпретирование объекта массива с помощью другого типа значения является потенциально небезопасной операцией. Рекомендуется внимательно использовать эту функцию.

Пример кода:

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

## <a name="section"></a>раздела

Возвращает подраздел объекта `array`, который находится в указанном источнике и, при необходимости, с указанным экстентом.

```cpp
array_view<value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,
    const Concurrency::extent<_Rank>& _Section_extent) restrict(amp,cpu);

array_view<const value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);

array_view<value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) restrict(amp,cpu);

array_view<const value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);

array_view<value_type,_Rank> section(
    const index<_Rank>& _Idx) restrict(amp,cpu);

array_view<const value_type,_Rank> section(
    const index<_Rank>& _Idx) const restrict(amp,cpu);

array_view<value_type,1> section(
    int _I0,
    int _E0) restrict(amp,cpu);

array_view<const value_type,1> section(
    int _I0,
    int _E0) const restrict(amp,cpu);

array_view<value_type,2> section(
    int _I0,
    int _I1,
    int _E0,
    int _E1) restrict(amp,cpu);

array_view<const value_type,2> section(
    int _I0,
    int _I1,
    int _E0,
    int _E1) const restrict(amp,cpu);

array_view<value_type,3> section(
    int _I0,
    int _I1,
    int _I2,
    int _E0,
    int _E1,
    int _E2) restrict(amp,cpu);

array_view<const value_type,3> section(
    int _I0,
    int _I1,
    int _I2,
    int _E0,
    int _E1,
    int _E2) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_E0*<br/>
Наиболее важный компонент экстента этого раздела.

*_E1*<br/>
Наиболее важный компонент в области этого раздела.

*_E2*<br/>
Наименее важный компонент экстента этого раздела.

*_Ext*<br/>
Объект [экстента](extent-class.md) , указывающий экстент раздела. Источник равен 0.

*_Idx*<br/>
Объект [index](index-class.md) , указывающий расположение источника. Подразделы — это оставшаяся часть экстента.

*_I0*<br/>
Наиболее важный компонент происхождения этого раздела.

*_I1*<br/>
Последующий важный компонент в происхождении этого раздела.

*_I2*<br/>
Наименее важный компонент происхождения этого раздела.

*_Rank*<br/>
Ранг раздела.

*_Section_extent*<br/>
Объект [экстента](extent-class.md) , указывающий экстент раздела.

*_Section_origin*<br/>
Объект [index](index-class.md) , указывающий расположение источника.

*value_type*<br/>
Тип данных копируемых элементов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает подраздел объекта `array`, который находится в указанном источнике и, при необходимости, с указанным экстентом. Если указан только объект `index`, подраздел содержит все элементы в связанной сетке, имеющие индексы, превышающие индексы элементов в объекте `index`.

## <a name="view_as"></a>view_as

Переинтерпретирует этот массив как [array_view](array-view-class.md) другого ранга.

```cpp
template <int _New_rank>
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) restrict(amp,cpu);

template <int _New_rank>
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_New_rank*<br/>
Ранг объекта `extent`, переданного в качестве параметра.

*_View_extent*<br/>
Экстент, используемый для создания нового объекта [array_view](array-view-class.md) .

*value_type*<br/>
Тип данных элементов в исходном `array`ном объекте и возвращенном `array_view`ном объекте.

### <a name="return-value"></a>Возвращаемое значение

Созданный объект [array_view](array-view-class.md) .

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
