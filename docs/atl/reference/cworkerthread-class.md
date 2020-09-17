---
title: Класс CWorkerThread
ms.date: 11/04/2016
f1_keywords:
- CWorkerThread
- ATLUTIL/ATL::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::AddHandle
- ATLUTIL/ATL::CWorkerThread::AddTimer
- ATLUTIL/ATL::CWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CWorkerThread::GetThreadId
- ATLUTIL/ATL::CWorkerThread::Initialize
- ATLUTIL/ATL::CWorkerThread::RemoveHandle
- ATLUTIL/ATL::CWorkerThread::Shutdown
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
ms.openlocfilehash: 05e6b432d44927fa7e276792643e29c80c42d822
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330212"
---
# <a name="cworkerthread-class"></a>Класс CWorkerThread

Этот класс создает рабочую нить или использует существующий, ждет на одной или нескольких ручках объекта ядра и выполняет заданную функцию клиента при сигнализации одной из ручек.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class ThreadTraits = DefaultThreadTraits>
class CWorkerThread
```

### <a name="parameters"></a>Параметры

*ThreadTraits*<br/>
Класс, обеспечивающий функцию создания потоков, такие как [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) или [Win32ThreadTraits.](../../atl/reference/win32threadtraits-class.md)

## <a name="members"></a>Участники

### <a name="protected-structures"></a>Защищенные структуры

|Имя|Описание|
|----------|-----------------|
|`WorkerClientEntry`||

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWorkerThread::WorkerThread](#cworkerthread)|Конструктор для рабочего потока.|
|[CWorkerThread:::](#dtor)|Деструктор для рабочего потока.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWorkerThread::AddHandle](#addhandle)|Вызовите этот метод, чтобы добавить ручку ожидающего объекта в список, поддерживаемый потоком рабочего.|
|[CWorkerThread:AddTimer](#addtimer)|Вызовите этот метод, чтобы добавить периодический таймер ожидания в список, поддерживаемый потоком рабочего.|
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|Вызовите этот метод, чтобы получить ручку потока рабочего потока.|
|[CWorkerThread::GetThreadId](#getthreadid)|Вызовите этот метод, чтобы получить идентификатор потока рабочего потока.|
|[CWorkerThread::Initialize](#initialize)|Вызовите этот метод, чтобы инициализировать рабочий поток.|
|[CWorkerThread::RemoveHandle](#removehandle)|Вызовите этот метод, чтобы удалить ручку из списка ожидающих объектов.|
|[CWorkerThread::Shutdown](#shutdown)|Вызовите этот метод, чтобы закрыть рабочую нить.|

## <a name="remarks"></a>Примечания

### <a name="to-use-cworkerthread"></a>Использовать CWorkerThread

1. Создайте экземпляр этого класса.

1. Позвоните [CWorkerThread::Initialize](#initialize).

1. Позвоните [CWorkerThread::AddHandle](#addhandle) с ручкой объекта ядра и указателем на реализацию [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).

   \- или -

   Позвоните [CWorkerThread::AddTimer](#addtimer) с указателем на реализацию [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).

1. Реализация [IWorkerThreadClient::Выполните,](../../atl/reference/iworkerthreadclient-interface.md#execute) чтобы предпринять некоторые действия, когда ручка или таймер сигнализируется.

1. Чтобы удалить объект из списка ожидающих объектов, позвоните [cWorkerThread::RemoveHandle](#removehandle).

1. Чтобы завершить работу потока, позвоните [cWorkerThread::Shutdown](#shutdown).

## <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="cworkerthreadaddhandle"></a><a name="addhandle"></a>CWorkerThread::AddHandle

Вызовите этот метод, чтобы добавить ручку ожидающего объекта в список, поддерживаемый потоком рабочего.

```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Ручка к ожидаемируемому объекту.

*pClient*<br/>
Указатель на интерфейс [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) на объекте, который будет вызываться при сигнале рукоятки.

*dwParam*<br/>
Параметр, который будет передан [IWorkerThreadClient::Выполнение,](../../atl/reference/iworkerthreadclient-interface.md#execute) когда ручка сигнализируется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

[IWorkerThreadClient::Выполнение](../../atl/reference/iworkerthreadclient-interface.md#execute) будет вызвано через *pClient* когда ручка, *hObject*, сигнализирована.

## <a name="cworkerthreadaddtimer"></a><a name="addtimer"></a>CWorkerThread:AddTimer

Вызовите этот метод, чтобы добавить периодический таймер ожидания в список, поддерживаемый потоком рабочего.

```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```

### <a name="parameters"></a>Параметры

*dwInterval*<br/>
Определяет период таймера в миллисекундах.

*pClient*<br/>
Указатель на интерфейс [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) на объекте, который будет вызываться при сигнале рукоятки.

*dwParam*<br/>
Параметр, который будет передан [IWorkerThreadClient::Выполнение,](../../atl/reference/iworkerthreadclient-interface.md#execute) когда ручка сигнализируется.

*phTimer*<br/>
(ваут) Адрес переменной HANDLE, которая, по успеху, получает ручку к вновь созданному таймеру.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

[IWorkerThreadClient::Выполнение](../../atl/reference/iworkerthreadclient-interface.md#execute) будет вызвано через *pClient* когда таймер сигнализируется.

Передайте ручку таймерота от *phTimer* к [CWorkerThread::RemoveHandle,](#removehandle) чтобы закрыть таймер.

## <a name="cworkerthreadcworkerthread"></a><a name="cworkerthread"></a>CWorkerThread::WorkerThread

Конструктор.

```
CWorkerThread() throw();
```

## <a name="cworkerthreadcworkerthread"></a><a name="dtor"></a>CWorkerThread:::

Деструктор

```
~CWorkerThread() throw();
```

### <a name="remarks"></a>Примечания

Вызовы [CWorkerThread::Закрытие](#shutdown).

## <a name="cworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>CWorkerThread::GetThreadHandle

Вызовите этот метод, чтобы получить ручку потока рабочего потока.

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку потока или NULL, если рабочая нить не была инициализирована.

## <a name="cworkerthreadgetthreadid"></a><a name="getthreadid"></a>CWorkerThread::GetThreadId

Вызовите этот метод, чтобы получить идентификатор потока рабочего потока.

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает идентификатор потока или NULL, если рабочая нить не была инициализирована.

## <a name="cworkerthreadinitialize"></a><a name="initialize"></a>CWorkerThread::Initialize

Вызовите этот метод, чтобы инициализировать рабочий поток.

```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```

### <a name="parameters"></a>Параметры

*pThread*<br/>
Существующий поток рабочего.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Этот метод следует вызывать для инициализации объекта после создания или после вызова [CWorkerThread::Shutdown](#shutdown).

Чтобы иметь два `CWorkerThread` или более объектов, используйте один и тот же поток рабочего, инициализируем один из них, не проходя никаких аргументов, а затем передайте указатель этому объекту `Initialize` методам других. Объекты, инициализированные с помощью указателя, должны быть закрыты до того, как объект будет использоваться для их инициализации.

Смотрите [CWorkerThread::Shutdown](#shutdown) для получения информации о том, как поведение этого метода меняется при инициализации с помощью указателя на существующий объект.

## <a name="cworkerthreadremovehandle"></a><a name="removehandle"></a>CWorkerThread::RemoveHandle

Вызовите этот метод, чтобы удалить ручку из списка ожидающих объектов.

```
HRESULT RemoveHandle(HANDLE hObject) throw();
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Ручка для удаления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

При удалении ручки [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) будет вызван на связанный объект, который был передан [AddHandle](#addhandle). Если этот вызов `CWorkerThread` не удается, вызов функции Windows [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) на ручке.

## <a name="cworkerthreadshutdown"></a><a name="shutdown"></a>CWorkerThread::Shutdown

Вызовите этот метод, чтобы закрыть рабочую нить.

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="parameters"></a>Параметры

*dwWait*<br/>
Время в миллисекундах ждать выключения рабочего потока. ATL_WORKER_THREAD_WAIT по умолчанию до 10 секунд. При необходимости вы можете определить свое собственное значение для этого символа, прежде чем включить atlutil.h.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT при сбое, например, если значение *тайм-аута, dwWait*, превышен.

### <a name="remarks"></a>Примечания

Чтобы повторно использовать объект, позвоните [CWorkerThread:: Инициализация](#initialize) после вызова этого метода.

Обратите внимание, что вызов `Shutdown` объекта, инициализированного с помощью указателя на другой `CWorkerThread` объект, не имеет эффекта и всегда возвращается S_OK.

## <a name="see-also"></a>См. также раздел

[DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)<br/>
[Классы](../../atl/reference/atl-classes.md)<br/>
[Многопоточность. Создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md)<br/>
[Интерфейс IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)
