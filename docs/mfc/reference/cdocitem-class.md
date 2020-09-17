---
title: Класс CDocItem
ms.date: 11/04/2016
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
ms.openlocfilehash: 438bc2a03239946dbfca53d5f2989c731b682ab0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375622"
---
# <a name="cdocitem-class"></a>Класс CDocItem

Базовый класс для элементов документа, являющихся компонентами данных документа.

## <a name="syntax"></a>Синтаксис

```
class CDocItem : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDocItem::GetDocument](#getdocument)|Возвращает документ, содержащий элемент.|
|[CDocItem::IsBlank](#isblank)|Определяет, содержит ли элемент какую-либо информацию.|

## <a name="remarks"></a>Примечания

`CDocItem`объекты используются для представления элементов OLE в клиентских и серверных документах.

Для получения дополнительной информации см. [Containers: Implementing a Container](../../mfc/containers-implementing-a-container.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocItem`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="cdocitemgetdocument"></a><a name="getdocument"></a>CDocItem::GetDocument

Вызовите эту функцию, чтобы получить документ, содержащий элемент.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на документ, содержащий элемент; NULL, если элемент не является частью документа.

### <a name="remarks"></a>Примечания

Эта функция переопределяется в производных классов [COleClientItem](../../mfc/reference/coleclientitem-class.md) и [COleServerItem](../../mfc/reference/coleserveritem-class.md), возвращая указатель либо [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), или объект [COleServerDoc.](../../mfc/reference/coleserverdoc-class.md)

## <a name="cdocitemisblank"></a><a name="isblank"></a>CDocItem::IsBlank

Вызывается инфраструктурой при возникновении сериализации по умолчанию.

```
virtual BOOL IsBlank() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент не содержит никакой информации; в противном случае 0.

### <a name="remarks"></a>Примечания

По умолчанию `CDocItem` объекты не являются пустыми. [COleClientItem](../../mfc/reference/coleclientitem-class.md) объекты иногда пустые, `CDocItem`потому что они получают непосредственно от . Тем не менее, объекты [COleServerItem](../../mfc/reference/coleserveritem-class.md) всегда пусты. По умолчанию приложения `COleClientItem` OLE, содержащие объекты, не имеют степени x или y, сериализируются. Это делается путем возвращения TRUE `IsBlank` из переопределения, когда элемент не имеет х или у степени.

Переопределить эту функцию, если вы хотите реализовать другие действия во время сериализации.

## <a name="see-also"></a>См. также раздел

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDocument](../../mfc/reference/coledocument-class.md)<br/>
[Класс ColeServerItem](../../mfc/reference/coleserveritem-class.md)<br/>
[Класс ColeClientItem](../../mfc/reference/coleclientitem-class.md)
