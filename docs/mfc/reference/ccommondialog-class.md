---
title: Класс CCommonДиалог
ms.date: 11/04/2016
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
ms.openlocfilehash: 853a4756df3b70f4f33deb7159b4d1aee610092c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369447"
---
# <a name="ccommondialog-class"></a>Класс CCommonДиалог

Базовый класс для классов, которые инкапсулируют функцию общих диалоговых окон Windows.

## <a name="syntax"></a>Синтаксис

```
class CCommonDialog : public CDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCommonДиалог::CCommonДиалог](#ccommondialog)|Формирует объект `CCommonDialog`.|

## <a name="remarks"></a>Примечания

Следующие классы инкапсулируют функциональность общих диалогов Windows:

- [CFileDialog](../../mfc/reference/cfiledialog-class.md)

- [CFontDialog](../../mfc/reference/cfontdialog-class.md)

- [CColorDialog](../../mfc/reference/ccolordialog-class.md)

- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)

- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)

- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)

- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)

- [COleDialog](../../mfc/reference/coledialog-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CCommonDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

## <a name="ccommondialogccommondialog"></a><a name="ccommondialog"></a>CCommonДиалог::CCommonДиалог

Формирует объект `CCommonDialog`.

```
explicit CCommonDialog(CWnd* pParentWnd);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указывает на объект окна родителя или владельца (типа [CWnd),](../../mfc/reference/cwnd-class.md)к которому принадлежит объект диалога. Если это NULL, родительское окно объекта диалога устанавливается на основное окно приложения.

### <a name="remarks"></a>Примечания

Смотрите [CDialog::CDialog](../../mfc/reference/cdialog-class.md#cdialog) для получения полной информации.

## <a name="see-also"></a>См. также раздел

[Класс CDialog](../../mfc/reference/cdialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFileDialog](../../mfc/reference/cfiledialog-class.md)<br/>
[Класс CFontDialog](../../mfc/reference/cfontdialog-class.md)<br/>
[Класс CColorDialog](../../mfc/reference/ccolordialog-class.md)<br/>
[Класс CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)<br/>
[Класс CPrintDialog](../../mfc/reference/cprintdialog-class.md)<br/>
[Класс CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
