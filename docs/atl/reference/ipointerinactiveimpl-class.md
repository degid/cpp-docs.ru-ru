---
title: IPointerInactiveImpImpl класс
ms.date: 11/04/2016
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
ms.openlocfilehash: 229b8c6803aa7b3817cb3d95474bde0502829f8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326451"
---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpImpl класс

Этот класс `IUnknown` реализует и методы интерфейса [IPointerInactive.](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive)

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IPointerInactiveImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|Извлекает текущую политику активации для объекта. Реализация ATL возвращает E_NOTIMPL.|
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|Уведомляет объект о перемещении указателя мыши по нему, указывая, что объект может стрелять событиями мыши. Реализация ATL возвращает E_NOTIMPL.|
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|Устанавливает указатель мыши для неактивного объекта. Реализация ATL возвращает E_NOTIMPL.|

## <a name="remarks"></a>Примечания

Неактивный объект — это объект, который просто загружается или работает. В отличие от активного объекта, неактивный объект не может получать сообщения с мышью и клавиатурой Windows. Таким образом, неактивные объекты используют меньше ресурсов и, как правило, более эффективны.

Интерфейс [IPointerInactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) позволяет объекту поддерживать минимальный уровень взаимодействия с мышью, оставаясь при этом неактивным. Эта функция особенно полезна для элементов управления.

Класс `IPointerInactiveImpl` реализует `IPointerInactive` методы, просто возвращая E_NOTIMPL. Тем не менее, он реализует `IUnknown` путем отправки информации на устройство свалки в отладочных сборках.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="ipointerinactiveimplgetactivationpolicy"></a><a name="getactivationpolicy"></a>IPointerInactiveImpl::GetActivationPolicy

Извлекает текущую политику активации для объекта.

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IPointerInactive::GetActivationPolicy](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) в Windows SDK.

## <a name="ipointerinactiveimploninactivemousemove"></a><a name="oninactivemousemove"></a>IPointerInactiveImpl::OnInactiveMouseMove

Уведомляет объект о перемещении указателя мыши по нему, указывая, что объект может стрелять событиями мыши.

```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IPointerInactive::OnInactiveMouseMove](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) в Windows SDK.

## <a name="ipointerinactiveimploninactivesetcursor"></a><a name="oninactivesetcursor"></a>IPointerInactiveImpl::OnInactiveSetCursor

Устанавливает указатель мыши для неактивного объекта.

```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IPointerInactive::OnInactiveSetCursor](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
