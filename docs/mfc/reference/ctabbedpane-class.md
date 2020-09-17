---
title: Класс CTabbedPane
ms.date: 11/04/2016
f1_keywords:
- CTabbedPane
- AFXTABBEDPANE/CTabbedPane
- AFXTABBEDPANE/CTabbedPane::DetachPane
- AFXTABBEDPANE/CTabbedPane::EnableTabAutoColor
- AFXTABBEDPANE/CTabbedPane::FloatTab
- AFXTABBEDPANE/CTabbedPane::GetTabArea
- AFXTABBEDPANE/CTabbedPane::GetTabWnd
- AFXTABBEDPANE/CTabbedPane::HasAutoHideMode
- AFXTABBEDPANE/CTabbedPane::IsTabLocationBottom
- AFXTABBEDPANE/CTabbedPane::ResetTabs
- AFXTABBEDPANE/CTabbedPane::SetTabAutoColors
- AFXTABBEDPANE/CTabbedPane::m_bTabsAlwaysTop
- AFXTABBEDPANE/CTabbedPane::m_pTabWndRTC
helpviewer_keywords:
- CTabbedPane [MFC], DetachPane
- CTabbedPane [MFC], EnableTabAutoColor
- CTabbedPane [MFC], FloatTab
- CTabbedPane [MFC], GetTabArea
- CTabbedPane [MFC], GetTabWnd
- CTabbedPane [MFC], HasAutoHideMode
- CTabbedPane [MFC], IsTabLocationBottom
- CTabbedPane [MFC], ResetTabs
- CTabbedPane [MFC], SetTabAutoColors
- CTabbedPane [MFC], m_bTabsAlwaysTop
- CTabbedPane [MFC], m_pTabWndRTC
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
ms.openlocfilehash: 17351eaed585ec34117a2ef825964fd51bd0d86b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365954"
---
# <a name="ctabbedpane-class"></a>Класс CTabbedPane

Реализует функциональные возможности области с отделяемыми вкладками.

или более подробно увидеть исходный код, расположенный в **папке VC\\atlmfc\\src\\mfc** установки.

## <a name="syntax"></a>Синтаксис

```
class CTabbedPane : public CBaseTabbedPane
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CTabbedPane::CTabbedPane`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTabbedPane::DetachPane](#detachpane)|(Оверлет [cBaseTabbedPane::DetachPane](../../mfc/reference/cbasetabbedpane-class.md#detachpane).)|
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|Включает или выключает автоматическую цветовую маркировку вкладок.|
|[CTabbedPane::FloatTab](#floattab)|Плавает панель, но только если панель в настоящее время находится в съемной вкладке. (Переопределяет [CBaseTabbedPane::FloatTab.)](../../mfc/reference/cbasetabbedpane-class.md#floattab)|
|[CTabbedPane::GetTabArea](#gettabarea)|Возвращает размер и положение области вкладок в окне с вкладками.|
|[CTabbedPane::GetTabWnd](#gettabwnd)||
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|Определяет возможность переключения панели с вкладками в режим автоматического скрытия. (Оверлет [CBaseTabbedPane::HasAutoHideMode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode).)|
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|Определяет, расположены ли вкладки в нижней части окна.|
|[CTabbedPane::ResetTabs](#resettabs)|Переводит все панели с вкладками в состояние по умолчанию.|
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|Задает список пользовательских цветов, которые могут применяться, когда включена возможность автоматической цветовой маркировки вкладок.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|Расположение вкладок в приложении по умолчанию.|
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|Сведения о классе среды выполнения для настраиваемого объекта, производного от класса `CMFCTabCtrl`.|

## <a name="remarks"></a>Примечания

Платформа автоматически создает экземпляр этого класса, когда пользователь прикрепляет одну панель к другой, подводя указатель мыши к заголовку второй панели. Все панели с вкладками, созданные платформой, имеют идентификатор -1.

Чтобы указать регулярные вкладки вместо вкладок в стиле Outlook, передайте AFX_CBRS_REGULAR_TABS стиль методу [CDockablePane::CreateEx.](../../mfc/reference/cdockablepane-class.md#createex)

Если создать панель с отделяемыми вкладками, она может быть автоматически уничтожена платформой, поэтому лучше не оставлять указатель. Чтобы получить указатель на панель с вкладками, вызовите метод `CBasePane::GetParentTabbedPane`.

## <a name="example"></a>Пример

В этом примере создается объект `CTabbedPane`. Далее мы используем [CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) для присоединения дополнительных вкладок.

```cpp
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);

if (!pTabbededBar->Create (_T(""),
    this,
    CRect (0,
    0,
    200,
    200),
    TRUE,
    (UINT) -1,
    WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |
    WS_CLIPCHILDREN | CBRS_LEFT |
    CBRS_FLOAT_MULTI))
{
    TRACE0("Failed to create Solution Explorer bar\n");

    return FALSE;      // fail to create
}

pTabbededBar->AddTab (&m_wndClassView);
pTabbededBar->AddTab (&m_wndResourceView);

pTabbededBar->AddTab (&m_wndFileView);
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);

DockPane(pTabbededBar);
```

## <a name="example"></a>Пример

Еще один способ создания элемента панели управления вкладками — использование [CDockablePane::AttachToTabWnd.](../../mfc/reference/cdockablepane-class.md#attachtotabwnd) Метод `AttachToTabWnd` динамически создает объект панели с помощью информации класса выполнения, установленной [CDockablePane::SetTabbedPaneRTC.](../../mfc/reference/cdockablepane-class.md#settabbedpanertc)

В этом примере рассматривается динамическое создание панели с вкладками, прикрепление двух вкладок друг к другу, а также преобразование второй вкладки в неотделяемую.

```cpp
DockPane(&m_wndClassView);

CTabbedPane* pTabbedBar = NULL;
m_wndResourceView.AttachToTabWnd (&m_wndClassView,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

m_wndFileView.AttachToTabWnd (pTabbedBar,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1,
    FALSE);
```

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CTabbedPane](../../mfc/reference/ctabbedpane-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxTabbedPane.h

## <a name="ctabbedpanedetachpane"></a><a name="detachpane"></a>CTabbedPane::DetachPane

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Параметры

(в) *pBar*<br/>

(в) *bHide*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="ctabbedpaneenabletabautocolor"></a><a name="enabletabautocolor"></a>CTabbedPane::EnableTabAutoColor

Включает или выключает автоматическую цветовую маркировку вкладок.

```
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE для автоматической окраски вкладок; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Используйте этот статический метод, чтобы включить или отключить автоматическую окраску вкладок во всех стеках в приложении. Когда эта функция включена, каждая вкладка заполняется собственным цветом. Список цветов, используемых для окрашивания вкладок, можно найти, позвонив по методу [CMFCBaseTabCtrl::GetAutoColors.](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors)

Вы можете указать список цветов, которые будут использоваться для вкладок, позвонив [по телефону CTabbedPane::SetTabAutoColors.](#settabautocolors)

Этот параметр по умолчанию отключен.

## <a name="ctabbedpanefloattab"></a><a name="floattab"></a>CTabbedPane::FloatTab

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Параметры

(в) *pBar*<br/>
(в) *nTabID*<br/>
(в) *докМетод*<br/>
(в) *bHide*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="ctabbedpanegettabarea"></a><a name="gettabarea"></a>CTabbedPane::GetTabArea

Возвращает размер и положение области вкладки в окне вкладки.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Параметры

*rectTabAreaTop*<br/>
(ваут) Содержит размер и положение в координатах экрана верхней области вкладки.

*rectTabAreaBottom*<br/>
(ваут) Содержит размер и положение в координатах экрана нижней области вкладки.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод, чтобы определить, как стыковка панели, что пользователь перетащит. Когда пользователь перетаскивает панель над областью вкладки панели целевого стекла, фреймворк пытается добавить его в качестве новой вкладки панели целевого. В противном случае он пытается пристыковать панель к боковой части целевого стекла, что включает в себя создание нового контейнера с стеклом с разделителем панели, отделяющей две панели.

Переопределить этот метод `CTabbedPane`в классе, полученном, чтобы изменить это поведение.

## <a name="ctabbedpanegettabwnd"></a><a name="gettabwnd"></a>CTabbedPane::GetTabWnd

```
CMFCTabCtrl* GetTabWnd() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="ctabbedpanehasautohidemode"></a><a name="hasautohidemode"></a>CTabbedPane:HasAutoHideMode

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="ctabbedpaneistablocationbottom"></a><a name="istablocationbottom"></a>CTabbedPane::IsTabLocationBottom

Определяет, расположены ли вкладки в нижней части окна.

```
virtual BOOL IsTabLocationBottom() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если область вкладок расположена в нижней части окна вкладки; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="ctabbedpanem_btabsalwaystop"></a><a name="m_btabsalwaystop"></a>CTabbedPane::m_bTabsAlwaysTop

Расположение вкладок в приложении по умолчанию.

```
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;
```

### <a name="remarks"></a>Примечания

Установите этот статический член к TRUE, чтобы заставить все вкладки в приложении, которые будут отображаться в верхней части панели вкладок.

Необходимо установить это значение до создания панели вкладок.

Значение по умолчанию — FALSE.

## <a name="ctabbedpanem_ptabwndrtc"></a><a name="m_ptabwndrtc"></a>CTabbedPane::m_pTabWndRTC

Сведения о классе среды выполнения для настраиваемого объекта, производного от класса `CMFCTabCtrl`.

```
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;
```

### <a name="remarks"></a>Примечания

Установите эту статическую переменную члена на указатель `CMFCTabCtrl`на информацию класса времени выполнения объекта, полученного, если вы используете пользовательское окно вкладки внутри панели вкладок.

## <a name="ctabbedpaneresettabs"></a><a name="resettabs"></a>CTabbedPane:ResetTabs

Переводит все панели с вкладками в состояние по умолчанию.

```
static void ResetTabs();
```

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы вернуть все панели вкладок в состояние по умолчанию. При вызове этот метод сбрасывает размеры границы и автоматическое состояние цвета всех табло.

## <a name="ctabbedpanesettabautocolors"></a><a name="settabautocolors"></a>CTabbedPane::SetTabAutoColors

Устанавливает список пользовательских цветов, которые используются при включении функции автоматического цвета.

```
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>Параметры

*arColors*<br/>
(в) Содержит массив цветов для установки.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы настроить список цветов, которые используются при включении функции автоматического цвета. Это статическая функция и влияет на все панели вкладок в приложении.

Используйте [CTabbedPane::EnableTabAutoColor](#enabletabautocolor) для включения или отключать функцию автоматического цвета.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)<br/>
[Класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)
