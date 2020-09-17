---
title: Класс CHtmlEditView
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
ms.openlocfilehash: 20d4586c1ae45e5f3f56c0adbb1ecb1757084fd7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752320"
---
# <a name="chtmleditview-class"></a>Класс CHtmlEditView

Предоставляет функции платформы редактирования WebBrowser в контексте архитектуры документов или представлений MFC.

## <a name="syntax"></a>Синтаксис

```
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHtmlEditView::HtmlEditView](#chtmleditview)|Формирует объект `CHtmlEditView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHtmlEditView::Создание](#create)|Создает новый объект окна.|
|[CHtmlEditView::GetDHtmlДокумент](#getdhtmldocument)|Возвращает `IHTMLDocument2` интерфейс в текущем документе.|
|[CHtmlEditView::GetStartDocument](#getstartdocument)|Извлекает имя документа по умолчанию для этого представления.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CHtmlView](../../mfc/reference/chtmlview-class.md)

`CHtmlEditView`

## <a name="requirements"></a>Требования

**Заголовок:** afxhtml.h

## <a name="chtmleditviewchtmleditview"></a><a name="chtmleditview"></a>CHtmlEditView::HtmlEditView

Формирует объект `CHtmlEditView`.

```
CHtmlEditView();
```

## <a name="chtmleditviewcreate"></a><a name="create"></a>CHtmlEditView::Создание

Создает новый объект окна.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>
Указывает на строку символов с нулевым завершением, которая называет класс Windows. Имя класса может быть любым именем, зарегистрированным в глобальной функции [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) или функции `RegisterClass` Windows. Если NULL, использует предопределенные атрибуты [CFrameWnd](../../mfc/reference/cframewnd-class.md) по умолчанию.

*lpszWindowName*<br/>
Указывает на строку символов с нулевым завершением, представляющую имя окна.

*dwStyle*<br/>
Определяет атрибуты стиля окна. По умолчанию установлены стили WS_VISIBLE и WS_CHILD Windows.

*rect*<br/>
Ссылка на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) с указанием размера и положения окна. Значение *rectDefault* позволяет Windows указать размер и положение нового окна.

*pParentWnd*<br/>
Указатель на родительское окно элемента управления.

*nID*<br/>
Идентификационный номер представления. По умолчанию, установлен на AFX_IDW_PANE_FIRST.

*pContext*<br/>
Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md). NULL по умолчанию.

### <a name="remarks"></a>Примечания

Этот метод также вызовет `Navigate` содержащийся метод WebBrowser для загрузки документа по умолчанию (см. [CHtmlEditView::GetStartDocument).](#getstartdocument)

## <a name="chtmleditviewgetdhtmldocument"></a><a name="getdhtmldocument"></a>CHtmlEditView::GetDHtmlДокумент

Возвращает `IHTMLDocument2` интерфейс в текущем документе.

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Параметры

*ppДокумент*<br/>
Интерфейс [IHTMLDocument2.](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\))

## <a name="chtmleditviewgetstartdocument"></a><a name="getstartdocument"></a>CHtmlEditView::GetStartDocument

Извлекает имя документа по умолчанию для этого представления.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>См. также раздел

[Образец HTMLEdit](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
