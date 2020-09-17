---
title: Класс CMFCDropDownToolBar
ms.date: 11/19/2018
f1_keywords:
- CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::AllowShowOnPaneMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadBitmap
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnLButtonUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnMouseMove
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnSendCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnUpdateCmdUI
helpviewer_keywords:
- CMFCDropDownToolBar [MFC], AllowShowOnPaneMenu
- CMFCDropDownToolBar [MFC], LoadBitmap
- CMFCDropDownToolBar [MFC], LoadToolBar
- CMFCDropDownToolBar [MFC], OnLButtonUp
- CMFCDropDownToolBar [MFC], OnMouseMove
- CMFCDropDownToolBar [MFC], OnSendCommand
- CMFCDropDownToolBar [MFC], OnUpdateCmdUI
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
ms.openlocfilehash: 68dd976471b39d7f50c2f0378b2fce99ad3feeca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367600"
---
# <a name="cmfcdropdowntoolbar-class"></a>Класс CMFCDropDownToolBar

Панель инструментов, которая появляется, когда пользователь нажимает и удерживает кнопку верхнего уровня панели инструментов.

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCDropDownToolBar : public CMFCToolBar
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Переопределяет `CPane::AllowShowOnPaneMenu`.)|
|[CMFCDropDownToolBar::LoadBitmap](#loadbitmap)|(Переопределяет [CMFCToolBar::LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap).)|
|[CMFCDropDownToolBar::LoadToolBar](#loadtoolbar)|(Переопределяет [CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar).)|
|[CMFCDropDowntoolbar::OnLButtonup](#onlbuttonup)||
|[CMFCDropDownToolbar::OnMouseMove](#onmousemove)||
|[CMFCDropDownToolbar::OnsendCommand](#onsendcommand)|(Переопределяет `CMFCToolBar::OnSendCommand`.)|
|[CMFCDropDownToolBar::OnUpdateCmdUI](#onupdatecmdui)|(Переопределяет [CMFCToolBar::OnUpdateCmdUI](cmfctoolbar-class.md).|

### <a name="remarks"></a>Примечания

Объект `CMFCDropDownToolBar` сочетает в себе внешний вид панели инструментов с поведением всплывающего меню. Когда пользователь нажимает и удерживает кнопку панели инструментов (см. [CMFCDropDownToolbarButton Class),](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)появляется панель инструментов, и пользователь может выбрать кнопку из панели инструментов, выпадающих вниз, прокрутив ее и выпустив кнопку мыши. После того, как пользователь выбирает кнопку в панели инструментов, выпадающих вниз, эта кнопка отображается в качестве текущей кнопки на панели инструментов верхнего уровня.

Панель инструментов выпадения не может быть настроена или пристыкована, и она не имеет состояния отрыва.

На следующей `CMFCDropDownToolBar` иллюстрации показан объект:

![Пример CMFCDropDownToolbar](../../mfc/reference/media/cmfcdropdown.png "Пример CMFCDropDownToolbar")

Вы создаете `CMFCDropDownToolBar` объект так же, как вы создаете обычную панель инструментов (см. [CMFCToolBar class).](../../mfc/reference/cmfctoolbar-class.md)

Чтобы вставить панель инструментов для выпадения в родительскую панель инструментов:

1. Зарезервируйте идентификатор ресурсов для кнопки в родительском ресурсе панели инструментов.

2. Создайте `CMFCDropDownToolBarButton` объект, содержащий панель инструментов для выпадения (для получения дополнительной информации см. [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton).](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)

3. Замените кнопку манекена с объектом `CMFCDropDownToolBarButton` с помощью [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

Для получения дополнительной информации о кнопках панели инструментов, [см.](../../mfc/walkthrough-putting-controls-on-toolbars.md) Например, панель инструментов для выпадающих средств см.

## <a name="example"></a>Пример

В следующем примере показано, `Create` как `CMFCDropDownToolBar` использовать метод в классе. Этот фрагмент кода является частью [образца демонстрации Visual Studio.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxdropdowntoolbar.h

## <a name="cmfcdropdowntoolbarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFCDropDownToolBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcdropdowntoolbarloadbitmap"></a><a name="loadbitmap"></a>CMFCDropDownToolBar::LoadBitmap

Загружает изображения значков панели инструментов из ресурсов приложения.

```
virtual BOOL LoadBitmap(
    UINT uiResID,
    UINT uiColdResID=0,
    UINT uiMenuResID=0,
    BOOL bLocked=FALSE,
    UINT uiDisabledResID=0,
    UINT uiMenuDisabledResID=0);
```

### <a name="parameters"></a>Параметры

*uiResID*<br/>
(в) Идентификатор ресурса битной карты, относящся к горячим изображениям панели инструментов.

*uiColdResID*<br/>
(в) Идентификатор ресурса битной карты, относящся к изображениям холодной панели инструментов.

*uiMenuResID*<br/>
(в) Идентификатор ресурса битной карты, отсылаемый к обычным изображениям меню.

*Заблокирован*<br/>
(в) TRUE для блокировки панели инструментов; в противном случае FALSE.

*uiDisabledResID*<br/>
(в) Идентификатор ресурса битной карты, отсылаемый к изображениям панели инструментов с ограниченными возможностями.

*uiMenuDisabledResID*<br/>
(в) Идентификатор ресурса битной карты, отсылаемый к изображениям отключенного меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод выполнен успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Метод [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) вызывает этот метод, чтобы загрузить изображения, связанные с панелью инструментов. Переопределите этот метод для выполнения пользовательской загрузки графических ресурсов.

Вызовите метод `LoadBitmapEx` , чтобы загрузить дополнительные изображения после создания панели инструментов.

## <a name="cmfcdropdowntoolbarloadtoolbar"></a><a name="loadtoolbar"></a>CMFCDropDownToolBar::LoadToolBar

```
virtual BOOL LoadToolBar(
    UINT uiResID,
    UINT uiColdResID = 0,
    UINT uiMenuResID = 0,
    BOOL = FALSE,
    UINT uiDisabledResID = 0,
    UINT uiMenuDisabledResID = 0,
    UINT uiHotResID = 0);
```

### <a name="parameters"></a>Параметры

(в) *uiResID*<br/>

(в) *uiColdResID*<br/>

(в) *uiMenuResID*<br/>

(в) *БУЛ*<br/>

(в) *uiDisabledResID*<br/>

(в) *uiMenuDisabledResID*<br/>

(в) *uiHotResID*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcdropdowntoolbaronlbuttonup"></a><a name="onlbuttonup"></a>CMFCDropDowntoolbar::OnLButtonup

```
afx_msg void OnLButtonUp(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Параметры

(в) *nФлаги*<br/>

(в) *точки*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcdropdowntoolbaronmousemove"></a><a name="onmousemove"></a>CMFCDropDownToolbar::OnMouseMove

```
afx_msg void OnMouseMove(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Параметры

(в) *nФлаги*<br/>

(в) *точки*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcdropdowntoolbaronsendcommand"></a><a name="onsendcommand"></a>CMFCDropDownToolbar::OnsendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Параметры

(в) *pButton*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcdropdowntoolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCDropDownToolBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Параметры

(в) *pTarget*<br/>

(в) *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBar::Создание](../../mfc/reference/cmfctoolbar-class.md#create)<br/>
[CMFCToolBar::Заменить кнопку](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[CmFCDropDownToolbarButton класс](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)<br/>
[Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)
