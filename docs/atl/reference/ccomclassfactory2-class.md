---
title: Класс CComClassFactory2
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
ms.openlocfilehash: 0cb2064cfaea6317c4522ff917f3963fca2219b8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321015"
---
# <a name="ccomclassfactory2-class"></a>Класс CComClassFactory2

Этот класс реализует интерфейс [IClassFactory2.](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2)

## <a name="syntax"></a>Синтаксис

```
template <class license>
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

#### <a name="parameters"></a>Параметры

*Лицензии*<br/>
Класс, который реализует следующие статические функции:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComClassFactory2::СозданиеInstance](#createinstance)|Создает объект указанного CLSID.|
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Учитывая ключ лицензии, создает объект указанного CLSID.|
|[CComClassFactory2:GetLicInfo](#getlicinfo)|Извлекает информацию, описывающую возможности лицензирования фабрики класса.|
|[CComClassFactory2:LockServer](#lockserver)|Запирает фабрику классов в памяти.|
|[CComClassFactory2:RequestLicKey](#requestlickey)|Создает и возвращает ключ лицензии.|

## <a name="remarks"></a>Примечания

`CComClassFactory2`реализует интерфейс [IClassFactory2,](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) который является продолжением [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory). `IClassFactory2`контролирует создание объекта через лицензию. Фабрика класса, исполняющая на лицензионной машине, может обеспечить ключ лицензии времени выполнения. Этот ключ лицензии позволяет приложению мгновенно использовать объекты, когда полной лицензии машины не существует.

Объекты ATL обычно приобретают фабрику класса, произвнося из [CComCoClass.](../../atl/reference/ccomcoclass-class.md) Этот класс включает в себя [макроDECLARE_CLASSFACTORY,](aggregation-and-class-factory-macros.md#declare_classfactory)который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) фабрикой класса по умолчанию. Для `CComClassFactory2`использования укажите [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) макрос в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`, параметр `CComClassFactory2`шаблона к, `VerifyLicenseKey`должен `GetLicenseKey`реализовать `IsLicenseValid`статические функции, и . Ниже приводится пример простого класса лицензии:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2`вытекает из `CComClassFactory2Base` обоих и *лицензии*. `CComClassFactory2Base`, в свою очередь, происходит от `IClassFactory2` и `CComObjectRootEx< CComGlobalsThreadModel >`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

`license`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomclassfactory2createinstance"></a><a name="createinstance"></a>CComClassFactory2::СозданиеInstance

Создает объект указанного CLSID и получает указатель интерфейса к этому объекту.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Параметры

*pUnkOuter*<br/>
(в) Если объект создается как часть агрегата, то *pUnkOuter* должен быть внешним неизвестным. В противном *случае, pUnkOuter* должен быть NULL.

*riid*<br/>
(в) IID запрашиваемого интерфейса. Если *pUnkOuter* не является NULL, `IID_IUnknown` *риид* должен быть .

*ppvObj*<br/>
(ваут) Указатель на указатель интерфейса, идентифицированный *riid*. Если объект не поддерживает этот интерфейс, *ppvObj* настроен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Требует, чтобы машина была полностью лицензирована. Если полной лицензии машины не существует, позвоните [CreateInstanceLic](#createinstancelic).

## <a name="ccomclassfactory2createinstancelic"></a><a name="createinstancelic"></a>CComClassFactory2::CreateInstanceLic

Как и [CreateInstance](#createinstance) `CreateInstanceLic` , за исключением того, что требует лицензионного ключа.

```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
*/,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```

### <a name="parameters"></a>Параметры

*pUnkOuter*<br/>
(в) Если объект создается как часть агрегата, то *pUnkOuter* должен быть внешним неизвестным. В противном *случае, pUnkOuter* должен быть NULL.

*pUnkReserved*<br/>
[in] Не используется. Должен иметь значение NULL.

*riid*<br/>
(в) IID запрашиваемого интерфейса. Если *pUnkOuter* не является NULL, `IID_IUnknown` *риид* должен быть .

*bstrKey*<br/>
(в) Ключ лицензии времени выполнения, ранее полученный от звонка в `RequestLicKey`. Этот ключ необходим для создания объекта.

*ppvObject*<br/>
(ваут) Указатель на указатель интерфейса, указанный *riid.* Если объект не поддерживает этот интерфейс, *ppvObject* настроен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Вы можете получить ключ лицензии с помощью [RequestLicKey](#requestlickey). Для того, чтобы создать объект на нелицензированной `CreateInstanceLic`машине, необходимо позвонить.

## <a name="ccomclassfactory2getlicinfo"></a><a name="getlicinfo"></a>CComClassFactory2:GetLicInfo

Заполняет структуру [LICINFO](/windows/win32/api/ocidl/ns-ocidl-licinfo) информацией, описывающая возможности лицензирования фабрики класса.

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>Параметры

*pLicInfo*<br/>
(ваут) Указатель на `LICINFO` структуру.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Член `fRuntimeKeyAvail` этой структуры указывает, позволяет ли фабрика класса создавать объекты на нелицензированной машине, учитывая, что у нас есть ключ лицензии. Участник *fLicVerified* указывает, существует ли полная лицензия машины.

## <a name="ccomclassfactory2lockserver"></a><a name="lockserver"></a>CComClassFactory2:LockServer

Приращения и декреты блокировки `_Module::Lock` модуля отсчитываются по вызову и, `_Module::Unlock`соответственно.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Параметры

*Стадо*<br/>
(в) Если true, количество блокировки приращено; в противном случае количество блокировки является decremented.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`_Module`относится к глобальному экземпляру [CComModule](../../atl/reference/ccommodule-class.md) или класса, полученного из него.

Вызов `LockServer` позволяет клиенту удерживать фабрику класса, чтобы быстро создать несколько объектов.

## <a name="ccomclassfactory2requestlickey"></a><a name="requestlickey"></a>CComClassFactory2:RequestLicKey

Создает и возвращает лицензионный `fRuntimeKeyAvail` ключ, при условии, что член структуры [LICINFO](/windows/win32/api/ocidl/ns-ocidl-licinfo) является правдой.

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>Параметры

*dwReserved*<br/>
[in] Не используется. Должен равняться нулю.

*pbstrKey*<br/>
(ваут) Указатель на ключ лицензии.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Ключ лицензии необходим для вызова [CreateInstanceLic](#createinstancelic) для создания объекта на нелицензированной машине. Если `fRuntimeKeyAvail` FALSE, то объекты могут быть созданы только на полностью лицензированной машине.

Позвоните [GetLicInfo,](#getlicinfo) чтобы `fRuntimeKeyAvail`получить значение .

## <a name="see-also"></a>См. также раздел

[Класс CComClassFactoryПоток](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[Класс CComClassFactoryСинглтон](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
