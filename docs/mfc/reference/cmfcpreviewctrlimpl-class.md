---
title: Класс CMFCPreviewCtrlImpl
ms.date: 11/04/2016
f1_keywords:
- CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::Create
- AFXWIN/CMFCPreviewCtrlImpl::Destroy
- AFXWIN/CMFCPreviewCtrlImpl::Focus
- AFXWIN/CMFCPreviewCtrlImpl::GetDocument
- AFXWIN/CMFCPreviewCtrlImpl::Redraw
- AFXWIN/CMFCPreviewCtrlImpl::SetDocument
- AFXWIN/CMFCPreviewCtrlImpl::SetHost
- AFXWIN/CMFCPreviewCtrlImpl::SetPreviewVisuals
- AFXWIN/CMFCPreviewCtrlImpl::SetRect
- AFXWIN/CMFCPreviewCtrlImpl::DoPaint
- AFXWIN/CMFCPreviewCtrlImpl::m_clrBackColor
- AFXWIN/CMFCPreviewCtrlImpl::m_clrTextColor
- AFXWIN/CMFCPreviewCtrlImpl::m_font
- AFXWIN/CMFCPreviewCtrlImpl::m_pDocument
helpviewer_keywords:
- CMFCPreviewCtrlImpl [MFC], CMFCPreviewCtrlImpl
- CMFCPreviewCtrlImpl [MFC], Create
- CMFCPreviewCtrlImpl [MFC], Destroy
- CMFCPreviewCtrlImpl [MFC], Focus
- CMFCPreviewCtrlImpl [MFC], GetDocument
- CMFCPreviewCtrlImpl [MFC], Redraw
- CMFCPreviewCtrlImpl [MFC], SetDocument
- CMFCPreviewCtrlImpl [MFC], SetHost
- CMFCPreviewCtrlImpl [MFC], SetPreviewVisuals
- CMFCPreviewCtrlImpl [MFC], SetRect
- CMFCPreviewCtrlImpl [MFC], DoPaint
- CMFCPreviewCtrlImpl [MFC], m_clrBackColor
- CMFCPreviewCtrlImpl [MFC], m_clrTextColor
- CMFCPreviewCtrlImpl [MFC], m_font
- CMFCPreviewCtrlImpl [MFC], m_pDocument
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
ms.openlocfilehash: 0c0a594a84b45ce7bf6f2c2fa5d1a547fa10eaa6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751848"
---
# <a name="cmfcpreviewctrlimpl-class"></a>Класс CMFCPreviewCtrlImpl

Этот класс реализует окно, которое помещается на окно хоста, предоставленное Shell для Rich Preview.

## <a name="syntax"></a>Синтаксис

```
class CMFCPreviewCtrlImpl : public CWnd;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCPreviewCtrlImpl:: »CMFCPreviewCtrlImpl](#dtor)|Уничтожает объект управления предварительным просмотром.|
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Строит объект управления предварительным просмотром.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::Создание](#create)|Перегружен. Для создания окна Windows был вызван обработчик Rich Preview.|
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|Вызывается Rich Preview обработчик, когда он должен уничтожить этот контроль.|
|[CMFCPreviewCtrlImpl:Фокус](#focus)|Устанавливает фокус на этот элемент управления.|
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|Возвращает документ, подключенный к этому элементу предварительного просмотра.|
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|Говорит этому элементу перерисовать.|
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|Вызывается обработчиком предварительного просмотра для создания взаимосвязи между реализацией документа и контролем предварительного просмотра.|
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|Устанавливает новый элемент управления.|
|[CMFCPreviewCtrlImpl::SetPreviewВизуальные](#setpreviewvisuals)|Вызывается Rich Preview обработчик, когда он должен установить визуальные эффекты богатого содержимого предварительного просмотра.|
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|Устанавливает новый прямоугольник для этого элемента управления.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|Вызывается инфраструктурой для отобрагиваемого предварительного просмотра.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|Фоновый цвет окна предварительного просмотра.|
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|Текстовый цвет окна предварительного просмотра.|
|[CMFCPreviewCtrlImpl::m_font](#m_font)|Шрифт, используемый для отображения текста в окне предварительного просмотра.|
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|Указатель на документ, содержимое которого просматривается в элементе управления.|

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="cmfcpreviewctrlimpl"></a>CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl

Строит объект управления предварительным просмотром.

### <a name="syntax"></a>Синтаксис

CMFCPreviewCtrlImpl();

## <a name="cmfcpreviewctrlimplcreate"></a><a name="create"></a>CMFCPreviewCtrlImpl::Создание

Перегружен. Для создания окна Windows был вызван обработчик Rich Preview.

### <a name="syntax"></a>Синтаксис

```
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc
);
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc,
   CCreateContext* pContext
);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
Ручка к окну хоста, поставляемая Shell для Rich Preview.

*Кнр*<br/>
Определяет начальный размер и положение окна.

*pContext*<br/>
Указатель на контекст создания.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если создание прошло успешно; в противном случае — значение FALSE.

## <a name="cmfcpreviewctrlimpldestroy"></a><a name="destroy"></a>CMFCPreviewCtrlImpl::Destroy

Вызывается Rich Preview обработчик, когда он должен уничтожить этот контроль.

### <a name="syntax"></a>Синтаксис

```
virtual void Destroy();
```

## <a name="cmfcpreviewctrlimpldopaint"></a><a name="dopaint"></a>CMFCPreviewCtrlImpl::DoPaint

Вызывается инфраструктурой для отобрагиваемого предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
virtual void DoPaint(
   CPaintDC* pDC
);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства для рисования.

## <a name="cmfcpreviewctrlimplfocus"></a><a name="focus"></a>CMFCPreviewCtrlImpl:Фокус

Устанавливает фокус на этот элемент управления.

### <a name="syntax"></a>Синтаксис

```
virtual void Focus();
```

## <a name="cmfcpreviewctrlimplgetdocument"></a><a name="getdocument"></a>CMFCPreviewCtrlImpl::GetDocument

Возвращает документ, подключенный к этому элементу предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
ATL::IDocument* GetDocument();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на документ, содержимое которого просматривается в элементе управления.

## <a name="cmfcpreviewctrlimplm_clrbackcolor"></a><a name="m_clrbackcolor"></a>CMFCPreviewCtrlImpl::m_clrBackColor

Фоновый цвет окна предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
COLORREF m_clrBackColor;
```

## <a name="cmfcpreviewctrlimplm_clrtextcolor"></a><a name="m_clrtextcolor"></a>CMFCPreviewCtrlImpl::m_clrTextColor

Текстовый цвет окна предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
COLORREF m_clrTextColor;
```

## <a name="cmfcpreviewctrlimplm_font--font-used-to-display-text-in-the-preview-window"></a><a name="m_font"></a>CMFCPreviewCtrlImpl::m_font шрифт используется для отображения текста в окне предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
CFont m_font;
```

## <a name="cmfcpreviewctrlimplm_pdocument"></a><a name="m_pdocument"></a>CMFCPreviewCtrlImpl::m_pDocument

Указатель на документ, содержимое которого просматривается в элементе управления.

### <a name="syntax"></a>Синтаксис

```
ATL::IDocument* m_pDocument;
```

## <a name="cmfcpreviewctrlimplredraw"></a><a name="redraw"></a>CMFCPreviewCtrlImpl::Redraw

Говорит этому элементу перерисовать.

### <a name="syntax"></a>Синтаксис

```
virtual void Redraw();
```

## <a name="cmfcpreviewctrlimplsetdocument"></a><a name="setdocument"></a>CMFCPreviewCtrlImpl::SetDocument

Вызывается обработчиком предварительного просмотра для создания взаимосвязи между реализацией документа и контролем предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```cpp
void SetDocument(
   IDocument* pDocument
);
```

### <a name="parameters"></a>Параметры

*pДокумент*<br/>
Указатель на реализацию документа.

## <a name="cmfcpreviewctrlimplsethost"></a><a name="sethost"></a>CMFCPreviewCtrlImpl::SetHost

Устанавливает новый элемент управления.

### <a name="syntax"></a>Синтаксис

```
virtual void SetHost(
   HWND hWndParent
);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
Дескриптор нового родительского окна.

## <a name="cmfcpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>CMFCPreviewCtrlImpl::SetPreviewВизуальные

Вызывается Rich Preview обработчик, когда он должен установить визуальные эффекты богатого содержимого предварительного просмотра.

### <a name="syntax"></a>Синтаксис

```
virtual void SetPreviewVisuals(
   COLORREF clrBack,
   COLORREF clrText,
   const LOGFONTW *plf
);
```

### <a name="parameters"></a>Параметры

*clrBack*<br/>
Фоновый цвет окна предварительного просмотра.

*clrText*<br/>
Текстовый цвет окна предварительного просмотра.

*Plf*<br/>
Шрифт, используемый для отображения текста в окне предварительного просмотра.

## <a name="cmfcpreviewctrlimplsetrect"></a><a name="setrect"></a>CMFCPreviewCtrlImpl::SetRect

Устанавливает новый прямоугольник для этого элемента управления.

### <a name="syntax"></a>Синтаксис

```
virtual void SetRect(
   const RECT* prc,
   BOOL bRedraw
);
```

### <a name="parameters"></a>Параметры

*Кнр*<br/>
Определяет новый размер и положение элемента предварительного просмотра.

*bRedraw*<br/>
Определяет, следует ли перерисовывать элемент управления.

### <a name="remarks"></a>Примечания

Обычно при повторном размере элемента управления хоста устанавливается новый прямоугольник.

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="dtor"></a>CMFCPreviewCtrlImpl:: »CMFCPreviewCtrlImpl

Уничтожает объект управления предварительным просмотром.

### <a name="syntax"></a>Синтаксис

```
virtual ~CMFCPreviewCtrlImpl();
```
