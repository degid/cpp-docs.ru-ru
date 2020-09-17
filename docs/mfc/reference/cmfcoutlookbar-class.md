---
title: Класс CMFCOutlookBar
ms.date: 06/25/2018
f1_keywords:
- CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar::AllowDestroyEmptyTabbedPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanAcceptPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanSetCaptionTextToTabName
- AFXOUTLOOKBAR/CMFCOutlookBar::Create
- AFXOUTLOOKBAR/CMFCOutlookBar::CreateCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::DoesAllowDynInsertBefore
- AFXOUTLOOKBAR/CMFCOutlookBar::FloatTab
- AFXOUTLOOKBAR/CMFCOutlookBar::GetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::GetTabArea
- AFXOUTLOOKBAR/CMFCOutlookBar::IsMode2003
- AFXOUTLOOKBAR/CMFCOutlookBar::OnAfterAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnBeforeAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnScroll
- AFXOUTLOOKBAR/CMFCOutlookBar::RemoveCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::SetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::SetMode2003
helpviewer_keywords:
- CMFCOutlookBar [MFC], AllowDestroyEmptyTabbedPane
- CMFCOutlookBar [MFC], CanAcceptPane
- CMFCOutlookBar [MFC], CanSetCaptionTextToTabName
- CMFCOutlookBar [MFC], Create
- CMFCOutlookBar [MFC], CreateCustomPage
- CMFCOutlookBar [MFC], DoesAllowDynInsertBefore
- CMFCOutlookBar [MFC], FloatTab
- CMFCOutlookBar [MFC], GetButtonsFont
- CMFCOutlookBar [MFC], GetTabArea
- CMFCOutlookBar [MFC], IsMode2003
- CMFCOutlookBar [MFC], OnAfterAnimation
- CMFCOutlookBar [MFC], OnBeforeAnimation
- CMFCOutlookBar [MFC], OnScroll
- CMFCOutlookBar [MFC], RemoveCustomPage
- CMFCOutlookBar [MFC], SetButtonsFont
- CMFCOutlookBar [MFC], SetMode2003
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
ms.openlocfilehash: fe328cb0d857ff9154624d218b1b56362890ce81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369652"
---
# <a name="cmfcoutlookbar-class"></a>Класс CMFCOutlookBar

Область со вкладками, которая имеет внешний вид области **Область переходов** в Microsoft Outlook 2000 или Outlook 2003. Объект `CMFCOutlookBar` содержит объект [класса CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md) и ряд вкладок. Вкладки могут быть либо объектами [cmFCOutlookBarPane класса,](../../mfc/reference/cmfcoutlookbarpane-class.md) либо `CWnd`объектами, полученными из полученных. Пользователю панель Outlook отображается как последовательность кнопок и область отображения. Когда пользователь нажимает кнопку, отображается соответствующая область элемента управления или кнопки.

## <a name="syntax"></a>Синтаксис

```cpp
class CMFCOutlookBar : public CBaseTabbedPane
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCOutlookBar::CMFCOutlookBar`|Конструктор по умолчанию.|
|`CMFCOutlookBar::~CMFCOutlookBar`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Определяет, можно ли уничтожить пустое табло. (Переопределяет [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Определяет, можно ли пристыковать еще одно стекло к панели бара Outlook. (Переопределяет CDockablePane::CanAcceptPane.)|
|[CMFCOutlookbar::Cansettexttotabname](#cansetcaptiontexttotabname)|Определяет, отображает ли подпись для панели вкладок тот же текст, что и активная вкладка. (Overrides [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|
|[CMFCOutlookBar::Создание](#create)|Создает элемент управления панели Outlook.|
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Создает пользовательскую вкладку панели Outlook.|
|`CMFCOutlookBar::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCOutlookBar: :DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Определяет, может ли пользователь свяжет панель управления на внешнем краю панели Outlook.|
|[CMFCOutlookBar::FloatTab](#floattab)|Плавает панель, но только если панель в настоящее время находится в съемной вкладке. (Переопределяет [CBaseTabbedPane::FloatTab.)](../../mfc/reference/cbasetabbedpane-class.md#floattab)|
|[CMFCOutlookBar::GetButton](#getbuttonsfont)|Возвращает шрифт текста на кнопки бара Outlook.|
|[CMFCOutlookBar:GetTabArea](#gettabarea)|Возвращает размер и положение областей вкладок в бар Outlook. (Переборывает [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|
|`CMFCOutlookBar::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Определяет, имитирует ли поведение бара Outlook поведение Microsoft Office Outlook 2003 (см. Замечания).|
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|Вызывается [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) после того, как активная вкладка была установлена с помощью анимации.|
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|Вызывается [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) перед страницей вкладок устанавливается в качестве активной вкладки с помощью анимации.|
|[CMFCOutlookBar::OnScroll](#onscroll)|Вызывается в рамках, если панель Outlook прокручивается вверх или вниз.|
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Удаляет пользовательскую вкладку панели Outlook.|
|[CMFCOutlookBar::SetButton](#setbuttonsfont)|Устанавливает шрифт текста на кнопках панели Outlook.|
|[CMFCOutlookBar:SetMode2003](#setmode2003)|Уточняется, имитирует ли поведение бара Outlook поведение Outlook outlook 2003 (см. Замечания).|

## <a name="remarks"></a>Примечания

На примере бара Outlook можно ознакомиться на [примере outlookDemo: приложение OutlookDemo.](../../overview/visual-cpp-samples.md)

## <a name="implementing-the-outlook-bar"></a>Реализация панели Outlook

Для использования элемента управления `CMFCOutlookBar` в своем приложении выполните следующие действия:

1. Внедрите объект `CMFCOutlookBar` в класс окна главного фрейма.

    ```cpp
    class CMainFrame : public CMDIFrameWnd
    {
        // ...
        CMFCOutlookBar m_wndOutlookBar;
        CMFCOutlookBarPane m_wndOutlookPane;
        // ...
    };
    ```

1. При обработке WM_CREATE сообщения в главном кадре позвоните в [CMFCOutlookBar::Создание](#create) метода для создания элемента управления вкладками панели Outlook.

    ```cpp
    m_wndOutlookBar.Create (_T("Shortcuts"),
        this,
        CRect (0, 0, 100, 100),
        ID_VIEW_OUTLOOKBAR,
        WS_CHILD | WS_VISIBLE | CBRS_LEFT);
    ```

1. Получить указатель на основной `CMFCOutlookBarTabCtrl` с помощью [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow).

    ```cpp
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();
    ```

1. Создайте объект [класса CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) для каждой вкладки, содержащей кнопки.

    ```cpp
    m_wndOutlookPane.Create(&m_wndOutlookBar,
        AFX_DEFAULT_TOOLBAR_STYLE,
        ID_OUTLOOK_PANE_GENERAL,
        AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);

    // make the Outlook pane detachable (enable docking)
    m_wndOutlookPane.EnableDocking(CBRS_ALIGN_ANY);

    // add buttons
    m_wndOutlookPane.AddButton(theApp.LoadIcon (IDR_MAINFRAME),
        "About",
        ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON),
        "Open",
        ID_FILE_OPEN);
    ```

1. Позвоните [CMFCOutlookBarTabCtrl::AddTab,](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) чтобы добавить каждую новую вкладку. Установите *bDeachable* параметр FALSE, чтобы сделать страницу несъемной. Или используйте [CMFCOutlookTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) для добавления съемных страниц.

    ```cpp
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);
    ```

1. Чтобы добавить `CWnd`элемент управления (например, [CMFCShellTreeCtrl Class)](../../mfc/reference/cmfcshelltreectrl-class.md)в качестве вкладки, создайте элемент управления и позвоните в [CMFCOutlookBarTabCtrl::AddTab,](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) чтобы добавить его в бар Outlook.

> [!NOTE]
> Вы должны использовать уникальные идентифицировать элементы управления для `CWnd`каждого объекта [класса CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) и для каждого объекта, полученного.

Чтобы динамически добавлять или удалять новые страницы во время выполнения, используйте [CMFCOutlookBar::CreateCustomPage](#createcustompage) и [CMFCOutlookBar::RemoveCustomPage](#removecustompage).

## <a name="outlook-2003-mode"></a>Режим Outlook 2003

В режиме Outlook 2003 кнопки вкладок расположены в нижней части панели панели Outlook. Когда нет достаточно места для отображения кнопок, они отображаются в виде значков в панели инструментов, как области вдоль нижней части панели.

Используйте [CMFCOutlookBar::SetMode2003](#setmode2003) для включения режима Outlook 2003. Используйте [CMFCOutlookTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) для установки битовой карты, содержащей значки, отображаемые в нижней части панели Outlook. Иконки в бит-карте должны быть заказаны индексом вкладок.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxoutlookbar.h

## <a name="cmfcoutlookbarallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a>CMFCOutlookBar::AllowDestroyEmptyTabbedPane

Определяет, можно ли уничтожить пустое табло.

```cpp
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если пустое табло панели могут быть уничтожены; в противном случае, FALSE. Реализация по умолчанию всегда возвращает TRUE.

### <a name="remarks"></a>Примечания

Если пустое табло не может быть уничтожено, фреймворк скрывает его.

## <a name="cmfcoutlookbarcanacceptpane"></a><a name="canacceptpane"></a>CMFCOutlookBar::CanAcceptPane

Определяет, можно ли пристыковать еще одно стекло к панели бара Outlook.

```cpp
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в) Указатель на другой панели, которая в настоящее время пристыкован к этой панели.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если еще одно стекло может быть пристыковано к панели бара Outlook; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Если панель Outlook находится в режиме Outlook 2003, стыковка не поддерживается, поэтому значение возврата FALSE.

Если параметр *pBar* NULL, этот метод возвращает FALSE.

В противном случае этот метод ведет себя как базовый метод [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane), за исключением того, что даже если стыковка не включена, бар Outlook все еще может включить другой бар Outlook, который будет пристыкован к нему.

## <a name="cmfcoutlookbarcansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a>CMFCOutlookbar::Cansettexttotabname

Определяет, отображает ли подпись для панели вкладок тот же текст, что и активная вкладка.

```cpp
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если подпись окна окна Outlook автоматически устанавливается на текст активной вкладки; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Используйте [CBaseTabbedPane::EnableSetCaptionTextToTabName,](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) чтобы включить или отключить эту функциональность.

В режиме Outlook 2003 эта настройка всегда включена.

## <a name="cmfcoutlookbarcreate"></a><a name="create"></a>CMFCOutlookBar::Создание

Создает элемент управления панели Outlook.

```cpp
virtual BOOL Create(
    LPCTSTR lpszCaption,
    CWnd* pParentWnd,
    const RECT& rect,
    UINT nID,
    DWORD dwStyle,
    DWORD dwControlBarStyle=AFX_CBRS_RESIZE,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>Параметры

*lpszCaption*<br/>
(в) Определяет заголовок окна.

*pParentWnd*<br/>
(в) Укажите указатель на родительское окно. Она не должна быть NULL.

*rect*<br/>
(в) Определяет размер и положение панели outlook в пикселях.

*nID*<br/>
(в) Упогоняет идентификатор управления. Должно быть отличным от других итогов управления, используемых в приложении.

*dwStyle*<br/>
(в) Определяет желаемый стиль панели управления. Для возможных значений [см.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*dwControlBarStyle*<br/>
(в) Определяет специальные библиотечные стили.

*pContext*<br/>
(в) Создайте контекст.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод успешен; в противном случае 0.

### <a name="remarks"></a>Примечания

Вы строите `CMFCOutlookBar` объект в два этапа. Сначала вызов конструктора, а `Create`затем вызов, который создает управление панелью outlook и прикрепляет его к объекту. `CMFCOutlookBar`

Смотрите [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) для списка доступных стилей, определяемых библиотекой, которые будут указаны *dwControlBarStyle.*

### <a name="example"></a>Пример

В следующем примере показано, `Create` как `CMFCOutlookBar` использовать метод класса. Этот фрагмент кода является частью [образца Outlook Multi Views.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]

## <a name="cmfcoutlookbarcreatecustompage"></a><a name="createcustompage"></a>CMFCOutlookBar::CreateCustomPage

Создает пользовательскую вкладку панели Outlook.

```cpp
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,
    BOOL bActivatePage=TRUE,
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,
    BOOL bEnableTextLabels=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszPageName*<br/>
(в) Метка страницы.

*bActivatePage*<br/>
(в) Если истина, страница становится активной после создания.

*dwEnabledDocking*<br/>
(в) Комбинация CBRS_ALIGN_ флагов, которая определяет включенные стороны стыковки при отсоединении страницы.

*bEnableTextLabels*<br/>
(в) Если true, текстовые метки включены для кнопок, которые находятся на странице.

### <a name="return-value"></a>Возвращаемое значение

Указатель на вновь созданную страницу или NULL, если творение не удалось.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы позволить пользователям создавать пользовательские страницы панели Outlook. Вы можете создать до 100 страниц в приложении. Иди имитного представления управления страницами начинается с 0xF000. Создание завершается неудачей, если общее количество пользовательских страниц панели Outlook превышает 100.

Используйте [CMFCOutlookBar::RemoveCustomPage](#removecustompage) для удаления пользовательских страниц.

## <a name="cmfcoutlookbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CMFCOutlookBar: :DoesAllowDynInsertBefore

Уточняется, может ли пользователь стыковки панели на внешнем краю бара Outlook.

```
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает FALSE.

### <a name="remarks"></a>Примечания

Фрейм `DoesAllowDynInsertBefore` вызывает метод, когда он ищет место для стыковки динамического стекла. Если функция возвращает FALSE, фреймворк не позволяет стыковку динамического стекла на внешних краях панели.

Обычно вы создаете панель Outlook в виде статического неплавательного управления. Вы можете переопределить эту функцию в производном классе и вернуть TRUE, чтобы изменить это поведение.

> [!NOTE]
> Поскольку динамические стекла проверяют состояние пристыкованных статических стекол при стыковке, при стыковке следует пристыковкать динамические стекла после статических стекол, когда это возможно.

## <a name="cmfcoutlookbarfloattab"></a><a name="floattab"></a>CMFCOutlookBar::FloatTab

Плавает панель.

```cpp
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в) Указатель на панель, чтобы плавать.

*nTabID*<br/>
(в) Индекс на нулевой основе вкладки для плавания.

*dockMethod*<br/>
(в) Определяет метод использования для сделать панель поплавок.  Для получения дополнительной информации [см. CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).

*bHide*<br/>
(в) ПРАВДА, чтобы скрыть стекло перед плавающей; в противном случае, FALSE. В отличие от базовой версии этого метода, этот параметр не имеет значения по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если панель плавали; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Этот метод похож на [CBaseTabbedPane::FloatTab,](../../mfc/reference/cbasetabbedpane-class.md#floattab) за исключением того, что он не позволяет последней оставшейся вкладке на панели Outlook для плавания.

## <a name="cmfcoutlookbargetbuttonsfont"></a><a name="getbuttonsfont"></a>CMFCOutlookBar::GetButton

Возвращает шрифт текста на вкладке кнопки страницы бара Outlook.

```cpp
CFont* GetButtonsFont() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект шрифта, который используется для отображения текста на вкладке страницы страницы Outlook.

### <a name="remarks"></a>Примечания

Используйте эту функцию для извлечения шрифта, который используется для отображения текста на вкладке кнопки Outlook. Вы можете установить шрифт, позвонив по [ТЕЛЕФОНу CMFCOutlookBar::SetButtonsFont](#setbuttonsfont).

## <a name="cmfcoutlookbargettabarea"></a><a name="gettabarea"></a>CMFCOutlookBar:GetTabArea

Определяет размер и положение областей вкладки в панели Outlook.

```cpp
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Параметры

*rectTabAreaTop*<br/>
(ваут) Содержит размер и положение (в координатах клиента) верхней области вкладки при возврате функции.

*rectTabAreaBottom*<br/>
(ваут) Содержит размер и положение (в координатах клиента) нижней области вкладки при возврате функции.

### <a name="remarks"></a>Примечания

Рамка вызывает этот метод для определения типа стыковки с целевым стеклом. Когда фреймворк определяет, что пользователь перетаскивает панель для пристыкования к области вкладки целевого стекла, он пытается добавить первую панель в качестве новой вкладки целевого стекла. В противном случае он пытается пристыковать первое стекло на соответствующей стороне целевого стекла. Рамка создает новый контейнер с ползунок для размещения дополнительного пристыкованного стекла.

Реализация по `GetTabArea` умолчанию возвращает всю область клиента в панели Outlook, если панель Outlook статична; то есть, если бар Outlook не может плавать. В противном случае он возвращает область, которую кнопки страницы занимают в верхней и нижней части управления панели Outlook.

Переопределить этот метод в `CMFCOutlookBar` классе, полученном из изменить это поведение.

## <a name="cmfcoutlookbarismode2003"></a><a name="ismode2003"></a>CMFCOutlookBar::IsMode2003

Уточняется, имитирует ли поведение бара Outlook поведение Microsoft Office Outlook 2003.

```cpp
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если панель Outlook работает в режиме Microsoft Office 2003; в противном случае 0.

### <a name="remarks"></a>Примечания

Вы можете включить этот режим с помощью [CMFCOutlookBar::SetMode2003](#setmode2003).

## <a name="cmfcoutlookbaronafteranimation"></a><a name="onafteranimation"></a>CMFCOutlookBar:OnafterAnimation

Вызывается [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) после того, как активная вкладка была установлена с помощью анимации.

```cpp
virtual void OnAfterAnimation(int nPage);
```

### <a name="parameters"></a>Параметры

*nСтраница*<br/>
(в) Индекс на нулевой основе страницы вкладок, который был активен.

### <a name="remarks"></a>Примечания

Визуальный эффект настройки активной вкладки зависит от того, включили ли вы анимацию. Для получения дополнительной информации [см. CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).

## <a name="cmfcoutlookbaronbeforeanimation"></a><a name="onbeforeanimation"></a>CMFCOutlookBar::OnbeforeAnimation

Вызывается [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) перед страницей вкладок устанавливается в качестве активной вкладки с помощью анимации.

```cpp
virtual BOOL OnBeforeAnimation(int nPage);
```

### <a name="parameters"></a>Параметры

*nСтраница*<br/>
(в) Индекс на нулевой основе страницы вкладок, который вот-вот будет настроен активным.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если анимация должна использоваться при настройке новой активной вкладки, или FALSE, если анимация должна быть отключена.

### <a name="remarks"></a>Примечания

## <a name="cmfcoutlookbaronscroll"></a><a name="onscroll"></a>CMFCOutlookBar::OnScroll

Вызывается в рамках, если панель Outlook прокручивается вверх или вниз.

```cpp
virtual void OnScroll(BOOL bDown);
```

### <a name="parameters"></a>Параметры

*bДаун*<br/>
(в) ПРАВДА, если панель Outlook прокрутки вниз, или FALSE, если он прокрутки вверх.

### <a name="remarks"></a>Примечания

## <a name="cmfcoutlookbarremovecustompage"></a><a name="removecustompage"></a>CMFCOutlookBar::RemoveCustomPage

Удаляет пользовательскую страницу вкладки панели Outlook.

```cpp
BOOL RemoveCustomPage(
    UINT uiPage,
    CMFCOutlookBarTabCtrl* pTargetWnd);
```

### <a name="parameters"></a>Параметры

*uiPage*<br/>
(в) Нулевой индекс страницы в окне родительского Outlook.

*pTargetWnd*<br/>
(в) Указатель на родительское окно Outlook.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользовательская страница была успешно удалена; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы удалить пользовательские страницы. Когда страница удалена, идентификатор управления возвращается в пул доступных идентификаторов.

Необходимо предоставить указатель на объект [класса CMFCOutlookBarTabCtrl,](../../mfc/reference/cmfcoutlookbartabctrl-class.md) в котором в настоящее время находится страница, которая будет удалена. Обратите внимание, что пользователь может перемещать съемные страницы между различными барами Outlook, но информация о пользовательской странице находится в панели Outlook, для которой вы вызвали [CMFCOutlookBar::CreateCustomPage](#createcustompage).

Используйте [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) для получения указателя на окно Outlook.

## <a name="cmfcoutlookbarsetbuttonsfont"></a><a name="setbuttonsfont"></a>CMFCOutlookBar::SetButton

Устанавливает шрифт текста на кнопках панели Outlook.

```cpp
void SetButtonsFont(
    CFont* pFont,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
(в) Определяет новый шрифт.

*bRedraw*<br/>
(в) Если true, панель Outlook будет перерисована.

### <a name="remarks"></a>Примечания

Используйте этот метод для установки шрифта для текста, отображаемого на кнопках страницы вкладок Outlook.

## <a name="cmfcoutlookbarsetmode2003"></a><a name="setmode2003"></a>CMFCOutlookBar:SetMode2003

Уточняется, имитирует ли поведение бара Outlook поведение Outlook outlook.

```cpp
void SetMode2003(BOOL bMode2003=TRUE);
```

### <a name="parameters"></a>Параметры

*bMode2003*<br/>
(в) Если TRUE, режим Office 2003 включен.

### <a name="remarks"></a>Примечания

Используйте эту функцию для включения или отключать режим Office 2003. В этом режиме панель Outlook имеет дополнительную панель инструментов с кнопкой настройки. Поведение бара Outlook соответствует поведению бара Outlook в Microsoft Office 2003.

По умолчанию этот режим отключен.

> [!NOTE]
> Эта функция должна быть вызвана до [CMFCOutlookBar::Создание](#create).

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)<br/>
[Класс CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)
