---
title: Класс IConnectionPointImpl
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
ms.openlocfilehash: c62ac3310a579379674674a7a9a517e3f2fd60e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329857"
---
# <a name="iconnectionpointimpl-class"></a>Класс IConnectionPointImpl

Этот класс реализует точку соединения.

## <a name="syntax"></a>Синтаксис

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IConnectionPointImpl`.

*пиид*<br/>
Указатель на IID интерфейса, представленный объектом точки соединения.

*Cdv*<br/>
Класс, управляющий соединениями. Значение по умолчанию [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), что позволяет неограниченное количество подключений. Вы также можете использовать [CComUnkArray](../../atl/reference/ccomunkarray-class.md), который определяет фиксированное количество соединений.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IConnectionPointImpl::Консультация](#advise)|Устанавливает связь между точкой соединения и раковиной.|
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Создает регистратор для итерата через соединения для точки соединения.|
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Извлекает IID интерфейса, представленного точкой соединения.|
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Извлекает указатель интерфейса на подключаемый объект.|
|[IConnectionPointImpl::Unadvise](#unadvise)|Прекращает подключение, ранее `Advise`установленное через .|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[IConnectionPointImpl::m_vec](#m_vec)|Управляет соединениями для точки соединения.|

## <a name="remarks"></a>Примечания

`IConnectionPointImpl`реализует точку соединения, которая позволяет объекту предоставить исходящий интерфейс клиенту. Клиент реализует этот интерфейс на объекте, называемом раковиной.

ATL использует [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) для реализации подключаемого объекта. Каждая точка соединения в соединимом объекте представляет собой исходящий интерфейс, идентифицированный *piid.* Класс *CDV* управляет соединениями между точкой соединения и раковиной. Каждое соединение однозначно идентифицируется "cookie".

Для получения дополнительной информации об использовании [Connection Points](../../atl/atl-connection-points.md)точек соединения в ATL, см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="iconnectionpointimpladvise"></a><a name="advise"></a>IConnectionPointImpl::Консультация

Устанавливает связь между точкой соединения и раковиной.

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>Примечания

Используйте [Unadvise](#unadvise) для завершения вызова соединения.

Смотрите [IConnectionPoint::Консультация](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) в Windows SDK.

## <a name="iconnectionpointimplenumconnections"></a><a name="enumconnections"></a>IConnectionPointImpl::EnumConnections

Создает регистратор для итерата через соединения для точки соединения.

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>Примечания

Смотрите [IConnectionPoint::EnumConnections](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) в Windows SDK.

## <a name="iconnectionpointimplgetconnectioninterface"></a><a name="getconnectioninterface"></a>IConnectionPointImpl::GetConnectionInterface

Извлекает IID интерфейса, представленного точкой соединения.

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>Примечания

Смотрите [IConnectionPoint::GetConnectionInterface](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) в Windows SDK.

## <a name="iconnectionpointimplgetconnectionpointcontainer"></a><a name="getconnectionpointcontainer"></a>IConnectionPointImpl::GetConnectionPointContainer

Извлекает указатель интерфейса на подключаемый объект.

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>Примечания

Смотрите [IConnectionPoint::GetConnectionPointContainer](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) в Windows SDK.

## <a name="iconnectionpointimplm_vec"></a><a name="m_vec"></a>IConnectionPointImpl::m_vec

Управляет соединениями между объектом точки соединения и раковиной.

```
CDV m_vec;
```

### <a name="remarks"></a>Примечания

По умолчанию, `m_vec` является [типом CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md).

## <a name="iconnectionpointimplunadvise"></a><a name="unadvise"></a>IConnectionPointImpl::Unadvise

Прекращает подключение, ранее установленное через [Advise.](#advise)

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>Примечания

Смотрите [IConnectionPoint::Unadvise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
