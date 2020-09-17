---
title: Класс location
ms.date: 11/04/2016
f1_keywords:
- location
- CONCRT/concurrency::location
- CONCRT/concurrency::location::location
- CONCRT/concurrency::location::current
- CONCRT/concurrency::location::from_numa_node
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
ms.openlocfilehash: 848be3131e23ff53f2dec16364b132ee7c218195
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87182698"
---
# <a name="location-class"></a>Класс location

Абстракция физического расположения на оборудовании.

## <a name="syntax"></a>Синтаксис

```cpp
class location;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[расположение](#ctor)|Перегружен. Формирует объект `location`.|
|[Деструктор ~ Location](#dtor)|Уничтожает объект `location` .|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[данном](#current)|Возвращает объект `location`, представляющий наиболее определенное расположение, выполняемое вызывающим потоком.|
|[from_numa_node](#from_numa_node)|Возвращает объект `location`, представляющий заданный узел NUMA.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator!=](#operator_neq)|Определяет, представляют ли два объекта `location` различные расположения.|
|[operator=](#operator_eq)|Назначает содержимое другого объекта `location` данному.|
|[operator==](#operator_eq_eq)|Определяет `location` , представляют ли два объекта одно и то же расположение.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`location`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

**Пространство имен:** concurrency

## <a name="location"></a><a name="dtor"></a>расположение ~

Уничтожает объект `location` .

```cpp
~location();
```

## <a name="current"></a><a name="current"></a>данном

Возвращает объект `location`, представляющий наиболее определенное расположение, выполняемое вызывающим потоком.

```cpp
static location __cdecl current();
```

### <a name="return-value"></a>Возвращаемое значение

Расположение, представляющее наиболее определенное место, выполняемое вызывающим потоком.

## <a name="from_numa_node"></a><a name="from_numa_node"></a>from_numa_node

Возвращает объект `location`, представляющий заданный узел NUMA.

```cpp
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```

### <a name="parameters"></a>Параметры

*_NumaNodeNumber*<br/>
Номер узла NUMA для построения его расположения.

### <a name="return-value"></a>Возвращаемое значение

Расположение, представляющее узел NUMA, указывается с помощью параметра `_NumaNodeNumber`.

## <a name="location"></a><a name="ctor"></a>места

Формирует объект `location`.

```cpp
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>

*_LocationType*<br/>

*_Id*<br/>

*_BindingId*<br/>

*_PBinding*<br/>
Используемых Указатель привязки.

### <a name="remarks"></a>Примечания

Созданное расположение по умолчанию представляет систему в целом.

## <a name="operator"></a><a name="operator_neq"></a>operator!=

Определяет, представляют ли два объекта `location` различные расположения.

```cpp
bool operator!= (const location& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Операнд `location` .

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если два расположения различаются; **`false`** в противном случае —.

## <a name="operator"></a><a name="operator_eq"></a>Оператор =

Назначает содержимое другого объекта `location` данному.

```cpp
location& operator= (const location& _Rhs);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Исходный объект `location`.

### <a name="return-value"></a>Возвращаемое значение

## <a name="operator"></a><a name="operator_eq_eq"></a>Оператор = =

Определяет `location` , представляют ли два объекта одно и то же расположение.

```cpp
bool operator== (const location& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Операнд `location` .

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если два расположения идентичны и **`false`** в противном случае.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)
