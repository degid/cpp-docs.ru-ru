---
title: Класс CMFCCaptionButton
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
ms.openlocfilehash: 1b0a999f1fd1e3df1b0a971220454397cead02a9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752595"
---
# <a name="cmfccaptionbutton-class"></a>Класс CMFCCaptionButton

Класс `CMFCCaptionButton` реализует кнопку, которая отображается на панели заголовков для стыковки или окна мини-рамки. Как правило, платформа создает кнопки заголовка автоматически.

## <a name="syntax"></a>Синтаксис

```
class CMFCCaptionButton : public CObject
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|Строит объект CMFCCaptionButton.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCCaptionButton::GetHit](#gethit)|Возвращает команду, представленную кнопкой.|
|[CMFCCaptionButton::GetIconID](#geticonid)|Возвращает идентификатор изображения, связанный с кнопкой.|
|[CMFCCaptionButton::GetRect](#getrect)|Возвращает прямоугольник, занятый кнопкой.|
|[CMFCCaptionButton::GetSize](#getsize)|Возвращает ширину и высоту кнопки.|
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Указывает, устанавливается ли высота заголовка бара на мини-размер.|
|[CMFCCaptionButton::Move](#move)|Устанавливает расположение рисования кнопки и состояние показа окна.|
|[CMFCCaptionButton::Ondraw](#ondraw)|Рисует кнопку заголовка.|
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Устанавливает мини-размер заголовка бара.|

## <a name="remarks"></a>Примечания

Вы можете получить класс из [класса CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) `AddButton`и использовать защищенный метод, чтобы добавить кнопки подписи к окну мини-рамки.

CPaneFrameWnd.h определяет идеки команд для двух типов кнопок подписей:

- AFX_CAPTION_BTN_PIN, которая отображает кнопку контакта, когда стыковочной панели поддерживает режим автоматической скрытности.

- AFX_CAPTION_BTN_CLOSE, которая отображает кнопку **"Закрыть",** когда панель может быть закрыта или скрыта.

## <a name="example"></a>Пример

В следующем примере показано, `CMFCCaptionButton` как построить объект и установить мини-размер заголовка.

[!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcaptionbutton.h

## <a name="cmfccaptionbuttoncmfccaptionbutton"></a><a name="cmfccaptionbutton"></a>CMFCCaptionButton::CMFCCaptionButton

Формирует объект `CMFCCaptionButton`.

```
CMFCCaptionButton();

CMFCCaptionButton(
    UINT nHit,
    BOOL bLeftAlign = FALSE);
```

### <a name="parameters"></a>Параметры

*nHit*<br/>
(в) Команда, связанная с кнопкой.

*bLeftAlign*<br/>
(в) Определяет, выравнивается ли кнопка влево.

В следующей таблице перечислены возможные значения параметра *nHit.*

|Значение|Get-Help|
|-----------|-------------|
|AFX_HTCLOSE|Кнопка закрытия.|
|HTMINBUTTON|Минимизировать кнопку.|
|HTMAXBUTTON|Кнопка максимизации.|
|AFX_HTLEFTBUTTON|Кнопка левой стрелки.|
|AFX_HTRIGHTBUTTON|Правая кнопка стрелки.|
|AFX_HTMENU|Кнопка меню «Вниз» вниз.|
|HTNOWHERE|Значение по умолчанию; не представляет собой команду.|

### <a name="remarks"></a>Примечания

По умолчанию кнопки заголовка не связаны с командой.

Кнопки подписи выровнены либо справа, либо слева.

## <a name="cmfccaptionbuttongethit"></a><a name="gethit"></a>CMFCCaptionButton::GetHit

Возвращает команду, представленную кнопкой.

```
UINT GetHit() const;
```

### <a name="return-value"></a>Возвращаемое значение

Команда, представленная кнопкой.

В следующей таблице перечислены возможные значения возврата.

|Значение|Get-Help|
|-----------|-------------|
|AFX_HTCLOSE|Кнопка закрытия.|
|HTMINBUTTON|Минимизировать кнопку.|
|HTMAXBUTTON|Кнопка максимизации.|
|AFX_HTLEFTBUTTON|Кнопка левой стрелки.|
|AFX_HTRIGHTBUTTON|Правая кнопка стрелки.|
|AFX_HTMENU|Кнопка меню «Вниз» вниз.|
|HTNOWHERE|Значение по умолчанию; не представляет собой команду.|

## <a name="cmfccaptionbuttongeticonid"></a><a name="geticonid"></a>CMFCCaptionButton::GetIconID

Возвращает идентификатор изображения, связанный с кнопкой.

```
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,
    BOOL bMaximized = FALSE) const;
```

### <a name="parameters"></a>Параметры

*bHorz*<br/>
(в) TRUE для идотов изображения левой или правой стрелки; FALSE для идотов изображения вверх или вниз.

*bMaximized*<br/>
(в) TRUE для максимификаи изображения; FALSE для минимизации идентификатора изображения.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор изображения.

### <a name="remarks"></a>Примечания

Параметры указывают инообразное изображение для минимизации или максимизации кнопок заголовков.

## <a name="cmfccaptionbuttongetrect"></a><a name="getrect"></a>CMFCCaptionButton::GetRect

Возвращает прямоугольник, занятый кнопкой.

```
virtual CRect GetRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Прямоугольник, представляющий расположение кнопки.

### <a name="remarks"></a>Примечания

Если вы не видите кнопку, возвращенный размер составляет 0.

## <a name="cmfccaptionbuttongetsize"></a><a name="getsize"></a>CMFCCaptionButton::GetSize

Возвращает ширину и высоту кнопки.

```
static CSize GetSize();
```

### <a name="return-value"></a>Возвращаемое значение

Внешние размеры кнопки.

### <a name="remarks"></a>Примечания

Возвращается размер включает пуговицу и границу.

## <a name="cmfccaptionbuttonisminiframebutton"></a><a name="isminiframebutton"></a>CMFCCaptionButton::IsMiniFrameButton

Указывает, устанавливается ли высота заголовка бара на мини-размер.

```
BOOL IsMiniFrameButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если подпись установлена на мини-размер; в противном случае FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfccaptionbuttonmove"></a><a name="move"></a>CMFCCaptionButton::Move

Устанавливает расположение рисования кнопки и состояние показа окна.

```cpp
void Move(
    const CPoint& ptTo,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Параметры

*птто*<br/>
(в) Новое место.

*bHide*<br/>
(в) Показывать ли кнопку.

## <a name="cmfccaptionbuttonondraw"></a><a name="ondraw"></a>CMFCCaptionButton::Ondraw

Рисует кнопку заголовка.

```
virtual void OnDraw(
    CDC* pDC,
    BOOL bActive,
    BOOL bHorz = TRUE,
    BOOL bMaximized = TRUE,
    BOOL bDisabled = FALSE);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства для кнопки.

*bАктивный*<br/>
(в) Нарисовать ли изображение активной кнопки.

*bHorz*<br/>
(в) Зарезервировано для использования в производном классе.

*bMaximized*<br/>
(в) Следует ли нарисовать максимальное изображение кнопки.

*bDisabled*<br/>
(в) Нарисовать ли изображение включенной кнопки.

### <a name="remarks"></a>Примечания

Параметр *bMaximized* используется, когда кнопка является максимальной или минимизировать кнопку.

## <a name="cmfccaptionbuttonsetminiframebutton"></a><a name="setminiframebutton"></a>CMFCCaptionButton::SetMiniFrameButton

Устанавливает мини-размер заголовка бара.

```cpp
void SetMiniFramebutton(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Параметры

*bSet*<br/>
(в) TRUE для мини-высота заглавного бара; FALSE для высоты заголовка по умолчанию.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)
