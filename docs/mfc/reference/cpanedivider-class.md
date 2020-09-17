---
title: Класс CPaneDivider
ms.date: 11/04/2016
f1_keywords:
- CPaneDivider
- AFXPANEDIVIDER/CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::AddPaneContainer
- AFXPANEDIVIDER/CPaneDivider::AddPane
- AFXPANEDIVIDER/CPaneDivider::AddRecentPane
- AFXPANEDIVIDER/CPaneDivider::CalcExpectedDockedRect
- AFXPANEDIVIDER/CPaneDivider::CalcFixedLayout
- AFXPANEDIVIDER/CPaneDivider::CheckVisibility
- AFXPANEDIVIDER/CPaneDivider::CreateEx
- AFXPANEDIVIDER/CPaneDivider::DoesAllowDynInsertBefore
- AFXPANEDIVIDER/CPaneDivider::DoesContainFloatingPane
- AFXPANEDIVIDER/CPaneDivider::FindPaneContainer
- AFXPANEDIVIDER/CPaneDivider::FindTabbedPane
- AFXPANEDIVIDER/CPaneDivider::GetDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::GetFirstPane
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividerStyle
- AFXPANEDIVIDER/CPaneDivider::GetRootContainerRect
- AFXPANEDIVIDER/CPaneDivider::GetWidth
- AFXPANEDIVIDER/CPaneDivider::Init
- AFXPANEDIVIDER/CPaneDivider::InsertPane
- AFXPANEDIVIDER/CPaneDivider::IsAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::IsDefault
- AFXPANEDIVIDER/CPaneDivider::IsHorizontal
- AFXPANEDIVIDER/CPaneDivider::Move
- AFXPANEDIVIDER/CPaneDivider::NotifyAboutRelease
- AFXPANEDIVIDER/CPaneDivider::OnShowPane
- AFXPANEDIVIDER/CPaneDivider::ReleaseEmptyPaneContainers
- AFXPANEDIVIDER/CPaneDivider::RemovePane
- AFXPANEDIVIDER/CPaneDivider::ReplacePane
- AFXPANEDIVIDER/CPaneDivider::RepositionPanes
- AFXPANEDIVIDER/CPaneDivider::Serialize
- AFXPANEDIVIDER/CPaneDivider::SetAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::SetPaneContainerManager
- AFXPANEDIVIDER/CPaneDivider::ShowWindow
- AFXPANEDIVIDER/CPaneDivider::StoreRecentDockSiteInfo
- AFXPANEDIVIDER/CPaneDivider::StoreRecentTabRelatedInfo
- AFXPANEDIVIDER/CPaneDivider::GetPanes
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividers
- AFXPANEDIVIDER/CPaneDivider::m_nDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::m_pSliderRTC
helpviewer_keywords:
- CPaneDivider [MFC], CPaneDivider
- CPaneDivider [MFC], AddPaneContainer
- CPaneDivider [MFC], AddPane
- CPaneDivider [MFC], AddRecentPane
- CPaneDivider [MFC], CalcExpectedDockedRect
- CPaneDivider [MFC], CalcFixedLayout
- CPaneDivider [MFC], CheckVisibility
- CPaneDivider [MFC], CreateEx
- CPaneDivider [MFC], DoesAllowDynInsertBefore
- CPaneDivider [MFC], DoesContainFloatingPane
- CPaneDivider [MFC], FindPaneContainer
- CPaneDivider [MFC], FindTabbedPane
- CPaneDivider [MFC], GetDefaultWidth
- CPaneDivider [MFC], GetFirstPane
- CPaneDivider [MFC], GetPaneDividerStyle
- CPaneDivider [MFC], GetRootContainerRect
- CPaneDivider [MFC], GetWidth
- CPaneDivider [MFC], Init
- CPaneDivider [MFC], InsertPane
- CPaneDivider [MFC], IsAutoHideMode
- CPaneDivider [MFC], IsDefault
- CPaneDivider [MFC], IsHorizontal
- CPaneDivider [MFC], Move
- CPaneDivider [MFC], NotifyAboutRelease
- CPaneDivider [MFC], OnShowPane
- CPaneDivider [MFC], ReleaseEmptyPaneContainers
- CPaneDivider [MFC], RemovePane
- CPaneDivider [MFC], ReplacePane
- CPaneDivider [MFC], RepositionPanes
- CPaneDivider [MFC], Serialize
- CPaneDivider [MFC], SetAutoHideMode
- CPaneDivider [MFC], SetPaneContainerManager
- CPaneDivider [MFC], ShowWindow
- CPaneDivider [MFC], StoreRecentDockSiteInfo
- CPaneDivider [MFC], StoreRecentTabRelatedInfo
- CPaneDivider [MFC], GetPanes
- CPaneDivider [MFC], GetPaneDividers
- CPaneDivider [MFC], m_nDefaultWidth
- CPaneDivider [MFC], m_pSliderRTC
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
ms.openlocfilehash: 0ebac4e18f65d789d5196266d57184744ad5ad28
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753630"
---
# <a name="cpanedivider-class"></a>Класс CPaneDivider

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

Класс `CPaneDivider` разделяет две панели, разделяет две группы стекол или отделяет группу стекол от области клиента окна основного кадра.

## <a name="syntax"></a>Синтаксис

```
class CPaneDivider : public CBasePane
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPaneDivider::CPaneDivider](#cpanedivider)||

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPaneDivider::AddPaneContainer](#addpanecontainer)||
|[CPaneDivider::AddPane](#addpane)||
|[CPaneDivider::AddRecentPane](#addrecentpane)||
|[CPaneDivider::CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CPaneDivider::CalcFixedLayout](#calcfixedlayout)|(Оверлет [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CPaneDivider::CheckВидимость](#checkvisibility)||
|[CPaneDivider::CreateEx](#createex)|(Переопределяет [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).)|
|[CPaneDivider::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(Переопределяет [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CPaneDivider::DoesContainFloatingPane](#doescontainfloatingpane)||
|[CPaneDivider::FindPaneContainer](#findpanecontainer)||
|[CPaneDivider::FindTabbedPane](#findtabbedpane)||
|[CPaneDivider::GetDefaultWidth](#getdefaultwidth)||
|[CPaneDivider::GetFirstPane](#getfirstpane)||
|[CPaneDivider::GetPaneDividerStyle](#getpanedividerstyle)||
|[CPaneDivider::GetRootContainerRect](#getrootcontainerrect)||
|[CPaneDivider::GetWidth](#getwidth)||
|[CPaneDivider::Init](#init)||
|[CPaneDivider::InsertPane](#insertpane)||
|[CPaneDivider::IsAutoHideMode](#isautohidemode)|(Переопределяет [CBasePane:: IsAutoHideMode](../../mfc/reference/cbasepane-class.md#isautohidemode).)|
|[CPaneDivider::IsDefault](#isdefault)||
|[CPaneDivider::IsHorizontal](#ishorizontal)|(Оверлет [CBasePane:: Горизонт.)](../../mfc/reference/cbasepane-class.md#ishorizontal)|
|[CPaneDivider::Перемещение](#move)||
|[CPaneDivider::NotifyAboutRelease](#notifyaboutrelease)||
|[CPaneDivider::OnShowPane](#onshowpane)||
|[CPaneDivider::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||
|[CPaneDivider::RemovePane](#removepane)||
|[CPaneDivider::ReplacePane](#replacepane)||
|[CPaneDivider::RepositionPanes](#repositionpanes)||
|[CPaneDivider::Serialize](#serialize)|(Переопределяет `CBasePane::Serialize`.)|
|[CPaneDivider::SetAutoHideMode](#setautohidemode)||
|[CPaneDivider::SetPaneContainerManager](#setpanecontainermanager)||
|[CPaneDivider::ShowWindow](#showwindow)||
|[CPaneDivider::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||
|[CPaneDivider::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPaneDivider:GetPanes](#getpanes)|Возвращает список стекол, которые находятся в [классе CPaneContainer.](../../mfc/reference/cpanecontainer-class.md) Этот метод следует вызывать только для разделителей панели по умолчанию.|
|[CPaneDivider:GetPaneDividers](#getpanedividers)|Возвращает список разделителей спачтом, которые находятся в [классе CPaneContainer.](../../mfc/reference/cpanecontainer-class.md) Этот метод следует вызывать только для разделителей панели по умолчанию.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CPaneDivider::m_nDefaultWidth](#m_ndefaultwidth)|Определяет ширину по умолчанию в пикселях всех разделителей панели в приложении.|
|[CPaneDivider::m_pSliderRTC](#m_psliderrtc)|Удерживает указатель на информацию класса `CPaneDivider`времени выполнения об объекте, полученном.|

## <a name="remarks"></a>Примечания

Фрейм `CPaneDivider` создает объекты автоматически при стыковке панели.

Существует два типа разделителей стекол:

- разделитель стекла по умолчанию создается, когда группа стекол пристыкована к стороне окна основной рамы. Разделитель панели по умолчанию содержит указатель на [класс CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md) и перенаправляет большинство операций на группу стекол (например, изменяя размер панели или стыковку другого стекла или контейнера) на диспетчера контейнера. Каждая стыковочные панели поддерживает указатель на его разделитель панели по умолчанию.

- Обычный разделитель стекол просто делит две стекла в контейнере. Для получения дополнительной [информации](../../mfc/reference/cpanecontainer-class.md)см.

## <a name="example"></a>Пример

В этом примере демонстрируется получение объекта `CPaneDivider` из объекта `CWorkspaceBar`. Этот фрагмент кода является частью [образца Демо-версии MDI Tabs.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Cobject](../../mfc/reference/cobject-class.md)\
&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Квн](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;[CPaneDivider](../../mfc/reference/cpanedivider-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxPaneDivider.h

## <a name="cpanedividersetautohidemode"></a><a name="setautohidemode"></a>CPaneDivider::SetAutoHideMode

```cpp
void SetAutoHideMode(BOOL bMode);
```

### <a name="parameters"></a>Параметры

(в) *bMode*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedividersetpanecontainermanager"></a><a name="setpanecontainermanager"></a>CPaneDivider::SetPaneContainerManager

```cpp
void SetPaneContainerManager(CPaneContainerManager* p);
```

### <a name="parameters"></a>Параметры

(в) *р*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedivideraddpane"></a><a name="addpane"></a>CPaneDivider::AddPane

```
virtual void AddPane(CDockablePane* pBar);
```

### <a name="parameters"></a>Параметры

(в) *pBar*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedivideraddpanecontainer"></a><a name="addpanecontainer"></a>CPaneDivider::AddPaneContainer

```
virtual BOOL AddPaneContainer(
    CPaneContainerManager& barContainerManager,
    BOOL bOuterEdge);

virtual BOOL AddPaneContainer(
    CDockablePane* pTargetBar,
    CPaneContainerManager& barContainerManager,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Параметры

(в) *barContainerManager*<br/>
(в) *bOuterEdge*<br/>
(в) *pTargetBar*<br/>
(в) *dwAlignment*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedivideraddrecentpane"></a><a name="addrecentpane"></a>CPaneDivider::AddRecentPane

```
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```

### <a name="parameters"></a>Параметры

(в) *pBar*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividercalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CPaneDivider::CalcExpectedDockedRect

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>Параметры

(в) *pWndTodock*<br/>
(в) *ptMouse*<br/>
(в) *rectResult*<br/>
(в) *bDrawTab*<br/>
(в) *ppTargetBar*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedividercalcfixedlayout"></a><a name="calcfixedlayout"></a>CPaneDivider::CalcFixedLayout

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

## <a name="cpanedividercheckvisibility"></a><a name="checkvisibility"></a>CPaneDivider::CheckВидимость

```
virtual BOOL CheckVisibility();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividercpanedivider"></a><a name="cpanedivider"></a>CPaneDivider::CPaneDivider

```
CPaneDivider();

CPaneDivider(
    BOOL bDefaultSlider,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>Параметры

(в) *bDefaultSlider*<br/>
(в) *pРодитель*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividercreateex"></a><a name="createex"></a>CPaneDivider::CreateEx

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Параметры

(в) *dwStyleEx*<br/>
(в) *dwStyle*<br/>
[in] *rect*<br/>
(в) *pParentWnd*<br/>
(в) *nID*<br/>
(в) *pКонтекст*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividerdoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CPaneDivider::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividerdoescontainfloatingpane"></a><a name="doescontainfloatingpane"></a>CPaneDivider::DoesContainFloatingPane

```
virtual BOOL DoesContainFloatingPane();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividerfindpanecontainer"></a><a name="findpanecontainer"></a>CPaneDivider::FindPaneContainer

```
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,
    BOOL& bLeftBar);
```

### <a name="parameters"></a>Параметры

(в) *pBar*<br/>
(в) *bLeftBar*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividerfindtabbedpane"></a><a name="findtabbedpane"></a>CPaneDivider::FindTabbedPane

```
CDockablePane* FindTabbedPane(UINT nID);
```

### <a name="parameters"></a>Параметры

(в) *nID*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividergetdefaultwidth"></a><a name="getdefaultwidth"></a>CPaneDivider::GetDefaultWidth

```
static int __stdcall GetDefaultWidth();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividergetfirstpane"></a><a name="getfirstpane"></a>CPaneDivider::GetFirstPane

```
const CBasePane* GetFirstPane() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividergetpanedividers"></a><a name="getpanedividers"></a>CPaneDivider:GetPaneDividers

Возвращает список разделителей спачтом, которые находятся в [классе CPaneContainer.](../../mfc/reference/cpanecontainer-class.md) Этот метод следует вызывать только для разделителей панели по умолчанию.

```cpp
void GetPaneDividers(CObList& lstSliders);
```

### <a name="parameters"></a>Параметры

*lstSliders*<br/>
(ваут) Содержит список разделителей спачтом, которые находятся в контейнере с стеклом.

### <a name="remarks"></a>Примечания

Этот метод следует вызывать только для разделителей панели по умолчанию. Разделитель панели по умолчанию является разделителем, который изменяет весь контейнер панели.

## <a name="cpanedividergetpanedividerstyle"></a><a name="getpanedividerstyle"></a>CPaneDivider::GetPaneDividerStyle

```
DWORD GetPaneDividerStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividergetpanes"></a><a name="getpanes"></a>CPaneDivider:GetPanes

Возвращает список стекол, которые находятся в [классе CPaneContainer.](../../mfc/reference/cpanecontainer-class.md) Этот метод следует вызывать только для получения разделителей панели по умолчанию.

```cpp
void GetPanes(CObList& lstBars);
```

### <a name="parameters"></a>Параметры

*lstBars*<br/>
(ваут) Содержит список стекол, которые находятся в контейнере стежка.

### <a name="remarks"></a>Примечания

Этот метод следует вызывать только для разделителей панели по умолчанию. Разделитель панели по умолчанию является разделителем, который изменяет весь контейнер панели.

## <a name="cpanedividergetrootcontainerrect"></a><a name="getrootcontainerrect"></a>CPaneDivider::GetRootContainerRect

```
CRect GetRootContainerRect();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividergetwidth"></a><a name="getwidth"></a>CPaneDivider::GetWidth

```
int GetWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividerinit"></a><a name="init"></a>CPaneDivider::Init

```cpp
void Init(
    BOOL bDefaultSlider = FALSE,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>Параметры

(в) *bDefaultSlider*<br/>
(в) *pРодитель*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedividerinsertpane"></a><a name="insertpane"></a>CPaneDivider::InsertPane

```
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,
    CDockablePane* pTargetBar,
    DWORD dwAlignment,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Параметры

(в) *pbartoInsert*<br/>
(в) *pTargetBar*<br/>
(в) *dwAlignment*<br/>
(в) *lpRect*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividerisautohidemode"></a><a name="isautohidemode"></a>CPaneDivider::IsAutoHideMode

```
BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividerisdefault"></a><a name="isdefault"></a>CPaneDivider::IsDefault

```
BOOL IsDefault() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividerishorizontal"></a><a name="ishorizontal"></a>CPaneDivider::IsHorizontal

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividerm_ndefaultwidth"></a><a name="m_ndefaultwidth"></a>CPaneDivider::m_nDefaultWidth

Определяет ширину по умолчанию в пикселях всех разделителей панели в приложении.

```
AFX_IMPORT_DATA static int m_nDefaultWidth;
```

## <a name="cpanedividermove"></a><a name="move"></a>CPaneDivider::Перемещение

```
virtual void Move(
    CPoint& ptOffset,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>Параметры

(в) *ptOffset*<br/>
(в) *bAdjustLayout*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedividerm_psliderrtc"></a><a name="m_psliderrtc"></a>CPaneDivider::m_pSliderRTC

Удерживает указатель для сведения о `CPaneDivider`классе времени выполнения объекта, полученного.

```
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;
```

### <a name="remarks"></a>Примечания

Установите эту переменную участника, если вы создаете пользовательский разделитель панели. Это позволяет фреймворку создать разделитель стекол при нарисованном стене.

### <a name="example"></a>Пример

В следующем примере показано, как установить переменную `m_pSliderRTC` участника:

```
class CMySplitter : public CPaneDivider
{
...
};

CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```

## <a name="cpanedividernotifyaboutrelease"></a><a name="notifyaboutrelease"></a>CPaneDivider::NotifyAboutRelease

```
virtual void NotifyAboutRelease();
```

### <a name="remarks"></a>Примечания

## <a name="cpanedivideronshowpane"></a><a name="onshowpane"></a>CPaneDivider::OnShowPane

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>Параметры

(в) *pBar*<br/>
(в) *bShow*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedividerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a>CPaneDivider::ReleaseEmptyPaneContainers

```cpp
void ReleaseEmptyPaneContainers();
```

### <a name="remarks"></a>Примечания

## <a name="cpanedividerremovepane"></a><a name="removepane"></a>CPaneDivider::RemovePane

```
virtual void RemovePane(CDockablePane* pBar);
```

### <a name="parameters"></a>Параметры

(в) *pBar*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedividerreplacepane"></a><a name="replacepane"></a>CPaneDivider::ReplacePane

```
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,
    CDockablePane* pBarToReplaceWith);
```

### <a name="parameters"></a>Параметры

(в) *pbartoReplace*<br/>
(в) *pbartoReplaceWith*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpanedividerrepositionpanes"></a><a name="repositionpanes"></a>CPaneDivider::RepositionPanes

```
virtual void RepositionPanes(
    CRect& rectNew,
    HDWP& hdwp);
```

### <a name="parameters"></a>Параметры

(в) *rectNew*<br/>
(в) *hdwp*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedividerserialize"></a><a name="serialize"></a>CPaneDivider::Serialize

```cpp
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

[in] *ar*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedividershowwindow"></a><a name="showwindow"></a>CPaneDivider::ShowWindow

```cpp
void ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>Параметры

(в) *nCmdShow*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedividerstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a>CPaneDivider::StoreRecentDockSiteInfo

```cpp
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```

### <a name="parameters"></a>Параметры

(в) *pBar*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpanedividerstorerecenttabrelatedinfo"></a><a name="storerecenttabrelatedinfo"></a>CPaneDivider::StoreRecentTabRelatedInfo

```cpp
void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,
    CDockablePane* pTabbedBar);
```

### <a name="parameters"></a>Параметры

(в) *pDockingBar*<br/>
(в) *pTabbedBar*<br/>

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md)<br/>
[Класс CPaneContainer](../../mfc/reference/cpanecontainer-class.md)<br/>
[Класс CDockingManager](../../mfc/reference/cdockingmanager-class.md)<br/>
[Класс CBasePane](../../mfc/reference/cbasepane-class.md)
