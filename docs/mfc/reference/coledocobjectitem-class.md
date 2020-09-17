---
title: Класс COleDocObjectItem
ms.date: 11/04/2016
f1_keywords:
- COleDocObjectItem
- AFXOLE/COleDocObjectItem
- AFXOLE/COleDocObjectItem::COleDocObjectItem
- AFXOLE/COleDocObjectItem::DoDefaultPrinting
- AFXOLE/COleDocObjectItem::ExecCommand
- AFXOLE/COleDocObjectItem::GetActiveView
- AFXOLE/COleDocObjectItem::GetPageCount
- AFXOLE/COleDocObjectItem::OnPreparePrinting
- AFXOLE/COleDocObjectItem::OnPrint
- AFXOLE/COleDocObjectItem::QueryCommand
- AFXOLE/COleDocObjectItem::Release
helpviewer_keywords:
- COleDocObjectItem [MFC], COleDocObjectItem
- COleDocObjectItem [MFC], DoDefaultPrinting
- COleDocObjectItem [MFC], ExecCommand
- COleDocObjectItem [MFC], GetActiveView
- COleDocObjectItem [MFC], GetPageCount
- COleDocObjectItem [MFC], OnPreparePrinting
- COleDocObjectItem [MFC], OnPrint
- COleDocObjectItem [MFC], QueryCommand
- COleDocObjectItem [MFC], Release
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
ms.openlocfilehash: a696226185dd99b9e277e74d92cbe15c95cc900a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375053"
---
# <a name="coledocobjectitem-class"></a>Класс COleDocObjectItem

Реализует хранение активных документов.

## <a name="syntax"></a>Синтаксис

```
class COleDocObjectItem : public COleClientItem
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Строит `COleDocObject` элемент.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleDocObjectItem::DoDefaultPrinting](#dodefaultprinting)|Печать документа контейнерного приложения с помощью настроек принтера по умолчанию.|
|[ColeDocObjectItem::ExecCommand](#execcommand)|Выполняет команду, указанную пользователем.|
|[ColeDocObjectItem::GetActiveView](#getactiveview)|Извлекает активное представление документа.|
|[ColeDocObjectItem::GetPageCount](#getpagecount)|Извлекает количество страниц в документе контейнерного приложения.|
|[ColeDocObjectitem::На подготовкек](#onprepareprinting)|Готовит документ контейнерного приложения для печати.|
|[ColeDocObjectitem::OnPrint](#onprint)|Печать документа контейнерного приложения.|
|[ColeDocObjectItem::Запрос](#querycommand)|Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.|
|[ColeDocObjectItem::Release](#release)|Выпускает соединение с элементом, связанным с OLE, и закрывает его, если он был открыт. Не разрушает клиентский элемент.|

## <a name="remarks"></a>Примечания

В MFC активный документ обрабатывается аналогично обычному встраиванию на месте, со следующими различиями:

- Класс- `COleDocument`derived по-прежнему поддерживает список встроенных элементов; однако, эти `COleDocObjectItem`элементы могут быть -производные элементы.

- Когда активный документ активен, он занимает всю область представления клиента, когда он находится в месте активной.

- Контейнер «Активный документооборот» полностью контролирует меню **справки.**

- Меню **справки** содержит пункты меню как для контейнера документов Active, так и для сервера.

Поскольку контейнер "Активный документ" владеет меню **справки,** контейнер отвечает за пересылку сообщений меню **справки** сервера на сервер. Эта интеграция обрабатывается `COleDocObjectItem`.

Для получения дополнительной информации о слиянии меню и [активации](../../mfc/active-document-containment.md)активного документа см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`COleDocObjectItem`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="coledocobjectitemcoledocobjectitem"></a><a name="coledocobjectitem"></a>ColeDocObjectItem::COleDocObjectItem

Вызов инициализации `COleDocObjectItem` этого участника функции для инициализации объекта.

```
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>Параметры

*pContainerDoc*<br/>
Указатель на `COleDocument` объект, выступающий в качестве активного контейнера документов. Этот параметр должен быть NULL, чтобы позволить IMPLEMENT_SERIALIZE. Обычно элементы OLE построены с помощью указателя документа, не являемого NULL.

## <a name="coledocobjectitemdodefaultprinting"></a><a name="dodefaultprinting"></a>COleDocObjectItem::DoDefaultPrinting

Вызывается инфраструктурой к документу с использованием настроек по умолчанию.

```
static HRESULT DoDefaultPrinting(
    CView* pCaller,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Параметры

*pCaller*<br/>
Указатель на объект [CView,](../../mfc/reference/cview-class.md) отправляющий команду печати.

*pInfo*<br/>
Указатель на объект [CPrintInfo,](../../mfc/reference/cprintinfo-structure.md) описывающий задание, которое должно быть напечатано.

## <a name="coledocobjectitemexeccommand"></a><a name="execcommand"></a>ColeDocObjectItem::ExecCommand

Вызов ифункции этого участника для выполнения команды, указанной пользователем.

```
HRESULT ExecCommand(
    DWORD nCmdID,
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,
    const GUID* pguidCmdGroup = NULL);
```

### <a name="parameters"></a>Параметры

*nCmdID*<br/>
Идентификатор команды для выполнения. Должен быть в группе, идентифицированной *pguidCmdGroup*.

*nCmdExecOpt*<br/>
Определяет параметры выполнения команд. По умолчанию установите выполнение команды без запроса пользователя. Список значений можно просмотреть [OLECMDEXECOPT.](/windows/win32/api/docobj/ne-docobj-olecmdexecopt)

*pguidCmdGroup*<br/>
Уникальный идентификатор группы команд. По умолчанию, NULL, который определяет стандартную группу. Команда, передаваемые в *nCmdID,* должна принадлежать группе.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха; в противном случае возвращает один из следующих кодов ошибок.

|Значение|Описание|
|-----------|-----------------|
|E_UNEXPECTED|Произошла непредвиденная ошибка.|
|E_FAIL|Произошла ошибка.|
|E_NOTIMPL|Указывает MFC сам должен попытаться перевести и отправить команду.|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup* не является NULL, но не указывает признанную командную группу.|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* не признается в качестве действительной команды в группе pGroup.|
|OLECMDERR_DISABLED|Команда, идентифицированная *nCmdID, отключена* и не может быть выполнена.|
|OLECMDERR_NOHELP|Звонивший обратился за помощью к команде, идентифицированной *nCmdID,* но помощь недоступна.|
|OLECMDERR_CANCELLED|Пользователь отменил выполнение.|

### <a name="remarks"></a>Примечания

*PguidCmdGroup* и параметры *nCmdID* вместе однозначно идентифицируют команду для ввода. Параметр *nCmdExecOpt* определяет точное действие, необходимое для принятия.

## <a name="coledocobjectitemgetactiveview"></a><a name="getactiveview"></a>ColeDocObjectItem::GetActiveView

Вызовите эту функцию участника, `IOleDocumentView` чтобы получить указатель на интерфейс активного представления.

```
LPOLEDOCUMENTVIEW GetActiveView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс [IOleDocumentView](/windows/win32/api/docobj/nn-docobj-ioledocumentview) в настоящее время активного представления. Если нет текущего представления, он возвращает NULL.

### <a name="remarks"></a>Примечания

Подсчет отсчета отсчета на возвращенном `IOleDocumentView` указателе не приращен до того, как он будет возвращен этой функцией.

## <a name="coledocobjectitemgetpagecount"></a><a name="getpagecount"></a>ColeDocObjectItem::GetPageCount

Вызовите эту функцию участника, чтобы получить количество страниц в документе.

```
BOOL GetPageCount(
    LPLONG pnFirstPage,
    LPLONG pcPages);
```

### <a name="parameters"></a>Параметры

*pnFirstPage*<br/>
Указатель на номер первой страницы документа. Может быть NULL, что указывает на то, что вызывающему не нужен этот номер.

*pcPages*<br/>
Указатель на общее количество страниц в документе. Может быть NULL, что указывает на то, что вызывающему не нужен этот номер.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="coledocobjectitemonprepareprinting"></a><a name="onprepareprinting"></a>ColeDocObjectitem::На подготовкек

Эта функция члена вызывается инфраструктурой для подготовки документа для печати.

```
static BOOL OnPreparePrinting(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Параметры

*pCaller*<br/>
Указатель на объект [CView,](../../mfc/reference/cview-class.md) отправляющий команду печати.

*pInfo*<br/>
Указатель на объект [CPrintInfo,](../../mfc/reference/cprintinfo-structure.md) описывающий задание, которое должно быть напечатано.

*bPrintAll*<br/>
Уточняется, должен ли быть напечатан весь документ.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="coledocobjectitemonprint"></a><a name="onprint"></a>ColeDocObjectitem::OnPrint

Эта функция члена вызывается инфраструктурой для печати документа.

```
static void OnPrint(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Параметры

*pCaller*<br/>
Указатель на объект CView, отправляющий команду печати.

*pInfo*<br/>
Указатель на объект [CPrintInfo,](../../mfc/reference/cprintinfo-structure.md) описывающий задание, которое должно быть напечатано.

*bPrintAll*<br/>
Уточняется, должен ли быть напечатан весь документ.

## <a name="coledocobjectitemquerycommand"></a><a name="querycommand"></a>ColeDocObjectItem::Запрос

Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.

```
HRESULT QueryCommand(
    ULONG nCmdID,
    DWORD* pdwStatus,
    OLECMDTEXT* pCmdText =NULL,
    const GUID* pguidCmdGroup =NULL);
```

### <a name="parameters"></a>Параметры

*nCmdID*<br/>
идентификатор запрашиваемых команд.

*pdwStatus*<br/>
Указатель на флаги, возвращенные в результате запроса. Список возможных значений [можно](/windows/win32/api/docobj/ne-docobj-olecmdf)узнать.

*pCmdText*<br/>
Указатель на структуру [OLECMDTEXT,](/windows/win32/api/docobj/ns-docobj-olecmdtext) в которой можно вернуть информацию об имени и статусе для одной команды. Может быть NULL, чтобы указать, что вызывающему не нужна эта информация.

*pguidCmdGroup*<br/>
Уникальный идентификатор командной группы; может быть NULL, чтобы указать стандартную группу.

### <a name="return-value"></a>Возвращаемое значение

Полный список значений возврата можно узнать на примере [IOleCommandTarget::QueryStatus](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) в SDK Windows.

### <a name="remarks"></a>Примечания

Эта функция члена имитирует функциональность метода [IOleCommandTarget::queryStatus,](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) как описано в SDK Windows.

## <a name="coledocobjectitemrelease"></a><a name="release"></a>ColeDocObjectItem::Release

Выпускает соединение с элементом, связанным с OLE, и закрывает его, если он был открыт. Не разрушает клиентский элемент.

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>Параметры

*dwCloseOption*<br/>
Пометить, при каких обстоятельствах элемент OLE сохраняется при возвращении в загруженное состояние. Список возможных значений можно [узнать: COleClientItem::Закрыть](../../mfc/reference/coleclientitem-class.md#close).

### <a name="remarks"></a>Примечания

Не разрушает клиентский элемент.

## <a name="see-also"></a>См. также раздел

[MFC Образец MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[Класс ColeClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс ColeClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Класс CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)
