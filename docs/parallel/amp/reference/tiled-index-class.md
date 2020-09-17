---
title: Класс tiled_index
ms.date: 03/27/2019
f1_keywords:
- tiled_index
- AMP/tiled_index
- AMP/Concurrency::tiled_index::tiled_index
- AMP/Concurrency::tiled_index::get_tile_extent
- AMP/Concurrency::tiled_index::barrier
- AMP/Concurrency::tiled_index::global
- AMP/Concurrency::tiled_index::local
- AMP/Concurrency::tiled_index::rank
- AMP/Concurrency::tiled_index::tile
- AMP/Concurrency::tiled_index::tile_dim0
- AMP/Concurrency::tiled_index::tile_dim1
- AMP/Concurrency::tiled_index::tile_dim2
- AMP/Concurrency::tiled_index::tile_origin
- AMP/Concurrency::tiled_index::tile_extent
helpviewer_keywords:
- tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
ms.openlocfilehash: 9d295093031eaee0a2d4dd83aa931060e6eebc07
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832274"
---
# <a name="tiled_index-class"></a>Класс tiled_index

Предоставляет индекс для объекта [tiled_extent](tiled-extent-class.md) . Этот класс имеет свойства для доступа к элементам по отношению к локальному источнику плитки и по отношению к глобальному источнику. Дополнительные сведения о мозаичных пробелах см. [в разделе Использование плиток](../../../parallel/amp/using-tiles.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <
    int _Dim0,
    int _Dim1 = 0,
    int _Dim2 = 0
>
class tiled_index : public _Tiled_index_base<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;

template <
    int _Dim0
>
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;
```

### <a name="parameters"></a>Параметры

*_Dim0*<br/>
Длина наиболее значимого измерения.

*_Dim1*<br/>
Длина последующего и значительного измерения.

*_Dim2*<br/>
Длина наименее значимого измерения.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор tiled_index](#ctor)|Инициализирует новый экземпляр класса `tile_index`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get_tile_extent](#tiled_index__get_tile_extent)|Возвращает объект [экстента](extent-class.md) , содержащий значения `tiled_index` аргументов шаблона `_Dim0` , `_Dim1` и `_Dim2` .|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[Константа барьера](#tiled_index__barrier)|Хранит объект [tile_barrier](tile-barrier-class.md) , представляющий барьер в текущей плитке потоков.|
|[глобальная константа](#tiled_index__global)|Хранит объект [индекса](index-class.md) ранга 1, 2 или 3, представляющий глобальный индекс в объекте Grid.|
|[local - константа](#tiled_index__local)|Сохраняет `index` объект ранга 1, 2 или 3, представляющий относительный индекс в текущей плитке объекта [tiled_extent](tiled-extent-class.md) .|
|[Константа Rank](#tiled_index__rank)|Хранит ранг `tiled_index` объекта.|
|[Константа плитки](#tiled_index__tile)|Сохраняет `index` объект с рангом 1, 2 или 3, представляющий координаты текущей плитки `tiled_extent` объекта.|
|[Константа tile_dim0](#tiled_index__tile_dim0)|Хранит длину наиболее значимого измерения.|
|[Константа tile_dim1](#tiled_index__tile_dim1)|Сохраняет длину последующего и значительного измерения.|
|[Константа tile_dim2](#tiled_index__tile_dim2)|Хранит длину наименее значимого измерения.|
|[Константа tile_origin](#tiled_index__tile_origin)|Сохраняет `index` объект с рангом 1, 2 или 3, представляющий глобальные координаты источника текущей плитки в `tiled_extent` объекте.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[tile_extent](#tile_extent)|Возвращает объект [экстента](extent-class.md) , содержащий значения `tiled_index` `tiled_index` аргументов шаблона аргументов шаблона `_Dim0` , `_Dim1` и `_Dim2` .|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_Tiled_index_base`

`tiled_index`

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="tiled_index-constructor"></a><a name="ctor"></a> Конструктор tiled_index

Инициализирует новый экземпляр класса `tiled_index`.

### <a name="syntax"></a>Синтаксис

```cpp
tiled_index(
    const index<rank>& _Global,
    const index<rank>& _Local,
    const index<rank>& _Tile,
    const index<rank>& _Tile_origin,
    const tile_barrier& _Barrier ) restrict(amp,cpu);

tiled_index(
    const tiled_index& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Global*<br/>
Глобальный [индекс](index-class.md) созданного объекта `tiled_index` .

*_Local*<br/>
Локальный [индекс](index-class.md) созданного `tiled_index`

*_Tile*<br/>
[Индекс](index-class.md) плитки созданного элемента`tiled_index`

*_Tile_origin*<br/>
[Индекс](index-class.md) источника плитки созданного элемента`tiled_index`

*_Barrier*<br/>
Объект [tile_barrier](tile-barrier-class.md) созданного объекта `tiled_index` .

*_Other*<br/>
Объект, который необходимо `tile_index` скопировать в создаваемый `tiled_index` .

### <a name="overloads"></a>Перегрузки

|Имя|Описание|
|-|-|
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|Инициализирует новый экземпляр `tile_index` класса из индекса плитки в глобальных координатах и относительного положения в плитке в локальных координатах. `_Global`Параметры и `_Tile_origin` вычисляются.|
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|Инициализирует новый экземпляр `tile_index` класса путем копирования указанного `tiled_index` объекта.|

## <a name="get_tile_extent"></a><a name="tiled_index__get_tile_extent"></a> get_tile_extent

Возвращает объект [экстента](extent-class.md) , содержащий значения `tiled_index` аргументов шаблона `_Dim0` , `_Dim1` и `_Dim2` .

### <a name="syntax"></a>Синтаксис

```cpp
extent<rank> get_tile_extent()restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

`extent`Объект, содержащий значения `tiled_index` аргументов шаблона `_Dim0` , `_Dim1` и `_Dim2` .

## <a name="barrier"></a><a name="tiled_index__barrier"></a> лежащим

Хранит объект [tile_barrier](tile-barrier-class.md) , представляющий барьер в текущей плитке потоков.

### <a name="syntax"></a>Синтаксис

```cpp
const tile_barrier barrier;
```

## <a name="global"></a><a name="tiled_index__global"></a> глобального

Хранит объект [индекса](index-class.md) ранга 1, 2 или 3, представляющий глобальный индекс объекта.

### <a name="syntax"></a>Синтаксис

```cpp
const index<rank> global;
```

## <a name="local"></a><a name="tiled_index__local"></a> Языковые

Хранит объект [индекса](index-class.md) ранга 1, 2 или 3, представляющий относительный индекс в текущей плитке объекта [tiled_extent](tiled-extent-class.md) .

### <a name="syntax"></a>Синтаксис

```cpp
const index<rank> local;
```

## <a name="rank"></a><a name="tiled_index__rank"></a> Рейтинг

Хранит ранг `tiled_index` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
static const int rank = _Rank;
```

## <a name="tile"></a><a name="tiled_index__tile"></a> Tile

Хранит объект [индекса](index-class.md) ранга 1, 2 или 3, который представляет координаты текущей плитки объекта [tiled_extent](tiled-extent-class.md) .

### <a name="syntax"></a>Синтаксис

```cpp
const index<rank> tile;
```

## <a name="tile_dim0"></a><a name="tiled_index__tile_dim0"></a> tile_dim0

Хранит длину наиболее значимого измерения.

### <a name="syntax"></a>Синтаксис

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tiled_index__tile_dim1"></a> tile_dim1

Сохраняет длину последующего и значительного измерения.

### <a name="syntax"></a>Синтаксис

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tiled_index__tile_dim2"></a> tile_dim2

Хранит длину наименее значимого измерения.

### <a name="syntax"></a>Синтаксис

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_origin"></a><a name="tiled_index__tile_origin"></a> tile_origin

Хранит объект [индекса](index-class.md) ранга 1, 2 или 3, представляющий глобальные координаты источника текущей плитки в объекте [tiled_extent](tiled-extent-class.md) .

### <a name="syntax"></a>Синтаксис

```cpp
const index<rank> tile_origin
```

## <a name="tile_extent"></a><a name="tile_extent"></a> tile_extent

Возвращает объект [экстента](extent-class.md) , содержащий значения `tiled_index` `tiled_index` аргументов шаблона аргументов шаблона `_Dim0` , `_Dim1` и `_Dim2` .

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
