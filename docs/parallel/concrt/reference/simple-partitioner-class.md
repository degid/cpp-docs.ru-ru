---
title: Класс simple_partitioner
ms.date: 11/04/2016
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
ms.openlocfilehash: 503f36b90c5eb3319f9aa2d56528172ffa95bb11
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142500"
---
# <a name="simple_partitioner-class"></a>Класс simple_partitioner

Класс `simple_partitioner` представляет статическое разделение диапазона, в котором итерации выполняются с помощью `parallel_for`. Разделитель делит диапазон на фрагменты таким образом, что каждый фрагмент имеет число итераций не менее указанного размера фрагмента.

## <a name="syntax"></a>Синтаксис

```cpp
class simple_partitioner;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[simple_partitioner](#ctor)|Формирует объект `simple_partitioner`.|
|[Деструктор ~ simple_partitioner](#dtor)|Уничтожает объект `simple_partitioner`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`simple_partitioner`

## <a name="requirements"></a>Требования

**Заголовок:** PPL.h

**Пространство имен:** concurrency

## <a name="dtor"></a>~ simple_partitioner

Уничтожает объект `simple_partitioner`.

```cpp
~simple_partitioner();
```

## <a name="ctor"></a>simple_partitioner

Формирует объект `simple_partitioner`.

```cpp
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>Параметры

*_Chunk_size*<br/>
Минимальный размер раздела.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
