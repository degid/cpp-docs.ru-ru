---
title: IConnectionPointContainerImpl класс
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
ms.openlocfilehash: f6009a1341d6715d6d2f170d3ff2aa1aa4ffcb96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329868"
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl класс

Этот класс реализует контейнер точки соединения для управления коллекцией объектов [IConnectionPointImpl.](../../atl/reference/iconnectionpointimpl-class.md)

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IConnectionPointContainerImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Создает регистратор для итерата через точки соединения, поддерживаемые в подключаемом объекте.|
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Извлекает указатель интерфейса в точку соединения, поддерживающую указанное IID.|

## <a name="remarks"></a>Примечания

`IConnectionPointContainerImpl`реализует контейнер точки соединения для управления коллекцией объектов [IConnectionPointImpl.](../../atl/reference/iconnectionpointimpl-class.md) `IConnectionPointContainerImpl`предоставляет два метода, которые клиент может вызвать для получения дополнительной информации о подключаемых объекта:

- `EnumConnectionPoints`позволяет клиенту определить, какие исходящие интерфейсы поддерживает объект.

- `FindConnectionPoint`позволяет клиенту определить, поддерживает ли объект определенный исходящий интерфейс.

Для получения информации об использовании точек соединения в ATL, [см.](../../atl/atl-connection-points.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="iconnectionpointcontainerimplenumconnectionpoints"></a><a name="enumconnectionpoints"></a>IConnectionPointContainerImpl::EnumConnectionPoints

Создает регистратор для итерата через точки соединения, поддерживаемые в подключаемом объекте.

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>Примечания

Смотрите [IConnectionPointContainer::EnumConnectionPoints](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) в Windows SDK.

## <a name="iconnectionpointcontainerimplfindconnectionpoint"></a><a name="findconnectionpoint"></a>IConnectionPointContainerImpl::FindConnectionPoint

Извлекает указатель интерфейса в точку соединения, поддерживающую указанное IID.

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>Примечания

Смотрите [IConnectionPointContainer::FindConnectionPoint](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
