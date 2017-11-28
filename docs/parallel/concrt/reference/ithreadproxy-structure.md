---
title: "Структура IThreadProxy | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IThreadProxy
- CONCRTRM/concurrency::IThreadProxy
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::GetId
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchOut
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchTo
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::YieldToSystem
dev_langs: C++
helpviewer_keywords: IThreadProxy structure
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f56e7858fc313ac35d5a3937e2d64472f28e355d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ithreadproxy-structure"></a>Структура IThreadProxy
Абстракция для потока выполнения. В зависимости от ключа политики `SchedulerType` созданного планировщика, диспетчер ресурсов предоставит прокси-поток, поддерживаемый обычным потоком Win32 или потоком планировщика пользовательского режима (UMS). Потоки UMS поддерживаются в 64-разрядных операционных системах Windows 7 и более поздних версий.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IThreadProxy;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IThreadProxy::GetId](#getid)|Возвращает уникальный идентификатор для прокси-поток.|  
|[IThreadProxy::SwitchOut](#switchout)|Отсоединяет контекст от базового корневого виртуального процессора.|  
|[IThreadProxy::SwitchTo](#switchto)|Выполняет совместное переключение контекста с текущего выполняемого контекста на другую страницу.|  
|[IThreadProxy::YieldToSystem](#yieldtosystem)|Позволяет вызвавшему потоку передать выполнение другому потоку, готовому к использованию на текущем процессоре. Операционная система выбирает следующий поток для выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Прокси-потоки привязаны к контекстам выполнения, представленными интерфейсом `IExecutionContext` как средство управления работой.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IThreadProxy`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="getid"></a>Метод IThreadProxy::GetId  
 Возвращает уникальный идентификатор для прокси-поток.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный целочисленный идентификатор.  
  
##  <a name="switchout"></a>Метод IThreadProxy::SwitchOut  
 Отсоединяет контекст от базового корневого виртуального процессора.  
  
```
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `switchState`  
 Указывает состояние прокси потока, выполняющего переключателя. Параметр имеет тип `SwitchingProxyState`.  
  
### <a name="remarks"></a>Примечания  
 Используйте `SwitchOut` при необходимости отсоединения контекста от корневого виртуального процессора, на котором он выполняется, по любой причине. В зависимости от значения, переданного параметру `switchState`, и от того, выполняется ли он на корневом виртуальном процессоре, вызов немедленно вернет управление или заблокирует прокси-поток, связанный с контекстом. Вызов `SwitchOut` с параметром со значением `Idle` является ошибочным. Это приведет к [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение.  
  
 Метод `SwitchOut` полезен, когда требуется сократить число корневых виртуальных процессоров у вашего планировщика либо потому, что диспетчер ресурсов рекомендовал так сделать, либо потому, что вы запросили корневой виртуальный процессор, который временно переподписан, и завершили работу с ним. В этом случае следует вызвать метод [IVirtualProcessorRoot::Remove](http://msdn.microsoft.com/en-us/ad699b4a-1972-4390-97ee-9c083ba7d9e4) на корневой виртуальный процессор, перед вызовом `SwitchOut` с параметром `switchState` значение `Blocking`. Это заблокирует прокси-поток и возобновит выполнение, когда другой корневой виртуальный процессор в планировщике будет доступен для его выполнения. Блокирующий прокси-поток можно возобновить путем вызова функции `SwitchTo` переключение контекста выполнения данного прокси-потока. Также можно возобновить прокси-поток с помощью соответствующего контекста для активации корневой виртуальный процессор. Дополнительные сведения о том, как это сделать см. в разделе [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate).  
  
 `SwitchOut` также может использоваться, когда требуется повторная инициализация виртуального процессора, чтобы его можно было активировать в будущем либо при блокировке прокси-потока, либо при временном отсоединении его от корневого виртуального процессора, на котором он выполняется, и от планировщика, который обслуживается потоком. Используйте `SwitchOut` с параметром `switchState` со значением `Blocking`, если необходимо заблокировать прокси-поток. Позже его можно будет возобновить с помощью или `SwitchTo`, или `IVirtualProcessorRoot::Activate`, как указано выше. Используйте `SwitchOut` со значением `Nesting` для этого параметра, если необходимо временно отсоединить этот прокси-поток от корневого виртуального процессора, на котором он выполняется, и от планировщика, с которым связан виртуальный процессор. Вызов `SwitchOut` с параметром `switchState` со значением `Nesting` при выполнении на корневом виртуальном процессоре вызовет повторную инициализацию корня и продолжение работы текущего прокси-потока, когда это не будет требоваться. Прокси-поток считается покинувшим планировщик до вызывает [IThreadProxy::SwitchOut](#switchout) метод с `Blocking` позднее времени. Второй вызов `SwitchOut` со значением параметра `Blocking` предназначен для возврата контекста в заблокированное состояние, чтобы он мог быть возобновлен с помощью или `SwitchTo`, или `IVirtualProcessorRoot::Activate` в планировщике, от которого его отсоединили. Поскольку он не выполнялся на корневом виртуальном процессоре, повторная инициализация не происходит.  
  
 Повторно инициализированный корневой виртуальный процессор ничем не отличается от абсолютно нового виртуального процессора, выделенного диспетчером ресурсов планировщику. Его можно использовать для выполнения, активировав его с контекстом выполнения с помощью `IVirtualProcessorRoot::Activate`.  
  
 `SwitchOut`должен быть вызван для `IThreadProxy` интерфейс, который представляет текущий выполняемый поток или результаты не определены.  
  
 В библиотеках и заголовках, поставляемых вместе с Visual Studio 2010, этот метод не принимает параметров и не инициализирует повторно корневой виртуальный процессор. Для сохранения старого поведения значение параметра по умолчанию задано как `Blocking`.  
  
##  <a name="switchto"></a>Метод IThreadProxy::SwitchTo  
 Выполняет совместное переключение контекста с текущего выполняемого контекста на другую страницу.  
  
```
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pContext`  
 Контекст выполнения, чтобы переключиться совместно.  
  
 `switchState`  
 Указывает состояние прокси потока, выполняющего переключателя. Параметр имеет тип `SwitchingProxyState`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для переключения из одного контекста выполнения в другой, из [IExecutionContext::Dispatch](iexecutioncontext-structure.md#dispatch) метод первого контекста выполнения. Метод связывает контекст выполнения `pContext` с прокси-поток, если он еще не связан с одним. Владение текущим прокси-потоком определяется значение, указываемое для `switchState` аргумент.  
  
 Используйте значение `Idle` при необходимости для получения текущей выполняемой прокси-поток с диспетчером ресурсов. Вызов `SwitchTo` с параметром `switchState` значение `Idle` приведет к контексту выполнения `pContext` для начала выполнения на основной ресурс выполнения. Владение этот прокси-поток передается в диспетчер ресурсов, а вы должны возвращать из контекста выполнения `Dispatch` метод вскоре после `SwitchTo` возвращает для завершения передачи. Контекст выполнения, который был управляем прокси-поток отсоединяется от прокси-поток и планировщик может свободно использовать его повторно или уничтожить его, как для него образом.  
  
 Используйте значение `Blocking` при необходимости этот прокси-поток переходит в состояние блокировки. Вызов `SwitchTo` с параметром `switchState` значение `Blocking` приведет к контексту выполнения `pContext` начала его выполнения, и блокировать текущего прокси-поток, пока будет возобновлено. Планировщик сохраняет владение прокси-потоком, когда прокси-поток находится в `Blocking` состояние. Блокирующий прокси-поток можно возобновить путем вызова функции `SwitchTo` переключение контекста выполнения данного прокси-потока. Также можно возобновить прокси-поток с помощью соответствующего контекста для активации корневой виртуальный процессор. Дополнительные сведения о том, как это сделать см. в разделе [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate).  
  
 Используйте значение `Nesting` Если необходимо временно отсоединить этот прокси-поток от корневого виртуального процессора, выполняется на и планировщик, который обслуживается для. Вызов `SwitchTo` с параметром `switchState` значение `Nesting` приведет к контексту выполнения `pContext` для запуска, выполнения и текущего прокси-поток также продолжит выполняться без необходимости корневой виртуальный процессор. Прокси-поток считается покинувшим планировщик до вызывает [IThreadProxy::SwitchOut](#switchout) метод позднее времени. `IThreadProxy::SwitchOut` Метод может заблокировать прокси-поток, пока корневой виртуальный процессор доступен для повторного планирования его.  
  
 `SwitchTo`должен быть вызван для `IThreadProxy` интерфейс, который представляет текущий выполняемый поток или результаты не определены. Эта функция создает `invalid_argument` Если параметр `pContext` равно `NULL`.  
  
##  <a name="yieldtosystem"></a>Метод IThreadProxy::YieldToSystem  
 Позволяет вызвавшему потоку передать выполнение другому потоку, готовому к использованию на текущем процессоре. Операционная система выбирает следующий поток для выполнения.  
  
```
virtual void YieldToSystem() = 0;
```  
  
### <a name="remarks"></a>Примечания  
 При вызове с помощью прокси-поток, поддерживаемый Обычный поток Windows, `YieldToSystem` ведет себя так же, как функции Windows `SwitchToThread`. Тем не менее, при вызове из планируемые потоки пользовательского режима (UMS), `SwitchToThread` функции делегирует задачу подбора следующего потока для запуска планировщика режима пользователя, не операционной системы. Для достижения желаемого эффекта переключения на другой поток готов в системе, используйте `YieldToSystem`.  
  
 `YieldToSystem`должен быть вызван для `IThreadProxy` интерфейс, который представляет текущий выполняемый поток или результаты не определены.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IExecutionContext](iexecutioncontext-structure.md)   
 [Структура IScheduler](ischeduler-structure.md)   
 [Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)