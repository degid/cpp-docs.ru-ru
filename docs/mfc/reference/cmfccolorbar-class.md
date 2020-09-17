---
title: Класс Кмфкколорбар
ms.date: 11/04/2016
f1_keywords:
- CMFCColorBar
- AFXCOLORBAR/CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::ContextToSize
- AFXCOLORBAR/CMFCColorBar::CreateControl
- AFXCOLORBAR/CMFCColorBar::Create
- AFXCOLORBAR/CMFCColorBar::EnableAutomaticButton
- AFXCOLORBAR/CMFCColorBar::EnableOtherButton
- AFXCOLORBAR/CMFCColorBar::GetColor
- AFXCOLORBAR/CMFCColorBar::GetCommandID
- AFXCOLORBAR/CMFCColorBar::GetHighlightedColor
- AFXCOLORBAR/CMFCColorBar::GetHorzMargin
- AFXCOLORBAR/CMFCColorBar::GetVertMargin
- AFXCOLORBAR/CMFCColorBar::IsTearOff
- AFXCOLORBAR/CMFCColorBar::SetColor
- AFXCOLORBAR/CMFCColorBar::SetColorName
- AFXCOLORBAR/CMFCColorBar::SetCommandID
- AFXCOLORBAR/CMFCColorBar::SetDocumentColors
- AFXCOLORBAR/CMFCColorBar::SetHorzMargin
- AFXCOLORBAR/CMFCColorBar::SetVertMargin
- AFXCOLORBAR/CMFCColorBar::AdjustLocations
- AFXCOLORBAR/CMFCColorBar::AllowChangeTextLabels
- AFXCOLORBAR/CMFCColorBar::AllowShowOnList
- AFXCOLORBAR/CMFCColorBar::CalcSize
- AFXCOLORBAR/CMFCColorBar::CreatePalette
- AFXCOLORBAR/CMFCColorBar::GetColorGridSize
- AFXCOLORBAR/CMFCColorBar::GetExtraHeight
- AFXCOLORBAR/CMFCColorBar::InitColors
- AFXCOLORBAR/CMFCColorBar::OnKey
- AFXCOLORBAR/CMFCColorBar::OnSendCommand
- AFXCOLORBAR/CMFCColorBar::OnUpdateCmdUI
- AFXCOLORBAR/CMFCColorBar::OpenColorDialog
- AFXCOLORBAR/CMFCColorBar::Rebuild
- AFXCOLORBAR/CMFCColorBar::SelectPalette
- AFXCOLORBAR/CMFCColorBar::SetPropList
- AFXCOLORBAR/CMFCColorBar::ShowCommandMessageString
helpviewer_keywords:
- CMFCColorBar [MFC], CMFCColorBar
- CMFCColorBar [MFC], ContextToSize
- CMFCColorBar [MFC], CreateControl
- CMFCColorBar [MFC], Create
- CMFCColorBar [MFC], EnableAutomaticButton
- CMFCColorBar [MFC], EnableOtherButton
- CMFCColorBar [MFC], GetColor
- CMFCColorBar [MFC], GetCommandID
- CMFCColorBar [MFC], GetHighlightedColor
- CMFCColorBar [MFC], GetHorzMargin
- CMFCColorBar [MFC], GetVertMargin
- CMFCColorBar [MFC], IsTearOff
- CMFCColorBar [MFC], SetColor
- CMFCColorBar [MFC], SetColorName
- CMFCColorBar [MFC], SetCommandID
- CMFCColorBar [MFC], SetDocumentColors
- CMFCColorBar [MFC], SetHorzMargin
- CMFCColorBar [MFC], SetVertMargin
- CMFCColorBar [MFC], AdjustLocations
- CMFCColorBar [MFC], AllowChangeTextLabels
- CMFCColorBar [MFC], AllowShowOnList
- CMFCColorBar [MFC], CalcSize
- CMFCColorBar [MFC], CreatePalette
- CMFCColorBar [MFC], GetColorGridSize
- CMFCColorBar [MFC], GetExtraHeight
- CMFCColorBar [MFC], InitColors
- CMFCColorBar [MFC], OnKey
- CMFCColorBar [MFC], OnSendCommand
- CMFCColorBar [MFC], OnUpdateCmdUI
- CMFCColorBar [MFC], OpenColorDialog
- CMFCColorBar [MFC], Rebuild
- CMFCColorBar [MFC], SelectPalette
- CMFCColorBar [MFC], SetPropList
- CMFCColorBar [MFC], ShowCommandMessageString
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
ms.openlocfilehash: ca28f8a07938e787fcf2d91d714c9dc82092194f
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561041"
---
# <a name="cmfccolorbar-class"></a>Класс Кмфкколорбар

`CMFCColorBar`Класс представляет закрепляемую панель управления, которая может выбирать цвета в документе или приложении.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorBar : public CMFCPopupMenuBar
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кмфкколорбар:: Кмфкколорбар](#cmfccolorbar)|Формирует объект `CMFCColorBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кмфкколорбар:: Контексттосизе](#contexttosize)|Вычисляет вертикальные и горизонтальные поля, необходимые для размещения кнопок в элементе управления "Цветовая шкала", а затем корректирует расположение этих кнопок.|
|[Кмфкколорбар:: CreateControl](#createcontrol)|Создает окно управления цветовой полосой, прикрепляет его к `CMFCColorBar` объекту и изменяет размер элемента управления, чтобы он содержал указанную палитру цветов.|
|[Кмфкколорбар:: Create](#create)|Создает окно управления цветовой полосой и прикрепляет его к `CMFCColorBar` объекту.|
|[Кмфкколорбар:: Енаблеаутоматикбуттон](#enableautomaticbutton)|Показывает или скрывает автоматическую кнопку.|
|[Кмфкколорбар:: Енаблеосербуттон](#enableotherbutton)|Включает или отключает отображение диалогового окна, позволяющего пользователю выбрать дополнительные цвета.|
|[Кмфкколорбар:: "Color"](#getcolor)|Извлекает выбранный в данный момент цвет.|
|[Кмфкколорбар:: Жеткоммандид](#getcommandid)|Получает идентификатор команды текущего элемента управления "Цветовая шкала".|
|[Кмфкколорбар:: Жесигхлигхтедколор](#gethighlightedcolor)|Извлекает цвет, обозначающий, что кнопка цвета имеет фокус. Это значит, что *кнопка активна.*|
|[Кмфкколорбар:: Жесорзмаргин](#gethorzmargin)|Извлекает горизонтальное поле, которое является пробелом между левой или правой ячейкой цвета и границей клиентской области.|
|[Кмфкколорбар:: Жетвертмаргин](#getvertmargin)|Извлекает вертикальное поле, которое является пространством между верхней или нижней ячейкой цвета и границей клиентской области.|
|[Кмфкколорбар:: Истеарофф](#istearoff)|Указывает, является ли текущая цветовая полоса закрепляемой.|
|[Кмфкколорбар:: Сетколор](#setcolor)|Задает цвет, выбранный в данный момент.|
|[Кмфкколорбар:: Сетколорнаме](#setcolorname)|Задает новое имя для указанного цвета.|
|[Кмфкколорбар:: Сеткоммандид](#setcommandid)|Задает новый идентификатор команды для элемента управления "Цветовая шкала".|
|[Кмфкколорбар:: Сетдокументколорс](#setdocumentcolors)|Задает список цветов, используемых в текущем документе.|
|[Кмфкколорбар:: Сесорзмаргин](#sethorzmargin)|Задает горизонтальное поле, которое является пробелом между левой или правой ячейкой цвета и границей клиентской области.|
|[Кмфкколорбар:: Сетвертмаргин](#setvertmargin)|Задает вертикальное поле, которое является пробелом между верхней или нижней ячейкой цвета и границей клиентской области.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[Кмфкколорбар:: Аджустлокатионс](#adjustlocations)|Настраивает положение кнопок цвета в элементе управления "Цветовая шкала".|
|[Кмфкколорбар:: Алловчанжетекстлабелс](#allowchangetextlabels)|Указывает, может ли измениться текстовая метка кнопок цвета.|
|[Кмфкколорбар:: Алловшовонлист](#allowshowonlist)|Указывает, может ли объект элемента управления "цветовая панель" отображаться в списке панелей инструментов в процессе настройки.|
|[Кмфкколорбар:: Калксизе](#calcsize)|Вызывается платформой как часть процесса вычисления макета.|
|[Кмфкколорбар:: Креатепалетте](#createpalette)|Инициализирует палитру с цветами в указанном массиве цветов.|
|[Кмфкколорбар:: Жетколоргридсизе](#getcolorgridsize)|Вычисляет количество строк и столбцов в сетке элемента управления "Цветовая шкала".|
|[Кмфкколорбар:: Жетекстрахеигхт](#getextraheight)|Вычисляет дополнительную высоту, которая требуется текущей цветовой шкале для вывода различных элементов пользовательского интерфейса, таких как **другая** кнопка, цвета документа и т. д.|
|[Кмфкколорбар:: Инитколорс](#initcolors)|Инициализирует массив цветов с цветами в указанной палитре или палитре системы по умолчанию.|
|[Кмфкколорбар:: Онкэй](#onkey)|Вызывается платформой при нажатии пользователем кнопки клавиатуры.|
|[Кмфкколорбар:: Онсендкомманд](#onsendcommand)|Вызывается платформой для закрытия иерархии элементов управления Popup.|
|[Кмфкколорбар:: Онупдатекмдуи](#onupdatecmdui)|Вызывается платформой для включения или отключения элемента пользовательского интерфейса элемента управления "Цветовая шкала" перед отображением элемента.|
|[Кмфкколорбар:: Опенколордиалог](#opencolordialog)|Открывает диалоговое окно "цвет".|
|[Кмфкколорбар:: Rebuild](#rebuild)|Полностью перерисовывает элемент управления "цветовая панель".|
|[Кмфкколорбар:: Селектпалетте](#selectpalette)|Устанавливает логическую палитру указанного контекста устройства в палитру родительской кнопки текущего элемента управления "Цветовая шкала".|
|[Кмфкколорбар:: Сетпроплист](#setproplist)|Устанавливает элемент `m_pWndPropList` защищенных данных в указанный указатель на элемент управления сетки свойств.|
|[Кмфкколорбар:: Шовкоммандмессажестринг](#showcommandmessagestring)|Запрашивает окно фрейма, которому принадлежит элемент управления "Цветовая шкала", для обновления строки сообщения в строке состояния.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|`m_bInternal`|Логическое поле, определяющее, обрабатываются ли события мыши. Как правило, события мыши обрабатываются, если это поле имеет значение TRUE, а режим настройки — FALSE.|
|`m_bIsEnabled`|Логическое значение, указывающее, включен ли элемент управления.|
|`m_bIsTearOff`|Логическое значение, указывающее, поддерживает ли элемент управления "цветовая панель" закрепление.|
|`m_BoxSize`|Объект [ксизе](../../atl-mfc-shared/reference/csize-class.md) , указывающий размер ячейки в сетке цветовой полосы.|
|`m_bShowDocColorsWhenDocked`|Логическое значение, указывающее, следует ли отображать цвета документа при закреплении цветовой панели. Дополнительные сведения см. в разделе [кмфкколорбар:: сетдокументколорс](#setdocumentcolors).|
|`m_bStdColorDlg`|Логическое значение, указывающее, следует ли отображать диалоговое окно стандартный системный цвет или диалоговое окно [кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md) . Дополнительные сведения см. в разделе [кмфкколорбар:: енаблеосербуттон](#enableotherbutton).|
|`m_ColorAutomatic`|Объект [COLORREF](/windows/win32/gdi/colorref) , в котором хранится текущий автоматический цвет. Дополнительные сведения см. в разделе [кмфкколорбар:: енаблеосербуттон](#enableotherbutton).|
|`m_ColorNames`|Объект [кмап](../../mfc/reference/cmap-class.md) , связывающий набор цветов RGB с их именами.|
|`m_colors`|[CArray](../../mfc/reference/carray-class.md) значений [COLORREF](/windows/win32/gdi/colorref) , которые содержат цвета, отображаемые в элементе управления "полоса цветов".|
|`m_ColorSelected`|Значение [COLORREF](/windows/win32/gdi/colorref) , которое является цветом, выбранным пользователем в элементе управления "полоса цветов".|
|`m_lstDocColors`|[CList](../../mfc/reference/clist-class.md) значений [COLORREF](/windows/win32/gdi/colorref) , которые содержат цвета, используемые в документе в данный момент.|
|`m_nCommandID`|Целое число без знака, которое является ИДЕНТИФИКАТОРом команды для кнопки цвета.|
|`m_nHorzMargin`|Целое число, которое является горизонтальным полем между кнопками цвета в сетке цветов.|
|`m_nHorzOffset`|Целое число, которое является горизонтальным смещением относительно центра кнопки цвета. Это значение является существенным, если в дополнение к цвету на кнопке отображается текст или изображение.|
|`m_nNumColumns`|Целое число, которое представляет собой количество столбцов в сетке цветов элемента управления "Цветовая шкала".|
|`m_nNumColumnsVert`|Целое число, которое является количеством столбцов в вертикально-ориентированной сетке цветов.|
|`m_nNumRowsHorz`|Целое число, которое является количеством столбцов в горизонтально-ориентированной сетке цветов.|
|`m_nRowHeight`|Целое число, которое является высотой строки цветовых кнопок в сетке цветов.|
|`m_nVertMargin`|Целое число, которое является вертикальным полем между кнопками цвета в сетке цветов.|
|`m_nVertOffset`|Целое число, которое является вертикальным смещением к центру кнопки цвета. Это значение является существенным, если в дополнение к цвету на кнопке отображается текст или изображение.|
|`m_Palette`|[Кпалетте](../../mfc/reference/cpalette-class.md) цветов, используемых в элементе управления "полоса цветов".|
|`m_pParentBtn`|Указатель на объект [кмфкколорбуттон](../../mfc/reference/cmfccolorbutton-class.md) , являющийся родительским по отношению к текущей кнопке. Это значение является существенным, если кнопка цвета находится в иерархии элементов управления панели инструментов или находится в элементе управления сеткой свойств цвета.|
|`m_pParentRibbonBtn`|Указатель на объект [кмфкриббонколорбуттон](../../mfc/reference/cmfcribboncolorbutton-class.md) , который находится на ленте и является родительской кнопкой текущей кнопки. Это значение является существенным, если кнопка цвета находится в иерархии элементов управления панели инструментов или находится в элементе управления сеткой свойств цвета.|
|`m_pWndPropList`|Указатель на объект [кмфкпропертигридктрл](../../mfc/reference/cmfcpropertygridctrl-class.md) .|
|`m_strAutoColor`|Значение [CString](../../atl-mfc-shared/reference/cstringt-class.md) , которое является текстом, отображаемым на кнопке **автоматически** . Дополнительные сведения см. в разделе [кмфкколорбар:: енаблеаутоматикбуттон](#enableautomaticbutton).|
|`m_strDocColors`|Значение [CString](../../atl-mfc-shared/reference/cstringt-class.md) , которое представляет собой текст, отображаемый на кнопке цвета документа. Дополнительные сведения см. в разделе [кмфкколорбар:: сетдокументколорс](#setdocumentcolors).|
|`m_strOtherColor`|Значение [CString](../../atl-mfc-shared/reference/cstringt-class.md) , которое является текстом, отображаемым на *другой* кнопке. Дополнительные сведения см. в разделе [кмфкколорбар:: енаблеосербуттон](#enableotherbutton).|

## <a name="remarks"></a>Примечания

Как правило, объект напрямую не создается `CMFCColorBar` . Вместо этого [класс кмфкколорменубуттон](../../mfc/reference/cmfccolormenubutton-class.md) (используемый в меню и панелях инструментов) или [класс кмфкколорбуттон](../../mfc/reference/cmfccolorbutton-class.md) создает `CMFCColorBar` объект.

`CMFCColorBar`Класс предоставляет следующие функциональные возможности:

- Автоматически корректирует список цветов документа.

- Сохраняет и восстанавливает свое состояние вместе с состоянием документа.

- Управляет кнопкой "автоматически".

- Использует элемент управления [класса кмфкколорпиккерктрл](../../mfc/reference/cmfccolorpickerctrl-class.md) для выбора пользовательского цвета.

- Поддерживает состояние "отрывного" (если оно создано с помощью [класса кмфкколорменубуттон](../../mfc/reference/cmfccolormenubutton-class.md)).

Чтобы внедрить `CMFCColorBar` функциональные возможности в приложение, выполните следующие действия.

1. Создайте обычную кнопку меню и назначьте ей идентификатор, например ID_CHAR_COLOR.

1. В классе окна фрейма Переопределите метод [CFrameWndEx:: оншовпопупмену](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) и замените кнопку обычного меню на объект [класса кмфкколорменубуттон](../../mfc/reference/cmfccolormenubutton-class.md) (путем вызова [CMFCToolBar:: реплацебуттон](../../mfc/reference/cmfctoolbar-class.md#replacebutton)).

1. Установите все стили и включите или отключите функции `CMFCColorBar` объекта во время создания [класса кмфкколорменубуттон](../../mfc/reference/cmfccolormenubutton-class.md) . `CMFCColorMenuButton`Объект динамически создает `CMFCColorBar` объект после того, как платформа вызывает `CreatePopupMenu` метод.

Когда пользователь нажимает кнопку элемента управления "Цветовая шкала", платформа использует `ON_COMMAND` макрос для уведомления родителя элемента управления "Цветовая шкала". В макросе параметр идентификатора команды — это значение, назначенное кнопке элемента управления "Цветовая шкала" на шаге 1 (ID_CHAR_COLOR в этом примере). Дополнительные сведения см. в статьях [класс кмфкколорменубуттон](../../mfc/reference/cmfccolormenubutton-class.md), [класс кмфкколорбуттон](../../mfc/reference/cmfccolorbutton-class.md), класс [кмфкколорпиккерктрл](../../mfc/reference/cmfccolorpickerctrl-class.md), класс [CFrameWndEx](../../mfc/reference/cframewndex-class.md)и классы классов [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md) .

## <a name="example"></a>Пример

В следующем примере показано, как настроить цветовую шкалу с помощью различных методов в `CMFCColorBar` классе. Методы задают горизонтальные и вертикальные поля, включают другую кнопку, создают окно управления цветовой полосой и задают выбранный в данный момент цвет. Этот пример является частью [примера новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[кмфкбасетулбар](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

[CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксколорбар.h

## <a name="cmfccolorbaradjustlocations"></a><a name="adjustlocations"></a> Кмфкколорбар:: Аджустлокатионс

Настраивает положение кнопок цвета в элементе управления "Цветовая шкала".

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой во время WM_SIZE обработки сообщения.

## <a name="cmfccolorbarallowchangetextlabels"></a><a name="allowchangetextlabels"></a> Кмфкколорбар:: Алловчанжетекстлабелс

Указывает, может ли измениться текстовая метка кнопок цвета.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда значение FALSE.

### <a name="remarks"></a>Примечания

По умолчанию этот метод всегда возвращает значение FALSE, означающее, что текстовые метки изменить нельзя. Переопределите этот метод, чтобы разрешить изменение текстовых меток.

## <a name="cmfccolorbarallowshowonlist"></a><a name="allowshowonlist"></a> Кмфкколорбар:: Алловшовонлист

Указывает, может ли объект элемента управления "цветовая панель" отображаться в списке панелей инструментов в процессе настройки.

```
virtual BOOL AllowShowOnList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда TRUE.

### <a name="remarks"></a>Примечания

По умолчанию этот метод всегда возвращает значение TRUE, что означает, что платформа может отображать элемент управления цветовой шкалой во время процесса настройки. Переопределите этот метод, чтобы реализовать другое поведение.

## <a name="cmfccolorbarcalcsize"></a><a name="calcsize"></a> Кмфкколорбар:: Калксизе

Вызывается платформой как часть процесса вычисления макета.

```
virtual CSize CalcSize(BOOL bVertDock);
```

### <a name="parameters"></a>Параметры

*бвертдокк*<br/>
окне Значение TRUE, чтобы указать, что элемент управления "цветовая панель" закреплен вертикально; Значение FALSE, чтобы указать, что элемент управления "цветовая панель" закреплен горизонтально.

### <a name="return-value"></a>Возвращаемое значение

Размер массива кнопок цвета в элементе управления "Цветовая шкала".

## <a name="cmfccolorbarcmfccolorbar"></a><a name="cmfccolorbar"></a> Кмфкколорбар:: Кмфкколорбар

Формирует объект `CMFCColorBar`.

```
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors,
    CList<COLORREF,COLORREF>& lstDocColors,
    int nColumns,
    int nRowsDockHorz,
    int nColDockVert,
    COLORREF colorAutomatic,
    UINT nCommandID,
    CMFCColorButton* pParentBtn);

CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors,
    CList<COLORREF,COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic,
    UINT nCommandID,
    CMFCRibbonColorButton* pParentRibbonBtn);

CMFCColorBar(
    CMFCColorBar& src,
    UINT uiCommandID);
```

### <a name="parameters"></a>Параметры

*красок*<br/>
окне Массив цветов, отображаемый платформой в элементе управления "полоса цветов".

*color*<br/>
окне Первоначально выбранный цвет.

*лпсзаутоколор*<br/>
окне Текстовая метка для кнопки цвета *автоматически* (по умолчанию) или null.

Стандартная метка для автоматической кнопки — **автоматически**.

*лпсзосерколор*<br/>
окне Текстовая метка *другой* кнопки, в которой отображаются дополнительные варианты выбора цвета или значение null.

Стандартная метка для другой кнопки — **Дополнительные цвета...**.

*лпсздокколорс*<br/>
окне Текстовая метка кнопки цвета документа. В палитре цвета документа перечислены все цвета, используемые в документе.

*лстдокколорс*<br/>
окне Список цветов, используемых в настоящий момент в документе.

*nColumns*<br/>
окне Число столбцов в массиве цветов.

*нровсдоккхорз*<br/>
окне Число строк, которое имеет цветовая шкала, когда она закреплена по горизонтали.

*нколдоккверт*<br/>
окне Число столбцов, которое имеет цветовую полосу, когда она закреплена по вертикали.

*колораутоматик*<br/>
окне Цвет по умолчанию, применяемый платформой при нажатии кнопки "автоматически".

*нкоммандид*<br/>
окне Идентификатор команды элемента управления "Цветовая шкала".

*ппарентбтн*<br/>
окне Указатель на родительскую кнопку.

*src*<br/>
окне Существующий `CMFCColorBar` объект, который будет скопирован в новый `CMFCColorBar` объект.

*уикоммандид*<br/>
окне Идентификатор команды.

## <a name="cmfccolorbarcontexttosize"></a><a name="contexttosize"></a> Кмфкколорбар:: Контексттосизе

Вычисляет вертикальные и горизонтальные поля, необходимые для размещения кнопок в элементе управления "Цветовая шкала", и корректирует положение этих кнопок.

```cpp
void ContextToSize(
    BOOL bSquareButtons = TRUE,
    BOOL bCenterButtons = TRUE);
```

### <a name="parameters"></a>Параметры

*бскуаребуттонс*\
окне Значение TRUE, чтобы указать, что форма кнопок в элементе управления "Цветовая шкала" является квадратной; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

*бцентербуттонс*\
окне Значение TRUE, чтобы указать, что содержимое на кнопке элемента управления "Цветовая шкала" выравнивается по центру; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorbarcreate"></a><a name="create"></a> Кмфкколорбар:: Create

Создает окно управления цветовой полосой и прикрепляет его к `CMFCColorBar` объекту.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle,
    UINT nID,
    CPalette* pPalette=NULL,
    int nColumns=0,
    int nRowsDockHorz=0,
    int nColDockVert=0);
```

### <a name="parameters"></a>Параметры

*ппарентвнд*<br/>
окне Указатель на родительское окно.

*двстиле*<br/>
окне Побитовое сочетание (или) [стилей окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*nID*<br/>
окне Идентификатор команды.

*ппалетте*<br/>
окне Указатель на палитру цветов. Значение по умолчанию — NULL.

*nColumns*<br/>
окне Число столбцов в элементе управления "полоса цветов". Значение по умолчанию равно 0.

*нровсдоккхорз*<br/>
окне Число строк в элементе управления "Цветовая шкала", когда оно закреплено по горизонтали. Значение по умолчанию равно 0.

*нколдоккверт*<br/>
окне Число столбцов в элементе управления "Цветовая шкала", когда оно закреплено по вертикали. Значение по умолчанию равно 0.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Чтобы создать `CMFCColorBar` объект, вызовите конструктор класса, а затем — этот метод. `Create`Метод создает элемент управления Windows и инициализирует список цветов.

## <a name="cmfccolorbarcreatecontrol"></a><a name="createcontrol"></a> Кмфкколорбар:: CreateControl

Создает окно управления цветовой полосой, прикрепляет его к `CMFCColorBar` объекту и изменяет размер окна элемента управления, чтобы оно содержало указанную палитру цветов.

```
virtual BOOL CreateControl(
    CWnd* pParentWnd,
    const CRect& rect,
    UINT nID,
    int nColumns=-1,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>Параметры

*ппарентвнд*<br/>
окне Указатель на родительское окно. Не может быть NULL.

*rect*<br/>
окне Ограничивающий прямоугольник, указывающий, где следует нарисовать элемент управления "цветовая полоса".

*nID*<br/>
окне Идентификатор элемента управления.

*nColumns*<br/>
окне Идеальное число столбцов в элементе управления "полоса цветов". Этот метод изменяет это число в соответствии с указанной палитрой цветов. Значение по умолчанию равно-1, что означает, что этот параметр не задан.

*ппалетте*<br/>
окне Указатель на палитру цветов или значение NULL. Если этот параметр имеет значение NULL, этот метод вычисляет размер элемента управления цветовой шкалы, как если бы было указано 20 цветов. Значение по умолчанию — NULL.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод завершился с ошибкой; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Этот метод использует параметры *Rect*, *нколумнс*и *ппалетте* для вычисления соответствующего числа, строк и столбцов в элементе управления "полоса цветов", а затем вызывает метод [кмфкколорбар:: Create](#create) .

## <a name="cmfccolorbarcreatepalette"></a><a name="createpalette"></a> Кмфкколорбар:: Креатепалетте

Инициализирует палитру с цветами в указанном массиве цветов.

```
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,
    CPalette& palette);
```

### <a name="parameters"></a>Параметры

*арколорс*\
окне Массив цветов.

*задания*\
окне Палитра цветов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

## <a name="cmfccolorbarenableautomaticbutton"></a><a name="enableautomaticbutton"></a> Кмфкколорбар:: Енаблеаутоматикбуттон

Показывает или скрывает автоматическую кнопку.

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*лпсзлабел*<br/>
окне Текстовая метка для кнопки цвета *автоматически* (по умолчанию) или null.

Стандартная метка для автоматической кнопки — **автоматически**.

*колораутоматик*<br/>
окне Цвет по умолчанию, применяемый платформой при нажатии кнопки "автоматически".

*bEnable*<br/>
окне Значение TRUE, чтобы включить автоматическую кнопку; Значение FALSE, чтобы отключить автоматическую кнопку. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Текстовая метка автоматической кнопки удаляется, если параметр *лпсзлабел* имеет значение null или параметр *бенабле* имеет значение false.

## <a name="cmfccolorbarenableotherbutton"></a><a name="enableotherbutton"></a> Кмфкколорбар:: Енаблеосербуттон

Включает или отключает отображение диалогового окна, позволяющего пользователю выбрать дополнительные цвета.

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*лпсзлабел*<br/>
окне Текстовая метка *другой* кнопки, в которой отображаются дополнительные варианты выбора цвета или значение null.

Стандартная метка для этой кнопки — **Дополнительные цвета...**

*балтколордлг*<br/>
окне Значение TRUE для вывода диалогового окна [кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md) ; Значение FALSE, чтобы отобразить стандартное диалоговое окно [кколордиалог](../../mfc/reference/ccolordialog-class.md) . Значение по умолчанию — TRUE.

*bEnable*<br/>
окне Значение TRUE, чтобы включить кнопку; Значение FALSE, чтобы отключить кнопку. Значение по умолчанию — TRUE.

## <a name="cmfccolorbargetcolor"></a><a name="getcolor"></a> Кмфкколорбар:: "Color"

Извлекает выбранный в данный момент цвет.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Выбранный в данный момент цвет.

## <a name="cmfccolorbargetcolorgridsize"></a><a name="getcolorgridsize"></a> Кмфкколорбар:: Жетколоргридсизе

Вычисляет количество строк и столбцов в сетке элемента управления "Цветовая шкала".

```
CSize GetColorGridSize(BOOL bVertDock) const;
```

### <a name="parameters"></a>Параметры

*бвертдокк*\
окне Значение TRUE, чтобы выполнить вычисление для элемента управления "полоса цветов", закрепленного по вертикали; в противном случае выполните вычисления для горизонтально закрепленного элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Объект [ксизе](../../atl-mfc-shared/reference/csize-class.md) , `cx` компонент которого содержит количество столбцов, а `cy` компонент компонента которого содержит количество строк.

## <a name="cmfccolorbargetcommandid"></a><a name="getcommandid"></a> Кмфкколорбар:: Жеткоммандид

Получает идентификатор команды текущего элемента управления "Цветовая шкала".

```
UINT GetCommandID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды.

### <a name="remarks"></a>Примечания

Когда пользователь выбирает новый цвет, платформа отправляет идентификатор команды в WM_COMMAND сообщение, чтобы уведомить родителя `CMFCColorBar` объекта.

## <a name="cmfccolorbargetextraheight"></a><a name="getextraheight"></a> Кмфкколорбар:: Жетекстрахеигхт

Вычисляет дополнительную высоту, которая требуется текущей цветовой шкале для вывода различных элементов пользовательского интерфейса, таких как **другие** цвета кнопки или документа.

```
int GetExtraHeight(int nNumColumns) const;
```

### <a name="parameters"></a>Параметры

*ннумколумнс*\
окне Если элемент управления "полоса цветов" содержит цвета документа, то число столбцов, отображаемых в сетке цветов документа. В противном случае это значение не используется.

### <a name="return-value"></a>Возвращаемое значение

Вычисляемая необходимая высота.

## <a name="cmfccolorbargethighlightedcolor"></a><a name="gethighlightedcolor"></a> Кмфкколорбар:: Жесигхлигхтедколор

Извлекает цвет, обозначающий, что кнопка цвета имеет фокус. Это значит, что *кнопка активна.*

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение RGB.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorbargethorzmargin"></a><a name="gethorzmargin"></a> Кмфкколорбар:: Жесорзмаргин

Извлекает горизонтальное поле, которое является пробелом между левой или правой ячейкой цвета и границей клиентской области.

```
int GetHorzMargin();
```

### <a name="return-value"></a>Возвращаемое значение

Горизонтальное поле.

## <a name="cmfccolorbargetvertmargin"></a><a name="getvertmargin"></a> Кмфкколорбар:: Жетвертмаргин

Извлекает вертикальное поле, которое является пространством между верхней или нижней ячейкой цвета и границей клиентской области.

```
int GetVertMargin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Вертикальное поле.

## <a name="cmfccolorbarinitcolors"></a><a name="initcolors"></a> Кмфкколорбар:: Инитколорс

Инициализирует массив цветов с цветами в указанной палитре или с системной палитрой по умолчанию.

```
static int InitColors(
    CPalette* pPalette,
    CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>Параметры

*ппалетте*\
окне Указатель на объект Palette или значение NULL. Если этот параметр имеет значение NULL, этот метод использует палитру по умолчанию операционной системы.

*арколорс*\
окне Массив цветов.

### <a name="return-value"></a>Возвращаемое значение

Число элементов в массиве цветов.

## <a name="cmfccolorbaristearoff"></a><a name="istearoff"></a> Кмфкколорбар:: Истеарофф

Указывает, является ли текущая цветовая полоса закрепляемой.

```
BOOL IsTearOff() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущий элемент управления "Цветовая шкала" является закрепляемым; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если элемент управления "цветовая панель" является закрепляемым, он может быть отсоединен от панели управления и закрепляется в другом месте.

## <a name="cmfccolorbaronkey"></a><a name="onkey"></a> Кмфкколорбар:: Онкэй

Вызывается платформой при нажатии пользователем кнопки клавиатуры.

```
virtual BOOL OnKey(UINT nChar);
```

### <a name="parameters"></a>Параметры

*nChar*<br/>
окне Код виртуального ключа для ключа, который пользователь нажал.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод обрабатывает указанный ключ; в противном случае — значение FALSE.

## <a name="cmfccolorbaronsendcommand"></a><a name="onsendcommand"></a> Кмфкколорбар:: Онсендкомманд

Вызывается платформой для закрытия иерархии всплывающих элементов управления.

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Параметры

*пбуттон*\
окне Указатель на элемент управления, находящийся на панели инструментов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

## <a name="cmfccolorbaronupdatecmdui"></a><a name="onupdatecmdui"></a> Кмфкколорбар:: Онупдатекмдуи

Вызывается платформой для включения или отключения элемента пользовательского интерфейса элемента управления "Цветовая шкала" перед отображением элемента.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Параметры

*птаржет*<br/>
окне Указатель на окно, содержащее элемент пользовательского интерфейса для обновления.

*бдисаблеифнохндлер*<br/>
окне Значение TRUE, чтобы отключить элемент пользовательского интерфейса, если в схеме сообщения не определен обработчик. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Когда пользователь приложения щелкает элемент пользовательского интерфейса, элемент должен определить, должен ли он отображаться как включенный или отключенный. Целевой объект командного сообщения предоставляет эти сведения путем реализации обработчика команд ON_UPDATE_COMMAND_UI. Используйте этот метод, чтобы помочь обработать команду. Дополнительные сведения см. в разделе [класс поддержка CCmdUI](../../mfc/reference/ccmdui-class.md).

## <a name="cmfccolorbaropencolordialog"></a><a name="opencolordialog"></a> Кмфкколорбар:: Опенколордиалог

Открывает диалоговое окно "цвет".

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Параметры

*колордефаулт*<br/>
окне Цвет, выбранный по умолчанию при открытии диалогового окна "цвет".

*колоррес*<br/>
заполняет Цвет, выбранный пользователем.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если пользователь выбрал цвет; Значение FALSE, если пользователь отменил диалоговое окно "цвет".

### <a name="remarks"></a>Примечания

## <a name="cmfccolorbarrebuild"></a><a name="rebuild"></a> Кмфкколорбар:: Rebuild

Полностью перерисовывает элемент управления "цветовая панель".

```
virtual void Rebuild();
```

## <a name="cmfccolorbarselectpalette"></a><a name="selectpalette"></a> Кмфкколорбар:: Селектпалетте

Устанавливает логическую палитру указанного контекста устройства в палитру родительской кнопки текущего элемента управления "Цветовая шкала".

```
CPalette* SelectPalette(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*Хозяин*\
окне Указатель на контекст устройства родительской кнопки текущего элемента управления "Цветовая шкала".

### <a name="return-value"></a>Возвращаемое значение

Указатель на палитру, которая заменяется палитрой родительской кнопки текущего элемента управления "Цветовая шкала".

## <a name="cmfccolorbarsetcolor"></a><a name="setcolor"></a> Кмфкколорбар:: Сетколор

Задает цвет, выбранный в данный момент.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*color*<br/>
окне Значение цвета RGB.

## <a name="cmfccolorbarsetcolorname"></a><a name="setcolorname"></a> Кмфкколорбар:: Сетколорнаме

Задает новое имя для указанного цвета.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Параметры

*color*<br/>
окне Значение RGB цвета.

*strName*<br/>
окне Новое имя для указанного цвета.

### <a name="remarks"></a>Примечания

Этот метод изменяет имя указанного цвета во всех `CMFCColorBar` объектах приложения.

## <a name="cmfccolorbarsetcommandid"></a><a name="setcommandid"></a> Кмфкколорбар:: Сеткоммандид

Задает новый идентификатор команды для элемента управления "Цветовая шкала".

```cpp
void SetCommandID(UINT nCommandID);
```

### <a name="parameters"></a>Параметры

*нкоммандид*<br/>
окне Идентификатор команды.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы изменить идентификатор команды элемента управления "Цветовая шкала" и уведомить родительское окно элемента управления об изменении идентификатора.

## <a name="cmfccolorbarsetdocumentcolors"></a><a name="setdocumentcolors"></a> Кмфкколорбар:: Сетдокументколорс

Задает список цветов, используемых в текущем документе.

```cpp
void SetDocumentColors(
    LPCTSTR lpszCaption,
    CList<COLORREF,COLORREF>& lstDocColors,
    BOOL bShowWhenDocked=FALSE);
```

### <a name="parameters"></a>Параметры

*лпсзкаптион*<br/>
окне Заголовок, отображаемый, если элемент управления "цветовая панель" не закреплен.

*лстдокколорс*<br/>
окне Список цветов, заменяющих текущие цвета документа.

*бшоввхендоккед*<br/>
окне Значение TRUE, чтобы отображать цвета документа, когда элемент управления "цветовая панель" закреплен; в противном случае — значение FALSE. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

*Цвета документа* — это цвета, которые в настоящий момент используются в документе. Платформа автоматически сохраняет список цветов документа, но этот метод можно использовать для изменения списка.

## <a name="cmfccolorbarsethorzmargin"></a><a name="sethorzmargin"></a> Кмфкколорбар:: Сесорзмаргин

Задает горизонтальное поле, которое является пробелом между левой или правой ячейкой цвета и границей клиентской области.

```cpp
void SetHorzMargin(int nHorzMargin);
```

### <a name="parameters"></a>Параметры

*нхорзмаргин*<br/>
окне Горизонтальное поле (в пикселях).

### <a name="remarks"></a>Примечания

По умолчанию конструктор [кмфкколорбар:: кмфкколорбар](#cmfccolorbar) устанавливает горизонтальное поле равным 4 пикселям.

## <a name="cmfccolorbarsetproplist"></a><a name="setproplist"></a> Кмфкколорбар:: Сетпроплист

Устанавливает элемент `m_pWndPropList` защищенных данных в указанный указатель на элемент управления сетки свойств.

```cpp
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>Параметры

*пвндлист*\
окне Указатель на объект элемента управления сетки свойств.

## <a name="cmfccolorbarsetvertmargin"></a><a name="setvertmargin"></a> Кмфкколорбар:: Сетвертмаргин

Задает вертикальное поле, которое является пробелом между верхней или нижней ячейкой цвета и границей клиентской области.

```cpp
void SetVertMargin(int nVertMargin);
```

### <a name="parameters"></a>Параметры

*нвертмаргин*<br/>
окне Вертикальное поле (в пикселях).

### <a name="remarks"></a>Примечания

По умолчанию конструктор [кмфкколорбар:: кмфкколорбар](#cmfccolorbar) устанавливает вертикальное поле равным 4 пикселям.

## <a name="cmfccolorbarshowcommandmessagestring"></a><a name="showcommandmessagestring"></a> Кмфкколорбар:: Шовкоммандмессажестринг

Запрашивает окно фрейма, которому принадлежит элемент управления "Цветовая шкала", для обновления строки сообщения в строке состояния.

```
virtual void ShowCommandMessageString(UINT uiCmdId);
```

### <a name="parameters"></a>Параметры

*уикмдид*<br/>
окне Идентификатор команды. (Этот параметр игнорируется.)

### <a name="remarks"></a>Примечания

Этот метод отправляет WM_SETMESSAGESTRING сообщение владельцу элемента управления "Цветовая шкала".

## <a name="see-also"></a>См. также

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
