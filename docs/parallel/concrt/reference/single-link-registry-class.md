---
title: Класс single_link_registry
ms.date: 11/04/2016
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
ms.openlocfilehash: 24f89a6b2fb998ba5e5a82dbb470accb45d0fd9f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219551"
---
# <a name="single_link_registry-class"></a>Класс single_link_registry

Объект `single_link_registry` представляет собой `network_link_registry`, управляющий только одним блоком источника или целевым блоком.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>Параметры

*_Block*<br/>
Тип данных блока, хранящийся в `single_link_registry` объекте.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[single_link_registry](#ctor)|Формирует объект `single_link_registry`.|
|[Деструктор ~ single_link_registry](#dtor)|Уничтожает `single_link_registry` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[add](#add)|Добавляет ссылку на `single_link_registry` объект. (Переопределяет [network_link_registry:: Add](network-link-registry-class.md#add).)|
|[begin](#begin)|Возвращает итератор на первый элемент в `single_link_registry` объекте. (Переопределяет [network_link_registry:: Begin](network-link-registry-class.md#begin).)|
|[contains](#contains)|Выполняет поиск `single_link_registry` указанного блока в объекте. (Переопределяет [network_link_registry:: Contains](network-link-registry-class.md#contains).)|
|[count](#count)|Подсчитывает количество элементов в `single_link_registry` объекте. (Переопределяет [network_link_registry:: count](network-link-registry-class.md#count).)|
|[remove](#remove)|Удаляет ссылку из `single_link_registry` объекта. (Переопределяет [network_link_registry::Remove](network-link-registry-class.md#remove).)|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[network_link_registry](network-link-registry-class.md)

`single_link_registry`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="add"></a><a name="add"></a>включить

Добавляет ссылку на `single_link_registry` объект.

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на добавляемый блок.

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_link_target](invalid-link-target-class.md) , если в этом реестре уже есть ссылка.

## <a name="begin"></a><a name="begin"></a>начале

Возвращает итератор на первый элемент в `single_link_registry` объекте.

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, обращающийся к первому элементу в `single_link_registry` объекте.

### <a name="remarks"></a>Примечания

Конечное состояние обозначается `NULL` ссылкой.

## <a name="contains"></a><a name="contains"></a>содержащих

Выполняет поиск `single_link_registry` указанного блока в объекте.

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок, который необходимо найти в `single_link_registry` объекте.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если ссылка найдена, **`false`** в противном случае.

## <a name="count"></a><a name="count"></a>расчета

Подсчитывает количество элементов в `single_link_registry` объекте.

```cpp
virtual size_t count();
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в объекте `single_link_registry`.

## <a name="remove"></a><a name="remove"></a>отменит

Удаляет ссылку из `single_link_registry` объекта.

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на удаляемый блок, если он найден.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если ссылка была найдена и удалена, **`false`** в противном случае.

## <a name="single_link_registry"></a><a name="ctor"></a>single_link_registry

Формирует объект `single_link_registry`.

```cpp
single_link_registry();
```

## <a name="single_link_registry"></a><a name="dtor"></a>~ single_link_registry

Уничтожает `single_link_registry` объект.

```cpp
virtual ~single_link_registry();
```

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_operation](invalid-operation-class.md) , если оно вызывается перед удалением ссылки.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс multi_link_registry](multi-link-registry-class.md)
