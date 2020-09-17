---
title: Класс CHtmlEditCtrl
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
helpviewer_keywords:
- CHtmlEditCtrl [MFC], CHtmlEditCtrl
- CHtmlEditCtrl [MFC], Create
- CHtmlEditCtrl [MFC], GetDHtmlDocument
- CHtmlEditCtrl [MFC], GetStartDocument
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
ms.openlocfilehash: 05063c62e9f7a5d88d3fecde842f979725200f98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366841"
---
# <a name="chtmleditctrl-class"></a>Класс CHtmlEditCtrl

Предоставляет функциональные возможности элемента управления ActiveX WebBrowser в окне MFC.

## <a name="syntax"></a>Синтаксис

```
class CHtmlEditCtrl: public CWnd,
    public CHtmlEditCtrlBase<CHtmlEditCtrl>
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHtmlEditCtrl::HtmlEditCtrl](#chtmleditctrl)|Формирует объект `CHtmlEditCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHtmlEditCtrl:Создание](#create)|Создает управление WebBrowser ActiveX и прикрепляет его к объекту. `CHtmlEditCtrl` Эта функция автоматически переносит управление WebBrowser ActiveX в режим отодевного изменения.|
|[CHtmlEditCtrl:GetDHtmlDocument](#getdhtmldocument)|Извлекает интерфейс [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) на документ, который в настоящее время загружен в элемент управления WebBrowser.|
|[CHtmlEditCtrl:GetStartDocument](#getstartdocument)|Извлекает URL-адрес в документ по умолчанию для загрузки в элементе управления WebBrowser.|

## <a name="remarks"></a>Примечания

После создания размещаемый элемент управления WebBrowser автоматически перекладывается в режим отодена.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHtmlEditCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxhtml.h

## <a name="chtmleditctrlchtmleditctrl"></a><a name="chtmleditctrl"></a>CHtmlEditCtrl::HtmlEditCtrl

Формирует объект `CHtmlEditCtrl`.

```
CHtmlEditCtrl();
```

## <a name="chtmleditctrlcreate"></a><a name="create"></a>CHtmlEditCtrl:Создание

Создает управление WebBrowser ActiveX и прикрепляет его к объекту. `CHtmlEditCtrl` Контроль WebBrowser ActiveX автоматически переходит к документу по умолчанию, а затем помещается в режиме отодействия с помощью этой функции.

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*lpszWindowName*<br/>
Этот параметр не используется.

*dwStyle*<br/>
Этот параметр не используется.

*rect*<br/>
Определяет размер и положение элемента управления.

*pParentWnd*<br/>
Определяет родительское окно элемента управления. Она не должна быть NULL.

*nID*<br/>
Уведомляет идентификатор элемента управления.

*pContext*<br/>
Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="chtmleditctrlgetdhtmldocument"></a><a name="getdhtmldocument"></a>CHtmlEditCtrl:GetDHtmlDocument

Получение интерфейса [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) на документе, который в настоящее время загружен в элемент управления WebBrowser

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Параметры

*ppДокумент*<br/>
Интерфейс документа.

## <a name="chtmleditctrlgetstartdocument"></a><a name="getstartdocument"></a>CHtmlEditCtrl:GetStartDocument

Извлекает URL-адрес в документ по умолчанию для загрузки в элементе управления WebBrowser.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
