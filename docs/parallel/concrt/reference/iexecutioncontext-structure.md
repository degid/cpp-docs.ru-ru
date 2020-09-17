---
title: Структура IExecutionContext
ms.date: 11/04/2016
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
ms.openlocfilehash: 532247ca1776452ad32476d2bcdfafcee3481058
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358793"
---
# <a name="iexecutioncontext-structure"></a>Структура IExecutionContext

Интерфейс для контекста выполнения, который может выполняться на данном виртуальном процессоре и к которому может применяться совместное переключение контекста.

## <a name="syntax"></a>Синтаксис

```cpp
struct IExecutionContext;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IExecutionКонтекст::Dispatch](#dispatch)|Метод, который вызывается при запуске прокси потока, выполнения определенного контекста выполнения. Это должно быть основным работником рутины для вашего планировщика.|
|[IExecutionКонтекст::GetId](#getid)|Возвращает уникальный идентификатор для контекста выполнения.|
|[IExecutionКонтекст::GetProxy](#getproxy)|Возвращает интерфейс в прокси-сервер потока, который выполняет этот контекст.|
|[IExecutionКонтекст::GetScheduler](#getscheduler)|Возвращает интерфейс планировщику, к которой принадлежит этот контекст выполнения.|
|[IExecutionКонтекст::SetProxy](#setproxy)|Связывает прокси-сервер потока с этим контекстом выполнения. Связанный прокси потока вызывает этот метод прямо перед тем, как `Dispatch` он начнет выполнение метода контекста.|

## <a name="remarks"></a>Примечания

Если вы внедряете пользовательский планировщик, который взаимодействует с менеджером ресурсов `IExecutionContext` Concurrency Runtime, вам необходимо реализовать интерфейс. Потоки, созданные диспетчером ресурсов, выполняют работу от имени планировщика, выполняя `IExecutionContext::Dispatch` метод.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IExecutionContext`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Название:** параллелизм

## <a name="iexecutioncontextdispatch-method"></a><a name="dispatch"></a>IExecutionКонтекст::Dметодиспатч

Метод, который вызывается при запуске прокси потока, выполнения определенного контекста выполнения. Это должно быть основным работником рутины для вашего планировщика.

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>Параметры

*pDispatchState*<br/>
Указатель на состояние, под которым отправляется этот контекст выполнения. Для получения дополнительной информации о состоянии отправки [см.](dispatchstate-structure.md)

## <a name="iexecutioncontextgetid-method"></a><a name="getid"></a>IExecutionКонтекст::GetId Метод

Возвращает уникальный идентификатор для контекста выполнения.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор несбыванного.

### <a name="remarks"></a>Примечания

Метод следует использовать `GetExecutionContextId` для получения уникального идентификатора для объекта, реализующего `IExecutionContext` интерфейс, прежде чем использовать интерфейс в качестве параметра для методов, поставляемых диспетчером ресурсов. Ожидается, что при вызове `GetId` функции необходимо вернуть тот же идентификатор.

Идентификатор, полученный из другого источника, может привести к неопределенному поведению.

## <a name="iexecutioncontextgetproxy-method"></a><a name="getproxy"></a>IExecutionКонтекст::GetProxy Метод

Возвращает интерфейс в прокси-сервер потока, который выполняет этот контекст.

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IThreadProxy`. Если прокси потока контекста выполнения не был инициализирован с `NULL`вызовом к, функция должна вернуться. `SetProxy`

### <a name="remarks"></a>Примечания

Перед вводом `SetProxy` `IThreadProxy` `Dispatch` метода в контекст выполнения— метод будет вызывать сявь в контексте выполнения, с интерфейсом в качестве параметра, прежде чем вводить метод в контексте. Вы должны хранить этот аргумент и вернуть `GetProxy()`его на звонки .

## <a name="iexecutioncontextgetscheduler-method"></a><a name="getscheduler"></a>IExecutionКонтекст::GetScheduler Метод

Возвращает интерфейс планировщику, к которой принадлежит этот контекст выполнения.

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IScheduler`.

### <a name="remarks"></a>Примечания

Перед использованием его в качестве параметра для методов, поставляемых диспетчером ресурсов, необходимо инициализировать контекст выполнения с допустимым `IScheduler` интерфейсом.

## <a name="iexecutioncontextsetproxy-method"></a><a name="setproxy"></a>IExecutionКонтекст::SetProxy Метод

Связывает прокси-сервер потока с этим контекстом выполнения. Связанный прокси потока вызывает этот метод прямо перед тем, как `Dispatch` он начнет выполнение метода контекста.

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>Параметры

*pThreadProxy*<br/>
Интерфейс для прокси потока, который вот-вот войдет в `Dispatch` метод в этом контексте выполнения.

### <a name="remarks"></a>Примечания

Ожидается, что вы `pThreadProxy` сохраните параметр и `GetProxy` вернете его по вызову методу. Диспетчер ресурсов гарантирует, что прокси-сервер потока, связанный с контекстом выполнения, `Dispatch` не изменится во время выполнения метода прокси потока.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IScheduler](ischeduler-structure.md)<br/>
[Структура IThreadProxy](ithreadproxy-structure.md)
