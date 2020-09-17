---
title: Структура ISchedulerProxy
ms.date: 11/04/2016
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
ms.openlocfilehash: dcb6d175fa84e33f6a5af974eb76f1e1246bdc35
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226702"
---
# <a name="ischedulerproxy-structure"></a>Структура ISchedulerProxy

Интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов среды выполнения с параллелизмом для согласования выделения ресурсов.

## <a name="syntax"></a>Синтаксис

```cpp
struct ISchedulerProxy;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ISchedulerProxy::BindContext](#bindcontext)|Связывает контекст выполнения с прокси-сервером потока, если он еще не связан с одним потоком.|
|[ISchedulerProxy::CreateOversubscriber](#createoversubscriber)|Создает новый корень виртуального процессора в аппаратном потоке, связанном с существующим ресурсом выполнения.|
|[ISchedulerProxy::RequestInitialVirtualProcessors](#requestinitialvirtualprocessors)|Запрашивает начальное выделение корней виртуального процессора. Каждый корень виртуального процессора представляет возможность выполнения одного потока, который может выполнять работу с планировщиком.|
|[ISchedulerProxy::Shutdown](#shutdown)|Уведомляет диспетчер ресурсов о завершении работы планировщика. Это приведет к тому, что диспетчер ресурсов немедленно освободит все ресурсы, предоставленные планировщику.|
|[ISchedulerProxy::SubscribeCurrentThread](#subscribecurrentthread)|Регистрирует текущий поток с диспетчер ресурсов, связывая его с этим планировщиком.|
|[ISchedulerProxy::UnbindContext](#unbindcontext)|Отменяет связь прокси-сервера потока с контекстом выполнения, указанным в `pContext` параметре, и возвращает его в свободный пул фабрики прокси-сервера потока. Этот метод может быть вызван только для контекста выполнения, который был привязан через метод [ISchedulerProxy::BindContext](#bindcontext) и еще не был запущен с помощью `pContext` параметра вызова метода [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) .|

## <a name="remarks"></a>Примечания

Диспетчер ресурсов передает `ISchedulerProxy` интерфейс каждому планировщику, который регистрируется с ним с помощью метода [IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISchedulerProxy`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

## <a name="ischedulerproxybindcontext-method"></a><a name="bindcontext"></a>Метод ISchedulerProxy::BindContext

Связывает контекст выполнения с прокси-сервером потока, если он еще не связан с одним потоком.

```cpp
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Параметры

*pContext*<br/>
Интерфейс к контексту выполнения, связываемый с прокси-потоком.

### <a name="remarks"></a>Примечания

Как правило, метод [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) будет привязывать прокси-сервер потока к контексту выполнения по запросу. Однако существуют обстоятельства, когда необходимо привязать контекст заранее, чтобы `SwitchTo` метод переключились на уже привязанный контекст. Это происходит в контексте планирования UMS, так как он не может вызывать методы, выделяющие память, и привязка прокси-сервера потока может привести к выделению памяти, если прокси-сервер потока недоступен в свободном пуле фабрики прокси потока.

`invalid_argument`Если параметр имеет значение, создается исключение `pContext` `NULL` .

## <a name="ischedulerproxycreateoversubscriber-method"></a><a name="createoversubscriber"></a>Метод ISchedulerProxy::CreateOversubscriber

Создает новый корень виртуального процессора в аппаратном потоке, связанном с существующим ресурсом выполнения.

```cpp
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```

### <a name="parameters"></a>Параметры

*pExecutionResource*<br/>
`IExecutionResource`Интерфейс, представляющий аппаратный поток, который нужно переподписать.

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IVirtualProcessorRoot`.

### <a name="remarks"></a>Примечания

Используйте этот метод, если вашему планировщику требуется отменить подписывание определенного аппаратного потока в течение ограниченного периода времени. Завершив работу с корнем виртуального процессора, необходимо вернуть его в Resource Manager, вызвав метод [Remove](iexecutionresource-structure.md#remove) `IVirtualProcessorRoot` интерфейса.

Поскольку интерфейс `IVirtualProcessorRoot` наследует от интерфейса `IExecutionResource`, можно даже переподписать существующий корневой виртуальный процессор.

## <a name="ischedulerproxyrequestinitialvirtualprocessors-method"></a><a name="requestinitialvirtualprocessors"></a>Метод ISchedulerProxy::RequestInitialVirtualProcessors

Запрашивает начальное выделение корней виртуального процессора. Каждый корень виртуального процессора представляет возможность выполнения одного потока, который может выполнять работу с планировщиком.

```cpp
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```

### <a name="parameters"></a>Параметры

*doSubscribeCurrentThread*<br/>
Следует ли подписывать текущий поток и учетную запись для него во время выделения ресурсов.

### <a name="return-value"></a>Возвращаемое значение

`IExecutionResource`Интерфейс для текущего потока, если параметр `doSubscribeCurrentThread` имеет значение **`true`** . Если значение равно **`false`** , метод возвращает значение null.

### <a name="remarks"></a>Примечания

Прежде чем планировщик будет выполнять какую-либо работу, он должен использовать этот метод для запроса корней виртуального процессора из диспетчер ресурсов. Диспетчер ресурсов будет получать доступ к политике планировщика с помощью [IScheduler:: Policy](ischeduler-structure.md#getpolicy) и использовать значения ключей политики `MinConcurrency` , `MaxConcurrency` а также определить, сколько `TargetOversubscriptionFactor` аппаратных потоков необходимо назначить планировщику, и сколько корней виртуального процессора следует создать для каждого аппаратного потока. Дополнительные сведения о том, как политики планировщика используются для определения первоначального выделения планировщика, см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).

Диспетчер ресурсов предоставляет ресурсы планировщику путем вызова метода [IScheduler:: аддвиртуалпроцессорс](ischeduler-structure.md#addvirtualprocessors) со списком корней виртуального процессора. Метод вызывается как обратный вызов планировщика перед возвратом из этого метода.

Если планировщик запросил подписку для текущего потока, задав для параметра значение `doSubscribeCurrentThread` **`true`** , метод возвращает `IExecutionResource` интерфейс. Подписка должна быть завершена позже с помощью метода [IExecutionResource::Remove](iexecutionresource-structure.md#remove) .

При определении выбранных аппаратных потоков диспетчер ресурсов будет пытаться выполнить оптимизацию для сходства узлов процессора. Если для текущего потока запрашивается подписка, это означает, что текущий поток намеревается участвовать в работе, назначенной этому планировщику. В этом случае корни выделенных виртуальных процессоров находятся на узле процессора, на котором выполняется текущий поток, если это возможно.

Процесс подписки потока увеличивает уровень подписки базового аппаратного потока на единицу. Уровень подписки уменьшается на единицу после завершения подписки. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ischedulerproxyshutdown-method"></a><a name="shutdown"></a>Метод ISchedulerProxy::Shutdown

Уведомляет диспетчер ресурсов о завершении работы планировщика. Это приведет к тому, что диспетчер ресурсов немедленно освободит все ресурсы, предоставленные планировщику.

```cpp
virtual void Shutdown() = 0;
```

### <a name="remarks"></a>Примечания

Все `IExecutionContext` интерфейсы, полученные планировщиком в результате подписки внешнего потока с помощью методов `ISchedulerProxy::RequestInitialVirtualProcessors` или, `ISchedulerProxy::SubscribeCurrentThread` должны возвращаться в Диспетчер ресурсов с помощью `IExecutionResource::Remove` перед завершением работы планировщика.

Если у вашего планировщика есть деактивированные корни виртуального процессора, необходимо активировать их с помощью [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate), а прокси-серверы потоков, выполняющиеся на них, оставить `Dispatch` метод контекстов выполнения, который они отправляют перед вызовом `Shutdown` по прокси-серверу планировщика.

Для планировщика необязательно возвращать все корневые виртуальные процессоры, выданные ему диспетчером ресурсов путем вызовов метода `Remove`, поскольку все корневые виртуальные процессоры будут возвращены диспетчеру ресурсов при завершении работы.

## <a name="ischedulerproxysubscribecurrentthread-method"></a><a name="subscribecurrentthread"></a>Метод ISchedulerProxy::SubscribeCurrentThread

Регистрирует текущий поток с диспетчер ресурсов, связывая его с этим планировщиком.

```cpp
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

`IExecutionResource`Взаимодействие, представляющее текущий поток в среде выполнения.

### <a name="remarks"></a>Примечания

Используйте этот метод, если необходимо, чтобы диспетчер ресурсов учетной записи для текущего потока при выделении ресурсов планировщику и другим планировщикам. Это особенно полезно, когда поток планирует участвовать в работе в очереди планировщика, а также к корням виртуальных процессоров, получаемым планировщиком от диспетчер ресурсов. Диспетчер ресурсов использует сведения, чтобы предотвратить ненужную избыточную подписку аппаратных потоков в системе.

Ресурс выполнения, полученный с помощью этого метода, должен возвращаться в диспетчер ресурсов с помощью метода [IExecutionResource::Remove](iexecutionresource-structure.md#remove) . Поток, вызывающий `Remove` метод, должен быть тем же потоком, который ранее вызвал `SubscribeCurrentThread` метод.

Процесс подписки потока увеличивает уровень подписки базового аппаратного потока на единицу. Уровень подписки уменьшается на единицу после завершения подписки. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ischedulerproxyunbindcontext-method"></a><a name="unbindcontext"></a>Метод ISchedulerProxy::UnbindContext

Отменяет связь прокси-сервера потока с контекстом выполнения, указанным в `pContext` параметре, и возвращает его в свободный пул фабрики прокси-сервера потока. Этот метод может быть вызван только для контекста выполнения, который был привязан через метод [ISchedulerProxy::BindContext](#bindcontext) и еще не был запущен с помощью `pContext` параметра вызова метода [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) .

```cpp
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Параметры

*pContext*<br/>
Контекст выполнения для отсвязи от прокси-сервера потока.

## <a name="see-also"></a>См. также статью

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Структура IScheduler](ischeduler-structure.md)<br/>
[Структура IThreadProxy](ithreadproxy-structure.md)<br/>
[Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)<br/>
[Структура IResourceManager](iresourcemanager-structure.md)
