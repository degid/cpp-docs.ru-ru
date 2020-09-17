---
title: Класс CListView
ms.date: 11/04/2016
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
ms.openlocfilehash: d7f3b7c43d98c4f2c42d0c27c8e224f33e4b3301
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749124"
---
# <a name="clistview-class"></a>Класс CListView

Упрощает использование управления списком и [CListCtrl](../../mfc/reference/clistctrl-class.md), класса, который инкапсулирует функциональность управления списком, с архитектурой просмотра документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CListView : public CCtrlView
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CListView:CListView](#clistview)|Формирует объект `CListView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CListView:GetListCtrl](#getlistctrl)|Возвращает элемент управления списка, связанный с представлением.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CListView::RemoveImageList](#removeimagelist)|Удаляет указанный список изображений из представления списка.|

## <a name="remarks"></a>Примечания

Для получения дополнительной информации об этой [CView](../../mfc/reference/cview-class.md) архитектуре см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>Требования

**Заголовок:** afxcview.h

## <a name="clistviewclistview"></a><a name="clistview"></a>CListView:CListView

Формирует объект `CListView`.

```
CListView();
```

## <a name="clistviewgetlistctrl"></a><a name="getlistctrl"></a>CListView:GetListCtrl

Вызовите эту функцию участника, чтобы получить ссылку на элемент управления списка, связанный с представлением.

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент управления списком, связанный с представлением.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

## <a name="clistviewremoveimagelist"></a><a name="removeimagelist"></a>CListView::RemoveImageList

Удаляет указанный список изображений из представления списка.

```cpp
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>Параметры

*nImageList*<br/>
Нулевой индекс изображения для удаления.

## <a name="see-also"></a>См. также раздел

[MFC Образец ROWLIST](../../overview/visual-cpp-samples.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)
