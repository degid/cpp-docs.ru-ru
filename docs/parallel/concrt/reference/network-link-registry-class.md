---
title: Класс network_link_registry
ms.date: 11/04/2016
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
ms.openlocfilehash: 18fabd0e741c144201f299271cdd01eb9ac55fac
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222684"
---
# <a name="network_link_registry-class"></a>Класс network_link_registry

Абстрактный базовый класс `network_link_registry` управляет связями между блоками источников и целевыми блоками.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _Block>
class network_link_registry;
```

### <a name="parameters"></a>Параметры

*_Block*<br/>
Тип данных блока, хранящийся в `network_link_registry` .

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`const_pointer`|Тип, предоставляющий указатель на **`const`** элемент в `network_link_registry` объекте.|
|`const_reference`|Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в объекте, `network_link_registry` для чтения и выполнения операций const.|
|`iterator`|Тип, предоставляющий итератор, который может считывать или изменять любой элемент в `network_link_registry` объекте.|
|`type`|Тип, представляющий тип блока, хранящегося в `network_link_registry` объекте.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[add](#add)|При переопределении в производном классе добавляет ссылку на `network_link_registry` объект.|
|[begin](#begin)|При переопределении в производном классе возвращает итератор на первый элемент в `network_link_registry` объекте.|
|[contains](#contains)|При переопределении в производном классе ищет `network_link_registry` указанный блок в объекте.|
|[count](#count)|При переопределении в производном классе возвращает число элементов в `network_link_registry` объекте.|
|[remove](#remove)|При переопределении в производном классе удаляет указанный блок из `network_link_registry` объекта.|

## <a name="remarks"></a>Примечания

`network link registry`Не является надежным для параллельного доступа.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`network_link_registry`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="add"></a><a name="add"></a>включить

При переопределении в производном классе добавляет ссылку на `network_link_registry` объект.

```cpp
virtual void add(_EType _Link) = 0;
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на добавляемый блок.

## <a name="begin"></a><a name="begin"></a>начале

При переопределении в производном классе возвращает итератор на первый элемент в `network_link_registry` объекте.

```cpp
virtual iterator begin() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, обращающийся к первому элементу в `network_link_registry` объекте.

### <a name="remarks"></a>Примечания

Конечное состояние итератора обозначается `NULL` ссылкой.

## <a name="contains"></a><a name="contains"></a>содержащих

При переопределении в производном классе ищет `network_link_registry` указанный блок в объекте.

```cpp
virtual bool contains(_EType _Link) = 0;
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок, поиск которого выполняется в `network_link_registry` объекте.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если блок найден; **`false`** в противном случае —.

## <a name="count"></a><a name="count"></a>расчета

При переопределении в производном классе возвращает число элементов в `network_link_registry` объекте.

```cpp
virtual size_t count() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в объекте `network_link_registry`.

## <a name="remove"></a><a name="remove"></a>отменит

При переопределении в производном классе удаляет указанный блок из `network_link_registry` объекта.

```cpp
virtual bool remove(_EType _Link) = 0;
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на удаляемый блок, если он найден.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если ссылка была найдена и удалена, **`false`** в противном случае.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс single_link_registry](single-link-registry-class.md)<br/>
[Класс multi_link_registry](multi-link-registry-class.md)
