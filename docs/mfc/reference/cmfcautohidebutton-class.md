---
title: Класс CMFCAutoHideButton
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::BringToTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Create
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAlignment
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAutoHideWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetParentToolBar
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetRect
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetTextSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::HighlightButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsActive
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHighlighted
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHorizontal
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsVisible
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Move
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDraw
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDrawBorder
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnFillBackground
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ReplacePane
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowAttachedWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::UnSetAutoHideMode
helpviewer_keywords:
- CMFCAutoHideButton [MFC], BringToTop
- CMFCAutoHideButton [MFC], Create
- CMFCAutoHideButton [MFC], GetAlignment
- CMFCAutoHideButton [MFC], GetAutoHideWindow
- CMFCAutoHideButton [MFC], GetParentToolBar
- CMFCAutoHideButton [MFC], GetRect
- CMFCAutoHideButton [MFC], GetSize
- CMFCAutoHideButton [MFC], GetTextSize
- CMFCAutoHideButton [MFC], HighlightButton
- CMFCAutoHideButton [MFC], IsActive
- CMFCAutoHideButton [MFC], IsHighlighted
- CMFCAutoHideButton [MFC], IsHorizontal
- CMFCAutoHideButton [MFC], IsTop
- CMFCAutoHideButton [MFC], IsVisible
- CMFCAutoHideButton [MFC], Move
- CMFCAutoHideButton [MFC], OnDraw
- CMFCAutoHideButton [MFC], OnDrawBorder
- CMFCAutoHideButton [MFC], OnFillBackground
- CMFCAutoHideButton [MFC], ReplacePane
- CMFCAutoHideButton [MFC], ShowAttachedWindow
- CMFCAutoHideButton [MFC], ShowButton
- CMFCAutoHideButton [MFC], UnSetAutoHideMode
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
ms.openlocfilehash: 3ea6ce13b8cca7e0130fe14459a832b476391b0c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751672"
---
# <a name="cmfcautohidebutton-class"></a>Класс CMFCAutoHideButton

Кнопка, отображающая или скрывающая [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) , настроенный на скрытие.

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCAutoHideButton : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCAutoHideButton::BringToTop](#bringtotop)||
|[CMFCAutoHideButton::Create](#create)|Создает и инициализирует кнопку автоматического скрытия.|
|[CMFCAutoHideButton::GetAlignment](#getalignment)|Извлекает выравнивание кнопки автоматического скрытия.|
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|Возвращает объект [CDockablePane,](../../mfc/reference/cdockablepane-class.md) связанный с кнопкой автоматического скрытия.|
|[CMFCAutoHideButton::GetParentToolBar](#getparenttoolbar)||
|[CMFCAutoHideButton::GetRect](#getrect)||
|[CMFCAutoHideButton::GetSize](#getsize)|Определяет размер кнопки автоматического скрытия.|
|[CMFCAutoHideButton::GetTextSize](#gettextsize)|Возвращает размер текстовой метки для кнопки автоматического скрытия.|
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|Выделяет кнопку автоматического скрытия.|
|[CMFCAutoHideButton::IsActive](#isactive)|Указывает, активна ли кнопка автоматического скрытия.|
|[CMFCAutoHideButton::IsHighlighted](#ishighlighted)|Возвращает выделенное состояние кнопки автоматического скрытия.|
|[CMFCAutoHideButton::IsHorizontal](#ishorizontal)|Определяет, является кнопка автоматического скрытия горизонтальной или вертикальной.|
|[CMFCAutoHideButton::IsTop](#istop)||
|[CMFCAutoHideButton::IsVisible](#isvisible)|Указывает, является ли кнопка видимой.|
|[CMFCAutoHideButton::Move](#move)||
|[CMFCAutoHideButton::OnDraw](#ondraw)|Этот метод вызывается платформой при рисовании кнопки автоматического скрытия.|
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|Этот метод вызывается платформой при рисовании границ кнопки автоматического скрытия.|
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|Этот метод вызывается платформой при заливке фона кнопки автоматического скрытия.|
|[CMFCAutoHideButton::ReplacePane](#replacepane)||
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|Показывает или скрывает связанный [CDockablePane класса](../../mfc/reference/cdockablepane-class.md).|
|[CMFCAutoHideButton::ShowButton](#showbutton)|Показывает или скрывает кнопку автоматического скрытия.|
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||

## <a name="remarks"></a>Примечания

При создании `CMFCAutoHideButton` объект прикрепляется к [классу CDockablePane.](../../mfc/reference/cdockablepane-class.md) В результате взаимодействия пользователя с объектом `CMFCAutoHideButton` показывается или скрывается объект `CDockablePane`.

По умолчанию при включении автоматического скрытия платформа автоматически создает объект класса `CMFCAutoHideButton`. Вместо объекта класса `CMFCAutoHideButton` платформа может создавать элемент настраиваемого класса пользовательского интерфейса. Чтобы указать, какой настраиваемый класс пользовательского интерфейса должна использовать платформа, задайте для статической переменной-члена `CMFCAutoHideBar::m_pAutoHideButtonRTS` значение, равное необходимому настраиваемому классу. Значение этой переменной по умолчанию — `CMFCAutoHideButton`.

## <a name="example"></a>Пример

В этом примере демонстрируется создание объекта `CMFCAutoHideButton` и использование различных методов класса `CMFCAutoHideButton`. В этом примере демонстрируется инициализация объекта `CMFCAutoHideButton` с помощью метода `Create`, а также отображение связанного класса `CDockablePane` и кнопки автоматического скрытия.

[!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAutoHideButton`

## <a name="requirements"></a>Требования

**Заголовок:** afxautohidebutton.h

## <a name="cmfcautohidebuttonbringtotop"></a><a name="bringtotop"></a>CMFCAutoHideButton::BringTotop

```cpp
void BringToTop();
```

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebuttoncreate"></a><a name="create"></a>CMFCAutoHideButton::Создание

Создает и инициализирует кнопку автоматического укрытия.

```
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Параметры

*pParentBar*<br/>
(в) Указатель на родительскую панель инструментов.

*pAutoHideWnd*<br/>
(в) Указатель на объект [CDockablePane.](../../mfc/reference/cdockablepane-class.md) Эта кнопка автоматической укрытия `CDockablePane`скрывает и показывает, что .

*dwAlignment*<br/>
(в) Значение, оговариващее выравнивание кнопки с окном основной рамы.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

При создании `CMFCAutoHideButton` объекта необходимо связать кнопку автоматического скрытия с определенной `CDockablePane`кнопкой . Пользователь может использовать кнопку автоматического сокрытия, `CDockablePane`чтобы скрыть и показать связанные .

Параметр *dwAlignment* указывает, где находится кнопка автоматического укрытия в приложении. Параметру может быть присвоено одно из следующих значений:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetalignment"></a><a name="getalignment"></a>CMFCAutoHideButton::GetAlignment

Извлекает выравнивание кнопки автоматического скрытия.

```
DWORD GetAlignment() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD, содержащее текущее выравнивание кнопки автоматического скрытия.

### <a name="remarks"></a>Примечания

Выравнивание кнопки автоматического скрытия указывает, где находится кнопка в приложении. Это может быть любое из следующих значений:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CRBS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetautohidewindow"></a><a name="getautohidewindow"></a>CMFCAutoHideButton::GetAutoHideWindow

Возвращает объект [CDockablePane,](../../mfc/reference/cdockablepane-class.md) связанный с кнопкой автоматического скрытия.

```
CDockablePane* GetAutoHideWindow() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на связанный `CDockablePane` объект.

### <a name="remarks"></a>Примечания

Чтобы связать кнопку автоматического `CDockablePane`сокрытия `CDockablePane` с, передайте в качестве параметра [CMFCAutoHideButton::Create](#create) метод.

## <a name="cmfcautohidebuttongetparenttoolbar"></a><a name="getparenttoolbar"></a>CMFCAutoHideButton::GetParentToolBar

```
CMFCAutoHideBar* GetParentToolBar();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebuttongetrect"></a><a name="getrect"></a>CMFCAutoHideButton::GetRect

```
CRect GetRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebuttongetsize"></a><a name="getsize"></a>CMFCAutoHideButton::GetSize

Определяет размер кнопки автоматического скрытия.

```
CSize GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CSize` содержащий размер кнопки.

### <a name="remarks"></a>Примечания

Расчетный размер включает в себя размер границы кнопки автоматического скрытия.

## <a name="cmfcautohidebuttongettextsize"></a><a name="gettextsize"></a>CMFCAutoHideButton::GetTextSize

Возвращает размер текстовой метки для кнопки автоматического скрытия.

```
virtual CSize GetTextSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CSize,](../../atl-mfc-shared/reference/csize-class.md) содержащий размер текста для кнопки автоматического сокрытия.

## <a name="cmfcautohidebuttonisactive"></a><a name="isactive"></a>CMFCAutoHideButton::Активный

Указывает, активна ли кнопка автоматического скрытия.

```
BOOL IsActive() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если кнопка автоматического укрытия активна; FALSE в противном случае.

### <a name="remarks"></a>Примечания

Кнопка автоматической скрытия активна при отображевом окне [сопутствуемого класса CDockablePane.](../../mfc/reference/cdockablepane-class.md)

## <a name="cmfcautohidebuttonishorizontal"></a><a name="ishorizontal"></a>CMFCAutoHideButton::Горизонт

Определяет, является кнопка автоматического скрытия горизонтальной или вертикальной.

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если кнопка горизонтальная; 0 в противном случае.

### <a name="remarks"></a>Примечания

При его создании фреймворк определяет ориентацию объекта [CMFCAutoHideButton.](../../mfc/reference/cmfcautohidebutton-class.md)  Вы можете контролировать ориентацию с помощью параметра *dwAlignment* в [cmFCAutoHideButton::Create](#create) метод.

## <a name="cmfcautohidebuttonistop"></a><a name="istop"></a>CMFCAutoHideButton::IsTop

```
BOOL IsTop() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebuttonisvisible"></a><a name="isvisible"></a>CMFCAutoHideButton::Видимо

Указывает, видна ли кнопка автоматической скрытия.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если кнопка видна; FALSE в противном случае.

## <a name="cmfcautohidebuttonondraw"></a><a name="ondraw"></a>CMFCAutoHideButton::Ondraw

Этот метод вызывается платформой при рисовании кнопки автоматического скрытия.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

### <a name="remarks"></a>Примечания

Если вы хотите настроить внешний вид автоматических кнопок в приложении, создайте новый класс, полученный из. `CMFCAutoHideButton` В вашем производном классе переопределить этот метод.

## <a name="cmfcautohidebuttonondrawborder"></a><a name="ondrawborder"></a>CMFCAutoHideButton::OndrawBorder

Этот метод вызывается платформой при рисовании границ кнопки автоматического скрытия.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rectBounds*<br/>
(в) Ограничивающий прямоугольник кнопки автоматической скрытности.

*rectBorderSize*<br/>
(в) Толщина границы для каждой стороны кнопки автоматической скрытности.

### <a name="remarks"></a>Примечания

Если вы хотите настроить границу каждой кнопки автоматической скрытности в `CMFCAutoHideButton`приложении, создайте новый класс, полученный из . В вашем производном классе переопределить этот метод.

## <a name="cmfcautohidebuttononfillbackground"></a><a name="onfillbackground"></a>CMFCAutoHideButton::Onfillbackground

Этот метод вызывается платформой при заливке фона кнопки автоматического скрытия.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Ограничивающий прямоугольник кнопки автоматической скрытности.

### <a name="remarks"></a>Примечания

Если вы хотите настроить фон для автоматических кнопок в приложении, `CMFCAutoHideButton`создайте новый класс, полученный из . В вашем производном классе переопределить этот метод.

## <a name="cmfcautohidebuttonshowattachedwindow"></a><a name="showattachedwindow"></a>CMFCAutoHideButton::ShowAttachedWindow

Показывает или скрывает связанный [CDockablePane класса](../../mfc/reference/cdockablepane-class.md).

```cpp
void ShowAttachedWindow(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
(в) Boolean, который определяет, показывает ли этот `CDockablePane`метод прилагается .

## <a name="cmfcautohidebuttonshowbutton"></a><a name="showbutton"></a>CMFCAutoHideButton::ShowButton

Показывает или скрывает кнопку автоматического скрытия.

```
virtual void ShowButton(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
(в) Булеан, который определяет, следует ли показывать кнопку автоматической скрыть.

## <a name="cmfcautohidebuttonmove"></a><a name="move"></a>CMFCAutoHideButton::Перемещение

```cpp
void Move(int nOffset);
```

### <a name="parameters"></a>Параметры

(в) *nOffset*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebuttonreplacepane"></a><a name="replacepane"></a>CMFCAutoHideButton::ReplacePane

```cpp
void ReplacePane(CDockablePane* pNewBar);
```

### <a name="parameters"></a>Параметры

(в) *pNewBar*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebuttonunsetautohidemode"></a><a name="unsetautohidemode"></a>CMFCAutoHideButton::UnsetAutoHideMode

Отключение режима автоматического скрытия.

```
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```

### <a name="parameters"></a>Параметры

*pFirstBarinGroup*<br/>
(в) Указатель на первый бар в группе.

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebuttonhighlightbutton"></a><a name="highlightbutton"></a>CMFCAutoHideButton::HighlightButton

Основные кнопки автоматического укрытия.

```
virtual void HighlightButton(BOOL bHighlight);
```

### <a name="parameters"></a>Параметры

*bHighlight*<br/>
Определяет новое состояние кнопки автоматического укрытия. TRUE указывает на то, что кнопка выделена, FALSE указывает, что кнопка не выделена.

### <a name="remarks"></a>Примечания

## <a name="cmfcautohidebuttonishighlighted"></a><a name="ishighlighted"></a>CMFCAutoHideButton::Ishighlight

Возвращает состояние выделения кнопки автоматического укрытия.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если кнопка автоматического укрытия выделена; в противном случае FALSE.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)<br/>
[Класс CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)
