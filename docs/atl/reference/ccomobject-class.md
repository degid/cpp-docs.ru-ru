---
title: Класс CComObject
ms.date: 11/04/2016
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
ms.openlocfilehash: 81246ad8bd6281d0b7578932cd431609a1ec4ac5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224257"
---
# <a name="ccomobject-class"></a>Класс CComObject

Этот класс реализует `IUnknown` для неагрегированного объекта.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComObject : public Base
```

#### <a name="parameters"></a>Параметры

*Из*<br/>
Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любых других интерфейсов, которые требуется поддерживать для объекта.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComObject:: CComObject](#ccomobject)|Конструктор.|
|[CComObject:: ~ CComObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComObject:: AddRef](#addref)|Увеличивает значение счетчика ссылок на объект.|
|[CComObject:: CreateInstance](#createinstance)|Статически Создает новый `CComObject` объект.|
|[CComObject:: QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[CComObject:: Release](#release)|Уменьшает значение счетчика ссылок на объект.|

## <a name="remarks"></a>Примечания

`CComObject`реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для неагрегированного объекта. Однако вызовы `QueryInterface` , `AddRef` и `Release` делегируются в `CComObjectRootEx` .

Дополнительные сведения об использовании см `CComObject` . в статье [основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComObject`

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="ccomobjectaddref"></a><a name="addref"></a>CComObject:: AddRef

Увеличивает значение счетчика ссылок на объект.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает новый инкрементный счетчик ссылок на объект. Это значение может быть полезно для диагностики или тестирования.

## <a name="ccomobjectccomobject"></a><a name="ccomobject"></a>CComObject:: CComObject

Конструктор увеличивает число блокировок модуля.

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>Параметры

<em>void\*</em><br/>
окне Этот неименованный параметр не используется. Он существует для симметрии с другими `CComXXXObjectXXX` конструкторами.

### <a name="remarks"></a>Примечания

Деструктор уменьшает его.

Если `CComObject` объект, производный от, успешно создан с помощью **`new`** оператора, начальное значение счетчика ссылок равно 0. Чтобы задать для счетчика ссылок правильное значение (1), выполните вызов функции [AddRef](#addref) .

## <a name="ccomobjectccomobject"></a><a name="dtor"></a>CComObject:: ~ CComObject

Деструктор

```
CComObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы, вызывает [финалрелеасе](ccomobjectrootex-class.md#finalrelease)и уменьшает число блокировок модуля.

## <a name="ccomobjectcreateinstance"></a><a name="createinstance"></a>CComObject:: CreateInstance

Эта статическая функция позволяет создать новый объект **<CComObject** `Base` **>** без дополнительной нагрузки на [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>Параметры

*PP*<br/>
заполняет Указатель на указатель **<CComObject** `Base` **>** . Если `CreateInstance` операция завершилась неудачно, *PP* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Возвращаемый объект имеет нулевое значение счетчика ссылок, поэтому вызовите `AddRef` его немедленно, а затем используйте `Release` для освобождения ссылки на указатель объекта по завершении.

Если прямой доступ к объекту не требуется, но по-прежнему требуется создать новый объект без дополнительной нагрузки `CoCreateInstance` , используйте [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

## <a name="ccomobjectqueryinterface"></a><a name="queryinterface"></a>CComObject:: QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор запрашиваемого интерфейса.

*ппвобжект*<br/>
заполняет Указатель на указатель интерфейса, идентифицируемый по *IID*. Если объект не поддерживает этот интерфейс, *ппвобжект* имеет значение null.

*PP*<br/>
заполняет Указатель на указатель интерфейса, идентифицируемый по типу `Q` . Если объект не поддерживает этот интерфейс, *PP* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccomobjectrelease"></a><a name="release"></a>CComObject:: Release

Уменьшает значение счетчика ссылок на объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает новый уменьшенный счетчик ссылок на объект. В отладочных сборках возвращаемое значение может быть полезным для диагностики или тестирования. В сборках, не относящихся к отладке, `Release` всегда возвращает 0.

## <a name="see-also"></a>См. также статью

[Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
