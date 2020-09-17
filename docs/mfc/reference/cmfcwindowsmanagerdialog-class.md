---
title: CmFCWindowsManagerДиалог Класс
ms.date: 11/04/2016
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
ms.openlocfilehash: e3928c0d3ae4f607dceb99c0762277e8ea9ddbde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319829"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CmFCWindowsManagerДиалог Класс

Объект `CMFCWindowsManagerDialog` позволяет пользователю управлять окнами mDI ребенка в приложении MDI.

## <a name="syntax"></a>Синтаксис

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCWindowsManagerДиалог::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Формирует объект `CMFCWindowsManagerDialog`.|

## <a name="remarks"></a>Примечания

В `CMFCWindowsManagerDialog` приложении содержится список детских окон MDI, которые в настоящее время открыты в приложении. Пользователь может вручную управлять состоянием детских окон MDI, используя этот диалоговый ящик.

`CMFCWindowsManagerDialog`встроен внутри [класса CMDIFrameWndEx.](../../mfc/reference/cmdiframewndex-class.md) Это `CMFCWindowsManagerDialog` не класс, который вы должны создавать вручную. Вместо этого, вызов функции [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog), `CMFCWindowsManagerDialog` и он будет создавать и отображать объект.

## <a name="example"></a>Пример

Ниже приводится следующий `CMFCWindowsManagerDialog` пример, как `CMDIFrameWndEx::ShowWindowsDialog`построить объект, вызывая . Этот фрагмент кода является частью [образца демонстрации Visual Studio.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxWindowsManagerDialog.h

## <a name="cmfcwindowsmanagerdialogcmfcwindowsmanagerdialog"></a><a name="cmfcwindowsmanagerdialog"></a>CMFCWindowsManagerДиалог::CMFCWindowsManagerDialog

Строит объект [CMFCWindowsManagerDialog.](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>Параметры

*pMDIFrame*<br/>
(в) Указатель на окно родителя или владельца.

*bHelpButton*<br/>
(в) Параметр Boolean, который определяет, отображает ли фреймворк кнопку **справки.**

### <a name="remarks"></a>Примечания

Для получения дополнительной информации о визуальных менеджеров, [см.](../../mfc/visualization-manager.md)

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)
