---
title: Класс CDocObjectServerItem
ms.date: 03/27/2019
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnDoVerb
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnDoVerb
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
ms.openlocfilehash: 1f0f5cf93aab35a17f7174b2beee0d1398564a3d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375526"
---
# <a name="cdocobjectserveritem-class"></a>Класс CDocObjectServerItem

Реализует команды OLE-сервера специально для серверов DocObject.

## <a name="syntax"></a>Синтаксис

```
class CDocObjectServerItem : public COleServerItem
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Формирует объект `CDocObjectServerItem`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDocObjectServerItem::GetDocument](#getdocument)|Извлекает указатель на документ, содержащий элемент.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CDocObjectServerItem::OndoVerb](#ondoverb)|Призван выполнить глагол.|
|[CDocObjectServerItem::OnHide](#onhide)|Бросает исключение, если фреймворк пытается скрыть элемент DocObject.|
|[CDocObjectServerItem::Onshow](#onshow)|Вызывается по системе, чтобы сделать элемент DocObject на месте активным. Если элемент не является DocObject, звонит [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|

## <a name="remarks"></a>Примечания

`CDocObjectServerItem`определяет переизлики функции членов: [OnHide,](#onhide) [OnDoVerb](#ondoverb)и [OnShow](#onshow).

Чтобы `CDocObjectServerItem`использовать, убедитесь, что [переопределение OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) в `COleServerDoc` `CDocObjectServerItem` вашем классе, полученном, возвращает новый объект. Если вам необходимо изменить какую-либо функциональность в элементе, `CDocObjectServerItem`можно создать новый экземпляр вашего собственного класса.

Для получения дополнительной информации о DocObjects, [см. CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) и [COleCmdUI](../../mfc/reference/colecmdui-class.md) в *MFC Справочник*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleServerItem](../../mfc/reference/coleserveritem-class.md)

`CDocObjectServerItem`

## <a name="requirements"></a>Требования

**Заголовок:** afxdocob.h

## <a name="cdocobjectserveritemcdocobjectserveritem"></a><a name="cdocobjectserveritem"></a>CDocObjectServerItem::CDocObjectServerItem

Формирует объект `CDocObjectServerItem`.

```
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*pServerDoc*<br/>
Указатель на документ, который будет содержать новый элемент DocObject.

*bAutoDelete*<br/>
Указывает, можно ли удалить объект при освобождении ссылки на него. Установите аргумент FALSE, `CDocObjectServerItem` если объект является неотъемлемой частью данных документа. Установите его на истину, если объект является вторичной структурой, используемой для определения диапазона данных документа, которые могут быть удалены инфраструктурой.

## <a name="cdocobjectserveritemgetdocument"></a><a name="getdocument"></a>CDocObjectServerItem::GetDocument

Извлекает указатель на документ, содержащий элемент.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на документ, содержащий элемент; NULL, если элемент не является частью документа.

### <a name="remarks"></a>Примечания

Это позволяет получить доступ к серверу документа, который вы передали в качестве аргумента конструктору [CDocObjectServerItem.](#cdocobjectserveritem)

## <a name="cdocobjectserveritemondoverb"></a><a name="ondoverb"></a>CDocObjectServerItem::OndoVerb

Вызывается фреймворком для выполнения указанного глагола.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Параметры

*iVerb*<br/>
Определяет глагол для выполнения. Для возможных значений [см. IOleObject::DoVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) в SDK Windows.

### <a name="remarks"></a>Примечания

Реализация по умолчанию вызывает функцию участника [OnShow,](#onshow) если элемент является DocObject и указан OLEIVERB_INPLACEACTIVATE или OLEIVERB_SHOW. Если элемент не является DocObject или указан другой глагол, реализация по умолчанию вызывает [COleServerItem::OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb).

## <a name="cdocobjectserveritemonhide"></a><a name="onhide"></a>CDocObjectServerItem::OnHide

Вызывается по фрейму, чтобы скрыть элемент.

```
virtual void OnHide();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию выбрасывает исключение, если элемент является DocObject. Вы не можете скрыть активный элемент DocObject, поскольку он принимает весь вид. Необходимо отключить элемент DocObject, чтобы он исчез. Если элемент не является DocObject, реализация по умолчанию вызывает [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).

## <a name="cdocobjectserveritemonshow"></a><a name="onshow"></a>CDocObjectServerItem::Onshow

Вызывается в рамках, чтобы поручить серверное приложение, чтобы сделать элемент DocObject на месте активным.

```
virtual void OnShow();
```

### <a name="remarks"></a>Примечания

Если элемент не является DocObject, реализация по умолчанию вызывает [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Переопределить эту функцию, если вы хотите выполнить специальную обработку при открытии элемента DocObject.

## <a name="see-also"></a>См. также раздел

[Класс ColeServerItem](../../mfc/reference/coleserveritem-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)<br/>
[Класс COleDocObjectItem](../../mfc/reference/coledocobjectitem-class.md)
