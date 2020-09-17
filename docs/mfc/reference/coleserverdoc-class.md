---
title: Класс ColeServerDoc
ms.date: 11/04/2016
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
helpviewer_keywords:
- COleServerDoc [MFC], COleServerDoc
- COleServerDoc [MFC], ActivateDocObject
- COleServerDoc [MFC], ActivateInPlace
- COleServerDoc [MFC], DeactivateAndUndo
- COleServerDoc [MFC], DiscardUndoState
- COleServerDoc [MFC], GetClientSite
- COleServerDoc [MFC], GetEmbeddedItem
- COleServerDoc [MFC], GetItemClipRect
- COleServerDoc [MFC], GetItemPosition
- COleServerDoc [MFC], GetZoomFactor
- COleServerDoc [MFC], IsDocObject
- COleServerDoc [MFC], IsEmbedded
- COleServerDoc [MFC], IsInPlaceActive
- COleServerDoc [MFC], NotifyChanged
- COleServerDoc [MFC], NotifyClosed
- COleServerDoc [MFC], NotifyRename
- COleServerDoc [MFC], NotifySaved
- COleServerDoc [MFC], OnDeactivate
- COleServerDoc [MFC], OnDeactivateUI
- COleServerDoc [MFC], OnDocWindowActivate
- COleServerDoc [MFC], OnResizeBorder
- COleServerDoc [MFC], OnShowControlBars
- COleServerDoc [MFC], OnUpdateDocument
- COleServerDoc [MFC], RequestPositionChange
- COleServerDoc [MFC], SaveEmbedding
- COleServerDoc [MFC], ScrollContainerBy
- COleServerDoc [MFC], UpdateAllItems
- COleServerDoc [MFC], CreateInPlaceFrame
- COleServerDoc [MFC], DestroyInPlaceFrame
- COleServerDoc [MFC], GetDocObjectServer
- COleServerDoc [MFC], OnClose
- COleServerDoc [MFC], OnExecOleCmd
- COleServerDoc [MFC], OnFrameWindowActivate
- COleServerDoc [MFC], OnGetEmbeddedItem
- COleServerDoc [MFC], OnReactivateAndUndo
- COleServerDoc [MFC], OnSetHostNames
- COleServerDoc [MFC], OnSetItemRects
- COleServerDoc [MFC], OnShowDocument
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
ms.openlocfilehash: 8e75ec5c00c614a225a059a2b3cf97a7a307c61c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753787"
---
# <a name="coleserverdoc-class"></a>Класс ColeServerDoc

Базовый класс для серверной документации OLE.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeServerDoc::COleServerDoc](#coleserverdoc)|Формирует объект `COleServerDoc`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeServerDoc::ActivateDocObject](#activatedocobject)|Активирует связанный документ DocObject.|
|[ColeServerDoc:ActivateinPlace](#activateinplace)|Активирует документ для редактирования на месте.|
|[ColeServerDoc::DэактивироватьАнддундо](#deactivateandundo)|Деактивирует пользовательский интерфейс сервера.|
|[ColeServerDoc::DiscardUndoState](#discardundostate)|Отбрасывает отменить информацию о состоянии.|
|[ColeServerDoc::GetClientSite](#getclientsite)|Извлекает указатель на базовый `IOleClientSite` интерфейс.|
|[ColeServerDoc::GetEmbeddedItem](#getembeddeditem)|Возвращает указатель на элемент, представляющий весь документ.|
|[ColeServerDoc::GetItemClipRect](#getitemcliprect)|Возвращает текущий прямоугольник отсечения для редактирования на месте.|
|[ColeServerDoc::GetItemPosition](#getitemposition)|Возвращает прямоугольник текущего положения, относительно клиентской области контейнерного приложения, для редактирования на месте.|
|[ColeServerDoc::Get'mFactor](#getzoomfactor)|Возвращает коэффициент масштабирования в пикселях.|
|[ColeServerDoc::IsDocObject](#isdocobject)|Определяет, является ли документ DocObject.|
|[ColeServerDoc::Isembedded](#isembedded)|Указывает, встроен ли документ в контейнерный документ или работает отдельно.|
|[ColeServerdoc::IsinPlaceActive](#isinplaceactive)|Возвращает TRUE, если элемент в настоящее время активирован на месте.|
|[ColeServerDoc::NotifyChanged](#notifychanged)|Уведомляет контейнеры о том, что пользователь изменил документ.|
|[ColeServerDoc::NotifyClosed](#notifyclosed)|Уведомляет контейнеры о том, что пользователь закрыл документ.|
|[ColeServerDoc::NotifyRename](#notifyrename)|Уведомляет контейнеры о том, что пользователь переименовал документ.|
|[ColeServerDoc::NotifySaved](#notifysaved)|Уведомляет контейнеры, которые пользователь сохранил.|
|[ColeServerDoc::OnDeactivate](#ondeactivate)|Вызывается системой, когда пользователь деактивирует элемент, который был активирован на месте.|
|[ColeServerDoc::OnDeactivateuI](#ondeactivateui)|Вызывается инфраструктурой для уничтожения элементов управления и других элементов пользовательского интерфейса, созданных для активации на месте.|
|[ColeServerDoc::OnDocWindowActivate](#ondocwindowactivate)|Вызывается системой при активации или деактивации окна кадра документа контейнера.|
|[ColeServerDoc::OnResizeBorder](#onresizeborder)|Вызывается системой при повторном размере окна кадра или документа приложения контейнера.|
|[ColeServerDoc::OnShowControlBars](#onshowcontrolbars)|Вызывается в рамках, чтобы показать или скрыть контрольные бары для редактирования на месте.|
|[ColeServerDoc::OnUpdateDocument](#onupdatedocument)|Вызов в фреймворк при сохранении встроенного элемента серверного документа, обновляя копию элемента контейнера.|
|[ColeServerDoc::RequestPositionChange](#requestpositionchange)|Изменяет положение кадрового редактирования на месте.|
|[ColeServerDoc::SaveEmbedding](#saveembedding)|Сообщает контейнерное приложение для сохранения документа.|
|[ColeServerDoc::Scrollcontainerby](#scrollcontainerby)|Прокрутка контейнерного документа.|
|[ColeServerDoc:UpdateAllItems](#updateallitems)|Уведомляет контейнеры о том, что пользователь изменил документ.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[ColeServerdoc::CreateinPlaceframe](#createinplaceframe)|Вызывается в рамках для создания окна кадра для редактирования на месте.|
|[ColeServerDoc::DestroyInPlaceframe](#destroyinplaceframe)|Вызывается рамки, чтобы уничтожить окно кадра для редактирования на месте.|
|[ColeServerDoc::GetDocObjectServer](#getdocobjectserver)|Переопределить эту функцию `CDocObjectServer` для создания нового объекта и указать, что этот документ является контейнером DocObject.|
|[ColeServerDoc::Onclose](#onclose)|Вызывается по системе, когда контейнер запрашивает для закрытия документа.|
|[ColeServerDoc::OnExecOleCmd](#onexecolecmd)|Выполняет указанную команду или отображает справку для команды.|
|[ColeServerDoc::OnFrameWindowActivate](#onframewindowactivate)|Вызывается фреймворком при активации или деактивации окна рамы контейнера.|
|[ColeServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|Вызывается, `COleServerItem` чтобы получить, который представляет весь документ; используется для получения встроенного элемента. Требуется реализация.|
|[ColeServerDoc::OnReactivateAndUndo](#onreactivateandundo)|Вызывается в рамках, чтобы отменить изменения, внесенные во время редактирования на месте.|
|[ColeServerDoc::Onsethostnamesnames](#onsethostnames)|Вызывается фреймворком, когда контейнер устанавливает заголовок окна для встроенного объекта.|
|[ColeServerDoc::OnSetItemRects](#onsetitemrects)|Вызывается в рамках, чтобы разместить на месте редактирования окна кадра в окне контейнерного приложения.|
|[ColeServerDoc::OnshowDocument](#onshowdocument)|Вызывается по системе, чтобы показать или скрыть документ.|

## <a name="remarks"></a>Примечания

Серверный документ может содержать объекты [COleServerItem,](../../mfc/reference/coleserveritem-class.md) которые представляют интерфейс сервера для встроенных или связанных элементов. Когда серверное приложение запускается контейнером для отсвагивания встроенного элемента, элемент загружается как собственный серверный документ; `COleServerDoc` объект содержит только `COleServerItem` один объект, состоящий из всего документа. Когда серверное приложение запускается контейнером для отсечения связанного элемента, существующий документ загружается с диска; часть содержимого документа выделена для обозначения связанного элемента.

`COleServerDoc`объекты могут также содержать элементы класса [COleClientItem.](../../mfc/reference/coleclientitem-class.md) Это позволяет создавать приложения для контейнерных серверов. Платформа предоставляет функции для `COleClientItem` правильного хранения `COleServerItem` элементов при обслуживании объектов.

Если серверное приложение не поддерживает ссылки, серверный документ всегда будет содержать только один элемент сервера, который представляет весь встроенный объект в качестве документа. Если приложение сервера поддерживает ссылки, оно должно создавать элемент сервера каждый раз, когда выбор копируется в Clipboard.

Для `COleServerDoc`использования, получения класса из него и реализации функции члена [OnGetEmbeddedItem,](#ongetembeddeditem) которая позволяет серверу поддерживать встроенные элементы. Извлеките `COleServerItem` класс из для реализации элементов в документах и возврата объектов этого класса из. `OnGetEmbeddedItem`

Для поддержки `COleServerDoc` связанных элементов предоставляется функция участника [OnGetLinkedItem.](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) Вы можете использовать реализацию по умолчанию или переопределить ее, если у вас есть свой собственный способ управления элементами документов.

Для каждого `COleServerDoc`типа серверного документа, поддерживаемого вашим приложением, нужен один -производный класс. Например, если приложение сервера поддерживает листы и `COleServerDoc`диаграммы, вам нужно два класса.

Для получения дополнительной информации [Servers: Implementing a Server](../../mfc/servers-implementing-a-server.md)о серверах см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

`COleServerDoc`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="coleserverdocactivatedocobject"></a><a name="activatedocobject"></a>ColeServerDoc::ActivateDocObject

Активирует связанный документ DocObject.

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>Примечания

По умолчанию не `COleServerDoc` поддерживает активные документы (также называемые DocObjects). Чтобы включить эту поддержку, смотрите [GetDocObjectServer](#getdocobjectserver) и класс [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md).

## <a name="coleserverdocactivateinplace"></a><a name="activateinplace"></a>ColeServerDoc:ActivateinPlace

Активирует элемент для редактирования на месте.

```
BOOL ActivateInPlace();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно; в противном случае 0, что указывает на то, что элемент полностью открыт.

### <a name="remarks"></a>Примечания

Эта функция выполняет все операции, необходимые для активации на месте. Он создает окно кадра на месте, активирует его и размерирует его к элементу, настраивает общие меню и другие элементы управления, прокручивает элемент в поле зрения и устанавливает фокус к окну кадра на месте.

Эта функция называется реализацией по умолчанию [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow). Вызовите эту функцию, если приложение поддерживает другой глагол для активации на месте (например, Play).

## <a name="coleserverdoccoleserverdoc"></a><a name="coleserverdoc"></a>ColeServerDoc::COleServerDoc

Строит объект `COleServerDoc` без соединения с DLL системы OLE.

```
COleServerDoc();
```

### <a name="remarks"></a>Примечания

Вы должны позвонить [COleLinkingDoc::Регистрация](../../mfc/reference/colelinkingdoc-class.md#register) для открытия связи с OLE. Если вы используете [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) `COleLinkingDoc::Register` в вашем приложении, называется `OnOpenDocument`для `OnSaveDocument`вас `COleLinkingDoc`'с реализацией `OnNewDocument`, и .

## <a name="coleserverdoccreateinplaceframe"></a><a name="createinplaceframe"></a>ColeServerdoc::CreateinPlaceframe

Платформа вызывает эту функцию для создания окна кадра для редактирования на месте.

```
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на родительское окно контейнерного приложения.

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно кадра на месте или NULL, если он не удался.

### <a name="remarks"></a>Примечания

Реализация по умолчанию использует информацию, указанную в шаблоне документа, для создания кадра. Используемое представление — это первое представление, созданное для документа. Это представление временно отделяется от исходного кадра и прикрепляется к вновь созданному кадру.

Это передовой overridable.

## <a name="coleserverdocdeactivateandundo"></a><a name="deactivateandundo"></a>ColeServerDoc::DэактивироватьАнддундо

Вызовите эту функцию, если приложение поддерживает Отменить и пользователь выбирает Отменить после активации элемента, но перед редактированием его.

```
BOOL DeactivateAndUndo();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Если контейнерное приложение написано с помощью библиотеки класса Microsoft Foundation, вызов этой функции вызывает вызов [COleClientItem::OnDeactivateAndUndo,](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) который отключает пользовательский интерфейс сервера.

## <a name="coleserverdocdestroyinplaceframe"></a><a name="destroyinplaceframe"></a>ColeServerDoc::DestroyInPlaceframe

Платформа вызывает эту функцию, чтобы уничтожить окно кадра на месте и вернуть окно документа приложения сервера в состояние перед активацией на месте.

```
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>Параметры

*pFrameWnd*<br/>
Указатель на окно рамы, которое должно быть уничтожено.

### <a name="remarks"></a>Примечания

Это передовой overridable.

## <a name="coleserverdocdiscardundostate"></a><a name="discardundostate"></a>ColeServerDoc::DiscardUndoState

Если пользователь выполняет операцию редактирования, которая не может быть отменена, позвоните в эту функцию, чтобы заставить контейнерное приложение отказаться от информации о состоянии, отменяемых от нее.

```
BOOL DiscardUndoState();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Эта функция предусмотрена таким образом, что серверы, поддерживающие Undo, могут свободно высвободействовать ресурсы, которые в противном случае были бы использованы неиспользуемой информацией об отстойном состоянии, которая не может быть использована.

## <a name="coleserverdocgetclientsite"></a><a name="getclientsite"></a>ColeServerDoc::GetClientSite

Извлекает указатель на базовый `IOleClientSite` интерфейс.

```
LPOLECLIENTSITE GetClientSite() const;
```

### <a name="return-value"></a>Возвращаемое значение

Извлекает указатель на базовый интерфейс [IOleClientSite.](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite)

## <a name="coleserverdocgetdocobjectserver"></a><a name="getdocobjectserver"></a>ColeServerDoc::GetDocObjectServer

Переизбь эту функцию для создания нового `CDocObjectServer` элемента и возврата указателя на него.

```
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```

### <a name="parameters"></a>Параметры

*pDocSite*<br/>
Указатель на `IOleDocumentSite` интерфейс, который подключит этот документ к серверу.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CDocObjectServer`a; NULL, если операция не удалась.

### <a name="remarks"></a>Примечания

При активации сервера DocObject возврат указателя, не являющихся null, показывает, что клиент может поддерживать DocObjects. Реализация по умолчанию возвращает NULL.

Типичная реализация документа, поддерживающего DocObjects, `CDocObjectServer` просто выделит новый объект и вернет его вызывающему. Пример:

[!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]

## <a name="coleserverdocgetembeddeditem"></a><a name="getembeddeditem"></a>ColeServerDoc::GetEmbeddedItem

Вызовите эту функцию, чтобы получить указатель на элемент, представляющий весь документ.

```
COleServerItem* GetEmbeddedItem();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент, представляющий весь документ; NULL, если операция не удалась.

### <a name="remarks"></a>Примечания

Он называет [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), виртуальная функция без реализации по умолчанию.

## <a name="coleserverdocgetitemcliprect"></a><a name="getitemcliprect"></a>ColeServerDoc::GetItemClipRect

Вызов `GetItemClipRect` функции участника, чтобы получить отсечения прямоугольник координаты элемента, который редактируется на месте.

```cpp
void GetItemClipRect(LPRECT lpClipRect) const;
```

### <a name="parameters"></a>Параметры

*lpClipRect*<br/>
Указатель на `RECT` структуру `CRect` или объект для получения координат отсечения-прямоугольника элемента.

### <a name="remarks"></a>Примечания

Координаты находятся в пикселях относительно клиентской области окна контейнерного приложения.

Рисунок не должен происходить за пределами прямоугольника отсечения. Обычно рисунок автоматически ограничивается. Используйте эту функцию, чтобы определить, прокрутил ли пользователь за пределами видимой части документа; если это так, прокрутите контейнерный документ по мере необходимости с помощью вызова [на ScrollContainerBy.](#scrollcontainerby)

## <a name="coleserverdocgetitemposition"></a><a name="getitemposition"></a>ColeServerDoc::GetItemPosition

Вызов `GetItemPosition` функции участника, чтобы получить координаты элемента, редактируемого на месте.

```cpp
void GetItemPosition(LPRECT lpPosRect) const;
```

### <a name="parameters"></a>Параметры

*lpPosRect*<br/>
Указатель на `RECT` структуру `CRect` или объект для получения координат элемента.

### <a name="remarks"></a>Примечания

Координаты находятся в пикселях относительно клиентской области окна контейнерного приложения.

Положение элемента можно сравнить с текущим прямоугольником отсечения, чтобы определить, в какой степени элемент виден (или не виден) на экране.

## <a name="coleserverdocgetzoomfactor"></a><a name="getzoomfactor"></a>ColeServerDoc::Get'mFactor

Функция `GetZoomFactor` участника определяет «зум-фактор» элемента, который был активирован для редактирования на месте.

```
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,
    LPSIZE lpSizeDenom = NULL,
    LPCRECT lpPosRect = NULL) const;
```

### <a name="parameters"></a>Параметры

*lpSizeNum*<br/>
Указатель на объект `CSize` класса, который будет держать числовируя фактора масштабирования. Может иметь значение NULL.

*lpSizeDenom*<br/>
Указатель на объект `CSize` класса, который будет удерживать знаменатель фактора масштабирования. Может иметь значение NULL.

*lpPosRect*<br/>
Указатель на объект `CRect` класса, описывающий новое положение элемента. Если этот аргумент NULL, функция использует текущее положение элемента.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент активирован для редактирования на месте и его коэффициент масштабирования не превышает 100% (1:1); в противном случае 0.

### <a name="remarks"></a>Примечания

Коэффициент масштабирования в пикселях — это доля размера элемента в его текущей степени. Если контейнерное приложение не установило размер элемента, используется его естественный размер (как определено [COleServerItem:OnGetExtent).](../../mfc/reference/coleserveritem-class.md#ongetextent)

Функция устанавливает первые два аргумента в числовитель и знаменатель "зум-фактора" элемента. Если элемент не редактируется, функция устанавливает эти аргументы на значение по умолчанию 100% (или 1:1) и возвращаетное значение ноль. Для получения дополнительной информации см. Техническое примечание 40, [MFC/OLE In-Place Resizing и масштабирование](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).

## <a name="coleserverdocisdocobject"></a><a name="isdocobject"></a>ColeServerDoc::IsDocObject

Определяет, является ли документ DocObject.

```
BOOL IsDocObject() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если документ DocObject; в противном случае FALSE.

## <a name="coleserverdocisembedded"></a><a name="isembedded"></a>ColeServerDoc::Isembedded

Вызов `IsEmbedded` функции участника, чтобы определить, представляет ли документ объект, встроенный в контейнер.

```
BOOL IsEmbedded() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `COleServerDoc` если объект представляет собой объект, встроенный в контейнер; в противном случае 0.

### <a name="remarks"></a>Примечания

Документ, загруженный из файла, не встраивается, хотя им может манипулировать контейнерное приложение в качестве ссылки. Документ, встроенный в контейнерный документ, считается встроенным.

## <a name="coleserverdocisinplaceactive"></a><a name="isinplaceactive"></a>ColeServerdoc::IsinPlaceActive

Вызовите функцию участника, `IsInPlaceActive` чтобы определить, находится ли элемент в настоящее время в активном состоянии.

```
BOOL IsInPlaceActive() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `COleServerDoc` если объект активен на месте; в противном случае 0.

## <a name="coleserverdocnotifychanged"></a><a name="notifychanged"></a>ColeServerDoc::NotifyChanged

Позвоните в эту функцию, чтобы уведомить все связанные элементы, связанные с документом, что документ изменился.

```cpp
void NotifyChanged();
```

### <a name="remarks"></a>Примечания

Как правило, эту функцию вызывают после изменения пользователем некоторых глобальных атрибутов, таких как размеры серверного документа. Если элемент OLE связан с документом с автоматической ссылкой, элемент обновляется с учетом изменений. В контейнерных приложениях, написанных в библиотеке `COleClientItem` класса Microsoft Foundation, вызывается функция участника [OnChange.](../../mfc/reference/coleclientitem-class.md#onchange)

> [!NOTE]
> Эта функция включена для совместимости с OLE 1. Новые приложения должны использовать [UpdateAllItems](#updateallitems).

## <a name="coleserverdocnotifyclosed"></a><a name="notifyclosed"></a>ColeServerDoc::NotifyClosed

Позвоните в эту функцию, чтобы уведомить контейнер (ы), что документ был закрыт.

```cpp
void NotifyClosed();
```

### <a name="remarks"></a>Примечания

Когда пользователь выбирает команду Close из меню `NotifyClosed` файла, вызывается выполнением `COleServerDoc`функции участника [OnCloseDocument.](../../mfc/reference/cdocument-class.md#onclosedocument) В контейнерных приложениях, написанных в библиотеке `COleClientItem` класса Microsoft Foundation, вызывается функция участника [OnChange.](../../mfc/reference/coleclientitem-class.md#onchange)

## <a name="coleserverdocnotifyrename"></a><a name="notifyrename"></a>ColeServerDoc::NotifyRename

Вызовите эту функцию после того, как пользователь переименует серверный документ.

```cpp
void NotifyRename(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Параметры

*lpszNewName*<br/>
Указатель на строку с указанием нового имени серверного документа; это, как правило, полностью квалифицированный путь.

### <a name="remarks"></a>Примечания

Когда пользователь выбирает команду Save As из `NotifyRename` меню файла, вызывается `COleServerDoc`реализация функции участника [OnSaveDocument.](../../mfc/reference/cdocument-class.md#onsavedocument) Эта функция уведомляет систему OL DLL, которая, в свою очередь, уведомляет контейнеры. В контейнерных приложениях, написанных в библиотеке `COleClientItem` класса Microsoft Foundation, вызывается функция участника [OnChange.](../../mfc/reference/coleclientitem-class.md#onchange)

## <a name="coleserverdocnotifysaved"></a><a name="notifysaved"></a>ColeServerDoc::NotifySaved

Вызовите эту функцию после того, как пользователь сохраняет серверный документ.

```cpp
void NotifySaved();
```

### <a name="remarks"></a>Примечания

Когда пользователь выбирает команду Сохранить из меню `NotifySaved` файла, `COleServerDoc`требуется для вас реализация [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument). Эта функция уведомляет систему OL DLL, которая, в свою очередь, уведомляет контейнеры. В контейнерных приложениях, написанных в библиотеке `COleClientItem` класса Microsoft Foundation, вызывается функция участника [OnChange.](../../mfc/reference/coleclientitem-class.md#onchange)

## <a name="coleserverdoconclose"></a><a name="onclose"></a>ColeServerDoc::Onclose

Вызывается системой, когда контейнер запрашивает, чтобы серверный документ был закрыт.

```
virtual void OnClose(OLECLOSE dwCloseOption);
```

### <a name="parameters"></a>Параметры

*dwCloseOption*<br/>
Значение из перечисления OLECLOSE. Этот параметр может принимать одно из следующих значений:

- OLECLOSE_SAVEIFDIRTY Файл сохраняется, если он был изменен.

- OLECLOSE_NOSAVE Файл закрыт без сохранения.

- OLECLOSE_PROMPTSAVE Если файл был изменен, пользователю предлагается сохранить его.

### <a name="remarks"></a>Примечания

Вызовы реализации по `CDocument::OnCloseDocument`умолчанию.

Для получения дополнительной информации и дополнительных значений [см.](/windows/win32/api/oleidl/ne-oleidl-oleclose)

## <a name="coleserverdocondeactivate"></a><a name="ondeactivate"></a>ColeServerDoc::OnDeactivate

Вызывается в рамках, когда пользователь деактивирует встроенный или связанный элемент, который в настоящее время находится на месте активной.

```
virtual void OnDeactivate();
```

### <a name="remarks"></a>Примечания

Эта функция восстанавливает пользовательский интерфейс контейнерного приложения в исходное состояние и уничтожает все меню и другие элементы управления, которые были созданы для активации на месте.

Информация об отсутсвии должна быть безоговорочно опубликована в этой точке.

Для получения дополнительной информации, [см.](../../mfc/activation-cpp.md)

## <a name="coleserverdocondeactivateui"></a><a name="ondeactivateui"></a>ColeServerDoc::OnDeactivateuI

Вызывается, когда пользователь деактивирует элемент, который был активирован на месте.

```
virtual void OnDeactivateUI(BOOL bUndoable);
```

### <a name="parameters"></a>Параметры

*bUndoable*<br/>
Уточняется, могут ли быть отменены изменения редактирования.

### <a name="remarks"></a>Примечания

Эта функция восстанавливает пользовательский интерфейс контейнерного приложения в исходное состояние, скрывая все меню и другие элементы управления, которые были созданы для активации на месте.

Рамки всегда устанавливает *bUndoable* к FALSE. Если сервер поддерживает отменить и есть операция, которая может быть отменена, позвоните в реализацию базового класса с *bUndoable* набором TRUE.

## <a name="coleserverdocondocwindowactivate"></a><a name="ondocwindowactivate"></a>ColeServerDoc::OnDocWindowActivate

Платформа вызывает эту функцию для активации или деактивации окна документа для редактирования на месте.

```
virtual void OnDocWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*bActivate*<br/>
Уточняется, будет ли окно документа активировано или отключено.

### <a name="remarks"></a>Примечания

Реализация по умолчанию удаляет или добавляет элементы пользовательского интерфейса уровня кадра по мере необходимости. Переопределить эту функцию, если вы хотите выполнить дополнительные действия, когда документ, содержащий ваш элемент активирован или деактивирован.

Для получения дополнительной информации, [см.](../../mfc/activation-cpp.md)

## <a name="coleserverdoconexecolecmd"></a><a name="onexecolecmd"></a>ColeServerDoc::OnExecOleCmd

Фрейм вызывает эту функцию для выполнения заданной команды или отображения справки для команды.

```
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,
    DWORD nCmdID,
    DWORD nCmdExecOpt,
    VARIANTARG* pvarargIn,
    VARIANTARG* pvarargOut);
```

### <a name="parameters"></a>Параметры

*pguidCmdGroup*<br/>
Указатель на GUID, который определяет набор команд. Может быть NULL, чтобы указать группу команд по умолчанию.

*nCmdID*<br/>
Команда для выполнения. Должен быть в группе, идентифицированной *pguidCmdGroup*.

*nCmdExecOut*<br/>
Способ выполнения объекта, одного или нескольких следующих значений из перечисления OLECMDEXECOPT:

OLECMDEXECOPT_DODEFAULT

OLECMDEXECOPT_PROMPTUSER

OLECMDEXECOPT_DONTPROMPTUSER

OLECMDEXECOPT_SHOWHELP

*pvarargin*<br/>
Указатель на VARIANTARG, содержащий входные аргументы для команды. Может иметь значение NULL.

*pvarargOut*<br/>
Указатель на VARIANTARG для получения значений возврата вывода из команды. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха; в противном случае, один из следующих кодов ошибок:

|Значение|Описание|
|-----------|-----------------|
|E_UNEXPECTED|Произошла неожиданная ошибка|
|E_FAIL|Произошла ошибка|
|E_NOTIMPL|Указывает MFC сам должен попытаться перевести и отправить команду|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup* не является NULL, но не указывает признанную командную группу|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* не признан адекваемым командованием в группе *pguidCmdGroup*|
|OLECMDERR_DISABLED|Команда, идентифицированная *nCmdID, отключена* и не может быть выполнена|
|OLECMDERR_NOHELP|Звонивший обратился за помощью к команде, идентифицированной *nCmdID,* но помощь недоступна|
|OLECMDERR_CANCELED|Пользователь отменил выполнение|

### <a name="remarks"></a>Примечания

`COleCmdUI`может использоваться для включения, обновления и установки других свойств команд пользовательского интерфейса DocObject. После того, как команды инициализированы, вы можете выполнить их с `OnExecOleCmd`.

Платформа вызывает функцию перед попыткой перевода и отправки команды документа OLE. Вам не нужно переопределять эту функцию для обработки стандартных команд документов OLE, но вы должны предоставить переопределение этой функции, если вы хотите обрабатывать свои собственные пользовательские команды или обрабатывать команды, которые принимают параметры или результаты возврата.

Большинство команд не принимают аргументы или значения возврата. Для большинства команд абонент может пройти NULL для *pvarargIn* и *pvarargOut*. Для команд, ожидающих входно-значений, абонент может объявить и инициализировать переменную VARIANTARG и передать указатель переменной *pvarargIn.* Для команд, требующих единого значения, аргумент может храниться непосредственно в VARIANTARG и передаваться функции. Несколько аргументов должны быть упакованы в VARIANTARG с `IDispatch` использованием одного из поддерживаемых типов (например, и SAFEARRAY).

Аналогичным образом, если команда возвращает аргументы, абонент должен объявить VARIANTARG, инициализировать его VT_EMPTY и передать его адрес в *pvarargOut*. Если команда возвращает одно значение, объект может хранить это значение непосредственно в *pvarargOut.* Несколько значений вывода должны быть упакованы в той или иной форме, подходящей для VARIANTARG.

Реализация этой функции базового класса будет выполнять OLE_COMMAND_MAP структуры, связанные с командной целью, и пытаться направить команду соответствующему обработчику. Реализация базового класса работает только с командами, которые не принимают аргументы или значения возврата. Если вам нужно обрабатывать команды, которые принимают аргументы или значения возврата, вы должны переопределить эту функцию и работать с параметрами *pvarargIn* и *pvarargOut* самостоятельно.

## <a name="coleserverdoconframewindowactivate"></a><a name="onframewindowactivate"></a>ColeServerDoc::OnFrameWindowActivate

Фрейм вызывает эту функцию при активации или деактивации окна кадрового окна контейнерного приложения.

```
virtual void OnFrameWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*bActivate*<br/>
Определяет, нужно ли активировать или деактивировать окно рамы.

### <a name="remarks"></a>Примечания

Реализация по умолчанию отменяет любые режимы справки, в которые может находиться окно кадра. Переопределить эту функцию, если вы хотите выполнить специальную обработку, когда окно кадра активировано или отключено.

Для получения дополнительной информации, [см.](../../mfc/activation-cpp.md)

## <a name="coleserverdocongetembeddeditem"></a><a name="ongetembeddeditem"></a>ColeServerDoc::OnGetEmbeddedItem

Вызывается в рамках, когда контейнерное приложение вызывает серверное приложение для создания или отсвачения встроенного элемента.

```
virtual COleServerItem* OnGetEmbeddedItem() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент, представляющий весь документ; NULL, если операция не удалась.

### <a name="remarks"></a>Примечания

Реализация по умолчанию отсутствует. Необходимо переопределить эту функцию, чтобы вернуть элемент, представляющий весь документ. Это значение возврата должно быть `COleServerItem`объектом класса, полученного.

## <a name="coleserverdoconreactivateandundo"></a><a name="onreactivateandundo"></a>ColeServerDoc::OnReactivateAndUndo

Платформа вызывает эту функцию, когда пользователь решает отменить изменения, внесенные в элемент, который был активирован на месте, изменен и затем деактивирован.

```
virtual BOOL OnReactivateAndUndo();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не делает ничего, кроме возврата FALSE для обозначения сбоя.

Переопределить эту функцию, если приложение поддерживает отменить. Обычно вы выполняете операцию отмены, а `ActivateInPlace`затем активируете элемент, позвонив. Если контейнерное приложение записано в библиотеке класса Microsoft Foundation, вызов `COleClientItem::ReactivateAndUndo` вызывает вызов этой функции.

## <a name="coleserverdoconresizeborder"></a><a name="onresizeborder"></a>ColeServerDoc::OnResizeBorder

Фрейм вызывает эту функцию при изменении размера frame-окон контейнерного приложения.

```
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,
    LPOLEINPLACEUIWINDOW lpUIWindow,
    BOOL bFrame);
```

### <a name="parameters"></a>Параметры

*lpRectBorder*<br/>
Указатель на `RECT` структуру `CRect` или объект, который определяет координаты границы.

*lpUIWindow*<br/>
Указатель на объект `IOleInPlaceUIWindow` класса, которому принадлежит текущий сеанс редактирования на месте.

*bФрейм*<br/>
ПРАВДА, если *lpUIWindow* указывает на окно кадра верхнего уровня контейнерного приложения или FALSE, если *lpUIWindow* указывает на окно кадра уровня контейнера.

### <a name="remarks"></a>Примечания

Эта функция изменяет размер и регулирует панели инструментов и другие элементы пользовательского интерфейса в соответствии с новым размером окна.

Для получения дополнительной информации, [см.](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceuiwindow)

Это передовой overridable.

## <a name="coleserverdoconsethostnames"></a><a name="onsethostnames"></a>ColeServerDoc::Onsethostnamesnames

Вызывается в рамках, когда контейнер устанавливает или изменяет имена узла для этого документа.

```
virtual void OnSetHostNames(
    LPCTSTR lpszHost,
    LPCTSTR lpszHostObj);
```

### <a name="parameters"></a>Параметры

*lpszHost*<br/>
Указатель на строку, которая определяет название приложения контейнера.

*lpszHostObj*<br/>
Указатель на строку, которая определяет название контейнера для документа.

### <a name="remarks"></a>Примечания

Реализация по умолчанию изменяет название документа для всех представлений, относящихся к этому документу.

Переопределить эту функцию, если приложение устанавливает названия через другой механизм.

## <a name="coleserverdoconsetitemrects"></a><a name="onsetitemrects"></a>ColeServerDoc::OnSetItemRects

Платформа вызывает эту функцию для размещения окна рамы редактирования в окне контейнерного приложения в окне кадра контейнерного приложения.

```
virtual void OnSetItemRects(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Параметры

*lpPosRect*<br/>
Указатель на `RECT` структуру `CRect` или объект, который определяет положение окна кадра по отношению к клиентской области контейнерного приложения.

*lpClipRect*<br/>
Указатель на `RECT` структуру `CRect` или объект, который определяет прямоугольник окна окна в месте относительно клиентской области контейнерного приложения.

### <a name="remarks"></a>Примечания

При необходимости переопределить эту функцию для обновления фактора масштабирования представления.

Эта функция обычно вызывается `RequestPositionChange` в ответ на вызов, хотя она может быть вызвана в любое время контейнером, чтобы запросить изменение позиции для элемента на месте.

## <a name="coleserverdoconshowcontrolbars"></a><a name="onshowcontrolbars"></a>ColeServerDoc::OnShowControlBars

Фрейм вызывает эту функцию, чтобы показать или скрыть панели управления серверного приложения, связанные с окном кадра, идентифицированным *pFrameWnd.*

```
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,
    BOOL bShow);
```

### <a name="parameters"></a>Параметры

*pFrameWnd*<br/>
Указатель на окно кадра, чьи панели управления должны быть скрыты или показаны.

*bShow*<br/>
Определяет, отображаются ли или скрыты контрольные бары.

### <a name="remarks"></a>Примечания

Реализация по умолчанию перечисляет все панели управления, принадлежащие этому окну кадра, и скрывает или показывает их.

## <a name="coleserverdoconshowdocument"></a><a name="onshowdocument"></a>ColeServerDoc::OnshowDocument

Фрейм `OnShowDocument` вызывает функцию, когда документ сервера должен быть скрыт или отображаться.

```
virtual void OnShowDocument(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
Уточняется, должен ли пользовательский интерфейс документа отображаться или скрываться.

### <a name="remarks"></a>Примечания

Если *bShow* является правдой, реализация по умолчанию активирует серверное приложение, если это необходимо, и заставляет контейнерное приложение прокрутить окно, чтобы элемент был виден. Если *bShow* является FALSE, реализация по умолчанию отключает элемент через `OnDeactivate`вызов, затем уничтожает или скрывает все окна кадра, которые были созданы для документа, за исключением первого. Если видимые документы не остаются, реализация по умолчанию скрывает серверное приложение.

## <a name="coleserverdoconupdatedocument"></a><a name="onupdatedocument"></a>ColeServerDoc::OnUpdateDocument

Вызывается инфраструктурой при сохранении документа, который является встроенным элементом в составе документа.

```
virtual BOOL OnUpdateDocument();
```

### <a name="return-value"></a>Возвращаемое значение

Незерно, если документ был успешно обновлен; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию вызывает [COleServerDoc::NotifySaved](#notifysaved) и [COleServerDoc::SaveEmbedding](#saveembedding) функции члена, а затем отмечает документ как чистый. Переопределить эту функцию, если вы хотите выполнить специальную обработку при обновлении встроенного элемента.

## <a name="coleserverdocrequestpositionchange"></a><a name="requestpositionchange"></a>ColeServerDoc::RequestPositionChange

Вызовите эту функцию участника, чтобы приложение контейнера изменило положение элемента.

```cpp
void RequestPositionChange(LPCRECT lpPosRect);
```

### <a name="parameters"></a>Параметры

*lpPosRect*<br/>
Указатель на `RECT` структуру `CRect` или объект, содержащий новое положение элемента.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается `UpdateAllItems`(в сочетании с) при изменении данных в активном элементе на месте. После этого вызова контейнер может или не может `OnSetItemRects`выполнить изменение, вызывая . Полученная позиция может отличаться от запрашиваемых.

## <a name="coleserverdocsaveembedding"></a><a name="saveembedding"></a>ColeServerDoc::SaveEmbedding

Вызовите эту функцию, чтобы сообщить контейнерное приложение, чтобы сохранить встроенный объект.

```cpp
void SaveEmbedding();
```

### <a name="remarks"></a>Примечания

Эта функция вызывается `OnUpdateDocument`автоматически от . Обратите внимание, что эта функция приводит к обновлению элемента на диске, поэтому он обычно вызывается только в результате определенного действия пользователя.

## <a name="coleserverdocscrollcontainerby"></a><a name="scrollcontainerby"></a>ColeServerDoc::Scrollcontainerby

Позвоните `ScrollContainerBy` функции участника для прокрутки контейнерного документа `sizeScroll`по количеству, в пикселях, указанных .

```
BOOL ScrollContainerBy(CSize sizeScroll);
```

### <a name="parameters"></a>Параметры

*размерScroll*<br/>
Уотрачает, как далеко прокрутить документ контейнера.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Положительные значения указывают на прокрутку вниз и вправо; отрицательные значения указывают на прокрутку вверх и влево.

## <a name="coleserverdocupdateallitems"></a><a name="updateallitems"></a>ColeServerDoc:UpdateAllItems

Позвоните в эту функцию, чтобы уведомить все связанные элементы, связанные с документом, что документ изменился.

```cpp
void UpdateAllItems(
    COleServerItem* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL,
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Параметры

*pСендер*<br/>
Указать на элемент, который изменил документ, или NULL, если все элементы должны быть обновлены.

*lHint*<br/>
Содержит информацию об модификации.

*Phint*<br/>
Указатель на объект, хранящей информацию об модификации.

*nDrawAspect*<br/>
Определяет, как должен быть нарисован элемент. Это значение из перечисления DVASPECT. Этот параметр может принимать одно из следующих значений:

- DVASPECT_CONTENT Элемент представлен таким образом, что он может отображаться как встроенный объект внутри контейнера.

- DVASPECT_THUMBNAIL Элемент отображается в представлении "thumbnail", чтобы его можно было отображать в инструменте просмотра.

- DVASPECT_ICON Элемент представлен иконой.

- DVASPECT_DOCPRINT Элемент представлен так, как если бы он был напечатан с помощью команды Print из меню файла.

### <a name="remarks"></a>Примечания

Обычно эту функцию можно вызвать после того, как пользователь изменяет серверный документ. Если элемент OLE связан с документом с автоматической ссылкой, элемент обновляется с учетом изменений. В контейнерных приложениях, написанных в библиотеке `COleClientItem` класса Microsoft Foundation, вызывается функция участника [OnChange.](../../mfc/reference/coleclientitem-class.md#onchange)

Эта функция `OnUpdate` вызывает функцию участника для каждого из элементов документа, за исключением элемента отправки, прохождения *pHint,* *lHint*и *nDrawAspect.* Используйте эти параметры для передачи информации в элементы о внесении изменений в документ. Вы можете кодировать информацию с помощью *lHint* или определить класс, полученный `CObject`в результате, для хранения информации об изменениях и передачи объекта этого класса с помощью *pHint.* Переопределить `OnUpdate` функцию участника `COleServerItem`в классе полученных элементов для оптимизации обновления каждого элемента в зависимости от того, изменилась ли его презентация.

## <a name="see-also"></a>См. также раздел

[MFC Образец HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDocument](../../mfc/reference/coledocument-class.md)<br/>
[Класс COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)<br/>
[Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)
