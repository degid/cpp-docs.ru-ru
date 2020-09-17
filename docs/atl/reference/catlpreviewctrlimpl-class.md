---
title: Класс Катлпревиевктрлимпл
ms.date: 11/04/2016
f1_keywords:
- CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Create
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Destroy
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Focus
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::OnPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Redraw
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetHost
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetPreviewVisuals
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetRect
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::DoPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_plf
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrBack
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrText
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
ms.openlocfilehash: fd94d0d6fe43d80b45def3f747c7b7d558de31d4
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167881"
---
# <a name="catlpreviewctrlimpl-class"></a>Класс Катлпревиевктрлимпл

Этот класс является реализацией библиотеки ATL окна, размещенной в главном окне, предоставляемом оболочкой для расширенного просмотра.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Катлпревиевктрлимпл:: ~ Катлпревиевктрлимпл](#dtor)|Разструктура объекта элемента управления предварительной версии.|
|[Катлпревиевктрлимпл:: Катлпревиевктрлимпл](#catlpreviewctrlimpl)|Конструирует объект элемента управления предварительной версии.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Катлпревиевктрлимпл:: Create](#create)|Вызывается расширенным обработчиком просмотра для создания окна Windows.|
|[Катлпревиевктрлимпл::D естрой](#destroy)|Вызывается расширенным обработчиком просмотра, когда ему требуется уничтожить этот элемент управления.|
|[Катлпревиевктрлимпл:: Focus](#focus)|Устанавливает фокус на этот элемент управления.|
|[Катлпревиевктрлимпл:: onpain](#onpaint)|Обрабатывает сообщение WM_PAINT.|
|[Катлпревиевктрлимпл:: перерисовка](#redraw)|Указывает, что этот элемент управления должен перерисовываться.|
|[Катлпревиевктрлимпл:: Сесост](#sethost)|Задает новый родительский элемент для этого элемента управления.|
|[Катлпревиевктрлимпл:: Сетпревиеввисуалс](#setpreviewvisuals)|Вызывается расширенным обработчиком просмотра, когда ему необходимо задать визуальные элементы расширенного просмотра содержимого.|
|[Катлпревиевктрлимпл:: SetRect](#setrect)|Задает новый ограничивающий прямоугольник для этого элемента управления.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[Катлпревиевктрлимпл::D Опаинт](#dopaint)|Вызывается платформой для отрисовки предварительной версии.|

### <a name="protected-constants"></a>Защищенные константы

|Имя|Описание|
|----------|-----------------|
|[Катлпревиевктрлимпл:: m_plf](#m_plf)|Шрифт, используемый для вывода текста в окне предварительного просмотра.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[Катлпревиевктрлимпл:: m_clrBack](#m_clrback)|Цвет фона окна предварительного просмотра.|
|[Катлпревиевктрлимпл:: m_clrText](#m_clrtext)|Цвет текста окна предварительного просмотра.|

## <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`TBase`

`ATL::CMessageMap`

`ATL::CWindowImplRoot<TBase>`

`ATL::CWindowImplBaseT<TBase,TWinTraits>`

[Библиотека ATL::\<квиндовимпл катлпревиевктрлимпл>](../../atl/reference/cwindowimpl-class.md)

`IPreviewCtrl`

`ATL::CAtlPreviewCtrlImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлпревиевктрлимпл.h

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="catlpreviewctrlimpl"></a>Катлпревиевктрлимпл:: Катлпревиевктрлимпл

Конструирует объект элемента управления предварительной версии.

```cpp
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="dtor"></a>Катлпревиевктрлимпл:: ~ Катлпревиевктрлимпл

Разструктура объекта элемента управления предварительной версии.

```cpp
virtual ~CAtlPreviewCtrlImpl(void);
```

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimplcreate"></a><a name="create"></a>Катлпревиевктрлимпл:: Create

Вызывается расширенным обработчиком просмотра для создания окна Windows.

```cpp
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```

### <a name="parameters"></a>Параметры

*хвндпарент*<br/>
Маркер главного окна, предоставляемый оболочкой для расширенной предварительной версии.

*PRC*<br/>
Задает начальный размер и расположение окна.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimpldestroy"></a><a name="destroy"></a>Катлпревиевктрлимпл::D естрой

Вызывается расширенным обработчиком просмотра, когда ему требуется уничтожить этот элемент управления.

```cpp
virtual void Destroy();
```

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimpldopaint"></a><a name="dopaint"></a>Катлпревиевктрлимпл::D Опаинт

Вызывается платформой для отрисовки предварительной версии.

```cpp
virtual void DoPaint(HDC hdc);
```

### <a name="parameters"></a>Параметры

*HDC*<br/>
Маркер контекста устройства для рисования.

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimplfocus"></a><a name="focus"></a>Катлпревиевктрлимпл:: Focus

Устанавливает фокус на этот элемент управления.

```cpp
virtual void Focus();
```

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimplm_clrback"></a><a name="m_clrback"></a>Катлпревиевктрлимпл:: m_clrBack

Цвет фона окна предварительного просмотра.

```cpp
COLORREF m_clrBack;
```

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimplm_clrtext"></a><a name="m_clrtext"></a>Катлпревиевктрлимпл:: m_clrText

Цвет текста окна предварительного просмотра.

```cpp
COLORREF m_clrText;
```

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimplm_plf"></a><a name="m_plf"></a>Катлпревиевктрлимпл:: m_plf

Шрифт, используемый для вывода текста в окне предварительного просмотра.

```cpp
const LOGFONTW* m_plf;
```

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimplonpaint"></a><a name="onpaint"></a>Катлпревиевктрлимпл:: onpain

Обрабатывает сообщение WM_PAINT.

```cpp
LRESULT OnPaint(
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>Параметры

*нмсг*<br/>
Задайте значение WM_PAINT.

*wParam*<br/>
Этот параметр не используется.

*lParam*<br/>
Этот параметр не используется.

*бхандлед*<br/>
При возврате этой функции она содержит значение TRUE.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 0.

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimplredraw"></a><a name="redraw"></a>Катлпревиевктрлимпл:: перерисовка

Указывает, что этот элемент управления должен перерисовываться.

```cpp
virtual void Redraw();
```

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimplsethost"></a><a name="sethost"></a>Катлпревиевктрлимпл:: Сесост

Задает новый родительский элемент для этого элемента управления.

```cpp
virtual void SetHost(HWND hWndParent);
```

### <a name="parameters"></a>Параметры

*хвндпарент*<br/>
Дескриптор нового родительского окна.

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>Катлпревиевктрлимпл:: Сетпревиеввисуалс

Вызывается расширенным обработчиком просмотра, когда ему необходимо задать визуальные элементы расширенного просмотра содержимого.

```cpp
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```

### <a name="parameters"></a>Параметры

*клрбакк*<br/>
Цвет фона окна предварительного просмотра.

*clrText*<br/>
Цвет текста окна предварительного просмотра.

*плф*<br/>
Шрифт, используемый для вывода текста в окне предварительного просмотра.

### <a name="remarks"></a>Примечания

## <a name="catlpreviewctrlimplsetrect"></a><a name="setrect"></a>Катлпревиевктрлимпл:: SetRect

Задает новый ограничивающий прямоугольник для этого элемента управления.

```cpp
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```

### <a name="parameters"></a>Параметры

*PRC*<br/>
Указывает новый размер и расположение элемента управления предварительной версии.

*bRedraw*<br/>
Указывает, следует ли перерисовать элемент управления.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)
