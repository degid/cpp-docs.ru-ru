---
title: IOleControlImpl класс
ms.date: 11/04/2016
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
ms.openlocfilehash: 947ec16e91b99cc42cff90abe7df4a5d13576e98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329624"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl класс

Этот класс обеспечивает реализацию `IOleControl` интерфейса по `IUnknown`умолчанию и реализует.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IOleControlImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IOleControlImpl::FreezeEvents](#freezeevents)|Указывает, игнорирует ли контейнер или принимает события из элемента управления.|
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Заполняет информацию о поведении клавиатуры управления. Реализация ATL возвращает E_NOTIMPL.|
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Сообщает элемент управления о том, что изменилось одно или несколько свойств окружающего контейнера. Реализация ATL возвращает S_OK.|
|[IOleControlImpl::OnMmonic](#onmnemonic)|Информирует элемент управления о том, что пользователь нажал указанный нажатие клавиши. Реализация ATL возвращает E_NOTIMPL.|

## <a name="remarks"></a>Примечания

Класс `IOleControlImpl` обеспечивает реализацию интерфейса [IOleControl](/windows/win32/api/ocidl/nn-ocidl-iolecontrol) по `IUnknown` умолчанию и реализации путем отправки информации на устройство свалки в отладочных сборках.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="iolecontrolimplfreezeevents"></a><a name="freezeevents"></a>IOleControlImpl::FreezeEvents

В реализации ATL, `FreezeEvents` приращения элемент `m_nFreezeEvents` данных `bFreeze` класса управления, если `m_nFreezeEvents` это `bFreeze` правда, и decrements, если false.

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>Примечания

`FreezeEvents`затем возвращается S_OK.

Смотрите [IOleControl::FreezeEvents](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-freezeevents) в Windows SDK.

## <a name="iolecontrolimplgetcontrolinfo"></a><a name="getcontrolinfo"></a>IOleControlImpl::GetControlInfo

Заполняет информацию о поведении клавиатуры управления.

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>Примечания

Смотрите [IOleControl:GetControlInfo](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

## <a name="iolecontrolimplonambientpropertychange"></a><a name="onambientpropertychange"></a>IOleControlImpl::OnAmbientPropertyChange

Сообщает элемент управления о том, что изменилось одно или несколько свойств окружающего контейнера.

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IOleControl::OnAmbientPropertyChange](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) в Windows SDK.

## <a name="iolecontrolimplonmnemonic"></a><a name="onmnemonic"></a>IOleControlImpl::OnMmonic

Информирует элемент управления о том, что пользователь нажал указанный нажатие клавиши.

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IOleControl::OnMmonic](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)<br/>
[Интерфейсы управления ActiveX](/windows/win32/com/activex-controls-interfaces)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
