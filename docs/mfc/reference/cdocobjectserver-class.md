---
title: Класс CDocObjectServer
ms.date: 09/12/2018
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
helpviewer_keywords:
- CDocObjectServer [MFC], CDocObjectServer
- CDocObjectServer [MFC], ActivateDocObject
- CDocObjectServer [MFC], OnActivateView
- CDocObjectServer [MFC], OnApplyViewState
- CDocObjectServer [MFC], OnSaveViewState
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
ms.openlocfilehash: f415df35b13e50eee092f87eca0627e5cf143720
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753291"
---
# <a name="cdocobjectserver-class"></a>Класс CDocObjectServer

Реализует дополнительные интерфейсы OLE, необходимые для преобразования стандартного сервера `COleDocument` в полноценный сервер DocObject: `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`и `IPrint`.

## <a name="syntax"></a>Синтаксис

```
class CDocObjectServer : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|Формирует объект `CDocObjectServer`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|Активирует сервер объекта документа, но не показывает его.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CDocObjectServer::OnActivateView](#onactivateview)|Отображает представление DocObject.|
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|Восстанавливает состояние представления DocObject.|
|[CDocObjectServer::OnSaveviewState](#onsaveviewstate)|Сохраняет состояние представления DocObject.|

## <a name="remarks"></a>Примечания

`CDocObjectServer`происходит от `CCmdTarget` и работает в `COleServerDoc` тесном контакте с подвергать интерфейсы.

Серверный документ DocObject может содержать объекты [CDocObjectServerItem,](../../mfc/reference/cdocobjectserveritem-class.md) которые представляют интерфейс сервера для элементов DocObject.

Чтобы настроить сервер DocObject, вывешив свой собственный класс `CDocObjectServer` из функций настройки представления, [OnActivateView,](#onactivateview) [OnApplyViewState](#onapplyviewstate)и [OnSaveViewState.](#onsaveviewstate) Вам нужно будет предоставить новый экземпляр вашего класса в ответ на вызовы фреймворка.

Для получения дополнительной информации о DocObjects, [см. CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) и [COleCmdUI](../../mfc/reference/colecmdui-class.md) в *MFC Справочник*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocObjectServer`

## <a name="requirements"></a>Требования

**Заголовок:** afxdocob.h

## <a name="cdocobjectserveractivatedocobject"></a><a name="activatedocobject"></a>CDocObjectServer::ActivateDocObject

Вызовите эту функцию, чтобы активировать (но не показывать) сервер объекта документа.

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>Примечания

`ActivateDocObject`вызова `IOleDocumentSite`'s `ActivateMe` метод, но не показывает вид, потому что он ждет конкретных инструкций о том, как настроить и отобразить представление, данное в вызове [на CDocObjectServer: OnActivateView](#onactivateview).

Вместе `ActivateDocObject` активируйте `OnActivateView` и отображайте представление DocObject. Активация DocObject отличается от других видов активации OLE на месте. Активация DocObject обходит границы люка и украшения объектов (например, рукоятки размеров), игнорирует функции размера объекта и рисует прокрутки баров в прямоугольнике представления, а не рисует их за пределами этого прямоугольника (как при обычной активации на месте).

## <a name="cdocobjectservercdocobjectserver"></a><a name="cdocobjectserver"></a>CDocObjectServer::CDocObjectServer

Создает и инициализирует объект `CDocObjectServer`.

```
explicit CDocObjectServer(
    COleServerDoc* pOwner,
    LPOLEDOCUMENTSITE pDocSite = NULL);
```

### <a name="parameters"></a>Параметры

*pOwner*<br/>
Указатель на документ сайта клиента, который является клиентом сервера DocObject.

*pDocSite*<br/>
Указатель на `IOleDocumentSite` интерфейс, реализованный контейнером.

### <a name="remarks"></a>Примечания

Когда DocObject активен, интерфейс клиента `IOleDocumentSite`сайта OLE () позволяет серверу DocObject общаться со своим клиентом (контейнером). При активации сервера DocObject сначала проверяется, реализует `IOleDocumentSite` ли контейнер интерфейс. Если это так, [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) называется, чтобы увидеть, если контейнер поддерживает DocObjects. По умолчанию возвращает `GetDocObjectServer` NULL. Необходимо `COleServerDoc::GetDocObjectServer` переопределить, чтобы `CDocObjectServer` построить новый объект или собственный объект, `COleServerDoc` с `IOleDocumentSite` указателями на контейнер и его интерфейс в качестве аргументов для конструктора.

## <a name="cdocobjectserveronactivateview"></a><a name="onactivateview"></a>CDocObjectServer::OnActivateView

Вызовите эту функцию для отображения представления DocObject.

```
virtual HRESULT OnActivateView();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение ошибки или предупреждения. По умолчанию, возвращает NOERROR в случае успеха; в противном случае, E_FAIL.

### <a name="remarks"></a>Примечания

Эта функция создает окно кадра на месте, рисует прокрутки в представлении, настраивает меню, которое сервер делит с контейнером, добавляет элементы управления кадром, устанавливает активный объект, затем, наконец, показывает окно кадра на месте и устанавливает фокус.

## <a name="cdocobjectserveronapplyviewstate"></a><a name="onapplyviewstate"></a>CDocObjectServer::OnApplyViewState

Переопределить эту функцию для восстановления состояния представления DocObject.

```
virtual void OnApplyViewState(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
Объект, `CArchive` с которого можно выставить состояние представления.

### <a name="remarks"></a>Примечания

Эта функция вызывается при отображении представления в первый раз после его мгновенного воспроизведения. `OnApplyViewState`инструктирует представление о репрефализации `CArchive` в соответствии с данными на объекте, ранее сохраненных с [OnSaveViewState.](#onsaveviewstate) Представление должно проверять данные `CArchive` в объекте, поскольку контейнер не пытается интерпретировать данные состояния представления каким-либо образом.

Можно использовать `OnSaveViewState` для хранения постоянной информации, характерной для состояния представления. Если вы `OnSaveViewState` переопределяете для хранения информации, вы хотите переопределить, `OnApplyViewState` чтобы прочитать эту информацию и применить ее к вашему представлению, когда она недавно активирована.

## <a name="cdocobjectserveronsaveviewstate"></a><a name="onsaveviewstate"></a>CDocObjectServer::OnSaveviewState

Переизобить эту функцию, чтобы сохранить дополнительную информацию о состоянии вашего представления DocObject.

```
virtual void OnSaveViewState(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
Объект, `CArchive` состояние представления которого является последовательным.

### <a name="remarks"></a>Примечания

Состояние может включать такие свойства, как тип представления, коэффициент масштабирования, пункт вставки и выбора и так далее. Контейнер обычно вызывает эту функцию перед деактивацией представления. Сохраненное состояние позже может быть восстановлено через [OnApplyViewState.](#onapplyviewstate)

Можно использовать `OnSaveViewState` для хранения постоянной информации, характерной для состояния представления. Если вы `OnSaveViewState` переопределяете для хранения информации, вы хотите переопределить, `OnApplyViewState` чтобы прочитать эту информацию и применить ее к вашему представлению, когда она недавно активирована.

## <a name="see-also"></a>См. также раздел

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)
