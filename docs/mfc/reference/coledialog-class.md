---
title: Класс COleDialog
ms.date: 11/04/2016
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
ms.openlocfilehash: 6a1983d426e97dd8063aee2857dc36557aa20677
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366097"
---
# <a name="coledialog-class"></a>Класс COleDialog

Предоставляет стандартные функции для диалоговых окон OLE.

## <a name="syntax"></a>Синтаксис

```
class COleDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeDialog::GetLastError](#getlasterror)|Возвращает код ошибки в диалоговое окно.|

## <a name="remarks"></a>Примечания

Библиотека класса Фонда Майкрософт предоставляет `COleDialog`несколько классов, полученных из:

- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)

- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)

- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)

- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)

- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)

- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)

Для получения дополнительной информации о OL-специфических диалоговых ящиков, [см.](../../mfc/dialog-boxes-in-ole.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

## <a name="coledialoggetlasterror"></a><a name="getlasterror"></a>ColeDialog::GetLastError

Позвоните `GetLastError` функции участника, чтобы `DoModal` получить дополнительную информацию об ошибке при возврате IDABORT.

```
UINT GetLastError() const;
```

### <a name="return-value"></a>Возвращаемое значение

Коды ошибок, `GetLastError` возвращенные в зависимости от отображаемого окна диалога.

### <a name="remarks"></a>Примечания

Просматривайте `DoModal` функцию участника в производных классах для получения информации о конкретных сообщениях об ошибках.

## <a name="see-also"></a>См. также раздел

[Класс CCommonДиалог](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
