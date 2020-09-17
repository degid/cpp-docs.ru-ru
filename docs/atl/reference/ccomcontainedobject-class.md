---
title: Класс CComContainedObject
ms.date: 11/04/2016
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
ms.openlocfilehash: 72ba27c3be6576621995ffb8c98995c6abc9324c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320786"
---
# <a name="ccomcontainedobject-class"></a>Класс CComContainedObject

Этот класс реализует [IUnknown,](/windows/win32/api/unknwn/nn-unknwn-iunknown) делегируя объекту `IUnknown`владельца.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>Параметры

*Базы*<br/>
Ваш класс, полученный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|Конструктор. Инициализирует указатель участника на `IUnknown`объект владельца.|
|[CComContainedObject::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComcontainedObject:AddRef](#addref)|Приращения, ссылка рассчитывает на объект владельца.|
|[CComContainedПредмет::GetControllingНеизвестный](#getcontrollingunknown)|Извлекает объект `IUnknown`владельца.|
|[CComContainedПредмет::QueryInterface](#queryinterface)|Извлекает указатель на запрашиваемый интерфейс на объекте владельца.|
|[CComContainedObject::Release](#release)|Декреты эталона рассчитывают на объект владельца.|

## <a name="remarks"></a>Примечания

ATL `CComContainedObject` использует в классах [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md), и [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject`реализует [IUnknown,](/windows/win32/api/unknwn/nn-unknwn-iunknown) делегируя объекту `IUnknown`владельца. (Владелец является либо внешним объектом агрегации, либо объектом, для которого создается интерфейс отрыва.) `CComContainedObject` звонки `CComObjectRootEx` `OuterQueryInterface`'s `OuterAddRef`, `OuterRelease`, и `Base`, все унаследованные через .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComContainedObject`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomcontainedobjectaddref"></a><a name="addref"></a>CComcontainedObject:AddRef

Приращения, ссылка рассчитывает на объект владельца.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="ccomcontainedobject"></a>CComContainedObject::CComContainedObject

Конструктор.

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
(в) Объект `IUnknown`владельца.

### <a name="remarks"></a>Примечания

Устанавливает `m_pOuterUnknown` указатель участника (наследуемый `Base` через класс) на *pv*.

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="dtor"></a>CComContainedObject::

Деструктор

```
~CComContainedObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

## <a name="ccomcontainedobjectgetcontrollingunknown"></a><a name="getcontrollingunknown"></a>CComContainedПредмет::GetControllingНеизвестный

Возвращает `m_pOuterUnknown` указатель участника (наследуемого через *базовый* класс), `IUnknown`который удерживает объект владельца.

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `IUnknown`владельца.

### <a name="remarks"></a>Примечания

Этот метод может `Base` быть виртуальным, если объявлен [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) макрос.

## <a name="ccomcontainedobjectqueryinterface"></a><a name="queryinterface"></a>CComContainedПредмет::QueryInterface

Извлекает указатель на запрашиваемый интерфейс на объекте владельца.

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

## <a name="ccomcontainedobjectrelease"></a><a name="release"></a>CComContainedObject::Release

Декреты эталона рассчитывают на объект владельца.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В сборках отладок возвращается значение, `Release` которое может быть полезно для диагностики или тестирования. В неотлибуговых `Release` сборках всегда возвращается 0.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
