---
title: Класс CCmdTarget
ms.date: 11/04/2016
f1_keywords:
- CCmdTarget
- AFXWIN/CCmdTarget
- AFXWIN/CCmdTarget::CCmdTarget
- AFXWIN/CCmdTarget::BeginWaitCursor
- AFXWIN/CCmdTarget::DoOleVerb
- AFXWIN/CCmdTarget::EnableAutomation
- AFXWIN/CCmdTarget::EnableConnections
- AFXWIN/CCmdTarget::EnableTypeLib
- AFXWIN/CCmdTarget::EndWaitCursor
- AFXWIN/CCmdTarget::EnumOleVerbs
- AFXWIN/CCmdTarget::FromIDispatch
- AFXWIN/CCmdTarget::GetDispatchIID
- AFXWIN/CCmdTarget::GetIDispatch
- AFXWIN/CCmdTarget::GetTypeInfoCount
- AFXWIN/CCmdTarget::GetTypeInfoOfGuid
- AFXWIN/CCmdTarget::GetTypeLib
- AFXWIN/CCmdTarget::GetTypeLibCache
- AFXWIN/CCmdTarget::IsInvokeAllowed
- AFXWIN/CCmdTarget::IsResultExpected
- AFXWIN/CCmdTarget::OnCmdMsg
- AFXWIN/CCmdTarget::OnFinalRelease
- AFXWIN/CCmdTarget::RestoreWaitCursor
helpviewer_keywords:
- CCmdTarget [MFC], CCmdTarget
- CCmdTarget [MFC], BeginWaitCursor
- CCmdTarget [MFC], DoOleVerb
- CCmdTarget [MFC], EnableAutomation
- CCmdTarget [MFC], EnableConnections
- CCmdTarget [MFC], EnableTypeLib
- CCmdTarget [MFC], EndWaitCursor
- CCmdTarget [MFC], EnumOleVerbs
- CCmdTarget [MFC], FromIDispatch
- CCmdTarget [MFC], GetDispatchIID
- CCmdTarget [MFC], GetIDispatch
- CCmdTarget [MFC], GetTypeInfoCount
- CCmdTarget [MFC], GetTypeInfoOfGuid
- CCmdTarget [MFC], GetTypeLib
- CCmdTarget [MFC], GetTypeLibCache
- CCmdTarget [MFC], IsInvokeAllowed
- CCmdTarget [MFC], IsResultExpected
- CCmdTarget [MFC], OnCmdMsg
- CCmdTarget [MFC], OnFinalRelease
- CCmdTarget [MFC], RestoreWaitCursor
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
ms.openlocfilehash: 1ef7040f3be1e4c30a6dc19e6093727299c9f1c3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752710"
---
# <a name="ccmdtarget-class"></a>Класс CCmdTarget

Базовый класс для архитектуры сообщений-карты Microsoft Foundation Class Library.

## <a name="syntax"></a>Синтаксис

```
class CCmdTarget : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCmdTarget::CCmdTarget](#ccmdtarget)|Формирует объект `CCmdTarget`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCmdTarget:BeginWaitCursor](#beginwaitcursor)|Отображает курсор в качестве курсора песочных часов.|
|[CCmdTarget::DoOleVerb](#dooleverb)|Вызывает действие, указанное глаголом OLE, чтобы быть выполнено.|
|[CCmdTarget:EnableAutomation](#enableautomation)|Позволяет автоматизацию `CCmdTarget` объекта.|
|[CCmdTarget:EnableConnections](#enableconnections)|Позволяет высвобяться событиями над точками соединения.|
|[CCmdTarget:EnableTypeLib](#enabletypelib)|Позволяет библиотеку типа объекта.|
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|Возвращается к предыдущему курсору.|
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|Перечисляет глаголы ole объекта.|
|[CCmdTarget:FromIDispatch](#fromidispatch)|Возвращает указатель объекту, `CCmdTarget` связанного с указателем. `IDispatch`|
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|Получает идентификатор интерфейса основной диспетчерской.|
|[CCmdTarget::GetIDispatch](#getidispatch)|Возвращает указатель объекту, `IDispatch` связанного с объектом. `CCmdTarget`|
|[CCmdTarget:GetTypeInfoCount](#gettypeinfocount)|Извлекает количество типовых информационных интерфейсов, которые предоставляет объект.|
|[CCmdTarget:GetTypeInfoOfGuid](#gettypeinfoofguid)|Загружает описание типа, соответствующее заданному идентификатору GUID.|
|[CCmdTarget:GetTypeLib](#gettypelib)|Получает указатель в библиотеку типов.|
|[CCmdTarget:GetTypeLibCache](#gettypelibcache)|Получает кэш библиотеки типа.|
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|Позволяет использовать метод автоматизации.|
|[CCmdTarget::IsResultExpected](#isresultexpected)|Возвращает ненулевой, если функция автоматизации должна вернуть значение.|
|[CCmdTarget:OnCmdMsg](#oncmdmsg)|Маршруты и отправки командных сообщений.|
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|Очищает сятку после выхода последней ссылки OLE.|
|[CCmdTarget:ВосстановлениеWaitCursor](#restorewaitcursor)|Восстанавливает курсор песочных часов.|

## <a name="remarks"></a>Примечания

Маршруты карты сообщений — команды или сообщения к функциям-членам, которые вы пишете для их обработки. (Команда — это сообщение из элемента меню, кнопки команды или ключа акселератора.)

Ключевые классы `CCmdTarget` фреймворка, полученные из: [CView,](../../mfc/reference/cview-class.md) [CWinApp,](../../mfc/reference/cwinapp-class.md) [CDocument,](../../mfc/reference/cdocument-class.md) [CWnd](../../mfc/reference/cwnd-class.md)и [CFrameWnd.](../../mfc/reference/cframewnd-class.md) Если вы намереваетесь для нового класса обрабатывать сообщения, `CCmdTarget`вычеркните класс из одного из этих классов, полученных. Вы редко получают класс `CCmdTarget` от непосредственно.

Для обзора командных целей и `OnCmdMsg` реуктора [Command Routing](../../mfc/command-routing.md) [см.](../../mfc/command-targets.md) [Mapping Messages](../../mfc/mapping-messages.md)

`CCmdTarget`включает в себя функции членов, которые обрабатывают дисплей курсора песочных часов. Отображение курсора песочных часов, когда вы ожидаете, что команда займет заметный временной интервал для выполнения.

Карты отправки, похожие на карты сообщений, используются для использования функциональности автоматизации `IDispatch` OLE. Разоблачая этот интерфейс, другие приложения (например, Visual Basic) могут зайти в ваше приложение.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="ccmdtargetbeginwaitcursor"></a><a name="beginwaitcursor"></a>CCmdTarget:BeginWaitCursor

Вызов эту функцию для отображения курсора в качестве песочных часов, когда вы ожидаете, что команда займет заметный временной интервал для выполнения.

```cpp
void BeginWaitCursor();
```

### <a name="remarks"></a>Примечания

Платформа вызывает эту функцию, чтобы показать пользователю, `CDocument` что он занят, например, когда объект загружается или сохраняет себя в файле.

Действия `BeginWaitCursor` не всегда эффективны за пределами одного обработчика `OnSetCursor` сообщений, так как другие действия, такие как обработка, могут изменить курсор.

Вызов `EndWaitCursor` для восстановления предыдущего курсора.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="ccmdtargetccmdtarget"></a><a name="ccmdtarget"></a>CCmdTarget::CCmdTarget

Формирует объект `CCmdTarget`.

```
CCmdTarget();
```

## <a name="ccmdtargetdooleverb"></a><a name="dooleverb"></a>CCmdTarget::DoOleVerb

Вызывает действие, указанное глаголом OLE, чтобы быть выполнено.

```
BOOL DoOleVerb(
    LONG iVerb,
    LPMSG lpMsg,
    HWND hWndParent,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*iVerb*<br/>
Численный идентификатор глагола.

*lpMsg*<br/>
Указатель на структуру [MSG,](/windows/win32/api/winuser/ns-winuser-msg) описывающую событие (например, двойной клик), который вызывает глагол.

*hWndParent*<br/>
Дескриптор окна документа, содержащего объект.

*lpRect*<br/>
Указатель на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) содержащую координаты, в пикселях, которые определяют прямоугольник связывания объекта в *hwndParent*.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА в случае успеха, в противном случае FALSE.

### <a name="remarks"></a>Примечания

Эта функция члена в основном является реализацией [IOleObject: :DoVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb). Возможные действия перечисляются [CCmdTarget::EnumOleVerbs](#enumoleverbs).

## <a name="ccmdtargetenableautomation"></a><a name="enableautomation"></a>CCmdTarget:EnableAutomation

Вызовите эту функцию, чтобы включить автоматизацию OLE для объекта.

```cpp
void EnableAutomation();
```

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается от конструктора объекта и должна вызываться только в том случае, если для класса была объявлена диспетчерская карта. Для получения дополнительной информации об автоматизации смотрите статьи [Автоматизация Клиентов](../../mfc/automation-clients.md) и [Автоматизация серверов](../../mfc/automation-servers.md).

## <a name="ccmdtargetenableconnections"></a><a name="enableconnections"></a>CCmdTarget:EnableConnections

Позволяет высвобяться событиями над точками соединения.

```cpp
void EnableConnections();
```

### <a name="remarks"></a>Примечания

Чтобы включить точки соединения, позвоните в эту функцию члена в конструкторе вашего производного класса.

## <a name="ccmdtargetenabletypelib"></a><a name="enabletypelib"></a>CCmdTarget:EnableTypeLib

Позволяет библиотеку типа объекта.

```cpp
void EnableTypeLib();
```

### <a name="remarks"></a>Примечания

Вызовите эту функцию участника `CCmdTarget`в конструктор объекта, полученного из вашего объекта, если она предоставляет информацию о типе.

## <a name="ccmdtargetendwaitcursor"></a><a name="endwaitcursor"></a>CCmdTarget::EndWaitCursor

Вызовите эту функцию `BeginWaitCursor` после того, как вы вызвали функцию участника, чтобы вернуться из курсора песочных часов в предыдущий курсор.

```cpp
void EndWaitCursor();
```

### <a name="remarks"></a>Примечания

Платформа также вызывает эту функцию члена после того, как она назвала курсор песочных часов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="ccmdtargetenumoleverbs"></a><a name="enumoleverbs"></a>CCmdTarget::EnumOleVerbs

Перечисляет глаголы ole объекта.

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>Параметры

*ppenumOleVerb*<br/>
Указатель на указатель на интерфейс [IEnumOLEVERB.](/windows/win32/api/oleidl/nn-oleidl-ienumoleverb)

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если объект поддерживает по крайней \* мере один глагол OLE `IEnumOLEVERB` (в этом случае *ppenumOleVerb* указывает на интерфейс перечисления), в противном случае FALSE.

### <a name="remarks"></a>Примечания

Эта функция члена в основном является реализацией [IOleObject::EnumVerbs](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs).

## <a name="ccmdtargetfromidispatch"></a><a name="fromidispatch"></a>CCmdTarget:FromIDispatch

Назовите эту `IDispatch` функцию для картирования указателя, полученного от функций членов автоматизации класса, в `CCmdTarget` объект, реализуемый интерфейсами `IDispatch` объекта.

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>Параметры

*lpDispatch*<br/>
Указатель на объект `IDispatch`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CCmdTarget` объект, связанный с *lpDispatch.* Эта функция возвращает `IDispatch` NULL, если объект не `IDispatch` признан объектом класса Microsoft Foundation.

### <a name="remarks"></a>Примечания

Результатом этой функции является обратный вызов функции `GetIDispatch`участника.

## <a name="ccmdtargetgetdispatchiid"></a><a name="getdispatchiid"></a>CCmdTarget::GetDispatchIID

Получает идентификатор интерфейса основной диспетчерской.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>Параметры

*pIID*<br/>
Указатель на идентификатор интерфейса («GUID»(/окна/win32/api/guiddef/ns-guiddef-guid.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА в случае успеха, в противном случае FALSE. В случае \* *успеха, pIID* устанавливается на основной идентификатор интерфейса диспетчеризации.

### <a name="remarks"></a>Примечания

Выведенные классы должны переопределить эту функцию `GetDispatchIID` члена (если не переопределить, возвращает FALSE). Смотрите [COleControl](../../mfc/reference/colecontrol-class.md).

## <a name="ccmdtargetgetidispatch"></a><a name="getidispatch"></a>CCmdTarget::GetIDispatch

Вызов эту функцию элемента для извлечения `IDispatch` указателя `IDispatch` из метода `IDispatch` автоматизации, который либо возвращает указатель, либо берет указатель по ссылке.

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>Параметры

*bAddRef*<br/>
Определяет, следует ли приравнять значение отсчета ссылок на объект.

### <a name="return-value"></a>Возвращаемое значение

Указатель, `IDispatch` связанный с объектом.

### <a name="remarks"></a>Примечания

Для объектов, которые вызывают `EnableAutomation` в своих конструкторов, что делает их автоматизации `IDispatch` включен, эта функция возвращает `IDispatch` указатель на осуществление класса Фонда, который используется клиентами, которые общаются через интерфейс. Вызов этой функции автоматически добавляет ссылку на указатель, поэтому не нужно звонить в [IUnknown::AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref).

## <a name="ccmdtargetgettypeinfocount"></a><a name="gettypeinfocount"></a>CCmdTarget:GetTypeInfoCount

Извлекает количество типовых информационных интерфейсов, которые предоставляет объект.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество типовых информационных интерфейсов.

### <a name="remarks"></a>Примечания

Эта функция участника в основном реализует [IDispatch::GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount).

Полученные классы должны переопределить эту функцию, чтобы вернуть количество предоставленных информационных интерфейсов типа (либо 0, либо 1). Если не переопределено, `GetTypeInfoCount` возвращает 0. Для переопределения используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макрос, `GetTypeLib` `GetTypeLibCache`который также реализует и .

## <a name="ccmdtargetgettypeinfoofguid"></a><a name="gettypeinfoofguid"></a>CCmdTarget:GetTypeInfoOfGuid

Загружает описание типа, соответствующее заданному идентификатору GUID.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>Параметры

*lcid*<br/>
Идентификатор `LCID`локализации ().

*guid*<br/>
«ГУИД»(/окна/win32/api/guiddef/ns-guid-guid описания типа.

*ppTypeInfo*<br/>
Указатель на указатель `ITypeInfo` на интерфейс.

### <a name="return-value"></a>Возвращаемое значение

HRESULT, указывающий на успех или неудачу вызова. В случае \* успеха *ppTypeInfo* указывает на информационный интерфейс типа.

## <a name="ccmdtargetgettypelib"></a><a name="gettypelib"></a>CCmdTarget:GetTypeLib

Получает указатель в библиотеку типов.

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>Параметры

*lcid*<br/>
Идентификатор языка (LCID).

*ppTypeLib*<br/>
Указатель на указатель на `ITypeLib` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

HRESULT, указывающий на успех или неудачу вызова. В случае \* успеха *ppTypeLib* указывает на интерфейс библиотеки типов.

### <a name="remarks"></a>Примечания

Полученные классы должны переопределить эту функцию `GetTypeLib` члена (если не переопределить, возвращает TYPE_E_CANTLOADLIBRARY). Используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макрос, `GetTypeInfoCount` который `GetTypeLibCache`также реализует и .

## <a name="ccmdtargetgettypelibcache"></a><a name="gettypelibcache"></a>CCmdTarget:GetTypeLibCache

Получает кэш библиотеки типа.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CTypeLibCache`.

### <a name="remarks"></a>Примечания

Выведенные классы должны переопределить эту функцию `GetTypeLibCache` члена (если не переопределить, возвращает NULL). Используйте [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) макрос, `GetTypeInfoCount` который `GetTypeLib`также реализует и .

## <a name="ccmdtargetisinvokeallowed"></a><a name="isinvokeallowed"></a>CCmdTarget::IsInvokeAllowed

Эта функция вызывается реализацией MFC, `IDispatch::Invoke` чтобы определить, можно ли вызывать данный метод автоматизации (идентифицированный *dispid).*

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>Параметры

*Dispid*<br/>
Идентификатор отправки.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод может быть вызван, в противном случае FALSE.

### <a name="remarks"></a>Примечания

Если `IsInvokeAllowed` возвращается `Invoke` TRUE, переходит к вызову метода; в `Invoke` противном случае, потерпит неудачу, вернувшись E_UNEXPECTED.

Выведенные классы могут переопределить эту функцию, чтобы `IsInvokeAllowed` вернуть соответствующие значения (если не переопределены, возвращает TRUE). Смотрите, в [частности, COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).

## <a name="ccmdtargetisresultexpected"></a><a name="isresultexpected"></a>CCmdTarget::IsResultExpected

Используется `IsResultExpected` для определения того, ожидает ли клиент возврата от его вызова к функции автоматизации.

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция автоматизации должна вернуть значение; в противном случае 0.

### <a name="remarks"></a>Примечания

Интерфейс OLE предоставляет информацию MFC о том, использует ли клиент или игнорирует результат вызова функции, а MFC, в свою очередь, использует эту информацию для определения результата `IsResultExpected`звонка. Если производство значения возврата является временной или ресурсоемкой, можно повысить эффективность, позвонив в эту функцию перед вычислением значения возврата.

Эта функция возвращает 0 только один раз, так что вы получите действительные значения возврата от других функций автоматизации, если вы называете их от функции автоматизации, что клиент призвал.

`IsResultExpected`возвращает ненулевое значение, если вызывается, когда вызов функции автоматизации не выполняется.

## <a name="ccmdtargetoncmdmsg"></a><a name="oncmdmsg"></a>CCmdTarget:OnCmdMsg

Вызывается по системе для маршрутизации и отправки командных сообщений и обработки обновления объектов интерфейса пользователя команды.

```
virtual BOOL OnCmdMsg(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Содержит идентификатор команды.

*nКод*<br/>
Идентифицирует код уведомления команды. Смотрите **Комментарии** для получения дополнительной информации о значениях для *nCode*.

*pExtra*<br/>
Используется в соответствии со значением *nCode*. Смотрите **Комментарии** для получения дополнительной информации о *pExtra*.

*pHandlerInfo*<br/>
Если не `OnCmdMsg` NULL, заполняет *pTarget* и *pmf* членов структуры *pHandlerInfo* вместо отправки команды. Как правило, этот параметр должен быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если сообщение обработано; в противном случае 0.

### <a name="remarks"></a>Примечания

Это основная процедура реализации архитектуры командных систем.

Во время `OnCmdMsg` выполнения, отправляет команду на другие объекты или обрабатывает `CCmdTarget::OnCmdMsg`саму команду, вызывая корневой класс, который делает фактический поиск карты сообщений. Для полного описания заголовка по умолчанию [см.](../../mfc/message-handling-and-mapping.md)

В редких случаях может потребоваться переопределить эту функцию участника, чтобы расширить стандартную командную передачу платформы. Обратитесь к [Technical Note 21](../../mfc/tn021-command-and-message-routing.md) для получения подробных сведений об архитектуре командного разгрома.

Если вы `OnCmdMsg`переопределяете, вы должны предоставить соответствующее значение для *nCode,* код уведомления команды, и *pExtra*, который зависит от значения *nCode.* В следующей таблице перечислены соответствующие значения:

|*nКодовое* значение|*pExtra* значение|
|-------------------|--------------------|
|CN_COMMAND|[Ccmdui](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT\*|
|CN_UPDATE_COMMAND_UI|CCmdUI\*|
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

## <a name="ccmdtargetonfinalrelease"></a><a name="onfinalrelease"></a>CCmdTarget::OnFinalRelease

Вызывается по фреймворку при выпуске последней ссылки OLE на объект или с его самого объекта.

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>Примечания

Переопределить эту функцию, чтобы обеспечить специальное обращение для этой ситуации. Реализация по умолчанию удаляет объект.

## <a name="ccmdtargetrestorewaitcursor"></a><a name="restorewaitcursor"></a>CCmdTarget:ВосстановлениеWaitCursor

Вызовите эту функцию, чтобы восстановить соответствующий курсор песочных часов после изменения системного курсора (например, после того, как окно сообщений открылось, а затем закрылось в середине длительной операции).

```cpp
void RestoreWaitCursor();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCmdUI](../../mfc/reference/ccmdui-class.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Класс CWinApp](../../mfc/reference/cwinapp-class.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Класс ColeDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)
