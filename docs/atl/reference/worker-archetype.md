---
title: Рабочий архетип
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: c9ed9b30b94a8debe133bc213c12063750bfb15a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747342"
---
# <a name="worker-archetype"></a>Рабочий архетип

Классы, соответствующие архетипу *рабочего,* предоставляют код для обработки рабочих элементов, выстраиваемых в очередь в пуле потоков.

**Реализация**

Для реализации класса, соответствующего этому архетипу, класс должен предоставить следующие функции:

|Метод|Описание|
|------------|-----------------|
|[Initialize](#initialize)|Вызывается для инициализации объекта работника до того, как любые запросы будут переданы в [выполнение.](#execute)|
|[Execute](#execute)|Вызывается для обработки рабочего элемента.|
|[Завершить](#terminate)|Вызывается для отсоединения объекта работы после того, как все запросы были переданы для [выполнения.](#execute)|

|Typedef|Описание|
|-------------|-----------------|
|[ЗапросType](#requesttype)|Typedef для типа рабочего элемента, который может быть обработан классом работника.|

Типичный класс *работников* выглядит следующим образом:

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**Существующие реализации**

Эти классы соответствуют этому архетипу:

|Class|Описание|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Получает запросы из пула потоков и передает их объекту рабочего, который создается и уничтожается для каждого запроса.|

**Использовать**

Эти параметры шаблона ожидают, что класс будет соответствовать этому архетипу:

|Имя параметра|Где используется|
|--------------------|-------------|
|*Работник*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*Работник*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="workerarchetypeexecute"></a><a name="execute"></a>РабочийАрхетип::Выполнение

Вызывается для обработки рабочего элемента.

```cpp
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>Параметры

*request*<br/>
Рабочий элемент, который будет обработан. Элемент работы имеет тот `RequestType`же тип, что и .

*pvWorkerParam*<br/>
Пользовательский параметр, понятный классу рабочих. Также перешли `WorkerArchetype::Initialize` `Terminate`к и .

*pOverlapped*<br/>
Указатель на структуру [OVERLAPPED,](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) используемый для создания очереди, в которой стояли рабочие элементы в очереди.

## <a name="workerarchetypeinitialize"></a><a name="initialize"></a>РабочийАрхетип::Инициализация

Вызывается для инициализации объекта `WorkerArchetype::Execute`работника до того, как будут переданы запросы.

```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>Параметры

*pvParam*<br/>
Пользовательский параметр, понятный классу рабочих. Также перешли `WorkerArchetype::Terminate` `WorkerArchetype::Execute`к и .

### <a name="return-value"></a>Возвращаемое значение

Вернуться TRUE на успех, FALSE на провал.

## <a name="workerarchetyperequesttype"></a><a name="requesttype"></a>РабочийАрхетип:ЗапросТип

Typedef для типа рабочего элемента, который может быть обработан классом работника.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>Примечания

Этот тип должен использоваться в `WorkerArchetype::Execute` качестве первого параметра и должен быть способен быть отлиты в и из ULONG_PTR.

## <a name="workerarchetypeterminate"></a><a name="terminate"></a>РабочийАрхетип::Прекращение

Вызывается для отunимитивизации объекта `WorkerArchetype::Execute`работника после того, как все запросы были переданы).

```cpp
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>Параметры

*pvParam*<br/>
Пользовательский параметр, понятный классу рабочих. Также перешли `WorkerArchetype::Initialize` `WorkerArchetype::Execute`к и .

## <a name="see-also"></a>См. также раздел

[Основные понятия](../../atl/active-template-library-atl-concepts.md)<br/>
[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)
