---
title: Класс COleTemplateServer
ms.date: 11/04/2016
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
helpviewer_keywords:
- COleTemplateServer [MFC], COleTemplateServer
- COleTemplateServer [MFC], ConnectTemplate
- COleTemplateServer [MFC], Unregister
- COleTemplateServer [MFC], UpdateRegistry
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
ms.openlocfilehash: 561da5060aae3c938dc3e55d0310718a881c1a3b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753726"
---
# <a name="coletemplateserver-class"></a>Класс COleTemplateServer

Используется для OLE-серверов визуального редактирования, серверов автоматизации и контейнеров связей (приложений, поддерживающих ссылки на внедряемые объекты).

## <a name="syntax"></a>Синтаксис

```
class COleTemplateServer : public COleObjectFactory
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeTemplateServer::COleTemplateServer](#coletemplateserver)|Формирует объект `COleTemplateServer`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeTemplateServer::ConnectTemplate](#connecttemplate)|Соединяет шаблон документа с базовым `COleObjectFactory` объектом.|
|[ColeTemplateServer::Unregister](#unregister)|Отменить регистрацию связанного шаблона документа.|
|[ColeTemplateServer::UpdateRegistry](#updateregistry)|Регистрирует тип документа в реестре системы OLE.|

## <a name="remarks"></a>Примечания

Этот класс происходит от класса [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); как правило, `COleTemplateServer` вы можете использовать непосредственно, а не производные свой собственный класс. `COleTemplateServer`использует объект [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) для управления серверными документами. Используйте `COleTemplateServer` при реализации полного сервера, то есть сервера, который можно запускать как отдельное приложение. Полные серверы, как правило, несколько документов интерфейс (MDI) приложений, хотя единый интерфейс документа (SDI) приложения поддерживаются. Для `COleTemplateServer` каждого типа серверного документа, который поддерживает приложение, необходим один объект; то есть, если приложение сервера поддерживает как листы, `COleTemplateServer` так и диаграммы, вы должны иметь два объекта.

`COleTemplateServer`переопределяет `OnCreateInstance` функцию члена, определяемую `COleObjectFactory`. Эта функция члена вызывается инфраструктурой для создания объекта сдолжного типа.

Для получения дополнительной информации [Servers: Implementing a Server](../../mfc/servers-implementing-a-server.md)о серверах см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)

`COleTemplateServer`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="coletemplateservercoletemplateserver"></a><a name="coletemplateserver"></a>ColeTemplateServer::COleTemplateServer

Формирует объект `COleTemplateServer`.

```
COleTemplateServer();
```

### <a name="remarks"></a>Примечания

Краткое описание использования `COleTemplateServer` класса можно ознакомьтесь с обзором класса [COleLinkingDoc.](../../mfc/reference/colelinkingdoc-class.md)

## <a name="coletemplateserverconnecttemplate"></a><a name="connecttemplate"></a>ColeTemplateServer::ConnectTemplate

Подключает шаблон документа, на который указывает *pDocTemplate,* к базовому объекту [COleObjectFactory.](../../mfc/reference/coleobjectfactory-class.md)

```cpp
void ConnectTemplate(
    REFCLSID clsid,
    CDocTemplate* pDocTemplate,
    BOOL bMultiInstance);
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
Ссылка на идентификатор класса OLE, запрашиваемый шаблоном.

*pDocTemplate*<br/>
Указатель на шаблон документа.

*bMultiInstance*<br/>
Указывает, может ли один экземпляр приложения поддерживать несколько моментций. Если true, несколько экземпляров приложения запускаются для каждого запроса на создание объекта.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см. ключ CLSID](/windows/win32/com/clsid-key-hklm) в SDK Windows.

## <a name="coletemplateserverunregister"></a><a name="unregister"></a>ColeTemplateServer::Unregister

Отменить регистрацию связанного шаблона документа.

```
BOOL Unregister();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

EnterRemarks

## <a name="coletemplateserverupdateregistry"></a><a name="updateregistry"></a>ColeTemplateServer::UpdateRegistry

Загружает информацию типа файла из строки документа-шаблона и помещает эту информацию в реестр системы OLE.

```cpp
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL,
    BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Параметры

*nAppType*<br/>
Значение из OLE_APPTYPE перечисления, которое определено в AFXDISP. H. Он может иметь любое из следующих значений:

- OAT_INPLACE_SERVER Сервер имеет полный пользовательский интерфейс сервера.

- OAT_SERVER Server поддерживает только встраивание.

- OAT_CONTAINER Контейнер поддерживает ссылки на встроенные объекты.

- OAT_DISPATCH_OBJECT объект `IDispatch`способен.

- OAT_DOC_OBJECT_SERVER Server поддерживает как встраивание, так и модель компонента объекта документа.

*rglpszRegister*<br/>
Список записей, которые записываются в реестр, только если нет записей.

*rglpszOverwrite*<br/>
Список записей, которые записываются в реестр, независимо от того, существуют ли какие-либо предыдущие записи.

*bРегистрация*<br/>
Определяет, должен ли класс быть зарегистрированным. Если *bRegister* является правдой, класс зарегистрирован в реестре системы. В противном случае он отменяет класс.

### <a name="remarks"></a>Примечания

Регистрационная информация загружается с помощью вызова в [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Полученные подстроки идентифицируются индексами `regFileTypeId` `regFileTypeName`и, `fileNewName`как описано `GetDocString` на справочных страницах.

Если `regFileTypeId` подстрока пуста или `GetDocString` вызов не справляется по какой-либо другой причине, эта функция выходит из строя и информация о файле не вводится в реестр.

Информация в аргументах *rglpszRegister* и *rglpszOverwrite* записывается в реестр через звонок в [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass). Информация по умолчанию, которая регистрируется, когда два аргумента являются NULL, подходит для большинства приложений. Подробнее о структуре информации в этих `AfxOleRegisterServerClass`аргументах см.

Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

## <a name="see-also"></a>См. также раздел

[MFC Образец HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс ColeServerDoc](../../mfc/reference/coleserverdoc-class.md)<br/>
[Класс ColeServerItem](../../mfc/reference/coleserveritem-class.md)
