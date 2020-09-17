---
title: Класс CComObjectGlobal
ms.date: 11/04/2016
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
ms.openlocfilehash: 9a784584179186cdf1e63c1ec43cad4d59391ec3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327625"
---
# <a name="ccomobjectglobal-class"></a>Класс CComObjectGlobal

Этот класс управляет подсчетом ссылок `Base` на модуль, содержащий объект.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComObjectGlobal : public Base
```

#### <a name="parameters"></a>Параметры

*Базы*<br/>
Ваш класс, полученный из [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx,](../../atl/reference/ccomobjectrootex-class.md)а также из любого другого интерфейса, который вы хотите поддерживать на объекте.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|Конструктор.|
|[CComObjectGlobal:::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComObjectGlobal:AddRef](#addref)|Реализует глобальную. `AddRef`|
|[CComObjectGlobal::QueryInterface](#queryinterface)|Реализует глобальную. `QueryInterface`|
|[CComObjectGlobal::Release](#release)|Реализует глобальную. `Release`|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|Содержит HRESULT, возвращенный `CComObjectGlobal` во время строительства объекта.|

## <a name="remarks"></a>Примечания

`CComObjectGlobal`управляет подсчетом ссылок на `Base` модуль, содержащий объект. `CComObjectGlobal`гарантирует, что ваш объект не будет удален до тех пор, пока модуль не будет выпущен. Объект будет удален только тогда, когда подсчет ссылок на весь модуль достигнет нуля.

Например, `CComObjectGlobal`использование фабрики класса может содержать общий глобальный объект, который является общим для всех своих клиентов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComObjectGlobal`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomobjectglobaladdref"></a><a name="addref"></a>CComObjectGlobal:AddRef

Приращения эталонного количества объекта по 1.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики и тестирования.

### <a name="remarks"></a>Примечания

По умолчанию, `AddRef` звонки `_Module::Lock`, где `_Module` глобальный экземпляр [CComModule](../../atl/reference/ccommodule-class.md) или класс, полученный от него.

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="ccomobjectglobal"></a>CComObjectGlobal::CComObjectGlobal

Конструктор. Звонки, `FinalConstruct` а затем `HRESULT` устанавливает `FinalConstruct` [m_hResFinalConstruct](#m_hresfinalconstruct) к возвращенному .

```
CComObjectGlobal(void* = NULL));
```

### <a name="remarks"></a>Примечания

Если вы не получили свой базовый класс от [CComObjectRoot,](../../atl/reference/ccomobjectroot-class.md)вы должны предоставить свой собственный `FinalConstruct` метод. Деструктор вызывает `FinalRelease`.

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="dtor"></a>CComObjectGlobal:::

Деструктор

```
CComObjectGlobal();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы и вызывает [FinalRelease](ccomobjectrootex-class.md#finalrelease).

## <a name="ccomobjectglobalm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a>CComObjectGlobal::m_hResFinalConstruct

Содержит HRESULT от `FinalConstruct` вызова во `CComObjectGlobal` время строительства объекта.

```
HRESULT m_hResFinalConstruct;
```

## <a name="ccomobjectglobalqueryinterface"></a><a name="queryinterface"></a>CComObjectGlobal::QueryInterface

Извлекает указатель на запрашиваемый указатель интерфейса.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID запрашиваемого интерфейса.

*ppvObject*<br/>
(ваут) Указатель на указатель интерфейса, идентифицированный iid, или NULL, если интерфейс не найден.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`QueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM.

## <a name="ccomobjectglobalrelease"></a><a name="release"></a>CComObjectGlobal::Release

Декретирует количество ссылок объекта на 1.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В сборках отладки возвращается значение, `Release` которое может быть полезно для диагностики и тестирования. В неотлибуговых `Release` сборках всегда возвращается 0.

### <a name="remarks"></a>Примечания

По умолчанию, `Release` звонки `_Module::Unlock`, где `_Module` глобальный экземпляр [CComModule](../../atl/reference/ccommodule-class.md) или класс, полученный от него.

## <a name="see-also"></a>См. также раздел

[Класс CComObjectStack](../../atl/reference/ccomobjectstack-class.md)<br/>
[Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Класс CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
