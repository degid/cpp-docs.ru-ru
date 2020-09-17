---
title: Класс CMFCMenuBar
ms.date: 10/18/2018
f1_keywords:
- CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar::AdjustLocations
- AFXMENUBAR/CMFCMenuBar::AllowChangeTextLabels
- AFXMENUBAR/CMFCMenuBar::AllowShowOnPaneMenu
- AFXMENUBAR/CMFCMenuBar::CalcFixedLayout
- AFXMENUBAR/CMFCMenuBar::CalcLayout
- AFXMENUBAR/CMFCMenuBar::CalcMaxButtonHeight
- AFXMENUBAR/CMFCMenuBar::CanBeClosed
- AFXMENUBAR/CMFCMenuBar::CanBeRestored
- AFXMENUBAR/CMFCMenuBar::Create
- AFXMENUBAR/CMFCMenuBar::CreateEx
- AFXMENUBAR/CMFCMenuBar::CreateFromMenu
- AFXMENUBAR/CMFCMenuBar::EnableHelpCombobox
- AFXMENUBAR/CMFCMenuBar::EnableMenuShadows
- AFXMENUBAR/CMFCMenuBar::GetAvailableExpandSize
- AFXMENUBAR/CMFCMenuBar::GetColumnWidth
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenu
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::GetFloatPopupDirection
- AFXMENUBAR/CMFCMenuBar::GetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::GetHelpCombobox
- AFXMENUBAR/CMFCMenuBar::GetHMenu
- AFXMENUBAR/CMFCMenuBar::GetMenuFont
- AFXMENUBAR/CMFCMenuBar::GetMenuItem
- AFXMENUBAR/CMFCMenuBar::GetRowHeight
- AFXMENUBAR/CMFCMenuBar::GetSystemButton
- AFXMENUBAR/CMFCMenuBar::GetSystemButtonsCount
- AFXMENUBAR/CMFCMenuBar::GetSystemMenu
- AFXMENUBAR/CMFCMenuBar::HighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsButtonExtraSizeAvailable
- AFXMENUBAR/CMFCMenuBar::IsHighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsMenuShadows
- AFXMENUBAR/CMFCMenuBar::IsRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommands
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommandsDelay
- AFXMENUBAR/CMFCMenuBar::LoadState
- AFXMENUBAR/CMFCMenuBar::OnChangeHot
- AFXMENUBAR/CMFCMenuBar::OnDefaultMenuLoaded
- AFXMENUBAR/CMFCMenuBar::OnSendCommand
- AFXMENUBAR/CMFCMenuBar::OnSetDefaultButtonText
- AFXMENUBAR/CMFCMenuBar::OnToolHitTest
- AFXMENUBAR/CMFCMenuBar::PreTranslateMessage
- AFXMENUBAR/CMFCMenuBar::RestoreOriginalstate
- AFXMENUBAR/CMFCMenuBar::SaveState
- AFXMENUBAR/CMFCMenuBar::SetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::SetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::SetMaximizeMode
- AFXMENUBAR/CMFCMenuBar::SetMenuButtonRTC
- AFXMENUBAR/CMFCMenuBar::SetMenuFont
- AFXMENUBAR/CMFCMenuBar::SetRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::SetShowAllCommands
helpviewer_keywords:
- CMFCMenuBar [MFC], AdjustLocations
- CMFCMenuBar [MFC], AllowChangeTextLabels
- CMFCMenuBar [MFC], AllowShowOnPaneMenu
- CMFCMenuBar [MFC], CalcFixedLayout
- CMFCMenuBar [MFC], CalcLayout
- CMFCMenuBar [MFC], CalcMaxButtonHeight
- CMFCMenuBar [MFC], CanBeClosed
- CMFCMenuBar [MFC], CanBeRestored
- CMFCMenuBar [MFC], Create
- CMFCMenuBar [MFC], CreateEx
- CMFCMenuBar [MFC], CreateFromMenu
- CMFCMenuBar [MFC], EnableHelpCombobox
- CMFCMenuBar [MFC], EnableMenuShadows
- CMFCMenuBar [MFC], GetAvailableExpandSize
- CMFCMenuBar [MFC], GetColumnWidth
- CMFCMenuBar [MFC], GetDefaultMenu
- CMFCMenuBar [MFC], GetDefaultMenuResId
- CMFCMenuBar [MFC], GetFloatPopupDirection
- CMFCMenuBar [MFC], GetForceDownArrows
- CMFCMenuBar [MFC], GetHelpCombobox
- CMFCMenuBar [MFC], GetHMenu
- CMFCMenuBar [MFC], GetMenuFont
- CMFCMenuBar [MFC], GetMenuItem
- CMFCMenuBar [MFC], GetRowHeight
- CMFCMenuBar [MFC], GetSystemButton
- CMFCMenuBar [MFC], GetSystemButtonsCount
- CMFCMenuBar [MFC], GetSystemMenu
- CMFCMenuBar [MFC], HighlightDisabledItems
- CMFCMenuBar [MFC], IsButtonExtraSizeAvailable
- CMFCMenuBar [MFC], IsHighlightDisabledItems
- CMFCMenuBar [MFC], IsMenuShadows
- CMFCMenuBar [MFC], IsRecentlyUsedMenus
- CMFCMenuBar [MFC], IsShowAllCommands
- CMFCMenuBar [MFC], IsShowAllCommandsDelay
- CMFCMenuBar [MFC], LoadState
- CMFCMenuBar [MFC], OnChangeHot
- CMFCMenuBar [MFC], OnDefaultMenuLoaded
- CMFCMenuBar [MFC], OnSendCommand
- CMFCMenuBar [MFC], OnSetDefaultButtonText
- CMFCMenuBar [MFC], OnToolHitTest
- CMFCMenuBar [MFC], PreTranslateMessage
- CMFCMenuBar [MFC], RestoreOriginalstate
- CMFCMenuBar [MFC], SaveState
- CMFCMenuBar [MFC], SetDefaultMenuResId
- CMFCMenuBar [MFC], SetForceDownArrows
- CMFCMenuBar [MFC], SetMaximizeMode
- CMFCMenuBar [MFC], SetMenuButtonRTC
- CMFCMenuBar [MFC], SetMenuFont
- CMFCMenuBar [MFC], SetRecentlyUsedMenus
- CMFCMenuBar [MFC], SetShowAllCommands
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
ms.openlocfilehash: f25bff9564eb7a4290f958f0b7810cac8ef7e238
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749619"
---
# <a name="cmfcmenubar-class"></a>Класс CMFCMenuBar

Строка меню, которая реализует закрепление.
Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCMenuBar : public CMFCToolbar
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|(Переопределяет `CMFCToolBar::AdjustLocations`.)|
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|Уточняется, можно ли отображать текстовые метки под изображениями на кнопках панели инструментов. (Перекрывает [CMFCToolBar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels).)|
|[CMFCMenuBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Переопределяет `CPane::AllowShowOnPaneMenu`.)|
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|Вычисляет горизонтальный размер панели инструментов. (Переопределяет [CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout).)|
|[CMFCMenuBar::CalcLayout](#calclayout)|(Переопределяет `CMFCToolBar::CalcLayout`.)|
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|Вычисляет максимальную высоту кнопок в панели инструментов. (Переопределяет [CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|
|[CMFCMenuBar::CanbeClosed](#canbeclosed)|Определяет, может ли пользователь закрыть панель инструментов. (Переопределяет [CMFCToolBar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed).)|
|[CMFCMenuBar::CanBeRestored](#canberestored)|Определяет, может ли система восстановить панель инструментов в исходное состояние после настройки. (Переопределяет [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[CMFCMenuBar::Создание](#create)|Создает элемент управления меню и `CMFCMenuBar` прикрепляет его к объекту.|
|[CMFCMenuBar::CreateEx](#createex)|Создает `CMFCMenuBar` объект с дополнительными опциями стиля.|
|[CMFCMenuBar::СозданиеFromMenu](#createfrommenu)|Инициализирует объект `CMFCMenuBar`. Принимает параметр HMENU, который выступает в `CMFCMenuBar`качестве шаблона для населенного пункта.|
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|Включает комбо-коробку **справки,** расположенную в правой части панели меню.|
|[CMFCMenuBar:EnableMenuShadows](#enablemenushadows)|Определяет, следует ли отображать тени для всплывающих меню.|
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|(Переопределяет [CPane::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize).)|
|[CMFCMenuBar::GetColumnШирин](#getcolumnwidth)|Возвращает ширину кнопок панели инструментов. (Переопределяет [CMFCToolBar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth).)|
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|Возвращает ручку в исходное меню в файле ресурса.|
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|Возвращает идентификатор ресурса для исходного меню в файле ресурса.|
|[CMFCMenuBar:GetFloatPopupDirection](#getfloatpopupdirection)||
|[CMFCMenuBar:GetForceDownСтрелы](#getforcedownarrows)||
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|Возвращает указатель в комбо-поле **Справки.**|
|[CMFCMenuBar::GetHMenu](#gethmenu)|Возвращает ручку в меню, прикрепленное к объекту. `CMFCMenuBar`|
|[CMFCMenuBar::GetMenuFont](#getmenufont)|Возвращает текущий глобальный шрифт для объектов меню.|
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|Возвращает кнопку панели инструментов, связанную с предоставленным индексом элемента.|
|[CMFCMenuBar::GetRowHeight](#getrowheight)|Возвращает высоту кнопок панели инструментов. (Переопределяет [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFCMenuBar:GetSystemButton](#getsystembutton)||
|[CMFCMenuBar::GetSystemButton](#getsystembuttonscount)||
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|Указывается, выделены ли отключенные элементы меню.|
|[CMFCMenuBar::IsButtonExtraSizeДоступно](#isbuttonextrasizeavailable)|Определяет, может ли панель инструментов отображать кнопки, которые имеют расширенные границы. (Переопределяет [CMFCToolBar::IsbuttonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|
|[CMFCMenuBar:: IsHighlightDisabledItems](#ishighlightdisableditems)|Указывается, выделены ли отключенные элементы.|
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|Указывает, нарисованы ли тени для всплывающих меню.|
|[CMFCMenuBar::НедавноИспользованныеMenus](#isrecentlyusedmenus)|Указывается, отображаются ли недавно используемые команды меню в панели меню.|
|[CMFCMenuBar::IsShowAllCommands](#isshowallcommands)|Указывает, отображаются ли всплывающие меню все команды.|
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|Указывает, отображаются ли меню все команды после короткой задержки.|
|[CMFCMenuBar::Нагрузка](#loadstate)|Загружает состояние `CMFCMenuBar` объекта из реестра.|
|[CMFCMenuBar::OnChangeHot](#onchangehot)|Вызывается по системе, когда пользователь выбирает кнопку на панели инструментов. (Переопределяет [CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|Вызывается фреймворком при загрузке окна кадра меню по умолчанию из файла ресурса.|
|[CMFCMenuBar::OnsendCommand](#onsendcommand)|(Переопределяет `CMFCToolBar::OnSendCommand`.)|
|[CMFCMenuBar::OnSetDefaultButtonText](#onsetdefaultbuttontext)|Вызывается в рамках, когда меню находится в режиме настройки и пользователь изменяет текст элемента меню.|
|[CMFCMenuBar:Ontoolhittest](#ontoolhittest)|(Переопределяет `CMFCToolBar::OnToolHitTest`.)|
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(Переопределяет `CMFCToolBar::PreTranslateMessage`.)|
|[CMFCMenuBar::ВосстановлениеOriginalstate](#restoreoriginalstate)|Вызывается в рамках, когда меню находится в режиме настройки и пользователь выбирает **сбросить** для панели меню.|
|[CMFCMenuBar::SaveState](#savestate)|Сохраняет состояние `CMFCMenuBar` объекта в реестре.|
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|Устанавливает исходное меню в файле ресурса.|
|[CMFCMenuBar::SetForceDownСтрелы](#setforcedownarrows)||
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|Вызывается по системе, когда окно ребенка MDI изменяет режим отображения. Если окно mDI ребенка является недавно максимизируется или больше не максимизируется, этот метод обновляет панель меню.|
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|Устанавливает информацию о классе выполнения, которая генерируется при динамическом создается кнопки меню.|
|[CMFCMenuBar::SetMenuFont](#setmenufont)|Устанавливает шрифт для всех меню в приложении.|
|[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)|Уточняется, отображает ли панель меню недавно используемые команды меню.|
|[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)|Определяет, отображаетли ли панель меню все команды.|

## <a name="remarks"></a>Примечания

Класс `CMFCMenuBar` представляет собой панель меню, которая реализует функциональность стыковки. Он напоминает панель инструментов, хотя она не может быть закрыта - она всегда отображается.

`CMFCMenuBar`поддерживает возможность отображения недавно использованных объектов элемента меню. Если эта опция `CMFCMenuBar` включена, отображается только подмножество доступных команд при первом просмотре. После этого недавно используемые команды отображаются вместе с исходным подмножеством команд. Кроме того, пользователь всегда может расширить меню, чтобы просмотреть все доступные команды. Таким образом, каждая доступная команда настроена для отображения постоянно или для отображения только в том случае, если она была выбрана недавно.

Чтобы использовать `CMFCMenuBar` объект, вдохните его в основной объект оконной рамы. При обработке `WM_CREATE` сообщения, вызова `CMFCMenuBar::Create` или `CMFCMenuBar::CreateEx`. Независимо от того, какой функции создания вы используете, пройти в указатель на окно основной кадр. Затем включите стыковку, позвонив [в CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking). Стыковка этого меню, позвонив [cFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane).

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCMenuBar` . На примере показано, как настроить стиль панели, включить кнопку настройки, включить поле справки, включить тени для всплывающих меню и обновить панель меню. Этот фрагмент кода является частью [образца IE Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

`CMFCMenuBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxmenubar.h

## <a name="cmfcmenubaradjustlocations"></a><a name="adjustlocations"></a>CMFCMenuBar::Настройки

Корректирует положение пунктов меню в баре меню.

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarallowchangetextlabels"></a><a name="allowchangetextlabels"></a>CMFCMenuBar::AllowChangeTextLabels

Определяет, разрешены ли текстовые метки под изображениями в панели меню.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если пользователь может выбрать, чтобы показать текстовые метки под изображениями.

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFCMenuBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCMenuBar::CalcFixedLayout

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

## <a name="cmfcmenubarcalclayout"></a><a name="calclayout"></a>CMFCMenuBar::CalcLayout

```
virtual CSize CalcLayout(
    DWORD dwMode,
    int nLength = -1);
```

### <a name="parameters"></a>Параметры

(в) *dwMode*<br/>

(в) *nДлина*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarcalcmaxbuttonheight"></a><a name="calcmaxbuttonheight"></a>CMFCMenuBar::CalcMaxButtonHeight

```
virtual int CalcMaxButtonHeight();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarcanbeclosed"></a><a name="canbeclosed"></a>CMFCMenuBar::CanbeClosed

```
virtual BOOL CanBeClosed() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarcanberestored"></a><a name="canberestored"></a>CMFCMenuBar::CanBeRestored

```
virtual BOOL CanBeRestored() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarcreate"></a><a name="create"></a>CMFCMenuBar::Создание

Создает элемент управления меню и прикрепляет его к объекту [CMFCMenuBar.](../../mfc/reference/cmfcmenubar-class.md)

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,
    UINT nID = AFX_IDW_MENUBAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
(в) Указатель на родительское окно `CMFCMenuBar` для нового объекта.

*dwStyle*<br/>
(в) Стиль нового меню бар.

*nID*<br/>
(в) Идентификатор для окна ребенка в панели меню.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

После построения `CMFCMenuBar` объекта необходимо `Create`вызвать . Этот метод `CMFCMenuBar` создает элемент управления и `CMFCMenuBar` прикрепляет его к объекту.

Для получения дополнительной информации о стилях панели инструментов см. [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).

## <a name="cmfcmenubarcreateex"></a><a name="createex"></a>CMFCMenuBar::CreateEx

Создает объект [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) с указанными расширенными стилями.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = TBSTYLE_FLAT,
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,
    CRect rcBorders = CRect(1,
    1,
    1,
    1),
    UINT nID =AFX_IDW_MENUBAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
(в) Указатель на родительское окно `CMFCMenuBar` нового объекта.

*dwCtrlStyle*<br/>
(в) Дополнительные стили для нового бара меню.

*dwStyle*<br/>
(в) Основной стиль нового меню бар.

*rcГраници*<br/>
(в) Параметр, `CRect` определяемый размеры границ `CMFCMenuBar` объекта.

*nID*<br/>
(в) Идентификатор для окна ребенка в панели меню.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод успешен; в противном случае 0.

### <a name="remarks"></a>Примечания

Вы должны использовать эту функцию вместо [CMFCMenuBar::Создание,](#create) когда вы хотите указать стили в дополнение к стилю панели инструментов. Некоторые часто используемые дополнительные стили являются TBSTYLE_TRANSPARENT и CBRS_TOP.

Для списков дополнительных стилей см. [common control styles](/windows/win32/Controls/common-control-styles) [Toolbar Control and Button Styles](/windows/win32/Controls/toolbar-control-and-button-styles) [common window styles](/windows/win32/winmsg/window-styles)

### <a name="example"></a>Пример

В следующем примере показано, `CreateEx` как `CMFCMenuBar` использовать метод класса. Этот фрагмент кода является частью [образца IE Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#2](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]

## <a name="cmfcmenubarcreatefrommenu"></a><a name="createfrommenu"></a>CMFCMenuBar::СозданиеFromMenu

Инициализирует объект [CMFCMenuBar.](../../mfc/reference/cmfcmenubar-class.md) Этот метод `CMFCMenuBar` моделирует объект после параметра HMENU.

```
virtual void CreateFromMenu(
    HMENU hMenu,
    BOOL bDefaultMenu = FALSE,
    BOOL bForceUpdate = FALSE);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
(в) Ручка ресурса меню. `CreateFromMenu`использует этот ресурс в `CMFCMenuBar`качестве шаблона для .

*bDefaultМеню*<br/>
(в) Boolean, указывающий, является ли новое меню меню по умолчанию.

*bForceUpdate*<br/>
(в) Boolean, указывающий, является ли этот метод заставляет обновление меню.

### <a name="remarks"></a>Примечания

Используйте этот метод, если вы хотите, чтобы элемент меню имел те же элементы меню, что и ресурс меню. Вы называете этот метод после вызова [CMFCMenuBar::Create](#create) или [CMFCMenuBar::CreateEx](#createex).

## <a name="cmfcmenubarenablehelpcombobox"></a><a name="enablehelpcombobox"></a>CMFCMenuBar::EnableHelpCombobox

Включает комбо-коробку **справки,** расположенную в правой части панели меню.

```cpp
void EnableHelpCombobox(
    UINT uiID,
    LPCTSTR lpszPrompt = NULL,
    int nComboBoxWidth = 150);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
(в) Идентификатор команды для кнопки комбо-коробки **Справки.**

*lpszPrompt*<br/>
(в) Строка, содержащая текст, который фреймворк отображает в комбо-поле, если он пуст и не активен. Например, "Введите текст здесь".

*nComboBoxWidth*<br/>
(в) Ширина кнопки для комбо-бокса в пикселях.

### <a name="remarks"></a>Примечания

Комбо-коробка **Help** напоминает комбо-поле **Help** в панели меню Microsoft Word.

При вызове этого метода с *uiID* набор 0, этот метод скрывает комбо-бокс. В противном случае этот метод автоматически отображает комбо-коробку на правой стороне панели меню. После вызова этого метода позвоните [по телефону CMFCMenuBar::GetHelpCombobox,](#gethelpcombobox) чтобы получить указатель на вставленный объект [CMFCToolBarComboButtonButton.](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

## <a name="cmfcmenubarenablemenushadows"></a><a name="enablemenushadows"></a>CMFCMenuBar:EnableMenuShadows

Включает тени для всплывающих меню.

```
static void EnableMenuShadows(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) Параметр Boolean, указывающий, следует ли включено тени для всплывающих меню.

### <a name="remarks"></a>Примечания

Алгоритм, который использует этот метод, является сложным и может снизить производительность приложения на более медленных системах.

## <a name="cmfcmenubargetavailableexpandsize"></a><a name="getavailableexpandsize"></a>CMFCMenuBar::GetAvailableExpandSize

```
virtual int GetAvailableExpandSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubargetcolumnwidth"></a><a name="getcolumnwidth"></a>CMFCMenuBar::GetColumnШирин

```
virtual int GetColumnWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubargetdefaultmenu"></a><a name="getdefaultmenu"></a>CMFCMenuBar::GetDefaultMenu

Извлекает ручку в исходное меню. Фрейм загружает исходное меню из файла ресурса.

```
HMENU GetDefaultMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка ресурса меню.

### <a name="remarks"></a>Примечания

Если приложение настраивает меню, вы можете использовать этот метод для получения ручки в исходное меню.

## <a name="cmfcmenubargetdefaultmenuresid"></a><a name="getdefaultmenuresid"></a>CMFCMenuBar::GetDefaultMenuResId

Извлекает идентификатор ресурса для меню по умолчанию.

```
UINT GetDefaultMenuResId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурсов меню.

### <a name="remarks"></a>Примечания

Фрейм загружает `CMFCMenuBar` меню по умолчанию для объекта из файла ресурса.

## <a name="cmfcmenubargetfloatpopupdirection"></a><a name="getfloatpopupdirection"></a>CMFCMenuBar:GetFloatPopupDirection

```
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```

### <a name="parameters"></a>Параметры

(в) *pButton*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubargetforcedownarrows"></a><a name="getforcedownarrows"></a>CMFCMenuBar:GetForceDownСтрелы

```
BOOL GetForceDownArrows();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubargethelpcombobox"></a><a name="gethelpcombobox"></a>CMFCMenuBar::GetHelpCombobox

Возвращает указатель в комбо-поле **Справки.**

```
CMFCToolBarComboBoxButton* GetHelpCombobox();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на комбо-коробку **Help.** NULL, если комбо-поле **Справка** скрыто или не включено.

### <a name="remarks"></a>Примечания

Комбо-поле **Help** расположено в правой части панели меню. Позвоните [методCMMenuBar::EnableHelpCombobox,](#enablehelpcombobox) чтобы включить этот комбо-бокс.

## <a name="cmfcmenubargethmenu"></a><a name="gethmenu"></a>CMFCMenuBar::GetHMenu

Извлекает ручку в меню, прикрепленное к объекту [CMFCMenuBar.](../../mfc/reference/cmfcmenubar-class.md)

```
HMENU GetHMenu() const;
```

## <a name="cmfcmenubargetmenufont"></a><a name="getmenufont"></a>CMFCMenuBar::GetMenuFont

Извлекает текущий шрифт меню.

```
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Параметры

*bHorz*<br/>
(в) Параметр Boolean, который определяет, возвращать ли горизонтальный или вертикальный шрифт. TRUE указывает на горизонтальный шрифт.

### <a name="return-value"></a>Возвращаемое значение

Указатель на параметр [CFont,](../../mfc/reference/cfont-class.md) содержащий текущий шрифт панели меню.

### <a name="remarks"></a>Примечания

Возвращенный шрифт является глобальным параметром приложения. Для всех `CMFCMenuBar` объектов сохраняются два глобальных шрифта. Эти отдельные шрифты используются для горизонтальных и вертикальных баров меню.

## <a name="cmfcmenubargetmenuitem"></a><a name="getmenuitem"></a>CMFCMenuBar::GetMenuItem

Извлекает объект [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) в панель меню на основе индекса элемента.

```
CMFCToolBarButton* GetMenuItem(int iItem) const;
```

### <a name="parameters"></a>Параметры

*iItem*<br/>
(в) Индекс элемента меню для возврата.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CMFCToolBarButton` объект, который соответствует индексу, указанному *iItem.* NULL, если индекс недействителен.

## <a name="cmfcmenubargetrowheight"></a><a name="getrowheight"></a>CMFCMenuBar::GetRowHeight

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubargetsystembutton"></a><a name="getsystembutton"></a>CMFCMenuBar:GetSystemButton

```
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,
    BOOL bByCommand = TRUE) const;
```

### <a name="parameters"></a>Параметры

(в) *uiBtn*<br/>

(в) *bByCommand*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubargetsystembuttonscount"></a><a name="getsystembuttonscount"></a>CMFCMenuBar::GetSystemButton

```
int GetSystemButtonsCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubargetsystemmenu"></a><a name="getsystemmenu"></a>CMFCMenuBar::GetSystemMenu

```
CMFCToolBarSystemMenuButton* GetSystemMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarhighlightdisableditems"></a><a name="highlightdisableditems"></a>CMFCMenuBar::HighlightDisabledItems

Контролирует, выделяется ли в фреймворке отключенные элементы меню.

```
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```

### <a name="parameters"></a>Параметры

*bHighlight*<br/>
(в) Параметр Boolean, указывающий на то, выделяется ли фреймворк недоступных элементов меню.

### <a name="remarks"></a>Примечания

По умолчанию фреймворк не выделяет недоступные элементы меню, когда пользователь размещает указатель мыши над ними.

## <a name="cmfcmenubarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a>CMFCMenuBar::IsButtonExtraSizeДоступно

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarishighlightdisableditems"></a><a name="ishighlightdisableditems"></a>CMFCMenuBar:: IsHighlightDisabledItems

Указывает, выделяется ли фреймворк недоступных элементов меню.

```
static BOOL IsHighlightDisabledItems();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если недоступные элементы меню выделены; в противном случае FALSE.

### <a name="remarks"></a>Примечания

По умолчанию фреймворк не выделяет недоступные элементы меню, когда пользователь размещает указатель мыши над ними. Для включения этой функции используйте метод [CMFCMenuBar::HighlightDisabledItems.](#highlightdisableditems)

## <a name="cmfcmenubarismenushadows"></a><a name="ismenushadows"></a>CMFCMenuBar::IsMenuShadows

Указывает, рисует ли фреймворк тени для всплывающих меню.

```
static BOOL IsMenuShadows();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если фреймворк рисует тени меню; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Используйте метод [CMFCMenuBar:EnableMenuShadows](#enablemenushadows) для включения или отключать эту функцию.

## <a name="cmfcmenubarisrecentlyusedmenus"></a><a name="isrecentlyusedmenus"></a>CMFCMenuBar::НедавноИспользованныеMenus

Указывается, отображаются ли недавно используемые команды меню в панели меню.

```
static BOOL IsRecentlyUsedMenus();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `CMFCMenuBar` если объект показывает недавно использованные команды меню; в противном случае 0.

### <a name="remarks"></a>Примечания

Используйте функцию [CMFCMenuBar::SetRecentlyUsedMenus,](#setrecentlyusedmenus) чтобы контролировать, показывает ли панель меню недавно используемые команды меню.

## <a name="cmfcmenubarisshowallcommands"></a><a name="isshowallcommands"></a>CMFCMenuBar::IsShowAllCommands

Указывает, отображаются ли меню все команды.

```
static BOOL IsShowAllCommands();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `CMFCMenuBar` если отображает все команды; в противном случае 0.

### <a name="remarks"></a>Примечания

Объект `CMFCMenuBar` может быть настроен либо для отображания всех команд, либо для отображания только подмноза команд. Для получения дополнительной информации об этой функции, см [CMFCMenuBar класса](../../mfc/reference/cmfcmenubar-class.md).

`IsShowAllCommands`расскажет вам, как эта функция `CMFCMenuBar` настроена для объекта. Чтобы контролировать, какие команды меню отображаются, используйте методы [CMFCMenuBar::SetShowAllCommands](#setshowallcommands) и [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus).

## <a name="cmfcmenubarisshowallcommandsdelay"></a><a name="isshowallcommandsdelay"></a>CMFCMenuBar::IsShowAllCommandsDelay

Указывает, отображает ли объект [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) все команды после короткой задержки.

```
static BOOL IsShowAllCommandsDelay();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если панель меню отображает полное меню после короткой задержки; в противном случае 0.

### <a name="remarks"></a>Примечания

При настройке панели меню для отображения недавно использованных элементов в панели меню отображается полное меню одним из двух способов:

- Отображение полного меню после запрограммированной задержки с момента, когда пользователь парит курсор над стрелкой в нижней части меню.

- Отобразите полное меню после того, как пользователь нажмет на стрелку в нижней части меню.

По умолчанию `CMFCMenuBar` все объекты используют опцию для отображения полного меню после короткой задержки. Этот параметр не может быть `CMFCMenuBar` изменен программно в классе. Тем не менее, пользователь может изменить поведение во время настройки панели инструментов с помощью **настраиваемый** диалоговой будки.

## <a name="cmfcmenubarloadstate"></a><a name="loadstate"></a>CMFCMenuBar::Нагрузка

Загружает состояние панели меню из реестра Windows.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Строка, содержащая путь ключа реестра Windows.

*Nindex*<br/>
(в) Идентификатор управления для панели меню.

*uiID*<br/>
(в) Зарезервированное значение.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод был успешным; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Используйте метод [CMFCMenuBar::SaveState,](#savestate) чтобы сохранить состояние панели меню в реестре. Сохраненная информация включает в себя пункты меню, состояние док-станции и положение бара меню.

В большинстве случаев `LoadState`ваша заявка не вызывает . Платформа вызывает этот метод, когда он инициализирует рабочее пространство.

## <a name="cmfcmenubaronchangehot"></a><a name="onchangehot"></a>CMFCMenuBar::OnChangeHot

```
virtual void OnChangeHot(int iHot);
```

### <a name="parameters"></a>Параметры

(в) *iHot*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarondefaultmenuloaded"></a><a name="ondefaultmenuloaded"></a>CMFCMenuBar::OnDefaultMenuLoaded

Платформа вызывает этот метод при загрузке ресурса меню из файла ресурса ресурса.

```
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
(в) Ручка для меню, прикрепленного к объекту. `CMFCMenuBar`

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции не выполняет никаких действий. Переопределить эту функцию для выполнения пользовательского кода после того, как фреймворк загрузит ресурс меню из файла ресурса.

## <a name="cmfcmenubaronsendcommand"></a><a name="onsendcommand"></a>CMFCMenuBar::OnsendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Параметры

(в) *pButton*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubaronsetdefaultbuttontext"></a><a name="onsetdefaultbuttontext"></a>CMFCMenuBar::OnSetDefaultButtonText

Рамочная система называет этот метод, когда пользователь меняет текст элемента в панели меню.

```
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Параметры

*pButton*<br/>
(в) Указатель на объект [CMFCToolBarButton,](../../mfc/reference/cmfctoolbarbutton-class.md) который пользователь хочет настроить.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если фреймворк применяется пользователем, изменяется в меню- бара; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Реализация по умолчанию для этого метода изменяет текст кнопки на текст, который предоставляет пользователь.

## <a name="cmfcmenubarontoolhittest"></a><a name="ontoolhittest"></a>CMFCMenuBar:Ontoolhittest

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

## <a name="cmfcmenubarpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCMenuBar::PreTranslateMessage

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

[in] *pMsg*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarrestoreoriginalstate"></a><a name="restoreoriginalstate"></a>CMFCMenuBar::ВосстановлениеOriginalstate

Вызывается по системе, когда пользователь выбирает **сбросить** из окна **настраиваемый** диалог.

```
virtual BOOL RestoreOriginalstate();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод успешен; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод вызывается, когда пользователь выбирает **спуск** из меню настройки. Вы также можете вручную вызвать этот метод, чтобы программно сбросить состояние панели меню. Этот метод загружает исходное состояние из файла ресурса.

Переопределить этот метод, если вы хотите сделать любую обработку, когда пользователь выбирает опцию **сбросить.**

## <a name="cmfcmenubarsavestate"></a><a name="savestate"></a>CMFCMenuBar::SaveState

Сохраняет состояние объекта [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) в реестре Windows.

```
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Строка, содержащая путь ключа реестра Windows.

*Nindex*<br/>
(в) Идентификатор управления для панели меню.

*uiID*<br/>
(в) Зарезервированное значение.

### <a name="return-value"></a>Возвращаемое значение

TRUE в случае успеха; в противном случае FALSE;

### <a name="remarks"></a>Примечания

Как правило, приложение `SaveState`не вызывает . Рамочная система вызывает этот метод при сериализации рабочего пространства. Для получения дополнительной информации [см. CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).

Сохраненная информация включает в себя пункты меню, состояние док-станции и положение бара меню.

## <a name="cmfcmenubarsetdefaultmenuresid"></a><a name="setdefaultmenuresid"></a>CMFCMenuBar::SetDefaultMenuResId

Устанавливает меню по умолчанию для объекта [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) на основе идентификатора ресурса.

```cpp
void SetDefaultMenuResId(UINT uiResId);
```

### <a name="parameters"></a>Параметры

*uiResId*<br/>
(в) Идентификатор ресурса для нового меню по умолчанию.

### <a name="remarks"></a>Примечания

[Метод CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate) восстанавливает меню по умолчанию из файла ресурса.

Используйте метод [CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid) для получения меню по умолчанию без его восстановления.

## <a name="cmfcmenubarsetforcedownarrows"></a><a name="setforcedownarrows"></a>CMFCMenuBar::SetForceDownСтрелы

```cpp
void SetForceDownArrows(BOOL bValue);
```

### <a name="parameters"></a>Параметры

(в) *bValue*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcmenubarsetmaximizemode"></a><a name="setmaximizemode"></a>CMFCMenuBar::SetMaximizeMode

Рамочная система вызывает этот метод, когда MDI меняет режим отображения, и панель меню должна быть обновлена.

```cpp
void SetMaximizeMode(
    BOOL bMax,
    CWnd* pWnd = NULL,
    BOOL bRecalcLayout = TRUE);
```

### <a name="parameters"></a>Параметры

*bMax*<br/>
(в) Булеан, который определяет режим. Дополнительные сведения см. в разделе «Примечания».

*pWnd*<br/>
(в) Указатель на окно ребенка MDI, которое меняется.

*bRecalcLayout*<br/>
(в) Boolean, который определяет, следует ли немедленно пересчитывать макет меню бара.

### <a name="remarks"></a>Примечания

При максимальном подключении окна mDI ребенка панель меню, прикрепленная к окну основной рамы MDI, отображает меню системы и кнопки **«Минимизация»,** **«Максимизируйте»** и **«Закройте».** Если *bMax* является правдой и *pWnd* не является NULL, окно mDI ребенка максимизируется и меню бар должен включать дополнительные элементы управления. В противном случае панель меню возвращается в обычное состояние.

## <a name="cmfcmenubarsetmenubuttonrtc"></a><a name="setmenubuttonrtc"></a>CMFCMenuBar::SetMenuButtonRTC

Устанавливает информацию о классе времени выполнения, которую используется фреймворк при создаете кнопки меню.

```cpp
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```

### <a name="parameters"></a>Параметры

*pMenuButtonRTC*<br/>
(в) Информация [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) для класса, полученного из [класса CMFCMenuButton.](../../mfc/reference/cmfcmenubutton-class.md)

### <a name="remarks"></a>Примечания

Когда пользователь добавляет новые кнопки в панель меню, фреймворк динамически создает кнопки. По умолчанию `CMFCMenuButton` он создает объекты. Переопределить этот метод, чтобы изменить тип объектов кнопки, которые создает платформа.

## <a name="cmfcmenubarsetmenufont"></a><a name="setmenufont"></a>CMFCMenuBar::SetMenuFont

Устанавливает шрифт для всех баров меню в приложении.

```
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Параметры

*lpLogFont*<br/>
(в) Указатель на структуру [LOGFONT,](/windows/win32/api/dimm/ns-dimm-logfonta) определяющую набор шрифта.

*bHorz*<br/>
(в) ПРАВДА, если вы хотите, чтобы параметр *lpLogFont* использовался для вертикального шрифта, FALSE, если вы хотите, чтобы он использовался для горизонтального шрифта.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод был успешным; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Для всех `CMFCMenuBar` объектов используются два шрифта. Эти отдельные шрифты используются для горизонтальных и вертикальных баров меню.

Настройки шрифта являются глобальными `CMFCMenuBar` переменными и влияют на все объекты.

## <a name="cmfcmenubarsetrecentlyusedmenus"></a><a name="setrecentlyusedmenus"></a>CMFCMenuBar::SetRecentlyUsedMenus

Контролирует, отображает ли панель меню недавно используемые команды меню.

```
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```

### <a name="parameters"></a>Параметры

*Бон*<br/>
(в) Boolean, который контролирует, отображаются ли недавно используемые команды меню.

## <a name="cmfcmenubarsetshowallcommands"></a><a name="setshowallcommands"></a>CMFCMenuBar::SetShowAllCommands

Контролирует, отображает ли меню все доступные команды.

```
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```

### <a name="parameters"></a>Параметры

*bShowAllCommands*<br/>
(в) Параметр Boolean, который определяет, отображает ли всплывающее меню все команды меню.

### <a name="remarks"></a>Примечания

Если в меню не отображаются все команды меню, оно скрывает команды, которые используются редко. Для получения дополнительной информации об [CMFCMenuBar Class](../../mfc/reference/cmfcmenubar-class.md)отображении команд меню см.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
