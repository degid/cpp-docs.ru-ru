---
title: Класс IRowsetNotifyImpl
ms.date: 11/04/2016
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
- IRowsetNotifyImpl.OnFieldChange
- IRowsetNotifyImpl::OnFieldChange
- OnFieldChange
- IRowsetNotifyImpl::OnRowChange
- IRowsetNotifyImpl.OnRowChange
- OnRowChange
- OnRowsetChange
- IRowsetNotifyImpl::OnRowsetChange
- IRowsetNotifyImpl.OnRowsetChange
helpviewer_keywords:
- IRowsetNotifyImpl class
- OnFieldChange method
- OnRowChange method
- OnRowsetChange method
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
ms.openlocfilehash: f938d9e92bc2f447ecfa82f2bfb27c8fda7652ab
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845111"
---
# <a name="irowsetnotifyimpl-class"></a>Класс IRowsetNotifyImpl

Реализует и регистрирует [IRowsetNotify клиента](/previous-versions/windows/desktop/ms712959(v=vs.85)) на потребителе (также называемом приемником), чтобы он мог обслуживать уведомления.

## <a name="syntax"></a>Синтаксис

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[онфиелдчанже](#onfieldchange)|Уведомляет объект-получатель о любом изменении значения в столбце.|
|[онровчанже](#onrowchange)|Уведомляет объект-получатель о первом изменении в строке или о любом изменении, оказывающем влияние на всю строку.|
|[онровсетчанже](#onrowsetchange)|Уведомляет объект-получатель о любом изменении, влияющем на весь набор строк.|

## <a name="remarks"></a>Примечания

См. статью [Получение уведомлений](../../data/oledb/receiving-notifications.md) о реализации интерфейса точки подключения на потребителе.

`IRowsetNotifyImpl` предоставляет фиктивную реализацию для `IRowsetNotify` , с пустыми функциями для `IRowsetNotify` методов [онфиелдчанже](/previous-versions/windows/desktop/ms715961(v=vs.85)), [онровчанже](/previous-versions/windows/desktop/ms722694(v=vs.85))и [онровсетчанже](/previous-versions/windows/desktop/ms722669(v=vs.85)). При наследовании от этого класса при реализации `IRowsetNotify` интерфейса можно реализовать только необходимые методы. Также необходимо предоставить пустые реализации для других методов самостоятельно.

## <a name="irowsetnotifyimplonfieldchange"></a><a name="onfieldchange"></a> IRowsetNotifyImpl:: Онфиелдчанже

Уведомляет объект-получатель о любом изменении значения в столбце.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(OnFieldChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ HROW /* hRow */,
/* [in] */ DBORDINAL /* cColumns */,
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>Параметры

Описание параметров см. в разделе [IRowsetNotify клиента:: онфиелдчанже](/previous-versions/windows/desktop/ms715961(v=vs.85)) .

### <a name="return-value"></a>Возвращаемое значение

Описание возвращаемого значения см. в разделе [IRowsetNotify клиента:: онфиелдчанже](/previous-versions/windows/desktop/ms715961(v=vs.85)) .

### <a name="remarks"></a>Примечания

Этот метод создает оболочку для метода [IRowsetNotify клиента:: онфиелдчанже](/previous-versions/windows/desktop/ms715961(v=vs.85)) . Дополнительные сведения см. в описании этого метода в справочнике по OLE DB программиста.

## <a name="irowsetnotifyimplonrowchange"></a><a name="onrowchange"></a> IRowsetNotifyImpl:: Онровчанже

Уведомляет объект-получатель о первом изменении в строке или о любом изменении, оказывающем влияние на всю строку.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(OnRowChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBCOUNTITEM /* cRows */,
/* [size_is][in] */ const HROW /* rghRows*/ [] ,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>Параметры

Описание параметров см. в разделе [IRowsetNotify клиента:: онровчанже](/previous-versions/windows/desktop/ms722694(v=vs.85)) .

### <a name="return-value"></a>Возвращаемое значение

Описание возвращаемого значения см. в разделе [IRowsetNotify клиента:: онровчанже](/previous-versions/windows/desktop/ms722694(v=vs.85)) .

### <a name="remarks"></a>Примечания

Этот метод создает оболочку для метода [IRowsetNotify клиента:: онровчанже](/previous-versions/windows/desktop/ms722694(v=vs.85)) . Дополнительные сведения см. в описании этого метода в справочнике по OLE DB программиста.

## <a name="irowsetnotifyimplonrowsetchange"></a><a name="onrowsetchange"></a> IRowsetNotifyImpl:: Онровсетчанже

Уведомляет объект-получатель о любом изменении, влияющем на весь набор строк.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(OnRowsetChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>Параметры

Описание параметров см. в разделе [IRowsetNotify клиента:: онровсетчанже](/previous-versions/windows/desktop/ms722669(v=vs.85)) .

### <a name="return-value"></a>Возвращаемое значение

Описание возвращаемого значения см. в разделе [IRowsetNotify клиента:: онровсетчанже](/previous-versions/windows/desktop/ms722669(v=vs.85)) .

### <a name="remarks"></a>Примечания

Этот метод создает оболочку для метода [IRowsetNotify клиента:: онровсетчанже](/previous-versions/windows/desktop/ms722669(v=vs.85)) . Дополнительные сведения см. в описании этого метода в справочнике по OLE DB программиста.

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[IRowsetNotify клиента](/previous-versions/windows/desktop/ms712959(v=vs.85)) 
 [Класс IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)
