---
title: Класс CMFCOutlookBarPane
ms.date: 11/04/2016
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
helpviewer_keywords:
- CMFCOutlookBarPane [MFC], AddButton
- CMFCOutlookBarPane [MFC], CanBeAttached
- CMFCOutlookBarPane [MFC], ClearAll
- CMFCOutlookBarPane [MFC], Create
- CMFCOutlookBarPane [MFC], EnablePageScrollMode
- CMFCOutlookBarPane [MFC], GetRegularColor
- CMFCOutlookBarPane [MFC], IsBackgroundTexture
- CMFCOutlookBarPane [MFC], IsDrawShadedHighlight
- CMFCOutlookBarPane [MFC], RemoveButton
- CMFCOutlookBarPane [MFC], SetBackColor
- CMFCOutlookBarPane [MFC], SetBackImage
- CMFCOutlookBarPane [MFC], SetDefaultState
- CMFCOutlookBarPane [MFC], SetExtraSpace
- CMFCOutlookBarPane [MFC], SetTextColor
- CMFCOutlookBarPane [MFC], SetTransparentColor
- CMFCOutlookBarPane [MFC], EnableContextMenuItems
- CMFCOutlookBarPane [MFC], RemoveAllButtons
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
ms.openlocfilehash: 97c7edde26bdf13e899d823dcf88d143068d86a4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749611"
---
# <a name="cmfcoutlookbarpane-class"></a>Класс CMFCOutlookBarPane

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

Контроль, полученный из [класса CMFCToolBar,](../../mfc/reference/cmfctoolbar-class.md) который может быть вставлен в бар Outlook [(класс CMFCOutlookBar).](../../mfc/reference/cmfcoutlookbar-class.md) Область панели Outlook содержит столбец больших кнопок. Пользователь может прокрутить список с кнопками вверх и вниз, если он больше области, в которой отображается. Когда пользователь окончательно удаляет область панели Outlook из панели Outlook, она может стать плавающей или прикрепиться к окну основного фрейма.

## <a name="syntax"></a>Синтаксис

```
class CMFCOutlookBarPane : public CMFCToolBar
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Конструктор по умолчанию.|
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCOutlookBarPane::Добавить кнопку](#addbutton)|Добавляет кнопку в панель Outlook.|
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|Определяет, можно ли пристыковать стекло к другому сну или окну рамы. (Переопределяет [CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached).)|
|`CMFCOutlookBarPane::CanBeRestored`|Определяет, может ли система восстановить панель инструментов в исходное состояние после настройки. (Переопределяет [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[CMFCOutlookBarPane::ClearAll](#clearall)|Освобождает ресурсы, используемые изображениями в панели бара Outlook.|
|[CMFCOutlookBarPane::Создание](#create)|Создает панель панели Outlook.|
|`CMFCOutlookBarPane::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCOutlookBarPane::Dock`|Вызывается по системе, чтобы стыковка панели панели outlook бар. (Переопределяет `CPane::Dock`.)|
|[CMFCOutlookBarPane:EnablePageScrollMode](#enablepagescrollmode)|Определяет, являются ли стрелка миноносца на панели Outlook заранее список кнопок по странице, или по кнопке.|
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Возвращает обычный (не выбранный) цвет текста панели панели Outlook.|
|`CMFCOutlookBarPane::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Определяет, есть ли фоновое изображение, загруженное для панели панели панели outlook.|
|`CMFCOutlookBarPane::IsChangeState`|Определяет, может ли плавающая панель быть пристыкована. (Переопределяет `CPane::IsChangeState`.)|
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|Определяет, затенена ли граница кнопки при выделении кнопки и отображении фонового изображения.|
|`CMFCOutlookBarPane::OnBeforeFloat`|Вызывается по фреймворку, когда панель вот-вот поплывет. (Переопределяет [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|
|[CMFCOutlookBarPane::Удалить кнопку](#removebutton)|Удаляет кнопку с указанным идентификатором команды.|
|`CMFCOutlookBarPane::RestoreOriginalstate`|Восстанавливает первоначальное состояние панели инструментов. (Переопределяет [CMFCToolBar::RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|Устанавливает цвет фона.|
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|Устанавливает фоновое изображение.|
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|Сброс панели Outlook панели с исходным набором кнопок.|
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Устанавливает количество пикселей обивки, используемой вокруг кнопок в панели панели Outlook.|
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Устанавливает цвета обычного и выделенного текста в панели бара Outlook.|
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Устанавливает прозрачный цвет панели панели Outlook.|
|`CMFCOutlookBarPane::SmartUpdate`|Используется внутренне для обновления бара Outlook. (Переопределяет `CMFCToolBar::SmartUpdate`.)|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCOutlookBarPane:EnableContextMenuItems](#enablecontextmenuitems)|Определяет, какие элементы меню ярлыка отображаются в режиме настройки.|
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Удаляет все кнопки из панели Outlook. (Перекрывает [CMFCToolBar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|

## <a name="remarks"></a>Примечания

Для получения информации о том, [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md)как реализовать панель Outlook, см.

На примере бара Outlook можно ознакомиться в примере проекта OutlookDemo.

## <a name="example"></a>Пример

Ниже приводится следующий пример, как `CMFCOutlookBarPane` использовать различные методы класса. На примере показано, как создать панель Outlook, включить режим прокрутки страницы, включить стыковку и установить цвет фона панели Outlook. Этот фрагмент кода является частью [образца Outlook Multi Views.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxoutlookbarpane.h

## <a name="cmfcoutlookbarpaneaddbutton"></a><a name="addbutton"></a>CMFCOutlookBarPane::Добавить кнопку

Добавляет кнопку в панель Outlook.

```
BOOL AddButton(
    UINT uiImage,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    UINT uiImage,
    UINT uiLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    LPCTSTR szBmpFileName,
    LPCTSTR szLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HBITMAP hBmp,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HICON hIcon,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1,
    BOOL bAlphaBlend=FALSE);
```

### <a name="parameters"></a>Параметры

*uiImage*<br/>
(в) Определяет идентификатор ресурса битной карты.

*lpszLabel*<br/>
(в) Определяет текст кнопки.

*iIdCommand*<br/>
(в) Упоняет идентификатор управления кнопкой.

*iInsertAt*<br/>
(в) Упоньте нулевой индекс на странице панели outlook, на которой можно вставить кнопку.

*uiLabel*<br/>
(в) Идентификатор строки ресурса.

*szBmpFileName*<br/>
(в) Определяет название файла изображения диска для загрузки.

*szLabel*<br/>
(в) Определяет текст кнопки.

*hBmp*<br/>
(в) Ручка к битовой карте кнопки.

*hIcon*<br/>
(в) Ручка к значку кнопок.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если кнопка была добавлена успешно; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы вставить новую кнопку на страницу бара Outlook. Изображение кнопки может быть загружено либо с ресурсов приложения, либо из дискового файла.

Если идентификатор страницы, указанный *uiPageID,* составляет -1, кнопка вставляется на первую страницу.

Если индекс, указанный *iInsertAt,* составляет -1, кнопка добавляется в конце страницы.

## <a name="cmfcoutlookbarpanecanbeattached"></a><a name="canbeattached"></a>CMFCOutlookBarPane::CanBeAttached

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcoutlookbarpaneclearall"></a><a name="clearall"></a>CMFCOutlookBarPane::ClearAll

Освобождает ресурсы, используемые изображениями на панели бара Outlook.

```cpp
void ClearAll();
```

### <a name="remarks"></a>Примечания

Этот метод непосредственно вызывает [CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear), который называется на изображениях, которые используются панелью Outlook.

## <a name="cmfcoutlookbarpanecreate"></a><a name="create"></a>CMFCOutlookBarPane::Создание

Создает панель панели Outlook.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,
    UINT uiID=(UINT)-1,
    DWORD dwControlBarStyle=0);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
(в) Опознавайте родительское окно управления панелью outlook. Не должно быть NULL.

*dwStyle*<br/>
(в) Стиль окна.  Список стилей окон можно узнать в [стиле window.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*uiID*<br/>
(в) Идентификатор управления. Должно быть уникальным, чтобы сохранить состояние управления.

*dwControlBarStyle*<br/>
(в) Определяется специальные стили, определяющие поведение управления панелью Outlook, когда оно отделено от бара Outlook.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод был успешным; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Чтобы построить `CMFCOutlookBarPane` объект, сначала позвоните в `Create`конструктор, а затем вызов , который создает `CMFCOutlookBarPane` панель Outlook панели управления и прикрепляет его к объекту.

Для получения `dwControlBarStyle` дополнительной информации о [см. CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).

## <a name="cmfcoutlookbarpaneenablecontextmenuitems"></a><a name="enablecontextmenuitems"></a>CMFCOutlookBarPane:EnableContextMenuItems

Определяет, какие элементы меню ярлыка отображаются в режиме настройки.

```
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,
    CMenu* pPopup);
```

### <a name="parameters"></a>Параметры

*pButton*<br/>
(в) Указатель на кнопку панели инструментов, которую нажал пользователь.

*pPopup*<br/>
(в) Указатель на меню ярлыка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если меню ярлыка должно быть отображено; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Переопределить этот метод, чтобы изменить стандартное меню ярлыка, которое фреймотображается в режиме настройки.

Реализация по умолчанию проверяет режим настройки [(CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)), и если он установлен на ИСТИНу, отключает все элементы меню ярлыка, кроме **удаления.** Затем он просто передает входные `CMFCToolBar::EnableContextMenuItems`параметры.

> [!NOTE]
> *Контекстное меню* является синонимом меню ярлыка.

## <a name="cmfcoutlookbarpaneenablepagescrollmode"></a><a name="enablepagescrollmode"></a>CMFCOutlookBarPane:EnablePageScrollMode

Уточняется, являются ли стрелка прокрутки на панели Outlook списком кнопок по странице за страницей или кнопкой за кнопкой.

```cpp
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```

### <a name="parameters"></a>Параметры

*bPageScroll*<br/>
(в) Если true, включите режим прокрутки страницы. Если FALSE, отойдите от режима прокрутки страницы.

## <a name="cmfcoutlookbarpanegetregularcolor"></a><a name="getregularcolor"></a>CMFCOutlookBarPane::GetRegularColor

Возвращает обычный (т.е. не выбранный) цвет текста панели панели Outlook.

```
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий цвет текста как значение цвета RGB.

### <a name="remarks"></a>Примечания

Используйте [CMFCOutlookBarPane::SetTextColor](#settextcolor) для установки текущего (обычного и выбранного) цвета текста панели Outlook. Вы можете получить цвет текста по умолчанию, позвонив в функцию [GetSysColor](/windows/win32/api/winuser/nf-winuser-getsyscolor) с индексом COLOR_WINDOW.

## <a name="cmfcoutlookbarpaneisbackgroundtexture"></a><a name="isbackgroundtexture"></a>CMFCOutlookBarPane::IsBackgroundTexture

Определяет, есть ли фоновое изображение, загруженное для панели панели панели outlook.

```
BOOL IsBackgroundTexture() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если есть фоновое изображение для отображения; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Вы можете добавить фоновое изображение, позвонив в функцию [CMFCOutlookBarPane::SetBackImage.](#setbackimage)

Если нет фонового изображения, фон окрашен цветом, указанным с помощью [CMFCOutlookBarPane::SetBackColor](#setbackcolor).

## <a name="cmfcoutlookbarpaneisdrawshadedhighlight"></a><a name="isdrawshadedhighlight"></a>CMFCOutlookBarPane::IsDrawShadedHighlight

Определяет, затенена ли граница кнопки при выделении кнопки и отображении фонового изображения.

```
BOOL IsDrawShadedHighlight() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если границы кнопки затенены; в противном случае FALSE.

## <a name="cmfcoutlookbarpaneremoveallbuttons"></a><a name="removeallbuttons"></a>CMFCOutlookBarPane::RemoveAllButtons

Удаляет все кнопки из панели Outlook.

```
virtual void RemoveAllButtons();
```

## <a name="cmfcoutlookbarpaneremovebutton"></a><a name="removebutton"></a>CMFCOutlookBarPane::Удалить кнопку

Удаляет кнопку с указанным идентификатором команды.

```
BOOL RemoveButton(UINT iIdCommand);
```

### <a name="parameters"></a>Параметры

*iIdCommand*<br/>
(в) Уотражай идентификатор команды кнопки для удаления.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если кнопка была успешно удалена; FALSE, если указанный идентификатор команды недействителен.

## <a name="cmfcoutlookbarpanesetbackcolor"></a><a name="setbackcolor"></a>CMFCOutlookBarPane::SetBackColor

Устанавливает цвет фона бара Outlook.

```cpp
void SetBackColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
[in] Задает новый цвет фона.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы установить текущий цвет фона для бара Outlook. Цвет фона используется только в том случае, если нет фонового изображения.

## <a name="cmfcoutlookbarpanesetbackimage"></a><a name="setbackimage"></a>CMFCOutlookBarPane::SetBackImage

Устанавливает фоновое изображение.

```cpp
void SetBackImage(UINT uiImageID);
```

### <a name="parameters"></a>Параметры

*uiImageID*<br/>
(в) Упогоняет идентификатор ресурса изображения.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы установить фоновое изображение панели Outlook. Список фоновых изображений управляется встроенным объектом [класса CMFCToolBarImages.](../../mfc/reference/cmfctoolbarimages-class.md)

## <a name="cmfcoutlookbarpanesetdefaultstate"></a><a name="setdefaultstate"></a>CMFCOutlookBarPane::SetDefaultState

Сброс панели Outlook панели с исходным набором кнопок.

```cpp
void SetDefaultState();
```

### <a name="remarks"></a>Примечания

Этот метод восстанавливает кнопки панели Outlook в исходном наборе. Этот метод `CMFCOutlookBarPane::RestoreOriginalstate`похож на, за исключением того, что он не вызывает перерисовку панели Outlook.

## <a name="cmfcoutlookbarpanesetextraspace"></a><a name="setextraspace"></a>CMFCOutlookBarPane::SetExtraSpace

Устанавливает количество пикселей обивки, используемой вокруг кнопок в панели панели Outlook.

```cpp
void SetExtraSpace()
```

## <a name="cmfcoutlookbarpanesettextcolor"></a><a name="settextcolor"></a>CMFCOutlookBarPane::SetTextColor

Устанавливает цвета обычного и выделенного текста в панели бара Outlook.

```cpp
void SetTextColor(
    COLORREF clrRegText,
    COLORREF clrSelText=0);
```

### <a name="parameters"></a>Параметры

*clrRegText*<br/>
(в) Определяет новый цвет для невыбранного текста.

*clrSelText*<br/>
(в) Определяет новый цвет для выбранного текста.

## <a name="cmfcoutlookbarpanesettransparentcolor"></a><a name="settransparentcolor"></a>CMFCOutlookBarPane::SetTransparentColor

Устанавливает прозрачный цвет панели панели Outlook.

```cpp
void SetTransparentColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Определяет новый прозрачный цвет.

### <a name="remarks"></a>Примечания

Прозрачный цвет необходим для отображения прозрачных изображений. Любое появление этого цвета на изображении окрашено фоновым цветом.  Нет никакого смешения фоновых и передних изображений.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
