---
title: Класс CComObjectNoLock
ms.date: 11/04/2016
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
ms.openlocfilehash: c190f495e284e98b27a6c6dc2099a8dfc4b1693d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327617"
---
# <a name="ccomobjectnolock-class"></a>Класс CComObjectNoLock

Этот класс `IUnknown` реализует для неагрегированного объекта, но не приращает количество блокировки модуля в конструкторе.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>Параметры

*Базы*<br/>
Ваш класс, полученный из [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx,](../../atl/reference/ccomobjectrootex-class.md)а также из любого другого интерфейса, который вы хотите поддерживать на объекте.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|Конструктор.|
|[CComObjectNoLock:::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComObjectNoLock::AddRef](#addref)|Приращения, отсылки рассчитывают на объект.|
|[CComObjectNoLock::QueryInterface](#queryinterface)|Возвращает указатель на запрашиваемый интерфейс.|
|[CComObjectNoLock::Release](#release)|Декретирует значение ссылки на объект.|

## <a name="remarks"></a>Примечания

`CComObjectNoLock`похож на [CComObject](../../atl/reference/ccomobject-class.md) в том, что он реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для неагрегированного объекта; однако, `CComObjectNoLock` не приравня количество блокировки модуля в конструкторе.

ATL `CComObjectNoLock` использует внутренне для заводов класса. В общем, вы не будете использовать этот класс напрямую.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomobjectnolockaddref"></a><a name="addref"></a>CComObjectNoLock::AddRef

Приращения, отсылки рассчитывают на объект.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

## <a name="ccomobjectnolockccomobjectnolock"></a><a name="ccomobjectnolock"></a>CComObjectNoLock::CComObjectNoLock

Конструктор. В отличие от [CComObject](../../atl/reference/ccomobject-class.md), не приращает количество блокировки модуля.

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>Параметры

<em>void\*</em><br/>
(в) Этот неназванный параметр не используется. Она существует для симметрии с другими `CComXXXObjectXXX` конструкторами.

## <a name="ccomobjectnolockccomobjectnolock"></a><a name="dtor"></a>CComObjectNoLock:::

Деструктор

```
~CComObjectNoLock();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы и вызывает [FinalRelease](ccomobjectrootex-class.md#finalrelease).

## <a name="ccomobjectnolockqueryinterface"></a><a name="queryinterface"></a>CComObjectNoLock::QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) Идентификатор запрашиваемого интерфейса.

*ppvObject*<br/>
(ваут) Указатель на указатель интерфейса, идентифицированный *iid.* Если объект не поддерживает этот интерфейс, *ppvObject* настроен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccomobjectnolockrelease"></a><a name="release"></a>CComObjectNoLock::Release

Декретирует значение ссылки на объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В сборках отладок возвращается значение, `Release` которое может быть полезно для диагностики или тестирования. В неотлибуговых `Release` сборках всегда возвращается 0.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
