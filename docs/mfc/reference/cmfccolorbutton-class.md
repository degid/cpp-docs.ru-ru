---
title: Класс Кмфкколорбуттон
ms.date: 11/04/2016
f1_keywords:
- CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::EnableAutomaticButton
- AFXCOLORBUTTON/CMFCColorButton::EnableOtherButton
- AFXCOLORBUTTON/CMFCColorButton::GetAutomaticColor
- AFXCOLORBUTTON/CMFCColorButton::GetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColorName
- AFXCOLORBUTTON/CMFCColorButton::SetColumnsNumber
- AFXCOLORBUTTON/CMFCColorButton::SetDocumentColors
- AFXCOLORBUTTON/CMFCColorButton::SetPalette
- AFXCOLORBUTTON/CMFCColorButton::SizeToContent
- AFXCOLORBUTTON/CMFCColorButton::IsDrawXPTheme
- AFXCOLORBUTTON/CMFCColorButton::OnDraw
- AFXCOLORBUTTON/CMFCColorButton::OnDrawBorder
- AFXCOLORBUTTON/CMFCColorButton::OnDrawFocusRect
- AFXCOLORBUTTON/CMFCColorButton::OnShowColorPopup
- AFXCOLORBUTTON/CMFCColorButton::RebuildPalette
- AFXCOLORBUTTON/CMFCColorButton::UpdateColor
- AFXCOLORBUTTON/CMFCColorButton::m_bEnabledInCustomizeMode
helpviewer_keywords:
- CMFCColorButton [MFC], CMFCColorButton
- CMFCColorButton [MFC], EnableAutomaticButton
- CMFCColorButton [MFC], EnableOtherButton
- CMFCColorButton [MFC], GetAutomaticColor
- CMFCColorButton [MFC], GetColor
- CMFCColorButton [MFC], SetColor
- CMFCColorButton [MFC], SetColorName
- CMFCColorButton [MFC], SetColumnsNumber
- CMFCColorButton [MFC], SetDocumentColors
- CMFCColorButton [MFC], SetPalette
- CMFCColorButton [MFC], SizeToContent
- CMFCColorButton [MFC], IsDrawXPTheme
- CMFCColorButton [MFC], OnDraw
- CMFCColorButton [MFC], OnDrawBorder
- CMFCColorButton [MFC], OnDrawFocusRect
- CMFCColorButton [MFC], OnShowColorPopup
- CMFCColorButton [MFC], RebuildPalette
- CMFCColorButton [MFC], UpdateColor
- CMFCColorButton [MFC], m_bEnabledInCustomizeMode
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
ms.openlocfilehash: 7abe37969799d7fcd78d525a5ec1c6faa9d876ee
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561002"
---
# <a name="cmfccolorbutton-class"></a>Класс Кмфкколорбуттон

`CMFCColorButton`Классы [классов и кмфкколорбар](../../mfc/reference/cmfccolorbar-class.md) используются совместно для реализации элемента управления "Выбор цвета".

## <a name="syntax"></a>Синтаксис

```
class CMFCColorButton : public CMFCButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кмфкколорбуттон:: Кмфкколорбуттон](#cmfccolorbutton)|Создает новый объект `CMFCColorButton`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кмфкколорбуттон:: Енаблеаутоматикбуттон](#enableautomaticbutton)|Включает и отключает кнопку "автоматически", расположенную над обычными кнопками цвета. (Стандартная системная автоматическая кнопка помечена как **Автоматическая**.)|
|[Кмфкколорбуттон:: Енаблеосербуттон](#enableotherbutton)|Включает и отключает кнопку "другое", расположенную под обычными кнопками цвета. (Стандартная системная кнопка "Other" помечена **дополнительными цветами**.)|
|[Кмфкколорбуттон:: Жетаутоматикколор](#getautomaticcolor)|Извлекает текущий автоматический цвет.|
|[Кмфкколорбуттон:: "Color"](#getcolor)|Извлекает цвет кнопки.|
|[Кмфкколорбуттон:: Сетколор](#setcolor)|Задает цвет кнопки.|
|[Кмфкколорбуттон:: Сетколорнаме](#setcolorname)|Задает имя цвета.|
|[Кмфкколорбуттон:: Сетколумнснумбер](#setcolumnsnumber)|Задает число столбцов в диалоговом окне «Палитра цветов».|
|[Кмфкколорбуттон:: Сетдокументколорс](#setdocumentcolors)|Задает список цветов для конкретного документа, отображаемых в диалоговом окне Палитра цветов.|
|[Кмфкколорбуттон:: Сетпалетте](#setpalette)|Задает палитру стандартных цветов дисплея.|
|[Кмфкколорбуттон:: SizeToContent](#sizetocontent)|Изменяет размер элемента управления "Кнопка" в зависимости от размера текста и изображения.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[Кмфкколорбуттон:: Исдравкспсеме](#isdrawxptheme)|Указывает, отображается ли кнопка текущего цвета в визуальном стиле Windows XP.|
|[Кмфкколорбуттон:: OnDraw](#ondraw)|Вызывается структурой для вывода изображения кнопки.|
|[Кмфкколорбуттон:: Ондравбордер](#ondrawborder)|Вызывается платформой для вывода границы кнопки.|
|[Кмфкколорбуттон:: Ондравфокусрект](#ondrawfocusrect)|Вызывается платформой для вывода прямоугольника фокуса, когда кнопка находится в фокусе.|
|[Кмфкколорбуттон:: Оншовколорпопуп](#onshowcolorpopup)|Вызывается структурой при отображении диалогового окна палитры цветов.|
|[Кмфкколорбуттон:: Ребуилдпалетте](#rebuildpalette)|Инициализирует `m_pPalette` член защищенных данных для указанной палитры или системной палитры по умолчанию.|
|[CMFCColorButton::UpdateColor](#updatecolor)|Вызывается структурой при выборе пользователем цвета из палитры диалогового окна выбора цвета.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|`m_bAltColorDlg`|Логическое значение. Если значение — TRUE, платформа отображает диалоговое окно [кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md) Color при нажатии *другой* кнопки или при значении false в диалоговом окне системный цвет. Значение по умолчанию — TRUE. Дополнительные сведения см. в разделе [кмфкколорбуттон:: енаблеосербуттон](#enableotherbutton).|
|`m_bAutoSetFocus`|Логическое значение. Если значение — TRUE, платформа устанавливает фокус на меню цвета при отображении меню или значение FALSE, если фокус не изменяется. Значение по умолчанию — TRUE.|
|[Кмфкколорбуттон:: m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Указывает, включен ли режим настройки для кнопки цвета.|
|`m_Color`|Значение [COLORREF](/windows/win32/gdi/colorref) . Содержит выбранный в данный момент цвет.|
|`m_ColorAutomatic`|Значение [COLORREF](/windows/win32/gdi/colorref) . Содержит выбранный в данный момент цвет по умолчанию.|
|`m_Colors`|[CArray](../../mfc/reference/carray-class.md) значений [COLORREF](/windows/win32/gdi/colorref) . Содержит доступные в данный момент цвета.|
|`m_lstDocColors`|[CList](../../mfc/reference/clist-class.md) значений [COLORREF](/windows/win32/gdi/colorref) . Содержит текущие цвета документа.|
|`m_nColumns`|Целое число. Содержит число столбцов, отображаемых в сетке цветов в меню выбора цвета.|
|`m_pPalette`|Указатель на [кпалетте](../../mfc/reference/cpalette-class.md). Содержит цвета, доступные в меню выбора текущего цвета.|
|`m_pPopup`|Указатель на объект [класса кмфкколорпопупмену](../../mfc/reference/cmfccolorpopupmenu-class.md) . Меню выбора цвета, которое отображается при нажатии кнопки «цвет».|
|`m_strAutoColorText`|Строка. Метка кнопки "автоматически" в меню выбора цвета.|
|`m_strDocColorsText`|Строка. Метка кнопки в меню выбора цвета, в котором отображаются цвета документа.|
|`m_strOtherText`|Строка. Метка кнопки "другое" в меню выбора цвета.|

## <a name="remarks"></a>Примечания

По умолчанию `CMFCColorButton` класс ведет себя как кнопка, открывающая диалоговое окно выбора цвета. Диалоговое окно Палитра цветов содержит массив мелких цветных кнопок и кнопку "другой", которая отображает настраиваемую палитру цветов. (Стандартная системная кнопка "Other" помечена **дополнительными цветами**.) Когда пользователь выбирает новый цвет, `CMFCColorButton` объект отражает изменение и отображает выбранный цвет.

Создайте элемент управления "Кнопка цвета" непосредственно в коде либо с помощью средства **ClassWizard** и шаблона диалогового окна. При непосредственном создании элемента управления "Кнопка цвета" добавьте в `CMFCColorButton` приложение переменную, а затем вызовите конструктор и `Create` методы `CMFCColorButton` объекта. При использовании **ClassWizard**добавьте `CButton` переменную в приложение, а затем измените тип переменной с `CButton` на `CMFCColorButton` .

Диалоговое окно Палитра цветов ( [класс кмфкколорбар](../../mfc/reference/cmfccolorbar-class.md)) отображается методом [Кмфкколорбуттон:: оншовколорпопуп](#onshowcolorpopup) , когда платформа вызывает `OnLButtonDown` обработчик событий. Метод [кмфкколорбуттон:: оншовколорпопуп](#onshowcolorpopup) можно переопределить для поддержки выбора пользовательского цвета.

`CMFCColorButton`Объект сообщает своему родителю, что изменяется цвет, отправив ему WM_COMMAND | Уведомление BN_CLICKED. Для получения текущего цвета родительский объект использует метод [кмфкколорбуттон:: Color](#getcolor) .

## <a name="example"></a>Пример

В следующем примере показано, как настроить кнопку цвета с помощью различных методов в `CMFCColorButton` классе. Методы задают цвет для кнопки цвета и ее количества столбцов, а также включают автоматические и другие кнопки. Этот пример является частью [демонстрационного примера строки состояния](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** афксколорбуттон.h

## <a name="cmfccolorbuttoncmfccolorbutton"></a><a name="cmfccolorbutton"></a> Кмфкколорбуттон:: Кмфкколорбуттон

Создает новый объект `CMFCColorButton`.

```
CMFCColorButton();
```

## <a name="cmfccolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a> Кмфкколорбуттон:: Енаблеаутоматикбуттон

Включите или отключите кнопку "автоматическое" элемента управления "Выбор цвета" и установите цвет автоматически (по умолчанию).

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*лпсзлабел*<br/>
окне Задает текст для автоматической кнопки.

*колораутоматик*<br/>
окне Значение RGB, указывающее цвет по умолчанию для кнопки автоматически.

*bEnable*<br/>
окне Указывает, включена ли автоматическая кнопка.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a> Кмфкколорбуттон:: Енаблеосербуттон

Включить или отключить кнопку "другие", которая отображается под обычными кнопками цвета.

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*лпсзлабел*<br/>
окне Задает текст кнопки.

*балтколордлг*<br/>
окне Указывает, открывается ли диалоговое окно [кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md) или диалоговое окно системный цвет при нажатии пользователем кнопки.

*bEnable*<br/>
окне Указывает, включена ли или отключена кнопка "другие".

### <a name="remarks"></a>Примечания

Нажмите кнопку "другие", чтобы отобразить диалоговое окно цвета. Если параметр *балтколордлг* имеет значение true, то отображается [класс кмфкколордиалог](../../mfc/reference/cmfccolordialog-class.md) . в противном случае отображается диалоговое окно системный цвет.

## <a name="cmfccolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a> Кмфкколорбуттон:: Жетаутоматикколор

Извлекает текущий автоматически цвет (по умолчанию).

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение RGB, представляющее текущий автоматический цвет.

### <a name="remarks"></a>Примечания

Текущий автоматический цвет задается методом [кмфкколорбуттон:: енаблеаутоматикбуттон](#enableautomaticbutton) .

## <a name="cmfccolorbuttongetcolor"></a><a name="getcolor"></a> Кмфкколорбуттон:: "Color"

Извлекает выбранный в данный момент цвет.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение RGB.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorbuttonisdrawxptheme"></a><a name="isdrawxptheme"></a> Кмфкколорбуттон:: Исдравкспсеме

Указывает, отображается ли кнопка текущего цвета в визуальном стиле Windows XP.

```
BOOL IsDrawXPTheme() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если стили оформления поддерживаются и кнопка текущего цвета отображается в визуальном стиле Windows XP; в противном случае — значение FALSE.

## <a name="cmfccolorbuttonm_benabledincustomizemode"></a><a name="m_benabledincustomizemode"></a> Кмфкколорбуттон:: m_bEnabledInCustomizeMode

Задает кнопку цвета в режиме настройки.

```
BOOL m_bEnabledInCustomizeMode;
```

### <a name="remarks"></a>Примечания

Если необходимо добавить кнопку цвета на страницу диалогового окна настройки (или разрешить пользователю выбирать другой цвет во время настройки), включите эту кнопку, установив `m_bEnabledInCustomizeMode` для элемента значение true. По умолчанию для этого элемента задано значение FALSE.

## <a name="cmfccolorbuttonondraw"></a><a name="ondraw"></a> Кмфкколорбуттон:: OnDraw

Вызывается платформой для отрисовки изображения кнопки.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
окне Указывает на контекст устройства, используемый для отрисовки изображения кнопки.

*rect*<br/>
окне Прямоугольник, ограничивающий кнопку.

*уистате*<br/>
окне Задает визуальное состояние кнопки.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы настроить процесс отрисовки.

## <a name="cmfccolorbuttonondrawborder"></a><a name="ondrawborder"></a> Кмфкколорбуттон:: Ондравбордер

Вызывается структурой для вывода границы кнопки.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
окне Указывает на контекст устройства, используемый для рисования границы.

*ректклиент*<br/>
окне Прямоугольник в контексте устройства, заданный параметром *PDC* , который определяет границы рисуемой кнопки.

*уистате*<br/>
окне Задает визуальное состояние кнопки.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы настроить внешний вид цветовой границы кнопки цвета.

## <a name="cmfccolorbuttonondrawfocusrect"></a><a name="ondrawfocusrect"></a> Кмфкколорбуттон:: Ондравфокусрект

Вызывается платформой для вывода прямоугольника фокуса, когда кнопка находится в фокусе.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
окне Указывает на контекст устройства, используемый для рисования прямоугольника фокуса.

*ректклиент*<br/>
окне Прямоугольник в контексте устройства, определяемый параметром *PDC* , который определяет границы кнопки.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы настроить внешний вид прямоугольника фокуса.

## <a name="cmfccolorbuttononshowcolorpopup"></a><a name="onshowcolorpopup"></a> Кмфкколорбуттон:: Оншовколорпопуп

Вызывается перед отображением цветовой полосы всплывающего окна.

```
virtual void OnShowColorPopup();
```

### <a name="remarks"></a>Примечания

## <a name="cmfccolorbuttonrebuildpalette"></a><a name="rebuildpalette"></a> Кмфкколорбуттон:: Ребуилдпалетте

Инициализирует `m_pPalette` член защищенных данных для указанной палитры или системной палитры по умолчанию.

```cpp
void RebuildPalette(CPalette* pPal);
```

### <a name="parameters"></a>Параметры

*ппал*\
окне Указатель на логическую палитру или значение NULL. Если значение равно NULL, используется системная палитра по умолчанию.

## <a name="cmfccolorbuttonsetcolor"></a><a name="setcolor"></a> Кмфкколорбуттон:: Сетколор

Задает цвет кнопки.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*color*<br/>
окне Значение RGB.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorbuttonsetcolorname"></a><a name="setcolorname"></a> Кмфкколорбуттон:: Сетколорнаме

Задает имя цвета.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Параметры

*color*<br/>
окне Значение RGB цвета.

*strName*<br/>
окне Имя цвета.

### <a name="remarks"></a>Примечания

Список имен цветов является глобальным для каждого приложения. Следовательно, этот метод передает свои параметры в [кмфкколорбар:: сетколорнаме](../../mfc/reference/cmfccolorbar-class.md#setcolorname).

## <a name="cmfccolorbuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a> Кмфкколорбуттон:: Сетколумнснумбер

Определяет количество столбцов, отображаемых в таблице цветов, которые отображаются для пользователя во время процесса выбора цвета пользователем.

```cpp
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Параметры

*nColumns*<br/>
окне Указывает количество столбцов.

### <a name="remarks"></a>Примечания

Пользователь может выбрать цвет из всплывающей цветовой панели, которая отображает таблицу предопределенных цветов. Этот метод используется для определения количества столбцов в таблице.

## <a name="cmfccolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a> Кмфкколорбуттон:: Сетдокументколорс

Задает набор цветов и имя набора. Набор цветов отображается с помощью объекта [класса кмфкколорбар](../../mfc/reference/cmfccolorbar-class.md) .

```cpp
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Параметры

*лпсзлабел*<br/>
окне Указывает метку, отображаемую с набором цветов документа.

*лстколорс*<br/>
окне Ссылка на список значений RGB.

### <a name="remarks"></a>Примечания

`CMFCColorButton`Объект содержит список значений RGB, которые передаются в объект [класса кмфкколорбар](../../mfc/reference/cmfccolorbar-class.md) . При отображении цветовой панели эти цвета отображаются в специальном разделе, метка которого указана параметром *лпсзлабел* .

## <a name="cmfccolorbuttonsetpalette"></a><a name="setpalette"></a> Кмфкколорбуттон:: Сетпалетте

Задает стандартные цвета, отображаемые во всплывающей цветовой панели.

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Параметры

*ппалетте*<br/>
окне Указатель на цветовую палитру.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorbuttonsizetocontent"></a><a name="sizetocontent"></a> Кмфкколорбуттон:: SizeToContent

Изменяет размер элемента управления "Кнопка" в соответствии с текстом и изображением.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Параметры

*бкалконли*<br/>
окне Если значение не равно нулю, то новый размер элемента управления "Кнопка" вычисляется, но фактический размер не изменяется.

### <a name="return-value"></a>Возвращаемое значение

`CSize`Объект, указывающий новый размер элемента управления "Кнопка".

### <a name="remarks"></a>Примечания

## <a name="cmfccolorbuttonupdatecolor"></a><a name="updatecolor"></a> Кмфкколорбуттон:: Упдатеколор

Вызывается структурой, когда пользователь выбирает цвет из цветовой панели, которая отображается, когда пользователь нажимает кнопку цвета.

```
virtual void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*color*<br/>
окне Цвет, выбранный пользователем.

### <a name="remarks"></a>Примечания

`UpdateColor`Функция изменяет цвет выбранной в данный момент кнопки и уведомляет ее родителя, отправляя WM_COMMAND сообщение с BN_CLICKED стандартным уведомлением. Чтобы получить выбранный цвет, используйте метод [кмфкколорбуттон::](#getcolor) WebMethod.

## <a name="see-also"></a>См. также

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс Кмфкбуттон](../../mfc/reference/cmfcbutton-class.md)<br/>
[Класс Кмфкколорбар](../../mfc/reference/cmfccolorbar-class.md)<br/>
[Кмфкколорбуттон:: Оншовколорпопуп](#onshowcolorpopup)<br/>
[COLORREF](/windows/win32/gdi/colorref)<br/>
[Класс Кпалетте](../../mfc/reference/cpalette-class.md)<br/>
[Класс CArray](../../mfc/reference/carray-class.md)<br/>
[Класс CList](../../mfc/reference/clist-class.md)<br/>
[CString](../../atl-mfc-shared/reference/cstringt-class.md)
