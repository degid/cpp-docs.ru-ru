---
title: IoleInPlaceObjectБезИмпл класс
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
ms.openlocfilehash: b0438692161f38445eb7cbed54edcc8a0ba8c0d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326578"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IoleInPlaceObjectБезИмпл класс

Этот класс `IUnknown` реализует и предоставляет методы, позволяющие бесконек управлять для приема сообщений окон и участия в операциях перетаскивания.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IOleInPlaceObjectWindowlessImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IoleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|Позволяет помощь, чувствительная к контексту. Реализация ATL возвращает E_NOTIMPL.|
|[IoleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Поставляет `IDropTarget` интерфейс для активного объекта без окон, который поддерживает перетаскивание и падение. Реализация ATL возвращает E_NOTIMPL.|
|[IoleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Получает дескриптор окна.|
|[IoleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Деактивирует активный элемент управления на месте.|
|[IoleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Отправляет сообщение из контейнера в элемент управления без окон, который находится на месте активного.|
|[IoleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Повторно активирует ранее деактивированный элемент управления. Реализация ATL возвращает E_NOTIMPL.|
|[IoleInPlacePlaceWindowlessImpl::SetObjectRects](#setobjectrects)|Указывает, какая часть элемента управления на месте видна.|
|[IoleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Деактивирует и удаляет пользовательский интерфейс, поддерживающий активацию на месте.|

## <a name="remarks"></a>Примечания

Интерфейс [IOleInPlaceObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) управляет реактивацией и деактивацией элементов управления на месте и определяет, сколько элементов управления должно быть видно. Интерфейс [IOleInPlaceObjectWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) позволяет беспривывным элементам управления окнам получать сообщения окон и участвовать в операциях перетаскивания. Класс `IOleInPlaceObjectWindowlessImpl` обеспечивает реализацию `IOleInPlaceObject` и `IOleInPlaceObjectWindowless` реализацию `IUnknown` по умолчанию и реализации путем отправки информации на устройство сброса в отладочных сборках.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IOleInPlaceObjectWindowless`

`IOleInPlaceObjectWindowlessImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="ioleinplaceobjectwindowlessimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a>IoleInPlaceObjectWindowlessImpl::ContextSensitiveHelp

Возвращает E_NOTIMPL.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="remarks"></a>Примечания

Смотрите [IOleWindow:: ContextSensitiveHelp](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) в Windows SDK.

## <a name="ioleinplaceobjectwindowlessimplgetdroptarget"></a><a name="getdroptarget"></a>IoleInPlaceObjectWindowlessImpl::GetDropTarget

Возвращает E_NOTIMPL.

```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```

### <a name="remarks"></a>Примечания

Смотрите [IOleInPlaceObjectWindowless::GetDropTarget](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-getdroptarget) в Windows SDK.

## <a name="ioleinplaceobjectwindowlessimplgetwindow"></a><a name="getwindow"></a>IoleInPlaceObjectWindowlessImpl::GetWindow

Контейнер вызывает эту функцию, чтобы получить ручку окна управления.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Примечания

Некоторые контейнеры не будут работать с элементом управления, который был без окон, даже если он в настоящее время окон. В реализации ATL, если член `m_bWasOnceWindowless` данных класса управления является истинным, функция возвращается E_FAIL. В противном случае, если *phwnd* `GetWindow` не является NULL, \* устанавливает `m_hWnd` *phwnd* к члену данных класса управления и возвращает S_OK.

Смотрите [IOleWindow::GetWindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) в Windows SDK.

## <a name="ioleinplaceobjectwindowlessimplinplacedeactivate"></a><a name="inplacedeactivate"></a>IoleInPlaceObjectWindowlessImpl::InPlaceDeactivate

Вызывается контейнером для деактивации активного управления на месте.

```
HRESULT InPlaceDeactivate(HWND* phwnd);
```

### <a name="remarks"></a>Примечания

Этот метод выполняет полную или частичную деактивацию в зависимости от состояния элемента управления. При необходимости пользовательский интерфейс элемента управления деактивирован, а окно элемента управления, если такового имеется, будет уничтожено. Контейнер уведомляется о том, что элемент управления больше не активен на месте. Интерфейс, `IOleInPlaceUIWindow` используемый контейнером для согласования меню и пограничного пространства, освобождается.

Смотрите [IOleInPlaceObject::InPlaceDeactivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) в Windows SDK.

## <a name="ioleinplaceobjectwindowlessimplonwindowmessage"></a><a name="onwindowmessage"></a>IoleInPlaceObjectWindowlessImpl::OnWindowMessage

Отправка сообщения из контейнера в управление без окон, которое находится на месте активного.

```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```

### <a name="remarks"></a>Примечания

Смотрите [IOleInPlaceObjectWindowless::OnWindowMessage](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-onwindowmessage) в Windows SDK.

## <a name="ioleinplaceobjectwindowlessimplreactivateandundo"></a><a name="reactivateandundo"></a>IoleInPlaceObjectWindowlessImpl::ReactivateAndUndo

Возвращает E_NOTIMPL.

```
HRESULT ReactivateAndUndo();
```

### <a name="remarks"></a>Примечания

Смотрите [IOleInPlaceObject::ReactivateAndUndo](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo) в Windows SDK.

## <a name="ioleinplaceobjectwindowlessimplsetobjectrects"></a><a name="setobjectrects"></a>IoleInPlacePlaceWindowlessImpl::SetObjectRects

Вызывается контейнером, чтобы сообщить диспетчеру, что его размер и/или положение изменилось.

```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```

### <a name="remarks"></a>Примечания

Обновляет элемент данных элемента `m_rcPos` управления и дисплей управления. Отображается только та часть элемента управления, которая пересекает область клипа. Если дисплей элемента управления был ранее обрезан, но отсечение было удалено, эту функцию можно вызвать, чтобы перерисовать полное представление элемента управления.

Смотрите [IOleInPlaceObject::SetObjectRects](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects) в Windows SDK.

## <a name="ioleinplaceobjectwindowlessimpluideactivate"></a><a name="uideactivate"></a>IoleInPlaceObjectWindowlessImpl::UIDeactivate

Деактивирует и удаляет пользовательский интерфейс элемента управления, поддерживающий активацию на месте.

```
HRESULT UIDeactivate();
```

### <a name="remarks"></a>Примечания

Устанавливает элемент `m_bUIActive` данных класса управления в FALSE. Реализация этой функции ATL всегда возвращает S_OK.

Смотрите [IOleInPlaceObject::UIDeactivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-uideactivate) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
