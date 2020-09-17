---
title: Класс COleDropSource
ms.date: 11/04/2016
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
helpviewer_keywords:
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
ms.openlocfilehash: 324c4b7273f021b43c319fb0a494ac843856c78a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375027"
---
# <a name="coledropsource-class"></a>Класс COleDropSource

Позволяет перетаскивают данные в цель падения.

## <a name="syntax"></a>Синтаксис

```
class COleDropSource : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeDropИсточник::COleDropИсточник](#coledropsource)|Формирует объект `COleDropSource`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeDropИсточник::GiveОбратная связь](#givefeedback)|Изменяет курсор во время операции перетаскивания и падения.|
|[ColeDropИсточник::Onbegindrag](#onbegindrag)|Ручки захвата мыши во время операции перетаскивания и падения.|
|[ColeDropSource::QueryContinueDrag](#querycontinuedrag)|Проверка, чтобы увидеть, следует ли перетаскивание продолжаться.|

## <a name="remarks"></a>Примечания

Класс [COleDropTarget](../../mfc/reference/coledroptarget-class.md) обрабатывает приемную часть операции перетаскивания и падения. Объект `COleDropSource` отвечает за определение того, когда операция перетаскивания начинается, обеспечивая обратную связь во время операции перетаскивания и определяя, когда операция перетаскивания заканчивается.

Чтобы использовать `COleDropSource` объект, просто позвоните в конструктор. Это упрощает процесс определения того, какие события, такие как щелчком мыши, начинают операцию перетаскивания с помощью [COleDataSource::DoDragDrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), или [COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) функции. Эти функции `COleDropSource` создадут объект для вас. Возможно, вы захотите изменить `COleDropSource` поведение функций по умолчанию. Эти функции членов будут называться в соответствующее время рамками.

Для получения дополнительной информации о перетаскивания [OLE drag and drop](../../mfc/drag-and-drop-ole.md)операций с использованием OLE, см.

Для получения дополнительной информации, [см.](/windows/win32/api/oleidl/nn-oleidl-idropsource)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropSource`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="coledropsourcecoledropsource"></a><a name="coledropsource"></a>ColeDropИсточник::COleDropИсточник

Формирует объект `COleDropSource`.

```
COleDropSource();
```

## <a name="coledropsourcegivefeedback"></a><a name="givefeedback"></a>ColeDropИсточник::GiveОбратная связь

Вызывается по рамкам после вызова [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) или [COleDropTarget: :DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).

```
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```

### <a name="parameters"></a>Параметры

*dropEffect*<br/>
Эффект, который вы хотели бы отобразить пользователю, обычно указывает на то, что произойдет, если в этот момент произошло падение с выбранными данными. Как правило, это значение, возвращенное последним вызовом в [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) или [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover). Это может быть один или несколько из следующих:

- DROPEFFECT_NONE падение не будет разрешено.

- DROPEFFECT_COPY будет выполнена операция копирования.

- DROPEFFECT_MOVE будет выполнена операция перемещения.

- DROPEFFECT_LINK Будет установлена связь с упавшими данными с исходными данными.

- DROPEFFECT_SCROLL операция перетаски вот-вот произойдет или происходит в цели.

### <a name="return-value"></a>Возвращаемое значение

Возвращает DRAGDROP_S_USEDEFAULTCURSORS, если перетаскивание продолжается, NOERROR, если это не так.

### <a name="remarks"></a>Примечания

Переопределить эту функцию, чтобы обеспечить обратную связь с пользователем о том, что произойдет, если падение произошло в этой точке. В реализации по умолчанию используются курсоры OLE по умолчанию. Для получения дополнительной информации о перетаскивания [OLE drag and drop](../../mfc/drag-and-drop-ole.md)операций с использованием OLE, см.

Для получения дополнительной информации, [см. IDropSource::GiveОбратная связь](/windows/win32/api/oleidl/nf-oleidl-idropsource-givefeedback), [IDropTarget: :DragOver](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover), и [IDropTarget::DragEnter](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) в Windows SDK.

## <a name="coledropsourceonbegindrag"></a><a name="onbegindrag"></a>ColeDropИсточник::Onbegindrag

Вызывается в фреймворке при возникновении события, которое может начать операцию перетаскивания, например нажатие кнопки левой мыши.

```
virtual BOOL OnBeginDrag(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно, содержащее выбранные данные.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если перетаскивание разрешено, в противном случае 0.

### <a name="remarks"></a>Примечания

Переизбь эту функцию, если вы хотите изменить способ запуска процесса перетаскивания. Реализация по умолчанию захватывает мышь и остается в режиме перетаскивания до тех пор, пока пользователь не нажмет левую или правую кнопку мыши или не нажмет на ESC, в это время он выпускает мышь.

## <a name="coledropsourcequerycontinuedrag"></a><a name="querycontinuedrag"></a>ColeDropSource::QueryContinueDrag

После начала перетаскивания эта функция неоднократно вызывается фректором до тех пор, пока операция перетаскивания не будет отменена или завершена.

```
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed,
    DWORD dwKeyState);
```

### <a name="parameters"></a>Параметры

*bEscapePressed*<br/>
Государства ли ключ ESC был нажат `COleDropSource::QueryContinueDrag`с момента последнего призыва к .

*dwKeyState*<br/>
Содержит состояние клавиш модификатора на клавиатуре. Это сочетание любого числа: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.

### <a name="return-value"></a>Возвращаемое значение

DRAGDROP_S_CANCEL, если нажатие клавиши ESC или правой кнопки или левой кнопки перед запуском. DRAGDROP_S_DROP, если операция по падению должна произойти. В противном случае S_OK.

### <a name="remarks"></a>Примечания

Переизбь эту функцию, если вы хотите изменить точку, в которой перетаскивание отменяется или происходит падение.

Реализация по умолчанию инициирует падение или отменяет перетаскивание следующим образом. Он отменяет операцию перетаскивания при нажатии клавиши ESC или правой кнопки мыши. Он инициирует операцию падения при поднятии левой кнопки мыши после начала перетаскивания. В противном случае он возвращает S_OK и не выполняет никаких дальнейших операций.

Поскольку эта функция часто вызывается, ее следует максимально оптимизировать.

## <a name="see-also"></a>См. также раздел

[MFC Образец HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
