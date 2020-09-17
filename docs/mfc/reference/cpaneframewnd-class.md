---
title: Класс CPaneFrameWnd
ms.date: 11/04/2016
f1_keywords:
- CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd::AddPane
- AFXPANEFRAMEWND/CPaneFrameWnd::AddRemovePaneFromGlobalList
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustPaneFrames
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcBorderSize
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcExpectedDockedRect
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeAttached
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeDockedToPane
- AFXPANEFRAMEWND/CPaneFrameWnd::CheckGripperVisibility
- AFXPANEFRAMEWND/CPaneFrameWnd::ConvertToTabbedDocument
- AFXPANEFRAMEWND/CPaneFrameWnd::Create
- AFXPANEFRAMEWND/CPaneFrameWnd::CreateEx
- AFXPANEFRAMEWND/CPaneFrameWnd::DockPane
- AFXPANEFRAMEWND/CPaneFrameWnd::FindFloatingPaneByID
- AFXPANEFRAMEWND/CPaneFrameWnd::FrameFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionHeight
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionText
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingMode
- AFXPANEFRAMEWND/CPaneFrameWnd::GetFirstVisiblePane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::GetParent
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPinState
- AFXPANEFRAMEWND/CPaneFrameWnd::GetRecentFloatingRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetVisiblePaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::HitTest
- AFXPANEFRAMEWND/CPaneFrameWnd::IsCaptured
- AFXPANEFRAMEWND/CPaneFrameWnd::IsDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollDown
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollUp
- AFXPANEFRAMEWND/CPaneFrameWnd::KillDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::LoadState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnBeforeDock
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDockToRecentPos
- AFXPANEFRAMEWND/CPaneFrameWnd::OnKillRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnMovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::OnPaneRecalcLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::OnSetRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnShowPane
- AFXPANEFRAMEWND/CPaneFrameWnd::PaneFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::Pin
- AFXPANEFRAMEWND/CPaneFrameWnd::RedrawAll
- AFXPANEFRAMEWND/CPaneFrameWnd::RemoveNonValidPanes
- AFXPANEFRAMEWND/CPaneFrameWnd::RemovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::ReplacePane
- AFXPANEFRAMEWND/CPaneFrameWnd::SaveState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetCaptionButtons
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::SetPreDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SizeToContent
- AFXPANEFRAMEWND/CPaneFrameWnd::StartTearOff
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentDockSiteInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentTabRelatedInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::OnCheckRollState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDrawBorder
- AFXPANEFRAMEWND/CPaneFrameWnd::m_bUseSaveBits
helpviewer_keywords:
- CPaneFrameWnd [MFC], AddPane
- CPaneFrameWnd [MFC], AddRemovePaneFromGlobalList
- CPaneFrameWnd [MFC], AdjustLayout
- CPaneFrameWnd [MFC], AdjustPaneFrames
- CPaneFrameWnd [MFC], CalcBorderSize
- CPaneFrameWnd [MFC], CalcExpectedDockedRect
- CPaneFrameWnd [MFC], CanBeAttached
- CPaneFrameWnd [MFC], CanBeDockedToPane
- CPaneFrameWnd [MFC], CheckGripperVisibility
- CPaneFrameWnd [MFC], ConvertToTabbedDocument
- CPaneFrameWnd [MFC], Create
- CPaneFrameWnd [MFC], CreateEx
- CPaneFrameWnd [MFC], DockPane
- CPaneFrameWnd [MFC], FindFloatingPaneByID
- CPaneFrameWnd [MFC], FrameFromPoint
- CPaneFrameWnd [MFC], GetCaptionHeight
- CPaneFrameWnd [MFC], GetCaptionRect
- CPaneFrameWnd [MFC], GetCaptionText
- CPaneFrameWnd [MFC], GetDockingManager
- CPaneFrameWnd [MFC], GetDockingMode
- CPaneFrameWnd [MFC], GetFirstVisiblePane
- CPaneFrameWnd [MFC], GetHotPoint
- CPaneFrameWnd [MFC], GetPane
- CPaneFrameWnd [MFC], GetPaneCount
- CPaneFrameWnd [MFC], GetParent
- CPaneFrameWnd [MFC], GetPinState
- CPaneFrameWnd [MFC], GetRecentFloatingRect
- CPaneFrameWnd [MFC], GetVisiblePaneCount
- CPaneFrameWnd [MFC], HitTest
- CPaneFrameWnd [MFC], IsCaptured
- CPaneFrameWnd [MFC], IsDelayShow
- CPaneFrameWnd [MFC], IsRollDown
- CPaneFrameWnd [MFC], IsRollUp
- CPaneFrameWnd [MFC], KillDockingTimer
- CPaneFrameWnd [MFC], LoadState
- CPaneFrameWnd [MFC], OnBeforeDock
- CPaneFrameWnd [MFC], OnDockToRecentPos
- CPaneFrameWnd [MFC], OnKillRollUpTimer
- CPaneFrameWnd [MFC], OnMovePane
- CPaneFrameWnd [MFC], OnPaneRecalcLayout
- CPaneFrameWnd [MFC], OnSetRollUpTimer
- CPaneFrameWnd [MFC], OnShowPane
- CPaneFrameWnd [MFC], PaneFromPoint
- CPaneFrameWnd [MFC], Pin
- CPaneFrameWnd [MFC], RedrawAll
- CPaneFrameWnd [MFC], RemoveNonValidPanes
- CPaneFrameWnd [MFC], RemovePane
- CPaneFrameWnd [MFC], ReplacePane
- CPaneFrameWnd [MFC], SaveState
- CPaneFrameWnd [MFC], SetCaptionButtons
- CPaneFrameWnd [MFC], SetDelayShow
- CPaneFrameWnd [MFC], SetDockingManager
- CPaneFrameWnd [MFC], SetDockingTimer
- CPaneFrameWnd [MFC], SetDockState
- CPaneFrameWnd [MFC], SetHotPoint
- CPaneFrameWnd [MFC], SetPreDockState
- CPaneFrameWnd [MFC], SizeToContent
- CPaneFrameWnd [MFC], StartTearOff
- CPaneFrameWnd [MFC], StoreRecentDockSiteInfo
- CPaneFrameWnd [MFC], StoreRecentTabRelatedInfo
- CPaneFrameWnd [MFC], OnCheckRollState
- CPaneFrameWnd [MFC], OnDrawBorder
- CPaneFrameWnd [MFC], m_bUseSaveBits
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
ms.openlocfilehash: 76f7c5c2c21f0e823545db3669ce454c8172317c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753607"
---
# <a name="cpaneframewnd-class"></a>Класс CPaneFrameWnd

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

Реализует окно минифрейма, которое содержит одну область. Область заполняет собой клиентскую область окна.

## <a name="syntax"></a>Синтаксис

```
class CPaneFrameWnd : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPaneFrameWnd::AddPane](#addpane)|Добавляет панель.|
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](#addremovepanefromgloballist)|Добавляет панель в глобальный список или удаляет из него.|
|[CPaneFrameWnd::AdjustLayout](#adjustlayout)|Настраивает макет окна области.|
|[CPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)||
|[CPaneFrameWnd::CalcBorderSize](#calcbordersize)|Вычисляет размер границ окна области.|
|[CPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|Вычисляет ожидаемый прямоугольник закрепленного окна.|
|[CPaneFrameWnd::CanBeAttached](#canbeattached)|Определяет, может ли текущая панель быть закреплена на другой панели или окне фрейма.|
|[CPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|Определяет, может ли окно области быть закреплено на панели.|
|[CPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)||
|[CPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|Преобразует панель в документ с вкладками.|
|[CPaneFrameWnd::Create](#create)|Создает окно области и прикрепляет его к объекту `CPaneFrameWnd`.|
|[CPaneFrameWnd::CreateEx](#createex)|Создает окно области и прикрепляет его к объекту `CPaneFrameWnd`.|
|[CPaneFrameWnd::DockPane](#dockpane)|Закрепляет область.|
|[CPaneFrameWnd::FindFloatingPaneByID](#findfloatingpanebyid)|Находит в глобальном списке плавающих панелей панель с указанным идентификатором элемента управления.|
|[CPaneFrameWnd::FrameFromPoint](#framefrompoint)|Находит окно области, содержащее предоставленную пользователем точку.|
|[CPaneFrameWnd::GetCaptionHeight](#getcaptionheight)|Возвращает высоту заголовка окна области.|
|[CPaneFrameWnd::GetCaptionRect](#getcaptionrect)|Вычисляет ограничивающий прямоугольник заголовка окна области.|
|[CPaneFrameWnd::GetCaptionText](#getcaptiontext)|Возвращает текст заголовка.|
|[CPaneFrameWnd::GetDockingManager](#getdockingmanager)||
|[CPaneFrameWnd::GetDockingMode](#getdockingmode)|Возвращает режим закрепления.|
|[CPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|Возвращает первую видимую панель, содержащуюся в окне области.|
|[CPaneFrameWnd::GetHotPoint](#gethotpoint)||
|[CPaneFrameWnd::GetPane](#getpane)|Возвращает панель, содержащуюся в окне области.|
|[CPaneFrameWnd::GetPaneCount](#getpanecount)|Возвращает число панелей, содержащихся в окне области.|
|[CPaneFrameWnd::GetParent](#getparent)||
|[CPaneFrameWnd::GetPinState](#getpinstate)||
|[CPaneFrameWnd::GetRecentFloatingRect](#getrecentfloatingrect)||
|[CPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|Возвращает число видимых панелей, содержащихся в окне области.|
|[CPaneFrameWnd::HitTest](#hittest)|Определяет, какая часть окна области находится в заданной точке.|
|[CPaneFrameWnd::IsCaptured](#iscaptured)||
|[CPaneFrameWnd::IsDelayShow](#isdelayshow)||
|[CPaneFrameWnd::IsRollDown](#isrolldown)|Определяет, требуется ли развертывание окна области.|
|[CPaneFrameWnd::IsRollUp](#isrollup)|Определяет, требуется ли свертывание окна области.|
|[CPaneFrameWnd::KillDockingTimer](#killdockingtimer)|Останавливает таймер закрепления.|
|[CPaneFrameWnd::LoadState](#loadstate)|Загружает состояние панели из реестра.|
|[CPaneFrameWnd::OnBeforeDock](#onbeforedock)|Определяет возможность закрепления.|
|[CPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|Закрепляет окно области в его последней позиции.|
|[CPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|Останавливает таймер свертки.|
|[CPaneFrameWnd::OnMovePane](#onmovepane)|Смещает окно области на указанное расстояние.|
|[CPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|Настраивает макет содержащейся панели.|
|[CPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|Устанавливает таймер свертки.|
|[CPaneFrameWnd::OnShowPane](#onshowpane)|Вызывается платформой при скрытии или отображении панели в окне области.|
|[CPaneFrameWnd::PaneFromPoint](#panefrompoint)|Возвращает панель, если она содержит предоставленную пользователем точку в пределах окна области.|
|[CPaneFrameWnd::Pin](#pin)||
|`CPaneFrameWnd::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для преобразования сообщений окна перед их передачей функциям Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) .|
|[CPaneFrameWnd::RedrawAll](#redrawall)|Перерисовывает все окна областей.|
|[CPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|Вызывается платформой для удаления недопустимых панелей.|
|[CPaneFrameWnd::RemovePane](#removepane)|Удаляет панель из окна области.|
|[CPaneFrameWnd::ReplacePane](#replacepane)|Заменяет одну панель другой.|
|[CPaneFrameWnd::SaveState](#savestate)|Сохраняет состояние панели в реестр.|
|`CPaneFrameWnd::Serialize`|Считывает этот объект из архива или записывает в него.|
|[CPaneFrameWnd::SetCaptionButtons](#setcaptionbuttons)|Задает кнопки заголовка.|
|[CPaneFrameWnd::SetDelayShow](#setdelayshow)||
|[CPaneFrameWnd::SetDockingManager](#setdockingmanager)||
|[CPaneFrameWnd::SetDockingTimer](#setdockingtimer)|Устанавливает таймер закрепления.|
|[CPaneFrameWnd::SetDockState](#setdockstate)|Задает состояние закрепления.|
|[CPaneFrameWnd::SetHotPoint](#sethotpoint)||
|[CPaneFrameWnd::SetPreDockState](#setpredockstate)|Вызывается платформой для задания предварительного состояния закрепления.|
|[CPaneFrameWnd::SizeToContent](#sizetocontent)|Делает размер окна области равным размеру содержащейся в нем панели.|
|[CPaneFrameWnd::StartTearOff](#starttearoff)|Делает меню перемещаемым.|
|[CPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|Определяет, требуется ли свертывание или развертывание окна области.|
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|Рисует границы окна области.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|Определяется, следует ли регистрировать класс окон в стиле CS_SAVEBITS класса.|

## <a name="remarks"></a>Примечания

Когда панель переходит из закрепленного состояния в плавающее, платформа автоматически создает объект `CPaneFrameWnd`.

Окно области можно перетащить вместе с его видимым содержимым (немедленное закрепление) или с помощью прямоугольника перетаскивания (стандартное закрепление). Режим закрепления панели контейнера окна области определяет поведение окна области при перетаскивании. Для получения дополнительной информации [см. CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).

В заголовке окна области отображаются кнопки, зависящие от стиля включенной панели. Если панель может быть закрыта [(CBasePane::CanBeClosed),](../../mfc/reference/cbasepane-class.md#canbeclosed)он отображает кнопку "Закрыть". Если панель имеет AFX_CBRS_AUTO_ROLLUP стиль, он отображает булавку.

Если вы получаете производный класс из класса `CPaneFrameWnd`, необходимо сообщить платформе способ его создания. Либо создайте класс, переопределив [CPane::CreateDefaultMiniframe,](../../mfc/reference/cpane-class.md#createdefaultminiframe)либо установите `CPane::m_pMiniFrameRTC` участника так, чтобы он указал на информацию о классе времени выполнения для вашего класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPaneFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxPaneFrameWnd.h

## <a name="cpaneframewndaddpane"></a><a name="addpane"></a>CPaneFrameWnd::AddPane

Добавляет панель.

```
virtual void AddPane(CBasePane* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Панель для добавления.

## <a name="cpaneframewndaddremovepanefromgloballist"></a><a name="addremovepanefromgloballist"></a>CPaneFrameWnd::AddRemovePaneFromGlobalList

Добавляет панель в глобальный список или удаляет из него.

```
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,
    BOOL bAdd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Панель для добавления или удаления.

*bAdd*<br/>
(в) Если ненулевой, добавить панель. Если 0, удалите панель.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод был успешным; в противном случае 0.

## <a name="cpaneframewndadjustlayout"></a><a name="adjustlayout"></a>CPaneFrameWnd::AdjustLayout

Настраивает макет окна области.

```
virtual void AdjustLayout();
```

## <a name="cpaneframewndadjustpaneframes"></a><a name="adjustpaneframes"></a>CPaneFrameWnd::AdjustPaneFrames

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndcalcbordersize"></a><a name="calcbordersize"></a>CPaneFrameWnd::CalcBorderSize

Вычисляет размер границ для окна мини-кадра.

```
virtual void CalcBorderSize(CRect& rectBorderSize) const;
```

### <a name="parameters"></a>Параметры

*rectBorderSize*<br/>
(ваут) Содержит размер в пикселях границы окна мини-кадра.

### <a name="remarks"></a>Примечания

Этот метод вызывается фреймворкой для расчета размера границы окна мини-кадра. Возвращающееся размер зависит от того, содержит ли окно miniframe панель инструментов или [CDockablePane.](../../mfc/reference/cdockablepane-class.md)

## <a name="cpaneframewndcalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CPaneFrameWnd::CalcExpectedDockedRect

Вычисляет ожидаемый прямоугольник закрепленного окна.

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>Параметры

*pWndTodock*<br/>
(в) Указатель на окно для стыковки.

*ptMouse*<br/>
(в) Расположение мыши.

*rectResult*<br/>
(ваут) Расчетный прямоугольник.

*bDrawTab*<br/>
(ваут) Если правда, нарисуйте вкладку. Если FALSE, не рисуйте вкладку.

*ppTargetBar*<br/>
(ваут) Указатель на целевое стекло.

### <a name="remarks"></a>Примечания

Этот метод вычисляет прямоугольник, который занимал бы окно, если пользователь перетащил окно в точку, указанную *ptMouse,* и пристыковал его туда.

## <a name="cpaneframewndcanbeattached"></a><a name="canbeattached"></a>CPaneFrameWnd::CanBeattached

Определяет, может ли текущая панель быть закреплена на другой панели или окне фрейма.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если панель может быть пристыкована к другому сну или окне рамы; в противном случае FALSE.

## <a name="cpaneframewndcanbedockedtopane"></a><a name="canbedockedtopane"></a>CPaneFrameWnd::CanBeDockedToPane

Определяет, может ли окно области быть закреплено на панели.

```
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;
```

### <a name="parameters"></a>Параметры

*pDockingBar*<br/>
(в) Панель.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если мини-рамка может быть пристыкована к *pDockingBar;* в противном случае 0.

## <a name="cpaneframewndcheckgrippervisibility"></a><a name="checkgrippervisibility"></a>CPaneFrameWnd::CheckGripperВидимость

```
virtual void CheckGripperVisibility();
```

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>CPaneFrameWnd::ConvertToTabbedDocument

Преобразует панель в документ с вкладками.

```
virtual void ConvertToTabbedDocument();
```

## <a name="cpaneframewndcreate"></a><a name="create"></a>CPaneFrameWnd::Создание

Создает окно мини-кадра и прикрепляет его к объекту [CPaneFrameWnd.](../../mfc/reference/cpaneframewnd-class.md)

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*lpszWindowName*<br/>
(в) Определяет текст для отображения на окне мини-кадра.

*dwStyle*<br/>
(в) Определяет стиль окна. Для получения дополнительной информации [см.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*rect*<br/>
(в) Определяет начальный размер и положение окна мини-кадра.

*pParentWnd*<br/>
(в, вне) Определяет родительский кадр окна мини-кадра. Это значение не должно быть NULL.

*pContext*<br/>
(в, вне) Определяет пользовательский контекст.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если окно было создано успешно; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Окно мини-кадра создается в два этапа. Во-первых, фреймворк `CPaneFrameWnd` создает объект. Во-вторых, он призывает `Create` создать окно миникадровой системы Windows и прикрепить его к объекту. `CPaneFrameWnd`

## <a name="cpaneframewndcreateex"></a><a name="createex"></a>CPaneFrameWnd::CreateEx

Создает окно мини-кадра и прикрепляет его к объекту [CPaneFrameWnd.](../../mfc/reference/cpaneframewnd-class.md)

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>Параметры

*dwStyleEx*<br/>
(в) Определяет расширенный стиль окна. Для получения дополнительной информации [см.](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)

*lpszWindowName*<br/>
(в) Определяет текст для отображения на окне мини-кадра.

*dwStyle*<br/>
(в) Определяет стиль окна. Для получения дополнительной информации [см.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*rect*<br/>
(в) Определяет начальный размер и положение окна мини-кадра.

*pParentWnd*<br/>
(в, вне) Определяет родительский кадр окна мини-кадра. Это значение не должно быть NULL.

*pContext*<br/>
(в, вне) Определяет пользовательский контекст.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если окно было создано успешно; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Окно мини-кадра создается в два этапа. Во-первых, фреймворк `CPaneFrameWnd` создает объект. Во-вторых, он призывает `Create` создать окно миникадровой системы Windows и прикрепить его к объекту. `CPaneFrameWnd`

## <a name="cpaneframewnddockpane"></a><a name="dockpane"></a>CPaneFrameWnd::DockPane

Закрепляет область.

```
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```

### <a name="parameters"></a>Параметры

*bWasDocked*<br/>
(ваут) ПРАВДА, если панель была уже пристыкована; в противном случае FALSE.

### <a name="return-value"></a>Возвращаемое значение

Если операция была успешной, то, `CDockablePane` что стекло было пристыковано к; в противном случае NULL.

## <a name="cpaneframewndfindfloatingpanebyid"></a><a name="findfloatingpanebyid"></a>CPaneFrameWnd::FindFloatingPaneByID

Находит в глобальном списке плавающих панелей панель с указанным идентификатором элемента управления.

```
static CBasePane* FindFloatingPaneByID(UINT nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
(в) Представляет идентификатор управления панели для поиска.

### <a name="return-value"></a>Возвращаемое значение

Панель с указанным идентификатором управления; в противном случае, NULL, если ни одно стекло не имеет указанного идентификатора управления.

## <a name="cpaneframewndframefrompoint"></a><a name="framefrompoint"></a>CPaneFrameWnd::FrameFromPoint

Находит окно мини-рамки, содержащее указанную точку.

```
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,
    int nSensitivity,
    CPaneFrameWnd* pFrameToExclude = NULL,
    BOOL bFloatMultiOnly = FALSE);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
(в) Точка, в координатах экрана.

*nЧувствительность*<br/>
(в) Увеличьте область поиска окна мини-рамки на этот размер. Окно мини-рамки удовлетворяет критериям поиска, если заданная точка попадает в увеличенную область.

*pFrameToExclude*<br/>
(в) Определяет окно мини-рамки, чтобы исключить из поиска.

*bFloatMultiТолько*<br/>
(в) Если правда, только поиск мини-рамки окна, которые имеют CBRS_FLOAT_MULTI стиль. Если FALSE, поиск всех мини-рамки окна.

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно мини-рамки, содержащее *pt;* в противном случае NULL.

## <a name="cpaneframewndgetcaptionheight"></a><a name="getcaptionheight"></a>CPaneFrameWnd::GetCaptionHeight

Возвращает высоту заголовка окна области.

```
virtual int GetCaptionHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Высота, в пикселях, окна мини-кадра.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы определить высоту окна мини-рамки. По умолчанию высота установлена на SM_CYSMCAPTION. Для получения дополнительной [GetSystemMetrics Function](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)информации см.

## <a name="cpaneframewndgetcaptionrect"></a><a name="getcaptionrect"></a>CPaneFrameWnd::GetCaptionRect

Вычисляет ограничивающий прямоугольник заголовка окна области.

```
virtual void GetCaptionRect(CRect& rectCaption) const;
```

### <a name="parameters"></a>Параметры

*rectCaption*<br/>
(ваут) Содержит размер и положение подписи окна мини-рамки в координатах экрана.

### <a name="remarks"></a>Примечания

Этот метод вызывается фреймворцом для расчета связующего прямоугольника подписи окна мини-рамки.

## <a name="cpaneframewndgetcaptiontext"></a><a name="getcaptiontext"></a>CPaneFrameWnd::GetCaptionText

Возвращает текст заголовка.

```
virtual CString GetCaptionText();
```

### <a name="return-value"></a>Возвращаемое значение

Заголовок текста окна мини-рамки.

### <a name="remarks"></a>Примечания

Этот метод вызывается фректовом при отображении текста подписи.

## <a name="cpaneframewndgetdockingmanager"></a><a name="getdockingmanager"></a>CPaneFrameWnd::GetDockingManager

```
CDockingManager* GetDockingManager() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndgetdockingmode"></a><a name="getdockingmode"></a>CPaneFrameWnd::GetDockingMode

Возвращает режим закрепления.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Режим стыковки. Одно из следующих значений:

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

## <a name="cpaneframewndgetfirstvisiblepane"></a><a name="getfirstvisiblepane"></a>CPaneFrameWnd::GetFirstVisiblePane

Возвращает первую видимую панель, содержащуюся в окне области.

```
virtual CWnd* GetFirstVisiblePane() const;
```

### <a name="return-value"></a>Возвращаемое значение

Первое стекло в окне мини-кадра, или NULL, если окно мини-рамки не содержит стекол.

## <a name="cpaneframewndgethotpoint"></a><a name="gethotpoint"></a>CPaneFrameWnd::GetHotPoint

```
CPoint GetHotPoint() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndgetpane"></a><a name="getpane"></a>CPaneFrameWnd::GetPane

Возвращает панель, содержащуюся в окне области.

```
virtual CWnd* GetPane() const;
```

### <a name="return-value"></a>Возвращаемое значение

Панель, содержащаяся в мини-кадре, или NULL, если окно мини-рамки не содержит стекол.

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndgetpanecount"></a><a name="getpanecount"></a>CPaneFrameWnd::GetPaneCount

Возвращает число панелей, содержащихся в окне области.

```
virtual int GetPaneCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество стекол в окне мини-кадра. Это значение может быть равно 0.

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndgetparent"></a><a name="getparent"></a>CPaneFrameWnd::GetParent

```
CWnd* GetParent();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndgetpinstate"></a><a name="getpinstate"></a>CPaneFrameWnd::GetPinState

```
BOOL GetPinState() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndgetrecentfloatingrect"></a><a name="getrecentfloatingrect"></a>CPaneFrameWnd::GetRecentFloatingRect

```
CRect GetRecentFloatingRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndgetvisiblepanecount"></a><a name="getvisiblepanecount"></a>CPaneFrameWnd::GetVisiblePaneCount

Возвращает число видимых панелей, содержащихся в окне области.

```
virtual int GetVisiblePaneCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество видимых стекол.

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndhittest"></a><a name="hittest"></a>CPaneFrameWnd::HitTest

Определяет, какая часть окна области находится в заданной точке.

```
virtual LRESULT HitTest(
    CPoint point,
    BOOL bDetectCaption);
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
[in] Точка для проверки.

*bDetectCaption*<br/>
(в) Если true, проверьте точку против подписи. Если FALSE, игнорируйте подпись.

### <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений:

|Значение|Значение|
|-----------|-------------|
|HTNOWHERE|Точка находится за окном мини-рамки.|
|HTclient|Дело в клиентской области.|
|HTcaption caption|Точка на заголовок.|
|HTTOP|Точка находится на вершине.|
|HTTOPLEFT|Точка находится в левом верхнем верхнем.|
|HTTOPRIGHT|Точка находится в правом верхнем.|
|HTLEFT|Точка слева.|
|HTRIGHT|Точка справа.|
|HTBOTTOM|Точка внизу.|
|HTBOTTOMLEFT|Точка находится в левом нижнем углу.|
|HTBOTTOMRIGHT|Точка находится в правом нижнем углу.|

## <a name="cpaneframewndiscaptured"></a><a name="iscaptured"></a>CPaneFrameWnd::Захваченный

```
BOOL IsCaptured() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndisdelayshow"></a><a name="isdelayshow"></a>CPaneFrameWnd::IsDelayShow

```
BOOL IsDelayShow() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndisrolldown"></a><a name="isrolldown"></a>CPaneFrameWnd::IsRollDown

Определяет, требуется ли развертывание окна области.

```
virtual BOOL IsRollDown() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если окно мини-рамки должно быть свернуто; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается фректовом, чтобы определить, следует ли свернуть окно мини-рамки. Функция свертывания/свертывания включена для окна мини-кадра, если оно содержит по крайней мере одно стекло, которое имеет AFX_CBRS_AUTO_ROLLUP флаг. Этот флаг устанавливается при создании панели. Для получения дополнительной информации [см. CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).

По умолчанию фреймворк проверяет, находится ли указатель мыши внутри прямоугольника окна мини-рамки, чтобы определить, нужно ли скатывать окно вниз. Это поведение можно переопределить в производном классе.

## <a name="cpaneframewndisrollup"></a><a name="isrollup"></a>CPaneFrameWnd::IsRollUp

Определяет, требуется ли свертывание окна области.

```
virtual BOOL IsRollUp() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если окно мини-рамки должно быть свернуто; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается фректовом, чтобы определить, следует ли свернуть окно мини-рамки. Функция свертывания/свертывания включена для окна мини-кадра, если оно содержит по крайней мере одно стекло, которое имеет AFX_CBRS_AUTO_ROLLUP флаг. Этот флаг устанавливается при создании панели. Для получения дополнительной информации [см. CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).

По умолчанию фреймворк проверяет, находится ли указатель мыши внутри прямоугольника окна мини-рамки, чтобы определить, нужно ли свернуть окно. Это поведение можно переопределить в производном классе.

## <a name="cpaneframewndkilldockingtimer"></a><a name="killdockingtimer"></a>CPaneFrameWnd::KillDockingTimer

Останавливает таймер закрепления.

```cpp
void KillDockingTimer();
```

## <a name="cpaneframewndloadstate"></a><a name="loadstate"></a>CPaneFrameWnd::LoadState

Загружает состояние панели из реестра.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Имя профиля.

*uiID*<br/>
(в) Идентификатор панели.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если состояние панели было загружено успешно; в противном случае FALSE.

## <a name="cpaneframewndm_busesavebits"></a><a name="m_busesavebits"></a>CPaneFrameWnd::m_bUseSaveBits

Определяется, следует ли регистрировать класс окон, который имеет стиль CS_SAVEBITS класса.

```
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;
```

### <a name="remarks"></a>Примечания

Установите этот статический член к TRUE, чтобы зарегистрировать класс окна мини-рамки, который имеет CS_SAVEBITS стиль. Это может помочь уменьшить мерцание, когда пользователь перетаскивает окно мини-рамки.

## <a name="cpaneframewndonbeforedock"></a><a name="onbeforedock"></a>CPaneFrameWnd::OnBeforeDock

Определяет возможность закрепления.

```
virtual BOOL OnBeforeDock();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если стыковка возможна; в противном случае, FALSE.

## <a name="cpaneframewndoncheckrollstate"></a><a name="oncheckrollstate"></a>CPaneFrameWnd::OnCheckRollState

Определяет, требуется ли свертывание или развертывание окна области.

```
virtual void OnCheckRollState();
```

### <a name="remarks"></a>Примечания

Этот метод вызывается фректовом, чтобы определить, следует ли свернуть окно мини-рамки вверх или вниз.

По умолчанию фреймворк вызывает [CPaneFrameWnd::IsRollUp](#isrollup) и [CPaneFrameWnd:::IsRollDown](#isrolldown) и просто растягивает или восстанавливает окно мини-рамки. Вы можете переопределить этот метод в производном классе, чтобы использовать другой визуальный эффект.

## <a name="cpaneframewndondocktorecentpos"></a><a name="ondocktorecentpos"></a>CPaneFrameWnd::OndockToRecentPos

Закрепляет окно области в его последней позиции.

```
virtual void OnDockToRecentPos();
```

## <a name="cpaneframewndondrawborder"></a><a name="ondrawborder"></a>CPaneFrameWnd::OnDrawBorder

Рисует границы окна области.

```
virtual void OnDrawBorder(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Контекст устройства, используемый для рисования границы.

### <a name="remarks"></a>Примечания

Этот метод называется фреймворком для рисования границ окна мини-рамки.

## <a name="cpaneframewndonkillrolluptimer"></a><a name="onkillrolluptimer"></a>CPaneFrameWnd::OnKillRollUpTimer

Останавливает таймер свертки.

```
virtual void OnKillRollUpTimer();
```

## <a name="cpaneframewndonmovepane"></a><a name="onmovepane"></a>CPaneFrameWnd::OnMovePane

Смещает окно области на указанное расстояние.

```
virtual void OnMovePane(
    CPane* pBar,
    CPoint ptOffset);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в) Указатель на панель (игнорирован).

*ptOffset*<br/>
(в) Смещение, с помощью которого для перемещения панели.

## <a name="cpaneframewndonpanerecalclayout"></a><a name="onpanerecalclayout"></a>CPaneFrameWnd::OnPaneRecalcLayout

Регулирует расположение панели внутри окна мини-рамки.

```
virtual void OnPaneRecalcLayout();
```

### <a name="remarks"></a>Примечания

Рамка вызывает этот метод, когда он должен настроить макет панели внутри окна мини-рамки.

По умолчанию панель расположена для покрытия всей клиентской области окна мини-кадра.

## <a name="cpaneframewndonsetrolluptimer"></a><a name="onsetrolluptimer"></a>CPaneFrameWnd::OnSetRollUpTimer

Устанавливает таймер свертки.

```
virtual void OnSetRollUpTimer();
```

## <a name="cpaneframewndonshowpane"></a><a name="onshowpane"></a>CPaneFrameWnd::OnShowPane

Вызывается платформой при скрытии или отображении панели в окне области.

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в) Панель, которая отображается или скрыта.

*bShow*<br/>
(в) ПРАВДА, если панель отображается; FALSE, если панель скрыта.

### <a name="remarks"></a>Примечания

Вызывается фреймворком, когда панель в окне мини-рамки отображается или скрыта. Реализация по умолчанию не выполняет никаких действий.

## <a name="cpaneframewndpin"></a><a name="pin"></a>CPaneFrameWnd::Pin

```cpp
void Pin(BOOL bPin = TRUE);
```

### <a name="parameters"></a>Параметры

(в) *bПин*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndpanefrompoint"></a><a name="panefrompoint"></a>CPaneFrameWnd::PaneFromPoint

Возвращает панель, если она содержит предоставленную пользователем точку в пределах окна области.

```
virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    BOOL bCheckVisibility);
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
(в) Точка, которую пользователь нажал, в координатах экрана.

*nЧувствительность*<br/>
(в) Этот параметр не используется.

*bCheckВидимость*<br/>
(в) TRUE указать, что только видимые стекла должны быть возвращены; в противном случае, FALSE.

### <a name="return-value"></a>Возвращаемое значение

Панель, которую пользователь нажал, или NULL, если в этом месте нет панели.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить панель, содержащую заданную точку.

## <a name="cpaneframewndredrawall"></a><a name="redrawall"></a>CPaneFrameWnd::RedrawAll

Перерисовывает все окна областей.

```
static void RedrawAll();
```

### <a name="remarks"></a>Примечания

Этот метод обновляет все окна мини-рамки, вызывая [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) для каждого окна.

## <a name="cpaneframewndremovenonvalidpanes"></a><a name="removenonvalidpanes"></a>CPaneFrameWnd::RemoveNonValidPanes

Вызывается платформой для удаления недопустимых панелей.

```
virtual void RemoveNonValidPanes();
```

## <a name="cpaneframewndremovepane"></a><a name="removepane"></a>CPaneFrameWnd::RemovePane

Удаляет панель из окна области.

```
virtual void RemovePane(
    CBasePane* pWnd,
    BOOL bDestroy = FALSE,
    BOOL bNoDelayedDestroy = FALSE);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Указатель на панель для удаления.

*bDestroy*<br/>
(в) Определяет, что происходит с окном мини-рамки. Если *bDestroy* является правдой, этот метод разрушает окно мини-рамки немедленно. Если это FALSE, этот метод разрушает окно мини-рамки после определенной задержки.

*bNoDelayedDestroy*<br/>
(в) Если правда, задержки уничтожения отключен. Если FALSE, задержка уничтожения включена.

### <a name="remarks"></a>Примечания

Рамки могут уничтожить окна мини-рамки сразу или после определенной задержки. Если вы хотите отсрочить разрушение окон мини-рам, пройдите FALSE в параметре *bNoDelayedDestroy.* Задержка разрушения происходит, когда фреймворк обрабатывает AFX_WM_CHECKEMPTYMINIFRAME сообщение.

## <a name="cpaneframewndreplacepane"></a><a name="replacepane"></a>CPaneFrameWnd::ReplacePane

Заменяет одну панель другой.

```
virtual void ReplacePane(
    CBasePane* pBarOrg,
    CBasePane* pBarReplaceWith);
```

### <a name="parameters"></a>Параметры

*pBarOrg*<br/>
(в) Указатель на исходное стекло.

*pBarReplaceWith*<br/>
(в) Указатель на панель, которая заменяет исходное стекло.

## <a name="cpaneframewndsavestate"></a><a name="savestate"></a>CPaneFrameWnd::SaveState

Сохраняет состояние панели в реестр.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Имя профиля.

*uiID*<br/>
(в) Идентификатор панели.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если состояние панели было сохранено успешно; в противном случае FALSE.

## <a name="cpaneframewndsetcaptionbuttons"></a><a name="setcaptionbuttons"></a>CPaneFrameWnd::SetCaptionButtons

Задает кнопки заголовка.

```
virtual void SetCaptionButtons(DWORD dwButtons);
```

### <a name="parameters"></a>Параметры

*dwButtons*<br/>
(в) Bitwise-OR сочетание следующих значений:

- AFX_CAPTION_BTN_CLOSE

- AFX_CAPTION_BTN_PIN

- AFX_CAPTION_BTN_MENU

- AFX_CAPTION_BTN_CUSTOMIZE

## <a name="cpaneframewndsetdelayshow"></a><a name="setdelayshow"></a>CPaneFrameWnd::SetDelayShow

```cpp
void SetDelayShow(BOOL bDelayShow);
```

### <a name="parameters"></a>Параметры

(в) *bDelayShow*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndsetdockingmanager"></a><a name="setdockingmanager"></a>CPaneFrameWnd::SetDockingManager

```cpp
void SetDockingManager(CDockingManager* pManager);
```

### <a name="parameters"></a>Параметры

(в) *pManager*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndsetdockingtimer"></a><a name="setdockingtimer"></a>CPaneFrameWnd::SetDockingTimer

Устанавливает таймер закрепления.

```cpp
void SetDockingTimer(UINT nTimeOut);
```

### <a name="parameters"></a>Параметры

*nTimeOut*<br/>
(в) Значение тайм-аута в миллисекундах.

## <a name="cpaneframewndsetdockstate"></a><a name="setdockstate"></a>CPaneFrameWnd::SetDockState

Задает состояние закрепления.

```
virtual void SetDockState(CDockingManager* pDockManager);
```

### <a name="parameters"></a>Параметры

*pDockManager*<br/>
(в) Указатель на менеджера по стыковке.

## <a name="cpaneframewndsethotpoint"></a><a name="sethotpoint"></a>CPaneFrameWnd::SetHotPoint

```cpp
void SetHotPoint(CPoint& ptNew);
```

### <a name="parameters"></a>Параметры

(в) *ptNew*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndsetpredockstate"></a><a name="setpredockstate"></a>CPaneFrameWnd::SetPreDockState

Вызывается платформой для задания предварительного состояния закрепления.

```
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,
    CBasePane* pBarToDock = NULL,
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```

### <a name="parameters"></a>Параметры

*preDockState*<br/>
(в) Возможные значения:

- PDS_NOTHING,

- PDS_DOCK_REGULAR,

- PDS_DOCK_TO_TAB

*пбартодок*<br/>
(в) Указатель на стекол для стыковки.

*dockMethod*<br/>
(в) Метод стыковки. (Этот параметр игнорируется.)

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если окно мини-рамки отстыковано; FALSE, если он пристыкован.

## <a name="cpaneframewndsizetocontent"></a><a name="sizetocontent"></a>CPaneFrameWnd::SizeToContent

Регулирует размер окна мини-рамки таким образом, чтобы оно было эквивалентно содержащемуся стекле.

```
virtual void SizeToContent();
```

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы настроить размер окна мини-рамки до размера содержащегося стекла.

## <a name="cpaneframewndstarttearoff"></a><a name="starttearoff"></a>CPaneFrameWnd::StartTearOff

Делает меню перемещаемым.

```
BOOL StartTearOff(CMFCPopu* pMenu);
```

### <a name="parameters"></a>Параметры

*pMenu*<br/>
(в) Указатель на меню.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод был успешным; в противном случае, FALSE.

## <a name="cpaneframewndstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a>CPaneFrameWnd::StoreRecentDockSiteInfo

```
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>Параметры

(в) *pBar*<br/>

### <a name="remarks"></a>Примечания

## <a name="cpaneframewndstorerecenttabrelatedinfo"></a><a name="storerecenttabrelatedinfo"></a>CPaneFrameWnd::StoreRecentTabRelatedInfo

```
virtual void StoreRecentTabRelatedInfo(
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
[Класс CWnd](../../mfc/reference/cwnd-class.md)
