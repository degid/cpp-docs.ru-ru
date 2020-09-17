---
title: Класс CComApartment
ms.date: 11/04/2016
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
ms.openlocfilehash: 13141d27592f6f40ea7b0529c61baba2fe83a10a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321117"
---
# <a name="ccomapartment-class"></a>Класс CComApartment

Этот класс обеспечивает поддержку для управления квартирой в модуле EXE, объединенном потоками.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CComApartment
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComApartment:CComApartment](#ccomapartment)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComApartment:Квартира](#apartment)|Отметки исходного адреса потока.|
|[CComApartment::GetLockCount](#getlockcount)|Возвращает текущий счет блокировки потока.|
|[CComApartment::Lock](#lock)|Приравливывает количество блокировки потока.|
|[CComApartment::Разблокировка](#unlock)|Утилищает количество блокировки потока.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComApartment::m_dwThreadID](#m_dwthreadid)|Содержит идентификатор потока.|
|[CComApartment::m_hThread](#m_hthread)|Содержит ручку потока.|
|[CComApartment::m_nLockCnt](#m_nlockcnt)|Содержит текущее количество блокировки потока.|

## <a name="remarks"></a>Примечания

`CComApartment`используется [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) для управления квартирой в модуле EXE, объединенном потоками. `CComApartment`предоставляет методы для приращения и decrementing блокировки рассчитывать на поток.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomapartmentapartment"></a><a name="apartment"></a>CComApartment:Квартира

Отметки исходного адреса потока.

```
DWORD Apartment();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда равно 0.

### <a name="remarks"></a>Примечания

Автоматически устанавливается во время [CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init).

## <a name="ccomapartmentccomapartment"></a><a name="ccomapartment"></a>CComApartment:CComApartment

Конструктор.

```
CComApartment();
```

### <a name="remarks"></a>Примечания

Инициализирует данные `CComApartment` членов [m_nLockCnt](#m_nlockcnt) и [m_hThread](#m_hthread).

## <a name="ccomapartmentgetlockcount"></a><a name="getlockcount"></a>CComApartment::GetLockCount

Возвращает текущий счет блокировки потока.

```
LONG GetLockCount();
```

### <a name="return-value"></a>Возвращаемое значение

Блокировка рассчитывает на нить.

## <a name="ccomapartmentlock"></a><a name="lock"></a>CComApartment::Lock

Приравливывает количество блокировки потока.

```
LONG Lock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Примечания

Вызывается [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock).

Подсчет блокировки на потоке используется для статистических целей.

## <a name="ccomapartmentm_dwthreadid"></a><a name="m_dwthreadid"></a>CComApartment::m_dwThreadID

Содержит идентификатор потока.

```
DWORD m_dwThreadID;
```

## <a name="ccomapartmentm_hthread"></a><a name="m_hthread"></a>CComApartment::m_hThread

Содержит ручку потока.

```
HANDLE m_hThread;
```

## <a name="ccomapartmentm_nlockcnt"></a><a name="m_nlockcnt"></a>CComApartment::m_nLockCnt

Содержит текущее количество блокировки потока.

```
LONG m_nLockCnt;
```

## <a name="ccomapartmentunlock"></a><a name="unlock"></a>CComApartment::Разблокировка

Утилищает количество блокировки потока.

```
LONG Unlock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Примечания

Вызывается [CComAutoThreadModule::Разблокировка](../../atl/reference/ccomautothreadmodule-class.md#lock).

Подсчет блокировки на потоке используется для статистических целей.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
