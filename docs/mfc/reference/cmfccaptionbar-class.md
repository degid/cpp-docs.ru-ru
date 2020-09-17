---
title: Класс CMFCCaptionBar
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
helpviewer_keywords:
- CMFCCaptionBar [MFC], Create
- CMFCCaptionBar [MFC], DoesAllowDynInsertBefore
- CMFCCaptionBar [MFC], EnableButton
- CMFCCaptionBar [MFC], GetAlignment
- CMFCCaptionBar [MFC], GetBorderSize
- CMFCCaptionBar [MFC], GetButtonRect
- CMFCCaptionBar [MFC], GetMargin
- CMFCCaptionBar [MFC], IsMessageBarMode
- CMFCCaptionBar [MFC], RemoveBitmap
- CMFCCaptionBar [MFC], RemoveButton
- CMFCCaptionBar [MFC], RemoveIcon
- CMFCCaptionBar [MFC], RemoveText
- CMFCCaptionBar [MFC], SetBitmap
- CMFCCaptionBar [MFC], SetBorderSize
- CMFCCaptionBar [MFC], SetButton
- CMFCCaptionBar [MFC], SetButtonPressed
- CMFCCaptionBar [MFC], SetButtonToolTip
- CMFCCaptionBar [MFC], SetFlatBorder
- CMFCCaptionBar [MFC], SetIcon
- CMFCCaptionBar [MFC], SetImageToolTip
- CMFCCaptionBar [MFC], SetMargin
- CMFCCaptionBar [MFC], SetText
- CMFCCaptionBar [MFC], OnDrawBackground
- CMFCCaptionBar [MFC], OnDrawBorder
- CMFCCaptionBar [MFC], OnDrawButton
- CMFCCaptionBar [MFC], OnDrawImage
- CMFCCaptionBar [MFC], OnDrawText
- CMFCCaptionBar [MFC], m_clrBarBackground
- CMFCCaptionBar [MFC], m_clrBarBorder
- CMFCCaptionBar [MFC], m_clrBarText
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
ms.openlocfilehash: c42b1ccb51a3c290e0887717d900543b8d5b277a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752625"
---
# <a name="cmfccaptionbar-class"></a>Класс CMFCCaptionBar

Объект `CMFCCaptionBar` представляет собой панель управления, которая может отображать три элемента: кнопку, текстовую метку и битную карту. Она может содержать только один элемент каждого типа одновременно. Можно выровнять каждый элемент по левому или правому краю элемента управления или по центру. Также можно применить плоский или трехмерный стиль к верхним и нижним границам заголовка окна.

## <a name="syntax"></a>Синтаксис

```
class CMFCCaptionBar : public CPane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCCaptionBar::Создание](#create)|Создает управление заголовком и прикрепляет его к объекту. `CMFCCaptionBar`|
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Указывает, можно ли динамически вставить другую панель панели подписей и родительский кадр. (Переопределяет [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCCaptionBar::EnableButton](#enablebutton)|Включает или отсваивает кнопку на панели подписей.|
|[CMFCCaptionBar::GetAlignment](#getalignment)|Возвращает выравнивание указанного элемента.|
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|Возвращает размер границы панели подписи.|
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|Извлекает прямоугольник кнопки на панели заголовков.|
|[CMFCCaptionBar::GetMargin](#getmargin)|Возвращает расстояние между краем элементов панели подписи и краем управления панели подписи.|
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|Определяет, находится ли панель подписей в режиме панели сообщений.|
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|Удаляет изображение биткарты из панели заголовков.|
|[CMFCCaptionBar::Удалить кнопку](#removebutton)|Удаляет кнопку из панели заголовков.|
|[CMFCCaptionBar::RemoveIcon](#removeicon)|Удаляет значок из панели подписей.|
|[CMFCCaptionBar::RemoveText](#removetext)|Удаляет текстовую метку из панели заголовков.|
|[CMFCCaptionBar::SetBitmap](#setbitmap)|Устанавливает изображение биткарты для панели подписей.|
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|Устанавливает размер границы панели подписи.|
|[CMFCCaptionBar::SetButton](#setbutton)|Устанавливает кнопку для панели подписей.|
|[CMFCCaptionBar::SetButton](#setbuttonpressed)|Определяет, остается ли кнопка нажатой.|
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|Устанавливает набор инструментов для кнопки.|
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|Устанавливает пограничный стиль панели подписей.|
|[CMFCCaptionBar::SetIcon](#seticon)|Устанавливает значок для панели подписей.|
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|Устанавливает набор инструментов для изображения для панели подписей.|
|[CMFCCaptionBar::SetMargin](#setmargin)|Устанавливает расстояние между краем элемента панели подписи и краем управления панели подписи.|
|[CMFCCaptionBar::SetText](#settext)|Устанавливает текстовую метку для панели подписей.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCCaptionBar::Ondrawbackground](#ondrawbackground)|Вызывается рамки для заполнения фона подписи бар.|
|[CMFCCaptionBar::OndrawBorder](#ondrawborder)|Вызывается рамки, чтобы нарисовать границу подписи бар.|
|[CMFCCaptionBar::OndrawButton](#ondrawbutton)|Вызывается по фреймворку, чтобы нарисовать кнопку заголовок бар.|
|[CMFCCaptionBar::OndrawImage](#ondrawimage)|Вызывается рамки, чтобы нарисовать изображение заголовка бара.|
|[CMFCCaptionBar::OndrawText](#ondrawtext)|Вызывается по фреймворку, чтобы нарисовать текст заголовка бара.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|Цвет фона панели заголовка.|
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|Цвет границы панели подписи.|
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|Цвет текста заголовка бара.|

## <a name="remarks"></a>Примечания

Чтобы создать панель подписей, выполните следующие действия:

1. Постройте `CMFCCaptionBar` объект. Как правило, панель заголовков добавляется в класс окна кадра.

1. Позвоните в [CMFCCaptionBar::Создать](#create) метод для создания управления `CMFCCaptionBar` заголовком и прикрепить его к объекту.

1. Позвоните [CMFCCaptionBar::SetButton](#setbutton), [CMFCCaptionBar::SetText](#settext), [CMFCCaptionBar::SetIcon](#seticon), и [CMFCCaptionBar::SetBitmap](#setbitmap) установить элементы подписи бар.

При установке элемента кнопки необходимо назначить кнопку идентификатор команды. Когда пользователь нажимает на кнопку, панель подписей направляет WM_COMMAND сообщений, которые имеют этот идентификатор, в окно родительской рамы.

Панель подписей также может работать в режиме панели сообщений, которая эмулирует панель сообщений, которая отображается в приложениях Microsoft Office 2007. В режиме панели сообщений панель подписей отображает битную карту, сообщение и кнопку (которая обычно открывает диалоговое окно). Вы можете назначить набор инструментов для бит-карты.

Чтобы включить режим панели сообщений, позвоните [cmFCCaptionBar::Создайте](#create) и установите четвертый параметр (bIsMessageBarMode) в TRUE.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCCaptionBar` . На примере показано, как создать контроль панели подписей, установить 3D-границу панели подписей, установить расстояние, в пикселях, между краем элементов панели заголовка и краем управления заголовком, установить кнопку для панели подписи, установить набор инструментов для кнопки, установить текстовую метку для панели подписи, установить изображение биткарты для панели подписи , и установить набор инструментов для изображения в подписи бар. Этот фрагмент кода является частью [образца MS Office 2007 Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcaptionbar.h

## <a name="cmfccaptionbarcreate"></a><a name="create"></a>CMFCCaptionBar::Создание

Создает управление заголовком и прикрепляет его к объекту. `CMFCCaptionBar`

```
BOOL Create(
    DWORD dwStyle,
    CWnd* pParentWnd,
    UINT uID,
    int nHeight=-1,
    BOOL bIsMessageBarMode=FALSE);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Логическое или сочетание стилей заголовка.

*pParentWnd*<br/>
Родительское окно управления заголовком.

*Uid*<br/>
Id управления заголовком.

*nВысота*<br/>
Высота, в пикселях, управления заголовком. Если это -1, высота рассчитывается в зависимости от высоты значка, текста и кнопки, что управление заголовком подписи отображает.

*bIsMessageBarMode*<br/>
TRUE, если панель подписей находится в режиме панели сообщений; FALSE в противном случае.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если контроль подписи бар создан успешно; FALSE в противном случае.

### <a name="remarks"></a>Примечания

Вы строите `CMFCCaptionBar` объект в два этапа. Сначала вы вызываете конструктор, а `Create` затем вызываете метод, который создает управление `CMFCCaptionBar` Windows и прикрепляет его к объекту.

## <a name="cmfccaptionbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CMFCCaptionBar: :DoesAllowDynInsertBefore

Указывает, можно ли динамически вставить другую панель панели подписей и родительский кадр.

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает FALSE, если не переопределена.

### <a name="remarks"></a>Примечания

## <a name="cmfccaptionbarenablebutton"></a><a name="enablebutton"></a>CMFCCaptionBar::EnableButton

Включает или отсваивает кнопку на панели подписей.

```cpp
void EnableButton(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) ПРАВДА, чтобы включить кнопку, FALSE отключить кнопку.

## <a name="cmfccaptionbargetalignment"></a><a name="getalignment"></a>CMFCCaptionBar::GetAlignment

Возвращает выравнивание указанного элемента.

```
BarElementAlignment GetAlignment(BarElement elem);
```

### <a name="parameters"></a>Параметры

*Elem*<br/>
(в) Элемент заголовка, для которого можно получить выравнивание.

### <a name="return-value"></a>Возвращаемое значение

Выравнивание элемента, например кнопки, битовой карты, текста или значка.

### <a name="remarks"></a>Примечания

Выравнивание элемента может быть одним из следующих значений:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbargetbordersize"></a><a name="getbordersize"></a>CMFCCaptionBar::GetBorderSize

Возвращает размер границы панели подписи.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер границы, в пикселях.

## <a name="cmfccaptionbargetbuttonrect"></a><a name="getbuttonrect"></a>CMFCCaptionBar::GetButtonRect

Извлекает прямоугольник кнопки на панели заголовков.

```
CRect GetButtonRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CRect` содержащий координаты связующего прямоугольника кнопки на панели заголовков.

## <a name="cmfccaptionbargetmargin"></a><a name="getmargin"></a>CMFCCaptionBar::GetMargin

Возвращает расстояние между краем элементов панели подписи и краем управления панели подписи.

```
int GetMargin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Расстояние, в пикселях, между краем элементов панели подписи и краем управления панели подписи.

## <a name="cmfccaptionbarismessagebarmode"></a><a name="ismessagebarmode"></a>CMFCCaptionBar::IsMessageBarMode

Определяет, находится ли панель подписей в режиме панели сообщений.

```
BOOL IsMessageBarMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если панель подписей находится в режиме панели сообщений; FALSE в противном случае.

### <a name="remarks"></a>Примечания

В режиме панели сообщений панель подписей отображает изображение с набором инструментов, текстом сообщения и кнопкой.

## <a name="cmfccaptionbarm_clrbarbackground"></a><a name="m_clrbarbackground"></a>CMFCCaptionBar::m_clrBarBackground

Цвет фона панели заголовка.

```
COLORREF m_clrBarBackground
```

## <a name="cmfccaptionbarm_clrbarborder"></a><a name="m_clrbarborder"></a>CMFCCaptionBar::m_clrBarBorder

Цвет границы панели подписи.

```
COLORREF m_clrBarBorder
```

## <a name="cmfccaptionbarm_clrbartext"></a><a name="m_clrbartext"></a>CMFCCaptionBar::m_clrBarText

Цвет текста заголовка бара.

```
COLORREF m_clrBarText
```

## <a name="cmfccaptionbarondrawbackground"></a><a name="ondrawbackground"></a>CMFCCaptionBar::Ondrawbackground

Вызывается рамки для заполнения фона подписи бар.

```
virtual void OnDrawBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства панели подписей.

*rect*<br/>
(в) Ограничивающий прямоугольник для заполнения.

### <a name="remarks"></a>Примечания

Метод `OnDrawBackground` вызывается, когда фон панели подписей вот-вот будет заполнен. Реализация по умолчанию заполняет фон с помощью [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) цвет.

Переопределить этот метод `CMFCCaptionBar` в производном классе, чтобы настроить внешний вид панели подписей.

## <a name="cmfccaptionbarondrawborder"></a><a name="ondrawborder"></a>CMFCCaptionBar::OndrawBorder

Вызывается рамки, чтобы нарисовать границу подписи бар.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Контекст устройства, используемый для отображения границ.

*rect*<br/>
(в) Ограничивающий прямоугольник.

### <a name="remarks"></a>Примечания

По умолчанию границы имеют плоский стиль.

Переопределить этот метод `CMFCCaptionBar` в производном классе, чтобы настроить внешний вид границ панели подписей.

## <a name="cmfccaptionbarondrawbutton"></a><a name="ondrawbutton"></a>CMFCCaptionBar::OndrawButton

Вызывается по фреймворку, чтобы нарисовать кнопку заголовок бар.

```
virtual void OnDrawButton(
    CDC* pDC,
    CRect rect,
    const CString& strButton,
    BOOL bEnabled);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства, который используется для отображения кнопки.

*rect*<br/>
(в) Ограничивающий прямоугольник кнопки.

*strButton*<br/>
(в) Текстовая метка кнопки.

*bВСтои*<br/>
(в) TRUE, если кнопка включена; FALSE в противном случае.

### <a name="remarks"></a>Примечания

Переопределить этот метод `CMFCCaptionBar` в производном классе, чтобы настроить внешний вид кнопки заголовка.

## <a name="cmfccaptionbarondrawimage"></a><a name="ondrawimage"></a>CMFCCaptionBar::OndrawImage

Вызывается рамки, чтобы нарисовать изображение заголовка бара.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства, используемый для отображения изображения.

*rect*<br/>
(в) Определяет ограничивающий прямоугольник изображения.

### <a name="remarks"></a>Примечания

Переопределить этот метод `CMFCCaptionBar` в производном классе, чтобы настроить внешний вид изображения.

## <a name="cmfccaptionbarondrawtext"></a><a name="ondrawtext"></a>CMFCCaptionBar::OndrawText

Вызывается по фреймворку, чтобы нарисовать текст заголовка бара.

```
virtual void OnDrawText(
    CDC* pDC,
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства, который используется для отображения кнопки.

*rect*<br/>
(в) Ограничивающий прямоугольник текста.

*strText*<br/>
(в) Текстовая строка для отображения.

### <a name="remarks"></a>Примечания

Реализация по умолчанию отображает `CDC::DrawText` текст с помощью и [CMFCCaptionBar::m_clrBarText](#m_clrbartext) цвет.

Переопределить этот метод `CMFCCaptionBar` в производном классе, чтобы настроить внешний вид текста панели подписей.

## <a name="cmfccaptionbarremovebitmap"></a><a name="removebitmap"></a>CMFCCaptionBar::RemoveBitmap

Удаляет изображение биткарты из панели заголовков.

```cpp
void RemoveBitmap();
```

## <a name="cmfccaptionbarremovebutton"></a><a name="removebutton"></a>CMFCCaptionBar::Удалить кнопку

Удаляет кнопку из панели заголовков.

```cpp
void RemoveButton();
```

### <a name="remarks"></a>Примечания

Расположение элементов панели подписей корректируется автоматически.

## <a name="cmfccaptionbarremoveicon"></a><a name="removeicon"></a>CMFCCaptionBar::RemoveIcon

Удаляет значок из панели подписей.

```cpp
void RemoveIcon();
```

## <a name="cmfccaptionbarremovetext"></a><a name="removetext"></a>CMFCCaptionBar::RemoveText

Удаляет текстовую метку из панели заголовков.

```cpp
void RemoveText();
```

## <a name="cmfccaptionbarsetbitmap"></a><a name="setbitmap"></a>CMFCCaptionBar::SetBitmap

Устанавливает изображение биткарты для панели подписей.

```cpp
void SetBitmap(
    HBITMAP hBitmap,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

void SetBitmap(
    UINT uiBmpResID,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
(в) Ручка к биткарте для установки.

*clrПрозрачный*<br/>
(в) Значение RGB, которое определяет прозрачный цвет битной карты.

*bStretch*<br/>
(в) Если true, бит-карта растягивается, если она не подходит для прямоугольника, ограничивающего изображение. В противном случае биткарта не растягивается.

*bmpВыравнива*<br/>
(в) Выравнивание бит-карты.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы установить битную карту на панели заголовков.

Предыдущая битовая карта уничтожается автоматически. Если в подписи бар отображается значок, потому что вы называете [CMFCCaptionBar::SetIcon](#seticon) метод, bitmap не будет отображаться, если вы удалите значок, позвонив [CMFCCaptionBar::RemoveIcon](#removeicon).

Битовая карта выравнивается в соответствии с параметром *bmpAlignment.*  Этот параметр может принимать одно из следующих значений `BarElementAlignment`:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetbordersize"></a><a name="setbordersize"></a>CMFCCaptionBar::SetBorderSize

Устанавливает размер границы панели подписи.

```cpp
void SetBorderSize(int nSize);
```

### <a name="parameters"></a>Параметры

*Nsize*<br/>
(в) Новый размер, в пикселях, границы панели заголовка.

## <a name="cmfccaptionbarsetbutton"></a><a name="setbutton"></a>CMFCCaptionBar::SetButton

Устанавливает кнопку для панели подписей.

```cpp
void SetButton(
    LPCTSTR lpszLabel,
    UINT uiCmdUI,
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,
    BOOL bHasDropDownArrow=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
Метка команды кнопки.

*uiCmdUI*<br/>
Идентификатор команды кнопки.

*btnAlignmnet*<br/>
Выравнивание кнопки.

*bHasDropDownArrow*<br/>
ПРАВДА, если кнопка отображает падение вниз стрелка, FALSE в противном случае.

## <a name="cmfccaptionbarsetbuttonpressed"></a><a name="setbuttonpressed"></a>CMFCCaptionBar::SetButton

Определяет, остается ли кнопка нажатой.

```cpp
void SetButtonPressed(BOOL bPresed=TRUE);
```

### <a name="parameters"></a>Параметры

*bPresed*<br/>
ПРАВДА, если кнопка сохраняет свое нажатое состояние, FALSE в противном случае.

## <a name="cmfccaptionbarsetbuttontooltip"></a><a name="setbuttontooltip"></a>CMFCCaptionBar::SetButtonToolTip

Устанавливает набор инструментов для кнопки.

```cpp
void SetButtonToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Параметры

*lpszToolTip*<br/>
(в) Подпись к инструменту.

*lpszОписание*<br/>
(в) Описание инструментария.

## <a name="cmfccaptionbarsetflatborder"></a><a name="setflatborder"></a>CMFCCaptionBar::SetFlatBorder

Устанавливает пограничный стиль панели подписей.

```cpp
void SetFlatBorder(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>Параметры

*bFlat*<br/>
(в) ПРАВДА, если граница подписи бар плоский. FALSE, если граница 3D.

## <a name="cmfccaptionbarseticon"></a><a name="seticon"></a>CMFCCaptionBar::SetIcon

Устанавливает значок для панели подписей.

```cpp
void SetIcon(
    HICON hIcon,
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
(в) Ручка к значку для установки.

*iconAlignment*<br/>
(в) Выравнивание значка.

### <a name="remarks"></a>Примечания

Подписи бары могут отображать либо значки или bitmaps. Смотрите [CMFCCaptionBar::SetBitmap,](#setbitmap) чтобы узнать, как отобразить бит-карту. Если вы установите иконку и битную карту, значок всегда отображается. Позвоните [CMFCCaptionBar::RemoveIcon,](#removeicon) чтобы удалить значок из панели подписей.

Значок выровнен в соответствии с параметром *iconAlignment.* Это может быть одно `BarElementAlignment` из следующих значений:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetimagetooltip"></a><a name="setimagetooltip"></a>CMFCCaptionBar::SetImageToolTip

Устанавливает набор инструментов для изображения в панели заголовков.

```cpp
void SetImageToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Параметры

*lpszToolTip*<br/>
(в) Текст инструментария.

*lpszОписание*<br/>
(в) Описание инструментария.

## <a name="cmfccaptionbarsetmargin"></a><a name="setmargin"></a>CMFCCaptionBar::SetMargin

Устанавливает расстояние между краем элемента панели подписи и краем управления панели подписи.

```cpp
void SetMargin(int nMargin);
```

### <a name="parameters"></a>Параметры

*nМаржа*<br/>
(в) Расстояние, в пикселях, между краем элементов панели подписи и краем управления панели подписи.

## <a name="cmfccaptionbarsettext"></a><a name="settext"></a>CMFCCaptionBar::SetText

Устанавливает текстовую метку для панели подписей.

```cpp
void SetText(
    const CString& strText,
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Параметры

*strText*<br/>
(в) Текст строки для установки.

*textAlignment*<br/>
(в) Выравнивание текста.

### <a name="remarks"></a>Примечания

Текстовая метка выравнивается по параметру *textAlignment.* Это может быть одно `BarElementAlignment` из следующих значений:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
