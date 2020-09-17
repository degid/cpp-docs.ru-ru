---
title: Класс CFirePropNotifyEvent
ms.date: 11/04/2016
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
ms.openlocfilehash: 1dfce42176341d74ffc7d9b42f856e71b17bf4f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326967"
---
# <a name="cfirepropnotifyevent-class"></a>Класс CFirePropNotifyEvent

Этот класс предоставляет методы уведомления раковины контейнера об изменениях свойства управления.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CFirePropNotifyEvent
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFirepropNotifyEvent::FireonChanged](#fireonchanged)|(Статик) Уведомляет раковину контейнера о том, что элемент управления изменился.|
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Статик) Уведомляет раковину контейнера о том, что элемент управления вот-вот изменится.|

## <a name="remarks"></a>Примечания

`CFirePropNotifyEvent`имеет два метода, которые уведомляют раковину контейнера о том, что свойство управления изменилось или вот-вот изменится.

Если класс, реализующий элемент `IPropertyNotifySink`управления, получен из, `CFirePropNotifyEvent` методы вызываются при вызове `FireOnRequestEdit` или. `FireOnChanged` Если ваш класс управления не `IPropertyNotifySink`получен от, вызовы на эти функции возвращаются S_OK.

Для получения дополнительной информации [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md)о создании элементов управления, см.

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="cfirepropnotifyeventfireonchanged"></a><a name="fireonchanged"></a>CFirepropNotifyEvent::FireonChanged

Уведомляет все подключенные интерфейсы [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) (на каждой точке соединения объекта), что указанное свойство объекта изменилось.

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
(в) Указатель на `IUnknown` объект, отправляющий уведомление.

*dispID*<br/>
(в) Идентификация измененного свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Эту функцию можно вызвать, даже если элемент управления не поддерживает точки соединения.

## <a name="cfirepropnotifyeventfireonrequestedit"></a><a name="fireonrequestedit"></a>CFirePropNotifyEvent::FireOnRequestEdit

Уведомляет все подключенные интерфейсы [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) (на каждой точке соединения объекта), что указанное свойство объекта вот-вот изменится.

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
(в) Указатель на `IUnknown` объект, отправляющий уведомление.

*dispID*<br/>
(в) Идентификатор свойства вот-вот изменится.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Эту функцию можно вызвать, даже если элемент управления не поддерживает точки соединения.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
