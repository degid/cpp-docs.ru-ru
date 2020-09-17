---
title: CDockSite Class
ms.date: 10/18/2018
f1_keywords:
- CDockSite
- AFXDOCKSITE/CDockSite
- AFXDOCKSITE/CDockSite::AddRow
- AFXDOCKSITE/CDockSite::AdjustDockingLayout
- AFXDOCKSITE/CDockSite::AdjustLayout
- AFXDOCKSITE/CDockSite::AlignDockSite
- AFXDOCKSITE/CDockSite::CalcFixedLayout
- AFXDOCKSITE/CDockSite::CanAcceptPane
- AFXDOCKSITE/CDockSite::CreateEx
- AFXDOCKSITE/CDockSite::CreateRow
- AFXDOCKSITE/CDockSite::DockPane
- AFXDOCKSITE/CDockSite::DoesAllowDynInsertBefore
- AFXDOCKSITE/CDockSite::FindRowIndex
- AFXDOCKSITE/CDockSite::FixupVirtualRects
- AFXDOCKSITE/CDockSite::GetDockSiteID
- AFXDOCKSITE/CDockSite::GetDockSiteRowsList
- AFXDOCKSITE/CDockSite::IsAccessibilityCompatible
- AFXDOCKSITE/CDockSite::IsDragMode
- AFXDOCKSITE/CDockSite::IsLastRow
- AFXDOCKSITE/CDockSite::IsRectWithinDockSite
- AFXDOCKSITE/CDockSite::IsResizable
- AFXDOCKSITE/CDockSite::MovePane
- AFXDOCKSITE/CDockSite::OnInsertRow
- AFXDOCKSITE/CDockSite::OnRemoveRow
- AFXDOCKSITE/CDockSite::OnResizeRow
- AFXDOCKSITE/CDockSite::OnSetWindowPos
- AFXDOCKSITE/CDockSite::OnShowRow
- AFXDOCKSITE/CDockSite::OnSizeParent
- AFXDOCKSITE/CDockSite::PaneFromPoint
- AFXDOCKSITE/CDockSite::DockPaneLeftOf
- AFXDOCKSITE/CDockSite::FindPaneByID
- AFXDOCKSITE/CDockSite::GetPaneList
- AFXDOCKSITE/CDockSite::RectSideFromPoint
- AFXDOCKSITE/CDockSite::RemovePane
- AFXDOCKSITE/CDockSite::RemoveRow
- AFXDOCKSITE/CDockSite::ReplacePane
- AFXDOCKSITE/CDockSite::RepositionPanes
- AFXDOCKSITE/CDockSite::ResizeDockSite
- AFXDOCKSITE/CDockSite::ResizeRow
- AFXDOCKSITE/CDockSite::ShowPane
- AFXDOCKSITE/CDockSite::ShowRow
- AFXDOCKSITE/CDockSite::SwapRows
helpviewer_keywords:
- CDockSite [MFC], AddRow
- CDockSite [MFC], AdjustDockingLayout
- CDockSite [MFC], AdjustLayout
- CDockSite [MFC], AlignDockSite
- CDockSite [MFC], CalcFixedLayout
- CDockSite [MFC], CanAcceptPane
- CDockSite [MFC], CreateEx
- CDockSite [MFC], CreateRow
- CDockSite [MFC], DockPane
- CDockSite [MFC], DoesAllowDynInsertBefore
- CDockSite [MFC], FindRowIndex
- CDockSite [MFC], FixupVirtualRects
- CDockSite [MFC], GetDockSiteID
- CDockSite [MFC], GetDockSiteRowsList
- CDockSite [MFC], IsAccessibilityCompatible
- CDockSite [MFC], IsDragMode
- CDockSite [MFC], IsLastRow
- CDockSite [MFC], IsRectWithinDockSite
- CDockSite [MFC], IsResizable
- CDockSite [MFC], MovePane
- CDockSite [MFC], OnInsertRow
- CDockSite [MFC], OnRemoveRow
- CDockSite [MFC], OnResizeRow
- CDockSite [MFC], OnSetWindowPos
- CDockSite [MFC], OnShowRow
- CDockSite [MFC], OnSizeParent
- CDockSite [MFC], PaneFromPoint
- CDockSite [MFC], DockPaneLeftOf
- CDockSite [MFC], FindPaneByID
- CDockSite [MFC], GetPaneList
- CDockSite [MFC], RectSideFromPoint
- CDockSite [MFC], RemovePane
- CDockSite [MFC], RemoveRow
- CDockSite [MFC], ReplacePane
- CDockSite [MFC], RepositionPanes
- CDockSite [MFC], ResizeDockSite
- CDockSite [MFC], ResizeRow
- CDockSite [MFC], ShowPane
- CDockSite [MFC], ShowRow
- CDockSite [MFC], SwapRows
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
ms.openlocfilehash: 471d68ead1bc5a11ace29f572647c4a7f2406b4e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753270"
---
# <a name="cdocksite-class"></a>CDockSite Class

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

Предоставляет функциональные возможности для упорядочения областей, которые являются производными от [CPane Class](../../mfc/reference/cpane-class.md) , в наборы строк.

## <a name="syntax"></a>Синтаксис

```
class CDockSite: public CBasePane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDockSite::AddRow](#addrow)||
|[CDockSite::AdjustDockingLayout](#adjustdockinglayout)|(Оверлет [CBasePane::AdjustDockingLayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout).)|
|[CDockSite::AdjustLayout](#adjustlayout)|(Оверлет [CBasePane::AdjustLayout](../../mfc/reference/cbasepane-class.md#adjustlayout).)|
|[CDockSite::AlignDockSite](#aligndocksite)||
|[CDockSite::CalcFixedLayout](#calcfixedlayout)|(Оверлет [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CDockSite::CanAcceptPane](#canacceptpane)|(Переопределяет [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane).)|
|[CDockSite::CreateEx](#createex)|(Переопределяет [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).)|
|[CDockSite::CreateRow](#createrow)||
|[CDockSite::DockPane](#dockpane)|(Оверлет [CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane).)|
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(Переопределяет [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CDockSite::FindRowIndex](#findrowindex)||
|[CDockSite::FixupVirtualRects](#fixupvirtualrects)||
|[CDockSite::GetDockSiteID](#getdocksiteid)||
|[CDockSite::GetDockSiteRowsList](#getdocksiterowslist)||
|[CDockSite::IsAccessibilityCompatible](#isaccessibilitycompatible)|(Переопределяет `CBasePane::IsAccessibilityCompatible`.)|
|[CDockSite::IsDragMode](#isdragmode)||
|[CDockSite::IsLastRow](#islastrow)||
|[CDockSite::IsRectWithinDockSite](#isrectwithindocksite)||
|[CDockSite::IsResizable](#isresizable)|(Переопределяет [CBasePane:: Изисуемый](../../mfc/reference/cbasepane-class.md#isresizable).)|
|[CDockSite::MovePane](#movepane)||
|[CDockSite::OnInsertRow](#oninsertrow)||
|[CDockSite::OnRemoveRow](#onremoverow)||
|[CDockSite::OnResizeRow](#onresizerow)||
|[CDockSite::OnSetWindowPos](#onsetwindowpos)||
|[CDockSite::OnShowRow](#onshowrow)||
|[CDockSite::OnSizeParent](#onsizeparent)||
|[CDockSite::PaneFromPoint](#panefrompoint)|Возвращает область, закрепленную на сайте закрепления в точке, указанной данным параметром.|
|[CDockSite::DockPaneLeftOf](#dockpaneleftof)|Закрепляет область слева от другой области.|
|[CdockSite::FindPaneByID](#findpanebyid)|Возвращает область, определенную по заданному идентификатору.|
|[CDockSite::GetPaneList](#getpanelist)|Возвращает список областей, которые закреплены на сайте закрепления.|
|[CDockSite::RectSideFromPoint](#rectsidefrompoint)||
|[CDockSite::RemovePane](#removepane)||
|[CDockSite::RemoveRow](#removerow)||
|[CDockSite::ReplacePane](#replacepane)||
|[CDockSite::RepositionPanes](#repositionpanes)||
|[CDockSite::ResizeDockSite](#resizedocksite)||
|[CDockSite::ResizeRow](#resizerow)||
|[CDockSite::ShowPane](#showpane)|Отображает область.|
|[CDockSite::ShowRow](#showrow)||
|[CDockSite::SwapRows](#swaprows)||

## <a name="remarks"></a>Примечания

Платформа создает `CDockSite` объекты автоматически при [вызове CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking). Окна сайта закрепления располагаются на границе области клиента в главном окне фрейма.

Обычно вам не нужно звонить в службы, предоставляемые сайтом док-станции, потому что [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md) обрабатывает эти службы.

## <a name="example"></a>Пример

В следующем примере показывается, как создать объект класса `CDockSite`.

[!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Cobject](../../mfc/reference/cobject-class.md)\
&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Квн](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Кдоксайт](../../mfc/reference/cdocksite-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxDockSite.h

## <a name="cdocksiteaddrow"></a><a name="addrow"></a>CDockSite::AddRow

```
CDockingPanesRow* AddRow(
    POSITION pos,
    int nHeight);
```

### <a name="parameters"></a>Параметры

(в) *pos*<br/>

(в) *nВысота*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksiteadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CdockSite::AdjustDockingLayout

```
virtual void AdjustDockingLayout();
```

### <a name="remarks"></a>Примечания

## <a name="cdocksiteadjustlayout"></a><a name="adjustlayout"></a>CdockSite:AdjustLayout

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>Примечания

## <a name="cdocksitealigndocksite"></a><a name="aligndocksite"></a>CDockSite::AlignDockSite

```cpp
void AlignDockSite(
    const CRect& rectToAlignBy,
    CRect& rectResult,
    BOOL bMoveImmediately);
```

### <a name="parameters"></a>Параметры

(в) *rectToAlignBy*<br/>

(в) *rectResult*<br/>

(в) *bMoveImmediately*<br/>

### <a name="remarks"></a>Примечания

## <a name="cdocksitecalcfixedlayout"></a><a name="calcfixedlayout"></a>CdockSite::CalcFixedLayout

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

## <a name="cdocksitecanacceptpane"></a><a name="canacceptpane"></a>CDockSite::CanAcceptPane

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Параметры

(в) *pBar*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksitecreateex"></a><a name="createex"></a>CDockSite::CreateEx

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    DWORD dwControlBarStyle,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

(в) *dwStyleEx*<br/>

(в) *dwStyle*<br/>

[in] *rect*<br/>

(в) *pParentWnd*<br/>

(в) *dwControlBarStyle*<br/>

(в) *pКонтекст*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksitecreaterow"></a><a name="createrow"></a>CDockSite::CreateRow

```
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nRowHeight);
```

### <a name="parameters"></a>Параметры

(в) *pParentDockBar*<br/>

(в) *nOffset*<br/>

(в) *nRowHeight*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksitedockpane"></a><a name="dockpane"></a>CDockSite::DockPane

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Параметры

(в) *pWnd*<br/>

(в) *докМетод*<br/>

(в) *lpRect*<br/>

### <a name="remarks"></a>Примечания

## <a name="cdocksitedockpaneleftof"></a><a name="dockpaneleftof"></a>CdockSite::DockPaneLeftOf

Закрепляет область слева от другой области.

```
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>Параметры

*пбартодок*<br/>
(в, вне) Указатель на стекол, чтобы быть пристыкован к левой части *pTargetBar*.

*pTargetBar*<br/>
(в, вне) Указатель на целевое стекло.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если панель пристыкована успешно; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cdocksitedoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CDockSite::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksitefindpanebyid"></a><a name="findpanebyid"></a>CdockSite::FindPaneByID

Возвращает панель с учетом идентификатора.

```
CPane* FindPaneByID(UINT nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
(в) Идентификатор команды панели, который будет найден.

### <a name="return-value"></a>Возвращаемое значение

Указатель на панель с указанным идентификатором команды или NULL, если панель не найдена.

### <a name="remarks"></a>Примечания

## <a name="cdocksitefindrowindex"></a><a name="findrowindex"></a>Кдоксайт::FindRowIndex

```
int FindRowIndex(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>Параметры

(в) *pRow*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksitefixupvirtualrects"></a><a name="fixupvirtualrects"></a>CDockSite::FixupVirtualRects

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>Примечания

## <a name="cdocksitegetdocksiteid"></a><a name="getdocksiteid"></a>CDockSite:GetDockSiteID

```
virtual UINT GetDockSiteID() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksitegetdocksiterowslist"></a><a name="getdocksiterowslist"></a>CDockSite::GetDockSiteRowsList

```
const CObList& GetDockSiteRowsList() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksitegetpanelist"></a><a name="getpanelist"></a>CDockSite:GetPaneList

Возвращает список стекол, которые пристыкованы к месту дока.

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Только для чтения ссылка на список стекол в настоящее время состыкован в стыковочном баре.

## <a name="cdocksiteisaccessibilitycompatible"></a><a name="isaccessibilitycompatible"></a>CDockSite::ДоступностьСовместимость

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksiteisdragmode"></a><a name="isdragmode"></a>Кдоксит::Исдрагмой

```
virtual BOOL IsDragMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksiteislastrow"></a><a name="islastrow"></a>Кдоксит::IsLastRow

```
bool IsLastRow(CDockingPanesRow* pRow) const;
```

### <a name="parameters"></a>Параметры

(в) *pRow*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksiteisrectwithindocksite"></a><a name="isrectwithindocksite"></a>CDockSite::IsRecinDockSite

```
BOOL IsRectWithinDockSite(
    CRect rect,
    CPoint& ptDelta);
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

(в) *ptDelta*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksiteisresizable"></a><a name="isresizable"></a>CDockSite::Изумного

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksitemovepane"></a><a name="movepane"></a>CDockSite:MovePane

```
virtual BOOL MovePane(
    CPane* pWnd,
    UINT nFlags,
    CPoint ptOffset);
```

### <a name="parameters"></a>Параметры

(в) *pWnd*<br/>

(в) *nФлаги*<br/>

(в) *ptOffset*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksiteoninsertrow"></a><a name="oninsertrow"></a>Кдоксит::НаИнстерроу

```
virtual void OnInsertRow(POSITION pos);
```

### <a name="parameters"></a>Параметры

(в) *pos*<br/>

### <a name="remarks"></a>Примечания

## <a name="cdocksiteonremoverow"></a><a name="onremoverow"></a>Кдоксит::ОнРумероу

```
virtual void OnRemoveRow(
    POSITION pos,
    BOOL bByShow = FALSE);
```

### <a name="parameters"></a>Параметры

(в) *pos*<br/>

(в) *bByShow*<br/>

### <a name="remarks"></a>Примечания

## <a name="cdocksiteonresizerow"></a><a name="onresizerow"></a>Cdocksite::OnResizerow

```
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,
    int nOffset);
```

### <a name="parameters"></a>Параметры

(в) *prowtoresize*<br/>

(в) *nOffset*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksiteonsizeparent"></a><a name="onsizeparent"></a>Cdocksite:OnSizeParent

```
virtual void OnSizeParent(
    CRect& rectAvailable,
    UINT nSide,
    BOOL bExpand,
    int nOffset);
```

### <a name="parameters"></a>Параметры

(в) *rectAvailable*<br/>

(в) *nSide*<br/>

(в) *bРасширить*<br/>

(в) *nOffset*<br/>

### <a name="remarks"></a>Примечания

## <a name="cdocksiteonsetwindowpos"></a><a name="onsetwindowpos"></a>Cdocksite::OnsetWindowPos

```
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,
    const CRect& rectWnd,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

(в) *pWndInsertAfter*<br/>

(в) *rectWnd*<br/>

(в) *nФлаги*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksiteonshowrow"></a><a name="onshowrow"></a>Кдоксит::OnShowrow

```
virtual void OnShowRow(
    POSITION pos,
    BOOL bShow);
```

### <a name="parameters"></a>Параметры

(в) *pos*<br/>

(в) *bShow*<br/>

### <a name="remarks"></a>Примечания

## <a name="cdocksitepanefrompoint"></a><a name="panefrompoint"></a>CDockSite::PaneFromPoint

Возвращает область, закрепленную на сайте закрепления в точке, указанной данным параметром.

```
virtual CPane* PaneFromPoint(CPoint pt);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
(в) Точка, в координатах экрана, для панели для извлечения.

### <a name="return-value"></a>Возвращаемое значение

Указатель на панель, расположенную в указанной точке или NULL, если в указанной точке не было стекол.

### <a name="remarks"></a>Примечания

## <a name="cdocksiterectsidefrompoint"></a><a name="rectsidefrompoint"></a>CDockSite::RectSideFromPoint

```
static int __stdcall RectSideFromPoint(
    const CRect& rect,
    const CPoint& point);
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

(в) *точки*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksiteremovepane"></a><a name="removepane"></a>CDockSite::RemovePane

```
virtual void RemovePane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Параметры

(в) *pWnd*<br/>

(в) *докМетод*<br/>

### <a name="remarks"></a>Примечания

## <a name="cdocksiteremoverow"></a><a name="removerow"></a>CDockSite::RemoveRow

```cpp
void RemoveRow(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>Параметры

(в) *pRow*<br/>

### <a name="remarks"></a>Примечания

## <a name="cdocksitereplacepane"></a><a name="replacepane"></a>CDockSite::ReplacePane

```
BOOL ReplacePane(
    CPane* pOldBar,
    CPane* pNewBar);
```

### <a name="parameters"></a>Параметры

(в) *pOldBar*<br/>

(в) *pNewBar*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksiterepositionpanes"></a><a name="repositionpanes"></a>CdockSite:RepositionPanes

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>Параметры

(в) *rectNewClientArea*<br/>

### <a name="remarks"></a>Примечания

## <a name="cdocksiteresizedocksite"></a><a name="resizedocksite"></a>Cdocksite:Resizedocksite

```cpp
void ResizeDockSite(
    int nNewWidth,
    int nNewHeight);
```

### <a name="parameters"></a>Параметры

(в) *nNewWidth*<br/>

(в) *nNewHeight*<br/>

### <a name="remarks"></a>Примечания

## <a name="cdocksiteresizerow"></a><a name="resizerow"></a>Кдоксит::Resizerow

```
int ResizeRow(
    CDockingPanesRow* pRow,
    int nNewSize,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>Параметры

(в) *pRow*<br/>

(в) *nNewSize*<br/>

(в) *bAdjustLayout*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cdocksiteshowpane"></a><a name="showpane"></a>CDockSite:ShowPane

Отображает область.

```
virtual BOOL ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в, вне) Указатель на панель, чтобы быть показаны или скрыты.

*bShow*<br/>
(в) TRUE указать, что панель должна быть показана; FALSE указать, что панель должна быть скрытой.

*bDelay*<br/>
(в) TRUE указать, что макет панели должен быть отложен до тех пор, пока не будет показано стекол; в противном случае, FALSE.

*bActivate*<br/>
(в) Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если панель была показана или скрыта успешно. FALSE, если указанное стекло не принадлежит этому сайту дока.

### <a name="remarks"></a>Примечания

Вызов иметод, чтобы показать или скрыть пристыкованные стекла. Как правило, вам не `CDockSite::ShowPane` нужно звонить напрямую, потому что он вызывается окном родительской рамы или базовым стеклом.

## <a name="cdocksiteshowrow"></a><a name="showrow"></a>CDockSite::ShowRow

```cpp
void ShowRow(
    CDockingPanesRow* pRow,
    BOOL bShow,
    BOOL bAdjustLayout);
```

### <a name="parameters"></a>Параметры

(в) *pRow*<br/>

(в) *bShow*<br/>

(в) *bAdjustLayout*<br/>

### <a name="remarks"></a>Примечания

## <a name="cdocksiteswaprows"></a><a name="swaprows"></a>CDockSite:SwapRows

```cpp
void SwapRows(
    CDockingPanesRow* pFirstRow,
    CDockingPanesRow* pSecondRow);
```

### <a name="parameters"></a>Параметры

(в) *pFirstRow*<br/>

(в) *pSecondRow*<br/>

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CBasePane](../../mfc/reference/cbasepane-class.md)
