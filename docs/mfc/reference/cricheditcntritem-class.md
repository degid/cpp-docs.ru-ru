---
title: Класс CrichEditCntrItem
ms.date: 11/04/2016
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
ms.openlocfilehash: 7b566fe7f1c0667dbcdb4976f79cd2e1597f48f6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752768"
---
# <a name="cricheditcntritem-class"></a>Класс CrichEditCntrItem

С [CRichEditView](../../mfc/reference/cricheditview-class.md) и [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), обеспечивает функциональность богатого управления рекреацией в контексте архитектуры представления документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CRichEditCntrItem : public COleClientItem
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CrichEditCntrItem::CrichEditCntrItem](#cricheditcntritem)|Формирует объект `CRichEditCntrItem`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CrichEditCntrItem:SyncToRichEditObject](#synctoricheditobject)|Активирует элемент как другой тип.|

## <a name="remarks"></a>Примечания

"Богатый элемент управления редактированием" — это окно, в котором пользователь может вводить и отстранять текст. Текст может быть назначен символ и форматирование абзацев, и может включать встроенные объекты OLE. Управление богатым редактированием обеспечивает интерфейс программирования для форматирования текста. Однако приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для того, чтобы операции форматирования были доступны пользователю.

`CRichEditView`сохраняет текст и форматирование характеристики текста. `CRichEditDoc`ведет список элементов клиента OLE, которые находятся в представлении. `CRichEditCntrItem`обеспечивает доступ к клиенту OL со стороны контейнера.

Этот общий элемент управления Windows (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанных с ними классов) доступен только для программ, работающих под Windows 95/98 и Windows NT версии 3.51 и позже.

Например, использование богатых элементов контейнеров для обработки в приложении MFC см. [WORDPAD](../../overview/visual-cpp-samples.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`CRichEditCntrItem`

## <a name="requirements"></a>Требования

**Заголовок:** afxrich.h

## <a name="cricheditcntritemcricheditcntritem"></a><a name="cricheditcntritem"></a>CrichEditCntrItem::CrichEditCntrItem

Вызовите эту `CRichEditCntrItem` функцию, чтобы создать объект и добавьте его в контейнерный документ.

```
CRichEditCntrItem(
    REOBJECT* preo = NULL,
    CRichEditDoc* pContainer = NULL);
```

### <a name="parameters"></a>Параметры

*preo*<br/>
Указатель на структуру [REOBJECT,](/windows/win32/api/richole/ns-richole-reobject) описывающий элемент OLE. Новый `CRichEditCntrItem` объект построен вокруг этого элемента OLE. Если *preo* null, клиентский элемент пуст.

*pContainer*<br/>
Указатель на контейнерный документ, который будет содержать этот элемент. Если *pContainer* является NULL, необходимо явно позвонить [в COleDocument::AddItem,](../../mfc/reference/coledocument-class.md#additem) чтобы добавить этот элемент клиента в документ.

### <a name="remarks"></a>Примечания

Эта функция не выполняет никакой инициализации OLE.

Для получения дополнительной [информации](/windows/win32/api/richole/ns-richole-reobject) см.

## <a name="cricheditcntritemsynctoricheditobject"></a><a name="synctoricheditobject"></a>CrichEditCntrItem:SyncToRichEditObject

Вызовите эту функцию для синхронизации аспекта устройства, [DVASPECT](/windows/win32/api/wtypes/ne-wtypes-dvaspect), об этом, `CRichEditCntrltem` указанном *reo*.

```cpp
void SyncToRichEditObject(REOBJECT& reo);
```

### <a name="parameters"></a>Параметры

*Reo*<br/>
Ссылка на структуру [REOBJECT,](/windows/win32/api/richole/ns-richole-reobject) описывающая элемент OLE.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см.](/windows/win32/api/wtypes/ne-wtypes-dvaspect)

## <a name="see-also"></a>См. также раздел

[MFC Образец WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[Класс ColeClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)<br/>
[Класс CrichEditView](../../mfc/reference/cricheditview-class.md)
