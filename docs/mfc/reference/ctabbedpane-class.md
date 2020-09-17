---
title: Класс Ктаббедпане
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
ms.openlocfilehash: cfc0a3099b1d5ff9bd1093cc911745bd61cde64c
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686643"
---
# <a name="ctabbedpane-class"></a>Класс Ктаббедпане

Реализует функциональные возможности области с отделяемыми вкладками.

или более подробные сведения см. в исходном коде, расположенном в папке **VC \\ атлмфк \\ src \\ библиотеки MFC** в установке Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CTabbedPane : public CBaseTabbedPane
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|`CTabbedPane::CTabbedPane`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CTabbedPane::DetachPane](#detachpane)|(Переопределяет [CBaseTabbedPane::D етачпане](../../mfc/reference/cbasetabbedpane-class.md#detachpane).)|
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|Включает или выключает автоматическую цветовую маркировку вкладок.|
|[CTabbedPane::FloatTab](#floattab)|Перемещает панель, но только в том случае, если эта панель находится на вкладке, которая отсоединена. (переопределяет [CBaseTabbedPane:: флоаттаб](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|
|[CTabbedPane::GetTabArea](#gettabarea)|Возвращает размер и положение области вкладок в окне с вкладками.|
|[CTabbedPane::GetTabWnd](#gettabwnd)||
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|Определяет возможность переключения панели с вкладками в режим автоматического скрытия. (Переопределяет [CBaseTabbedPane:: хасаутохидемоде](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode).)|
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

Чтобы задать обычные вкладки вместо вкладок в стиле Outlook, передайте AFX_CBRS_REGULAR_TABSный стиль в метод [CDockablePane:: креатикс](../../mfc/reference/cdockablepane-class.md#createex) .

Если создать панель с отделяемыми вкладками, она может быть автоматически уничтожена платформой, поэтому лучше не оставлять указатель. Чтобы получить указатель на панель с вкладками, вызовите метод `CBasePane::GetParentTabbedPane`.

## <a name="examples"></a>Примеры

В этом примере создается объект `CTabbedPane`. Далее мы используем [CBaseTabbedPane:: аддтаб](../../mfc/reference/cbasetabbedpane-class.md#addtab) для присоединения дополнительных вкладок.

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

Другим способом создания объекта панели элементов управления с вкладками является использование [CDockablePane:: аттачтотабвнд](../../mfc/reference/cdockablepane-class.md#attachtotabwnd). `AttachToTabWnd`Метод динамически создает объект области с вкладками, используя сведения о классе среды выполнения, заданные с помощью [CDockablePane:: сеттаббедпанертк](../../mfc/reference/cdockablepane-class.md#settabbedpanertc).

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

**Заголовок:** афкстаббедпане. h

## <a name="ctabbedpanedetachpane"></a><a name="detachpane"></a> Ктаббедпане::D Етачпане

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Параметры

окне *пбар*<br/>

окне *бхиде*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="ctabbedpaneenabletabautocolor"></a><a name="enabletabautocolor"></a> Ктаббедпане:: Енаблетабаутоколор

Включает или выключает автоматическую цветовую маркировку вкладок.

```
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
окне Значение TRUE, чтобы включить автоматическое Окрашивание вкладок; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Используйте этот статический метод, чтобы включить или отключить автоматическое Окрашивание вкладок во всех панелях с вкладками в приложении. Если эта функция включена, каждая вкладка заполняется своим собственным цветом. Список цветов, используемых для выделения цветом вкладок, можно найти, вызвав метод [CMFCBaseTabCtrl:: жетаутоколорс](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors) .

Можно указать список цветов, которые будут использоваться для вкладок, вызвав [ктаббедпане:: сеттабаутоколорс](#settabautocolors).

Этот параметр по умолчанию отключен.

## <a name="ctabbedpanefloattab"></a><a name="floattab"></a> Ктаббедпане:: Флоаттаб

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Параметры

окне *пбар*<br/>
окне *нтабид*<br/>
окне *доккмесод*<br/>
окне *бхиде*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="ctabbedpanegettabarea"></a><a name="gettabarea"></a> Ктаббедпане:: Жеттабареа

Возвращает размер и позицию области вкладки в окне с вкладками.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Параметры

*rectTabAreaTop*<br/>
заполняет Содержит размер и позицию (в экранных координатах) области верхней вкладки.

*rectTabAreaBottom*<br/>
заполняет Содержит размер и позицию в экранных координатах нижней области вкладки.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод, чтобы определить, как закрепить область, которую пользователь перетаскивает. Когда пользователь перетаскивает область над областью вкладок целевой области, платформа пытается добавить ее в качестве новой вкладки целевой области. В противном случае он пытается закрепить панель на стороне целевой области, которая включает создание нового контейнера панели с разделителем панели, разделяющим две панели.

Переопределите этот метод в `CTabbedPane` классе, производном от, чтобы изменить это поведение.

## <a name="ctabbedpanegettabwnd"></a><a name="gettabwnd"></a> Ктаббедпане:: Жеттабвнд

```
CMFCTabCtrl* GetTabWnd() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="ctabbedpanehasautohidemode"></a><a name="hasautohidemode"></a> Ктаббедпане:: Хасаутохидемоде

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="ctabbedpaneistablocationbottom"></a><a name="istablocationbottom"></a> Ктаббедпане:: Истаблокатионботтом

Определяет, расположены ли вкладки в нижней части окна.

```
virtual BOOL IsTabLocationBottom() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если область вкладки находится в нижней части окна с вкладками; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

## <a name="ctabbedpanem_btabsalwaystop"></a><a name="m_btabsalwaystop"></a> Ктаббедпане:: m_bTabsAlwaysTop

Расположение вкладок в приложении по умолчанию.

```
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;
```

### <a name="remarks"></a>Примечания

Задайте для этого статического элемента значение TRUE, чтобы все вкладки в приложении отображались в верхней части панели с вкладками.

Это значение необходимо задать до создания панели с вкладками.

Значение по умолчанию — FALSE.

## <a name="ctabbedpanem_ptabwndrtc"></a><a name="m_ptabwndrtc"></a> Ктаббедпане:: m_pTabWndRTC

Сведения о классе среды выполнения для настраиваемого объекта, производного от класса `CMFCTabCtrl`.

```
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;
```

### <a name="remarks"></a>Примечания

Задайте для этой статической переменной-члена указатель на сведения о классе среды выполнения `CMFCTabCtrl` объекта, производного от, если вы используете настраиваемое окно с вкладками внутри области с вкладками.

## <a name="ctabbedpaneresettabs"></a><a name="resettabs"></a> Ктаббедпане:: Ресеттабс

Переводит все панели с вкладками в состояние по умолчанию.

```
static void ResetTabs();
```

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы вернуть все панели с вкладками в состояние по умолчанию. При вызове этот метод сбрасывает размеры границ и автоматическое состояние цвета для всех панелей с вкладками.

## <a name="ctabbedpanesettabautocolors"></a><a name="settabautocolors"></a> Ктаббедпане:: Сеттабаутоколорс

Задает список пользовательских цветов, используемых при включенной функции автоцветности.

```
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>Параметры

*arColors*<br/>
окне Содержит массив заданных цветов.

### <a name="remarks"></a>Примечания

Этот метод используется для настройки списка цветов, используемых при включенной функции автоцветности. Это статическая функция, влияющая на все области с вкладками в приложении.

Используйте [ктаббедпане:: енаблетабаутоколор](#enabletabautocolor) , чтобы включить или отключить функцию автоматического цвета.

## <a name="see-also"></a>См. также

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)<br/>
[Класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)
