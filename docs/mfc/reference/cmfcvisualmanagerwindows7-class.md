---
title: Класс CMFCVisualManagerWindows7
ms.date: 03/27/2019
f1_keywords:
- CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::OnFillMenuImageRect
helpviewer_keywords:
- CMFCVisualManagerWindows7 Class [MFC]
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
ms.openlocfilehash: 6686afecc2b8ef97ea24ef45ff5225433677a954
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319837"
---
# <a name="cmfcvisualmanagerwindows7-class"></a>Класс CMFCVisualManagerWindows7

Приложение `CMFCVisualManagerWindows7` создает внешний вид приложения Windows 7.

## <a name="syntax"></a>Синтаксис

```
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCVisualManagerWindows7:CMFCVisualManagerWindows7](#cmfcvisualmanagerwindows7)|Конструктор по умолчанию.|
|[CMFCVisualManagerWindows7: :-CMFCVisualManagerWindows7](#_dtorcmfcvisualmanagerwindows7)|Деструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCVisualManagerWindows7::CleanStyle`|Очищает текущий визуальный стиль и сбрасывает визуальный стиль по умолчанию.|
|`CMFCVisualManagerWindows7::CleanUp`|Очищает все объекты в пользовательском интерфейсе и сбрасывает меню.|
|`CMFCVisualManagerWindows7::DrawNcBtn`|Рисует кнопку в области неклиента на кадре. Рамка использует этот метод, чтобы свести к минимуму, максимизировать, закрыть и восстановить кнопки в верхнем правом углу оконной рамы. Этот метод вызывается только тогда, когда программа использует `Aero` тему.|
|`CMFCVisualManagerWindows7::DrawNcText`|Рисует текст в области неклиента на кадре. Платформа использует этот метод для рисования заголовка приложения в заголовке бара в верхней части окна кадра.|
|`CMFCVisualManagerWindows7::DrawSeparator`|Рисует сепаратор на [классе CMFCToolBar.](../../mfc/reference/cmfctoolbar-class.md)|
|`CMFCVisualManagerWindows7::GetRibbonBar`|Извлекает [класс CMFCRibbonBar,](../../mfc/reference/cmfcribbonbar-class.md) связанный с пользовательским интерфейсом.|
|[CMFCVisualManagerWindows7:GetRibbonEditBackgroundColor](#getribboneditbackgroundcolor)|Получает Лента отодвинет фонового цвета коробки.|
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|Переопределяет [CMFCVisualManager::GetRibbonPopupBorderSize](../../mfc/reference/cmfcvisualmanager-class.md#getribbonpopupbordersize)|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|Переопределяет [CMFCVisualManager::GetRibbonКвиКвИКВАйтТулБарХеверстом](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarchevronoffset)|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|Переопределяет [CMFCVisualManager::GetRibbonКвиКвИКВАйтТулПравоМаргл](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarrightmargin)|
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|Переопределяет [CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ishighlightwholemenuitem)|
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|Переопределяет [CMFCVisualManager::IsOwnerdrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#isownerdrawmenucheck)|
|`CMFCVisualManagerWindows7::IsRibbonPresent`|Определяет, `CMFCRibbonBar` присутствует ли и виден a.|
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|Переопределяет [CMFCVisualManagerWindows::OndrawbuttonBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawbuttonborder)|
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|Переопределяет [CMFCVisualManagerWindows::OndrawCheckBoxex](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcheckboxex)|
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|Переопределяет [CMFCVisualManagerWindows::OndrawComboDropButton](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcombodropbutton)|
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|Переопределяет [CMFCVisualManager::OndrawDefaultRibbonImage](../../mfc/reference/cmfcvisualmanager-class.md#ondrawdefaultribbonimage)|
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|Переопределяет [CMFCVisualManagerWindows::OndrawMenuBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawmenuborder)|
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|Переопределяет [CMFCVisualManager::OndrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck)|
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|Переопределяет [CMFCVisualManager::OndrawMenulabel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenulabel)|
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|Переопределяет метод `CMFCVisualManager::OnDrawRadioButton`.|
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|Переопределяет [CMFCVisualManager::OndrawRibbonApplicationButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonapplicationbutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|Переопределяет [CMFCVisualManager::OndrawRibbonButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonbuttonborder)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|Переопределяет [CMFCVisualManager::OndrawribbonCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaption)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|Переопределяет [CMFCVisualManager::OndrawRibbonCaptionButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaptionbutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|Переопределяет [CMFCVisualManager::OndrawRibbonКатегория](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategory)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|Переопределяет [CMFCVisualManager::OndrawRibbonCategoryTab](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorytab)|
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|Переопределяет [CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbondefaultpanebutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|Переопределяет [CMFCVisualManager::OndrawRibbonGalleryButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbongallerybutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|Переопределяет метод `CMFCVisualManager::OnDrawRibbonLaunchButton`.|
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|Переопределяет [CMFCVisualManager::OndrawRibbonMenuCheckFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonmenucheckframe)|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|Переопределяет [CMFCVisualManager::OndrawRibbonPanel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanel)|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|Переопределяет [CMFCVisualManager::OndrawRibbonPanelCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanelcaption)|
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|Переопределяет [CMFCVisualManager::OndrawribbonProgressBar](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonprogressbar)|
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|Переопределяет [CMFCVisualManager::OndrawribbonRecentFilesFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonrecentfilesframe)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|Переопределяет [CMFCVisualManager::OnDrawRibbonSliderChannel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderchannel)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|Переопределяет [CMFCVisualManager::OnDrawRibbonSliderThumb](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderthumb)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|Переопределяет [CMFCVisualManager::OnDrawRibbonSliderЗомБаттон](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderzoombutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|Переопределяет [CMFCVisualManager::OnDrawRibbonStatusBarPane](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonstatusbarpane)|
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|Переопределяет [CMFCVisualManager::OnDrawRibbonTabsFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbontabsframe)|
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|Переопределяет [CMFCVisualManagerWindows::OndrawstatusbarSizeBox](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawstatusbarsizebox)|
|`CMFCVisualManagerWindows7::OnFillBarBackground`|Переопределяет [CMFCVisualManagerWindows::OnfillBarbackground](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbarbackground)|
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|Переопределяет [CMFCVisualManagerWindows::OnfillbuttonInterior](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbuttoninterior)|
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](#onfillmenuimagerect)|Рамочная система вызывает этот метод, когда он заполняет область вокруг изображений элемента меню.|
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|Переопределяет [CMFCVisualManager::OnfillRibbonButton](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonbutton)|
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|Переопределяет [CMFCVisualManager::OnfillRibbonКваAccessToolBarPopup](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonquickaccesstoolbarpopup)|
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|Переопределяет [CMFCVisualManagerWindows::OnhighlightMenuitem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onhighlightmenuitem)|
|`CMFCVisualManagerWindows7::OnNcActivate`|Переопределяет [CMFCVisualManager::OnNcActivate](../../mfc/reference/cmfcvisualmanager-class.md#onncactivate)|
|`CMFCVisualManagerWindows7::OnNcPaint`|Переопределяет [CMFCVisualManager::Onncpaint](../../mfc/reference/cmfcvisualmanager-class.md#onncpaint)|
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|Переопределяет [CMFCVisualManagerWindows::OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onupdatesystemcolors)|
|`CMFCVisualManagerWindows7::SetResourceHandle`|Устанавливает ручку ресурса, описывая атрибуты визуального менеджера.|
|`CMFCVisualManagerWindows7::SetStyle`|Устанавливает цветовую гамму графического интерфейса. `CMFCVisualManagerWindows7`|

## <a name="remarks"></a>Примечания

Используйте `CMFCVisualManagerWindows7` класс, чтобы изменить внешний вид приложения, чтобы имитировать приложение Windows 7 по умолчанию. Этот класс может оказаться недействительным, если приложение работает на версии Windows раньше, чем Windows 7. В этом сценарии приложение использует визуальный менеджер по умолчанию, определенный в [CMFCVisualManager.](../../mfc/reference/cmfcvisualmanager-class.md)

CMFCVisualManagerWindows7 наследует несколько методов как из [CMFCVisualManagerWindows класса](../../mfc/reference/cmfcvisualmanagerwindows-class.md) и `CMFCVisualManager` класса. Методы, перечисленные в предыдущем разделе, `CMFCVisualManagerWindows7` являются новыми для класса методами.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseВизуальныйМенеджер](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)

`CMFCVisualManagerWindows7`

## <a name="requirements"></a>Требования

**Заголовок:** afxvisualmanagerwindows7.h

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="_dtorcmfcvisualmanagerwindows7"></a>CMFCVisualManagerWindows7: :-CMFCVisualManagerWindows7

Деструктор по умолчанию.

```
virtual ~CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="cmfcvisualmanagerwindows7"></a>CMFCVisualManagerWindows7:CMFCVisualManagerWindows7

Конструктор по умолчанию.

```
CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7getribboneditbackgroundcolor"></a><a name="getribboneditbackgroundcolor"></a>CMFCVisualManagerWindows7:GetRibbonEditBackgroundColor

Получает фоновый цвет ленты отодвинет коробку.

```
virtual COLORREF GetRibbonEditBackgroundColor (
    CMFCRibbonRichEditCtrl* pEdit,
    BOOL bIsHighlighted,
    BOOL bIsPaneHighlighted,
    BOOL bIsDisabled);
```

### <a name="parameters"></a>Параметры

*Полред*<br/>
(в) Указатель на управление правкой. Это значение не может быть NULL.

*bIsHighlighted*<br/>
(ваут) Возвращает ли лента поле выделено.

*bIsPaneАулион*<br/>
(ваут) Возвращает TRUE, если лента панели, которая содержит *pEdit* выделен.

*bIsDisabled*<br/>
(ваут) Возвращает ли *pEdit* отключен.

### <a name="return-value"></a>Возвращаемое значение

Фоновый цвет коробки для отсечения *pEdit*.

### <a name="remarks"></a>Примечания

## <a name="cmfcvisualmanagerwindows7onfillmenuimagerect"></a><a name="onfillmenuimagerect"></a>CMFCVisualManagerWindows7::OnFillMenuImageRect

Рамочная система вызывает этот метод, когда он заполняет область вокруг изображения элемента меню.

```
virtual void OnFillMenuImageRect(
    CDC* pDC,
    CMFCToolBarButton* pButton,
    CRect rectangle,
    CMFCVisualManager::AFX_BUTTON_STATE state);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства кнопки меню.

*pButton*<br/>
(в) Указатель на `CMFCToolBarButton`. Рамки заполняют фон для этой кнопки.

*Прямоугольник*<br/>
(в) Прямоугольник, который определяет границы области изображения кнопки меню.

*Государства*<br/>
(в) Состояние кнопки.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[CmFCVisualManagerWindows Класс](../../mfc/reference/cmfcvisualmanagerwindows-class.md)
