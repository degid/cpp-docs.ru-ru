---
title: Класс Кмфктабдроптаржет
ms.date: 11/04/2016
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
ms.openlocfilehash: 9160cfd847977f98ac22eecd72632822c751a3aa
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834236"
---
# <a name="cmfctabdroptarget-class"></a>Класс Кмфктабдроптаржет

Предоставляет механизм связи между элементом управления "Вкладка" и библиотеками OLE.

## <a name="syntax"></a>Синтаксис

```
class CMFCTabDropTarget : public COleDropTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|-|-|
|`CMFCTabDropTarget::CMFCTabDropTarget`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|-|-|
|[Кмфктабдроптаржет:: OnDragEnter](#ondragenter)|Вызывается структурой, когда пользователь перетаскивает объект в окно вкладки. (Переопределяет [коледроптаржет:: OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|
|[Кмфктабдроптаржет:: OnDragLeave](#ondragleave)|Вызывается структурой, когда пользователь перетаскивает объект за пределы окна вкладки, на котором находится фокус. (Переопределяет [коледроптаржет:: OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|
|[Кмфктабдроптаржет:: OnDragOver](#ondragover)|Вызывается структурой, когда пользователь перетаскивает объект в окно вкладки, которое имеет фокус. (Переопределяет [коледроптаржет:: OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|
|[Кмфктабдроптаржет:: Ондропекс](#ondropex)|Вызывается платформой, когда пользователь отпускает кнопку мыши в конце операции перетаскивания. (Переопределяет [коледроптаржет:: ондропекс](../../mfc/reference/coledroptarget-class.md#ondropex).)|
|[Кмфктабдроптаржет:: Register](#register)|Регистрирует элемент управления как объект, который может быть целевым объектом операции перетаскивания OLE.|

### <a name="remarks"></a>Примечания

Этот класс обеспечивает поддержку перетаскивания для `CMFCBaseTabCtrl` класса. Если приложение инициализирует библиотеки OLE с помощью функции [афксолеинит](ole-initialization.md#afxoleinit) , `CMFCBaseTabCtrl` объекты регистрируются для операций перетаскивания.

`CMFCTabDropTarget`Класс расширяет его базовый класс, делая вкладку, находящуюся под курсором, когда выполняется операция перетаскивания. Дополнительные сведения об операциях перетаскивания см. в разделе [перетаскивание OLE](../../mfc/drag-and-drop-ole.md).

## <a name="example"></a>Пример

В этом примере демонстрируется создание объекта `CMFCTabDropTarget` и использование его метода `Register`.

[!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleDropTarget](../../mfc/reference/coledroptarget-class.md)

[кмфктабдроптаржет](../../mfc/reference/cmfctabdroptarget-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxbasetabctrl.h

## <a name="cmfctabdroptargetondragenter"></a><a name="ondragenter"></a> Кмфктабдроптаржет:: OnDragEnter

Вызывается структурой, когда пользователь перетаскивает объект в окно вкладки.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*Приводится*\
[in] Не используется.

*pDataObject*\
окне Указатель на объект, который перетаскивается пользователь.

*двкэйстате*\
окне Содержит состояние клавиш модификатора. Это сочетание любого числа следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.

*точки*\
окне Расположение курсора в координатах клиента.

### <a name="return-value"></a>Возвращаемое значение

Результат, полученный при возникновении перетаскивания в месте, указанном параметром *Point*. Это может быть одно или несколько из следующих:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Примечания

Этот метод возвращает DROPEFFECT_NONE, если платформа панели инструментов не находится в режиме настройки или если формат данных буфера обмена недоступен. В противном случае возвращается результат вызова `CMFCBaseTabCtrl::OnDragEnter` с предоставленными параметрами.

Дополнительные сведения о режиме настройки см. в разделе [CMFCToolBar:: искустомиземоде](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах данных буфера обмена см. в разделе [коледатаобжект:: исдатааваилабле](../../mfc/reference/coledataobject-class.md#isdataavailable).

## <a name="cmfctabdroptargetondragleave"></a><a name="ondragleave"></a> Кмфктабдроптаржет:: OnDragLeave

Вызывается структурой, когда пользователь перетаскивает объект за пределы окна вкладки, на котором находится фокус.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*\
[in] Не используется.

### <a name="remarks"></a>Примечания

Этот метод вызывает `CMFCBaseTabCtrl::OnDragLeave` метод для выполнения операции перетаскивания.

## <a name="cmfctabdroptargetondragover"></a><a name="ondragover"></a> Кмфктабдроптаржет:: OnDragOver

Вызывается структурой, когда пользователь перетаскивает объект в окно вкладки, которое имеет фокус.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*Приводится*\
[in] Не используется.

*pDataObject*\
окне Указатель на объект, который перетаскивается пользователь.

*двкэйстате*\
окне Содержит состояние клавиш модификатора. Это сочетание любого числа следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.

*точки*\
окне Расположение указателя мыши в координатах клиента.

### <a name="return-value"></a>Возвращаемое значение

Результат, полученный при возникновении перетаскивания в месте, указанном параметром *Point*. Это может быть одно или несколько из следующих:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Примечания

Этот метод делает вкладку, расположенную под курсором, когда операция перетаскивания выполняется активно. Он возвращает DROPEFFECT_NONE, если платформа панели инструментов не находится в режиме настройки или если формат данных буфера обмена недоступен. В противном случае возвращается результат вызова `CMFCBaseTabCtrl::OnDragOver` с предоставленными параметрами.

Дополнительные сведения о режиме настройки см. в разделе [CMFCToolBar:: искустомиземоде](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах данных буфера обмена см. в разделе [коледатаобжект:: исдатааваилабле](../../mfc/reference/coledataobject-class.md#isdataavailable).

## <a name="cmfctabdroptargetondropex"></a><a name="ondropex"></a> Кмфктабдроптаржет:: Ондропекс

Вызывается платформой, когда пользователь отпускает кнопку мыши в конце операции перетаскивания.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*Приводится*\
[in] Не используется.

*pDataObject*\
окне Указатель на объект, который перетаскивается пользователь.

*дропеффект*\
окне Операция удаления по умолчанию.

*дроплист*\
[in] Не используется.

*точки*\
окне Расположение указателя мыши в координатах клиента.

### <a name="return-value"></a>Возвращаемое значение

Итоговый результат удаления. Это может быть одно или несколько из следующих:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Примечания

Этот метод вызывает, `CMFCBaseTabCtrl::OnDrop` Если платформа панели инструментов находится в режиме настройки и доступен формат данных буфера обмена. Если вызов `CMFCBaseTabCtrl::OnDrop` возвращает ненулевое значение, этот метод возвращает результат перетаскивания по умолчанию, заданный параметром *дропеффект*. В противном случае этот метод возвращает DROPEFFECT_NONE. Дополнительные сведения об эффектах перетаскивания см. в разделе [коледроптаржет:: ондропекс](../../mfc/reference/coledroptarget-class.md#ondropex).

Дополнительные сведения о режиме настройки см. в разделе [CMFCToolBar:: искустомиземоде](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах данных буфера обмена см. в разделе [коледатаобжект:: исдатааваилабле](../../mfc/reference/coledataobject-class.md#isdataavailable).

## <a name="cmfctabdroptargetregister"></a><a name="register"></a> Кмфктабдроптаржет:: Register

Регистрирует элемент управления как объект, который может быть целевым объектом операции перетаскивания OLE.

```
BOOL Register(CMFCBaseTabCtrl *pOwner);
```

### <a name="parameters"></a>Параметры

*повнер*\
окне Элемент управления "Вкладка" для регистрации в качестве цели перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если регистрация прошла успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод вызывает [коледроптаржет:: Register](../../mfc/reference/coledroptarget-class.md#register) для регистрации элемента управления для операций перетаскивания.

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Перетаскивание OLE](../../mfc/drag-and-drop-ole.md)
