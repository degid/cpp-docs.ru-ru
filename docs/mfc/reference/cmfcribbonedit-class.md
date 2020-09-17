---
title: Класс CMFCRibbonEdit
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
helpviewer_keywords:
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CanBeStretched
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CopyFrom
- CMFCRibbonEdit [MFC], CreateEdit
- CMFCRibbonEdit [MFC], DestroyCtrl
- CMFCRibbonEdit [MFC], DropDownList
- CMFCRibbonEdit [MFC], EnableSpinButtons
- CMFCRibbonEdit [MFC], GetCompactSize
- CMFCRibbonEdit [MFC], GetEditText
- CMFCRibbonEdit [MFC], GetIntermediateSize
- CMFCRibbonEdit [MFC], GetTextAlign
- CMFCRibbonEdit [MFC], GetWidth
- CMFCRibbonEdit [MFC], HasCompactMode
- CMFCRibbonEdit [MFC], HasFocus
- CMFCRibbonEdit [MFC], HasLargeMode
- CMFCRibbonEdit [MFC], HasSpinButtons
- CMFCRibbonEdit [MFC], IsHighlighted
- CMFCRibbonEdit [MFC], OnAfterChangeRect
- CMFCRibbonEdit [MFC], OnDraw
- CMFCRibbonEdit [MFC], OnDrawLabelAndImage
- CMFCRibbonEdit [MFC], OnDrawOnList
- CMFCRibbonEdit [MFC], OnEnable
- CMFCRibbonEdit [MFC], OnHighlight
- CMFCRibbonEdit [MFC], OnKey
- CMFCRibbonEdit [MFC], OnLButtonDown
- CMFCRibbonEdit [MFC], OnLButtonUp
- CMFCRibbonEdit [MFC], OnRTLChanged
- CMFCRibbonEdit [MFC], OnShow
- CMFCRibbonEdit [MFC], Redraw
- CMFCRibbonEdit [MFC], SetACCData
- CMFCRibbonEdit [MFC], SetEditText
- CMFCRibbonEdit [MFC], SetTextAlign
- CMFCRibbonEdit [MFC], SetWidth
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
ms.openlocfilehash: ab621a05f9b658eee9babb14e257680fa95e0f96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375181"
---
# <a name="cmfcribbonedit-class"></a>Класс CMFCRibbonEdit

Реализует элемент управления отсечения, который расположен на ленте бар.

## <a name="syntax"></a>Синтаксис

```cpp
class CMFCRibbonEdit : public CMFCRibbonButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Формирует объект `CMFCRibbonEdit`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|Указывает, может ли `CMFCRibbonEdit` высота управления увеличиваться вертикально до высоты ленточного ряда.|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Формирует объект `CMFCRibbonEdit`.|
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|Копирует состояние указанного `CMFCRibbonEdit` объекта к `CMFCRibbonEdit` текущему объекту.|
|[CMFCRibbonEdit::CreateEdit](#createedit)|Создает новый текстовый `CMFCRibbonEdit` ящик для объекта.|
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|Уничтожает `CMFCRibbonEdit` объект.|
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|Падает с ящика списка.|
|[CMFCRibbonEdit:EnableSpinButtons](#enablespinbuttons)|Включает и устанавливает диапазон кнопки спина для текстового ящика.|
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|Извлекает компактный размер `CFMCRibbonEdit` объекта.|
|[CMFCRibbonEdit::GetEditText](#getedittext)|Извлекает текст в текстовую коробку.|
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|Извлекает промежуточный размер `CMFCRibbonEdit` объекта.|
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|Извлекает выравнивание текста в текстовом поле.|
|[CMFCRibbonEdit::GetWidth](#getwidth)|Извлекает ширину, в пикселях, элемента `CMFCRibbonEdit` управления.|
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Указывает, может ли `CMFCRibbonEdit` размер дисплея для управления быть компактным.|
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Указывает, `CMFCRIbbonEdit` имеет ли элемент управления фокус.|
|[CMFCRibbonEdit:HasLargeMode](#haslargemode)|Указывает, может ли `CMFCRibbonEdit` размер дисплея для управления быть большим.|
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Указывает, есть ли в текстовом поле кнопка вращения.|
|[CMFCRibbonEdit::Ishighlighted](#ishighlighted)|Указывает, `CMFCRibbonEdit` выделен ли элемент управления.|
|[CMFCRibbonEdit::AfterChangeRect](#onafterchangerect)|Вызывается фреймворцом, когда размеры `CMFCRibbonEdit` прямоугольника дисплея для изменения элемента управления.|
|[CMFCRibbonEdit::OnDraw](#ondraw)|Вызывается рамки, чтобы `CMFCRibbonEdit` нарисовать контроль.|
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|Вызывается рамкой, чтобы нарисовать `CMFCRibbonEdit` этикетку и изображение для управления.|
|[CMFCRibbonEdit::OndrawOnList](#ondrawonlist)|Вызывается фреймворком, чтобы нарисовать `CMFCRibbonEdit` элемент управления в поле списка команд.|
|[CMFCRibbonEdit::OnEnable](#onenable)|Вызывается в рамках, чтобы включить `CMFCRibbonEdit` или отключить элемент управления.|
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|Вызывается по фрейму, когда указатель входит `CMFCRibbonEdit` или выходит за пределы элемента управления.|
|[CMFCRibbonEdit::OnKey](#onkey)|Вызывается по системе, когда пользователь нажимает клавишу и `CMFCRibbonEdit` элемент управления имеет фокус.|
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Вызывается фреймворком для обновления элемента `CMFCRibbonEdit` управления, когда пользователь нажимает кнопку левой мыши на элементе управления.|
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Вызывается по фреймворку, когда пользователь выпускает левую кнопку мыши.|
|[CMFCRibbonEdit::OnRTLИзменен](#onrtlchanged)|Вызывается инфраструктурой для `CMFCRibbonEdit` обновления элемента управления при изменении направления макета.|
|[CMFCRibbonEdit::OnShow](#onshow)|Вызывается по системе, чтобы `CMFCRibbonEdit` показать или скрыть элемент управления.|
|[CMFCRibbonEdit::Redraw](#redraw)|Обновляет отображение элемента `CMFCRibbonEdit` управления.|
|[CMFCRibbonEdit::SetACCData](#setaccdata)|Устанавливает данные о `CMFCRibbonEdit` доступности объекта.|
|[CMFCRibbonEdit::SetEditText](#setedittext)|Устанавливает текст в текстовом поле.|
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Устанавливает выравнивание текста текстового окна.|
|[CMFCRibbonEdit::SetWidth](#setwidth)|Устанавливает ширину текстового `CMFCRibbonEdit` поля для управления.|

## <a name="remarks"></a>Примечания

## <a name="example"></a>Пример

В следующем примере показано, `CMFCRibbonEdit` как построить объект, показать кнопки вращения рядом с управлением редактирования и установить текст управления редактированием. Этот фрагмент кода является частью [образца MS Office 2007 Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** afxRibbonEdit.h

## <a name="cmfcribboneditcanbestretched"></a><a name="canbestretched"></a>CMFCRibbonEdit::CanBeStretched

Указывает, может ли высота управления [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) увеличиваться вертикально до высоты ленточного ряда.

```cpp
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditcmfcribbonedit"></a><a name="cmfcribbonedit"></a>CMFCRibbonEdit::CMFCRibbonEdit

Строит объект [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
CMFCRibbonEdit(
    UINT nID,
    int nWidth,
    LPCTSTR lpszLabel = NULL,
    int nImage = -1);

CMFCRibbonEdit();
```

### <a name="parameters"></a>Параметры

*nID*<br/>
(в) Идентификатор команды для `CMFCRibbonEdit` управления.

*nWidth*<br/>
(в) Ширина, в пикселях, текстового ящика `CMFCRibbonEdit` для управления.

*lpszLabel*<br/>
(в) Метка для `CMFCRibbonEdit` управления.

*nИзображение*<br/>
(в) Индекс небольшого изображения для `CMFCRibbonEdit` управления. Коллекция небольших изображений поддерживается категорией родительской ленты.

### <a name="remarks"></a>Примечания

Элемент `CMFCRibbonEdit` управления не использует большое изображение.

## <a name="cmfcribboneditcopyfrom"></a><a name="copyfrom"></a>CMFCRibbonEdit::CopyFrom

Копирует состояние указанного объекта [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) с текущим объектом [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
(в) Объект `CMFCRibbonEdit` исходного кода.

### <a name="remarks"></a>Примечания

Параметр *src* должен `CMFCRibbonEdit`быть типа.

## <a name="cmfcribboneditcreateedit"></a><a name="createedit"></a>CMFCRibbonEdit::CreateEdit

Создает новый текстовый ящик для объекта [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Указатель на родительское окно `CMFCRibbonEdit` объекта.

*dwEditStyle*<br/>
(в) Определяет стиль текстового окна. Стили окон, перечисленные в разделе Remarks, можно объединить со [стилями управления правками,](/windows/win32/Controls/edit-control-styles) описанными в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый текстовый ящик, если метод был успешным; в противном случае, NULL.

### <a name="remarks"></a>Примечания

Переопределить этот метод в производном классе для создания пользовательского текстового окна.

Вы можете применить следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к текстовому окну:

- **WS_CHILD**

- **WS_VISIBLE**

- **WS_DISABLED**

- **WS_GROUP**

- **WS_TABSTOP**

## <a name="cmfcribboneditdestroyctrl"></a><a name="destroyctrl"></a>CMFCRibbonEdit::DestroyCtrl

Уничтожает объект [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual void DestroyCtrl();
```

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditdropdownlist"></a><a name="dropdownlist"></a>CMFCRibbonEdit::DropDownList

Падает с ящика списка.

```cpp
virtual void DropDownList();
```

### <a name="remarks"></a>Примечания

По умолчанию этот метод ничего не делает. Переопределить этот метод, чтобы упасть в поле списка.

## <a name="cmfcribboneditenablespinbuttons"></a><a name="enablespinbuttons"></a>CMFCRibbonEdit:EnableSpinButtons

Включает и устанавливает диапазон кнопки спина для текстового ящика.

```cpp
void EnableSpinButtons(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Параметры

*nMin*<br/>
(в) Минимальное значение кнопки спина.

*nMax*<br/>
(в) Максимальное значение кнопки спина.

### <a name="remarks"></a>Примечания

Кнопки спина отображают стрелку вверх и вниз и позволяют пользователям перемещаться по фиксированному набору значений.

## <a name="cmfcribboneditgetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonEdit::GetCompactSize

Извлекает компактный размер объекта [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства `CMFCRibbonEdit` для объекта.

### <a name="return-value"></a>Возвращаемое значение

Компактный размер `CMFCRibbonEdit` объекта.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditgetedittext"></a><a name="getedittext"></a>CMFCRibbonEdit::GetEditText

Извлекает текст в текстовую коробку.

```cpp
CString GetEditText() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текст в текстовом окне.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditgetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonEdit::GetIntermediateSize

Извлекает промежуточный размер объекта [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства `CMFCRibbonEdit` для объекта.

### <a name="return-value"></a>Возвращаемое значение

Промежуточный размер `CMFCRibbonEdit` объекта.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditgettextalign"></a><a name="gettextalign"></a>CMFCRibbonEdit::GetTextAlign

Извлекает выравнивание текста в текстовом поле.

```cpp
int GetTextAlign() const;
```

### <a name="return-value"></a>Возвращаемое значение

Перечисленное значение выравнивания текста. Смотрите раздел Замечания для возможных значений.

### <a name="remarks"></a>Примечания

Возвратное значение является одним из следующих стилей управления отсеиваний:

- **ES_LEFT** для левого выравнивания

- **ES_CENTER выравнивание** центра

- **ES_RIGHT** для правильного выравнивания

Для получения дополнительной информации [Edit Control Styles](/windows/win32/Controls/edit-control-styles)об этих стилях см.

## <a name="cmfcribboneditgetwidth"></a><a name="getwidth"></a>CMFCRibbonEdit::GetWidth

Извлекает ширину, в пикселях, управления [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>Параметры

*bInFloatyMode*<br/>
(в) TRUE, `CMFCRibbonEdit` если элемент управления находится в плавающем режиме; в противном случае, FALSE.

### <a name="return-value"></a>Возвращаемое значение

Ширина, в пикселях, элемента `CMFCRibbonEdit` управления.

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonedithascompactmode"></a><a name="hascompactmode"></a>CMFCRibbonEdit::HasCompactMode

Указывает, может ли размер дисплея для управления [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) быть компактным.

```cpp
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается TRUE.

### <a name="remarks"></a>Примечания

По умолчанию этот метод всегда возвращает TRUE. Переопределить этот метод, чтобы указать, может ли размер дисплея быть компактным.

## <a name="cmfcribbonedithasfocus"></a><a name="hasfocus"></a>CMFCRibbonEdit::HasFocus

Указывает, имеет ли внимание элемент управления [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, `CMFCRibbonEdit` если элемент управления имеет фокус; в противном случае FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonedithaslargemode"></a><a name="haslargemode"></a>CMFCRibbonEdit:HasLargeMode

Указывает, может ли размер дисплея для управления [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) быть большим.

```cpp
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает FALSE.

### <a name="remarks"></a>Примечания

По умолчанию этот метод всегда возвращает FALSE. Переопределить этот метод, чтобы указать, может ли размер дисплея быть большим.

## <a name="cmfcribbonedithasspinbuttons"></a><a name="hasspinbuttons"></a>CMFCRibbonEdit::HasSpinButtons

Указывает, есть ли в текстовом поле кнопка вращения.

```cpp
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если текстовый ящик имеет кнопку спина; в противном случае FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditishighlighted"></a><a name="ishighlighted"></a>CMFCRibbonEdit::Ishighlighted

Указывает, выделяется ли элемент управления [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, `CMFCRibbonEdit` если элемент управления выделен; в противном случае FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditonafterchangerect"></a><a name="onafterchangerect"></a>CMFCRibbonEdit::AfterChangeRect

Вызывается по фрейму, когда размеры прямоугольника дисплея для изменения управления [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства `CMFCRibbonEdit` для управления.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditondraw"></a><a name="ondraw"></a>CMFCRibbonEdit::OnDraw

Вызывается в рамках обратить [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления.

```cpp
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства `CMFCRibbonEdit` для управления.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditondrawlabelandimage"></a><a name="ondrawlabelandimage"></a>CMFCRibbonEdit::OnDrawLabelAndImage

Вызывается рамки для рисования этикетки и изображения для управления [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства `CMFCRibbonEdit` для управления.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonEdit::OndrawOnList

Вызывается по системе, чтобы нарисовать управление [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) в поле списка команд.

```cpp
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства `CMFCRibbonEdit` для управления.

*strText*<br/>
(в) Текст дисплея [ ](../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit класс").

*nTextOffset*<br/>
(в) Расстояние, в пикселях, от левой стороны окна списка до текста дисплея.

*rect*<br/>
(в) Прямоугольник дисплея `CMFCRibbonEdit` для управления.

*bIsSelected*<br/>
(в) Этот параметр не используется.

*bНазалион*<br/>
(в) Этот параметр не используется.

### <a name="remarks"></a>Примечания

Коробка списка команд отображает элементы управления лентой, чтобы пользователи могли настроить панель инструментов быстрого доступа.

## <a name="cmfcribboneditonenable"></a><a name="onenable"></a>CMFCRibbonEdit::OnEnable

Вызывается в рамках, чтобы включить или отключить контроль [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE для обеспечения контроля; FALSE, чтобы отключить элемент управления.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditonhighlight"></a><a name="onhighlight"></a>CMFCRibbonEdit::OnHighlight

Вызывается по системе, когда указатель входит или выходит за пределы контроля [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>Параметры

*bHighlight*<br/>
(в) TRUE, если указатель находится в `CMFCRibbonEdit` границах управления; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditonkey"></a><a name="onkey"></a>CMFCRibbonEdit::OnKey

Вызывается по рамкам, когда пользователь нажимает на клавишу и [cmFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) управления имеет фокус.

```cpp
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>Параметры

*bIsMenuKey*<br/>
(в) TRUE, если клавиатура отображает всплывающее меню; в противном случае, FALSE.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если событие было обработано; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditonlbuttondown"></a><a name="onlbuttondown"></a>CMFCRibbonEdit::OnLButtonDown

Вызывается по системе для обновления управления [CMFCRibbonEdit,](../../mfc/reference/cmfcribbonedit-class.md) когда пользователь нажимает левую кнопку мыши на элементе управления.

```cpp
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
(в) Этот параметр не используется.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditonlbuttonup"></a><a name="onlbuttonup"></a>CMFCRibbonEdit::OnLButtonUp

Вызывается по фреймворку, когда пользователь выпускает левую кнопку мыши.

```cpp
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
(в) Этот параметр не используется.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditonrtlchanged"></a><a name="onrtlchanged"></a>CMFCRibbonEdit::OnRTLИзменен

Вызывается в рамках для обновления управления [CMFCRibbonEdit,](../../mfc/reference/cmfcribbonedit-class.md) когда макет меняет направление.

```cpp
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>Параметры

*bIsRTL*<br/>
(в) ПРАВДА, если макет справа налево; FALSE, если макет слева направо.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditonshow"></a><a name="onshow"></a>CMFCRibbonEdit::OnShow

Вызывается по системе, чтобы показать или скрыть контроль [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
(в) TRUE, чтобы показать контроль; FALSE, чтобы скрыть контроль.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditredraw"></a><a name="redraw"></a>CMFCRibbonEdit::Redraw

Обновляет дисплей управления [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual void Redraw();
```

### <a name="remarks"></a>Примечания

Этот метод перерисовывает прямоугольник дисплея для `CMFCRibbonEdit` объекта, косвенно вызывая [CWnd::RedrawWindow](/windows/win32/api/winuser/nf-winuser-redrawwindow) с набором RDW_INVALIDATE, RDW_ERASE и RDW_UPDATENOW флагов.

## <a name="cmfcribboneditsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonEdit::SetACCData

Устанавливает данные о доступности для объекта [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Параметры

*pРодитель*<br/>
Указатель на родительское `CMFCRibbonEdit` окно для объекта.

*данные*<br/>
Данные о доступности `CMFCRibbonEdit` объекта.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается TRUE.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboneditsetedittext"></a><a name="setedittext"></a>CMFCRibbonEdit::SetEditText

Устанавливает текст в текстовом поле.

```cpp
void SetEditText(CString strText);
```

### <a name="parameters"></a>Параметры

*strText*<br/>
(в) Текст для текстового ящика.

## <a name="cmfcribboneditsettextalign"></a><a name="settextalign"></a>CMFCRibbonEdit::SetTextAlign

Устанавливает выравнивание текста текстового окна.

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Параметры

*nAlign*<br/>
(в) Перечисленное значение выравнивания текста. Смотрите раздел Замечания для возможных значений.

### <a name="remarks"></a>Примечания

Параметр *nAlign* является одним из следующих стилей управления отсеиваний:

- ES_LEFT для левого выравнивания

- ES_CENTER выравнивание центра

- ES_RIGHT для правильного выравнивания

Для получения дополнительной информации [Edit Control Styles](/windows/win32/Controls/edit-control-styles)об этих стилях см.

## <a name="cmfcribboneditsetwidth"></a><a name="setwidth"></a>CMFCRibbonEdit::SetWidth

Устанавливает ширину текстового поля для управления [CMFCRibbonEdit.](../../mfc/reference/cmfcribbonedit-class.md)

```cpp
void SetWidth(
    int nWidth,
    BOOL bInFloatyMode = FALSE);
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
(в) Ширина, в пикселях, текстового ящика.

*bInFloatyMode*<br/>
TRUE для установки ширины для плавающего режима; FALSE установить ширину для обычного режима.

### <a name="remarks"></a>Примечания

Элемент `CMFCRibbonEdit` управления имеет две ширины в зависимости от режима отображения: плавающий режим и обычный режим.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
