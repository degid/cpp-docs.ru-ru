---
title: Класс static_partitioner
ms.date: 11/04/2016
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
ms.openlocfilehash: 7a58daa27bc7a2f51f78a3068a2f152979ffdd72
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142683"
---
# <a name="static_partitioner-class"></a>Класс static_partitioner

Класс `static_partitioner` представляет статическое разделение диапазона, в котором итерации выполняются с помощью `parallel_for`. Модуль разделения разделяет диапазон на количество фрагментов, доступных для базового планировщика.

## <a name="syntax"></a>Синтаксис

```cpp
class static_partitioner;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[static_partitioner](#ctor)|Формирует объект `static_partitioner`.|
|[Деструктор ~ static_partitioner](#dtor)|Уничтожает объект `static_partitioner`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`static_partitioner`

## <a name="requirements"></a>Требования

**Заголовок:** PPL.h

**Пространство имен:** concurrency

## <a name="dtor"></a>~ static_partitioner

Уничтожает объект `static_partitioner`.

```cpp
~static_partitioner();
```

## <a name="ctor"></a>static_partitioner

Формирует объект `static_partitioner`.

```cpp
static_partitioner();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
