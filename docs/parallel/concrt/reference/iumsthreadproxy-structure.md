---
title: Структура IUMSThreadProxy
ms.date: 11/04/2016
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
ms.openlocfilehash: 2e748b1da02394e1f70afd8b92947e1291957c62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368083"
---
# <a name="iumsthreadproxy-structure"></a>Структура IUMSThreadProxy

Абстракция для потока выполнения. Если требуется предоставлять для планировщика потоки планировщика в пользовательском режиме (UMS), задайте для элемента политики планировщика `SchedulerKind` значение `UmsThreadDefault` и реализуйте интерфейс `IUMSScheduler`. Потоки UMS поддерживаются только в 64-разрядных операционных системах Windows 7 и более поздних версий.

## <a name="syntax"></a>Синтаксис

```cpp
struct IUMSThreadProxy : public IThreadProxy;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IUMSThreadProxy::EnterCriticalRegion](#entercriticalregion)|Вызывается для того, чтобы войти в критический регион. Находясь в критически важном регионе, планировщик не будет наблюдать асинхронные операции блокировки, которые происходят в регионе. Это означает, что планировщик не будет повторно введен для сбоев страницы, суспензий потока, асинхронных процедурных вызовов ядра (APCs) и т.д. для потока UMS.|
|[IUMSThreadProxy::EnterHypercriticalRegion](#enterhypercriticalregion)|Вызывается для того, чтобы войти в гипер-критический регион. Находясь в гиперкритической области, планировщик не будет наблюдать никаких блокирующих операций, которые происходят в регионе. Это означает, что в планировщик не будет повторных входов для блокирующих вызовов функции, блокирующих попыток получения блокировки, сбоев страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. п. для потока UMS.|
|[IUMSThreadProxy::ExitCriticalRegion](#exitcriticalregion)|Вызывается для того, чтобы выйти из критического региона.|
|[IUMSThreadProxy::ExitHyperCriticalRegion](#exithypercriticalregion)|Вызывается для того, чтобы выйти из гиперкритической области.|
|[IUMSThreadProxy::GetCriticalRegionType](#getcriticalregiontype)|Возвращает, в каком критическом регионе находится прокси потока. Поскольку гиперкритические регионы представляют собой супермножество критически важных регионов, если `InsideHyperCriticalRegion` код вошел в критический регион, а затем в гиперкритический регион, будет возвращен.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[IThreadProxy](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Название:** параллелизм

## <a name="iumsthreadproxyentercriticalregion-method"></a><a name="entercriticalregion"></a>IUMSThreadProxy::Метод EnterCriticalRegion

Вызывается для того, чтобы войти в критический регион. Находясь в критически важном регионе, планировщик не будет наблюдать асинхронные операции блокировки, которые происходят в регионе. Это означает, что планировщик не будет повторно введен для сбоев страницы, суспензий потока, асинхронных процедурных вызовов ядра (APCs) и т.д. для потока UMS.

```cpp
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Новая глубина критической области. Критические регионы являются реакторами.

## <a name="iumsthreadproxyenterhypercriticalregion-method"></a><a name="enterhypercriticalregion"></a>IUMSThreadProxy::Метод EnterHyperCriticalRegion

Вызывается для того, чтобы войти в гипер-критический регион. Находясь в гиперкритической области, планировщик не будет наблюдать никаких блокирующих операций, которые происходят в регионе. Это означает, что в планировщик не будет повторных входов для блокирующих вызовов функции, блокирующих попыток получения блокировки, сбоев страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. п. для потока UMS.

```cpp
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Новая глубина гиперкритической области. Гиперкритические регионы ретент.

### <a name="remarks"></a>Примечания

Планировщик должен быть чрезвычайно осторожным в отношении того, какие методы он называет и какие блокировки он приобретает в таких регионах. Если код в таком регионе блокируется на блокировке, которая удерживается чем-то, что планировщик отвечает за планирование, может возникнуть блокировка.

## <a name="iumsthreadproxyexitcriticalregion-method"></a><a name="exitcriticalregion"></a>IUMSThreadProxy::Метод ExitCriticalRegion

Вызывается для того, чтобы выйти из критического региона.

```cpp
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Новая глубина критической области. Критические регионы являются реакторами.

## <a name="iumsthreadproxyexithypercriticalregion-method"></a><a name="exithypercriticalregion"></a>IUMSThreadProxy::ExitHyperCriticalRegion Метод

Вызывается для того, чтобы выйти из гиперкритической области.

```cpp
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Новая глубина гиперкритической области. Гиперкритические регионы ретент.

## <a name="iumsthreadproxygetcriticalregiontype-method"></a><a name="getcriticalregiontype"></a>IUMSThreadProxy::GetCriticalRegionType Метод

Возвращает, в каком критическом регионе находится прокси потока. Поскольку гиперкритические регионы представляют собой супермножество критически важных регионов, если `InsideHyperCriticalRegion` код вошел в критический регион, а затем в гиперкритический регион, будет возвращен.

```cpp
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Тип критической области прокси потока находится внутри.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IUMSScheduler](iumsscheduler-structure.md)
