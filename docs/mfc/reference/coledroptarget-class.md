---
title: Класс ColeDropTarget
ms.date: 11/04/2016
f1_keywords:
- COleDropTarget
- AFXOLE/COleDropTarget
- AFXOLE/COleDropTarget::COleDropTarget
- AFXOLE/COleDropTarget::OnDragEnter
- AFXOLE/COleDropTarget::OnDragLeave
- AFXOLE/COleDropTarget::OnDragOver
- AFXOLE/COleDropTarget::OnDragScroll
- AFXOLE/COleDropTarget::OnDrop
- AFXOLE/COleDropTarget::OnDropEx
- AFXOLE/COleDropTarget::Register
- AFXOLE/COleDropTarget::Revoke
helpviewer_keywords:
- COleDropTarget [MFC], COleDropTarget
- COleDropTarget [MFC], OnDragEnter
- COleDropTarget [MFC], OnDragLeave
- COleDropTarget [MFC], OnDragOver
- COleDropTarget [MFC], OnDragScroll
- COleDropTarget [MFC], OnDrop
- COleDropTarget [MFC], OnDropEx
- COleDropTarget [MFC], Register
- COleDropTarget [MFC], Revoke
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
ms.openlocfilehash: 01eb277da029d06ee44d8e048cf3244f4371a9ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374996"
---
# <a name="coledroptarget-class"></a>Класс ColeDropTarget

Предоставляет механизм взаимодействия между окном и библиотеками OLE.

## <a name="syntax"></a>Синтаксис

```
class COleDropTarget : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeDropTarget::COleDropTarget](#coledroptarget)|Формирует объект `COleDropTarget`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColedropTarget::OndragEnter](#ondragenter)|Вызывается, когда курсор впервые входит в окно.|
|[ColeDropTarget::OndragLeave](#ondragleave)|Вызывается, когда курсор вытащили из окна.|
|[Coledroptarget::Ondragover](#ondragover)|Вызывается неоднократно, когда курсор перетаскивается через окно.|
|[ColeDropTarget::OndragScroll](#ondragscroll)|Вызывается, чтобы определить, втягивается ли курсор в область прокрутки окна.|
|[ColeDropTarget:OnDrop](#ondrop)|Вызывается при удалении данных в окно обработчик по умолчанию.|
|[ColeDropTarget::OnDropEx](#ondropex)|Вызывается при падении данных в окно, начальный обработчик.|
|[ColeDropTarget::Регистрация](#register)|Регистрирует окно в качестве допустимой цели падения.|
|[ColeDropTarget::Отозвать](#revoke)|Вызывает прекращение действия окна.|

## <a name="remarks"></a>Примечания

Создание объекта этого класса позволяет окну принимать данные через механизм перетаскивания и падения OLE.

Чтобы получить окно для принятия команд капли, необходимо сначала `COleDropTarget` создать объект класса, а затем вызвать `CWnd` функцию [Регистра](#register) с указателем на нужный объект в качестве единственного параметра.

Для получения дополнительной информации о перетаскивания [OLE drag and drop](../../mfc/drag-and-drop-ole.md)операций с использованием OLE, см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropTarget`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="coledroptargetcoledroptarget"></a><a name="coledroptarget"></a>ColeDropTarget::COleDropTarget

Строит объект класса. `COleDropTarget`

```
COleDropTarget();
```

### <a name="remarks"></a>Примечания

Call [Register,](#register) чтобы связать этот объект с окном.

## <a name="coledroptargetondragenter"></a><a name="ondragenter"></a>ColedropTarget::OndragEnter

Вызывается по фрейму, когда курсор сначала втягивается в окно.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно, в которое входит курсор.

*pDataObject*<br/>
Указывает на объект данных, содержащий данные, которые могут быть удалены.

*dwKeyState*<br/>
Содержит состояние ключей модификатора. Это сочетание любого числа: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.

*Точки*<br/>
Содержит текущее местоположение курсора в координатах клиента.

### <a name="return-value"></a>Возвращаемое значение

Эффект, который приведет, если падение было предпринято в месте, указанном по *пункту.* Это может быть один или несколько из следующих:

- DROPEFFECT_NONE падение не будет разрешено.

- DROPEFFECT_COPY будет выполнена операция копирования.

- DROPEFFECT_MOVE будет выполнена операция перемещения.

- DROPEFFECT_LINK Будет установлена связь с упавшими данными с исходными данными.

- DROPEFFECT_SCROLL операция перетаски вот-вот произойдет или происходит в цели.

### <a name="remarks"></a>Примечания

Переопределить эту функцию, чтобы позволить операциям сброса происходить в окне. Реализация по умолчанию вызывает [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), который просто возвращает DROPEFFECT_NONE по умолчанию.

Для получения дополнительной информации с [:Dм.](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter)

## <a name="coledroptargetondragleave"></a><a name="ondragleave"></a>ColeDropTarget::OndragLeave

Вызывается фреймворком, когда курсор покидает окно во время операции перетаскивания.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно, которое покидает курсор.

### <a name="remarks"></a>Примечания

Переопределить эту функцию, если требуется особое поведение, когда операция перетаскивания покидает указанное окно. Реализация этой функции по умолчанию вызывает [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).

Для получения дополнительной информации см. [IDropTarget::DragLeave](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragleave) в Windows SDK.

## <a name="coledroptargetondragover"></a><a name="ondragover"></a>Coledroptarget::Ondragover

Вызывается по фрейму, когда курсор перетаскивается через окно.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно, что курсор закончился.

*pDataObject*<br/>
Указывает на объект данных, содержащий данные, которые должны быть удалены.

*dwKeyState*<br/>
Содержит состояние ключей модификатора. Это сочетание любого числа: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.

*Точки*<br/>
Содержит текущее местоположение курсора в координатах клиента.

### <a name="return-value"></a>Возвращаемое значение

Эффект, который приведет, если падение было предпринято в месте, указанном по *пункту.* Это может быть один или несколько из следующих:

- DROPEFFECT_NONE падение не будет разрешено.

- DROPEFFECT_COPY будет выполнена операция копирования.

- DROPEFFECT_MOVE будет выполнена операция перемещения.

- DROPEFFECT_LINK Будет установлена связь с упавшими данными с исходными данными.

- DROPEFFECT_SCROLL указывает на то, что операция перетасктий вот-вот произойдет или происходит в цели.

### <a name="remarks"></a>Примечания

Эта функция должна быть перекрыта, чтобы в окне происходили операции сброса. Реализация этой функции по умолчанию вызывает [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover), который возвращает DROPEFFECT_NONE по умолчанию. Поскольку эта функция часто вызывается во время операции перетаскивания, ее следует максимально оптимизировать.

Для получения дополнительной информации [:D](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover) см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]

## <a name="coledroptargetondragscroll"></a><a name="ondragscroll"></a>ColeDropTarget::OndragScroll

Вызывается по системе перед вызовом [OnDragEnter](#ondragenter) или [OnDragOver,](#ondragover) чтобы определить, находится ли *точка* в области прокрутки.

```
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно, в течение которого курсор закончился.

*dwKeyState*<br/>
Содержит состояние ключей модификатора. Это сочетание любого числа: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.

*Точки*<br/>
Содержит расположение курсора, в пикселях, по отношению к экрану.

### <a name="return-value"></a>Возвращаемое значение

Эффект, который приведет, если падение было предпринято в месте, указанном по *пункту.* Это может быть один или несколько из следующих:

- DROPEFFECT_NONE падение не будет разрешено.

- DROPEFFECT_COPY будет выполнена операция копирования.

- DROPEFFECT_MOVE будет выполнена операция перемещения.

- DROPEFFECT_LINK Будет установлена связь с упавшими данными с исходными данными.

- DROPEFFECT_SCROLL указывает на то, что операция перетасктий вот-вот произойдет или происходит в цели.

### <a name="remarks"></a>Примечания

Переопределить эту функцию, когда требуется предоставить специальное поведение для этого события. Реализация этой функции по умолчанию вызывает [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), который возвращает DROPEFFECT_NONE и прокручивает окно, когда курсор втягивается в область прокрутки по умолчанию внутри границы окна.

## <a name="coledroptargetondrop"></a><a name="ondrop"></a>ColeDropTarget:OnDrop

Вызывается в рамках, когда операция падения должна произойти.

```
virtual BOOL OnDrop(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно, в течение которого курсор закончился.

*pDataObject*<br/>
Указывает на объект данных, содержащий данные, которые должны быть удалены.

*dropEffect*<br/>
Эффект, который пользователь выбрал для операции сброса. Это может быть один или несколько из следующих:

- DROPEFFECT_COPY будет выполнена операция копирования.

- DROPEFFECT_MOVE будет выполнена операция перемещения.

- DROPEFFECT_LINK Будет установлена связь с упавшими данными с исходными данными.

*Точки*<br/>
Содержит расположение курсора, в пикселях, по отношению к экрану.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если падение успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Платформа сначала вызывает [OnDropEx](#ondropex). Если `OnDropEx` функция не обрабатывает падение, то фреймворк вызывает эту функцию члена, `OnDrop`. Как правило, приложение переопределяет [OnDropEx](../../mfc/reference/cview-class.md#ondropex) в классе представления для обработки правильной кнопки мыши перетаскивания и падения. Как правило, класс представления [OnDrop](../../mfc/reference/cview-class.md#ondrop) используется для обработки простого перетаскивания и падения.

Реализация по `COleDropTarget::OnDrop` умолчанию вызовов [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), которая просто возвращает FALSE по умолчанию.

Для получения дополнительной информации [:D](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) см.

## <a name="coledroptargetondropex"></a><a name="ondropex"></a>ColeDropTarget::OnDropEx

Вызывается в рамках, когда операция падения должна произойти.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно, в течение которого курсор закончился.

*pDataObject*<br/>
Указывает на объект данных, содержащий данные, которые должны быть удалены.

*dropDefault*<br/>
Эффект, который пользователь выбрал для операции сброса по умолчанию, основан на текущем состоянии ключа. Это может быть DROPEFFECT_NONE. Эффекты выпадения обсуждаются в разделе Замечания.

*dropList*<br/>
Список эффектов падения, которые поддерживает источник капли. Значения эффекта drop можно комбинировать с помощью bitwise ИЛИ** (&#124;) **операции. Эффекты выпадения обсуждаются в разделе Замечания.

*Точки*<br/>
Содержит расположение курсора, в пикселях, по отношению к экрану.

### <a name="return-value"></a>Возвращаемое значение

Эффект падения, полученный в результате попытки падения в месте, указанном *по пункту.* Эффекты выпадения обсуждаются в разделе Замечания.

### <a name="remarks"></a>Примечания

Сначала фреймворк вызывает эту функцию. Если он не обрабатывает падение, фреймворк вызывает [OnDrop.](#ondrop) Как правило, вы переопределить [OnDropEx](../../mfc/reference/cview-class.md#ondropex) в классе представления для поддержки правой кнопки мыши перетаскивания и падения. Как правило, класс представления [OnDrop](../../mfc/reference/cview-class.md#ondrop) используется для обработки случая поддержки простого перетаскивания и падения.

Реализация вызовов `COleDropTarget::OnDropEx` cView по умолчанию::OnDropEx . [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) По умолчанию [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) просто возвращает фиктивное значение, чтобы указать, что функция участника [OnDrop](#ondrop) должна быть вызвана.

Эффекты выпадения описывают действие, связанное с операцией падения. Смотрите следующий список эффектов падения:

- DROPEFFECT_NONE падение не будет разрешено.

- DROPEFFECT_COPY будет выполнена операция копирования.

- DROPEFFECT_MOVE будет выполнена операция перемещения.

- DROPEFFECT_LINK Будет установлена связь с упавшими данными с исходными данными.

- DROPEFFECT_SCROLL указывает на то, что операция перетасктий вот-вот произойдет или происходит в цели.

Для получения дополнительной информации [:D](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) см.

## <a name="coledroptargetregister"></a><a name="register"></a>ColeDropTarget::Регистрация

Вызовите эту функцию, чтобы зарегистрировать свое окно с OLE DLLs в качестве допустимой цели падения.

```
BOOL Register(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно, которое должно быть зарегистрировано в качестве цели падения.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если регистрация успешна; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция должна быть вызвана для того, чтобы операции по падению были приняты.

Для получения дополнительной информации [см.](/windows/win32/api/ole2/nf-ole2-registerdragdrop)

## <a name="coledroptargetrevoke"></a><a name="revoke"></a>ColeDropTarget::Отозвать

Вызов исчисляйте эту функцию, прежде чем уничтожить любое окно, которое было зарегистрировано в качестве цели падения через вызов [регистра,](#register) чтобы удалить его из списка целей падения.

```
virtual void Revoke();
```

### <a name="remarks"></a>Примечания

Эта функция автоматически вызывается из обработчика [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) для зарегистрированного окна, поэтому обычно нет необходимости вызывать эту функцию явно.

Для получения дополнительной информации [см.](/windows/win32/api/ole2/nf-ole2-revokedragdrop)

## <a name="see-also"></a>См. также раздел

[MFC Образец HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDropSource](../../mfc/reference/coledropsource-class.md)
