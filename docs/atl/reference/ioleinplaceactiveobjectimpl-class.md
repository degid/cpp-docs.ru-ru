---
title: IoleInPlaceActiveObjectImpL класс
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
ms.openlocfilehash: b39ba2845a5483444dac53d1616654e902969c77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326588"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>IoleInPlaceActiveObjectImpL класс

Этот класс предоставляет методы для содействия связи между управлением на месте и его контейнером.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IOleInPlaceActiveObjectImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IoleInPlaceActiveObjectImpl:ContextSensitiveHelp](#contextsensitivehelp)|Позволяет помощь, чувствительная к контексту. Реализация ATL возвращает E_NOTIMPL.|
|[IoleInPlaceActiveObjectImpl:EnableModeless](#enablemodeless)|Включает в себя бесрежимные диалоговые ящики. Реализация ATL возвращает S_OK.|
|[IoleInPlaceActiveObjectImpl::GetWindow](#getwindow)|Получает дескриптор окна.|
|[IoleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|Уведомляет элемент управления при активации или отключении окна документа контейнера. Реализация ATL возвращает S_OK.|
|[IoleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|Уведомляет элемент управления при активации или деактивации окна верхнего уровня кадра. Возврат ы реализации ATL|
|[IoleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|Информирует о контроле, необходимом для изогивания своих границ. Реализация ATL возвращает S_OK.|
|[IoleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|Обрабатывает акселератор-ключ меню сообщений из контейнера. Реализация ATL возвращает E_NOTIMPL.|

## <a name="remarks"></a>Примечания

Интерфейс [IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) помогает в общении между управлением на месте и контейнером; например, сообщение об активном состоянии элемента управления и контейнера и информирование о контроле, необходимом для изобретивания размера. Класс `IOleInPlaceActiveObjectImpl` обеспечивает реализацию `IOleInPlaceActiveObject` и `IUnknown` поддержку по умолчанию, отправляя информацию на устройство сброса в сборках отладок.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="ioleinplaceactiveobjectimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a>IoleInPlaceActiveObjectImpl:ContextSensitiveHelp

Позволяет помощь, чувствительная к контексту.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IOleWindow:: ContextSensitiveHelp](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) в Windows SDK.

## <a name="ioleinplaceactiveobjectimplenablemodeless"></a><a name="enablemodeless"></a>IoleInPlaceActiveObjectImpl:EnableModeless

Включает в себя бесрежимные диалоговые ящики.

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IOleInPlaceActiveObject::Опромновение](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless) в Windows SDK.

## <a name="ioleinplaceactiveobjectimplgetwindow"></a><a name="getwindow"></a>IoleInPlaceActiveObjectImpl::GetWindow

Контейнер вызывает эту функцию, чтобы получить ручку окна управления.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Примечания

Некоторые контейнеры не будут работать с элементом управления, который был без окон, даже если он в настоящее время окон. В реализации ATL, `CComControl::m_bWasOnceWindowless` если участник данных является правдой, функция возвращается E_FAIL. В противном случае, если \* `GetWindow` *phwnd* не является NULL, присваивает *phwnd* члену `m_hWnd` данных класса управления и возвращает S_OK.

Смотрите [IOleWindow::GetWindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) в Windows SDK.

## <a name="ioleinplaceactiveobjectimplondocwindowactivate"></a><a name="ondocwindowactivate"></a>IoleInPlaceActiveObjectImpl::OnDocWindowActivate

Уведомляет элемент управления при активации или отключении окна документа контейнера.

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IOleInPlaceActiveObject::OnDocWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) в Windows SDK.

## <a name="ioleinplaceactiveobjectimplonframewindowactivate"></a><a name="onframewindowactivate"></a>IoleInPlaceActiveObjectImpl::OnFrameWindowActivate

Уведомляет элемент управления при активации или деактивации окна верхнего уровня кадра.

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IOleInPlaceActiveObject::OnFrameWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) в Windows SDK.

## <a name="ioleinplaceactiveobjectimplresizeborder"></a><a name="resizeborder"></a>IoleInPlaceActiveObjectImpl::ResizeBorder

Информирует о контроле, необходимом для изогивания своих границ.

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IOleInPlaceActiveObject::ResizeBorder](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) в Windows SDK.

## <a name="ioleinplaceactiveobjectimpltranslateaccelerator"></a><a name="translateaccelerator"></a>IoleInPlaceActiveObjectImpl::TranslateAccelerator

Обрабатывает акселератор-ключ меню сообщений из контейнера.

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод поддерживает следующие возвращаемые значения.

S_OK, успешно ли было переведено сообщение.

S_FALSE, если сообщение не было переведено.

### <a name="remarks"></a>Примечания

Смотрите [IOleInPlaceActiveObject::TranslateAccelerator](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Интерфейсы управления ActiveX](/windows/win32/com/activex-controls-interfaces)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
