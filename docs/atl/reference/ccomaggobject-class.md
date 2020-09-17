---
title: Класс CComAggObject
ms.date: 11/04/2016
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
ms.openlocfilehash: b9200c9c396fc16b6df3f4c2f4c66fb7976316d4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748165"
---
# <a name="ccomaggobject-class"></a>Класс CComAggObject

Этот класс реализует интерфейс [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для агрегированного объекта. По определению, агрегированный объект содержится внутри внешнего объекта. Класс `CComAggObject` похож на [класс CComObject,](../../atl/reference/ccomobject-class.md)за исключением того, что он предоставляет интерфейс, который непосредственно доступен для внешних клиентов.

## <a name="syntax"></a>Синтаксис

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Параметры

*Содержащиеся*<br/>
Ваш класс, полученный из [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx,](../../atl/reference/ccomobjectrootex-class.md)а также из любых других интерфейсов, которые вы хотите поддерживать на объекте.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComAggObject::CComAggObject](#ccomaggobject)|Конструктор.|
|[CComAggObject:::CComAggObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComAggObject:AddRef](#addref)|Приращения эталона рассчитывают на агрегированный объект.|
|[CComAggObject::Создание](#createinstance)|Эта статическая функция позволяет создавать новый **CComAggObject<** `contained` **>** объект без накладных расходов [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).|
|[CComAggObject::FinalConstruct](#finalconstruct)|Выполняет окончательную инициализацию `m_contained`.|
|[CComAggObject::FinalRelease](#finalrelease)|Выполняет окончательное `m_contained`уничтожение .|
|[CComAggObject::QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[CComAggObject:Release](#release)|Декреты эталона рассчитывают на агрегированный объект.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComAggObject::m_contained](#m_contained)|Делегаты `IUnknown` звонят к внешнему неизвестному.|

## <a name="remarks"></a>Примечания

`CComAggObject`реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для агрегированного объекта. `CComAggObject`имеет свой `IUnknown` собственный интерфейс, отдельно `IUnknown` от интерфейса внешнего объекта, и поддерживает свой собственный подсчет ссылок.

Для получения дополнительной информации об агрегации смотрите в статье [Основы объектов ATL COM](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomaggobjectaddref"></a><a name="addref"></a>CComAggObject:AddRef

Приращения эталона рассчитывают на агрегированный объект.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

## <a name="ccomaggobjectccomaggobject"></a><a name="ccomaggobject"></a>CComAggObject::CComAggObject

Конструктор.

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
(в) Внешнее неизвестное.

### <a name="remarks"></a>Примечания

Инициализирует элемент `CComContainedObject`[m_contained](#m_contained) и увеличивает счетчик блокировок модуля.

Декременты декретов модуля блокировки.

## <a name="ccomaggobjectccomaggobject"></a><a name="dtor"></a>CComAggObject:::CComAggObject

Деструктор

```
~CComAggObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы, вызывает [FinalRelease](#finalrelease)и высчитывает количество блокировки модуля.

## <a name="ccomaggobjectcreateinstance"></a><a name="createinstance"></a>CComAggObject::Создание

Эта статическая функция позволяет создавать новый **CComAggObject<** `contained` **>** объект без накладных расходов [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>Параметры

*Pp*<br/>
(ваут) Указатель на **CComAggObject\<**<em>содержал</em> **>** указатель. Если `CreateInstance` неудача, *pp* установлен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Возвращается объект имеет подсчет ссылок `AddRef` ноль, `Release` поэтому немедленно позвоните, а затем используйте для освобождения ссылки на указатель объекта, когда вы закончите.

Если вам не нужен прямой доступ к объекту, но все `CoCreateInstance`же хотите создать новый объект без накладных расходов, используйте [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) вместо этого.

## <a name="ccomaggobjectfinalconstruct"></a><a name="finalconstruct"></a>CComAggObject::FinalConstruct

Этот метод, вызванный на заключительных этапах строительства объекта, выполняет любую окончательную инициализацию на [m_contained](#m_contained) члене.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccomaggobjectfinalrelease"></a><a name="finalrelease"></a>CComAggObject::FinalRelease

Вызывается во время уничтожения объекта, этот метод освобождает [m_contained](#m_contained) члена.

```cpp
void FinalRelease();
```

## <a name="ccomaggobjectm_contained"></a><a name="m_contained"></a>CComAggObject::m_contained

Объект [CComContainedObject, полученный](../../atl/reference/ccomcontainedobject-class.md) из вашего класса.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Параметры

*Содержащиеся*<br/>
(в) Ваш класс, полученный из [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx,](../../atl/reference/ccomobjectrootex-class.md)а также из любых других интерфейсов, которые вы хотите поддерживать на объекте.

### <a name="remarks"></a>Примечания

Все `IUnknown` вызовы через `m_contained` делегируются внешнему неизвестному.

## <a name="ccomaggobjectqueryinterface"></a><a name="queryinterface"></a>CComAggObject::QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) Идентификатор запрашиваемого интерфейса.

*ppvObject*<br/>
(ваут) Указатель на указатель интерфейса, идентифицированный *iid.* Если объект не поддерживает этот интерфейс, *ppvObject* настроен на NULL.

*Pp*<br/>
(ваут) Указатель на указатель интерфейса, `Q`идентифицированный по типу. Если объект не поддерживает этот интерфейс, *pp* настроен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если запрашиваемый `IUnknown` `QueryInterface` интерфейс, возвращает указатель на собственный `IUnknown` агрегированный объект и приращает значение отсчета ссылок. В противном случае этот метод `CComContainedObject` запрашивает интерфейс через члена, [m_contained](#m_contained).

## <a name="ccomaggobjectrelease"></a><a name="release"></a>CComAggObject:Release

Декреты эталона рассчитывают на агрегированный объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В сборках отладок возвращается значение, `Release` которое может быть полезно для диагностики или тестирования. В неотлибуговых `Release` сборках всегда возвращается 0.

## <a name="see-also"></a>См. также раздел

[Класс CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
