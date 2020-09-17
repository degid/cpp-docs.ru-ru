---
title: Структура IResourceManager
ms.date: 03/27/2019
f1_keywords:
- IResourceManager
- CONCRTRM/concurrency::IResourceManager
- CONCRTRM/concurrency::IResourceManager::IResourceManager::OSVersion
- CONCRTRM/concurrency::IResourceManager::IResourceManager::CreateNodeTopology
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetAvailableNodeCount
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetFirstNode
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Reference
- CONCRTRM/concurrency::IResourceManager::IResourceManager::RegisterScheduler
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Release
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
ms.openlocfilehash: 15e27a586fc039791255c01a053f6a1109183f90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368187"
---
# <a name="iresourcemanager-structure"></a>Структура IResourceManager

Интерфейс для диспетчера ресурсов среды выполнения с параллелизмом. Это интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов.

## <a name="syntax"></a>Синтаксис

```cpp
struct IResourceManager;
```

## <a name="members"></a>Участники

### <a name="public-enumerations"></a>Открытые перечисления

|Имя|Описание|
|----------|-----------------|
|[IResourceManager::: Ведомости](#osversion)|Перечислимый тип, представляющий версию операционной системы.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IResourceManager::CreateNodeTopology](#createnodetopology)|Присутствующий только в отладке сборки времени выполнения, этот метод является тестовый крюк, предназначенный для облегчения тестирования менеджера ресурсов на различных аппаратных топологий, не требуя фактического оборудования, соответствующего конфигурации. При сборке розничной торговли времен выполнения этот метод возвращается без выполнения каких-либо действий.|
|[IResourceManager::GetAvailableNodeCount](#getavailablenodecount)|Возвращает количество узлов, доступных диспетчеру ресурсов.|
|[IResourceManager::GetFirstNode](#getfirstnode)|Возвращает первый узел в порядке перечисления, определенном диспетчером ресурсов.|
|[IResourceManager::Ссылка](#reference)|Приращения, отсылки, учитываются в экземпляре «Менеджер ресурсов».|
|[IResourceManager::RegisterScheduler](#registerscheduler)|Регистрирует планировщик с менеджером ресурсов. После регистрации планировщика он должен общаться с `ISchedulerProxy` менеджером ресурсов с помощью возвращенного интерфейса.|
|[IResourceManager::Release](#release)|Декреты эталона учитываются в экземпляре ресурсного менеджера. Менеджер ресурсов уничтожается, когда `0`его количество ссылок идет на .|

## <a name="remarks"></a>Примечания

Используйте функцию [CreateResourceManager](concurrency-namespace-functions.md) для получения интерфейса в экземпляре Singleton Resource Manager. Метод приравнирует ссылку на менеджера ресурсов, и вы должны вызвать [IResourceManager::Release](#release) метод для освобождения ссылки, когда вы сделали с менеджером ресурсов. Как правило, каждый планировщик, который вы создаете, вызывает этот метод во время создания и выпускает ссылку на диспетчера ресурсов после его выключения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IResourceManager`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Название:** параллелизм

## <a name="iresourcemanagercreatenodetopology-method"></a><a name="createnodetopology"></a>IResourceManager::СоздатьМетодНотопологии

Присутствующий только в отладке сборки времени выполнения, этот метод является тестовый крюк, предназначенный для облегчения тестирования менеджера ресурсов на различных аппаратных топологий, не требуя фактического оборудования, соответствующего конфигурации. При сборке розничной торговли времен выполнения этот метод возвращается без выполнения каких-либо действий.

```cpp
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```

### <a name="parameters"></a>Параметры

*nodeCount*<br/>
Количество имитируемых узлов процессора.

*pCoreCount*<br/>
Массив, который определяет количество ядер на каждом узлах.

*pNodeDistance*<br/>
Матрица, определяющая расстояние узлов между любыми двумя узлами. Этот параметр может `NULL`иметь значение.

*pProcessorGroups*<br/>
Массив, который определяет группу процессоров, к которой принадлежит каждый узлы.

### <a name="remarks"></a>Примечания

[invalid_argument](../../../standard-library/invalid-argument-class.md) брошен, если `nodeCount` параметр `0` имеет значение было передано в, или если параметр `pCoreCount` имеет значение. `NULL`

[invalid_operation](invalid-operation-class.md) брошен, если этот метод называется в то время как другие планировщики существуют в процессе.

## <a name="iresourcemanagergetavailablenodecount-method"></a><a name="getavailablenodecount"></a>IResourceManager::GetAvailableNodeCount Метод

Возвращает количество узлов, доступных диспетчеру ресурсов.

```cpp
virtual unsigned int GetAvailableNodeCount() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Количество узлов, доступных диспетчеру ресурсов.

## <a name="iresourcemanagergetfirstnode-method"></a><a name="getfirstnode"></a>IResourceManager::GetFirstNode Метод

Возвращает первый узел в порядке перечисления, определенном диспетчером ресурсов.

```cpp
virtual ITopologyNode* GetFirstNode() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Первый узла в порядке перечисления, определяемом менеджером ресурсов.

## <a name="iresourcemanagerosversion-enumeration"></a><a name="osversion"></a>IResourceManager::OSVersion Enumeration

Перечислимый тип, представляющий версию операционной системы.

```cpp
enum OSVersion;
```

## <a name="iresourcemanagerreference-method"></a><a name="reference"></a>IResourceManager::Справочный метод

Приращения, отсылки, учитываются в экземпляре «Менеджер ресурсов».

```cpp
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

В результате отсчет ссылок.

## <a name="iresourcemanagerregisterscheduler-method"></a><a name="registerscheduler"></a>IResourceManager::RegisterScheduler Метод

Регистрирует планировщик с менеджером ресурсов. После регистрации планировщика он должен общаться с `ISchedulerProxy` менеджером ресурсов с помощью возвращенного интерфейса.

```cpp
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```

### <a name="parameters"></a>Параметры

*pПланировщик*<br/>
Интерфейс `IScheduler` для регистрации планировщика.

*version*<br/>
Версия интерфейса связи, используемая планировщиком для связи с менеджером ресурсов. Использование версии позволяет диспетчеру ресурсов развивать интерфейс связи, позволяя планировщикам получить доступ к старым функциям. Планировщики, которые хотят использовать функции Resource Manager, присутствующие `CONCRT_RM_VERSION_1`в Visual Studio 2010, должны использовать версию.

### <a name="return-value"></a>Возвращаемое значение

Интерфейс, `ISchedulerProxy` связанный диспетчером ресурсов с планировщиком. Ваш планировщик должен использовать этот интерфейс для связи с менеджером ресурсов с этого момента.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы начать общение с менеджером ресурсов. Метод связывает `IScheduler` интерфейс для планировщика с `ISchedulerProxy` интерфейсом и передает его обратно к вам. Вы можете использовать возвращенный интерфейс для запроса ресурсов выполнения для использования планировщиком или для подписки на потоки с менеджером ресурсов. Диспетчер ресурсов будет использовать элементы политики из политики планировщика, возвращенные [методом IScheduler::GetPolicy,](ischeduler-structure.md#getpolicy) чтобы определить, какой тип потоков потребуется планировщику для выполнения работы. Если `SchedulerKind` ключ политики `UmsThreadDefault` имеет значение, а значение считывается `IScheduler` обратно из политики, `IUMSScheduler` поскольку значение, `UmsThreadDefault`интерфейс, передаваемый методу, должен быть интерфейсом.

Метод выбрасывает `invalid_argument` исключение, если `pScheduler` параметр `NULL` имеет значение `version` или если параметр не является действительной версией для интерфейса связи.

## <a name="iresourcemanagerrelease-method"></a><a name="release"></a>IResourceManager::Метод выпуска

Декреты эталона учитываются в экземпляре ресурсного менеджера. Менеджер ресурсов уничтожается, когда `0`его количество ссылок идет на .

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

В результате отсчет ссылок.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура ISchedulerProxy](ischedulerproxy-structure.md)<br/>
[Структура IScheduler](ischeduler-structure.md)
