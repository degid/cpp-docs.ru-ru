---
title: IDispEventSimpleImpl класс
ms.date: 11/04/2016
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
ms.openlocfilehash: 779e143094760c7bd868ad33f590f7fd8f004762
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329738"
---
# <a name="idispeventsimpleimpl-class"></a>IDispEventSimpleImpl класс

Этот класс обеспечивает реализацию `IDispatch` методов, не получая информацию о типе из библиотеки типов.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <UINT nID, class T, const IID* pdiid>
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```

#### <a name="parameters"></a>Параметры

*nID*<br/>
Уникальный идентификатор для исходного объекта. Когда `IDispEventSimpleImpl` базовый класс для композитного элемента управления, используйте идентификатор ресурсов желаемого содержащегося элемента управления для этого параметра. В других случаях используйте произвольный положительный штат.

*T*<br/>
Класс пользователя, который является производным от `IDispEventSimpleImpl`.

*pdiid*<br/>
Указатель на IID-интерфейс события, реализованный этим классом.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IDispEventSimpleImpl::Консультация](#advise)|Устанавливает соединение с источником события по умолчанию.|
|[IDispEventSimpleImpl::DispEventAdvise](#dispeventadvise)|Устанавливает связь с источником события.|
|[IDispEventSimpleImpl: :DispEventUnadvise](#dispeventunadvise)|Прерывает соединение с источником событий.|
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|Возвращает E_NOTIMPL.|
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|Возвращает E_NOTIMPL.|
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|Возвращает E_NOTIMPL.|
|[IDispEventSimpleImpl::Invoke](#invoke)|Вызывает обработчиков событий, перечисленных на карте раковины события.|
|[IDispEventSimpleImpl::Unadvise](#unadvise)|Перерывы соединения с источником события по умолчанию.|

## <a name="remarks"></a>Примечания

`IDispEventSimpleImpl`предоставляет способ реализации дисинтерфейса событий, не требуя от вас предоставления кода реализации для каждого метода/события на этом интерфейсе. `IDispEventSimpleImpl`обеспечивает реализацию методов. `IDispatch` Вам нужно только предоставить реализации для событий, которые вы заинтересованы в обработке.

`IDispEventSimpleImpl`работает в сочетании с картой раковины событий в вашем классе, чтобы направить события к соответствующей функции обработчика. Для использования этого класса:

- Добавьте [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) макрос а также к карте раковины событий для каждого события на каждом объекте, с которым вы хотите справиться.

- Информация о типе предложения для каждого события, передавая указатель [на _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) структуру в качестве параметра для каждой записи. На платформе x86 `_ATL_FUNC_INFO.cc` значение должно быть CC_CDECL с помощью функции вызова вызова обратного вызова __stdcall.

- Позвоните [DispEventAdvise,](#dispeventadvise) чтобы установить связь между исходным объектом и базовым классом.

- Позвоните [DispEventUnadvise,](#dispeventunadvise) чтобы разорвать соединение.

Вы должны `IDispEventSimpleImpl` извлечь из (используя уникальное значение для *nID)* для каждого объекта, для которого вам нужно обрабатывать события. Можно повторно использовать базовый класс, не советуя с одним исходным объектом, а затем консультировать против другого исходного объекта, `IDispEventSimpleImpl` но максимальное количество исходных объектов, которые могут обрабатываться одним объектом одновременно, ограничено количеством базовых классов.

`IDispEventSimplImpl`обеспечивает ту же функциональность, [что и IDispEventImpl,](../../atl/reference/idispeventimpl-class.md)за исключением того, что он не получает тип информации об интерфейсе из библиотеки типов. Мастера генерируют код только `IDispEventImpl`на основе, `IDispEventSimpleImpl` но вы можете использовать, добавляя код вручную. Используйте, `IDispEventSimpleImpl` когда у вас нет библиотеки типов, описывающей интерфейс события, или вы хотите избежать накладных расходов, связанных с использованием библиотеки типов.

> [!NOTE]
> `IDispEventImpl`и `IDispEventSimpleImpl` обеспечить свою `IUnknown::QueryInterface` собственную реализацию, позволяющую каждому `IDispEventImpl` или `IDispEventSimpleImpl` базовому классу выступать в качестве отдельного удостоверения COM, обеспечивая при этом прямой доступ к членам класса в вашем основном объекте COM.

Ce ATL реализация sinks событий ActiveX поддерживает только значения возврата типа HRESULT или недействительными из ваших методов обработчика событий; любое другое значение возврата не поддерживается, и его поведение не определено.

Для получения дополнительной [информации см.](../../atl/supporting-idispeventimpl.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_IDispEvent`

`_IDispEventLocator`

`IDispEventSimpleImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="idispeventsimpleimpladvise"></a><a name="advise"></a>IDispEventSimpleImpl::Консультация

Вызовите этот метод, чтобы установить соединение с источником событий, представленным *pUnk.*

```
HRESULT Advise(IUnknown* pUnk);
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
(в) Указатель на `IUnknown` интерфейс объекта источника события.

### <a name="return-value"></a>Возвращаемое значение

S_OK или любой сбой HRESULT значение.

### <a name="remarks"></a>Примечания

Как только соединение установлено, события, выпущенные из *pUnk,* будут направляться обработчикам в вашем классе по карте раковины событий.

> [!NOTE]
> Если ваш класс происходит `IDispEventSimpleImpl` от нескольких классов, вам нужно будет отнести вызовы к этому методу, обрасывая вызов с определенным базовым классом, который вас интересует.

`Advise`устанавливает соединение с источником события по умолчанию, он получает IID источника события по умолчанию объекта, определяемого [AtlGetObjectSourceInterface.](composite-control-global-functions.md#atlgetobjectsourceinterface)

## <a name="idispeventsimpleimpldispeventadvise"></a><a name="dispeventadvise"></a>IDispEventSimpleImpl::DispEventAdvise

Вызовите этот метод, чтобы установить соединение с источником событий, представленным *pUnk.*

```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
(в) Указатель на `IUnknown` интерфейс объекта источника события.

*пиид*<br/>
Указатель на IID объекта источника событий.

### <a name="return-value"></a>Возвращаемое значение

S_OK или любой сбой HRESULT значение.

### <a name="remarks"></a>Примечания

Впоследствии события, выпущенные из *pUnk,* будут направляться обработчикам в вашем классе по карте раковины событий.

> [!NOTE]
> Если ваш класс происходит `IDispEventSimpleImpl` от нескольких классов, вам нужно будет отнести вызовы к этому методу, обрасывая вызов с определенным базовым классом, который вас интересует.

`DispEventAdvise`устанавливает связь с источником события, `pdiid`указанным в .

## <a name="idispeventsimpleimpldispeventunadvise"></a><a name="dispeventunadvise"></a>IDispEventSimpleImpl: :DispEventUnadvise

Разрывает соединение с исходным ресурсом события, представленным *pUnk.*

```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
(в) Указатель на `IUnknown` интерфейс объекта источника события.

*пиид*<br/>
Указатель на IID объекта источника событий.

### <a name="return-value"></a>Возвращаемое значение

S_OK или любой сбой HRESULT значение.

### <a name="remarks"></a>Примечания

После того, как соединение будет прервано, события больше не будут направляться к функциям обработчика, перечисленным на карте раковины событий.

> [!NOTE]
> Если ваш класс происходит `IDispEventSimpleImpl` от нескольких классов, вам нужно будет отнести вызовы к этому методу, обрасывая вызов с определенным базовым классом, который вас интересует.

`DispEventAdvise`прерывает соединение, которое было установлено с источником события, указанным в `pdiid`.

## <a name="idispeventsimpleimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventSimpleImpl::GetIDsOfNames

Это осуществление `IDispatch::GetIDsOfNames` возвратов E_NOTIMPL.

```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```

### <a name="remarks"></a>Примечания

Смотрите [IDispatch::GetIDsOfNames](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) в Windows SDK.

## <a name="idispeventsimpleimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventSimpleImpl::GetTypeInfo

Это осуществление `IDispatch::GetTypeInfo` возвратов E_NOTIMPL.

```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```

### <a name="remarks"></a>Примечания

Смотрите [IDispatch::GetTypeInfo](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo) в Windows SDK.

## <a name="idispeventsimpleimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEventSimpleImpl::GetTypeInfoCount

Это осуществление `IDispatch::GetTypeInfoCount` возвратов E_NOTIMPL.

```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```

### <a name="remarks"></a>Примечания

Смотрите [IDispatch::GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) в Windows SDK.

## <a name="idispeventsimpleimplinvoke"></a><a name="invoke"></a>IDispEventSimpleImpl::Invoke

Эта реализация `IDispatch::Invoke` вызовов обработчивателей событий, перечисленных на карте раковины событий.

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```

### <a name="remarks"></a>Примечания

Смотрите [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke).

## <a name="idispeventsimpleimplunadvise"></a><a name="unadvise"></a>IDispEventSimpleImpl::Unadvise

Разрывает соединение с исходным ресурсом события, представленным *pUnk.*

```
HRESULT Unadvise(IUnknown* pUnk);
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
(в) Указатель на `IUnknown` интерфейс объекта источника события.

### <a name="return-value"></a>Возвращаемое значение

S_OK или любой сбой HRESULT значение.

### <a name="remarks"></a>Примечания

После того, как соединение будет прервано, события больше не будут направляться к функциям обработчика, перечисленным на карте раковины событий.

> [!NOTE]
> Если ваш класс происходит `IDispEventSimpleImpl` от нескольких классов, вам нужно будет отнести вызовы к этому методу, обрасывая вызов с определенным базовым классом, который вас интересует.

`Unadvise`прерывает соединение, которое было установлено `pdiid`с исходным течением события по умолчанию, указанным в .

`Unavise`прерывает соединение с источником события по умолчанию, он получает IID источника события по умолчанию объекта, определяемого [AtlGetObjectSourceInterface.](composite-control-global-functions.md#atlgetobjectsourceinterface)

## <a name="see-also"></a>См. также раздел

[структура _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl класс](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventImpl Класс](../../atl/reference/idispeventimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
