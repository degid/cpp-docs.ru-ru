---
title: Класс CMFCRibbonMiniToolBar
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
helpviewer_keywords:
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
ms.openlocfilehash: 5e5ac6c923640b7584d89a9c6f75d941deadddf3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754077"
---
# <a name="cmfcribbonminitoolbar-class"></a>Класс CMFCRibbonMiniToolBar

Реализует контекстно-зависимую панель инструментов контекстного меню.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Конструктор по умолчанию.|
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCRibbonMiniToolBar::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(Переопределяет `CMFCPopupMenu::IsRibbonMiniToolBar`.)|
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|Задает список команд, отображаемых на панели инструментов.|
|[CMFCRibbonMiniToolBar::Show](#show)|Отображает мини-панель инструментов по указанным координатам экрана.|
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|Отображает мини-панель инструментов вместе с контекстным меню.|

## <a name="remarks"></a>Примечания

Мини-панель инструментов обычно отображается, когда пользователь выделяет объект в документе. Например, после выделения блока текста в текстовом редакторе отображается мини-панель инструментов с командами форматирования текста.

Когда указатель мыши выходит за пределы мини-панели инструментов, она становится прозрачной.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

`CMFCRibbonPanelMenu`

[CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRibbonMiniToolBar.h

## <a name="cmfcribbonminitoolbarsetcommands"></a><a name="setcommands"></a>CMFCRibbonMiniToolBar::SetCommands

Задает список команд, отображаемых на панели инструментов.

```cpp
void SetCommands(
    CMFCRibbonBar* pRibbonBar,
    const CList<UINT,UINT>& lstCommands);
```

### <a name="parameters"></a>Параметры

*pRibbonBar*<br/>
(в) Лента бар, что мини панели инструментов ищет кнопки для отображения.

*lstCommands*<br/>
(в) Список команд, которые будут отображаться на панели инструментов мини. Все категории лент ы ищут, чтобы найти связанные кнопки.

### <a name="remarks"></a>Примечания

Используйте эту функцию, чтобы установить список команд, которые будут отображаться в панели мини-инструментов.

### <a name="example"></a>Пример

В следующем примере показано, `SetCommands` как `CMFCRibbonMiniToolBar` использовать метод класса. Этот фрагмент кода является частью [образца MS Office 2007 Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]

## <a name="cmfcribbonminitoolbarshow"></a><a name="show"></a>CMFCRibbonMiniToolБар::Шоу

Отображает мини-панель инструментов по указанным координатам экрана.

```
BOOL Show(
    int x,
    int y);
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Определяет горизонтальное положение панели мини-инструментов в координатах экрана.

*Y*<br/>
(в) Определяет вертикальное положение панели мини-инструментов в координатах экрана.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если мини-панель инструментов была показана успешно; в противном случае, FALSE.

## <a name="cmfcribbonminitoolbarshowwithcontextmenu"></a><a name="showwithcontextmenu"></a>CMFCRibbonMinitoolБар:ShowWithContextMenu

Отображает мини-панель инструментов вместе с контекстным меню.

```
BOOL ShowWithContextMenu(
    int x,
    int y,
    UINT uiMenuResID,
    CWnd* pWndOwner);
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Определяет горизонтальное положение контекстного меню в координатах экрана.

*Y*<br/>
(в) Определяет вертикальное положение контекстного меню в координатах экрана.

*uiMenuResID*<br/>
(в) Уотек идентификатора ресурсов контекстного меню для отображения.

*pWndВладелец*<br/>
(в) Определяет окно, которое получает сообщения из контекстного меню.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если контекстное меню было отображено успешно; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Используйте эту функцию для отображения мини-панели инструментов с контекстным меню. Контекстное меню расположено на 15 пикселей ниже панели мини-инструментов.

## <a name="cmfcribbonminitoolbariscontextmenumode"></a><a name="iscontextmenumode"></a>CMFCRibbonMinitoolБар::IsContextMenuMode

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
BOOL IsContextMenuMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonminitoolbarisribbonminitoolbar"></a><a name="isribbonminitoolbar"></a>CMFCRibbonMinitoolБар::IsRibbonMinitoolБар

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual BOOL IsRibbonMiniToolBar() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
