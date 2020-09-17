---
title: Класс CComPolyObject
ms.date: 11/04/2016
f1_keywords:
- CComPolyObject
- ATLCOM/ATL::CComPolyObject
- ATLCOM/ATL::CComPolyObject::CComPolyObject
- ATLCOM/ATL::CComPolyObject::AddRef
- ATLCOM/ATL::CComPolyObject::CreateInstance
- ATLCOM/ATL::CComPolyObject::FinalConstruct
- ATLCOM/ATL::CComPolyObject::FinalRelease
- ATLCOM/ATL::CComPolyObject::QueryInterface
- ATLCOM/ATL::CComPolyObject::Release
- ATLCOM/ATL::CComPolyObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
ms.openlocfilehash: c880d170a03196d0e15ea8741c786e560d90ddc4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747780"
---
# <a name="ccompolyobject-class"></a>Класс CComPolyObject

Этот класс `IUnknown` реализует сяордля для агрегированного или неагрегированного объекта.

## <a name="syntax"></a>Синтаксис

```
template<class contained>
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Параметры

*Содержащиеся*<br/>
Ваш класс, полученный из [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx,](../../atl/reference/ccomobjectrootex-class.md)а также из любых других интерфейсов, которые вы хотите поддерживать на объекте.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCompolyObject::CComPolyObject](#ccompolyobject)|Конструктор.|
|[CComPolyObject:::CComPolyObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComPolyObject:AddRef](#addref)|Приращения отсчета ссылки объекта.|
|[CComPolyObject::СозданиеInstance](#createinstance)|(Статик) Позволяет создать новый **cComPolyObject<** `contained` **>** объект без накладных расходов [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).|
|[CComPolyObject::FinalConstruct](#finalconstruct)|Выполняет окончательную инициализацию `m_contained`.|
|[CComPolyObject::FinalRelease](#finalrelease)|Выполняет окончательное `m_contained`уничтожение .|
|[CComPolyObject::QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[CComPolyObject::Release](#release)|Декретирует количество ссылок объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComPolyObject::m_contained](#m_contained)|Делегаты `IUnknown` звонят внешнему неизвестному, если `IUnknown` объект агрегирован, или к объекту, если объект не агрегирован.|

## <a name="remarks"></a>Примечания

`CComPolyObject`реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для агрегированного или неагрегированного объекта.

При создании `CComPolyObject` экземпляра проверяется значение внешнего неизвестного. Если он NULL, `IUnknown` реализуется для неагрегированного объекта. Если внешний неизвестный `IUnknown` не является NULL, реализуется для агрегированного объекта.

Преимущество использования `CComPolyObject` заключается в том, что вы избегаете как [CComAggObject,](../../atl/reference/ccomaggobject-class.md) так и [CComObject](../../atl/reference/ccomobject-class.md) в модуле для обработки агрегированных и неагрегированных случаев. Один `CComPolyObject` объект обрабатывает оба случая. Это означает, что в модуле существует только одна копия vtable и одна копия функций. Если ваш vtable большой, это может существенно уменьшить размер модуля. Однако, если ваш vtable `CComPolyObject` небольшой, использование может привести к несколько большему размеру модуля, `CComAggObject` `CComObject`потому что он не оптимизирован для агрегированного или неагрегированного объекта, как есть и .

Если DECLARE_POLY_AGGREGATABLE макрос указан в определении `CComPolyObject` класса объекта, будет использоваться для создания объекта. DECLARE_POLY_AGGREGATABLE будет автоматически объявлен, если вы используете ATL Project Wizard для создания полного управления или управления Internet Explorer.

Если агрегировать, `CComPolyObject` объект `IUnknown`имеет свой собственный, `IUnknown`отдельно от внешнего объекта, и поддерживает свой собственный счет ссылки. `CComPolyObject`использует [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) для делегирования внешнему неизвестному.

Для получения дополнительной информации об агрегации смотрите в статье [Основы объектов ATL COM](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccompolyobjectaddref"></a><a name="addref"></a>CComPolyObject:AddRef

Приращения, отсылки рассчитывают на объект.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

## <a name="ccompolyobjectccompolyobject"></a><a name="ccompolyobject"></a>CCompolyObject::CComPolyObject

Конструктор.

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
(в) Указатель на внешний неизвестный, если объект должен быть агрегирован, или NULL, если объект не агрегирован.

### <a name="remarks"></a>Примечания

Инициализирует `CComContainedObject`[элемент данных](#m_contained),m_containedиувеличиваетсчетчикблокировок модуля.

Декременты декретов модуля блокировки.

## <a name="ccompolyobjectccompolyobject"></a><a name="dtor"></a>CComPolyObject:::CComPolyObject

Деструктор

```
~CComPolyObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы, вызывает [FinalRelease](#finalrelease)и высчитывает количество блокировки модуля.

## <a name="ccompolyobjectcreateinstance"></a><a name="createinstance"></a>CComPolyObject::СозданиеInstance

Позволяет создать новый **cComPolyObject<** `contained` **>** объект без накладных расходов [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>Параметры

*Pp*<br/>
(ваут) Указатель на **указатель CComPolyObject<** `contained` **>** указателя. Если `CreateInstance` неудача, *pp* установлен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Возвращается объект имеет подсчет ссылок `AddRef` ноль, `Release` поэтому немедленно позвоните, а затем используйте для освобождения ссылки на указатель объекта, когда вы закончите.

Если вам не нужен прямой доступ к объекту, но все же `CoCreateInstance`хотите создать новый объект без накладных расходов, используйте [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) вместо этого.

## <a name="ccompolyobjectfinalconstruct"></a><a name="finalconstruct"></a>CComPolyObject::FinalConstruct

Этот метод, вызванный на заключительных этапах строительства объекта, выполняет любую окончательную инициализацию на [m_contained](#m_contained) члена данных.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccompolyobjectfinalrelease"></a><a name="finalrelease"></a>CComPolyObject::FinalRelease

Этот метод, [вызванный](#m_contained) во время уничтожения объектов, освобождает m_contained членов данных.

```cpp
void FinalRelease();
```

## <a name="ccompolyobjectm_contained"></a><a name="m_contained"></a>CComPolyObject::m_contained

Объект [CComContainedObject, полученный](../../atl/reference/ccomcontainedobject-class.md) из вашего класса.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Параметры

*Содержащиеся*<br/>
(в) Ваш класс, полученный из [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx,](../../atl/reference/ccomobjectrootex-class.md)а также из любых других интерфейсов, которые вы хотите поддерживать на объекте.

### <a name="remarks"></a>Примечания

`IUnknown`звонки `m_contained` делегируются внешнему неизвестному, если объект агрегирован, или к объекту, `IUnknown` если объект не агрегирован.

## <a name="ccompolyobjectqueryinterface"></a><a name="queryinterface"></a>CComPolyObject::QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT QueryInterface(Q** pp);
```

### <a name="parameters"></a>Параметры

*Q*<br/>
Интерфейс COM.

*Iid*<br/>
(в) Идентификатор запрашиваемого интерфейса.

*ppvObject*<br/>
(ваут) Указатель на указатель интерфейса, идентифицированный *iid.* Если объект не поддерживает этот интерфейс, *ppvObject* настроен на NULL.

*Pp*<br/>
(ваут) Указатель на интерфейс, `__uuidof(Q)`идентифицированный .

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Для агрегированного объекта, если `IUnknown`запрашиваемый интерфейс, `QueryInterface` возвращает указатель `IUnknown` к агрегированному объекту, и приравняет значение отсчета ссылки. В противном случае этот метод `CComContainedObject` запрашивает интерфейс через члена данных, [m_contained](#m_contained).

## <a name="ccompolyobjectrelease"></a><a name="release"></a>CComPolyObject::Release

Декретирует значение ссылки на объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В сборках отладок возвращается значение, `Release` которое может быть полезно для диагностики или тестирования. В недебаговых `Release` сборках всегда возвращается 0.

## <a name="see-also"></a>См. также раздел

[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
