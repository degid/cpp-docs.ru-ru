---
title: Класс CNonStatelessWorker
ms.date: 11/04/2016
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
ms.openlocfilehash: 6264bb6bc9070b5ce170b294f9db0d371e7b6b71
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747671"
---
# <a name="cnonstatelessworker-class"></a>Класс CNonStatelessWorker

Получает запросы из пула потоков и передает их объекту рабочего, который создается и уничтожается по каждому запросу.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>Параметры

*Работник*<br/>
Класс рабочего потока, соответствующий [архетипу рабочего,](../../atl/reference/worker-archetype.md) подходящий для обработки запросов в очереди на [CThreadPool.](../../atl/reference/cthreadpool-class.md)

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CNonStatelessWorker::RequestType](#requesttype)|Реализация [WorkerArchetype::RequestType](worker-archetype.md#requesttype).|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CNonStatelessWorker:::Исполнение](#execute)|Реализация [WorkerArchetype::Execute](worker-archetype.md#execute).|
|[CNonStatelessWorker::](#initialize)|Реализация [WorkerArchetype::Первоначальная](worker-archetype.md#initialize).|
|[CNonStatelessWorker::: Прекращение](#terminate)|Реализация [WorkerArchetype::Terminate](worker-archetype.md#terminate).|

## <a name="remarks"></a>Примечания

Этот класс является простой рабочей нитью для использования с [CThreadPool.](../../atl/reference/cthreadpool-class.md) Этот класс не предоставляет каких-либо собственных возможностей обработки запросов. Вместо этого он мгновенно устанавливает один экземпляр *Рабочего* на запрос и делегирует реализацию своих методов в этот экземпляр.

Преимущество этого класса заключается в том, что он обеспечивает удобный способ изменения модели состояния для существующих классов рабочих потоков. `CThreadPool`создаст один рабочий в течение всего срока службы потока, так что если класс рабочего удерживает состояние, он будет удерживать его в нескольких запросах. Просто обернув этот `CNonStatelessWorker` класс в `CThreadPool`шаблон, прежде чем использовать его с, срок службы работника и состояние, которое он держит ограничивается одним запросом.

## <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="cnonstatelessworkerexecute"></a><a name="execute"></a>CNonStatelessWorker:::Исполнение

Реализация [WorkerArchetype::Execute](worker-archetype.md#execute).

```cpp
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>Примечания

Этот метод создает экземпляр класса *«Рабочий»* в стеке и вызывает [инициализацию](worker-archetype.md#initialize) на этом объекте. Если инициализация успешна, этот метод также вызывает [выполнение](worker-archetype.md#execute) и [прекращение](worker-archetype.md#terminate) на одном объекте.

## <a name="cnonstatelessworkerinitialize"></a><a name="initialize"></a>CNonStatelessWorker::

Реализация [WorkerArchetype::Первоначальная](worker-archetype.md#initialize).

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается TRUE.

### <a name="remarks"></a>Примечания

Этот класс не делает никакой инициализации в `Initialize`.

## <a name="cnonstatelessworkerrequesttype"></a><a name="requesttype"></a>CNonStatelessWorker::RequestType

Реализация [WorkerArchetype::RequestType](worker-archetype.md#requesttype).

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>Примечания

Этот класс обрабатывает тот же тип рабочего элемента, что и класс, используемый для параметра *шаблона «Рабочий».* Подробнее о ней читайте [в обзоре CNonStatelessWorker.](../../atl/reference/cnonstatelessworker-class.md)

## <a name="cnonstatelessworkerterminate"></a><a name="terminate"></a>CNonStatelessWorker::: Прекращение

Реализация [WorkerArchetype::Terminate](worker-archetype.md#terminate).

```cpp
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>Примечания

Этот класс не делает никакой очистки в `Terminate`.

## <a name="see-also"></a>См. также раздел

[Класс CThreadPool](../../atl/reference/cthreadpool-class.md)<br/>
[Рабочий архетип](../../atl/reference/worker-archetype.md)<br/>
[Классы](../../atl/reference/atl-classes.md)
