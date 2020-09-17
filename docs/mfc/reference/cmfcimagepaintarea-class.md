---
title: Класс перечисление CMFCImagePaintArea
ms.date: 11/04/2016
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
ms.openlocfilehash: ee960b27651489ac1c196789d41a6c5ee396b260
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831155"
---
# <a name="cmfcimagepaintarea-class"></a>Класс перечисление CMFCImagePaintArea

Предоставляет область изображения, используемую для изменения изображения в диалоговом окне Редактор изображений.

## <a name="syntax"></a>Синтаксис

```
class CMFCImagePaintArea : public CButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|-|-|
|[Перечисление CMFCImagePaintArea:: перечисление CMFCImagePaintArea](#cmfcimagepaintarea)|Формирует объект `CMFCImagePaintArea`.|
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[Перечисление CMFCImagePaintArea:: Мода](#getmode)|Извлекает текущий режим рисования.|
|[Перечисление CMFCImagePaintArea:: Сетбитмап](#setbitmap)|Задает точечный рисунок для области изображения.|
|[Перечисление CMFCImagePaintArea:: Сетколор](#setcolor)|Задает текущий цвет рисования.|
|[Перечисление CMFCImagePaintArea:: SetMode](#setmode)|Задает текущий режим рисования.|

### <a name="remarks"></a>Примечания

Данный класс не предназначен для непосредственного использования в коде.

Платформа использует этот класс для вывода области изображения в диалоговом окне редактора изображений. Дополнительные сведения о диалоговом окне Редактор изображений см. в разделе [класс кмфЦимажеедитордиалог](../../mfc/reference/cmfcimageeditordialog-class.md).

## <a name="example"></a>Пример

В следующем примере показано, как создать объект `CMFCImagePaintArea` класса, задать текущий цвет рисования, установить текущий режим рисования и задать точечный рисунок для области изображения.

[!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[Перечисление CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксимажепаинтареа.h

## <a name="cmfcimagepaintareacmfcimagepaintarea"></a><a name="cmfcimagepaintarea"></a> Перечисление CMFCImagePaintArea:: перечисление CMFCImagePaintArea

Формирует объект `CMFCImagePaintArea`.

```
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```

### <a name="parameters"></a>Параметры

*ппарентдлг*\
окне Указатель на диалоговое окно, которое является родительским для редактора изображений.

## <a name="cmfcimagepaintareagetmode"></a><a name="getmode"></a> Перечисление CMFCImagePaintArea:: Мода

Извлекает текущий режим рисования.

```
IMAGE_EDIT_MODE GetMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) , указывающее текущий режим рисования.

## <a name="cmfcimagepaintareasetbitmap"></a><a name="setbitmap"></a> Перечисление CMFCImagePaintArea:: Сетбитмап

Задает точечный рисунок для области изображения.

```cpp
void SetBitmap(CBitmap* pBitmap);
```

### <a name="parameters"></a>Параметры

*пбитмап*\
окне Новое растровое изображение для вывода.

### <a name="remarks"></a>Примечания

Если *пбитмап* имеет значение null, этот метод устанавливает размер изменяемой области рисования равным нулю. В противном случае размер изменяемой области заливки устанавливается равным размеру указанного растрового изображения.

## <a name="cmfcimagepaintareasetcolor"></a><a name="setcolor"></a> Перечисление CMFCImagePaintArea:: Сетколор

Задает текущий цвет рисования.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*\
окне Новый цвет рисования.

### <a name="remarks"></a>Примечания

При выборе цвета на панели палитры редактора изображений или палитре цветов платформа вызывает этот метод для обновления текущего цвета рисования. Исходный цвет рисования — черный (значение COLORREF 0).

Цвет рисования используется диалоговым окном Редактор изображений для всех режимов рисования, кроме IMAGE_EDIT_MODE_COLOR. Дополнительные сведения о режимах рисования см. в разделе [перечисление CMFCImagePaintArea:: IMAGE_EDIT_MODE enumeration](cmfcimagepaintarea-image-edit-mode-enumeration.md).

## <a name="cmfcimagepaintareasetmode"></a><a name="setmode"></a> Перечисление CMFCImagePaintArea:: SetMode

Задает текущий режим рисования.

```cpp
void SetMode(IMAGE_EDIT_MODE mode);
```

### <a name="parameters"></a>Параметры

*режима*\
окне Значение [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) , указывающее текущий режим рисования.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс КмфЦимажеедитордиалог](../../mfc/reference/cmfcimageeditordialog-class.md)
