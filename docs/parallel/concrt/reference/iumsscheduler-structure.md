---
title: Структура IUMSScheduler
ms.date: 11/04/2016
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
ms.openlocfilehash: 70954906122c048e5199a801632626d35a8e3f18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368099"
---
# <a name="iumsscheduler-structure"></a>Структура IUMSScheduler

Интерфейс абстракции планировщика, которому требуется, чтобы диспетчер ресурсов среды выполнения с параллелизмом передал ему потоки планировщика в пользовательском режиме (UMS). Диспетчер ресурсов среды выполнения с параллелизмом использует этот интерфейс для взаимодействия с планировщиками потоков UMS. Интерфейс `IUMSScheduler` наследует от интерфейса `IScheduler` .

## <a name="syntax"></a>Синтаксис

```cpp
struct IUMSScheduler : public IScheduler;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IUMSScheduler::SetCompletionList](#setcompletionlist)|Присваивает `IUMSCompletionList` интерфейс планировщику потоков UMS.|

## <a name="remarks"></a>Примечания

Если вы реализуете пользовательский планировщик, который общается с диспетчером ресурсов, и вы хотите, чтобы потоки UMS были переданы планировщику вместо обычных потоков Win32, вы должны предоставить реализацию `IUMSScheduler` интерфейса. Кроме того, следует установить значение политики `SchedulerKind` для `UmsThreadDefault`ключа политики планировщика. Если политика определяет поток UMS, `IScheduler` интерфейс, который передается в качестве параметра [IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler) метод должен быть интерфейсом. `IUMSScheduler`

Менеджер ресурсов может передавать вам потоки UMS только на операционных системах, которые имеют функцию UMS. 64-разрядные операционные системы с версией Windows 7 и более высокой поддержкой ПОТОКОВ UMS. Если вы создаете политику `SchedulerKind` планировщика с `UmsThreadDefault` набором ключей к значению, а базовая платформа не поддерживает UMS, значение `SchedulerKind` ключа в этой политике будет изменено на значение. `ThreadScheduler` Вы всегда должны прочитать это значение политики, прежде чем ожидать получения потоков UMS.

Интерфейс `IUMSScheduler` является одним из конца двустороннего канала связи между планировщиком и менеджером ресурсов. Другой конец представлен интерфейсами `IResourceManager` `ISchedulerProxy` и интерфейсами, которые реализуются менеджером ресурсов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[IScheduler](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Название:** параллелизм

## <a name="iumsschedulersetcompletionlist-method"></a><a name="setcompletionlist"></a>IUMSScheduler::SetCompletionList Метод

Присваивает `IUMSCompletionList` интерфейс планировщику потоков UMS.

```cpp
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>Параметры

*pCompletionList*<br/>
Интерфейс списка завершения для планировщика. Существует единый список на планировщика.

### <a name="remarks"></a>Примечания

Менеджер ресурсов будет ссылаться на этот метод на планировщике, который указывает, что он хочет ПОТОКи UMS, после того, как планировщик запросил первоначальное распределение ресурсов. Планировщик может использовать `IUMSCompletionList` интерфейс, чтобы определить, когда прокси-потоки UMS разблокированы. Доступ к этому интерфейсу действителен только из прокси-сервера потока, работающего на корне виртуального процессора, назначенном планировщику UMS.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[Структура IScheduler](ischeduler-structure.md)<br/>
[Структура IUMSCompletionList](iumscompletionlist-structure.md)<br/>
[Структура IResourceManager](iresourcemanager-structure.md)
