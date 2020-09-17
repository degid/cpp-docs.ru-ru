---
title: Касс extent (C++ AMP)
ms.date: 03/27/2019
f1_keywords:
- extent
- AMP/extent
- AMP/Concurrency::extent::extent
- AMP/Concurrency::extent::contains
- AMP/Concurrency::extent::size
- AMP/Concurrency::extent::tile
- AMP/Concurrency::extent::rank Constant
helpviewer_keywords:
- extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
ms.openlocfilehash: b9fd0ffb0c3ac6e0b80823e9f31c3615a045262b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222736"
---
# <a name="extent-class-c-amp"></a>Касс extent (C++ AMP)

Представляет вектор из *n* целочисленных значений, задающих границы *n*-мерного пространства с источником 0. Значения в векторе упорядочиваются от наиболее значимых к минимально значимым.

## <a name="syntax"></a>Синтаксис

```cpp
template <int _Rank>
class extent;
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг `extent` объекта.

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор экстента](#ctor)|Инициализирует новый экземпляр класса `extent`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[contains](#contains)|Проверяет, имеет ли указанный `extent` объект указанный ранг.|
|[size](#size)|Возвращает общий линейный размер экстента (в единицах элементов).|
|[tile](#tile)|Создает `tiled_extent` объект с экстентами мозаики, заданными заданными измерениями.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator-](#operator_min)|Возвращает новый `extent` объект, созданный путем вычитания `index` элементов из соответствующих `extent` элементов.|
|[operator--](#operator_min_min)|Уменьшает каждый элемент `extent` объекта.|
|[operator%=](#operator_mod_eq)|Вычисляет остаток от деления каждого элемента в `extent` объекте, если этот элемент делится на число.|
|[operator*=](#operator_star_eq)|Умножает каждый элемент `extent` объекта на число.|
|[operator/=](#operator_min_eq)|Делит каждый элемент `extent` объекта на число.|
|[extent::operator\[\]](#operator_at)|Возвращает элемент, расположенный по указанному индексу.|
|[operator+](#operator_add)|Возвращает новый `extent` объект, созданный путем добавления соответствующих `index` `extent` элементов и.|
|[operator++](#operator_add_add)|Увеличивает каждый элемент `extent` объекта.|
|[operator+=](#operator_add_eq)|Добавляет указанный номер к каждому элементу `extent` объекта.|
|[operator=](#operator_eq)|Копирует содержимое другого `extent` объекта в этот объект.|
|[operator-=](#operator_min_eq)|Вычитает указанное число из каждого элемента `extent` объекта.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[Константа Rank](#rank_constant)|Возвращает ранг `extent` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`extent`

## <a name="contains"></a><a name="contains"></a>содержащих

Указывает, содержится ли указанное значение [индекса](index-class.md) в объекте "экстент".

### <a name="syntax"></a>Синтаксис

```cpp
bool contains(const index<rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Проверяемое значение `index`.

### <a name="return-value"></a>Возвращаемое значение

**`true`**, если указанное значение *индекса* содержится в `extent` объекте; в противном случае — **`false`** .

## <a name="extent"></a><a name="ctor"></a>экстент

Инициализирует новый экземпляр класса "экстент".

### <a name="syntax"></a>Синтаксис

```cpp
extent() restrict(amp,cpu);
extent(const extent<_Rank>& _Other) restrict(amp,cpu);
explicit extent(int _I) restrict(amp,cpu);
extent(int _I0,  int _I1) restrict(amp,cpu);
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);
explicit extent(const int _Array[_Rank])restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Array*<br/>
Массив `_Rank` целых чисел, используемый для создания нового `extent` объекта.

*_I*<br/>
Длина экстента.

*_I0*<br/>
Длина наиболее значимого измерения.

*_I1*<br/>
Длина измерения "следующий к значимости".

*_I2*<br/>
Длина наименее значимого измерения.

*_Other*<br/>
`extent`Объект, на котором основан новый `extent` объект.

## <a name="remarks"></a>Примечания

Конструктор по умолчанию инициализирует `extent` объект с рангом 3.

Если массив используется для создания `extent` объекта, длина массива должна совпадать с рангом `extent` объекта.

## <a name="operator"></a><a name="operator_mod_eq"></a>operator%=

Вычисляет остаток от деления каждого элемента в экстенте, если этот элемент делится на число.

### <a name="syntax"></a>Синтаксис

```cpp
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число для поиска модуля.

### <a name="return-value"></a>Возвращаемое значение

Объект `extent`.

## <a name="operator"></a><a name="operator_star_eq"></a>operator*=

Умножает каждый элемент в объекте "экстент" на указанное число.

### <a name="syntax"></a>Синтаксис

```cpp
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число для умножения.

### <a name="return-value"></a>Возвращаемое значение

Объект `extent`.

## <a name="operator"></a><a name="operator_add"></a>operator+

Возвращает новый `extent` объект, созданный путем добавления соответствующих `index` элементов и `extent` .

### <a name="syntax"></a>Синтаксис

```cpp
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
`index`Объект, содержащий добавляемые элементы.

### <a name="return-value"></a>Возвращаемое значение

Новый объект `extent`.

## <a name="operator"></a><a name="operator_add_add"></a>operator++

Увеличивает каждый элемент объекта "экстент".

### <a name="syntax"></a>Синтаксис

```cpp
extent<_Rank>& operator++() restrict(amp,cpu);
extent<_Rank> operator++(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Для оператора префикса — `extent` объект ( **`*this`** ). Для оператора суффикса — новый `extent` объект.

## <a name="operator"></a><a name="operator_add_eq"></a>operator+=

Добавляет указанный номер к каждому элементу объекта "экстент".

### <a name="syntax"></a>Синтаксис

```cpp
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Добавляемое число, индекс или экстент.

### <a name="return-value"></a>Возвращаемое значение

Результирующий объект `extent`.

## <a name="operator-"></a><a name="operator_min"></a>operator-

Создает новый `extent` объект путем вычитания каждого элемента указанного `index` объекта из соответствующего элемента в этом `extent` объекте.

### <a name="syntax"></a>Синтаксис

```cpp
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
`index`Объект, содержащий элементы для вычитания.

### <a name="return-value"></a>Возвращаемое значение

Новый объект `extent`.

## <a name="operator--"></a><a name="operator_min_min"></a>operator--

Уменьшает каждый элемент в объекте "экстент".

### <a name="syntax"></a>Синтаксис

```cpp
extent<_Rank>& operator--() restrict(amp,cpu);
extent<_Rank> operator--(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Для оператора префикса — `extent` объект ( **`*this`** ). Для оператора суффикса — новый `extent` объект.

## <a name="operator"></a><a name="operator_div_eq"></a>operator/=

Делит каждый элемент в объекте "экстент" на указанное число.

### <a name="syntax"></a>Синтаксис

```cpp
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число, на которое производится деление.

### <a name="return-value"></a>Возвращаемое значение

Объект `extent`.

## <a name="operator-"></a><a name="operator_min_eq"></a>operator-=

Вычитает указанное число из каждого элемента объекта "экстент".

### <a name="syntax"></a>Синтаксис

```cpp
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Вычитаемое число.

### <a name="return-value"></a>Возвращаемое значение

Результирующий объект `extent`.

## <a name="operator"></a><a name="operator_eq"></a>operator=

Копирует содержимое другого объекта "расширение" в этот объект.

### <a name="syntax"></a>Синтаксис

```cpp
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект, из которого производится `extent` копирование.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `extent` объект.

## <a name="extentoperator-"></a><a name="operator_at"></a>extent::operator\[\]

Возвращает элемент, расположенный по указанному индексу.

### <a name="syntax"></a>Синтаксис

```cpp
int operator[](unsigned int _Index) const restrict(amp,cpu);
int& operator[](unsigned int _Index) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Целое число от 0 до ранга минус 1.

### <a name="return-value"></a>Возвращаемое значение

Элемент, расположенный по указанному индексу.

## <a name="rank"></a><a name="rank_constant"></a>Рейтинг

Хранит ранг объекта "экстент".

### <a name="syntax"></a>Синтаксис

```cpp
static const int rank = _Rank;
```

## <a name="size"></a><a name="size"></a>изменять

Возвращает общий линейный размер `extent` объекта (в единицах элементов).

### <a name="syntax"></a>Синтаксис

```cpp
unsigned int size() const restrict(amp,cpu);
```

## <a name="tile"></a><a name="tile"></a>Tile

Создает объект tiled_extent с указанными измерениями плитки.

```cpp
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```

### <a name="parameters"></a>Параметры

*_Dim0*<br/>
Наиболее важный компонент мозаичного экстента.
*_Dim1*<br/>
Наиболее важный компонент мозаичного экстента.
*_Dim2*<br/>
Наименее важный компонент мозаичного экстента.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
