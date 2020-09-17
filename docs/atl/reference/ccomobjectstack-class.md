---
title: Класс CComObjectStack
ms.date: 11/04/2016
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
ms.openlocfilehash: 8c3fd56635da8b80c84f6151009586b7bd2b4341
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327578"
---
# <a name="ccomobjectstack-class"></a>Класс CComObjectStack

Этот класс создает временный объект COM и обеспечивает его `IUnknown`скелетной реализацией .

## <a name="syntax"></a>Синтаксис

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>Параметры

*Базы*<br/>
Ваш класс, полученный из [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx,](../../atl/reference/ccomobjectrootex-class.md)а также из любого другого интерфейса, который вы хотите поддерживать на объекте.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComObjectStack::CComObjectstack](#ccomobjectstack)|Конструктор.|
|[CComObjectStack:::CComObjectstack](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComObjectstack:AddRef](#addref)|Возвращает ноль. В режиме отладки, вызовы `_ASSERTE`.|
|[CComObjectStack::QueryInterface](#queryinterface)|Возвращает E_NOINTERFACE. В режиме отладки, вызовы `_ASSERTE`.|
|[CComObjectStack::Release](#release)|Возвращает ноль. В режиме отладки, вызовы `_ASSERTE`. ~|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|Содержит HRESULT, возвращенный `CComObjectStack` во время строительства объекта.|

## <a name="remarks"></a>Примечания

`CComObjectStack`используется для создания временного объекта COM и обеспечения объекта `IUnknown`скелетной реализации. Как правило, объект используется в качестве локальной переменной в пределах одной функции (т.е. нажата на стек). Поскольку объект разрушается по окончании функции, подсчет ссылок не выполняется для повышения эффективности.

Ниже приводится следующий пример, как создать объект COM, используемый внутри функции:

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

Временный `Tempobj` объект нажат на стек и автоматически исчезает по окончании функции.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComObjectStack`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomobjectstackaddref"></a><a name="addref"></a>CComObjectstack:AddRef

Возвращает ноль.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ноль.

### <a name="remarks"></a>Примечания

В режиме отладки, вызовы `_ASSERTE`.

## <a name="ccomobjectstackccomobjectstack"></a><a name="ccomobjectstack"></a>CComObjectStack::CComObjectstack

Конструктор.

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>Примечания

Вызовы, `FinalConstruct` а затем устанавливает [m_hResFinalConstruct](#m_hresfinalconstruct) на HRESULT вернулся `FinalConstruct`. Если вы не получили свой базовый класс от [CComObjectRoot,](../../atl/reference/ccomobjectroot-class.md)вы должны предоставить свой собственный `FinalConstruct` метод. Деструктор вызывает `FinalRelease`.

## <a name="ccomobjectstackccomobjectstack"></a><a name="dtor"></a>CComObjectStack:::CComObjectstack

Деструктор

```
CComObjectStack();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы и вызывает [FinalRelease](ccomobjectrootex-class.md#finalrelease).

## <a name="ccomobjectstackm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a>CComObjectStack::m_hResFinalConstruct

Содержит HRESULT вернулся `FinalConstruct` из вызова `CComObjectStack` во время строительства объекта.

```
HRESULT    m_hResFinalConstruct;
```

## <a name="ccomobjectstackqueryinterface"></a><a name="queryinterface"></a>CComObjectStack::QueryInterface

Возвращает E_NOINTERFACE.

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOINTERFACE.

### <a name="remarks"></a>Примечания

В режиме отладки, вызовы `_ASSERTE`.

## <a name="ccomobjectstackrelease"></a><a name="release"></a>CComObjectStack::Release

Возвращает ноль.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ноль.

### <a name="remarks"></a>Примечания

В режиме отладки, вызовы `_ASSERTE`.

## <a name="see-also"></a>См. также раздел

[Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Класс CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Класс CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
