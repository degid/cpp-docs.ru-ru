---
title: CmFCColorMenuButton класс
ms.date: 11/04/2016
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
ms.openlocfilehash: 9c895573c626a890facfef689fce4b516aff5115
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752515"
---
# <a name="cmfccolormenubutton-class"></a>CmFCColorMenuButton класс

Класс `CMFCColorMenuButton` поддерживает команду меню или кнопку панели инструментов, которая запускает поле диалога сборщика цветов.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Формирует объект `CMFCColorMenuButton`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Включает и отстраняет "автоматическую" кнопку, расположенную над обычными цветными кнопками. (Стандартная автоматическая кнопка системы помечена **Как автоматическая**.)|
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Позволяет отображать конкретные цвета, связанные с документами, а не цвета системы.|
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Включает и отстраняет "другие" кнопки, которая расположена ниже обычных цветовых кнопок. (Стандартная кнопка системы "другие" помечена **больше цветов**.)|
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Позволяет оторвать цветное стекло.|
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Извлекает текущий автоматический цвет.|
|[CMFCColorMenuButton::GetColor](#getcolor)|Извлекает цвет текущей кнопки.|
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Извлекает цвет, соответствующий указанному идентификатору команды.|
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается инфраструктурой при изменении родительского окна.|
|[CMFCColorMenuButton::OpenColorДиалог](#opencolordialog)|Открывает поле диалога выбора цвета.|
|[CMFCColorMenuButton::SetColor](#setcolor)|Устанавливает цвет текущей кнопки цвета.|
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Устанавливает цвет указанной кнопки цветового меню.|
|[CMFCColorMenuButton::SetColorName](#setcolorname)|Устанавливает новое имя для указанного цвета.|
|[CMFCColorMenuButton::SetColumnsНомер](#setcolumnsnumber)|Устанавливает количество столбцов, отображаемых объектом. `CMFCColorBar`|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Копирует другую кнопку панели инструментов на текущую кнопку.|
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Создает цвет сборщик диалоговую коробку.|
|[CMFCColorMenuButton::IsemptyMenuAllowed](#isemptymenuallowed)|Указывает, поддерживаются ли пустые меню.|
|[CMFCColorMenuButton::Ondraw](#ondraw)|Вызывается по системе для отображения изображения на кнопке.|
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Вызывается фреймворком перед отображением `CMFCColorMenuButton` объекта в списке диалогового окна настройки панели инструментов.|

## <a name="remarks"></a>Примечания

Чтобы заменить исходную кнопку команды `CMFCColorMenuButton` меню или `CMFCColorMenuButton` кнопку панели инструментов объектом, создайте `ReplaceButton` объект, установите любые соответствующие стили [класса CMFCColorBar,](../../mfc/reference/cmfccolorbar-class.md) а затем позвоните по методу класса [CMFCToolBar.](../../mfc/reference/cmfctoolbar-class.md) Если вы настраиваете панель инструментов, позвоните в метод [CMFCToolBarsCustomizeDialog::ReplaceButton.](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton)

Коробка диалогов цветного сборщика создается во время обработки обработчика событий [CMFCColorMenuButton::CreatePopupMenu.](#createpopupmenu) Обработчик события уведомляет родительский кадр с WM_COMMAND сообщением. Объект `CMFCColorMenuButton` отправляет идентификатор управления, назначенный исходной кнопке команды меню или панели инструментов.

## <a name="example"></a>Пример

В следующем примере показано, как создать и настроить кнопку цветового меню с помощью различных методов в `CMFCColorMenuButton` классе. В примере `CPalette` объект сначала создается, а затем используется `CMFCColorMenuButton` для построения объекта класса. Объект `CMFCColorMenuButton` настраивается, включив его автоматические и другие кнопки, а также установив его цвет и количество столбцов. Этот код является частью [образца Word Pad.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcolormenubutton.h

## <a name="cmfccolormenubuttoncmfccolormenubutton"></a><a name="cmfccolormenubutton"></a>CMFCColorMenuButton::CMFCColorMenuButton

Формирует объект `CMFCColorMenuButton`.

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>Параметры

*uiCmdID*<br/>
(в) Идентификатор команды кнопки.

*lpszText*<br/>
(в) Текст кнопки.

*pPalette*<br/>
(в) Указатель на цветовую палитру кнопки.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Первым конструктором является конструктор по умолчанию. Текущий цвет объекта и автоматический цвет инициализированы к черному (RGB (0, 0, 0)).

Второй конструктор инициализирует кнопку к цвету, который соответствует указанному идентификатору команды.

## <a name="cmfccolormenubuttoncopyfrom"></a><a name="copyfrom"></a>CMFCColorMenuButton::CopyFrom

Копирует один [объект cmFCToolBarMenuButton класса,](../../mfc/reference/cmfctoolbarmenubutton-class.md)полученный на другой.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
(в) Кнопка исходного кода для копирования.

### <a name="remarks"></a>Примечания

Переопределить этот метод для копирования объектов, полученных `CMFCColorMenuButton` от объекта.

## <a name="cmfccolormenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a>CMFCColorMenuButton::CreatePopupMenu

Создает цвет сборщик диалоговую коробку.

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, представляющий поле диалога сборщика цветов.

### <a name="remarks"></a>Примечания

Этот метод вызывается фреймворком, когда пользователь нажимает кнопку цветового меню.

## <a name="cmfccolormenubuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCColorMenuButton::EnableAutomaticButton

Включает и отстраняет "автоматическую" кнопку, расположенную над обычными цветными кнопками. (Стандартная автоматическая кнопка системы помечена **Как автоматическая**.)

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Определяет текст кнопки, который отображается, когда кнопка становится автоматической.

*colorAutomatic*<br/>
(в) Определяет новый автоматический цвет.

*bEnable*<br/>
(в) Уточняется, является ли кнопка автоматической или нет.

### <a name="remarks"></a>Примечания

Автоматическая кнопка применяет текущий цвет по умолчанию.

## <a name="cmfccolormenubuttonenabledocumentcolors"></a><a name="enabledocumentcolors"></a>CMFCColorMenuButton::EnableDocumentColors

Позволяет отображать конкретные цвета, связанные с документами, а не цвета системы.

```cpp
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Определяет текст кнопки.

*bEnable*<br/>
(в) TRUE для отображения конкретных цветов документа или FALSE для отображения цвета системы.

### <a name="remarks"></a>Примечания

Используйте этот метод для отображения текущих цветов документа или цветов палитры системы, когда пользователь нажимает кнопку цветового меню.

## <a name="cmfccolormenubuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFCColorMenuButton::EnableOtherButton

Включает и отстраняет "другие" кнопки, которая расположена ниже обычных цветовых кнопок. (Стандартная кнопка системы "другие" помечена **больше цветов**.)

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Определяет текст кнопки.

*bAltColorDlg*<br/>
(в) Укажите TRUE `CMFCColorDialog` для отображения диалогового окна или FALSE для отображения стандартной системы цветдиалога.

*bEnable*<br/>
(в) Указать TRUE для отображения "другой" кнопки; в противном случае, FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

## <a name="cmfccolormenubuttonenabletearoff"></a><a name="enabletearoff"></a>CMFCColorMenuButton::EnableTearOff

Позволяет оторвать цветное стекло.

```cpp
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
(в) Определяет идентификатор для разрыва панели.

*nVertDockКолонки*<br/>
(в) Определяет количество столбцов в вертикально пристыкованных цветовых стеклах в состоянии отрыва.

*nHorzDockRows*<br/>
(в) Определяет количество строк для горизонтально пристыкованного цветового стекла в состоянии отрыва.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы включить функцию «слезы» для `CMFCColorMenuButton` цветового стекла, которое всплывает при нажатии кнопки.

## <a name="cmfccolormenubuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>CMFCColorMenuButton::GetAutomaticColor

Извлекает текущий автоматический цвет.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB, представляющее текущий автоматический цвет.

### <a name="remarks"></a>Примечания

Позвоните по этому методу, чтобы получить автоматический цвет, который устанавливается [CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton).

## <a name="cmfccolormenubuttongetcolor"></a><a name="getcolor"></a>CMFCColorMenuButton::GetColor

Извлекает цвет текущей кнопки.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет кнопки.

### <a name="remarks"></a>Примечания

## <a name="cmfccolormenubuttongetcolorbycmdid"></a><a name="getcolorbycmdid"></a>CMFCColorMenuButton::GetColorByCmdID

Извлекает цвет, соответствующий указанному идентификатору команды.

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>Параметры

*uiCmdID*<br/>
(в) Идентификатор команды.

### <a name="return-value"></a>Возвращаемое значение

Цвет, соответствующий указанному идентификатору команды.

### <a name="remarks"></a>Примечания

Используйте этот метод, когда у вас есть несколько цветовых кнопок в приложении. Когда пользователь нажимает кнопку цвета, кнопка отправляет свой идентификатор команды в WM_COMMAND сообщение своему родителю. Метод `GetColorByCmdID` использует идентификатор команды для получения соответствующего цвета.

## <a name="cmfccolormenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a>CMFCColorMenuButton::IsemptyMenuAllowed

Указывает, поддерживаются ли пустые меню.

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если разрешено пустое меню; в противном случае, ноль.

### <a name="remarks"></a>Примечания

Пустые меню поддерживаются по умолчанию. Переопределить этот метод, чтобы изменить это поведение в производном классе.

## <a name="cmfccolormenubuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCColorMenuButton::OnChangeParentWnd

Вызывается инфраструктурой при изменении родительского окна.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Указатель на новое родительское окно.

### <a name="remarks"></a>Примечания

## <a name="cmfccolormenubuttonondraw"></a><a name="ondraw"></a>CMFCColorMenuButton::Ondraw

Вызывается по системе для отображения изображения на кнопке.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz=TRUE,
    BOOL bCustomizeMode=FALSE,
    BOOL bHighlight=FALSE,
    BOOL bDrawBorder=TRUE,
    BOOL bGrayDisabledButtons=TRUE);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Прямоугольник, который граничит с областью для перерисовки.

*pImages*<br/>
(в) Указывает на список изображений панели инструментов.

*bHorz*<br/>
(в) TRUE указать, что панель инструментов находится в горизонтальном пристыкованном состоянии; в противном случае, FALSE. Значение по умолчанию — TRUE.

*bCustomizeMode*<br/>
(в) TRUE указать, что приложение находится в режиме настройки; в противном случае, FALSE. Значение по умолчанию — FALSE.

*bHighlight*<br/>
(в) TRUE указать, что кнопка выделена; в противном случае, FALSE. Значение по умолчанию — FALSE.

*bDrawBorder*<br/>
(в) TRUE указать, что граница кнопки отображается; в противном случае, FALSE. Значение по умолчанию — TRUE.

*bGrayDisabledButtons*<br/>
(в) TRUE указать, что отключенные кнопки серые (затуманенные) из; в противном случае, FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

## <a name="cmfccolormenubuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCColorMenuButton::OnDrawOnCustomizeList

Вызывается фреймворком перед отображением `CMFCColorMenuButton` объекта в списке диалогового окна настройки панели инструментов.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Прямоугольник, который связывает кнопку, которая будет нарисована.

*bВыбор*<br/>
(в) TRUE указывает, что кнопка находится в выбранном состоянии; в противном случае, FALSE.

### <a name="return-value"></a>Возвращаемое значение

Ширина кнопки.

### <a name="remarks"></a>Примечания

Этот метод вызывается фреймворкой, когда `CMFCColorMenuButton` объект отображается в поле списка в процессе настройки панели инструментов.

## <a name="cmfccolormenubuttonopencolordialog"></a><a name="opencolordialog"></a>CMFCColorMenuButton::OpenColorДиалог

Открывает поле диалога выбора цвета.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Параметры

*colorDefault*<br/>
(в) Цвет по умолчанию, выбранный в цветном диалоговом поле.

*colorRes*<br/>
(ваут) Возвращает цвет, выбранный пользователем из цветного диалогового окна.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь выбирает новый цвет; в противном случае, ноль.

### <a name="remarks"></a>Примечания

При нажатии кнопки меню позвоните по этому методу, чтобы открыть цветное поле диалога. Если значение возврата ненулевое, цвет, выбранный пользователем, сохраняется в параметре *colorRes.* Используйте метод [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) для переключения между стандартным цветным диалоговым полем и диалоговым окном [cmFCColorDialog.](../../mfc/reference/cmfccolordialog-class.md)

## <a name="cmfccolormenubuttonsetcolor"></a><a name="setcolor"></a>CMFCColorMenuButton::SetColor

Устанавливает цвет текущей кнопки цвета.

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>Параметры

*Clr*<br/>
(в) Значение цвета RGB.

*bNotify*<br/>
(в) TRUE для применения цвета параметра *clr* к любой связанной кнопке меню или кнопке панели инструментов; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы изменить цвет текущей кнопки цвета. Если параметр *bNotify* незеролитный, цвет соответствующей кнопки в любом связанном всплывающем меню или панели инструментов изменяется на цвет, указанный параметром *clr.*

## <a name="cmfccolormenubuttonsetcolorbycmdid"></a><a name="setcolorbycmdid"></a>CMFCColorMenuButton::SetColorByCmdID

Устанавливает цвет указанной кнопки цветового меню.

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>Параметры

*uiCmdID*<br/>
(в) Идентификатор ресурса кнопки цветового меню.

*Цвет*<br/>
(в) Значение цвета RGB.

## <a name="cmfccolormenubuttonsetcolorname"></a><a name="setcolorname"></a>CMFCColorMenuButton::SetColorName

Устанавливает новое имя для указанного цвета.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Значение RGB цвета, имя которого изменяется.

*strName*<br/>
(в) Новое название цвета.

### <a name="remarks"></a>Примечания

## <a name="cmfccolormenubuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFCColorMenuButton::SetColumnsНомер

Устанавливает количество столбцов для отображения в элементе управления цветовой выбор (объект [CMFCColorBar).](../../mfc/reference/cmfccolorbar-class.md)

```cpp
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Параметры

*nColumns*<br/>
(в) Количество столбцов для отображения.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarsИнтоуктияДиолог класс](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[Класс CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)
