---
title: класс CMFCRibbonColorButton
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
ms.openlocfilehash: 528b883d75889589c7021f462324dd9dcb71be25
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754842"
---
# <a name="cmfcribboncolorbutton-class"></a>класс CMFCRibbonColorButton

Класс `CMFCRibbonColorButton` реализует кнопку цвета, которую можно добавить на панель ленты. Кнопка цвета ленты отображает раскрывающееся меню, содержащее одну или несколько палитр.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonColorButton : public CMFCRibbonGallery
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|Добавляет группу цветов в стандартную область цветов.|
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|Указывает, нажата ли кнопка **Автоматически** .|
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|Активирует кнопку **Другие** .|
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||
|[CMFCRibbonColorButton::GetColor](#getcolor)|Возвращает выбранный в данный момент цвет.|
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|Возвращает размер цветовых элементов, отображаемых на цветовой панели.|
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|Возвращает цвет элемента, выбранного в данный момент во всплывающей цветовой палитре.|
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|Удаляет все группы цветов из стандартной области цветов.|
|[CMFCRibbonColorButton::SetColor](#setcolor)|Выбирает цвет в стандартной области цветов.|
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|Задает размер всех цветовых элементов, отображаемых на цветовой панели.|
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|Задает список значений RGB, которые должны отображаться в области цветов документа.|
|[CMFCRibbonColorButton::SetPalette](#setpalette)||
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||

## <a name="remarks"></a>Примечания

Когда пользователь нажимает кнопку цвета на ленте, отображается цветовая панель. По умолчанию эта панель содержит палитру выбора цвета, называемую стандартной областью цветов. Помимо этого, цветовая панель может содержать кнопку **Автоматически** , которая позволяет пользователю выбрать цвет по умолчанию, и кнопку **Другие** , которая позволяет открыть всплывающую цветовую палитру с дополнительными цветами.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCRibbonColorButton` . В нем показано, как создать объект `CMFCRibbonColorButton` , задать большое изображение, активировать кнопку **Автоматически** , активировать кнопку **Другие** , задать число столбцов, задать размер всех цветовых элементов, отображаемых на цветовой панели, добавить группу цветов в стандартную область цветов и указать список значений RGB, которые должны отображаться в области цветов документа. Этот фрагмент кода входит в состав [примера Draw Client](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribboncolorbutton.h

## <a name="cmfcribboncolorbuttonaddcolorsgroup"></a><a name="addcolorsgroup"></a>CMFCRibbonColorButton::AddColorsGroup

Добавляет группу цветов в стандартную область цветов.

```cpp
void AddColorsGroup(
    LPCTSTR lpszName,
    const CList<COLORREF,COLORREF>& lstColors,
    BOOL bContiguousColumns=FALSE);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
(в) Название группы.

*lstColors*<br/>
(в) Список цветов.

*bContiguousКолонки*<br/>
(в) Контролируйте, как цветные элементы отображаются в группе. Если правда, цветные элементы нарисованы без вертикального интервала. Если FALSE, цветные элементы нарисованы с вертикальным интервалом.

### <a name="remarks"></a>Примечания

Используйте эту функцию, чтобы сделать цвет всплывающее отображение нескольких групп цветов. Вы можете контролировать, как цвета отображаются в группе.

## <a name="cmfcribboncolorbuttoncmfcribboncolorbutton"></a><a name="cmfcribboncolorbutton"></a>CMFCRibbonColorButton::CMFCRibbonColorButton

Формирует объект `CMFCRibbonColorButton`.

```
CMFCRibbonColorButton();

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex,
    COLORREF color = RGB(0, 0, 0));

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    BOOL bSimpleButtonLook,
    int nSmallImageIndex,
    int nLargeImageIndex,
    COLORREF color = RGB(0, 0, 0));
```

### <a name="parameters"></a>Параметры

*nID*<br/>
(в) Упоняет идентификатор команды для выполнения, когда пользователь нажимает на кнопку.

*lpszText*<br/>
(в) Определяет текст для отображаться на кнопке.

*nSmallImageIndex*<br/>
(в) Индекс небольшого изображения на нулевой основе появится на кнопке.

*Цвет*<br/>
(в) Цвет кнопки (по умолчанию на черный).

*bSimpleButtonLook*<br/>
(в) Если правда, кнопка обращается как простой прямоугольник.

*nLargeImageIndex*<br/>
(в) Индекс большого изображения с нулевым уровнем, чтобы появиться на кнопке.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCRibbonColorButton::EnableAutomaticButton

Указывает, нажата ли кнопка **Автоматически** .

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE,
    LPCTSTR lpszToolTip=NULL,
    BOOL bOnTop=TRUE,
    BOOL bDrawBorder=FALSE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Метка для кнопки **Автоматическая.**

*colorAutomatic*<br/>
(в) Значение RGB, которое определяет цвет кнопки **автоматическая** по умолчанию.

*bEnable*<br/>
(в) TRUE, если кнопка **Автоматическая** включена; FALSE, если он отключен.

*lpszToolTip*<br/>
(в) Инструментная кнопка **Автоматическая.**

*bOnTop*<br/>
(в) Определяет, находится ли **кнопка Автоматическая** сверху, до цветовой палитры.

*bDrawBorder*<br/>
(в) ПРАВДА, если приложение рисует границу вокруг цвета бар на ленте цвет кнопки. Цветовая панель отображает выбранный в настоящее время цвет. FALSE, если приложение не рисует границу

## <a name="cmfcribboncolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFCRibbonColorButton::EnableOtherButton

Активирует кнопку **Другие** .

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    LPCTSTR lpszToolTip=NULL);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
Метка кнопки.

*lpszToolTip*<br/>
Текст инструментария для **другой** кнопки.

### <a name="remarks"></a>Примечания

**Другая** кнопка — это кнопка, отображаемый под группой цветов. Когда пользователь нажимает кнопку **«Другая»,** она отображает цветовой диалог.

## <a name="cmfcribboncolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>CMFCRibbonColorButton::GetAutomaticColor

Извлекает текущий цвет автоматической кнопки.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB, представляющее текущий цвет автоматической кнопки.

### <a name="remarks"></a>Примечания

Цвет автоматической кнопки устанавливается `colorAutomatic` параметром, передаваемым методу. `CMFCRibbonColorButton::EnableAutomaticButton`

## <a name="cmfcribboncolorbuttongetcolor"></a><a name="getcolor"></a>CMFCRibbonColorButton::GetColor

Возвращает выбранный в данный момент цвет.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет выбран, нажав на кнопку.

## <a name="cmfcribboncolorbuttongetcolorboxsize"></a><a name="getcolorboxsize"></a>CMFCRibbonColorButton::GetColorBoxSize

Возвращает размер цветовых элементов, отображаемых на цветовой панели.

```
CSize GetColorBoxSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер цветных кнопок в выпадающей цветовой палитре.

## <a name="cmfcribboncolorbuttongetcolumns"></a><a name="getcolumns"></a>CMFCRibbonColorButton::GetКолонки

Получает количество элементов в строке галереи отображения кнопки ленты цвета.

```
int GetColumns() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество значков в каждой строке.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncolorbuttongethighlightedcolor"></a><a name="gethighlightedcolor"></a>CMFCRibbonColorButton::GetHighlightedColor

Возвращает цвет выбранного в настоящее время элемента на всплывающее цветовую палитру.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет выбранного в настоящее время элемента на всплывающем цветовой палитре.

## <a name="cmfcribboncolorbuttonremoveallcolorgroups"></a><a name="removeallcolorgroups"></a>CMFCRibbonColorButton::RemoveAllColorGroups

Удаляет все группы цветов из стандартной области цветов.

```cpp
void RemoveAllColorGroups();
```

## <a name="cmfcribboncolorbuttonsetcolor"></a><a name="setcolor"></a>CMFCRibbonColorButton::SetColor

Выбирает цвет в стандартной области цветов.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Цвет для установки.

## <a name="cmfcribboncolorbuttonsetcolorboxsize"></a><a name="setcolorboxsize"></a>CMFCRibbonColorButton::SetColorBoxSize

Задает размер всех цветовых элементов, отображаемых на цветовой панели.

```cpp
void SetColorBoxSize(CSize sizeBox);
```

### <a name="parameters"></a>Параметры

*sizeBox*<br/>
(в) Новый размер цветовых кнопок в цветовой палитре.

## <a name="cmfcribboncolorbuttonsetcolorname"></a><a name="setcolorname"></a>CMFCRibbonColorButton::SetColorName

Устанавливает новое имя для указанного цвета.

```
static void __stdcall SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Значение RGB цвета.

*strName*<br/>
(в) Новое название для указанного цвета.

### <a name="remarks"></a>Примечания

Поскольку `CMFCColorBar::SetColorName`он вызывает, этот метод изменяет `CMFCColorBar` имя указанного цвета во всех объектах в приложении.

## <a name="cmfcribboncolorbuttonsetcolumns"></a><a name="setcolumns"></a>CMFCRibbonColorButton::SetColumns

Устанавливает количество столбцов, отображаемых в таблице цветов, которые представлены пользователю в процессе выбора цвета пользователя.

```cpp
void SetColumns(int nColumns);
```

### <a name="parameters"></a>Параметры

*nColumns*<br/>
(в) Количество цветовых иконок для отображения в каждой строке.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a>CMFCRibbonColorButton::SetDocumentColors

Задает список значений RGB, которые должны отображаться в области цветов документа.

```cpp
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Текст, который будет отображаться с цветами документа.

*lstColors*<br/>
(в) Ссылка на список значений RGB.

## <a name="cmfcribboncolorbuttonsetpalette"></a><a name="setpalette"></a>CMFCRibbonColorButton::SetPalette

Определяет стандартные цвета для отображения в цветовой таблице, отображаемой кнопкой цвета.

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Параметры

*pPalette*<br/>
(в) Указатель на цветовую палитру.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncolorbuttonupdatecolor"></a><a name="updatecolor"></a>CMFCRibbonColorButton::UpdateColor

Вызывается по фреймворку, когда пользователь выбирает цвет из цветовой таблицы, отображаемой при нажатии кнопки цвета.

```cpp
void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Цвет, выбранный пользователем.

### <a name="remarks"></a>Примечания

Метод `CMFCRibbonColorButton::UpdateColor` изменяет цвет выбранной в настоящее время кнопки и уведомляет своего родителя, отправляя WM_COMMAND сообщение с BN_CLICKED стандартным уведомлением. Используйте метод [CMFCRibbonColorButton::GetColor](#getcolor) для получения выбранного цвета.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)
