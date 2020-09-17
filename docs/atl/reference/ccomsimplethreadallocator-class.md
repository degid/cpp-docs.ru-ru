---
title: Класс CComSimpleThreadAllocator
ms.date: 11/04/2016
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
ms.openlocfilehash: 4a3cce492db4db9f46aeb4efe738ee6a594ddcfc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327348"
---
# <a name="ccomsimplethreadallocator-class"></a>Класс CComSimpleThreadAllocator

Этот класс управляет выбором `CComAutoThreadModule`потоков для класса.

## <a name="syntax"></a>Синтаксис

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComSimpleThreadAllocator::GetThread](#getthread)|Выбирает поток.|

## <a name="remarks"></a>Примечания

`CComSimpleThreadAllocator`управляет выбором потоков для [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread`просто циклы через каждый поток и возвращает следующий в последовательности.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomsimplethreadallocatorgetthread"></a><a name="getthread"></a>CComSimpleThreadAllocator::GetThread

Выберите поток, указав следующий поток в последовательности.

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>Параметры

*pApt*<br/>
Не используется при реализации по умолчанию ATL.

*nThreads*<br/>
Максимальное количество потоков в модуле EXE.

### <a name="return-value"></a>Возвращаемое значение

Многокомнатная между нулем и *(nThreads* - 1). Идентифицирует одну из потоков в модуле EXE.

### <a name="remarks"></a>Примечания

Вы можете `GetThread` переопределить, чтобы обеспечить другой метод отбора или использовать параметр *pApt.*

`GetThread`называется [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).

## <a name="see-also"></a>См. также раздел

[Класс CComApartment](../../atl/reference/ccomapartment-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
