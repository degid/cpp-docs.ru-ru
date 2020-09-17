---
title: Класс CComCachedTearOffObject
ms.date: 11/04/2016
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
ms.openlocfilehash: 019b90c932de144d05fbf05f3ca339f4e5d6edd1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748101"
---
# <a name="ccomcachedtearoffobject-class"></a>Класс CComCachedTearOffObject

Этот класс реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для отрыва интерфейса.

## <a name="syntax"></a>Синтаксис

```
template
<class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Параметры

*Содержащиеся*<br/>
Ваш класс отрыва, полученный из `CComTearOffObjectBase` интерфейсов, которые вы хотите, чтобы ваш объект отрыва в поддержку.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComCachedTearoffObject::CcomCachedTearOffObject](#ccomcachedtearoffobject)|Конструктор.|
|[CComCachedTearOffObject:: »CComCachedTearOffObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComCachedTearOffObject:AddRef](#addref)|Приращения отсчета `CComCachedTearOffObject` ссылки на объект.|
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|Вызывает `m_contained::FinalConstruct` (метод типа разрыва).|
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|Вызывает `m_contained::FinalRelease` (метод типа разрыва).|
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|Возвращает указатель на `IUnknown` `CComCachedTearOffObject` объект или в запрашиваемый интерфейс в классе отрыва (класс). `contained`|
|[CComCachedTearOffObject::Release](#release)|Декретирует значение подсчета `CComCachedTearOffObject` ссылок на объект и уничтожает его, если количество ссылок составляет 0.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComCachedTearOffObject::m_contained](#m_contained)|Объект, `CComContainedObject` полученный из класса отрыва `contained`(класс).|

## <a name="remarks"></a>Примечания

`CComCachedTearOffObject`реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для отрыва интерфейса. Этот класс `CComTearOffObject` отличается `CComCachedTearOffObject` тем, `IUnknown`что имеет свой собственный, отдельно от объекта владельца `IUnknown` (владелец является объектом, для которого создается разрыв). `CComCachedTearOffObject`поддерживает свой собственный подсчет `IUnknown` ссылок на его и удаляет себя, как только его количество ссылок равна нулю. Однако, если вы запросите любой из его отрывая интерфейсов, количество ссылок объекта владельца `IUnknown` будет приравнено.

Если `CComCachedTearOffObject` объект, реализующий разрыв, уже мгновенно, и интерфейс отрыва запрашивается снова, `CComCachedTearOffObject` тот же объект используется повторно. В отличие от этого, если интерфейс `CComTearOffObject` отрыва, реализованный a, `CComTearOffObject` снова запрашивается через объект владельца, другой будет мгновенно.

Класс владельца должен `FinalRelease` реализовать `Release` и призвать `IUnknown` `CComCachedTearOffObject`кэшированный для, который будет decrement его ссылка рассчитывать. Это приведет `CComCachedTearOffObject`к `FinalRelease` тому, что "с" будет вызвано и удалено разрыв.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomcachedtearoffobjectaddref"></a><a name="addref"></a>CComCachedTearOffObject:AddRef

Приращения эталонного `CComCachedTearOffObject` количества объекта по 1.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики и тестирования.

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="ccomcachedtearoffobject"></a>CComCachedTearoffObject::CcomCachedTearOffObject

Конструктор.

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
(в) Указатель на `IUnknown` `CComCachedTearOffObject`.

### <a name="remarks"></a>Примечания

Инициализирует `CComContainedObject` участника, [m_contained](#m_contained).

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="dtor"></a>CComCachedTearOffObject:: »CComCachedTearOffObject

Деструктор

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы и вызывает [FinalRelease](#finalrelease).

## <a name="ccomcachedtearoffobjectfinalconstruct"></a><a name="finalconstruct"></a>CComCachedTearOffObject::FinalConstruct

`m_contained::FinalConstruct` Вызовы `m_contained`для `CComContainedObject` <  `contained` создания,> объект, используемый для доступа к интерфейсу, реализованному вашим классом отрыва.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccomcachedtearoffobjectfinalrelease"></a><a name="finalrelease"></a>CComCachedTearOffObject::FinalRelease

Звонки `m_contained::FinalRelease` на `m_contained`бесплатное, `CComContainedObject` <  `contained`> объект.

```cpp
void FinalRelease();
```

## <a name="ccomcachedtearoffobjectm_contained"></a><a name="m_contained"></a>CComCachedTearOffObject::m_contained

Объект [CComContainedObject,](../../atl/reference/ccomcontainedobject-class.md) полученный из класса отрыва.

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>Параметры

*Содержащиеся*<br/>
(в) Ваш класс отрыва, полученный из `CComTearOffObjectBase` интерфейсов, которые вы хотите, чтобы ваш объект отрыва в поддержку.

### <a name="remarks"></a>Примечания

`m_contained` Методы наследуют используются для доступа к интерфейсу отрыва в вашем отрыв-офф класса `QueryInterface` `FinalConstruct`через `FinalRelease`кэшированный слезоточивый объект, и .

## <a name="ccomcachedtearoffobjectqueryinterface"></a><a name="queryinterface"></a>CComCachedTearOffObject::QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID запрашиваемого интерфейса.

*ppvObject*<br/>
(ваут) Указатель на указатель интерфейса, идентифицированный *iid,* или NULL, если интерфейс не найден.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если запрашиваемый `IUnknown`интерфейс, возвращает указатель `CComCachedTearOffObject`на `IUnknown` 's собственной и приращения ссылки кол. В противном случае запросы для интерфейса в классе отрыва с `CComObjectRootEx`использованием метода [Внутреннего КвейтиИнтерфейса,](ccomobjectrootex-class.md#internalqueryinterface) унаследованного от .

## <a name="ccomcachedtearoffobjectrelease"></a><a name="release"></a>CComCachedTearOffObject::Release

Удаляет значение отсчета ссылки на 1 и, если число `CComCachedTearOffObject` ссылок рассылается на 0, удаляет объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В неотлибуговых сборках всегда возвращается 0. В сборках отладок возвращается значение, которое может быть полезно для диагностики или тестирования.

## <a name="see-also"></a>См. также раздел

[Класс CComTearOffObject](../../atl/reference/ccomtearoffobject-class.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
