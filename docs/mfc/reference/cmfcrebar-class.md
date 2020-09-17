---
title: Класс CMFCReBar
ms.date: 11/04/2016
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
helpviewer_keywords:
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
ms.openlocfilehash: 409c97aba64c97ecf0443d14a70848cc298a44ba
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749999"
---
# <a name="cmfcrebar-class"></a>Класс CMFCReBar

Объект `CMFCReBar` — это панель управления, обеспечивающая информацию о компоновке, настойчивости и состоянии для управления арматурой.
Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCReBar : public CPane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRebar:Addbar](#addbar)|Добавляет полосу к армате.|
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(Оверлет [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCReBar:CanFloat](#canfloat)|(Переопределяет [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CMFCReBar::Создание](#create)|Создает элемент управления арматом и `CMFCReBar` прикрепляет его к объекту.|
|[CMFCReBar::EnableDocking](#enabledocking)|(Переопределяет [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|
|[CMFCRebar:GetrebarBandinfosize](#getrebarbandinfosize)||
|[CMFCRebar:GetrebarCtrl](#getrebarctrl)|Обеспечивает прямой доступ к базовому общему контролю [CReBarCtrl.](../../mfc/reference/crebarctrl-class.md)|
|[CMFCRebar::OnShowControlbarMenu](#onshowcontrolbarmenu)|(Переопределяет [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCRebar::Ontoolhittest](#ontoolhittest)|(Оверлет: [OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(Оверлет [CBasePane::OnUpdateCmdUI](cbasepane-class.md).)|
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Переопределяет [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|

## <a name="remarks"></a>Примечания

Объект `CMFCReBar` может содержать различные детские окна. Это включает в себя отодевать коробки, панели инструментов и списки. Вы можете изменить размер арматы программно, или пользователь может вручную изменить размер арматы, перетащив ее сцепление бар. Вы также можете установить фон арматы объекта на бит-карту по вашему выбору.

Объект арматы ведет себя аналогично объекту панели инструментов. Элемент управления арматом может содержать одну или несколько полос, и каждая полоса может содержать планку захвата, бит-карту, текстовую этикетку и детское окно.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCReBar` . На примере показано, как создать элемент управления арматом и добавить к нему полосу. Полоса функционирует как внутренняя панель инструментов. Этот фрагмент кода является частью [образца теста Rebar.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Cobject](../../mfc/reference/cobject-class.md)\
&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Квн](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[КПэйне](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[-CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRebar.h

## <a name="cmfcrebaraddbar"></a><a name="addbar"></a>CMFCRebar:Addbar

Добавляет полосу к армате.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в, вне) Указатель на детское окно, которое должно быть вставлено в армату. Ссылка на объект должна иметь стиль **WS_CHILD** окна.

*pszText*<br/>
(в) Определяет текст, чтобы появиться на армате. Текст не является частью окна ребенка. Скорее, он отображается на самой армате.

*pbmp*<br/>
(в, вне) Определяет битную карту, которая будет отображаться на фоне арматы.

*dwStyle*<br/>
(в) Содержит стиль для применения к группе. Полный список стилей полос можно `fStyle` узнать в структуре [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) в документации Windows SDK.

*clrFore*<br/>
(в) Представляет цвет переднего плана арматы.

*clrBack*<br/>
(в) Представляет фоновый цвет арматы.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если полоса была успешно добавлена в арматру; в противном случае, FALSE.

## <a name="cmfcrebarcreate"></a><a name="create"></a>CMFCReBar::Создание

Создает элемент управления арматом и прикрепляет его к объекту [CMFCReBar.](../../mfc/reference/cmfcrebar-class.md)

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
(в, вне) Указатель на родительское окно этого элемента управления армаза.

*dwCtrlStyle*<br/>
(в) Определяет стиль управления арматом. Значение стиля по умолчанию **является RBS_BANDBORDERS,** который отображает узкие линии, чтобы отделить соседние полосы на элементе управления арматом. Список допустимых стилей [можно](/windows/win32/Controls/rebar-control-styles) узнать в документации SDK Windows.

*dwStyle*<br/>
(в) Стиль управления окнами. Список действительных стилей можно узнать в [виде стилей window.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*nID*<br/>
(в) Идентификатор ребенка-окна армабы.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если армата была создана успешно; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcrebargetrebarctrl"></a><a name="getrebarctrl"></a>CMFCRebar:GetrebarCtrl

Обеспечивает прямой `CReBarCtrl` доступ к базовому общему контролю для `CMFCReBar` объектов.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на основной `CReBarCtrl` объект.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы воспользоваться общей функциональностью управления арматой Windows при настройке армазы.

## <a name="cmfcrebarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCReBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

(в) *bStretch*<br/>
(в) *bHorz*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcrebarcanfloat"></a><a name="canfloat"></a>CMFCReBar:CanFloat

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcrebarenabledocking"></a><a name="enabledocking"></a>CMFCReBar::EnableDocking

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Параметры

(в) *dwDockStyle*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcrebargetrebarbandinfosize"></a><a name="getrebarbandinfosize"></a>CMFCRebar:GetrebarBandinfosize

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcrebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a>CMFCRebar::OnShowControlbarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Параметры

[in] *CPoint*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcrebarontoolhittest"></a><a name="ontoolhittest"></a>CMFCRebar::Ontoolhittest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>Параметры

(в) *точки*<br/>
(в) *pTI*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcrebaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCReBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Параметры

(в) *pTarget*<br/>
(в) *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcrebarsetpanealignment"></a><a name="setpanealignment"></a>CMFCReBar::SetPaneAlignment

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>Параметры

(в) *dwAlignment*<br/>

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CReBarCtrl](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane Class](../../mfc/reference/cpane-class.md)
