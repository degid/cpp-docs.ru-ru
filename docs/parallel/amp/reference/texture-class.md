---
title: Класс texture
ms.date: 11/04/2016
f1_keywords:
- texture
- AMP_GRAPHICS/texture
- AMP_GRAPHICS/concurrency::graphics::texture::texture
- AMP_GRAPHICS/concurrency::graphics::texture::copy_to
- AMP_GRAPHICS/concurrency::graphics::texture::data
- AMP_GRAPHICS/concurrency::graphics::texture::get
- AMP_GRAPHICS/concurrency::graphics::texture::get_associated_accelerator_view
- AMP_GRAPHICS/concurrency::graphics::texture::get_depth_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::get_row_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::set
- AMP_GRAPHICS/concurrency::graphics::texture::rank
- AMP_GRAPHICS/concurrency::graphics::texture::associated_accelerator_view
- AMP_GRAPHICS/concurrency::graphics::texture::depth_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::row_pitch
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
ms.openlocfilehash: b8a37293166ec21aeb9410f05fb70c9753ec4f22
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230419"
---
# <a name="texture-class"></a>Класс texture

Текстура — это статистическое выражение данных в `accelerator_view` домене экстента. Это коллекция переменных, по одному для каждого элемента в домене экстента. Каждая переменная содержит значение, соответствующее типу-примитиву C++ ( **`unsigned int`** , **`int`** , **`float`** , **`double`** ), скалярному типу ( `norm` , или `unorm` ) или короткому вектору типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename value_type,  int _Rank>
class texture;
```

### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип элементов текстуры.

*_Rank*<br/>
Ранг текстуры.

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`scalar_type`|Скалярные типы.|
|`value_type`|Типы значений.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор текстур](#ctor)|Инициализирует новый экземпляр класса `texture`.|
|[~ Деструктор текстуры](#ctor)|Уничтожает `texture` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[copy_to](#copy_to)|Копирует `texture` объект в место назначения, выполняя глубокое копирование.|
|[data](#data)|Возвращает указатель ЦП на необработанные данные этой текстуры.|
|[get](#get)|Возвращает значение элемента по указанному индексу.|
|[get_associated_accelerator_view](#get_associated_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) , который является предпочтительным целевым объектом для копирования текстуры в.|
|[get_depth_pitch](#get_depth_pitch)|Возвращает число байтов между каждым срезом глубины в трехмерной текстуре на ЦП.|
|[get_row_pitch](#get_row_pitch)|Возвращает число байтов между строками в двухмерной или трехмерной промежуточной текстуре ЦП.|
|[set](#set)|Задает значение элемента по указанному индексу.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор ()](#operator_call)|Возвращает значение элемента, заданное параметрами.|
|[оператор\[\]](#operator_at)|Возвращает элемент, расположенный по указанному индексу.|
|[operator=](#operator_eq)|Копирует указанный объект [текстуры](texture-class.md) в эту единицу.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[Константа Rank](#rank)|Возвращает ранг `texture` объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[associated_accelerator_view](#associated_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) , который является предпочтительным целевым объектом для копирования текстуры в.|
|[depth_pitch](#depth_pitch)|Возвращает число байтов между каждым срезом глубины в трехмерной текстуре на ЦП.|
|[row_pitch](#row_pitch)|Возвращает количество байтов между строками в двухмерной или трехмерной промежуточной текстуре ЦП.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_Texture_base`

`texture`

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен:** concurrency::graphics

## <a name="texture"></a><a name="dtor"></a>~ Текстура

Уничтожает `texture` объект.

```cpp
~texture() restrict(cpu);
```

## <a name="associated_accelerator_view"></a><a name="associated_accelerator_view"></a>associated_accelerator_view

Возвращает [accelerator_view](accelerator-view-class.md) , который является предпочтительным целевым объектом для копирования текстуры в.

```cpp
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;
```

## <a name="copy_to"></a><a name="copy_to"></a>copy_to

Копирует `texture` объект в место назначения, выполняя глубокое копирование.

```cpp
void copy_to(texture& _Dest) const;
void copy_to(writeonly_texture_view<value_type, _Rank>& _Dest) const;
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Объект для копирования.

*_Rank*<br/>
Ранг текстуры.

*value_type*<br/>
Тип элементов текстуры.

## <a name="data"></a>Данные <a name="data"></a>.

Возвращает указатель ЦП на необработанные данные этой текстуры.

```cpp
void* data() restrict(cpu);

const void* data() const restrict(cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на необработанные данные текстуры.

## <a name="depth_pitch"></a><a name="depth_pitch"></a>depth_pitch

Возвращает число байтов между каждым срезом глубины в трехмерной текстуре на ЦП.

```cpp
__declspec(property(get= get_depth_pitch)) unsigned int depth_pitch;
```

## <a name="get"></a><a name="get"></a>Получить

Возвращает значение элемента по указанному индексу.

```cpp
const value_type get(const index<_Rank>& _Index) const restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение элемента по указанному индексу.

## <a name="get_associated_accelerator_view"></a><a name="get_associated_accelerator_view"></a>get_associated_accelerator_view

Возвращает accelerator_view, который является предпочтительным целевым объектом для копирования текстуры в.

```cpp
Concurrency::accelerator_view get_associated_accelerator_view() const restrict(cpu);
```

### <a name="return-value"></a>Возвращаемое значение

[Accelerator_view](accelerator-view-class.md) , который является предпочтительным целевым объектом для этой текстуры, в которую будет скопирована Эта текстура.

## <a name="get_depth_pitch"></a><a name="get_depth_pitch"></a>get_depth_pitch

Возвращает число байтов между каждым срезом глубины в трехмерной текстуре на ЦП.

```cpp
unsigned int get_depth_pitch() const restrict(cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Число байтов между каждым срезом глубины в трехмерной промежуточной текстуре ЦП.

## <a name="get_row_pitch"></a><a name="get_row_pitch"></a>get_row_pitch

Возвращает число байтов между каждой строкой в двумерной промежуточной текстуре или между каждой строкой среза глубины в трехмерной промежуточной текстуре.

```cpp
unsigned int get_row_pitch() const restrict(cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Число байтов между каждой строкой в двумерной промежуточной текстуре или между каждой строкой среза глубины в трехмерной промежуточной текстуре.

## <a name="operator"></a><a name="operator_call"></a>оператор ()

Возвращает значение элемента, заданное параметрами.

```cpp
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

const value_type operator() (
    int _I0) const restrict(amp);

const value_type operator() (
    int _I0,
    int _I1) const restrict(amp);

const value_type operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс.

*_I0*<br/>
Наиболее важный компонент индекса.

*_I1*<br/>
Компонент индекса "новый", наиболее важный для использования.

*_I2*<br/>
Наименее важный компонент индекса.

*_Rank*<br/>
Ранг индекса.

### <a name="return-value"></a>Возвращаемое значение

Значение элемента, заданное параметрами.

## <a name="operator"></a><a name="operator_at"></a>operator []

Возвращает элемент, расположенный по указанному индексу.

```cpp
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

const value_type operator[] (int _I0) const restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс.

*_I0*<br/>
Индекс.

### <a name="return-value"></a>Возвращаемое значение

Элемент, расположенный по указанному индексу.

## <a name="operator"></a><a name="operator_eq"></a>Оператор =

Копирует указанный объект [текстуры](texture-class.md) в эту единицу.

```cpp
texture& operator= (
    const texture& _Other);

texture& operator= (
    texture<value_type, _Rank>&& _Other);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект, из которого производится `texture` копирование.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `texture` объект.

## <a name="rank"></a><a name="rank"></a>Рейтинг

Возвращает ранг `texture` объекта.

```cpp
static const int rank = _Rank;
```

## <a name="row_pitch"></a><a name="row_pitch"></a>row_pitch

Возвращает количество байтов между строками в двухмерной или трехмерной промежуточной текстуре ЦП.

```cpp
__declspec(property(get= get_row_pitch)) unsigned int row_pitch;
```

## <a name="set"></a><a name="set"></a>параметр

Задает значение элемента по указанному индексу.

```cpp
void set(
    const index<_Rank>& _Index,
    const value_type& value) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс элемента.

*_Rank*<br/>
Ранг индекса.

*value*<br/>
Новое значение элемента.

## <a name="texture"></a><a name="ctor"></a>поддержки

Инициализирует новый экземпляр класса `texture`.

```cpp
texture(const Concurrency::extent<_Rank>& _Ext) restrict(cpu);

texture(int _E0) restrict(cpu);

texture(int _E0, int _E1) restrict(cpu);

texture(int _E0, int _E1, int _E2) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    const Concurrency::extent<_Rank>& _Ext,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    int _E2,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    const Concurrency::extent<_Rank>& _Ext,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    int _E2,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu))  ;

texture(
    int _E0,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av)  ;

texture(
    int _E0,
    int _E1,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av)  ;

texture(
    int _E0,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    const texture& _Src,
    const Concurrency::accelerator_view& _Acc_view);

texture(
    texture&& _Other);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av);

texture(
    const texture& _Src);
```

### <a name="parameters"></a>Параметры

*_Acc_view*<br/>
[Accelerator_view](accelerator-view-class.md) , указывающий расположение текстуры.

*_Av*<br/>
[Accelerator_view](accelerator-view-class.md) , указывающий расположение текстуры.

*_Associated_av*<br/>
Accelerator_view, указывающий предпочтительный целевой объект для копирования в эту текстуру или из нее.

*_Bits_per_scalar_element*<br/>
Количество битов на каждый скалярный элемент в базовом скалярном типе текстуры. В общем, поддерживаются значения 8, 16, 32 и 64. Если указано значение 0, то количество бит совпадает с базовым scalar_type. 64 является допустимым только для текстур с двойным интерфейсом.

*_Ext*<br/>
Экстент в каждом измерении текстуры.

*_E0*<br/>
Наиболее важный компонент текстуры.

*_E1*<br/>
Компонент текстуры «последующий-самый важный».

*_E2*<br/>
Наименее важный компонент экстента текстуры.

*_Input_iterator*<br/>
Тип итератора ввода.

*_Mipmap_levels*<br/>
Число уровней mipmap в базовой текстуре. Если указано значение 0, то текстура будет иметь полный диапазон уровней mipmap до наименьшего возможного размера для указанного экстента.

*_Rank*<br/>
Ранг экстента.

*_Source*<br/>
Указатель на буфер узла.

*_Src*<br/>
Копируемая текстура.

*_Src_byte_size*<br/>
Число байтов в исходном буфере.

*_Src_first*<br/>
Начальный итератор в исходный контейнер.

*_Src_last*<br/>
Конечный итератор в исходный контейнер.

*_Other*<br/>
Другой источник данных.

*_Rank*<br/>
Ранг раздела.

## <a name="see-also"></a>См. также статью

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
