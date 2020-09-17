---
title: Класс CMFCPopupMenuBar
ms.date: 11/04/2016
f1_keywords:
- CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::AdjustSizeImmediate
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::BuildOrigItems
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::CloseDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ExportToMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::FindDestintationToolBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetCurrentMenuImageSize
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetDefaultMenuId
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetLastCommandIndex
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ImportFromMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsDropDownListMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsPaletteMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanel
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanelInRegularMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::LoadFromHash
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::RestoreDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetButtonStyle
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::StartPopupMenuTimer
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::m_bDisableSideBarInXPMode
helpviewer_keywords:
- CMFCPopupMenuBar [MFC], AdjustSizeImmediate
- CMFCPopupMenuBar [MFC], BuildOrigItems
- CMFCPopupMenuBar [MFC], CloseDelayedSubMenu
- CMFCPopupMenuBar [MFC], ExportToMenu
- CMFCPopupMenuBar [MFC], FindDestintationToolBar
- CMFCPopupMenuBar [MFC], GetCurrentMenuImageSize
- CMFCPopupMenuBar [MFC], GetDefaultMenuId
- CMFCPopupMenuBar [MFC], GetLastCommandIndex
- CMFCPopupMenuBar [MFC], GetOffset
- CMFCPopupMenuBar [MFC], ImportFromMenu
- CMFCPopupMenuBar [MFC], IsDropDownListMode
- CMFCPopupMenuBar [MFC], IsPaletteMode
- CMFCPopupMenuBar [MFC], IsRibbonPanel
- CMFCPopupMenuBar [MFC], IsRibbonPanelInRegularMode
- CMFCPopupMenuBar [MFC], LoadFromHash
- CMFCPopupMenuBar [MFC], RestoreDelayedSubMenu
- CMFCPopupMenuBar [MFC], SetButtonStyle
- CMFCPopupMenuBar [MFC], SetOffset
- CMFCPopupMenuBar [MFC], StartPopupMenuTimer
- CMFCPopupMenuBar [MFC], m_bDisableSideBarInXPMode
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
ms.openlocfilehash: c0ba90246d19e8dd07c856eec6a518a8513ee665
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751917"
---
# <a name="cmfcpopupmenubar-class"></a>Класс CMFCPopupMenuBar

Строка меню, внедренная в контекстное меню.

## <a name="syntax"></a>Синтаксис

```
class CMFCPopupMenuBar : public CMFCToolBar
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|Немедленно пересчитывает расположение панели. (Переопределяет [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|Загружает всплывающие элементы меню из заданного ресурса меню.|
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|Закрывает кнопку отложенного всплывающих меню.|
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|Создает меню из кнопок всплывающих меню.|
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|Находит панель инструментов, в которой находится указанная точка.|
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Указывает размер изображений с кнопкой меню.|
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|Возвращает идентификатор элемента меню по умолчанию.|
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|Получает индекс последней вызываемых команд меню.|
|[CMFCPopupMenuBar::GetOffset](#getoffset)|Получает смещение строки панели всплывающих меню.|
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|Импортирует кнопки всплывающих меню из указанного меню.|
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|Указывает, находится ли всплывающее меню в режиме выпадающего списка.|
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|Указывает, находится ли всплывающий панель меню в режиме палитры.|
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|Указывает, является ли это ленточной панелью (FALSE по умолчанию).|
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|Указывает, является ли это ленточной панелью в обычном режиме (FALSE по умолчанию).|
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|Загружает архивное меню.|
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|Восстанавливает кнопку отложенного меню для закрытия панели всплывающих меню.|
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|Устанавливает стиль кнопки панели инструментов в данном индексе. (Переопределяет [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)|
|[CMFCPopupMenuBar::SetOffset](#setoffset)|Устанавливает смещение строки панели всплывающих меню.|
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|Запускает таймер для указанной кнопки запоздалого всплывающих меню.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Уточняется, будет ли серая боковая панель отображаться при появлении приложения Windows XP.|

## <a name="remarks"></a>Примечания

Создается `CMFCPopupMenuBar` одновременно с [классом CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) и встроен внутри него. Охватывает `CMFCPopupMenuBar` всю клиентскую область `CMFCPopupMenu` объекта. Он поддерживает клавиатуру и мышь ввода. Он также сообщает, что `CMFCPopupMenu` вход в и верхнего уровня окна кадра.

## <a name="example"></a>Пример

В следующем примере показано, `CMFCPopupMenuBar` как инициализировать объект из `CMFCPopupMenu` объекта. Этот фрагмент кода входит в состав [примера Draw Client](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpopupmenubar.h

## <a name="cmfcpopupmenubaradjustsizeimmediate"></a><a name="adjustsizeimmediate"></a>CMFCPopupMenuBar::AdjustSizeImmediate

Немедленно пересчитывает макет панели меню popup. (Перекрывает [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).

```
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```

### <a name="parameters"></a>Параметры

*bRecalcLayout*<br/>
(в) TRUE для автоматического пересчета макета панели меню popup; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarbuildorigitems"></a><a name="buildorigitems"></a>CMFCPopupMenuBar::BuildOrigItems

Загружает всплывающие элементы меню из заданного ресурса меню.

```
BOOL BuildOrigItems(UINT uiMenuResID);
```

### <a name="parameters"></a>Параметры

*uiMenuResID*<br/>
(в) Упоняет идентификатор меню ресурса меню для загрузки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ПРАВДА, если успешно или FALSE, если нет.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarclosedelayedsubmenu"></a><a name="closedelayedsubmenu"></a>CMFCPopupMenuBar::CloseDelayedSubMenu

Закрывает кнопку всплывающее меню, которая была отложена.

```
virtual void CloseDelayedSubMenu();
```

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarexporttomenu"></a><a name="exporttomenu"></a>CMFCPopupMenuBar::ExportToMenu

Создает меню из кнопок всплывающих меню.

```
virtual HMENU ExportToMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку в новое меню.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarfinddestintationtoolbar"></a><a name="finddestintationtoolbar"></a>CMFCPopupMenuBar::FindDestintationToolBar

Находит панель инструментов, в которой находится указанная точка.

```
CMFCToolBar* FindDestintationToolBar(CPoint point);
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
(в) Точка на экране.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку на панель инструментов, где находится точка, если она есть, или NULL, если нет.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubargetcurrentmenuimagesize"></a><a name="getcurrentmenuimagesize"></a>CMFCPopupMenuBar::GetCurrentMenuImage

Указывает размер изображений с кнопкой меню.

```
virtual CSize GetCurrentMenuImageSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает размер изображений с кнопкой меню в панели инструментов.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubargetdefaultmenuid"></a><a name="getdefaultmenuid"></a>CMFCPopupMenuBar::GetDefaultMenuId

Возвращает идентификатор элемента меню по умолчанию.

```
UINT GetDefaultMenuId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает идентификатор элемента меню по умолчанию в панели меню всплывающих.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubargetlastcommandindex"></a><a name="getlastcommandindex"></a>CMFCPopupMenuBar::GetLastCommandIndex

Получает индекс последней вызываемых команд меню.

```
static int __stdcall GetLastCommandIndex();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает индекс последней вызываемый команды меню.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubargetoffset"></a><a name="getoffset"></a>CMFCPopupMenuBar::GetOffset

Получает смещение строки панели всплывающих меню.

```
int GetOffset() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает смещение строки панели всплывающих меню.

### <a name="remarks"></a>Примечания

Это значение устанавливается с помощью [CMFCPopupMenuBar::SetOffset](#setoffset).

## <a name="cmfcpopupmenubarimportfrommenu"></a><a name="importfrommenu"></a>CMFCPopupMenuBar::ИмпортFromMenu

Импортирует кнопки всплывающих меню из указанного меню.

```
virtual BOOL ImportFromMenu(
    HMENU hMenu,
    BOOL bShowAllCommands = FALSE);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
(в) Меню, из которого импортировать всплывающие кнопки меню.

*bShowAllCommands*<br/>
(в) ПРАВДА, если все команды в меню должны быть импортированы, или FALSE, если редко используемые из них могут быть скрыты.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если кнопки меню были успешно импортированы из меню, или FALSE, если нет.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarisdropdownlistmode"></a><a name="isdropdownlistmode"></a>CMFCPopupMenuBar::IsDropDownListMode

Указывает, находится ли всплывающее меню в режиме выпадающего списка.

```
BOOL IsDropDownListMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если всплывающее меню бар находится в выпадающих вниз список режиме, или FALSE, если нет.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarispalettemode"></a><a name="ispalettemode"></a>CMFCPopupMenuBar::IsPaletteMode

Указывает, находится ли всплывающий панель меню в режиме палитры.

```
BOOL IsPaletteMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если режим палитры включен, или FALSE, если нет.

### <a name="remarks"></a>Примечания

Когда панель меню настроена на палитру, элементы меню отображаются в нескольких столбцах и ограниченном количестве строк.

## <a name="cmfcpopupmenubarisribbonpanel"></a><a name="isribbonpanel"></a>CMFCPopupMenuBar::IsRibbonPanel

Указывает, является ли это ленточной панелью (FALSE по умолчанию).

```
virtual BOOL IsRibbonPanel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает FALSE по умолчанию, указывая, что это не лента панели.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarisribbonpanelinregularmode"></a><a name="isribbonpanelinregularmode"></a>CMFCPopupMenuBar::IsribbonPanelInRegularMode

Указывает, является ли это ленточной панелью в обычном режиме (FALSE по умолчанию).

```
virtual BOOL IsRibbonPanelInRegularMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает FALSE по умолчанию, указывая, что это не лента панели в обычном режиме.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarloadfromhash"></a><a name="loadfromhash"></a>CMFCPopupMenuBar::LoadFromHash

Загружает архивное меню.

```
BOOL LoadFromHash(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
(в) Ручка в архивируемом меню для загрузки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если меню загружено успешно, или FALSE, если нет.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarm_bdisablesidebarinxpmode"></a><a name="m_bdisablesidebarinxpmode"></a>CMFCPopupMenuBar::m_bDisableSideBarInXPMode

Параметр Boolean, указывающий, имеет ли ваше приложение серую боковую панель, когда оно имеет внешний вид Windows XP.

```
BOOL m_bDisableSideBarInXPMode;
```

### <a name="remarks"></a>Примечания

Если эта переменная участника установлена на FALSE и ваше приложение имеет внешний вид Windows XP, фреймворк рисует серую боковую панель в приложении.

Значение по умолчанию — FALSE.

## <a name="cmfcpopupmenubarrestoredelayedsubmenu"></a><a name="restoredelayedsubmenu"></a>CMFCPopupMenuBar::RestoreDelayedSubMenu

Восстанавливает кнопку отложенного меню для закрытия панели всплывающих меню.

```
virtual void RestoreDelayedSubMenu();
```

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarsetbuttonstyle"></a><a name="setbuttonstyle"></a>CMFCPopupMenuBar::SetButtonStyle

Устанавливает стиль кнопки панели инструментов в данном индексе. (Переопределяет [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)

```
virtual void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Индекс на нулевой основе кнопки панели инструментов, стиль которой должен быть установлен.

*nStyle*<br/>
(в) Стиль кнопки. Ознакомиться со [стилами управления панелью инструментов](../../mfc/reference/toolbar-control-styles.md) можно найти в списках доступных стилей кнопок для панели инструментов.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarsetoffset"></a><a name="setoffset"></a>CMFCPopupMenuBar::SetOffset

Устанавливает смещение строки панели всплывающих меню.

```cpp
void SetOffset(int iOffset);
```

### <a name="parameters"></a>Параметры

*iOffset*<br/>
(в) Количество строк, которые должны быть компенсированы панелью всплывающих меню.

### <a name="remarks"></a>Примечания

## <a name="cmfcpopupmenubarstartpopupmenutimer"></a><a name="startpopupmenutimer"></a>CMFCPopupMenuBar::StartPopupMenur

Запускает таймер для указанной кнопки запоздалого всплывающих меню.

```cpp
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,
    int nDelayFactor = 1);
```

### <a name="parameters"></a>Параметры

*pMenuButton*<br/>
(в) Указатель на кнопку меню, для которой можно установить таймер задержки.

*nDelayFactor*<br/>
(в) Коэффициент задержки, равный по крайней мере одному, для умножения на стандартное время задержки меню (обычно между половиной секунды и пятью секундами).

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)<br/>
[Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)
