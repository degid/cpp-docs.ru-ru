---
title: Класс CFolderPickerDialog
ms.date: 03/27/2019
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: ed3dc151060519bce216cf4a2f3d6559d6b8937e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373849"
---
# <a name="cfolderpickerdialog-class"></a>Класс CFolderPickerDialog

Класс CFolderPickerDialog реализует CFileDialog в режиме сборщика папок.

## <a name="syntax"></a>Синтаксис

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFolderPickerДиалог::: »CFolderPickerDialog](#_dtorcfolderpickerdialog)|Деструктор.|
|[CFolderPickerДиалог::CFolderPickerDialog](#cfolderpickerdialog)|Конструктор.|

## <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[CFileDialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="cfolderpickerdialog"></a>CFolderPickerДиалог::CFolderPickerDialog

Конструктор.

```
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL,
    DWORD dwSize = 0);
```

### <a name="parameters"></a>Параметры

*lpszFolder*<br/>
Начальная папка.

*dwFlags*<br/>
Сочетание одного или нескольких флагов, которые позволяют настроить диалоговую коробку.

*pParentWnd*<br/>
Указатель на родительское или владелец окна объекта диалоговой коробки.

*dwSize*<br/>
Размер структуры OPENFILENAME.

### <a name="remarks"></a>Примечания

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="_dtorcfolderpickerdialog"></a>CFolderPickerДиалог::: »CFolderPickerDialog

Деструктор.

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
