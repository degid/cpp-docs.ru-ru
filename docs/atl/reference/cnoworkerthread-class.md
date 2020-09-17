---
title: Класс CNoWorkerThread
ms.date: 11/04/2016
f1_keywords:
- CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread::AddHandle
- ATLUTIL/ATL::CNoWorkerThread::AddTimer
- ATLUTIL/ATL::CNoWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CNoWorkerThread::GetThreadId
- ATLUTIL/ATL::CNoWorkerThread::Initialize
- ATLUTIL/ATL::CNoWorkerThread::RemoveHandle
- ATLUTIL/ATL::CNoWorkerThread::Shutdown
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
ms.openlocfilehash: 90056e648a53218ac06083d43ca34870e1ca72fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326711"
---
# <a name="cnoworkerthread-class"></a>Класс CNoWorkerThread

Используйте этот класс в `MonitorClass` качестве аргумента для параметра шаблона для кэша классов, если вы хотите отключить динамическое обслуживание кэша.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CNoWorkerThread
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CNoWorkerThread::AddHandle](#addhandle)|Нефункциональный эквивалент [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).|
|[CNoWorkerThread::AddTimer](#addtimer)|Нефункциональный эквивалент [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).|
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|Нефункциональный эквивалент [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).|
|[CNoWorkerThread::GetThreadId](#getthreadid)|Нефункциональный эквивалент [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|
|[CNoWorkerThread::Первоначальнизировать](#initialize)|Нефункциональный эквивалент [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).|
|[CNoWorkerThread::RemoveHandle](#removehandle)|Нефункциональный эквивалент [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).|
|[CNoWorkerThread::Закрытие](#shutdown)|Нефункциональный эквивалент [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).|

## <a name="remarks"></a>Примечания

Этот класс предоставляет тот же общедоступный интерфейс, что и [CWorkerThread.](../../atl/reference/cworkerthread-class.md) Этот интерфейс, как ожидается, будет предоставлен параметром `MonitorClass` шаблона для кэша классов.

Методы в этом классе реализованы, чтобы ничего не делать. Методы, возвращающие HRESULT, всегда возвращаются S_OK, а методы, возвращающие Идентификатор HANDLE или thread ID, всегда возвращают 0.

## <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="cnoworkerthreadaddhandle"></a><a name="addhandle"></a>CNoWorkerThread::AddHandle

Нефункциональный эквивалент [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

```
HRESULT AddHandle(HANDLE /* hObject */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */) throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается S_OK.

### <a name="remarks"></a>Примечания

Реализация, предоставляемая этим классом, ничего не делает.

## <a name="cnoworkerthreadaddtimer"></a><a name="addtimer"></a>CNoWorkerThread::AddTimer

Нефункциональный эквивалент [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).

```
HRESULT AddTimer(DWORD /* dwInterval */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */,
    HANDLE* /* phTimer */) throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается S_OK.

### <a name="remarks"></a>Примечания

Реализация, предоставляемая этим классом, ничего не делает.

## <a name="cnoworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>CNoWorkerThread::GetThreadHandle

Нефункциональный эквивалент [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение NULL.

### <a name="remarks"></a>Примечания

Реализация, предоставляемая этим классом, ничего не делает.

## <a name="cnoworkerthreadgetthreadid"></a><a name="getthreadid"></a>CNoWorkerThread::GetThreadId

Нефункциональный эквивалент [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 0.

### <a name="remarks"></a>Примечания

Реализация, предоставляемая этим классом, ничего не делает.

## <a name="cnoworkerthreadinitialize"></a><a name="initialize"></a>CNoWorkerThread::Первоначальнизировать

Нефункциональный эквивалент [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).

```
HRESULT Initialize() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается S_OK.

### <a name="remarks"></a>Примечания

Реализация, предоставляемая этим классом, ничего не делает.

## <a name="cnoworkerthreadremovehandle"></a><a name="removehandle"></a>CNoWorkerThread::RemoveHandle

Нефункциональный эквивалент [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).

```
HRESULT RemoveHandle(HANDLE /* hObject */) throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается S_OK.

### <a name="remarks"></a>Примечания

Реализация, предоставляемая этим классом, ничего не делает.

## <a name="cnoworkerthreadshutdown"></a><a name="shutdown"></a>CNoWorkerThread::Закрытие

Нефункциональный эквивалент [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается S_OK.

### <a name="remarks"></a>Примечания

Реализация, предоставляемая этим классом, ничего не делает.
