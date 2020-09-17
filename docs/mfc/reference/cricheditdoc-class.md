---
title: Класс CRichEditDoc
ms.date: 11/04/2016
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
ms.openlocfilehash: 587cf65543e24e586fb8b2336481d6e841473134
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368264"
---
# <a name="cricheditdoc-class"></a>Класс CRichEditDoc

С [CRichEditView](../../mfc/reference/cricheditview-class.md) и [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), обеспечивает функциональность богатого управления рекреацией в контексте архитектуры представления документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CrichEditDoc::CreateClientItem](#createclientitem)|Вызывается для выполнения очистки документа.|
|[CrichEditDoc::GetStreamFormat](#getstreamformat)|Указывает, должны ли входные данные и вывод потока включать информацию о форматировании.|
|[CrichEditDoc:GetView](#getview)|Извлекает ассоциированный объект [CRichEditView.](../../mfc/reference/cricheditview-class.md)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CrichEditDoc::m_bRTF](#m_brtf)|Указывает, должен ли поток вввв/о включать форматирование.|

## <a name="remarks"></a>Примечания

"Богатый элемент управления редактированием" — это окно, в котором пользователь может вводить и отстранять текст. Текст может быть назначен символ и форматирование абзацев, и может включать встроенные объекты OLE. Управление богатым редактированием обеспечивает интерфейс программирования для форматирования текста. Однако приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для того, чтобы операции форматирования были доступны пользователю.

`CRichEditView`сохраняет текст и форматирование характеристики текста. `CRichEditDoc`ведет список клиентских элементов, которые находятся в представлении. `CRichEditCntrItem`обеспечивает доступ к клиентским элементам OLE.

Этот общий элемент управления Windows (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанных с ними классов) доступен только для программ, работающих под Windows 95/98 и Windows NT версии 3.51 и позже.

Например, использование богатого документа для отодеватели в приложении MFC см. [WORDPAD](../../overview/visual-cpp-samples.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)

`CRichEditDoc`

## <a name="requirements"></a>Требования

**Заголовок:** afxrich.h

## <a name="cricheditdoccreateclientitem"></a><a name="createclientitem"></a>CrichEditDoc::CreateClientItem

Вызовите эту `CRichEditCntrItem` функцию, чтобы создать объект и добавьте его в этот документ.

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>Параметры

*preo*<br/>
Указатель на структуру [REOBJECT,](/windows/win32/api/richole/ns-richole-reobject) описывающий элемент OLE. Новый `CRichEditCntrItem` объект построен вокруг этого элемента OLE. Если *preo* null, новый элемент клиента пуст.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый объект [CRichEditCntrItem,](../../mfc/reference/cricheditcntritem-class.md) который был добавлен в этот документ.

### <a name="remarks"></a>Примечания

Эта функция не выполняет никакой инициализации OLE.

Для получения дополнительной [информации](/windows/win32/api/richole/ns-richole-reobject) см.

## <a name="cricheditdocgetstreamformat"></a><a name="getstreamformat"></a>CrichEditDoc::GetStreamFormat

Вызовите эту функцию, чтобы определить текстовый формат для потоковой передачи содержимого богатого редактирования.

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>Возвращаемое значение

Один из следующих флагов:

- SF_TEXT указывает на то, что богатый элемент управления ретрижки не поддерживает информацию о форматировании.

- SF_RTF указывает на то, что богатый элемент управления реитриек действительно поддерживает информацию форматирования.

### <a name="remarks"></a>Примечания

Значение возврата основано на [m_bRTF](#m_brtf) члене данных. Эта функция возвращает `m_bRTF` SF_RTF, если это правда; в противном случае, SF_TEXT.

## <a name="cricheditdocgetview"></a><a name="getview"></a>CrichEditDoc:GetView

Вызовите эту функцию для доступа к `CRichEditDoc` объекту [CRichEditView,](../../mfc/reference/cricheditview-class.md) связанного с этим объектом.

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CRichEditView` объект, связанный с документом.

### <a name="remarks"></a>Примечания

Текст и информация о форматировании `CRichEditView` содержатся внутри объекта. Объект `CRichEditDoc` поддерживает элементы OLE для сериализации. Там должно быть `CRichEditView` только `CRichEditDoc`один для каждого .

## <a name="cricheditdocm_brtf"></a><a name="m_brtf"></a>CrichEditDoc::m_bRTF

Когда TRUE, указывает, что [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) и [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) должны хранить параграф и характеристики форматирования символов.

```
BOOL m_bRTF;
```

## <a name="see-also"></a>См. также раздел

[MFC Образец WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[Класс ColeServerDoc](../../mfc/reference/coleserverdoc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CrichEditView](../../mfc/reference/cricheditview-class.md)<br/>
[Класс CrichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)<br/>
[Класс COleDocument](../../mfc/reference/coledocument-class.md)<br/>
[Класс CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)
