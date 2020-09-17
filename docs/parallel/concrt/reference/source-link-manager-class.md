---
title: Класс source_link_manager
ms.date: 11/04/2016
f1_keywords:
- source_link_manager
- AGENTS/concurrency::source_link_manager
- AGENTS/concurrency::source_link_manager::source_link_manager
- AGENTS/concurrency::source_link_manager::add
- AGENTS/concurrency::source_link_manager::begin
- AGENTS/concurrency::source_link_manager::contains
- AGENTS/concurrency::source_link_manager::count
- AGENTS/concurrency::source_link_manager::reference
- AGENTS/concurrency::source_link_manager::register_target_block
- AGENTS/concurrency::source_link_manager::release
- AGENTS/concurrency::source_link_manager::remove
- AGENTS/concurrency::source_link_manager::set_bound
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
ms.openlocfilehash: 98f99bb5aec85a640eaf83a07fae3a1b667f7d91
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228431"
---
# <a name="source_link_manager-class"></a>Класс source_link_manager

Объект `source_link_manager` управляет сетевыми соединениями блоков обмена сообщениями с блоками `ISource`.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _LinkRegistry>
class source_link_manager;
```

### <a name="parameters"></a>Параметры

*_LinkRegistry*<br/>
Реестр сетевых связей.

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`const_pointer`|Тип, предоставляющий указатель на **`const`** элемент в `source_link_manager` объекте.|
|`const_reference`|Тип, предоставляющий ссылку на **`const`** элемент, хранящийся в объекте, `source_link_manager` для чтения и выполнения операций const.|
|`iterator`|Тип, предоставляющий итератор, который может считывать или изменять любой элемент в `source_link_manager` объекте.|
|`type`|Тип реестра ссылок, управляемый `source_link_manager` объектом.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[source_link_manager](#ctor)|Формирует объект `source_link_manager`.|
|[Деструктор ~ source_link_manager](#dtor)|Уничтожает `source_link_manager` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[add](#add)|Добавляет ссылку на объект в качестве источника `source_link_manager` .|
|[begin](#begin)|Возвращает итератор на первый элемент в `source_link_manager` объекте.|
|[contains](#contains)|Выполняет поиск `network_link_registry` `source_link_manager` указанного блока в этом объекте.|
|[count](#count)|Подсчитывает количество связанных блоков в `source_link_manager` объекте.|
|[reference](#reference)|Получает ссылку на `source_link_manager` объект.|
|[register_target_block](#register_target_block)|Регистрирует целевой блок, содержащий этот `source_link_manager` объект.|
|[отпускании](#release)|Освобождает ссылку на `source_link_manager` объект.|
|[remove](#remove)|Удаляет ссылку из `source_link_manager` объекта.|
|[set_bound](#set_bound)|Задает максимальное число ссылок на источники, которые могут быть добавлены к этому `source_link_manager` объекту.|

## <a name="remarks"></a>Примечания

Сейчас блоки исходного кода подсчитываются. Это оболочка для `network_link_registry` объекта, который разрешает одновременный доступ к ссылкам и предоставляет возможность ссылаться на ссылки через обратные вызовы. Блоки сообщений `target_block` `propagator_block` должны использовать этот класс для ссылок на исходные элементы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`source_link_manager`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="add"></a><a name="add"></a>включить

Добавляет ссылку на объект в качестве источника `source_link_manager` .

```cpp
void add(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на добавляемый блок.

## <a name="begin"></a><a name="begin"></a>начале

Возвращает итератор на первый элемент в `source_link_manager` объекте.

```cpp
iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, обращающийся к первому элементу в `source_link_manager` объекте.

### <a name="remarks"></a>Примечания

Конечное состояние итератора обозначается `NULL` ссылкой.

## <a name="contains"></a><a name="contains"></a>содержащих

Выполняет поиск `network_link_registry` `source_link_manager` указанного блока в этом объекте.

```cpp
bool contains(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок, который необходимо найти в `source_link_manager` объекте.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если указанный блок найден; **`false`** в противном случае —.

## <a name="count"></a><a name="count"></a>расчета

Подсчитывает количество связанных блоков в `source_link_manager` объекте.

```cpp
size_t count();
```

### <a name="return-value"></a>Возвращаемое значение

Число связанных блоков в `source_link_manager` объекте.

## <a name="reference"></a><a name="reference"></a>IsReference

Получает ссылку на `source_link_manager` объект.

```cpp
void reference();
```

## <a name="register_target_block"></a><a name="register_target_block"></a>register_target_block

Регистрирует целевой блок, содержащий этот `source_link_manager` объект.

```cpp
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Целевой блок, содержащий этот `source_link_manager` объект.

## <a name="release"></a><a name="release"></a>отпускании

Освобождает ссылку на `source_link_manager` объект.

```cpp
void release();
```

## <a name="remove"></a><a name="remove"></a>отменит

Удаляет ссылку из `source_link_manager` объекта.

```cpp
bool remove(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на удаляемый блок, если он найден.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если ссылка была найдена и удалена, **`false`** в противном случае.

## <a name="set_bound"></a><a name="set_bound"></a>set_bound

Задает максимальное число ссылок на источники, которые могут быть добавлены к этому `source_link_manager` объекту.

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Параметры

*_MaxLinks*<br/>
Максимальное число ссылок.

## <a name="source_link_manager"></a><a name="ctor"></a>source_link_manager

Формирует объект `source_link_manager`.

```cpp
source_link_manager();
```

## <a name="source_link_manager"></a><a name="dtor"></a>~ source_link_manager

Уничтожает `source_link_manager` объект.

```cpp
~source_link_manager();
```

## <a name="see-also"></a>См. также статью

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс single_link_registry](single-link-registry-class.md)<br/>
[Класс multi_link_registry](multi-link-registry-class.md)
