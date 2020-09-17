---
title: Класс COleLinksDialog
ms.date: 11/04/2016
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
ms.openlocfilehash: f120678c822749c8f27c3c56c95fcdd54647aca3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374936"
---
# <a name="colelinksdialog-class"></a>Класс COleLinksDialog

Используется для диалогового окна OLE "Изменить ссылки".

## <a name="syntax"></a>Синтаксис

```
class COleLinksDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeLinksДиалог::COleLinksДиалог](#colelinksdialog)|Формирует объект `COleLinksDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeLinksDialog::DoModal](#domodal)|Отображает диалоговую коробку OLE Edit Links.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleLinksDialog::m_el](#m_el)|Структура типа OLEUIEDITLINKS, которая контролирует поведение диалогового окна.|

## <a name="remarks"></a>Примечания

Создайте объект `COleLinksDialog` класса, когда вы хотите вызвать этот диалоговый ящик. После `COleLinksDialog` построения объекта можно использовать [структуру m_el](#m_el) для инициализации значений или состояний элементов управления в диалоговом поле. Структура `m_el` типа OLEUIEDITLINKS. Для получения дополнительной информации об [использовании](#domodal) этого класса диалогов см.

> [!NOTE]
> Этот класс используется с генерируемым приложением Wizard.?

Для получения дополнительной информации, см. [OLEUIEDITLINKS](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) структуры в Windows SDK.

Для получения дополнительной информации о OLE конкретных диалоговых коробок, [см.](../../mfc/dialog-boxes-in-ole.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleLinksDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

## <a name="colelinksdialogdomodal"></a><a name="domodal"></a>ColeLinksDialog::DoModal

Отображает диалоговую коробку OLE Edit Links.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если диалоговая коробка была успешно отображана.

- IDCANCEL, если пользователь отменил диалоговую будку.

- IDABORT, если произошла ошибка. Если IDABORT возвращается, `COleDialog::GetLastError` позвоните функции участника, чтобы получить больше информации о типе ошибки, которая произошла. Список возможных ошибок [OleUIEditLinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) можно узнать в SDK Windows.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные элементы управления диалоговой коробкой, установив элементы [структуры m_el,](#m_el) вы должны сделать это перед вызовом, `DoModal`но после построения объекта диалога.

## <a name="colelinksdialogcolelinksdialog"></a><a name="colelinksdialog"></a>ColeLinksДиалог::COleLinksДиалог

Формирует объект `COleLinksDialog`.

```
COleLinksDialog (
    COleDocument* pDoc,
    CView* pView,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Указывает на документ OLE, содержащий ссылки, которые будут отредактированы.

*pView*<br/>
Указывает на текущий вид на *pDoc*.

*dwFlags*<br/>
Флаг создания, содержащий 0 или ELF_SHOWHELP, чтобы указать, будет ли отображаться кнопка справки при отображении диалогового окна.

*pParentWnd*<br/>
Указывает на объект окна родителя `CWnd`или владельца (типа), к которому принадлежит объект диалога. Если это NULL, родительское окно окна диалогов устанавливается на основное окно приложения.

### <a name="remarks"></a>Примечания

Эта функция строит `COleLinksDialog` только объект. Чтобы отобразить диалоговую будку, позвоните в функцию [DoModal.](#domodal)

## <a name="colelinksdialogm_el"></a><a name="m_el"></a>ColeLinksДиалогог::m_el

Структура типа OLEUIEDITLINKS используется для управления поведением диалогового окна Edit Links.

```
OLEUIEDITLINKS m_el;
```

### <a name="remarks"></a>Примечания

Члены этой структуры могут быть изменены либо непосредственно, либо через функции членов.

Для получения дополнительной информации, см. [OLEUIEDITLINKS](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) структуры в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
