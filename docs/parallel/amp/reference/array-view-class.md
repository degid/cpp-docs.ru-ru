---
title: Класс array_view
ms.date: 11/04/2016
f1_keywords:
- array_view
- AMP/array_view
- AMP/Concurrency::array_view::array_view
- AMP/Concurrency::array_view::copy_to
- AMP/Concurrency::array_view::data
- AMP/Concurrency::array_view::discard_data
- AMP/Concurrency::array_view::get_extent
- AMP/Concurrency::array_view::get_ref
- AMP/Concurrency::array_view::get_source_accelerator_view
- AMP/Concurrency::array_view::refresh
- AMP/Concurrency::array_view::reinterpret_as
- AMP/Concurrency::array_view::section
- AMP/Concurrency::array_view::synchronize
- AMP/Concurrency::array_view::synchronize_async
- AMP/Concurrency::array_view::synchronize_to
- AMP/Concurrency::array_view::synchronize_to_async
- AMP/Concurrency::array_view::view_as
- AMP/Concurrency::array_view::rank
- AMP/Concurrency::array_view::extent
- AMP/Concurrency::array_view::source_accelerator_view
- AMP/Concurrency::array_view::value_type
helpviewer_keywords:
- array_view class
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
ms.openlocfilehash: 2aef75eedcde2a2064fe12815d9afd21fee2c293
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127141"
---
# <a name="array_view-class"></a>Класс array_view

Представляет N-мерный вид данных, хранящихся в другом контейнере.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename value_type,
    int _Rank = 1
>
class array_view : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;

template <
    typename value_type,
    int _Rank
>
class array_view<const value_type, _Rank> : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;
```

### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип данных элементов в объекте `array_view`.

*_Rank*<br/>
Ранг объекта `array_view`.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор array_view](#ctor)|Инициализирует новый экземпляр класса `array_view`. Конструктор по умолчанию для `array<T,N>`отсутствует. Все конструкторы могут выполняться только на ЦП и не могут выполняться на целевом объекте Direct3D.|
|[Деструктор ~ array_view](#ctor)|Уничтожает объект `array_view`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[copy_to](#copy_to)|Копирует содержимое объекта `array_view` в указанное место назначения путем вызова `copy(*this, dest)`.|
|[data](#data)|Возвращает указатель на необработанные данные `array_view`.|
|[discard_data](#discard_data)|Отменяет текущие данные, лежащие в этом представлении.|
|[get_extent](#get_extent)|Возвращает объект экстента объекта array_view.|
|[get_ref](#get_ref)|Возвращает ссылку на индексированный элемент.|
|[get_source_accelerator_view](#get_source_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) , где расположен источник данных `array_view`.|
|[обновляется](#refresh)|Уведомляет объект `array_view` о том, что связанная с ним память была изменена вне интерфейса `array_view`. Вызов этого метода выводит все кэшированные данные в устаревшем виде.|
|[reinterpret_as](#reinterpret_as)|Возвращает одномерный массив, содержащий все элементы в объекте `array_view`.|
|[section](#section)|Возвращает подраздел объекта `array_view`, который находится в указанном источнике и, при необходимости, с указанным экстентом.|
|[synchronize](#synchronize)|Синхронизирует любые изменения, внесенные в объект `array_view`, обратно в исходные данные.|
|[synchronize_async](#synchronize_async)|Асинхронно синхронизирует любые изменения, внесенные в объект `array_view`, обратно в исходные данные.|
|[synchronize_to](#synchronize_to)|Синхронизирует все изменения, внесенные в объект `array_view`, с указанным [accelerator_view](accelerator-view-class.md).|
|[synchronize_to_async](#synchronize_to_async)|Асинхронно синхронизирует любые изменения, внесенные в объект `array_view`, в указанный [accelerator_view](accelerator-view-class.md).|
|[view_as](#view_as)|Создает объект `array_view` с другим рангом, используя данные этого `array_view` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator()](#operator_call)|Возвращает значение элемента, заданного параметром или параметрами.|
|[operator\[\]](#operator_at)|Возвращает элемент, заданный параметрами.|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `array_view` в этот объект.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[Константа Rank](#rank)|Хранит ранг объекта `array_view`.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[extent](#extent)|Получает объект `extent`, который определяет форму объекта `array_view`.|
|[source_accelerator_view](#source_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) , где расположен источник данных `array_view`|
|[value_type](#value_type)|Тип значения `array_view` и привязанного массива.|

## <a name="remarks"></a>Примечания

Класс `array_view` представляет представление данных, содержащихся в объекте [массива](array-class.md) или подразделе объекта `array`.

Можно получить доступ к объекту `array_view`, где находятся исходные данные (локально) или в другом ускорителе или домене согласования (удаленно). При удаленном доступе к объекту представления копируются и кэшируются по мере необходимости. За исключением эффектов автоматического кэширования, `array_view` объекты имеют профиль производительности, аналогичный `array` объектам. При доступе к данным через представления возникают небольшие потери производительности.

Существует три сценария удаленного использования.

- Представление указателя системной памяти передается с помощью [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each) вызова ускорителя и доступа к нему по сочетанию клавиш.

- Представление массива, расположенного в ускорителе, передается с помощью `parallel_for_each` вызова другого ускорителя и доступа к нему.

- Доступ к массиву, расположенному на ускорителе, осуществляется через ЦП.

В любом из этих сценариев представления, на которые имеются ссылки, копируются средой выполнения в удаленное расположение и, если они были изменены вызовами объекта `array_view`, копируются обратно в локальное расположение. Среда выполнения может оптимизировать процесс копирования изменений назад, может копировать только измененные элементы или копировать неизмененные фрагменты. Перекрывающиеся `array_view` объекты в одном источнике данных не гарантируют поддержание ссылочной целостности в удаленном расположении.

Необходимо синхронизировать любой многопоточный доступ к одному и тому же источнику данных.

Среда выполнения предоставляет следующие гарантии относительно кэширования данных в `array_view`ных объектах:

- Все хорошо синхронизированные обращения к объекту `array` и объекту `array_view` в нем в порядке программ подчиняются последовательному взаимосвязи.

- Все хорошо синхронизированные доступ к перекрывающимся `array_view` объектам одного и того же ускорителя в одном `array`ном объекте имеют псевдонимы через объект `array`. Они применяют общее число происходящих перед связью, которая подчиняется порядкам программ. Кэширование отсутствует. Если `array_view` объекты выполняются на разных ускорителях, порядок доступа не определен, создается состояние гонки.

При создании объекта `array_view` с помощью указателя в системной памяти необходимо изменить объект View `array_view` только с помощью указателя `array_view`. Кроме того, необходимо вызвать `refresh()` для одного из объектов `array_view`, присоединенных к системному указателю, если базовая память, управляемая в машинном формате, изменяется напрямую, а не через объект `array_view`.

Любое действие уведомляет объект `array_view` о том, что базовая память базовой памяти изменилась и все копии, расположенные на ускорителе, устарели. Если следовать этим рекомендациям, представления на основе указателя идентичны тем, которые предоставляются представлениям параллельных массивов данных.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_Array_view_shape`

`_Array_view_base`

`array_view`

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="dtor"></a>~ array_view

Уничтожает объект `array_view`.

```cpp
~array_view()restrict(amp,cpu);
```

## <a name="ctor"></a>array_view

Инициализирует новый экземпляр класса `array_view`.

```cpp
array_view(
    array<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view& _Other)restrict(amp,cpu);

explicit array_view(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

template <
    typename _Container
>
array_view(
    const Concurrency::extent<_Rank>& _Extent,
    _Container& _Src) restrict(cpu);

array_view(
    const Concurrency::extent<_Rank>& _Extent,
    value_type* _Src)restrict(amp,cpu);

explicit array_view(
    int _E0) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    _Container& _Src,
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    int _E0,
    _Container& _Src) restrict(cpu);

explicit array_view(
    int _E0,
    int _E1) __CPU_ONLY;

template <
    typename _Container
>
explicit array_view(
    int _E0,
    int _E1,
    _Container& _Src) restrict(cpu);

explicit array_view(
    int _E0,
    int _E1,
    int _E2) __CPU_ONLY;

template <
    typename _Container
>
explicit array_view(
    int _E0,
    int _E1,
    int _E2,
    _Container& _Src);

explicit array_view(
    int _E0,
    _In_ value_type* _Src)restrict(amp,cpu);

template <
    typename _Arr_type,
    int _Size
>
explicit array_view(
    _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

explicit array_view(
    int _E0,
    int _E1,
    _In_ value_type* _Src)restrict(amp,cpu);

explicit array_view(
    int _E0,
    int _E1,
    int _E2,
    _In_ value_type* _Src)restrict(amp,cpu);

array_view(
    const array<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view<const value_type, _Rank>& _Src)restrict(amp,cpu);

template <
    typename _Container
>
array_view(
    const Concurrency::extent<_Rank>& _Extent,
    const _Container& _Src) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    const _Container& _Src,
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

array_view(
    const Concurrency::extent<_Rank>& _Extent,
    const value_type* _Src)restrict(amp,cpu);

template <
    typename _Arr_type,
    int _Size
>
explicit array_view(
    const _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

template <
    typename _Container
>
array_view(
    int _E0,
    const _Container& _Src);

template <
    typename _Container
>
array_view(
    int _E0,
    int _E1,
    const _Container& _Src);

template <
    typename _Container
>
array_view(
    int _E0,
    int _E1,
    int _E2,
    const _Container& _Src);

array_view(
    int _E0,
    const value_type* _Src)restrict(amp,cpu);

array_view(
    int _E0,
    int _E1,
    const value_type* _Src) restrict(amp,cpu);

array_view(
    int _E0,
    int _E1,
    int _E2,
    const value_type* _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Arr_type*<br/>
Тип элемента массива в стиле C, из которого передаются данные.

*_Container*<br/>
Аргумент шаблона, который должен указывать линейный контейнер, поддерживающий `data()` и `size()` членов.

*_E0*<br/>
Наиболее важный компонент экстента этого раздела.

*_E1*<br/>
Наиболее важный компонент в области этого раздела.

*_E2*<br/>
Наименее важный компонент экстента этого раздела.

*_Extent*<br/>
Экстент в каждом измерении этого `array_view`.

*_Other*<br/>
Объект типа `array_view<T,N>`, из которого инициализируется новый `array_view`.

*_Size*<br/>
Размер массива в стиле C, из которого передаются данные.

*_Src*<br/>
Указатель на исходные данные, которые будут скопированы в новый массив.

## <a name="copy_to"></a>copy_to

Копирует содержимое объекта `array_view` в указанный целевой объект, вызывая метод `copy(*this, dest)`.

```cpp
void copy_to(
    array<value_type, _Rank>& _Dest) const;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const;
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Объект для копирования.

## <a name="data"></a>Data

Возвращает указатель на необработанные данные `array_view`.

```cpp
value_type* data() const restrict(amp,
    cpu);

const value_type* data() const restrict(amp,
    cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на необработанные данные `array_view`.

## <a name="discard_data"></a>discard_data

Отменяет текущие данные, лежащие в этом представлении. Это указание оптимизации для среды выполнения, используемое, чтобы избежать копирования текущего содержимого представления на целевой `accelerator_view`, к которому он обращается, и рекомендуется использовать его, если существующее содержимое не требуется. Этот метод является оператором No-Op при использовании в контексте ограничения (amp)

```cpp
void discard_data() const restrict(cpu);
```

## <a name="extent"></a>экстент

Получает объект `extent`, который определяет форму объекта `array_view`.

```cpp
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

## <a name="get_extent"></a>get_extent

Возвращает объект [экстента](extent-class.md) объекта `array_view`.

```cpp
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```

### <a name="return-value"></a>Возвращаемое значение

Объект `extent` объекта `array_view`

## <a name="get_ref"></a>get_ref

Получите ссылку на элемент, индексируемый _Index. В отличие от других операторов индексирования для доступа к array_view ЦП, этот метод не выполняет неявную синхронизацию содержимого этого array_view с ЦП. После доступа к array_view в удаленном расположении или выполнения операции копирования, включающей эту array_view, пользователи должны явным образом синхронизировать array_view с ЦП перед вызовом этого метода. Несоблюдение этого действия приводит к неопределенному поведению.

```cpp
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент, индексированный по _Index

## <a name="get_source_accelerator_view"></a>get_source_accelerator_view

Возвращает accelerator_view, где расположен источник данных array_view. Если array_view не имеет источника данных, этот API выдает исключение runtime_exception

```cpp
accelerator_view get_source_accelerator_view() const;
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="operator_call"></a>оператор ()

Возвращает значение элемента, заданного параметром или параметрами.

```cpp
value_type& operator() (
    const index<_Rank>& _Index) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator() (
    int _I) const restrict(amp,cpu);

value_type& operator() (
    int _I0,
    int _I1) const restrict(amp,cpu);

value_type& operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator() (
    int _I) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Расположение элемента.

*_I0*<br/>
Индекс в первом измерении.

*_I1*<br/>
Индекс во втором измерении.

*_I2*<br/>
Индекс в третьем измерении.

*_I*<br/>
Расположение элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение элемента, заданного параметром или параметрами.

## <a name="operator_at"></a>operator []

Возвращает элемент, заданный параметрами.

```cpp
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс.

*_I*<br/>
Индекс.

### <a name="return-value"></a>Возвращаемое значение

Значение элемента в индексе или `array_view` проецируется на наиболее значимое измерение.

## <a name="operator_eq"></a>Оператор =

Копирует содержимое указанного объекта `array_view` в этот объект.

```cpp
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект `array_view`, из которого производится копирование.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот объект `array_view`.

## <a name="rank"></a>Рейтинг

Хранит ранг объекта `array_view`.

```cpp
static const int rank = _Rank;
```

## <a name="refresh"></a>обновляется

Уведомляет объект `array_view` о том, что связанная с ним память была изменена вне интерфейса `array_view`. Вызов этого метода выводит все кэшированные данные в устаревшем виде.

```cpp
void refresh() const restrict(cpu);
```

## <a name="reinterpret_as"></a>reinterpret_as

Повторно интерпретирует array_view с помощью одномерного array_view, который может иметь тип значения, отличный от типа исходного array_view.

### <a name="syntax"></a>Синтаксис

```cpp
template <
    typename _Value_type2
>
array_view< _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);

template <
    typename _Value_type2
>
array_view<const _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Value_type2*<br/>
Тип данных нового объекта `array_view`.

### <a name="return-value"></a>Возвращаемое значение

Объект `array_view` или константный `array_view` объект, основанный на этом `array_view`, с типом элемента, преобразованным из `T` в `_Value_type2`, а ранг уменьшился с *N* до 1.

### <a name="remarks"></a>Примечания

Иногда удобно просматривать многомерный массив в виде линейного одномерного массива, который может иметь тип значения, отличный от типа исходного массива. Это можно сделать на `array_view` с помощью этого метода.

**Предупреждение об ошибке** Повторное выполнение объекта array_view с использованием другого типа значения является потенциально небезопасной операцией. Эта функция должна использоваться с осторожностью.

Ниже приведен пример:

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

## <a name="section"></a>раздела

Возвращает подраздел объекта `array_view`, который находится в указанном источнике и, при необходимости, с указанным экстентом.

```cpp
array_view section(
    const Concurrency::index<_Rank>& _Section_origin,
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);

array_view section(
    const Concurrency::index<_Rank>& _Idx) const restrict(amp,cpu);

array_view section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);

array_view section(
    int _I0,
    int _E0) const restrict(amp,cpu);

array_view section(
    int _I0,
    int _I1,
    int _E0,
    int _E1) const restrict(amp,cpu);

array_view section(
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

### <a name="return-value"></a>Возвращаемое значение

Подраздел объекта `array_view`, который находится в указанном источнике и, при необходимости, с указанным экстентом. Если указан только объект `index`, подраздел содержит все элементы в связанном экстенте с индексами, превышающими индексы элементов в объекте `index`.

## <a name="source_accelerator_view"></a>source_accelerator_view

Возвращает accelerator_view источника, с которым связана эта array_view.

```cpp
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;
```

## <a name="synchronize"></a>полнит

Синхронизирует любые изменения, внесенные в объект `array_view`, обратно в исходные данные.

```cpp
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize() const restrict(cpu);
```

### <a name="parameters"></a>Параметры

*_Access_type*<br/>
Предполагаемый [access_type](concurrency-namespace-enums-amp.md#access_type) на целевом [accelerator_view](accelerator-view-class.md). Этот параметр имеет значение по умолчанию `access_type_read`.

## <a name="synchronize_async"></a>synchronize_async

Асинхронно синхронизирует любые изменения, внесенные в объект `array_view`, обратно в исходные данные.

```cpp
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_async() const restrict(cpu);
```

### <a name="parameters"></a>Параметры

*_Access_type*<br/>
Предполагаемый [access_type](concurrency-namespace-enums-amp.md#access_type) на целевом [accelerator_view](accelerator-view-class.md). Этот параметр имеет значение по умолчанию `access_type_read`.

### <a name="return-value"></a>Возвращаемое значение

Будущее, на которую следует ожидать завершения операции.

## <a name="synchronize_to"></a>synchronize_to

Синхронизирует все изменения, внесенные в этот array_view, в указанный accelerator_view.

```cpp
void synchronize_to(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>Параметры

*_Accl_view*<br/>
Целевой accelerator_view для синхронизации.

*_Access_type*<br/>
Требуемый access_type на целевом accelerator_view. Этот параметр имеет значение по умолчанию access_type_read.

## <a name="synchronize_to_async"></a>synchronize_to_async

Асинхронно синхронизирует любые изменения, внесенные в этот array_view, в указанный accelerator_view.

```cpp
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>Параметры

*_Accl_view*<br/>
Целевой accelerator_view для синхронизации.

*_Access_type*<br/>
Требуемый access_type на целевом accelerator_view. Этот параметр имеет значение по умолчанию access_type_read.

### <a name="return-value"></a>Возвращаемое значение

Будущее, на которую следует ожидать завершения операции.

## <a name="value_type"></a>value_type

Тип значения array_view и привязанного массива.

```cpp
typedef typenamevalue_type value_type;
```

## <a name="view_as"></a>view_as

Переинтерпретирует этот `array_view` как `array_view` другого ранга.

```cpp
template <
    int _New_rank
>
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);

template <
    int _New_rank
>
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank> _View_extent) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_New_rank*<br/>
Ранг нового объекта `array_view`.

*_View_extent*<br/>
`extent`изменения формы.

*value_type*<br/>
Тип данных элементов как исходного объекта [массива](array-class.md) , так и возвращенного `array_view` объекта.

### <a name="return-value"></a>Возвращаемое значение

Созданный объект `array_view`.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
