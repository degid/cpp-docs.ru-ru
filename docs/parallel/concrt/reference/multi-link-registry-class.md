---
title: Класс multi_link_registry
ms.date: 11/04/2016
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
ms.openlocfilehash: 777b3f5206b4a595b5dcac653d608255e92f4ef6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231706"
---
# <a name="multi_link_registry-class"></a>Класс multi_link_registry

Объект `multi_link_registry` представляет собой `network_link_registry`, управляющий несколькими блоками источников или целевыми блоками.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>Параметры

*_Block*<br/>
Тип данных блока, хранящийся в `multi_link_registry` объекте.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[multi_link_registry](#ctor)|Формирует объект `multi_link_registry`.|
|[Деструктор ~ multi_link_registry](#dtor)|Уничтожает `multi_link_registry` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[add](#add)|Добавляет ссылку на `multi_link_registry` объект. (Переопределяет [network_link_registry:: Add](network-link-registry-class.md#add).)|
|[begin](#begin)|Возвращает итератор на первый элемент в `multi_link_registry` объекте. (Переопределяет [network_link_registry:: Begin](network-link-registry-class.md#begin).)|
|[contains](#contains)|Выполняет поиск `multi_link_registry` указанного блока в объекте. (Переопределяет [network_link_registry:: Contains](network-link-registry-class.md#contains).)|
|[count](#count)|Подсчитывает количество элементов в `multi_link_registry` объекте. (Переопределяет [network_link_registry:: count](network-link-registry-class.md#count).)|
|[remove](#remove)|Удаляет ссылку из `multi_link_registry` объекта. (Переопределяет [network_link_registry::Remove](network-link-registry-class.md#remove).)|
|[set_bound](#set_bound)|Задает верхнюю границу числа ссылок, которые `multi_link_registry` может содержать объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[network_link_registry](network-link-registry-class.md)

`multi_link_registry`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="add"></a><a name="add"></a>включить

Добавляет ссылку на `multi_link_registry` объект.

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на добавляемый блок.

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_link_target](invalid-link-target-class.md) , если ссылка уже имеется в реестре, или если привязка уже была задана с помощью `set_bound` функции и связь была удалена.

## <a name="begin"></a><a name="begin"></a>начале

Возвращает итератор на первый элемент в `multi_link_registry` объекте.

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, обращающийся к первому элементу в `multi_link_registry` объекте.

### <a name="remarks"></a>Примечания

Конечное состояние обозначается `NULL` ссылкой.

## <a name="contains"></a><a name="contains"></a>содержащих

Выполняет поиск `multi_link_registry` указанного блока в объекте.

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок, который необходимо найти в `multi_link_registry` объекте.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если указанный блок найден; **`false`** в противном случае —.

## <a name="count"></a><a name="count"></a>расчета

Подсчитывает количество элементов в `multi_link_registry` объекте.

```cpp
virtual size_t count();
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в объекте `multi_link_registry`.

## <a name="multi_link_registry"></a><a name="ctor"></a>multi_link_registry

Формирует объект `multi_link_registry`.

```cpp
multi_link_registry();
```

## <a name="multi_link_registry"></a><a name="dtor"></a>~ multi_link_registry

Уничтожает `multi_link_registry` объект.

```cpp
virtual ~multi_link_registry();
```

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_operation](invalid-operation-class.md) , если вызывается до удаления всех ссылок.

## <a name="remove"></a><a name="remove"></a>отменит

Удаляет ссылку из `multi_link_registry` объекта.

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на удаляемый блок, если он найден.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если ссылка была найдена и удалена, **`false`** в противном случае.

## <a name="set_bound"></a><a name="set_bound"></a>set_bound

Задает верхнюю границу числа ссылок, которые `multi_link_registry` может содержать объект.

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Параметры

*_MaxLinks*<br/>
Максимальное число ссылок, которые `multi_link_registry` может содержать объект.

### <a name="remarks"></a>Примечания

После установки границы отсоединение записи приведет к тому, что объект `multi_link_registry` войдет в неизменяемое состояние, где дальнейшие вызовы `add` создадут исключение `invalid_link_target`.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс single_link_registry](single-link-registry-class.md)
