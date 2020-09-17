---
title: Класс COleServerItem
ms.date: 11/04/2016
f1_keywords:
- COleServerItem
- AFXOLE/COleServerItem
- AFXOLE/COleServerItem::COleServerItem
- AFXOLE/COleServerItem::AddOtherClipboardData
- AFXOLE/COleServerItem::CopyToClipboard
- AFXOLE/COleServerItem::DoDragDrop
- AFXOLE/COleServerItem::GetClipboardData
- AFXOLE/COleServerItem::GetDocument
- AFXOLE/COleServerItem::GetEmbedSourceData
- AFXOLE/COleServerItem::GetItemName
- AFXOLE/COleServerItem::GetLinkSourceData
- AFXOLE/COleServerItem::GetObjectDescriptorData
- AFXOLE/COleServerItem::IsConnected
- AFXOLE/COleServerItem::IsLinkedItem
- AFXOLE/COleServerItem::NotifyChanged
- AFXOLE/COleServerItem::OnDoVerb
- AFXOLE/COleServerItem::OnDraw
- AFXOLE/COleServerItem::OnDrawEx
- AFXOLE/COleServerItem::OnGetClipboardData
- AFXOLE/COleServerItem::OnGetExtent
- AFXOLE/COleServerItem::OnInitFromData
- AFXOLE/COleServerItem::OnQueryUpdateItems
- AFXOLE/COleServerItem::OnRenderData
- AFXOLE/COleServerItem::OnRenderFileData
- AFXOLE/COleServerItem::OnRenderGlobalData
- AFXOLE/COleServerItem::OnSetColorScheme
- AFXOLE/COleServerItem::OnSetData
- AFXOLE/COleServerItem::OnSetExtent
- AFXOLE/COleServerItem::OnUpdate
- AFXOLE/COleServerItem::OnUpdateItems
- AFXOLE/COleServerItem::SetItemName
- AFXOLE/COleServerItem::GetDataSource
- AFXOLE/COleServerItem::OnHide
- AFXOLE/COleServerItem::OnOpen
- AFXOLE/COleServerItem::OnShow
- AFXOLE/COleServerItem::m_sizeExtent
helpviewer_keywords:
- COleServerItem [MFC], COleServerItem
- COleServerItem [MFC], AddOtherClipboardData
- COleServerItem [MFC], CopyToClipboard
- COleServerItem [MFC], DoDragDrop
- COleServerItem [MFC], GetClipboardData
- COleServerItem [MFC], GetDocument
- COleServerItem [MFC], GetEmbedSourceData
- COleServerItem [MFC], GetItemName
- COleServerItem [MFC], GetLinkSourceData
- COleServerItem [MFC], GetObjectDescriptorData
- COleServerItem [MFC], IsConnected
- COleServerItem [MFC], IsLinkedItem
- COleServerItem [MFC], NotifyChanged
- COleServerItem [MFC], OnDoVerb
- COleServerItem [MFC], OnDraw
- COleServerItem [MFC], OnDrawEx
- COleServerItem [MFC], OnGetClipboardData
- COleServerItem [MFC], OnGetExtent
- COleServerItem [MFC], OnInitFromData
- COleServerItem [MFC], OnQueryUpdateItems
- COleServerItem [MFC], OnRenderData
- COleServerItem [MFC], OnRenderFileData
- COleServerItem [MFC], OnRenderGlobalData
- COleServerItem [MFC], OnSetColorScheme
- COleServerItem [MFC], OnSetData
- COleServerItem [MFC], OnSetExtent
- COleServerItem [MFC], OnUpdate
- COleServerItem [MFC], OnUpdateItems
- COleServerItem [MFC], SetItemName
- COleServerItem [MFC], GetDataSource
- COleServerItem [MFC], OnHide
- COleServerItem [MFC], OnOpen
- COleServerItem [MFC], OnShow
- COleServerItem [MFC], m_sizeExtent
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
ms.openlocfilehash: 6131dceb314edff9f8208865e374cac349c7f1ce
ms.sourcegitcommit: 13f42c339fb7af935e3a93ac80e350d5e784c9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "87470983"
---
# <a name="coleserveritem-class"></a>Класс COleServerItem

Предоставляет серверный интерфейс элементам OLE.

## <a name="syntax"></a>Синтаксис

```
class COleServerItem : public CDocItem
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleServerItem:: COleServerItem](#coleserveritem)|Формирует объект `COleServerItem`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleServerItem:: Аддосерклипбоарддата](#addotherclipboarddata)|Размещает форматы представления и преобразования в `COleDataSource` объекте.|
|[COleServerItem:: Копитоклипбоард](#copytoclipboard)|Копирует элемент в буфер обмена.|
|[COleServerItem::D Одрагдроп](#dodragdrop)|Выполняет операцию перетаскивания.|
|[COleServerItem:: Жетклипбоарддата](#getclipboarddata)|Возвращает источник данных для использования при переносе данных (перетаскивание или буфер обмена).|
|[COleServerItem:: a Document](#getdocument)|Возвращает серверный документ, содержащий элемент.|
|[COleServerItem:: Жетембедсаурцедата](#getembedsourcedata)|Возвращает CF_EMBEDSOURCE данные для элемента OLE.|
|[COleServerItem:: Жетитемнаме](#getitemname)|Возвращает имя элемента. Используется только для связанных элементов.|
|[COleServerItem:: Жетлинксаурцедата](#getlinksourcedata)|Возвращает CF_LINKSOURCE данные для элемента OLE.|
|[COleServerItem:: Жетобжектдескриптордата](#getobjectdescriptordata)|Возвращает CF_OBJECTDESCRIPTOR данные для элемента OLE.|
|[COleServerItem:: a Connected](#isconnected)|Указывает, присоединен ли элемент к активному контейнеру.|
|[COleServerItem:: Ислинкедитем](#islinkeditem)|Указывает, представляет ли элемент связанный элемент OLE.|
|[COleServerItem:: Нотифичанжед](#notifychanged)|Обновляет все контейнеры с автоматическим обновлением связей.|
|[COleServerItem:: Ондоверб](#ondoverb)|Вызывается для выполнения команды.|
|[COleServerItem:: OnDraw](#ondraw)|Вызывается, когда контейнер запрашивает прорисовку элемента; требуется реализация.|
|[COleServerItem:: OnDrawEx](#ondrawex)|Вызывается для специализированного рисования элемента.|
|[COleServerItem:: Онжетклипбоарддата](#ongetclipboarddata)|Вызывается платформой для получения данных, которые будут скопированы в буфер обмена.|
|[COleServerItem:: OnGetExtent](#ongetextent)|Вызывается платформой для получения размера объекта OLE.|
|[COleServerItem:: Онинитфромдата](#oninitfromdata)|Вызывается платформой для инициализации элемента OLE с использованием содержимого указанного объекта пересылки данных.|
|[COleServerItem:: Онкуерюпдатеитемс](#onqueryupdateitems)|Вызывается для определения необходимости обновления любых связанных элементов.|
|[COleServerItem:: Онрендердата](#onrenderdata)|Извлекает данные в рамках отложенной отрисовки.|
|[COleServerItem:: Онрендерфиледата](#onrenderfiledata)|Извлекает данные в `CFile` объект в рамках отложенной отрисовки.|
|[COleServerItem:: Онрендерглобалдата](#onrenderglobaldata)|Извлекает данные в ХГЛОБАЛ в рамках отложенной подготовки к просмотру.|
|[COleServerItem:: Онсетколорсчеме](#onsetcolorscheme)|Вызывается для установки цветовой схемы элемента.|
|[COleServerItem:: Онсетдата](#onsetdata)|Вызывается для задания данных элемента.|
|[COleServerItem:: Онсетекстент](#onsetextent)|Вызывается платформой для установки размера элемента OLE.|
|[COleServerItem:: OnUpdate](#onupdate)|Вызывается при изменении некоторой части документа, к которой принадлежит элемент.|
|[COleServerItem:: Онупдатеитемс](#onupdateitems)|Вызывается для обновления кэша представления всех элементов в документе сервера.|
|[COleServerItem:: Сетитемнаме](#setitemname)|Задает имя элемента. Используется только для связанных элементов.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[COleServerItem:: DataSource](#getdatasource)|Возвращает объект, используемый для хранения форматов преобразования.|
|[COleServerItem:: onHide](#onhide)|Вызывается платформой для скрытия элемента OLE.|
|[COleServerItem:: OnOpen](#onopen)|Вызывается платформой для вывода элемента OLE в своем собственном окне верхнего уровня.|
|[COleServerItem:: onShow](#onshow)|Вызывается, когда контейнер запрашивает отображение элемента.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleServerItem:: m_sizeExtent](#m_sizeextent)|Информирует сервер о том, какая часть объекта OLE является видимой.|

## <a name="remarks"></a>Комментарии

Связанный элемент может представлять некоторые или все серверные документы. Внедренный элемент всегда представляет весь серверный документ.

`COleServerItem`Класс определяет несколько переопределяемых функций-членов, которые вызываются библиотеками динамической компоновки (DLL) системы OLE, обычно в ответ на запросы из приложения-контейнера. Эти функции элементов позволяют приложению контейнера манипулировать элементом неявно различными способами, например путем его отображения, выполнения команд или извлечения данных в различных форматах.

Чтобы использовать `COleServerItem` , создайте класс из него и реализуйте функции-члены [OnDraw](#ondraw) и [Serialize](../../mfc/reference/cobject-class.md#serialize) . `OnDraw`Функция предоставляет представление метафайла элемента, что позволяет отображать его при открытии приложением-контейнером составного документа. `Serialize`Функция `CObject` предоставляет собственное представление элемента, позволяя передавать внедренный элемент между серверным и контейнерным приложением. [OnGetExtent](#ongetextent) обеспечивает естественный размер элемента в контейнере, позволяя контейнеру изменять размер элемента.

Дополнительные сведения о серверах и связанных разделах см. в статьях [серверы: реализация сервера](../../mfc/servers-implementing-a-server.md) и «создание приложения-контейнера/сервера» в разделе [контейнеры статьи: дополнительные возможности](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

`COleServerItem`

## <a name="requirements"></a>Требования

**Заголовок:** афксоле.h

## <a name="coleserveritemaddotherclipboarddata"></a><a name="addotherclipboarddata"></a>COleServerItem:: Аддосерклипбоарддата

Вызовите эту функцию, чтобы разместить представления и форматы преобразования для элемента OLE в указанном `COleDataSource` объекте.

```cpp
void AddOtherClipboardData(COleDataSource* pDataSource);
```

### <a name="parameters"></a>Параметры

*пдатасаурце*<br/>
Указатель на `COleDataSource` объект, в который должны быть помещены данные.

### <a name="remarks"></a>Комментарии

Необходимо реализовать функцию-член [OnDraw](#ondraw) , чтобы предоставить формат представления (изображение метафайла) для элемента. Для поддержки других форматов преобразования зарегистрируйте их с помощью объекта [COleDataSource](../../mfc/reference/coledatasource-class.md) , возвращаемого методом GetObject [, и](#getdatasource) переопределите функцию члена [онрендердата](#onrenderdata) , чтобы предоставить данные в форматах, которые требуется поддерживать.

## <a name="coleserveritemcoleserveritem"></a><a name="coleserveritem"></a>COleServerItem:: COleServerItem

Создает `COleServerItem` объект и добавляет его в коллекцию элементов документа серверного документа.

```
COleServerItem(
    COleServerDoc* pServerDoc,
    BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*псервердок*<br/>
Указатель на документ, в котором будет содержаться новый элемент.

*баутоделете*<br/>
Флаг, указывающий, можно ли удалить объект при освобождении ссылки на него. Установите значение FALSE, если `COleServerItem` объект является неотъемлемой частью данных документа, которые необходимо удалить. Задайте значение TRUE, если объект является вторичной структурой, используемой для обнаружения диапазона в данных документа, который может быть удален платформой.

## <a name="coleserveritemcopytoclipboard"></a><a name="copytoclipboard"></a>COleServerItem:: Копитоклипбоард

Вызовите эту функцию, чтобы скопировать элемент OLE в буфер обмена.

```cpp
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```

### <a name="parameters"></a>Параметры

*бинклуделинк*<br/>
Задайте значение TRUE, если данные связи должны быть скопированы в буфер обмена. Установите значение FALSE, если серверное приложение не поддерживает ссылки.

### <a name="remarks"></a>Комментарии

Функция-член [онжетклипбоарддата](#ongetclipboarddata) используется для создания объекта [COleDataSource](../../mfc/reference/coledatasource-class.md) , содержащего данные OLE-элемента в поддерживаемых форматах. Затем функция помещает `COleDataSource` объект в буфер обмена с помощью функции [COleDataSource:: сетклипбоард](../../mfc/reference/coledatasource-class.md#setclipboard) . `COleDataSource`Объект включает в себя собственные данные элемента и его представление в CF_METAFILEPICT формате, а также данные в любых поддерживаемых форматах преобразования. Для работы этой функции члена необходимо реализовать [сериализацию](../../mfc/reference/cobject-class.md#serialize) и [OnDraw](#ondraw) .

## <a name="coleserveritemdodragdrop"></a><a name="dodragdrop"></a>COleServerItem::D Одрагдроп

Вызовите `DoDragDrop` функцию-член для выполнения операции перетаскивания.

```
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,
    CPoint ptOffset,
    BOOL bIncludeLink = FALSE,
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,
    LPCRECT lpRectStartDrag = NULL);
```

### <a name="parameters"></a>Параметры

*лпректитем*<br/>
Прямоугольник элемента на экране (в пикселях) относительно клиентской области.

*птоффсет*<br/>
Смещение от *лпитемрект* , где позиция мыши находилась в момент перетаскивания.

*бинклуделинк*<br/>
Задайте значение TRUE, если данные связи должны быть скопированы в буфер обмена. Если приложение не поддерживает ссылки, задайте для него значение FALSE.

*двеффектс*<br/>
Определяет, какие эффекты будет разрешено источником перетаскивания в операции перетаскивания (сочетание копирования, перемещения и связи).

*лпректстартдраг*<br/>
Указатель на прямоугольник, который определяет, где фактически начинается перетаскивание. Дополнительные сведения см. в разделе "Примечания".

### <a name="return-value"></a>Возвращаемое значение

Значение из перечисления ДРОПЕФФЕКТ. Если это DROPEFFECT_MOVE, исходные данные должны быть удалены.

### <a name="remarks"></a>Комментарии

Операция перетаскивания не запускается немедленно. Он ждет, пока курсор мыши не покидает прямоугольник, заданный параметром *лпректстартдраг* , или до тех пор, пока не пройдет указанное число миллисекунд. Если *лпректстартдраг* имеет значение null, то используется прямоугольник по умолчанию, чтобы перетаскивание начиналось, когда курсор мыши перемещается на один пиксель.

Время задержки задается параметром раздела реестра. Время задержки можно изменить, вызвав [CWinApp:: вритепрофилестринг](../../mfc/reference/cwinapp-class.md#writeprofilestring) или [CWinApp:: вритепрофилеинт](../../mfc/reference/cwinapp-class.md#writeprofileint). Если не указать время задержки, используется значение по умолчанию 200 миллисекунд. Время задержки перетаскивания сохраняется следующим образом:

- Время задержки перетаскивания Windows NT хранится в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini \Виндовс\драгделай.

- Время задержки перетаскивания Windows 3. x сохраняется в файле WIN.INI в разделе [Windows}.

- Время задержки перетаскивания Windows 95/98 хранится в кэшированной версии WIN.INI.

Дополнительные сведения о том, как данные задержки перетаскивания хранятся в реестре или в. INI-файла см. в разделе [вритепрофилестринг](/windows/win32/api/winbase/nf-winbase-writeprofilestringw) в Windows SDK.

## <a name="coleserveritemgetclipboarddata"></a><a name="getclipboarddata"></a>COleServerItem:: Жетклипбоарддата

Вызывайте эту функцию для заполнения указанного объекта [COleDataSource](../../mfc/reference/coledatasource-class.md) всеми данными, которые будут скопированы в буфер обмена, если вы вызвали [копитоклипбоард](#copytoclipboard) (одни и те же данные будут передаваться при вызове [DoDragDrop](#dodragdrop)).

```cpp
void GetClipboardData(
    COleDataSource* pDataSource,
    BOOL bIncludeLink = FALSE,
    LPPOINT lpOffset = NULL,
    LPSIZE lpSize = NULL);
```

### <a name="parameters"></a>Параметры

*пдатасаурце*<br/>
Указатель на `COleDataSource` объект, который будет принимать данные элемента OLE во всех поддерживаемых форматах.

*бинклуделинк*<br/>
Значение TRUE, если данные связи должны быть скопированы в буфер обмена. Значение FALSE, если серверное приложение не поддерживает ссылки.

*лпоффсет*<br/>
Смещение (в пикселях) курсора мыши от начала объекта.

*лпсизе*<br/>
Размер объекта в пикселях.

### <a name="remarks"></a>Комментарии

Эта функция вызывает функцию члена [жетембедсаурцедата](#getembedsourcedata) для получения собственных данных для элемента OLE и вызывает функцию члена [аддосерклипбоарддата](#addotherclipboarddata) для получения формата представления и всех поддерживаемых форматов преобразования. Если *бинклуделинк* имеет значение true, функция также вызывает [жетлинксаурцедата](#getlinksourcedata) для получения данных ссылки для элемента.

Переопределите эту функцию, если требуется поместить форматы в `COleDataSource` объект до или после этих форматов, предоставляемых `CopyToClipboard` .

## <a name="coleserveritemgetdatasource"></a><a name="getdatasource"></a>COleServerItem:: DataSource

Вызовите эту функцию, чтобы получить объект [COleDataSource](../../mfc/reference/coledatasource-class.md) , используемый для хранения форматов преобразования, поддерживаемых серверным приложением.

```
COleDataSource* GetDataSource();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект, `COleDataSource` используемый для хранения форматов преобразования.

### <a name="remarks"></a>Комментарии

Если вы хотите, чтобы серверное приложение предлагало данные в различных форматах во время операций обмена данными, зарегистрируйте эти форматы с помощью `COleDataSource` объекта, возвращаемого этой функцией. Например, если необходимо предоставить CF_TEXT представление OLE-элемента для буфера обмена или операций перетаскивания, можно зарегистрировать формат с `COleDataSource` объектом, который возвращает эта функция, а затем переопределить `OnRenderXxxData` функцию-член для предоставления данных.

## <a name="coleserveritemgetdocument"></a><a name="getdocument"></a>COleServerItem:: a Document

Вызовите эту функцию, чтобы получить указатель на документ, содержащий элемент.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на документ, содержащий элемент; Значение NULL, если элемент не является частью документа.

### <a name="remarks"></a>Комментарии

Это позволяет получить доступ к серверному документу, переданному в качестве аргумента в `COleServerItem` конструктор.

## <a name="coleserveritemgetembedsourcedata"></a><a name="getembedsourcedata"></a>COleServerItem:: Жетембедсаурцедата

Вызовите эту функцию, чтобы получить данные CF_EMBEDSOURCE для объекта OLE.

```cpp
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*лпстгмедиум*<br/>
Указатель на структуру [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1) , которая получит данные CF_EMBEDSOURCE для объекта OLE.

### <a name="remarks"></a>Комментарии

Этот формат включает в себя собственные данные элемента. Для `Serialize` правильной работы этой функции необходимо реализовать функцию члена.

Затем результат можно добавить в источник данных с помощью [COleDataSource:: качедата](../../mfc/reference/coledatasource-class.md#cachedata). Эта функция вызывается автоматически с помощью [COleServerItem:: онжетклипбоарддата](#ongetclipboarddata).

Дополнительные сведения см. в разделе [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1) в Windows SDK.

## <a name="coleserveritemgetitemname"></a><a name="getitemname"></a>COleServerItem:: Жетитемнаме

Вызовите эту функцию, чтобы получить имя элемента.

```
const CString& GetItemName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя элемента.

### <a name="remarks"></a>Комментарии

Обычно эта функция вызывается только для связанных элементов.

## <a name="coleserveritemgetlinksourcedata"></a><a name="getlinksourcedata"></a>COleServerItem:: Жетлинксаурцедата

Вызовите эту функцию, чтобы получить данные CF_LINKSOURCE для объекта OLE.

```
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*лпстгмедиум*<br/>
Указатель на структуру [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1) , которая получит данные CF_LINKSOURCE для объекта OLE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Комментарии

Этот формат включает CLSID, описывающий тип элемента OLE, и сведения, необходимые для нахождение документа, содержащего элемент OLE.

Затем результат можно добавить в источник данных с помощью [COleDataSource:: качедата](../../mfc/reference/coledatasource-class.md#cachedata). Эта функция вызывается автоматически с помощью [онжетклипбоарддата](#ongetclipboarddata).

Дополнительные сведения см. в разделе [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1) в Windows SDK.

## <a name="coleserveritemgetobjectdescriptordata"></a><a name="getobjectdescriptordata"></a>COleServerItem:: Жетобжектдескриптордата

Вызовите эту функцию, чтобы получить данные CF_OBJECTDESCRIPTOR для объекта OLE.

```cpp
void GetObjectDescriptorData(
    LPPOINT lpOffset,
    LPSIZE lpSize,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*лпоффсет*<br/>
Смещение щелчка мыши в левом верхнем углу элемента OLE. Может иметь значение NULL.

*лпсизе*<br/>
Размер элемента OLE. Может иметь значение NULL.

*лпстгмедиум*<br/>
Указатель на структуру [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1) , которая получит данные CF_OBJECTDESCRIPTOR для объекта OLE.

### <a name="remarks"></a>Комментарии

Сведения копируются в `STGMEDIUM` структуру, на которую указывает *лпстгмедиум*. Этот формат включает сведения, необходимые для диалогового окна «Специальная вставка».

Дополнительные сведения см. в разделе [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1) в Windows SDK.

## <a name="coleserveritemisconnected"></a><a name="isconnected"></a>COleServerItem:: a Connected

Вызовите эту функцию, чтобы проверить, подключен ли элемент OLE.

```
BOOL IsConnected() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент подключен; в противном случае — 0.

### <a name="remarks"></a>Комментарии

Элемент OLE считается подключенным, если один или несколько контейнеров имеют ссылки на этот элемент. Элемент подключается, если его счетчик ссылок больше 0 или если это внедренный элемент.

## <a name="coleserveritemislinkeditem"></a><a name="islinkeditem"></a>COleServerItem:: Ислинкедитем

Вызовите эту функцию, чтобы определить, является ли элемент OLE связанным элементом.

```
BOOL IsLinkedItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент является связанным элементом. в противном случае — 0.

### <a name="remarks"></a>Комментарии

Элемент связан, если элемент является допустимым и не возвращается в списке внедренных элементов документа. Связанный элемент может быть подключен к контейнеру или не подключаться к нему.

Обычно один и тот же класс используется как для связанных, так и для внедренных элементов. `IsLinkedItem`позволяет выполнять поведение связанных элементов не так, как внедренные элементы, хотя многие из них являются общими.

## <a name="coleserveritemm_sizeextent"></a><a name="m_sizeextent"></a>COleServerItem:: m_sizeExtent

Этот член сообщает серверу, какая часть объекта отображается в документе-контейнере.

```
CSize m_sizeExtent;
```

### <a name="remarks"></a>Комментарии

Реализация [онсетекстент](#onsetextent) по умолчанию задает этот элемент.

## <a name="coleserveritemnotifychanged"></a><a name="notifychanged"></a>COleServerItem:: Нотифичанжед

Вызовите эту функцию после изменения связанного элемента.

```cpp
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Параметры

*ндраваспект*<br/>
Значение из перечисления ДВАСПЕКТ, указывающее, какой аспект объекта OLE изменился. Этот параметр может принимать любое из перечисленных ниже значений.

- DVASPECT_CONTENT элемент представлен таким образом, что он может отображаться как внедренный объект внутри своего контейнера.

- DVASPECT_THUMBNAIL элемент отображается в виде эскиза, чтобы его можно было отобразить в средстве просмотра.

- DVASPECT_ICON элемент представлен значком.

- DVASPECT_DOCPRINT элемент представлен так, как если бы он был распечатан с помощью команды Печать в меню файл.

### <a name="remarks"></a>Комментарии

Если элемент контейнера связан с документом с автоматическим связыванием, элемент обновляется для отражения изменений. В приложениях-контейнерах, написанных с помощью библиотека Microsoft Foundation Class, в ответе вызывается [COleClientItem:: OnChange](../../mfc/reference/coleclientitem-class.md#onchange) .

## <a name="coleserveritemondoverb"></a><a name="ondoverb"></a>COleServerItem:: Ондоверб

Вызывается платформой для выполнения указанной команды.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Параметры

*иверб*<br/>
Задает выполняемую команду. Это может быть одно из следующих:

|Значение|Значение|Символ|
|-----------|-------------|------------|
|0|первичный глагол|OLEIVERB_PRIMARY|
|1|Вторичная команда|(нет)|
|- 1|Отображаемый элемент для редактирования|OLEIVERB_SHOW|
|- 2|Изменить элемент в отдельном окне|OLEIVERB_OPEN|
|- 3|Скрыть элемент|OLEIVERB_HIDE|

Значение-1 обычно является псевдонимом для другой команды. Если открытая Правка не поддерживается,-2 имеет тот же результат, что и-1. Дополнительные значения см. в разделе [иолеобжект::D оверб](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) в Windows SDK.

### <a name="remarks"></a>Комментарии

Если приложение-контейнер было написано с библиотека Microsoft Foundation Class, эта функция вызывается при вызове функции-члена [COleClientItem:: Activate](../../mfc/reference/coleclientitem-class.md#activate) соответствующего `COleClientItem` объекта. Реализация по умолчанию вызывает функцию-член [onShow](#onshow) , если указана первичная команда или OLEIVERB_SHOW, [onShow](#onopen) , если указана вторичная команда или OLEIVERB_OPEN, и [onshow](#onhide) , если указан OLEIVERB_HIDE. Реализация по умолчанию вызывает, `OnShow` Если *иверб* не является одной из команд, перечисленных выше.

Переопределите эту функцию, если основная команда не отображает элемент. Например, если элемент является записью звука и воспроизводится его основная команда, вам не нужно будет отображать серверное приложение для воспроизведения элемента.

Дополнительные сведения см. в разделе [иолеобжект::D оверб](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) в Windows SDK.

## <a name="coleserveritemondraw"></a><a name="ondraw"></a>COleServerItem:: OnDraw

Вызывается платформой для отрисовки элемента OLE в метафайл.

```
virtual BOOL OnDraw(
    CDC* pDC,
    CSize& rSize) = 0;
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
Указатель на объект [CDC](../../mfc/reference/cdc-class.md) , для которого рисуется элемент. Контекст вывода автоматически подключается к контексту для просмотра атрибута, чтобы можно было вызывать функции атрибутов, хотя это делает то же самое, что и для каждого устройства метафайлов.

*rSize*<br/>
Размер (в единицах HIMETRIC), в котором рисуется метафайл.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент был успешно нарисован; в противном случае — 0.

### <a name="remarks"></a>Комментарии

Представление метафайла элемента OLE используется для отображения элемента в контейнерном приложении. Если приложение-контейнер было написано с библиотека Microsoft Foundation Class, то этот метафайл используется функцией-членом [Draw](../../mfc/reference/coleclientitem-class.md#draw) соответствующего объекта [COleClientItem](../../mfc/reference/coleclientitem-class.md) . Реализация по умолчанию отсутствует. Эта функция должна быть переопределена для отрисовки элемента в указанном контексте устройства.

## <a name="coleserveritemondrawex"></a><a name="ondrawex"></a>COleServerItem:: OnDrawEx

Вызывается платформой для всех рисунков.

```
virtual BOOL OnDrawEx(
    CDC* pDC,
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
Указатель на объект [CDC](../../mfc/reference/cdc-class.md) , для которого рисуется элемент. Контроллер домена автоматически подключается к атрибуту контроллера домена, чтобы можно было вызывать функции атрибутов, хотя это делает это в виде метафайла, относящегося к устройству.

*ндраваспект*<br/>
Значение из перечисления ДВАСПЕКТ. Этот параметр может принимать любое из перечисленных ниже значений.

- DVASPECT_CONTENT элемент представлен таким образом, что он может отображаться как внедренный объект внутри своего контейнера.

- DVASPECT_THUMBNAIL элемент отображается в виде эскиза, чтобы его можно было отобразить в средстве просмотра.

- DVASPECT_ICON элемент представлен значком.

- DVASPECT_DOCPRINT элемент представлен так, как если бы он был распечатан с помощью команды Печать в меню файл.

*rSize*<br/>
Размер элемента в единицах HIMETRIC.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент был успешно нарисован; в противном случае — 0.

### <a name="remarks"></a>Комментарии

Реализация по умолчанию вызывает, `OnDraw` когда дваспект равен DVASPECT_CONTENT; в противном случае происходит сбой.

Переопределите эту функцию, чтобы предоставить данные представления для других аспектов, кроме DVASPECT_CONTENT, таких как DVASPECT_ICON или DVASPECT_THUMBNAIL.

## <a name="coleserveritemongetclipboarddata"></a><a name="ongetclipboarddata"></a>COleServerItem:: Онжетклипбоарддата

Вызвано платформой для получения `COleDataSource` объекта, содержащего все данные, которые будут помещены в буфер обмена путем вызова функции-члена [копитоклипбоард](#copytoclipboard) .

```
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,
    LPPOINT lpOffset,
    LPSIZE lpSize);
```

### <a name="parameters"></a>Параметры

*бинклуделинк*<br/>
Задайте значение TRUE, если данные связи должны быть скопированы в буфер обмена. Установите значение FALSE, если серверное приложение не поддерживает ссылки.

*лпоффсет*<br/>
Смещение курсора мыши от начала объекта в пикселях.

*лпсизе*<br/>
Размер объекта в пикселях.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [COleDataSource](../../mfc/reference/coledatasource-class.md) , содержащий данные буфера обмена.

### <a name="remarks"></a>Комментарии

Реализация по умолчанию этой функции вызывает [жетклипбоарддата](#getclipboarddata).

## <a name="coleserveritemongetextent"></a><a name="ongetextent"></a>COleServerItem:: OnGetExtent

Вызвано платформой для получения размера (в единицах HIMETRIC) элемента OLE.

```
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Параметры

*ндраваспект*<br/>
Задает аспект объекта OLE, границы которого должны быть извлечены. Этот параметр может принимать любое из перечисленных ниже значений.

- DVASPECT_CONTENT элемент представлен таким образом, что он может отображаться как внедренный объект внутри своего контейнера.

- DVASPECT_THUMBNAIL элемент отображается в виде эскиза, чтобы его можно было отобразить в средстве просмотра.

- DVASPECT_ICON элемент представлен значком.

- DVASPECT_DOCPRINT элемент представлен так, как если бы он был распечатан с помощью команды Печать в меню файл.

*rSize*<br/>
Ссылка на `CSize` объект, который получит размер объекта OLE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Комментарии

Если приложение-контейнер было написано с библиотека Microsoft Foundation Class, эта функция вызывается при вызове функции [-члена](../../mfc/reference/coleclientitem-class.md#getextent) `COleClientItem` GetObject соответствующего объекта. Реализация по умолчанию не выполняет никаких действий. Его необходимо реализовать самостоятельно. Переопределите эту функцию, если требуется выполнить специальную обработку при обработке запроса на размер элемента OLE.

## <a name="coleserveritemonhide"></a><a name="onhide"></a>COleServerItem:: onHide

Вызывается платформой для скрытия элемента OLE.

```
virtual void OnHide();
```

### <a name="remarks"></a>Комментарии

Вызовы по умолчанию `COleServerDoc::OnShowDocument( FALSE )` . Функция также уведомляет контейнер о том, что элемент OLE был скрыт. Переопределите эту функцию, если требуется выполнить специальную обработку при скрытии элемента OLE.

## <a name="coleserveritemoninitfromdata"></a><a name="oninitfromdata"></a>COleServerItem:: Онинитфромдата

Вызывается платформой для инициализации элемента OLE с помощью содержимого *pDataObject*.

```
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,
    BOOL bCreation);
```

### <a name="parameters"></a>Параметры

*pDataObject*<br/>
Указатель на объект данных OLE, содержащий данные в различных форматах для инициализации элемента OLE.

*бкреатион*<br/>
Значение TRUE, если функция вызывается для инициализации элемента OLE, созданного приложением-контейнером. Значение FALSE, если функция вызывается для замены содержимого уже существующего объекта OLE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Комментарии

Если *бкреатион* имеет значение true, эта функция вызывается, если контейнер реализует вставку нового объекта на основе текущего выделения. Выбранные данные используются при создании нового элемента OLE. Например, при выборе диапазона ячеек в программе электронной таблицы и последующем использовании команды «вставить новый объект» для создания диаграммы на основе значений в выбранном диапазоне. Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию, чтобы выбрать приемлемый формат из предложенных *pDataObject* и инициализировать элемент OLE на основе предоставленных данных. Это расширенный переопределяемый объект.

Дополнительные сведения см. в разделе [иолеобжект:: инитфромдата](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) в Windows SDK.

## <a name="coleserveritemonopen"></a><a name="onopen"></a>COleServerItem:: OnOpen

Вызывается платформой для вывода элемента OLE в отдельном экземпляре серверного приложения, а не на месте.

```
virtual void OnOpen();
```

### <a name="remarks"></a>Комментарии

Реализация по умолчанию активирует первое окно фрейма, в котором отображается документ, содержащий объект OLE. Если приложение является мини-сервером, то в реализации по умолчанию отображается главное окно. Функция также уведомляет контейнер о том, что был открыт элемент OLE.

Переопределите эту функцию, если требуется выполнить специальную обработку при открытии элемента OLE. Это особенно распространено для связанных элементов, где необходимо задать ссылку при открытии.

Дополнительные сведения см. в разделе [иолеклиентсите:: оншоввиндов](/windows/win32/api/oleidl/nf-oleidl-ioleclientsite-onshowwindow) в Windows SDK.

## <a name="coleserveritemonqueryupdateitems"></a><a name="onqueryupdateitems"></a>COleServerItem:: Онкуерюпдатеитемс

Вызывается платформой для определения, устарели ли все связанные элементы в текущем серверном документе.

```
virtual BOOL OnQueryUpdateItems();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ содержит элементы, нуждающиеся в обновлениях; 0, если все элементы актуальны.

### <a name="remarks"></a>Комментарии

Элемент устарел, если его исходный документ был изменен, но связанный элемент не был обновлен для отражения изменений в документе.

## <a name="coleserveritemonrenderdata"></a><a name="onrenderdata"></a>COleServerItem:: Онрендердата

Вызывается платформой для получения данных в указанном формате.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , указывающую формат, в котором запрашиваются сведения.

*лпстгмедиум*<br/>
Указывает на структуру [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1) , в которой должны возвращаться данные.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Комментарии

Указанный формат — один, ранее помещенный в `COleDataSource` объект с помощью функции-члена [Делайрендердата](../../mfc/reference/coledatasource-class.md#delayrenderdata) или [делайрендерфиледата](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) для отложенной отрисовки. Реализация по умолчанию этой функции вызывает [онрендерфиледата](#onrenderfiledata) или [онрендерглобалдата](#onrenderglobaldata)соответственно, если указанный носитель представляет собой либо файл, либо память. Если ни один из этих форматов не указан, реализация по умолчанию возвращает 0 и не выполняет никаких действий.

Если *лпстгмедиум* ->  *тимед* TYMED_NULL, стгмедиум должен выделяться и заполняться, как указано *лпформатетк->тимед*. Если не TYMED_NULL, СТГМЕДИУМ должен быть заполнен данными.

Это расширенный переопределяемый объект. Переопределите эту функцию, чтобы предоставить данные в запрошенном формате и среднем. В зависимости от данных может потребоваться переопределить одну из других версий этой функции. Если данные невелики и имеют фиксированный размер, переопределите `OnRenderGlobalData` . Если данные находятся в файле или имеют переменный размер, переопределите `OnRenderFileData` .

Дополнительные сведения см. в разделе [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata), [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1), [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc)и [тимед](/windows/win32/api/objidl/ne-objidl-tymed) в Windows SDK.

## <a name="coleserveritemonrenderfiledata"></a><a name="onrenderfiledata"></a>COleServerItem:: Онрендерфиледата

Вызывается платформой для получения данных в указанном формате, когда среда хранения представляет собой файл.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Параметры

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , указывающую формат, в котором запрашиваются сведения.

*pFile*<br/>
Указывает на `CFile` объект, в котором должны быть визуализированы данные.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Комментарии

Указанный формат — один, ранее помещенный в `COleDataSource` объект с помощью функции-члена [делайрендердата](../../mfc/reference/coledatasource-class.md#delayrenderdata) для отложенной отрисовки. Реализация по умолчанию этой функции просто возвращает значение FALSE.

Это расширенный переопределяемый объект. Переопределите эту функцию, чтобы предоставить данные в запрошенном формате и среднем. В зависимости от данных может потребоваться переопределить одну из других версий этой функции. Если требуется выполнить обработку нескольких средних носителей, переопределите [онрендердата](#onrenderdata). Если данные находятся в файле или имеют переменный размер, переопределите [онрендерфиледата](#onrenderfiledata).

Дополнительные сведения см. в разделе [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) и [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

## <a name="coleserveritemonrenderglobaldata"></a><a name="onrenderglobaldata"></a>COleServerItem:: Онрендерглобалдата

Вызывается платформой для получения данных в указанном формате, если указанный носитель является глобальной памятью.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>Параметры

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , указывающую формат, в котором запрашиваются сведения.

*фглобал*<br/>
Указывает на указатель на глобальную память, в которой должны возвращаться данные. Если память не была выделена, этот параметр может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Комментарии

Указанный формат — один, ранее помещенный в `COleDataSource` объект с помощью функции-члена [делайрендердата](../../mfc/reference/coledatasource-class.md#delayrenderdata) для отложенной отрисовки. Реализация по умолчанию этой функции просто возвращает значение FALSE.

Если *фглобал* имеет значение null, то новый хглобал должен быть выделен и возвращен в *фглобал*. В противном случае ХГЛОБАЛ, заданный параметром *фглобал* , должен быть заполнен данными. Объем данных, помещаемых в ХГЛОБАЛ, не должен превышать текущий размер блока памяти. Кроме того, блок нельзя перераспределить до большего размера.

Это расширенный переопределяемый объект. Переопределите эту функцию, чтобы предоставить данные в запрошенном формате и среднем. В зависимости от данных может потребоваться переопределить одну из других версий этой функции. Если требуется выполнить обработку нескольких средних носителей, переопределите [онрендердата](#onrenderdata). Если данные находятся в файле или имеют переменный размер, переопределите [онрендерфиледата](#onrenderfiledata).

Дополнительные сведения см. в разделе [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) и [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

## <a name="coleserveritemonsetcolorscheme"></a><a name="onsetcolorscheme"></a>COleServerItem:: Онсетколорсчеме

Вызывается платформой для указания цветовой палитры, используемой при редактировании элемента OLE.

```
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```

### <a name="parameters"></a>Параметры

*лплогпалетте*<br/>
Указатель на структуру [Логпалетте](/windows/win32/api/wingdi/ns-wingdi-logpalette) Windows.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если используется цветовая палитра; в противном случае — 0.

### <a name="remarks"></a>Комментарии

Если приложение-контейнер было написано с помощью библиотека Microsoft Foundation Class, эта функция вызывается при вызове функции [иолеобжект:: сетколорсчеме](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) соответствующего `COleClientItem` объекта. Реализация по умолчанию возвращает значение FALSE. Переопределите эту функцию, если хотите использовать рекомендуемую палитру. Серверное приложение не обязательно должно использовать предлагаемую палитру.

Дополнительные сведения см. в разделе [иолеобжект:: сетколорсчеме](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) в Windows SDK.

## <a name="coleserveritemonsetdata"></a><a name="onsetdata"></a>COleServerItem:: Онсетдата

Вызывается платформой для замены данных объекта OLE указанными данными.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Параметры

*лпформатетк*<br/>
Указатель на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , указывающую формат данных.

*лпстгмедиум*<br/>
Указатель на структуру [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1) , в которой находятся данные.

*брелеасе*<br/>
Указывает, кто является владельцем среды хранения после завершения вызова функции. Вызывающий объект решает, кто отвечает за освобождение ресурсов, выделенных от имени среды хранения. Вызывающий объект делает это, настроив *брелеасе*. Если *брелеасе* имеет ненулевое значение, элемент сервера принимает владение, освобождая носитель по завершении его использования. Если *брелеасе* имеет значение 0, вызывающий объект удерживает владение, а серверный элемент может использовать среду хранения только на время вызова.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Комментарии

Элемент сервера не принимает владение данными, пока он не будет успешно получен. То есть он не принимает владение, если возвращает 0. Если источник данных принимает владение, он освобождает среду хранения, вызывая функцию [релеасестгмедиум](/windows/win32/api/ole2/nf-ole2-releasestgmedium) .

Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию, чтобы заменить данные объекта OLE указанными данными. Это расширенный переопределяемый объект.

Дополнительные сведения см. в разделе [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1), [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc)и [релеасестгмедиум](/windows/win32/api/ole2/nf-ole2-releasestgmedium) в Windows SDK.

## <a name="coleserveritemonsetextent"></a><a name="onsetextent"></a>COleServerItem:: Онсетекстент

Вызывается платформой, чтобы сообщить элементу OLE о том, сколько места доступно для него в документе-контейнере.

```
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,
    const CSize& size);
```

### <a name="parameters"></a>Параметры

*ндраваспект*<br/>
Задает аспект объекта OLE, границы которого задаются. Этот параметр может принимать любое из перечисленных ниже значений.

- DVASPECT_CONTENT элемент представлен таким образом, что он может отображаться как внедренный объект внутри своего контейнера.

- DVASPECT_THUMBNAIL элемент отображается в виде эскиза, чтобы его можно было отобразить в средстве просмотра.

- DVASPECT_ICON элемент представлен значком.

- DVASPECT_DOCPRINT элемент представлен так, как если бы он был распечатан с помощью команды Печать в меню файл.

*size*<br/>
Структура [ксизе](../../atl-mfc-shared/reference/csize-class.md) , указывающая новый размер OLE-элемента.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Комментарии

Если приложение-контейнер было написано с библиотека Microsoft Foundation Class, эта функция вызывается при вызове функции-члена [сетекстент](../../mfc/reference/coleclientitem-class.md#setextent) соответствующего `COleClientItem` объекта. Реализация по умолчанию устанавливает [m_sizeExtent](#m_sizeextent) элемент на указанный размер, если *ндраваспект* имеет DVASPECT_CONTENT. в противном случае возвращается значение 0. Переопределите эту функцию для выполнения особой обработки при изменении размера элемента.

## <a name="coleserveritemonshow"></a><a name="onshow"></a>COleServerItem:: onShow

Вызывается платформой для указания серверному приложению отображать элемент OLE на месте.

```
virtual void OnShow();
```

### <a name="remarks"></a>Комментарии

Эта функция обычно вызывается, когда пользователь приложения-контейнера создает элемент или выполняет команду, например Edit, которая требует отображения элемента. Реализация по умолчанию пытается выполнить активацию на месте. Если это не удается, функция вызывает `OnOpen` функцию-член для вывода элемента OLE в отдельном окне.

Переопределите эту функцию, если требуется выполнить специальную обработку при отображении элемента OLE.

## <a name="coleserveritemonupdate"></a><a name="onupdate"></a>COleServerItem:: OnUpdate

Вызывается платформой при изменении элемента.

```
virtual void OnUpdate(
    COleServerItem* pSender,
    LPARAM lHint,
    CObject* pHint,
    DVASPECT nDrawAspect);
```

### <a name="parameters"></a>Параметры

*псендер*<br/>
Указатель на элемент, который изменил документ. Может иметь значение NULL.

*лхинт*<br/>
Содержит сведения об изменении.

*финт*<br/>
Указатель на объект, в котором хранятся сведения об изменении.

*ндраваспект*<br/>
Значение из перечисления ДВАСПЕКТ. Этот параметр может иметь одно из следующих значений:

- DVASPECT_CONTENT элемент представлен таким образом, что он может отображаться как внедренный объект внутри своего контейнера.

- DVASPECT_THUMBNAIL элемент отображается в виде эскиза, чтобы его можно было отобразить в средстве просмотра.

- DVASPECT_ICON элемент представлен значком.

- DVASPECT_DOCPRINT элемент представлен так, как если бы он был распечатан с помощью команды Печать в меню файл.

### <a name="remarks"></a>Комментарии

Реализация по умолчанию вызывает [нотифичанжед](#notifychanged), независимо от подсказок или отправителя.

## <a name="coleserveritemonupdateitems"></a><a name="onupdateitems"></a>COleServerItem:: Онупдатеитемс

Вызывается платформой для обновления всех элементов в документе сервера.

```
virtual void OnUpdateItems();
```

### <a name="remarks"></a>Комментарии

Реализация по умолчанию вызывает [упдателинк](../../mfc/reference/coleclientitem-class.md#updatelink) для всех `COleClientItem` объектов в документе.

## <a name="coleserveritemsetitemname"></a><a name="setitemname"></a>COleServerItem:: Сетитемнаме

Вызывайте эту функцию при создании связанного элемента, чтобы задать его имя.

```cpp
void SetItemName(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Параметры

*лпсзитемнаме*<br/>
Указатель на новое имя элемента.

### <a name="remarks"></a>Комментарии

Имя должно быть уникальным в пределах документа. При вызове серверного приложения для изменения связанного элемента приложение использует это имя для поиска элемента. Вам не нужно вызывать эту функцию для внедренных элементов.

## <a name="see-also"></a>См. также статью

[Пример MFC для примера HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс КдоЦитем](../../mfc/reference/cdocitem-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Класс Колесервердок](../../mfc/reference/coleserverdoc-class.md)<br/>
[Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)
