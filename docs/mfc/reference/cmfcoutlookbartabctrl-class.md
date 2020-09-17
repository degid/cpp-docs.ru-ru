---
title: CMFCOutlookBarTabCtrl Class
ms.date: 10/18/2018
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
helpviewer_keywords:
- CMFCOutlookBarTabCtrl [MFC], AddControl
- CMFCOutlookBarTabCtrl [MFC], CanShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], CanShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], Create
- CMFCOutlookBarTabCtrl [MFC], EnableAnimation
- CMFCOutlookBarTabCtrl [MFC], EnableInPlaceEdit
- CMFCOutlookBarTabCtrl [MFC], EnableScrollButtons
- CMFCOutlookBarTabCtrl [MFC], GetBorderSize
- CMFCOutlookBarTabCtrl [MFC], GetVisiblePageButtons
- CMFCOutlookBarTabCtrl [MFC], IsAnimation
- CMFCOutlookBarTabCtrl [MFC], IsMode2003
- CMFCOutlookBarTabCtrl [MFC], OnShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowOptions
- CMFCOutlookBarTabCtrl [MFC], SetActiveTab
- CMFCOutlookBarTabCtrl [MFC], SetBorderSize
- CMFCOutlookBarTabCtrl [MFC], SetPageButtonTextAlign
- CMFCOutlookBarTabCtrl [MFC], SetToolbarImageList
- CMFCOutlookBarTabCtrl [MFC], SetVisiblePageButtons
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
ms.openlocfilehash: 9c5d7d5135c3b207bbf113970deb8cbeb186bcca
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749567"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class

Элемент управления "вкладка", который имеет внешний вид раздела **Область переходов** в Microsoft Outlook.
Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Конструктор по умолчанию.|
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCOutlookBarTabCtrl:AddControl](#addcontrol)|Добавляет элемент управления Windows в новую вкладку в бар Outlook.|
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Вызывается фреймворком для определения размеров окна для отсылки, `CMFCBaseTabCtrl::CalcRectEdit`которая появляется при переиме пользователя вкладки. (Overrides.)|
|[CMFCOutlookBarTabCtrl:CanShowFewerPageButtons](#canshowfewerpagebuttons)|Вызывается инфраструктурой во время операций по оптимизации, чтобы определить, можно ли отображать меньше кнопок страницы вкладок панели Outlook, чем в настоящее время.|
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Вызывается инфраструктурой во время операций по оптимизации, чтобы определить, можно ли отображать больше кнопок страницы вкладок Outlook, чем в настоящее время.|
|[CMFCOutlookBarTabCtrl::Создание](#create)|Создает элемент управления вкладки панели Outlook.|
|`CMFCOutlookBarTabCtrl::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCOutlookBarTabCtrl:EnableAnimation](#enableanimation)|Определяет, включена ли анимация, возникающая во время переключения между активными вкладками.|
|[CMFCOutlookBarTabCtrl:EnableInPlaceEdit](#enableinplaceedit)|Уточняется, может ли пользователь изменять текстовые метки на кнопках вкладок бара Outlook. (Переопределяет [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|
|[CMFCOutlookBarTabCtrl:EnableScrollButtons](#enablescrollbuttons)|Вызывается фреймворком для включения кнопок, позволяющих пользователю прокручивать кнопки на панели Outlook.|
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Определяет область, которая содержит указанную точку. (Оверлет [CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|
|[CMFCOutlookBarTabCtrl:GetBorderSize](#getbordersize)|Возвращает размер границы элемента управления вкладки Outlook.|
|`CMFCOutlookBarTabCtrl::GetTabArea`|Извлекает размер и положение области вкладки набора вкладок. (Отменяет [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|
|`CMFCOutlookBarTabCtrl::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||
|[CMFCOutlookBarTabCtrl::Анимация](#isanimation)|Определяет, включена ли анимация, возникающая во время переключения между активными вкладками.|
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Определяет, находится ли элемент управления вкладками панели Outlook в режиме, который эмулирует Microsoft Outlook 2003.|
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Определяет, находится ли точка внутри области вкладок. (Переопределяет [CMFCBasetabctrl::Isptintabarea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Указывает, является ли вкладка отделяемой. (Оверлет [CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Вызывается фреймворком при вставке или удалении вкладки. (Переопределяет `CMFCBaseTabCtrl::OnChangeTabs`.)|
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|Вызывается фреймворком, чтобы уменьшить количество видимых кнопок страницы вкладок.|
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Вызывается фреймворком, чтобы увеличить количество видимых кнопок страницы вкладок.|
|[CMFCOutlookBarTabCtrl:OnShowOptions](#onshowoptions)|Отображает диалог **параметры навигации.**|
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Повторно вычисляет внутренний макет набора вкладок. (Оверлет [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Устанавливает активную вкладку. (Отменяет [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|
|[CMFCOutlookBarTabCtrl:SetBorderSize](#setbordersize)|Устанавливает размер границы элемента управления вкладки Outlook.|
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Устанавливает выравнивание текстовых меток на кнопках вкладок бара Outlook.|
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Устанавливает битную карту, содержащую значки, отображаемые в нижней части панели Outlook в режиме Outlook 2003 (см. [класс CMFCOutlookBar).](../../mfc/reference/cmfcoutlookbar-class.md)|
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||

## <a name="remarks"></a>Примечания

Для создания панели Outlook с поддержкой `CMFCOutlookBar` стыковки используйте объект для размещения элемента управления вкладкой панели Outlook. Для получения дополнительной информации [см.](../../mfc/reference/cmfcoutlookbar-class.md)

## <a name="example"></a>Пример

В следующем примере показано, `CMFCOutlookBarTabCtrl` как инициализировать `CMFCOutlookBarTabCtrl` объект и использовать различные методы в классе. На примере показано, как включить редактирование на месте текстовой метки на кнопках страницы вкладок панели Outlook, включить анимацию, включить ручки прокрутки, которые позволяют пользователю прокручивать кнопки на панели Outlook, установить размер границы элемента управления вкладкой Outlook и установить выравнивание текстовых меток на кнопках вкладок панели Outlook. Этот фрагмент кода является частью [образца Outlook Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)

[CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxoutlookbartabctrl.h

## <a name="cmfcoutlookbartabctrladdcontrol"></a><a name="addcontrol"></a>CMFCOutlookBarTabCtrl:AddControl

Добавляет элемент управления Windows в новую вкладку в бар Outlook.

```cpp
void AddControl(
    CWnd* pWndCtrl,
    LPCTSTR lpszName,
    int nImageID=-1,
    BOOL bDetachable=TRUE,
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```

### <a name="parameters"></a>Параметры

*pWndCtrl*<br/>
(в) Указатель на элемент управления для добавления.

*lpszName*<br/>
(в) Упогоняет название вкладки.

*bDetachable*<br/>
(в) Если true, страница будет создана как съемная.

*nImageID*<br/>
(в) Индекс изображения во внутреннем списке изображений для отображения изображения в новой вкладке.

*dwControlBarStyle*<br/>
(в) Обращите AFX_ CBRS_ стиль для завернутых стыковочных стекол.

### <a name="remarks"></a>Примечания

Используйте эту функцию, чтобы добавить элемент управления в качестве новой страницы панели Outlook.

Эта функция внутренне вызывает [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).

Если вы установите *bDetachable* для `AddControl` `CDockablePaneAdapter` TRUE, внутренне создает объект и обертывает дополнительный элемент управления. Он автоматически устанавливает класс времени выполнения окна вкладки `CMFCOutlookBar` в класс времени выполнения и класс `CMultiPaneFrameWnd`времени выполнения плавающей рамы.

### <a name="example"></a>Пример

В следующем примере показано, `AddControl` как `CMFCOutlookBarTabCtrl` использовать метод в классе. Этот фрагмент кода является частью [образца Outlook Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]

## <a name="cmfcoutlookbartabctrlcanshowfewerpagebuttons"></a><a name="canshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl:CanShowFewerPageButtons

Вызывается инфраструктурой во время операций по оптимизации, чтобы определить, можно ли отображать меньше ежей кнопок вкладки панели Outlook, чем это видно в настоящее время.

```
virtual BOOL CanShowFewerPageButtons() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если есть более чем одна кнопка; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Управление вкладками панели Outlook динамически добавляет или удаляет вкладки с дисплея в зависимости от того, сколько места доступно. Этот метод используется рамками для оказания помощи в этом процессе.

## <a name="cmfcoutlookbartabctrlcanshowmorepagebuttons"></a><a name="canshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowMorePageButtons

Вызывается инфраструктурой во время операций по оптимизации, чтобы определить, можно ли отображать больше кнопок страницы вкладок Outlook, чем в настоящее время.

```
virtual BOOL CanShowMorePageButtons() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если есть кнопки, которые в настоящее время не видны; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Управление вкладками панели Outlook динамически добавляет или удаляет вкладки с дисплея, в зависимости от того, сколько места доступно. Этот метод используется рамками для оказания помощи в этом процессе.

## <a name="cmfcoutlookbartabctrlcreate"></a><a name="create"></a>CMFCOutlookBarTabCtrl::Создание

Создает элемент управления вкладки панели Outlook.

```
virtual BOOL Create(
    const CRect& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Определяет начальный размер и положение в пикселях.

*pParentWnd*<br/>
(в) Указывает на родительское окно. Не должно быть NULL.

*nID*<br/>
(в) Идентификатор управления.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент управления был успешно создан; в противном случае 0.

### <a name="remarks"></a>Примечания

Обычно элементы управления вкладками панели Outlook создаются, когда [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md) контролирует WM_CREATE сообщение процесса.

## <a name="cmfcoutlookbartabctrlenableanimation"></a><a name="enableanimation"></a>CMFCOutlookBarTabCtrl:EnableAnimation

Определяет, включена ли анимация, возникающая во время переключения между активными вкладками.

```
static void EnableAnimation(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) Уточняется, должна ли анимация быть включена или отключена.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы включить и отключить анимацию. Когда пользователь открывает страницу вкладок, подпись страницы скользит вверх или вниз, если анимация включена. Если анимация отключена, страница сразу же активируется.

По умолчанию включена анимация.

## <a name="cmfcoutlookbartabctrlenableinplaceedit"></a><a name="enableinplaceedit"></a>CMFCOutlookBarTabCtrl:EnableInPlaceEdit

Уточняется, может ли пользователь изменять текстовые метки на кнопках страницы вкладок в баре Outlook.

```
virtual void EnableInPlaceEdit(BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Если true, включите редактирование текста на месте. Если FALSE, отогнать на месте редактирования.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы включить или отключить редактирование текстовых меток на кнопках страницы вкладок. По умолчанию редактирование на месте отключено.

## <a name="cmfcoutlookbartabctrlenablescrollbuttons"></a><a name="enablescrollbuttons"></a>CMFCOutlookBarTabCtrl:EnableScrollButtons

Вызывается фректов, чтобы включить ручки прокрутки, которые позволяют пользователю прокручивать кнопки на панели панели Outlook.

```cpp
void EnableScrollButtons(
    BOOL bEnable = TRUE,
    BOOL bIsUp = TRUE,
    BOOL bIsDown = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) Определяет, отображаются ли кнопки прокрутки.

*bIsUp*<br/>
(в) Определяет, отображается ли верхняя панель прокрутки.

*bIsDown*<br/>
(в) Определяет, отображается ли нижняя панель прокрутки.

### <a name="remarks"></a>Примечания

Позволяет отображать кнопки прокрутки. Этот метод вызывается фректовом при изменении активной вкладки для восстановления кнопок прокрутки.

## <a name="cmfcoutlookbartabctrlgetbordersize"></a><a name="getbordersize"></a>CMFCOutlookBarTabCtrl:GetBorderSize

Возвращает размер границы элемента управления вкладки Outlook.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер границы, в пикселях.

## <a name="cmfcoutlookbartabctrlgetvisiblepagebuttons"></a><a name="getvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::GetVisiblePageButtons

```
int GetVisiblePageButtons() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcoutlookbartabctrlisanimation"></a><a name="isanimation"></a>CMFCOutlookBarTabCtrl::Анимация

Определяет, включена ли анимация, возникающая во время переключения между активными вкладками.

```
static BOOL IsAnimation();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если анимация включена; в противном случае 0.

### <a name="remarks"></a>Примечания

Позвоните в [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation) функции для включения или отключить анимацию.

## <a name="cmfcoutlookbartabctrlismode2003"></a><a name="ismode2003"></a>CMFCOutlookBarTabCtrl::IsMode2003

Определяет, находится ли элемент управления вкладками панели Outlook в режиме, который эмулирует Microsoft Outlook 2003.

```
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если управление вкладками панели Outlook находится в режиме Outlook 2003; в противном случае FALSE;

### <a name="remarks"></a>Примечания

Это значение устанавливается [CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).

## <a name="cmfcoutlookbartabctrlonshowfewerpagebuttons"></a><a name="onshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowFewerPageButtons

Вызывается фреймворком, чтобы уменьшить количество видимых кнопок страницы вкладок.

```
virtual void OnShowFewerPageButtons();
```

### <a name="remarks"></a>Примечания

Этот метод регулирует количество видимых кнопок вкладок страницы при повторном размере элемента управления.

## <a name="cmfcoutlookbartabctrlonshowmorepagebuttons"></a><a name="onshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowMorePageButtons

Вызывается фреймворком, чтобы увеличить количество видимых кнопок страницы вкладок.

```
virtual void OnShowMorePageButtons();
```

### <a name="remarks"></a>Примечания

Этот метод регулирует количество кнопок страницы вкладок, которые видны при повторном размере элемента управления.

## <a name="cmfcoutlookbartabctrlonshowoptions"></a><a name="onshowoptions"></a>CMFCOutlookBarTabCtrl:OnShowOptions

Отображает диалоговую коробку **навигационных опций Pane Options.**

```
virtual void OnShowOptions();
```

### <a name="remarks"></a>Примечания

Диалоговая коробка **Navigation Pane Options** позволяет пользователю выбрать, какие кнопки страницы вкладок должны отображаться, и порядок, в котором они отображаются.

Этот метод вызывается фректовой, когда пользователь выбирает элемент меню **параметры навигации** из меню настройки элемента управления.

## <a name="cmfcoutlookbartabctrlsetactivetab"></a><a name="setactivetab"></a>CMFCOutlookBarTabCtrl::SetActiveTab

Устанавливает активную вкладку. Активная вкладка является открытой, с ее содержимым видимым.

```
virtual BOOL SetActiveTab(int iTab);
```

### <a name="parameters"></a>Параметры

*iTab*<br/>
(в) Нулевой индекс вкладки, которая будет открыта.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если указанная вкладка была успешно открыта; в противном случае 0.

### <a name="remarks"></a>Примечания

Визуальный эффект настройки активной вкладки зависит от того, включили ли вы анимацию. Для получения дополнительной информации [см. CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation).

## <a name="cmfcoutlookbartabctrlsetbordersize"></a><a name="setbordersize"></a>CMFCOutlookBarTabCtrl:SetBorderSize

Устанавливает размер границы элемента управления вкладки Outlook.

```cpp
void SetBorderSize(int nBorderSize);
```

### <a name="parameters"></a>Параметры

*nBorderSize*<br/>
(в) Определяет новый размер границы в пикселях.

### <a name="remarks"></a>Примечания

Устанавливает новый размер границы и пересчитывает макет окна outlook.

## <a name="cmfcoutlookbartabctrlsetpagebuttontextalign"></a><a name="setpagebuttontextalign"></a>CMFCOutlookBarTabCtrl::SetPageButtonTextAlign

Устанавливает выравнивание текстовых меток на кнопках вкладок бара Outlook.

```cpp
void SetPageButtonTextAlign(
    UINT uiAlign,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Параметры

*uiAlign*<br/>
(в) Определяет выравнивание текста.

*bRedraw*<br/>
(в) Если true, окно перспективы будет перерисовано.

### <a name="remarks"></a>Примечания

Используйте эту функцию, чтобы изменить выравнивание текста для кнопок страницы.

*uiAlign* может быть одним из следующих значений:

|Константа|Значение|
|--------------|-------------|
|TA_LEFT|Левое выравнивание|
|TA_CENTER|Выравнивание центра|
|TA_RIGHT|Правое выравнивание|

Значение по умолчанию является TA_CENTER.

## <a name="cmfcoutlookbartabctrlsettoolbarimagelist"></a><a name="settoolbarimagelist"></a>CMFCOutlookBarTabCtrl::SetToolbarImageList

Устанавливает битную карту, содержащую значки, отображаемые в нижней части панели Outlook в режиме Outlook 2003.

```
BOOL SetToolbarImageList(
    UINT uiID,
    int cx,
    COLORREF clrTransp=RGB(255, 0, 255));
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
(в) Определяет идентификатор ресурса изображения для загрузки.

*Cx*<br/>
(в) Определяет ширину изображения в списке изображений в пикселях.

*clrTransp*<br/>
(в) Значение RGB, которое определяет прозрачный цвет.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE в случае успеха; в противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Используйте эту функцию, чтобы прикрепить список изображений, изображения которого будут отображаться на кнопках панели инструментов в режиме Microsoft Office 2003. Индексы изображений должны соответствовать индексам страниц.

Этот метод не следует называть если не в режиме Microsoft Office 2003. Для получения дополнительной информации [см.](../../mfc/reference/cmfcoutlookbar-class.md)

## <a name="cmfcoutlookbartabctrlsetvisiblepagebuttons"></a><a name="setvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::SetVisiblePageButtons

```cpp
void SetVisiblePageButtons(int nVisiblePageButtons);
```

### <a name="parameters"></a>Параметры

(в) *nVisiblePageButtons*<br/>

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)<br/>
[Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[Класс CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)
