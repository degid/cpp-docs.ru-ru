---
title: Класс CComClassFactory
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
ms.openlocfilehash: 041575339906b83488697f1db5a7f8b08b53070e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321019"
---
# <a name="ccomclassfactory-class"></a>Класс CComClassFactory

Этот класс реализует интерфейс [IClassFactory.](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)

## <a name="syntax"></a>Синтаксис

```
class CComClassFactory
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComClassFactory::СозданиеInstance](#createinstance)|Создает объект указанного CLSID.|
|[CComClassFactory::LockServer](#lockserver)|Запирает фабрику классов в памяти.|

## <a name="remarks"></a>Примечания

`CComClassFactory`реализует интерфейс [IClassFactory,](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) который содержит методы создания объекта конкретного CLSID, а также блокировку фабрики класса в памяти, чтобы позволить создавать новые объекты быстрее. `IClassFactory`должны быть реализованы для каждого класса, который вы регистрируетесь в системном реестре и которому вы назначаете CLSID.

Объекты ATL обычно приобретают фабрику класса, произвнося из [CComCoClass.](../../atl/reference/ccomcoclass-class.md) Этот класс включает в себя `CComClassFactory` [макро-DECLARE_CLASSFACTORY,](aggregation-and-class-factory-macros.md#declare_classfactory)который объявляется фабрикой класса по умолчанию. Чтобы переопределить этот по умолчанию, укажите один из `DECLARE_CLASSFACTORY`макросов *XXX* в определении класса. Например, [в DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) макросе используется указанный класс для фабрики класса:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

В приведенном выше определении `CMyClassFactory` класса указывается, что будет использоваться в качестве фабрики класса по умолчанию объекта. `CMyClassFactory`должны вытекать `CComClassFactory` из `CreateInstance`и переопределить .

ATL предоставляет три других макроса, которые объявляют фабрику класса:

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) Использует [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), который контролирует создание через лицензию.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) Использует [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких квартирах.

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) Использует [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), который строит один объект [CComObjectGlobal.](../../atl/reference/ccomobjectglobal-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomclassfactorycreateinstance"></a><a name="createinstance"></a>CComClassFactory::СозданиеInstance

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

## <a name="ccomclassfactorylockserver"></a><a name="lockserver"></a>CComClassFactory::LockServer

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

Вызов `LockServer` позволяет клиенту удерживать фабрику класса, чтобы несколько объектов могли быть быстро созданы.

## <a name="see-also"></a>См. также раздел

[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
