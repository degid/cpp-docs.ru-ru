---
title: Класс CCtrlView
ms.date: 11/04/2016
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
helpviewer_keywords:
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
ms.openlocfilehash: f77f1c265920bd160da790647ef754c55e6dbda3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369357"
---
# <a name="cctrlview-class"></a>Класс CCtrlView

Адаптирует архитектуру "документ-представление" для распространенных элементов управления, поддерживаемых Windows 98 и Windows NT (версии 3.51 и более поздние).

## <a name="syntax"></a>Синтаксис

```
class CCtrlView : public CView
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCtrlView::CCtrlView](#cctrlview)|Формирует объект `CCtrlView`.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CCtrlview::OnDraw](#ondraw)|Вызывается фректовой для рисования с помощью заданного контекста устройства.|
|[CCtrlView::PreCreateWindow](#precreatewindow)|Вызывается до создания окна Windows, присоединенного к данному объекту класса `CCtrlView`.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|Содержит стиль по умолчанию для класса представления.|
|[CCtrlView::m_strClass](#m_strclass)|Содержит название класса Windows для класса представления.|

## <a name="remarks"></a>Примечания

Класс `CCtrlView` и его производные, [CEditView,](../../mfc/reference/ceditview-class.md) [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md)и [CRichEditView,](../../mfc/reference/cricheditview-class.md)адаптируют архитектуру просмотра документов к новым общим элементам управления, поддерживаемым версиями Windows 95/98 и Windows NT 3.51 и позже. Для получения дополнительной информации об [Document/View Architecture](../../mfc/document-view-architecture.md)архитектуре просмотра документов см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CCtrlView`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cctrlviewcctrlview"></a><a name="cctrlview"></a>CCtrlView::CCtrlView

Формирует объект `CCtrlView`.

```
CCtrlView(
    LPCTSTR lpszClass,
    DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*lpszClass*<br/>
Название класса Windows класса представления.

*dwStyle*<br/>
Стиль класса представления.

### <a name="remarks"></a>Примечания

Фрейм вызывает конструктора при создании нового окна кадра или разделении окна. Переуряднетесь [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) для инициализации представления после присоединения документа. Вызов [CWnd::Создать](../../mfc/reference/cwnd-class.md#create) или [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) для создания объекта Windows.

## <a name="cctrlviewm_strclass"></a><a name="m_strclass"></a>CCtrlView::m_strClass

Содержит название класса Windows для класса представления.

```
CString m_strClass;
```

## <a name="cctrlviewm_dwdefaultstyle"></a><a name="m_dwdefaultstyle"></a>CCtrlView::m_dwDefaultStyle

Содержит стиль по умолчанию для класса представления.

```
DWORD m_dwDefaultStyle;
```

### <a name="remarks"></a>Примечания

Этот стиль применяется при создании окна.

## <a name="cctrlviewondraw"></a><a name="ondraw"></a>CCtrlview::OnDraw

Вызывается фректовой для `CCtrlView` рисования содержимого объекта с помощью заданного контекста устройства.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства, в котором происходит рисунок.

### <a name="remarks"></a>Примечания

`OnDraw`обычно требуется для отображения экрана, проходя контекст экрана устройства, указанного *pDC.*

## <a name="cctrlviewprecreatewindow"></a><a name="precreatewindow"></a>CCtrlView::PreCreateWindow

Вызывается до создания окна Windows, присоединенного к данному объекту класса `CWnd`.

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Параметры

*cs*<br/>
Структура [CREATESTRUCT.](/windows/win32/api/winuser/ns-winuser-createstructw)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если создание окна должно продолжаться; 0, чтобы указать сбой создания.

### <a name="remarks"></a>Примечания

Никогда не звоните в эту функцию напрямую.

Реализация этой функции по умолчанию проверяет имя класса окна NULL и заменяет соответствующий по умолчанию. Переизместите эту `CREATESTRUCT` функцию члена, чтобы изменить структуру до создания окна.

Каждый класс, `CCtrlView` полученный из добавляет свою `PreCreateWindow`собственную функциональность к его переопределение . По замыслу, эти `PreCreateWindow` производные не документированы. Чтобы определить стили, подходящие для каждого класса и взаимозависимости между стилями, можно изучить исходный код MFC для базового класса приложения. Если вы решите `PreCreateWindow`переопределить, вы можете определить, обеспечивают ли стили, используемые в базовом классе приложения, необходимую функциональность, используя информацию, собранную из исходного кода MFC.

Для получения дополнительной информации об изменении стилей окна [см.](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>См. также раздел

[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CTreeView](../../mfc/reference/ctreeview-class.md)<br/>
[Класс CListView](../../mfc/reference/clistview-class.md)<br/>
[Класс CrichEditView](../../mfc/reference/cricheditview-class.md)
