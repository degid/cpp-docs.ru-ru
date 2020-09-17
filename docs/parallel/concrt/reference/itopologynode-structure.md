---
title: Структура ITopologyNode
ms.date: 11/04/2016
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
ms.openlocfilehash: 7cb815c4f7dc5ad09e8d352abc3f3375b8d9e205
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368106"
---
# <a name="itopologynode-structure"></a>Структура ITopologyNode

Интерфейс для узла топологии, как определено диспетчером ресурсов. Узел содержит один или несколько ресурсов выполнения.

## <a name="syntax"></a>Синтаксис

```cpp
struct ITopologyNode;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ITopologyNode::GetExecutionResourceCount](#getexecutionresourcecount)|Возвращает количество ресурсов выполнения, сгруппированных в этом узле.|
|[ITopologyNode::GetFirstExecutionРесурс](#getfirstexecutionresource)|Возвращает первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.|
|[ITopologyNode::GetId](#getid)|Возвращает уникальный идентификатор менеджера ресурсов для этого узла.|
|[ITopologyNode::GetNext](#getnext)|Возвращает интерфейс следующего узла топологии в порядке перечисления.|
|[ITopologyNode::GetNumaNode](#getnumanode)|Возвращает назначенный Windows номер узла NUMA, к которому принадлежит этот узло Ресурс Maanger.|

## <a name="remarks"></a>Примечания

Этот интерфейс обычно используется для ходьбы по топологии системы, наблюдаемой диспетчером ресурсов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ITopologyNode`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Название:** параллелизм

## <a name="itopologynodegetexecutionresourcecount-method"></a><a name="getexecutionresourcecount"></a>ITopologyNode::GetExecutionResourceCount Метод

Возвращает количество ресурсов выполнения, сгруппированных в этом узле.

```cpp
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Количество ресурсов выполнения, сгруппированных в этом узле.

## <a name="itopologynodegetfirstexecutionresource-method"></a><a name="getfirstexecutionresource"></a>ITopologyNode::GetFirstExecutionResource Метод

Возвращает первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.

```cpp
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.

## <a name="itopologynodegetid-method"></a><a name="getid"></a>ITopologyNode::GetId Метод

Возвращает уникальный идентификатор менеджера ресурсов для этого узла.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор менеджера ресурсов для этого узла.

### <a name="remarks"></a>Примечания

Concurrency Runtime представляет аппаратные потоки в системе в группах узлов процессоров. Узлы обычно получаются из аппаратной топологии системы. Например, все процессоры на определенном гнезде или определенном узлах NUMA могут принадлежать к одному и тому же узлам процессора. Диспетчер ресурсов присваивает эти узлы `0` уникальным идентификаторам, начиная с до и включая, `nodeCount - 1`где `nodeCount` представлено общее количество узлов процессора в системе.

Количество узлов можно получить из функции [GetProcessorNodeCount.](concurrency-namespace-functions.md)

## <a name="itopologynodegetnext-method"></a><a name="getnext"></a>ITopologyNode::GetNext Метод

Возвращает интерфейс следующего узла топологии в порядке перечисления.

```cpp
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс следующего узла в порядке перечисления. Если в порядке перечисления топологии системы больше нет узлов, этот метод возвращает значение `NULL`.

## <a name="itopologynodegetnumanode-method"></a><a name="getnumanode"></a>ITopologyNode::GetNumaNode Метод

Возвращает назначенный Windows номер узла NUMA, к которому принадлежит этот узло Ресурс Maanger.

```cpp
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Windows присвоила номер узла NUMA, к которому принадлежит этот узла диспетчера ресурсов.

### <a name="remarks"></a>Примечания

Прокси-сервер потока, работающий на корне виртуального процессора, принадлежащем этому узлам, будет иметь сродство, по крайней мере, к уровню узла NUMA для узла NUMA, возвращенного этим методом.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
