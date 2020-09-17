---
title: IPropertyNotifySinkCP класс
ms.date: 11/04/2016
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
ms.openlocfilehash: c6d98bf5a6dfe5566839eb22bcd2bab2a9c28e4d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329601"
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP класс

Этот класс предоставляет интерфейс [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) как исходящий интерфейс на подключаемом объекте.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T, class CDV = CComDynamicUnkArray>
class IPropertyNotifySinkCP
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IPropertyNotifySinkCP`.

*Cdv*<br/>
Класс, управляющий соединениями между точкой соединения и ее поглотителями. Значение по умолчанию [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), что позволяет неограниченное количество подключений. Вы также можете использовать [CComUnkArray](../../atl/reference/ccomunkarray-class.md), который определяет фиксированное количество соединений.

## <a name="remarks"></a>Примечания

`IPropertyNotifySinkCP`наследует все методы через свой базовый класс, [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).

Интерфейс [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) позволяет объекту раковины получать уведомления об изменениях свойства. Класс `IPropertyNotifySinkCP` предоставляет этот интерфейс как исходящий интерфейс на подключаемом объекте. Клиент должен реализовать `IPropertyNotifySink` методы на раковине.

Вывести свой `IPropertyNotifySinkCP` класс из того момента, когда `IPropertyNotifySink` требуется создать точку соединения, представляющую интерфейс.

Для получения дополнительной информации об использовании [Connection Points](../../atl/atl-connection-points.md)точек соединения в ATL, см.

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="see-also"></a>См. также раздел

[Класс IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)<br/>
[IConnectionPointContainerImpl класс](../../atl/reference/iconnectionpointcontainerimpl-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
