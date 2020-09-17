---
title: Класс КмфЦимажеедиторпалеттебар
ms.date: 11/04/2016
f1_keywords:
- CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::GetRowHeight
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable
helpviewer_keywords:
- CMFCImageEditorPaletteBar [MFC], GetRowHeight
- CMFCImageEditorPaletteBar [MFC], IsButtonExtraSizeAvailable
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
ms.openlocfilehash: 007fa94269a6a42bf076d2d75a18860896503aa1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831168"
---
# <a name="cmfcimageeditorpalettebar-class"></a>Класс КмфЦимажеедиторпалеттебар

Предоставляет функциональные возможности панели палитры для диалогового окна редактора изображений.

## <a name="syntax"></a>Синтаксис

```
class CMFCImageEditorPaletteBar : public CMFCToolBar
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[КмфЦимажеедиторпалеттебар:: Жетровхеигхт](#getrowheight)|Возвращает высоту кнопок панели инструментов. (Переопределяет [CMFCToolBar:: жетровхеигхт](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[КмфЦимажеедиторпалеттебар:: Исбуттонекстрасизеаваилабле](#isbuttonextrasizeavailable)|Определяет, может ли на панели инструментов отображаться кнопка с расширенными границами. (Переопределяет [CMFCToolBar:: исбуттонекстрасизеаваилабле](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|

### <a name="remarks"></a>Примечания

Данный класс не предназначен для непосредственного использования в коде.

Платформа использует этот класс для вывода панели палитры в диалоговом окне редактора изображений. Дополнительные сведения о диалоговом окне Редактор изображений см. в разделе [класс кмфЦимажеедитордиалог](../../mfc/reference/cmfcimageeditordialog-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[кмфкбасетулба](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[кмфЦимажеедиторпалеттебар](../../mfc/reference/cmfcimageeditorpalettebar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксимажеедитордиалог.h

## <a name="cmfcimageeditorpalettebargetrowheight"></a><a name="getrowheight"></a> КмфЦимажеедиторпалеттебар:: Жетровхеигхт

Возвращает высоту кнопок панели инструментов.

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Высота каждой кнопки на панели инструментов.

## <a name="cmfcimageeditorpalettebarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a> КмфЦимажеедиторпалеттебар:: Исбуттонекстрасизеаваилабле

Определяет, может ли на панели инструментов отображаться кнопка с расширенными границами.

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает значение FALSE.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс КмфЦимажеедитордиалог](../../mfc/reference/cmfcimageeditordialog-class.md)
