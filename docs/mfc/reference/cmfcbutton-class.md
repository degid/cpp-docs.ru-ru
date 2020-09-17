---
title: Класс CMFCButton
ms.date: 08/28/2018
f1_keywords:
- CMFCButton
- AFXBUTTON/CMFCButton
- AFXBUTTON/CMFCButton::CleanUp
- AFXBUTTON/CMFCButton::EnableFullTextTooltip
- AFXBUTTON/CMFCButton::EnableMenuFont
- AFXBUTTON/CMFCButton::EnableWindowsTheming
- AFXBUTTON/CMFCButton::GetToolTipCtrl
- AFXBUTTON/CMFCButton::IsAutoCheck
- AFXBUTTON/CMFCButton::IsAutorepeatCommandMode
- AFXBUTTON/CMFCButton::IsCheckBox
- AFXBUTTON/CMFCButton::IsChecked
- AFXBUTTON/CMFCButton::IsHighlighted
- AFXBUTTON/CMFCButton::IsPressed
- AFXBUTTON/CMFCButton::IsPushed
- AFXBUTTON/CMFCButton::IsRadioButton
- AFXBUTTON/CMFCButton::IsWindowsThemingEnabled
- AFXBUTTON/CMFCButton::SetAutorepeatMode
- AFXBUTTON/CMFCButton::SetCheckedImage
- AFXBUTTON/CMFCButton::SetFaceColor
- AFXBUTTON/CMFCButton::SetImage
- AFXBUTTON/CMFCButton::SetMouseCursor
- AFXBUTTON/CMFCButton::SetMouseCursorHand
- AFXBUTTON/CMFCButton::SetStdImage
- AFXBUTTON/CMFCButton::SetTextColor
- AFXBUTTON/CMFCButton::SetTextHotColor
- AFXBUTTON/CMFCButton::SetTooltip
- AFXBUTTON/CMFCButton::SizeToContent
- AFXBUTTON/CMFCButton::OnDraw
- AFXBUTTON/CMFCButton::OnDrawBorder
- AFXBUTTON/CMFCButton::OnDrawFocusRect
- AFXBUTTON/CMFCButton::OnDrawText
- AFXBUTTON/CMFCButton::OnFillBackground
- AFXBUTTON/CMFCButton::SelectFont
- AFXBUTTON/CMFCButton::m_bDrawFocus
- AFXBUTTON/CMFCButton::m_bHighlightChecked
- AFXBUTTON/CMFCButton::m_bRightImage
- AFXBUTTON/CMFCButton::m_bTransparent
- AFXBUTTON/CMFCButton::m_nAlignStyle
- AFXBUTTON/CMFCButton::m_nFlatStyle
helpviewer_keywords:
- CMFCButton [MFC], CleanUp
- CMFCButton [MFC], EnableFullTextTooltip
- CMFCButton [MFC], EnableMenuFont
- CMFCButton [MFC], EnableWindowsTheming
- CMFCButton [MFC], GetToolTipCtrl
- CMFCButton [MFC], IsAutoCheck
- CMFCButton [MFC], IsAutorepeatCommandMode
- CMFCButton [MFC], IsCheckBox
- CMFCButton [MFC], IsChecked
- CMFCButton [MFC], IsHighlighted
- CMFCButton [MFC], IsPressed
- CMFCButton [MFC], IsPushed
- CMFCButton [MFC], IsRadioButton
- CMFCButton [MFC], IsWindowsThemingEnabled
- CMFCButton [MFC], SetAutorepeatMode
- CMFCButton [MFC], SetCheckedImage
- CMFCButton [MFC], SetFaceColor
- CMFCButton [MFC], SetImage
- CMFCButton [MFC], SetMouseCursor
- CMFCButton [MFC], SetMouseCursorHand
- CMFCButton [MFC], SetStdImage
- CMFCButton [MFC], SetTextColor
- CMFCButton [MFC], SetTextHotColor
- CMFCButton [MFC], SetTooltip
- CMFCButton [MFC], SizeToContent
- CMFCButton [MFC], OnDraw
- CMFCButton [MFC], OnDrawBorder
- CMFCButton [MFC], OnDrawFocusRect
- CMFCButton [MFC], OnDrawText
- CMFCButton [MFC], OnFillBackground
- CMFCButton [MFC], SelectFont
- CMFCButton [MFC], m_bDrawFocus
- CMFCButton [MFC], m_bHighlightChecked
- CMFCButton [MFC], m_bRightImage
- CMFCButton [MFC], m_bTransparent
- CMFCButton [MFC], m_nAlignStyle
- CMFCButton [MFC], m_nFlatStyle
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
ms.openlocfilehash: e949feaaac3570e1518cfb488cc1c42a471a1c46
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754869"
---
# <a name="cmfcbutton-class"></a>Класс CMFCButton

Класс `CMFCButton` добавляет функциональность к классу [CButton,](../../mfc/reference/cbutton-class.md) например, выравнивание текста кнопки, объединение текста кнопки и изображения, выбор курсора и указание наконечника инструмента.

## <a name="syntax"></a>Синтаксис

```
class CMFCButton : public CButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCButton::CMFCButton`|Конструктор по умолчанию.|
|`CMFCButton::~CMFCButton`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCButton::Очистка](#cleanup)|Сброс внутренних переменных и освобождает выделенные ресурсы, такие как изображения, бит-карты и значки.|
|`CMFCButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCButton::DrawItem`|Вызывается в рамках, когда визуальный аспект нарисованной владельцем кнопки изменился. (Переопределяет [CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem).)|
|[CMFCButton:EnableFullTextTooltip](#enablefulltexttooltip)|Определяет, следует ли отображать полный текст инструментария в большом окне tooltip или усеченной версии текста в небольшом окне tooltip.|
|[CMFC Кнопка::EnableMenuFont](#enablemenufont)|Уточняется, является ли шрифт текста кнопки таким же, как шрифт меню приложения.|
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|Уточняется, соответствует ли стиль границы кнопок текущей теме Windows.|
|`CMFCButton::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCКнопка::GetToolTipCtrl](#gettooltipctrl)|Возвращает ссылку на базовый элемент управления набором инструментов.|
|[CMFCButton::IsAutoCheck](#isautocheck)|Указывает, является ли флажок или радиокнопка автоматической кнопкой.|
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|Указывает, настроена ли кнопка в режим автоматического повторения.|
|[CMFCButton::IsCheckBox](#ischeckbox)|Указывает, является ли кнопка кнопкой флажка.|
|[CMFCButton::Проверено](#ischecked)|Указывает, проверяется ли текущая кнопка.|
|[CMFCКнопка::Изумя](#ishighlighted)|Указывает, выделена ли кнопка.|
|[CMFCButton::Ispressed](#ispressed)|Указывает, нажата ли кнопка и выделена.|
|[CMFCButton::Ispushed](#ispushed)|Указывает, нажата ли кнопка.|
|[CMFCButton::IsRadioButton](#isradiobutton)|Указывает, является ли кнопка радиокнопкой.|
|[CMFCButton::IsWindowsTheming](#iswindowsthemingenabled)|Указывает, соответствует ли стиль границы кнопок текущей теме Windows.|
|`CMFCButton::OnDrawParentBackground`|Рисует фон родительской кнопки в указанной области. (Овердионные [AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|
|`CMFCButton::PreTranslateMessage`|Переводит оконные сообщения перед отправкой на функции [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|Устанавливает кнопку в режиме автоматического повторения.|
|[CMFCButton::SetCheckedImage](#setcheckedimage)|Устанавливает изображение для проверенной кнопки.|
|[CMFC Кнопка::SetFaceColor](#setfacecolor)|Устанавливает цвет фона для текста кнопки.|
|[CMFCButton::SetImage](#setimage)|Устанавливает изображение для кнопки.|
|[CMFCКнопка::SetMouseCursor](#setmousecursor)|Устанавливает изображение курсора.|
|[CMFCКнопка::SetMouseCursorHand](#setmousecursorhand)|Устанавливает курсор на изображение руки.|
|[CMFCButton::SetStdImage](#setstdimage)|Использует `CMenuImages` объект для установки изображения кнопки.|
|[CMFCButton::SetTextColor](#settextcolor)|Устанавливает цвет текста кнопки для кнопки, которая не выбрана.|
|[CMFCButton::SetTextHotColor](#settexthotcolor)|Устанавливает цвет текста кнопки для выбранной кнопки.|
|[CMFCButton::SetTooltip](#settooltip)|Ассоциирует инструмент с кнопкой.|
|[CMFC Кнопка::SizetoContent](#sizetocontent)|Изображка кнопки, чтобы содержать текст кнопки и изображение.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFC Кнопка::OnDraw](#ondraw)|Вызывается по фрейму, чтобы нарисовать кнопку.|
|[CMFCButton::OndrawBorder](#ondrawborder)|Вызывается рамки, чтобы нарисовать границу кнопки.|
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|Вызывается рамки, чтобы нарисовать прямоугольник фокусировки для кнопки.|
|[CMFC Button::OndrawText](#ondrawtext)|Вызывается по фреймворку, чтобы нарисовать текст кнопки.|
|[CMFCButton::OnFillbackground](#onfillbackground)|Вызывается рамки, чтобы нарисовать фон текста кнопки.|
|[CMFCButton::SelectFont](#selectfont)|Извлекает шрифт, связанный с указанным контекстом устройства.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|Определяет выравнивание текста кнопки.|
|[CMFCButton::m_bDontUseWinXPTheme](#m_bDontUseWinXPTheme)|Уточняется, следует ли использовать темы Windows XP.|
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|Указывает, следует ли нарисовать прямоугольник фокусировки вокруг кнопки.|
|[CMFCКнопка::m_nFlatStyle](#m_nflatstyle)|Определяет стиль кнопки, такой как безграничный, плоский, полуплоский или 3D.|
|[CMFCКнопка::m_bGrayDisabled](#m_bGrayDisabled)|Когда TRUE, позволяет отключенкнопка будет обращена как серый из.|
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|Указывается, следует ли выделить кнопку в стиле BS_CHECKBOX, когда курсор парит над ней.|
|[CMFCButton::m_bResponseOnButtonDown](#m_bResponseOnButtonDown)|Указывает, следует ли реагировать на события спугивая кнопки.|
|[CMFCButton::m_bRightImage](#m_brightimage)|Указывает, следует ли отображать изображение на правой стороне кнопки.|
|[CMFCButton::m_bTopImage](#m_bTopImage)| Указывает, находится ли изображение в верхней части кнопки.|
|[CMFCКнопка::m_bTransparent](#m_btransparent)|Указывает, является ли кнопка прозрачной.|
|[CMFCButton::m_bWasDblClk](#m_bWasDblClk)| Указывает, было ли последнее событие щелчка двойным щелчком мыши.|

## <a name="remarks"></a>Примечания

Другие типы кнопок `CMFCButton` получены из класса, такие как класс [CMFCURLLinkButton,](../../mfc/reference/cmfclinkctrl-class.md) который поддерживает гиперссылки, и `CMFCColorButton` класс, который поддерживает поле диалога сборщика цветов.

`CMFCButton` Стиль объекта может быть *3D,* *плоский,* *полуплоский* или *без границы.* Текст кнопки может быть выровнен слева, сверху или в центре кнопки. Во время выполнения, вы можете контролировать ли кнопка отображает текст, изображение, или текст и изображение. Вы также можете указать, что определенное изображение курсора отображается, когда курсор парит над кнопкой.

Создайте управление кнопками либо непосредственно в коде, либо с помощью инструмента **MFC Class Wizard** и шаблона диалогового окна. Если вы создаете кнопку `CMFCButton` управления непосредственно, добавить переменную в `Create` приложение, `CMFCButton` а затем вызвать конструктор и методы объекта. Если вы используете **Мастер класса MFC,** добавьте переменную `CButton` в приложение, `CButton` `CMFCButton`а затем измените тип переменной с к .

Для обработки сообщений уведомлений в приложении диалогового окна добавьте запись на карту сообщений и обработчик событий для каждого уведомления. Уведомления, отправленные `CMFCButton` объектом, такие же, `CButton` как и уведомления, отправленные объектом.

## <a name="example"></a>Пример

В следующем примере показано, как настроить свойства кнопки `CMFCButton` с помощью различных методов в классе. Пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxbutton.h

## <a name="cmfcbuttoncleanup"></a><a name="cleanup"></a>CMFCButton::Очистка

Сброс внутренних переменных и освобождает выделенные ресурсы, такие как изображения, бит-карты и значки.

```
virtual void CleanUp();
```

## <a name="cmfcbuttonenablefulltexttooltip"></a><a name="enablefulltexttooltip"></a>CMFCButton:EnableFullTextTooltip

Определяет, следует ли отображать полный текст инструментария в большом окне tooltip или усеченной версии текста в небольшом окне tooltip.

```cpp
void EnableFullTextTooltip(BOOL bOn=TRUE);
```

### <a name="parameters"></a>Параметры

*Бон*<br/>
(в) TRUE для отображения всего текста; FALSE для отображения усеченного текста.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonenablemenufont"></a><a name="enablemenufont"></a>CMFC Кнопка::EnableMenuFont

Уточняется, является ли шрифт текста кнопки таким же, как шрифт меню приложения.

```cpp
void EnableMenuFont(
    BOOL bOn=TRUE,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Параметры

*Бон*<br/>
(в) TRUE использовать шрифт меню приложения в качестве шрифта текста кнопки; FALSE для использования системного шрифта. Значение по умолчанию — TRUE.

*bRedraw*<br/>
(в) TRUE немедленно перерисовать экран; в противном случае, FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Если вы не используете этот метод для указания шрифта текста кнопки, можно указать шрифт с помощью [cWnd::SetFont.](../../mfc/reference/cwnd-class.md#setfont) Если вы вообще не указали шрифт, в фреймворке устанавливается шрифт по умолчанию.

## <a name="cmfcbuttonenablewindowstheming"></a><a name="enablewindowstheming"></a>CMFCButton::EnableWindowsTheming

Уточняется, соответствует ли стиль границы кнопок текущей теме Windows.

```
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE использовать текущую тему Windows, чтобы нарисовать границы кнопок; FALSE, чтобы не использовать тему Windows. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Этот метод влияет на все кнопки в приложении, которые являются производными `CMFCButton` от класса.

## <a name="cmfcbuttongettooltipctrl"></a><a name="gettooltipctrl"></a>CMFCКнопка::GetToolTipCtrl

Возвращает ссылку на базовый элемент управления набором инструментов.

```
CToolTipCtrl& GetToolTipCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на базовый элемент управления набором инструментов.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonisautocheck"></a><a name="isautocheck"></a>CMFCButton::IsAutoCheck

Указывает, является ли флажок или радиокнопка автоматической кнопкой.

```
BOOL IsAutoCheck() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если кнопка имеет стиль BS_AUTOCHECKBOX или BS_AUTORADIOBUTTON; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonisautorepeatcommandmode"></a><a name="isautorepeatcommandmode"></a>CMFCButton::IsAutorepeatCommandMode

Указывает, настроена ли кнопка в режим автоматического повторения.

```
BOOL IsAutorepeatCommandMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если кнопка настроена в режим автоматического повторения; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Используйте метод [CMFCButton::SetAutorepeatMode](#setautorepeatmode) для установки кнопки в режим автоматического повтора.

## <a name="cmfcbuttonischeckbox"></a><a name="ischeckbox"></a>CMFCButton::IsCheckBox

Указывает, является ли кнопка кнопкой флажка.

```
BOOL IsCheckBox() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если кнопка имеет либо BS_CHECKBOX или BS_AUTOCHECKBOX стиль; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonischecked"></a><a name="ischecked"></a>CMFCButton::Проверено

Указывает, проверяется ли текущая кнопка.

```
BOOL IsChecked() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если текущая кнопка проверена; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

В фреймворке используются различные способы указания на проверку различных видов кнопок. Например, радиокнопка проверяется, когда она содержит точку; флажок проверяется, когда он содержит **X**.

## <a name="cmfcbuttonishighlighted"></a><a name="ishighlighted"></a>CMFCКнопка::Изумя

Указывает, выделена ли кнопка.

```
BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если кнопка выделена; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Кнопка становится выделенной, когда мышь парит над кнопкой.

## <a name="cmfcbuttonispressed"></a><a name="ispressed"></a>CMFCButton::Ispressed

Указывает, нажата ли кнопка и выделена.

```
BOOL IsPressed() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если кнопка нажата; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonispushed"></a><a name="ispushed"></a>CMFCButton::Ispushed

Указывает, нажата ли кнопка.

```
BOOL IsPushed() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если кнопка нажата; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonisradiobutton"></a><a name="isradiobutton"></a>CMFCButton::IsRadioButton

Указывает, является ли кнопка радиокнопкой.

```
BOOL IsRadioButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если стиль кнопки BS_RADIOBUTTON или BS_AUTORADIOBUTTON; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttoniswindowsthemingenabled"></a><a name="iswindowsthemingenabled"></a>CMFCButton::IsWindowsTheming

Указывает, соответствует ли стиль границы кнопок текущей теме Windows.

```
static BOOL IsWindowsThemingEnabled();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если стиль границы кнопки соответствует текущей теме Windows; в противном случае, FALSE.

## <a name="cmfcbuttonm_bdontusewinxptheme"></a><a name="m_bDontUseWinXPTheme"/>CMFCButton::m_bDontUseWinXPTheme

Уточняется, следует ли использовать темы Windows XP при рисовании кнопки.

```
BOOL m_bDontUseWinXPTheme;
```

## <a name="cmfcbuttonm_bdrawfocus"></a><a name="m_bdrawfocus"></a>CMFCButton::m_bDrawFocus

Указывает, следует ли нарисовать прямоугольник фокусировки вокруг кнопки.

```
BOOL m_bDrawFocus;
```

### <a name="remarks"></a>Примечания

Установите `m_bDrawFocus` участника TRUE, чтобы указать, что фреймворк нарисует прямоугольник фокусировки вокруг текста и изображения кнопки, если кнопка получит фокус.

Конструктор `CMFCButton` инициализирует этот член к TRUE.

## <a name="cmfcbuttonm_bgraydisabled"></a><a name="m_bGrayDisabled"></a>CMFCКнопка::m_bGrayDisabled

Когда TRUE, позволяет отключенкнопка будет обращена как серый из.

```
BOOL m_bGrayDisabled;
```

## <a name="cmfcbuttonm_bhighlightchecked"></a><a name="m_bhighlightchecked"></a>CMFCButton::m_bHighlightChecked

Указывается, следует ли выделить кнопку в стиле BS_CHECKBOX, когда курсор парит над ней.

```
BOOL m_bHighlightChecked;
```

### <a name="remarks"></a>Примечания

Установите `m_bHighlightChecked` участника TRUE, чтобы указать, что фреймворк выделит кнопку в стиле BS_CHECKBOX, когда мышь парит над ней.

## <a name="cmfcbuttonm_bresponseonbuttondown"></a><a name="m_bResponseOnButtonDown"></a>CMFCButton::m_bResponseOnButtonDown

Указывает, следует ли реагировать на события спугивая кнопки.

```
BOOL m_bResponseOnButtonDown;
```

## <a name="cmfcbuttonm_brightimage"></a><a name="m_brightimage"></a>CMFCButton::m_bRightImage

Указывает, следует ли отображать изображение на правой стороне кнопки.

```
BOOL m_bRightImage;
```

## <a name="cmfcbuttonm_btopimagem_btopimage"></a><a name="m_bTopImage"></a>CMFCButton::m_bTopImage(#m_bTopImage)

Указывает, находится ли изображение в верхней части кнопки.

```
BOOL m_bTopImage;
```

### <a name="remarks"></a>Примечания

Установите `m_bRightImage` член утвердить, что фреймворк будет отображать изображение кнопки справа от текстовой метки кнопки.

## <a name="cmfcbuttonm_btransparent"></a><a name="m_btransparent"></a>CMFCКнопка::m_bTransparent

Указывает, является ли кнопка прозрачной.

```
BOOL m_bTransparent;
```

### <a name="remarks"></a>Примечания

Установите `m_bTransparent` участника TRUE, чтобы указать, что фреймворк сделает кнопку прозрачной. Конструктор `CMFCButton` инициализирует этот член на FALSE.

## <a name="cmfcbuttonm_nalignstyle"></a><a name="m_nalignstyle"></a>CMFCButton::m_nAlignStyle

Определяет выравнивание текста кнопки.

```
AlignStyle m_nAlignStyle;
```

### <a name="remarks"></a>Примечания

Используйте одно `CMFCButton::AlignStyle` из следующих значений перечисления для указания выравнивания текста кнопки:

|Значение|Описание|
|-----------|-----------------|
|ALIGN_CENTER|(По умолчанию) Выравнивает текст кнопки к центру кнопки.|
|ALIGN_LEFT|Выравнивает текст кнопки с левой стороны кнопки.|
|ALIGN_RIGHT|Выравнивает текст кнопки с правой стороны кнопки.|

Конструктор `CMFCButton` инициализирует этот член для ALIGN_CENTER.

## <a name="cmfcbuttonm_bwasdblclkm_bwasdblclk"></a><a name="m_bWasDblClk"></a>CMFCButton::m_bWasDblClk (#m_bWasDblClk)

Указывает, было ли последнее событие щелчка двойным щелчком мыши.

```
BOOL m_bWasDblClk;
```

## <a name="cmfcbuttonm_nflatstyle"></a><a name="m_nflatstyle"></a>CMFCКнопка::m_nFlatStyle

Определяет стиль кнопки, такой как безграничный, плоский, полуплоский или 3D.

```
FlatStyle  m_nFlatStyle;
```

### <a name="remarks"></a>Примечания

В следующей `CMFCButton::m_nFlatStyle` таблице перечислены значения перечисления, которые определяют внешний вид кнопки.

|Значение|Описание|
|-----------|-----------------|
|BUTTONSTYLE_3D|(По умолчанию) Кнопка, как представляется, имеют высокие, трехмерные стороны. При нажатии кнопки кнопка, как представляется, нажата в глубокий отступ.|
|BUTTONSTYLE_FLAT|Когда мышь не останавливается над кнопкой, кнопка оказывается двумерной и не имеет поднятых сторон. Когда мышь останавливается над кнопкой, кнопка, кажется, имеет низкие, трехмерные стороны. При нажатии кнопки кнопка, как представляется, нажата в неглубокий отступ.|
|BUTTONSTYLE_SEMIFLAT|Кнопка, как представляется, имеют низкие, трехмерные стороны. При нажатии кнопки кнопка, как представляется, нажата в глубокий отступ.|
|BUTTONSTYLE_NOBORDERS|Кнопка не имеет поднятых сторон и всегда отображается двумерной. Кнопка, как представляется, не нажата в отступ при нажатии.|

Конструктор `CMFCButton` инициализирует этот член для BUTTONSTYLE_3D.

### <a name="example"></a>Пример

В следующем примере показано, как установить значения переменной `m_nFlatStyle` члена в `CMFCButton` классе. Этот пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]

## <a name="cmfcbuttonondraw"></a><a name="ondraw"></a>CMFC Кнопка::OnDraw

Вызывается по фрейму, чтобы нарисовать кнопку.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Ссылка на прямоугольник, который граничит с кнопкой.

*uiState*<br/>
(в) Текущее состояние кнопки. Для получения дополнительной `itemState` информации [DRAWITEMSTRUCT Structure](/windows/win32/api/winuser/ns-winuser-drawitemstruct) см.

### <a name="remarks"></a>Примечания

Переувизируйте этот метод, чтобы использовать свой собственный код, чтобы нарисовать кнопку.

## <a name="cmfcbuttonondrawborder"></a><a name="ondrawborder"></a>CMFCButton::OndrawBorder

Вызывается рамки, чтобы нарисовать границу кнопки.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rectClient*<br/>
(в) Ссылка на прямоугольник, который граничит с кнопкой.

*uiState*<br/>
(в) Текущее состояние кнопки. Для получения дополнительной `itemState` информации [DRAWITEMSTRUCT Structure](/windows/win32/api/winuser/ns-winuser-drawitemstruct) см.

### <a name="remarks"></a>Примечания

Переувизируйте этот метод, чтобы использовать свой собственный код для рисования границы.

## <a name="cmfcbuttonondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCButton::OnDrawFocusRect

Вызывается рамки, чтобы нарисовать прямоугольник фокусировки для кнопки.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rectClient*<br/>
(в) Ссылка на прямоугольник, который граничит с кнопкой.

### <a name="remarks"></a>Примечания

Переувизируйте этот метод, чтобы использовать свой собственный код, чтобы нарисовать прямоугольник фокусировки.

## <a name="cmfcbuttonondrawtext"></a><a name="ondrawtext"></a>CMFC Button::OndrawText

Вызывается по фреймворку, чтобы нарисовать текст кнопки.

```
virtual void OnDrawText(
    CDC* pDC,
    const CRect& rect,
    const CString& strText,
    UINT uiDTFlags,
    UINT uiState);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Ссылка на прямоугольник, который граничит с кнопкой.

*strText*<br/>
(в) Текст нарисовать.

*uiDTФлаги*<br/>
(в) Флаги, указывающие, как форматировать текст. Для получения дополнительной *информации* с [:Dм.](../../mfc/reference/cdc-class.md#drawtext)

*uiState*<br/>
[in] Зарезервировано.

### <a name="remarks"></a>Примечания

Переувизируйте этот метод, чтобы использовать свой собственный код для рисования текста кнопки.

## <a name="cmfcbuttononfillbackground"></a><a name="onfillbackground"></a>CMFCButton::OnFillbackground

Вызывается рамки, чтобы нарисовать фон текста кнопки.

```
virtual void OnFillBackground(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rectClient*<br/>
(в) Ссылка на прямоугольник, который граничит с кнопкой.

### <a name="remarks"></a>Примечания

Переувизируйте этот метод, чтобы использовать свой собственный код, чтобы нарисовать фон кнопки.

## <a name="cmfcbuttonselectfont"></a><a name="selectfont"></a>CMFCButton::SelectFont

Извлекает шрифт, связанный с указанным контекстом устройства.

```
virtual CFont* SelectFont(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

### <a name="return-value"></a>Возвращаемое значение

Переувизируйте этот метод, чтобы использовать свой собственный код для извлечения шрифта.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonsetautorepeatmode"></a><a name="setautorepeatmode"></a>CMFCButton::SetAutorepeatMode

Устанавливает кнопку в режиме автоматического повторения.

```cpp
void SetAutorepeatMode(int nTimeDelay=500);
```

### <a name="parameters"></a>Параметры

*nTimeDelay*<br/>
(в) Неотрицательное число, оповещаевщее интервал между сообщениями, отправляемыми в родительское окно. Интервал измеряется в миллисекундах, а его значение по умолчанию составляет 500 миллисекунд. Укажите ноль для автоматического автоматического повторения режима сообщения.

### <a name="remarks"></a>Примечания

Этот метод заставляет кнопку постоянно отправлять сообщения WM_COMMAND в родительское окно до тех пор, пока кнопка не будет выпущена, или параметр *nTimeDelay* будет сведен к нулю.

## <a name="cmfcbuttonsetcheckedimage"></a><a name="setcheckedimage"></a>CMFCButton::SetCheckedImage

Устанавливает изображение для проверенной кнопки.

```cpp
void SetCheckedImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetCheckedImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetCheckedImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
(в) Ручка к значку, которая содержит бит-карту и маску для нового изображения.

*bAutoDestroy*<br/>
(в) TRUE указать, что ресурсы bitmap будут уничтожаться автоматически; в противном случае, FALSE. Значение по умолчанию — TRUE.

*hIconHot*<br/>
(в) Обработка значка, содержащего изображение для выбранного состояния.

*hBitmap*<br/>
(в) Обработка к битной карте, содержащей изображение для невыбранного состояния.

*hBitmapHot*<br/>
(в) Обработка к битной карте, содержащей изображение для выбранного состояния.

*bMap3dЦвета*<br/>
(в) Определяет прозрачный цвет для фона кнопки; то есть, лицо кнопки. TRUE для использования цветового значения RGB (192, 192, 192); FALSE использовать цветовое `AFX_GLOBAL_DATA::clrBtnFace`значение, определяемое .

*uiBmpResId*<br/>
(в) Идентификатор ресурсов для невыбранного изображения.

*uiBmpHotResId*<br/>
(в) Идентификатор ресурсов для выбранного изображения.

*hIconDisabled*<br/>
(в) Ручка к значку для инвалидного изображения.

*hBitmapИнвалид*<br/>
(в) Обработка к битной карте, содержащей отключенное изображение.

*uiBmpDsblResID*<br/>
(в) Идентификатор ресурса отключенной битной карты.

*bAlphaBlend*<br/>
(в) TRUE использовать только 32-битные изображения, которые используют альфа-канал; FALSE, чтобы не использовать только изображения альфа-канала. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonsetfacecolor"></a><a name="setfacecolor"></a>CMFC Кнопка::SetFaceColor

Устанавливает цвет фона для текста кнопки.

```cpp
void SetFaceColor(
    COLORREF crFace,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Параметры

*crFace*<br/>
(в) Значение цвета RGB.

*bRedraw*<br/>
(в) TRUE перерисовать экран немедленно; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы определить новый цвет заполнения для фона кнопки (лицо). Обратите внимание, что фон не заполняется, когда переменная [CMFCButton::m_bTransparent](#m_btransparent) член истины.

## <a name="cmfcbuttonsetimage"></a><a name="setimage"></a>CMFCButton::SetImage

Устанавливает изображение для кнопки.

```cpp
void SetImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
(в) Ручка к значку, которая содержит бит-карту и маску для нового изображения.

*bAutoDestroy*<br/>
(в) TRUE указать, что ресурсы bitmap будут уничтожаться автоматически; в противном случае, FALSE. Значение по умолчанию — TRUE.

*hIconHot*<br/>
(в) Обработка значка, содержащего изображение для выбранного состояния.

*hBitmap*<br/>
(в) Обработка к битной карте, содержащей изображение для невыбранного состояния.

*hBitmapHot*<br/>
(в) Обработка к битной карте, содержащей изображение для выбранного состояния.

*uiBmpResId*<br/>
(в) Идентификатор ресурсов для невыбранного изображения.

*uiBmpHotResId*<br/>
(в) Идентификатор ресурсов для выбранного изображения.

*bMap3dЦвета*<br/>
(в) Определяет прозрачный цвет для фона кнопки; то есть, лицо кнопки. TRUE для использования цветового значения RGB (192, 192, 192); FALSE использовать цветовое `AFX_GLOBAL_DATA::clrBtnFace`значение, определяемое .

*hIconDisabled*<br/>
(в) Ручка к значку для инвалидного изображения.

*hBitmapИнвалид*<br/>
(в) Обработка к битной карте, содержащей отключенное изображение.

*uiBmpDsblResID*<br/>
(в) Идентификатор ресурса отключенной битной карты.

*bAlphaBlend*<br/>
(в) TRUE использовать только 32-битные изображения, которые используют альфа-канал; FALSE, чтобы не использовать только изображения альфа-канала. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

В следующем примере показано, как `SetImage` использовать различные версии метода `CMFCButton` в классе. Пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]

## <a name="cmfcbuttonsetmousecursor"></a><a name="setmousecursor"></a>CMFCКнопка::SetMouseCursor

Устанавливает изображение курсора.

```cpp
void SetMouseCursor(HCURSOR hcursor);
```

### <a name="parameters"></a>Параметры

*hcursor*<br/>
(в) Ручка курсора.

### <a name="remarks"></a>Примечания

Используйте этот метод для ассоциировать изображение курсора, например курсор руки, с кнопкой. Курсор загружается из ресурсов приложения.

### <a name="example"></a>Пример

В следующем примере показано, `SetMouseCursor` как `CMFCButton` использовать метод в классе. Пример является частью кода в [образце new Controls.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]

## <a name="cmfcbuttonsetmousecursorhand"></a><a name="setmousecursorhand"></a>CMFCКнопка::SetMouseCursorHand

Устанавливает курсор на изображение руки.

```cpp
void SetMouseCursorHand();
```

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы связать изображение курсора руки с кнопкой. Курсор загружается из ресурсов приложения.

## <a name="cmfcbuttonsetstdimage"></a><a name="setstdimage"></a>CMFCButton::SetStdImage

Использует `CMenuImages` объект для установки изображения кнопки.

```cpp
void SetStdImage(
    CMenuImages::IMAGES_IDS id,
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
(в) Один из идентификаторов изображений кнопки, который определяется в перечислении. `CMenuImage::IMAGES_IDS` Значения изображения указывают изображения, такие как стрелки, контакты и кнопки радио.

*state*<br/>
(в) Один из идентификаторов состояния `CMenuImages::IMAGE_STATE` состояния кнопок, который определяется в перечислении. Состояния изображения указывают цвета кнопок, такие как черный, серый, светло-серый, белый и темно-серый. Значение по умолчанию — `CMenuImages::ImageBlack`.

*idDisabled*<br/>
(в) Один из идентификаторов изображений кнопки, который определяется в перечислении. `CMenuImage::IMAGES_IDS` Изображение указывает на то, что кнопка отключена. Значение по умолчанию является `CMenuImages::IdArrowDown`первым изображением кнопки ().

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonsettextcolor"></a><a name="settextcolor"></a>CMFCButton::SetTextColor

Устанавливает цвет текста кнопки для кнопки, которая не выбрана.

```cpp
void SetTextColor(COLORREF clrText);
```

### <a name="parameters"></a>Параметры

*clrText*<br/>
(в) Значение цвета RGB.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonsettexthotcolor"></a><a name="settexthotcolor"></a>CMFCButton::SetTextHotColor

Устанавливает цвет текста кнопки для выбранной кнопки.

```cpp
void SetTextHotColor(COLORREF clrTextHot);
```

### <a name="parameters"></a>Параметры

*clrTextHot*<br/>
(в) Значение цвета RGB.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonsettooltip"></a><a name="settooltip"></a>CMFCButton::SetTooltip

Ассоциирует инструмент с кнопкой.

```cpp
void SetTooltip(LPCTSTR lpszToolTipText);
```

### <a name="parameters"></a>Параметры

*lpszToolTipText*<br/>
(в) Указатель на текст для инструментария. Укажите NULL, чтобы отключить инструментарий.

### <a name="remarks"></a>Примечания

## <a name="cmfcbuttonsizetocontent"></a><a name="sizetocontent"></a>CMFC Кнопка::SizetoContent

Изображка кнопки, чтобы содержать текст кнопки и изображение.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Параметры

*bCalcТолько*<br/>
(в) TRUE для расчета, но не изменения нового размера кнопки; FALSE изменить размер кнопки. Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Объект, `CSize` содержащий новый размер кнопки.

### <a name="remarks"></a>Примечания

По умолчанию этот метод вычисляет новый размер, который включает горизонтальный запас в 10 пикселей и вертикальный запас 5 пикселей.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)<br/>
[Класс CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)<br/>
[Класс CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)
