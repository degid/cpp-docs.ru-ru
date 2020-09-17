---
title: Класс CComClassFactoryСинглтон
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: ec860f7ef59b7d3289bf2e18fea0f0e064a7c8f9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320820"
---
# <a name="ccomclassfactorysingleton-class"></a>Класс CComClassFactoryСинглтон

Этот класс происходит от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для построения одного объекта.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Твой класс.

`CComClassFactorySingleton`происходит от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для построения одного объекта. Каждый вызов `CreateInstance` метода просто запрашивает этот объект для указателя интерфейса.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComClassFactorySingleton::CreateInstance](#createinstance)|Запросы `m_spObj` для указателя интерфейса.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComClassFactoryСинглтон::m_spObj](#m_spobj)|[Объект CComObjectGlobal,](../../atl/reference/ccomobjectglobal-class.md) построенный `CComClassFactorySingleton`.|

## <a name="remarks"></a>Примечания

Объекты ATL обычно приобретают фабрику класса, произвнося из [CComCoClass.](../../atl/reference/ccomcoclass-class.md) Этот класс включает в себя `CComClassFactory` [макро-DECLARE_CLASSFACTORY,](aggregation-and-class-factory-macros.md#declare_classfactory)который объявляется фабрикой класса по умолчанию. Для `CComClassFactorySingleton`использования укажите [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) макрос в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomclassfactorysingletoncreateinstance"></a><a name="createinstance"></a>CComClassFactorySingleton::CreateInstance

Вызовы `QueryInterface` через [m_spObj,](#m_spobj) чтобы получить указатель интерфейса.

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

## <a name="ccomclassfactorysingletonm_spobj"></a><a name="m_spobj"></a>CComClassFactoryСинглтон::m_spObj

[Объект CComObjectGlobal,](../../atl/reference/ccomobjectglobal-class.md) построенный `CComClassFactorySingleton`.

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>Примечания

Каждый вызов методу [CreateInstance](#createinstance) просто запрашивает этот объект для указателя интерфейса.

Обратите внимание, что `m_spObj` текущая форма представляет `CComClassFactorySingleton` собой нарушение изменения от способа, который работал в предыдущих версиях ATL. В предыдущих `CComClassFactorySingleton` версиях объект создавался одновременно с фабрикой класса, во время инициализации сервера. В Visual C'.NET 2003 и позже объект создается лениво, по первому запросу. Это изменение может привести к ошибкам в программах, которые полагаются на раннюю инициализацию.

## <a name="see-also"></a>См. также раздел

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[Класс CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)<br/>
[Класс CComClassFactoryПоток](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
