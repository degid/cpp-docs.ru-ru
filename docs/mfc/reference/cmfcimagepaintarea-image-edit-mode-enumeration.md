---
title: Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE
ms.date: 11/04/2016
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
ms.openlocfilehash: 37c877cc8562a9479535d9c6132e49e7c9b7e82f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831142"
---
# <a name="cmfcimagepaintareaimage_edit_mode-enumeration"></a>Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE

Задает режим рисования, используемый для изменения изображения в диалоговом окне редактора изображений.

## <a name="syntax"></a>Синтаксис

```
enum IMAGE_EDIT_MODE
{
    IMAGE_EDIT_MODE_PEN = 0,
    IMAGE_EDIT_MODE_FILL,
    IMAGE_EDIT_MODE_LINE,
    IMAGE_EDIT_MODE_RECT,
    IMAGE_EDIT_MODE_ELLIPSE,
    IMAGE_EDIT_MODE_COLOR
};
```

## <a name="members"></a>Участники

|Имя|Описание|
|-|-|
|IMAGE_EDIT_MODE_PEN|Используется для рисования отдельных пикселов.|
|IMAGE_EDIT_MODE_FILL|Используется для заполнения всех смежных областей, содержащих цвет в текущем положении курсора.|
|IMAGE_EDIT_MODE_LINE|Используется для рисования линии.|
|IMAGE_EDIT_MODE_RECT|Используется для рисования прямоугольника.|
|IMAGE_EDIT_MODE_ELLIPSE|Используется для рисования эллипса.|
|IMAGE_EDIT_MODE_COLOR|Используется для установки текущего цвета на цвет в текущем положении курсора.|

### <a name="remarks"></a>Примечания

`CMFCImagePaintArea`Классы и `CMFCImageEditorDialog` используют это перечисление для установки текущего режима рисования. Режим рисования и текущий цвет используются для изменения области изображения в диалоговом окне редактора изображений. Дополнительные сведения о `CMFCImagePaintArea` и `CMFCImageEditorDialog` см. в разделе [класс перечисление CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md) и [класс кмфЦимажеедитордиалог](../../mfc/reference/cmfcimageeditordialog-class.md).

При выборе цвета из изображения с помощью IMAGE_EDIT_MODE_COLOR режима рисования платформа устанавливает для текущего режима рисования значение IMAGE_EDIT_MODE_PEN.

## <a name="requirements"></a>Требования

**Заголовок:** афксимажепаинтареа.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс перечисление CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)<br/>
[Класс КмфЦимажеедитордиалог](../../mfc/reference/cmfcimageeditordialog-class.md)
