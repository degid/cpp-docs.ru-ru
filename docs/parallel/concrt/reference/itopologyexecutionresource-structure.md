---
title: Структура ITopologyExecutionResource
ms.date: 11/04/2016
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
ms.openlocfilehash: 2c9221cab1ac2d48bd099a769188e4bee797823c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368149"
---
# <a name="itopologyexecutionresource-structure"></a>Структура ITopologyExecutionResource

Интерфейс для ресурса выполнения, как определено диспетчером ресурсов.

## <a name="syntax"></a>Синтаксис

```cpp
struct ITopologyExecutionResource;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ITopologyExecutionРесурс::: Газета.](#getid)|Возвращает уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.|
|[ITopologyExecutionРесурс::: GetNext](#getnext)|Возвращает интерфейс для следующего ресурса выполнения в порядке перечисления.|

## <a name="remarks"></a>Примечания

Этот интерфейс обычно используется для ходьбы по топологии системы, наблюдаемой диспетчером ресурсов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ITopologyExecutionResource`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Название:** параллелизм

## <a name="itopologyexecutionresourcegetid-method"></a><a name="getid"></a>ITopologyExecutionРесурс::GetId Метод

Возвращает уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.

## <a name="itopologyexecutionresourcegetnext-method"></a><a name="getnext"></a>ITopologyExecutionРесурс::GetNext Метод

Возвращает интерфейс для следующего ресурса выполнения в порядке перечисления.

```cpp
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс для следующего ресурса выполнения в порядке перечисления. Если больше нет узлов в порядке перечисления узла, которому принадлежит этот ресурс выполнения, этот метод возвращает значение `NULL`.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
