---
title: Класс COleUpdateDialog
ms.date: 11/04/2016
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
helpviewer_keywords:
- COleUpdateDialog [MFC], COleUpdateDialog
- COleUpdateDialog [MFC], DoModal
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
ms.openlocfilehash: 9e2c7a8d79ebf5e6483a06354b280e474d7b8e61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374839"
---
# <a name="coleupdatedialog-class"></a>Класс COleUpdateDialog

Используется в особых случаях в диалоговом окне OLE "Изменить ссылки", которое используется при необходимости обновления только существующих связанных или внедренных объектов в документе.

## <a name="syntax"></a>Синтаксис

```
class COleUpdateDialog : public COleLinksDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeUpdateДиалог::COleUpdateДиалог](#coleupdatedialog)|Формирует объект `COleUpdateDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeUpdateДиалог::DoModal](#domodal)|Отображает диалоговую коробку **Edit Links** в режиме обновления.|

## <a name="remarks"></a>Примечания

Для получения дополнительной информации о OLE конкретных диалоговых коробок, [см.](../../mfc/dialog-boxes-in-ole.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

[COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

`COleUpdateDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

## <a name="coleupdatedialogcoleupdatedialog"></a><a name="coleupdatedialog"></a>ColeUpdateДиалог::COleUpdateДиалог

Формирует объект `COleUpdateDialog`.

```
explicit COleUpdateDialog(
    COleDocument* pDoc,
    BOOL bUpdateLinks = TRUE,
    BOOL bUpdateEmbeddings = FALSE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Указывает на документ, содержащий ссылки, которые могут нуждаться в обновлении.

*bUpdateLinks*<br/>
Пометить, определяющий, должны ли быть обновлены связанные объекты.

*bUpdateEmbeddings*<br/>
Пометить, определяющий, должны ли быть обновлены встроенные объекты.

*pParentWnd*<br/>
Указывает на объект окна родителя `CWnd`или владельца (типа), к которому принадлежит объект диалога. Если это NULL, родительское окно окна диалогов будет установлено на основное окно приложения.

### <a name="remarks"></a>Примечания

Эта функция строит `COleUpdateDialog` только объект. Для отображения диалогового окна позвоните [в DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Этот класс следует использовать, а не `COleLinksDialog` когда требуется обновлять только существующие связанные или встроенные элементы.

## <a name="coleupdatedialogdomodal"></a><a name="domodal"></a>ColeUpdateДиалог::DoModal

Отображает диалоговую коробку Edit Links в режиме обновления.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если диалоговая коробка вернулась успешно.

- IDCANCEL, если ни один из связанных или встроенных элементов в текущем документе не нуждается в обновлении.

- IDABORT, если произошла ошибка. Если IDABORT возвращается, позвоните в функцию [COleDialog::GetLastError,](../../mfc/reference/coledialog-class.md#getlasterror) чтобы получить больше информации о типе ошибки, которая произошла. Список возможных ошибок [OleUIEditLinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) можно узнать в SDK Windows.

### <a name="remarks"></a>Примечания

Все ссылки и/или встраивания обновляются, если пользователь не выберет кнопку «Отмена».

## <a name="see-also"></a>См. также раздел

[MFC Образец OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)
