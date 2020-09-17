---
title: Класс ColeReReresizebar
ms.date: 11/04/2016
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
ms.openlocfilehash: beb0c37b6ac23310b7d5c8506fbdaf677dd74d8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376151"
---
# <a name="coleresizebar-class"></a>Класс ColeReReresizebar

Тип панели элементов управления, который поддерживает изменение размера элементов OLE "на месте".

## <a name="syntax"></a>Синтаксис

```
class COleResizeBar : public CControlBar
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeReResizebar::ColeReresizebar](#coleresizebar)|Формирует объект `COleResizeBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeReResizebar::Создание](#create)|Создает и инициализирует окно ребенка `COleResizeBar` Windows и связывает его с объектом.|

## <a name="remarks"></a>Примечания

`COleResizeBar`объекты отображаются как [CRectTracker](../../mfc/reference/crecttracker-class.md) с вылупившихся границы и внешних рефигурных ручек.

`COleResizeBar`объекты обычно являются встроенными членами объектов окна кадра, полученных из класса [COleIPFrameWnd.](../../mfc/reference/coleipframewnd-class.md)

Для получения дополнительной информации, [см.](../../mfc/activation-cpp.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[Ccontrolbar](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="coleresizebarcoleresizebar"></a><a name="coleresizebar"></a>ColeReResizebar::ColeReresizebar

Формирует объект `COleResizeBar`.

```
COleResizeBar();
```

### <a name="remarks"></a>Примечания

Вызов `Create` для создания объекта панели повторного размера.

## <a name="coleresizebarcreate"></a><a name="create"></a>ColeReResizebar::Создание

Создает детское окно и связывает `COleResizeBar` его с объектом.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_RESIZE_BAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на родительское окно панели повторного размера.

*dwStyle*<br/>
Определяет атрибуты [стиля окна.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*nID*<br/>
Идентификатор окна ребенка в баре resize.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если был создан бар повторного размера; в противном случае 0.

## <a name="see-also"></a>См. также раздел

[MFC Образец SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс ColeServerDoc](../../mfc/reference/coleserverdoc-class.md)
