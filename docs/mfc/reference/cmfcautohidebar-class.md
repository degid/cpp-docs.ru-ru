---
title: Класс CMFCAutoHideBar
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
helpviewer_keywords:
- CMFCAutoHideBar [MFC], CMFCAutoHideBar
- CMFCAutoHideBar [MFC], AddAutoHideWindow
- CMFCAutoHideBar [MFC], AllowShowOnPaneMenu
- CMFCAutoHideBar [MFC], CalcFixedLayout
- CMFCAutoHideBar [MFC], Create
- CMFCAutoHideBar [MFC], GetFirstAHWindow
- CMFCAutoHideBar [MFC], GetVisibleCount
- CMFCAutoHideBar [MFC], OnShowControlBarMenu
- CMFCAutoHideBar [MFC], RemoveAutoHideWindow
- CMFCAutoHideBar [MFC], SetActiveInGroup
- CMFCAutoHideBar [MFC], SetRecentVisibleState
- CMFCAutoHideBar [MFC], ShowAutoHideWindow
- CMFCAutoHideBar [MFC], StretchPane
- CMFCAutoHideBar [MFC], UnSetAutoHideMode
- CMFCAutoHideBar [MFC], UpdateVisibleState
- CMFCAutoHideBar [MFC], m_nShowAHWndDelay
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
ms.openlocfilehash: 05f77dfba442f1ce4a375c8f225908799ece1788
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751771"
---
# <a name="cmfcautohidebar-class"></a>Класс CMFCAutoHideBar

Класс `CMFCAutoHideBar` — это специальный класс панели инструментов, реализующий возможность автоматического скрытия.

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCAutoHideBar : public CPane
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Переопределяет `CPane::AllowShowOnPaneMenu`.)|
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|(Оверлет [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCAutoHideBar::Create](#create)|Создает панель управления и прикрепляет ее к объекту [CPane.](../../mfc/reference/cpane-class.md) (Перекрывает [CPane::Создание](../../mfc/reference/cpane-class.md#create).)|
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|Вызывается платформой непосредственно перед отображением меню особой панели. (Переопределяет [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(Перекрывает [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).)|
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||
|[CMFCAutoHideBar::StretchPane](#stretchpane)|Растягивает панель по вертикали или горизонтали. (Оверлет [CBasePane::StretchPane](../../mfc/reference/cbasepane-class.md#stretchpane).)|
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|Задержка времени между моментом, когда пользователь помещает курсор мыши на [класс CMFCAutoHideButton,](../../mfc/reference/cmfcautohidebutton-class.md) и моментом, когда фреймворк показывает связанное окно.|

## <a name="remarks"></a>Примечания

Когда пользователь переключает область закрепления в режим автоматического скрытия, платформа автоматически создает объект `CMFCAutoHideBar`. Он также создает необходимые [объекты CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) и [CMFCAutoHideButton.](../../mfc/reference/cmfcautohidebutton-class.md) Каждый объект `CAutoHideDockSite` связан с определенным объектом `CMFCAutoHideButton`.

Класс `CMFCAutoHideBar` реализует отображение объекта `CAutoHideDockSite`, когда пользователь наводит указатель мыши на объект `CMFCAutoHideButton`. Когда панель инструментов получает сообщение WM_MOUSEMOVE, объект `CMFCAutoHideBar` запускает таймер. Когда отсчет завершается, панели инструментов отправляется уведомление о событии WM_TIMER. Панель инструментов обрабатывает это событие, проверяя, расположен ли указатель мыши на той же кнопке автоматического скрытия, на которой он находился при запуске таймера. В случае положительного результата отображается прикрепленный объект `CAutoHideDockSite`.

Длительность задержки таймера можно регулировать с помощью параметра `m_nShowAHWndDelay`. Значение по умолчанию составляет 400 мс.

## <a name="example"></a>Пример

В этом примере демонстрируется создание объекта `CMFCAutoHideBar` и использование его метода `GetDockSiteRow`.

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxautohidebar.h

## <a name="cmfcautohidebaraddautohidewindow"></a><a name="addautohidewindow"></a>CMFCAutoHideBar::AddAutoHideWindow

Добавляет в окно `CDockablePane` функциональные возможности, которые позволяют ему выполнять автоматическое скрытие.

```
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Параметры

*pAutoHideWnd*<br/>
(в) Окно, которое ты хочешь спрятать.

*dwAlignment*<br/>
(в) Значение, оговариваеще выравнивание кнопки автоматического скрытия с окном приложения.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Параметр *dwAlignment* указывает, где находится кнопка автоматического укрытия в приложении. Параметру может быть присвоено одно из следующих значений:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFCAutoHideBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCAutoHideBar::CalcFixedLayout

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

## <a name="cmfcautohidebarcmfcautohidebar"></a><a name="cmfcautohidebar"></a>CMFCAutoHideBar::CMFCAutoHideBar

Создает объект CMFCAutoHideBar.

```
CMFCAutoHideBar();
```

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebarcreate"></a><a name="create"></a>CMFCAutoHideBar::Создание

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>

*dwStyle*<br/>

*rect*<br/>

*pParentWnd*<br/>

*nID*<br/>

*dwControlBarStyle*<br/>

*pContext*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebargetfirstahwindow"></a><a name="getfirstahwindow"></a>CMFCAutoHideBar::GetFirstAHWindow

Возвращает указатель на первое окно автоматического скрытия в приложении.

```
CDockablePane* GetFirstAHWindow();
```

### <a name="return-value"></a>Возвращаемое значение

Первое окно автоматического скрытия в приложении или значение NULL, если его не существует.

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebargetvisiblecount"></a><a name="getvisiblecount"></a>CMFCAutoHideBar::GetVisibleCount

Получает количество видимых кнопок автоматического скрытия.

```
int GetVisibleCount();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество видимых кнопок автоматического скрытия.

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebarm_nshowahwnddelay"></a><a name="m_nshowahwnddelay"></a>CMFCAutoHideBar::m_nShowAHWndDelay

Задержка времени между моментом, когда пользователь помещает курсор мыши на [класс CMFCAutoHideButton,](../../mfc/reference/cmfcautohidebutton-class.md) и моментом, когда фреймворк показывает связанное окно.

```
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;
```

### <a name="remarks"></a>Примечания

Когда пользователь помещает курсор мыши `CMFCAutoHideButton`на, есть небольшая задержка, прежде чем фреймворк отображает связанное окно. Этот параметр определяет длину этой задержки в миллисекундах.

## <a name="cmfcautohidebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a>CMFCAutoHidebar::OnShowControlbarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Параметры

[in] *CPoint*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebarremoveautohidewindow"></a><a name="removeautohidewindow"></a>CMFCAutoHideBar::RemoveAutoHideWindow

Удаляет и уничтожает окно автоматического скрытия.

```
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```

### <a name="parameters"></a>Параметры

CDockablePane *pAutoHideWnd* автоматическое окно для удаления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebarsetactiveingroup"></a><a name="setactiveingroup"></a>CMFCAutoHidebar::SetActiveInGroup

Помечает строку автоматического скрытия как активную.

```
virtual void SetActiveInGroup(BOOL bActive);
```

### <a name="parameters"></a>Параметры

(в) BOOL *bActive* TRUE, чтобы установить на активную; в противном случае FALSE.

### <a name="remarks"></a>Примечания

См. раздел [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).

## <a name="cmfcautohidebarsetrecentvisiblestate"></a><a name="setrecentvisiblestate"></a>CMFCAutoHideBar::SetRecentVisibleState

```cpp
void SetRecentVisibleState(BOOL bState);
```

### <a name="parameters"></a>Параметры

*bState*<br/>
(в) Состояние для установки.

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebarshowautohidewindow"></a><a name="showautohidewindow"></a>CMFCAutoHideBar:ShowAutoHideWindow

Показывает окно автоматического скрытия.

```
BOOL ShowAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Параметры

*pAutoHideWnd*<br/>
(в) Окно, чтобы показать.

*bShow*<br/>
(в) ПРАВДА, чтобы показать окно.

*bDelay*<br/>
(в) Этот параметр игнорируется.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebarstretchpane"></a><a name="stretchpane"></a>CMFCAutoHideBar::StretchPane

Изменение размеров строки автоматического скрытия в свернутом состоянии в соответствии с размерами объекта `CMFCAutoHideButton` .

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>Параметры

*nДлина*<br/>
(в) Значение не используется в базовой реализации. В производных реализациях это значение используется для указания длины панели, размер которой был изменен.

*bVert*<br/>
(в) Значение не используется в базовой реализации. В производных реализациях используйте TRUE для обработки случая, когда панель автоматического прятки сворачивается вертикально, и FALSE для случая, когда панель автоматической скрытия рухнула горизонтально.

### <a name="return-value"></a>Возвращаемое значение

Размер, полученный в результате изменения размера панели.

### <a name="remarks"></a>Примечания

Производные классы могут переопределять этот метод для настройки поведения.

## <a name="cmfcautohidebarunsetautohidemode"></a><a name="unsetautohidemode"></a>CMFCAutoHideBar::UnsetAutoHideMode

Отключает режим автоматического скрытия для группы строк автоматического скрытия.

```cpp
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)
```

### <a name="parameters"></a>Параметры

pFirstBarInGroup Указатель на первый автоматический бар в группе.

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebarupdatevisiblestate"></a><a name="updatevisiblestate"></a>CMFCAutoHideBar::ОбновлениеВидимоегосударство

Вызывается платформой при необходимости перерисовать строку автоматического скрытия.

```cpp
void UpdateVisibleState();
```

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CPane Class](../../mfc/reference/cpane-class.md)<br/>
[Класс CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)<br/>
[Класс CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)
