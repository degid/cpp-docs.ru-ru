---
title: Класс CComClassFactoryПоток
ms.date: 11/04/2016
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
ms.openlocfilehash: e997d92adfa9df46c82dacbd297db495b037c6e6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320909"
---
# <a name="ccomclassfactoryautothread-class"></a>Класс CComClassFactoryПоток

Этот класс реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) и позволяет создавать объекты в нескольких квартирах.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CComClassFactoryAutoThread
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|Создает объект указанного CLSID.|
|[CComClassFactoryAutoThread::LockServer](#lockserver)|Запирает фабрику классов в памяти.|

## <a name="remarks"></a>Примечания

`CComClassFactoryAutoThread`похож на [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), но позволяет объекты, которые будут созданы в нескольких квартирах. Чтобы воспользоваться этой поддержкой, выберите модуль EXE из [CComAutoThreadModule.](../../atl/reference/ccomautothreadmodule-class.md)

Объекты ATL обычно приобретают фабрику класса, произвнося из [CComCoClass.](../../atl/reference/ccomcoclass-class.md) Этот класс включает в себя [макроDECLARE_CLASSFACTORY,](aggregation-and-class-factory-macros.md#declare_classfactory)который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) фабрикой класса по умолчанию. Для `CComClassFactoryAutoThread`использования укажите [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) макрос в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomclassfactoryautothreadcreateinstance"></a><a name="createinstance"></a>CComClassFactoryAutoThread::CreateInstance

Создает объект указанного CLSID и получает указатель интерфейса к этому объекту.

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
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

Если модуль происходит от [CComAutoThreadModule,](../../atl/reference/ccomautothreadmodule-class.md) `CreateInstance` сначала выбирает поток для создания объекта в сопутствующая квартира.

## <a name="ccomclassfactoryautothreadlockserver"></a><a name="lockserver"></a>CComClassFactoryAutoThread::LockServer

Приращения и декреты блокировки `_Module::Lock` модуля отсчитываются по вызову и, `_Module::Unlock`соответственно.

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>Параметры

*Стадо*<br/>
(в) Если true, количество блокировки приращено; в противном случае количество блокировки является decremented.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

При `CComClassFactoryAutoThread`использовании , как правило, `_Module` относится к глобальному экземпляру [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

Вызов `LockServer` позволяет клиенту удерживать фабрику класса, чтобы быстро создать несколько объектов.

## <a name="see-also"></a>См. также раздел

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[Класс CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)<br/>
[Класс CComClassFactoryСинглтон](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
