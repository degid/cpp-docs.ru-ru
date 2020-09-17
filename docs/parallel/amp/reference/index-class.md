---
title: Класс index
ms.date: 03/27/2019
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
ms.openlocfilehash: 50222015e6b365dc161fd4334067c26c7f288337
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365149"
---
# <a name="index-class"></a>Класс index

Определяет *вектор*N-мерного индекса.

## <a name="syntax"></a>Синтаксис

```cpp
template <int _Rank>
class index;
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг, или количество измерений.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[индекс конструктор](#index_ctor)|Инициализирует новый экземпляр класса `index`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator--](#operator--)|Декретирует каждый `index` элемент объекта.|
|[оператор%](#operator_mod_eq)|Вычисляет модуль (остаток) каждого элемента в объекте, `index` когда этот элемент делится на число.|
|[оператора](#operator_star_eq)|Умножает каждый `index` элемент объекта на число.|
|[оператор/я](#operator_div_eq)|Разделяет каждый `index` элемент объекта на число.|
|[индекс::оператор\[\]](#operator_at)|Возвращает элемент, наданный в указанном индексе.|
|[оператор](#operator_add_add)|Приращения каждого `index` элемента объекта.|
|[оператора](#operator_add_eq)|Добавляет указанное число к `index` каждому элементу объекта.|
|[оператора](#operator_eq)|Копирует содержимое указанного `index` объекта в этот.|
|[operator-я](#operator_-_eq)|Вычитает указанное число из каждого `index` элемента объекта.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[ранг константа](#rank)|Хранит ранг `index` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`index`

## <a name="remarks"></a>Примечания

Структура `index` представляет собой вектором координат *N,* который определяет уникальное положение в *N-мерном*пространстве. Значения в векторе упорядочены от наиболее значительных до наименее значительных. Вы можете получить значения компонентов с помощью [оператора.](#operator_eq)

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="index-constructor"></a><a name="index_ctor"></a>индекс конструктор

Инициализирует новый экземпляр класса индекса.

```cpp
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Array*<br/>
Одномерный массив со значениями ранга.

*_i*<br/>
Расположение индекса в одномерном индексе.

*_I0*<br/>
Длина наиболее значительного измерения.

*_I1*<br/>
Длина следующего к самому значительному измерению.

*_I2*<br/>
Длина наименее значимого измерения.

*_Other*<br/>
Объект индекса, на котором основан новый объект индекса.

## <a name="operator--"></a><a name="operator--"></a>оператор--

Декретирует каждый элемент объекта индекса.

```cpp
index<_Rank>& operator--() restrict(amp,cpu);

index operator--(
   int
) restrict(amp,cpu);
```

### <a name="return-values"></a>Возвращаемые значения

Для оператора префикса, объекта индекса (это). Для оператора суффикса новый объект индекса.

## <a name="operator"></a><a name="operator_mod_eq"></a>оператор%

Вычисляет модуль (остаток) каждого элемента в объекте индекса, когда этот элемент делится на указанное число.

```cpp
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число разделить, чтобы найти модуля.

## <a name="return-value"></a>Возвращаемое значение

Объект индекса.

## <a name="operator"></a><a name="operator_star_eq"></a>оператора

Умножает каждый элемент объекта индекса на указанное число.

```cpp
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число, чтобы умножить.

## <a name="operator"></a><a name="operator_div_eq"></a>оператор/я

Разделяет каждый элемент объекта индекса на указанное число.

```cpp
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число, чтобы разделить.

## <a name="operator"></a><a name="operator_at"></a>Оператор\[\]

Возвращает компонент индекса в указанном месте.

```cpp
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Цель от 0 до ранга минус 1.

### <a name="return-value"></a>Возвращаемое значение

Элемент, наданный в указанном индексе.

### <a name="remarks"></a>Примечания

В следующем примере отображаются значения компонентов индекса.

```cpp
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator"></a><a name="operator_add_add"></a>оператор

Приращения каждого элемента объекта индекса.

```cpp
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Для оператора префикса, объекта индекса (это). Для оператора суффикса новый объект индекса.

## <a name="operator"></a><a name="operator_add_eq"></a>оператора

Добавляет указанное число к каждому элементу объекта индекса.

```cpp
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Номер для добавления.

### <a name="return-value"></a>Возвращаемое значение

Объект индекса.

## <a name="operator"></a><a name="operator_eq"></a>оператора

Копирует содержимое указанного объекта индекса в этот объект.

```cpp
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект индекса для копирования.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот объект индекса.

## <a name="operator-"></a><a name="operator_-_eq"></a>оператор-я

Вычитает указанное число из каждого элемента объекта индекса.

```cpp
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Число вычесть.

### <a name="return-value"></a>Возвращаемое значение

Объект индекса.

## <a name="rank"></a><a name="rank"></a>Ранга

Получает ранг объекта индекса.

```cpp
static const int rank = _Rank;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен параллелизма (КЗ АМП)](concurrency-namespace-cpp-amp.md)
