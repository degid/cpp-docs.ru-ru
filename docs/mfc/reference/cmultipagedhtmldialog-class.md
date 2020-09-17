---
title: Класс CmultiPageDHtmlDialog
ms.date: 03/27/2019
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
ms.openlocfilehash: 89e4830c3b5c6cb663ca2d2935adaaae3f356958
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319655"
---
# <a name="cmultipagedhtmldialog-class"></a>Класс CmultiPageDHtmlDialog

Многостраничное диалоговое окно последовательно отображает несколько HTML-страниц и обрабатывает события каждой страницы.

## <a name="syntax"></a>Синтаксис

```
class CMultiPageDHtmlDialog : public CDHtmlDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CmultipagedHtmlDialog::CmultipagedHtmlDialog](#cmultipagedhtmldialog)|Строит многостраничный (волшебник-стиль) диалоговый объект DHTML.|
|[CmultipagedHtmlDialog:::»CmultipagedHtmlDialog](#_dtorcmultipagedhtmldialog)|Уничтожает многостраничный диалоговой объект DHTML.|

## <a name="remarks"></a>Примечания

Механизмом для этого является [карта событий DHTML и URL,](dhtml-event-maps.md)которая содержит встроенные карты событий для каждой страницы.

## <a name="example"></a>Пример

Этот многостраничный диалог предполагает три HTML-ресурса, определяющих простую функциональность, похожую на мастера. На первой странице есть **кнопка Next,** вторая кнопка **Prev** и **Next,** а третья кнопка **Prev.** При нажатии одной из кнопок функция обработчика вызывает [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) для загрузки соответствующей новой страницы.

Соответствующие части классной декларации (в CMyMultiPageDlg.h):

[!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]

Соответствующие части реализации класса (в CMyMultipageDlg.cpp):

[!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[CWnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[CDialog](../../mfc/reference/cdialog-class.md)

[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)

`CMultiPageDHtmlDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdhtml.h

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="cmultipagedhtmldialog"></a>CmultipagedHtmlDialog::CmultipagedHtmlDialog

Строит многостраничный (волшебник-стиль) диалоговый объект DHTML.

```
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,
    LPCTSTR szHtmlResID = NULL,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog(
    UINT nIDTemplate,
    UINT nHtmlResID = 0,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog();
```

### <a name="parameters"></a>Параметры

*lpszTemplateName*<br/>
Строка с нулевым завершением, которая является названием ресурса шаблона диалог-бокса.

*szHtmlResID*<br/>
Строка с нулевым завершением, которая является именем ресурса HTML.

*pParentWnd*<br/>
Указатель на объект окна родителя или владельца (типа [CWnd),](../../mfc/reference/cwnd-class.md)к которому принадлежит объект диалога. Если это NULL, родительское окно объекта диалога устанавливается на основное окно приложения.

*nIDTemplate*<br/>
Содержит идентификационный номер ресурса шаблона диалогового ящика.

*nHtmlResID*<br/>
Содержит идентификационный номер ресурса HTML.

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="_dtorcmultipagedhtmldialog"></a>CmultipagedHtmlDialog:::»CmultipagedHtmlDialog

Уничтожает многостраничный диалоговой объект DHTML.

```
virtual ~CMultiPageDHtmlDialog();
```

## <a name="see-also"></a>См. также раздел

[Класс CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)
