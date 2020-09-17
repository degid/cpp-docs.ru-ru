---
title: IDispEventImpl Класс
ms.date: 11/04/2016
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
ms.openlocfilehash: fa6e9f972accd0115d9f1e3248bd97ddde0c3c63
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329759"
---
# <a name="idispeventimpl-class"></a>IDispEventImpl Класс

Этот класс обеспечивает реализацию `IDispatch` методов.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0,
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```

#### <a name="parameters"></a>Параметры

*nID*<br/>
Уникальный идентификатор для исходного объекта. Когда `IDispEventImpl` базовый класс для композитного элемента управления, используйте идентификатор ресурсов желаемого содержащегося элемента управления для этого параметра. В других случаях используйте произвольный положительный штат.

*T*<br/>
Класс пользователя, который является производным от `IDispEventImpl`.

*pdiid*<br/>
Указатель на IID-интерфейс события, реализованный этим классом. Этот интерфейс должен быть определен в библиотеке типа, обозначаемой *plibid,* *wMajor*и *wMinor.*

*плибид*<br/>
Указатель на библиотеку типов, определяющую интерфейс диспетчерской связи, на который указывает *pdiid.* Если **&GUID_NULL,** библиотека типов будет загружена из объекта, высужаемого событиями.

*wMajor*<br/>
Основной номер версии для библиотеки типов. Значение по умолчанию — 0.

*wMinor*<br/>
Дополнительный номер версии для библиотеки типов. Значение по умолчанию — 0.

*tihclass*<br/>
Класс используется для управления информацией типа для *T.* Значение по умолчанию — `CComTypeInfoHolder`это класс типа; однако, вы можете переопределить этот параметр шаблона, предоставив класс типа, кроме `CComTypeInfoHolder`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|Класс используется для управления информацией типа. По умолчанию — `CComTypeInfoHolder`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|Находит индекс функции для указанного идентификатора диспетчера.|
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|Карты одного члена и факультативного набора имен аргументов в соответствующий набор множество DISPIDs.|
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Извлекает информацию о типе объекта.|
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Извлекает количество типовых информационных интерфейсов.|
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|Извлекает базовый тип пользовательского типа.|

## <a name="remarks"></a>Примечания

`IDispEventImpl`предоставляет способ реализации дисинтерфейса событий, не требуя от вас предоставления кода реализации для каждого метода/события на этом интерфейсе. `IDispEventImpl`обеспечивает реализацию методов. `IDispatch` Вам нужно только предоставить реализации для событий, которые вы заинтересованы в обработке.

`IDispEventImpl`работает в сочетании с картой раковины событий в вашем классе, чтобы направить события к соответствующей функции обработчика. Для использования этого класса:

Добавьте [SINK_ENTRY](composite-control-macros.md#sink_entry) или [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) макрос атакжем ес карту раковины события для каждого события на каждом объекте, с которым вы хотите справиться. При `IDispEventImpl` использовании в качестве базового класса композитного элемента управления можно позвонить [в AtlAdviseSinkMap,](connection-point-global-functions.md#atladvisesinkmap) чтобы установить и разорвать связь с источниками событий для всех записей на карте раковины события. В других случаях, или для усиления контроля, вызов [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) для установления связи между исходным объектом и базовым классом. Позвоните [DispEventUnadvise,](idispeventsimpleimpl-class.md#dispeventunadvise) чтобы разорвать соединение.

Вы должны `IDispEventImpl` извлечь из (используя уникальное значение для *nID)* для каждого объекта, для которого вам нужно обрабатывать события. Можно повторно использовать базовый класс, не советуя с одним исходным объектом, а затем консультировать против другого исходного объекта, `IDispEventImpl` но максимальное количество исходных объектов, которые могут обрабатываться одним объектом одновременно, ограничено количеством базовых классов.

`IDispEventImpl`обеспечивает ту же функциональность, [что и IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), за исключением того, что он получает тип информации о интерфейсе из библиотеки типов, а не поставляются в качестве указателя на [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) структуру. Используйте, `IDispEventSimpleImpl` когда у вас нет библиотеки типов, описывающей интерфейс события, или вы хотите избежать накладных расходов, связанных с использованием библиотеки типов.

> [!NOTE]
> `IDispEventImpl`и `IDispEventSimpleImpl` обеспечить свою `IUnknown::QueryInterface` собственную реализацию, позволяющую каждому `IDispEventImpl` и `IDispEventSimpleImpl` базовому классу действовать в качестве отдельного удостоверения COM, обеспечивая при этом прямой доступ к членам класса в вашем основном объекте COM.

Ce ATL реализация sinks событий ActiveX поддерживает только значения возврата типа HRESULT или недействительными из ваших методов обработчика событий; любое другое значение возврата не поддерживается, и его поведение не определено.

Для получения дополнительной [информации см.](../../atl/supporting-idispeventimpl.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_IDispEvent`

`_IDispEventLocator`

[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="idispeventimplgetfuncinfofromid"></a><a name="getfuncinfofromid"></a>IDispEventImpl::GetFuncInfoFromId

Находит индекс функции для указанного идентификатора диспетчера.

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) Ссылка на идентификатор функции.

*dispidMember*<br/>
(в) Идентификатор диспетчерской функции.

*lcid*<br/>
(в) Контекст локализации идентификатора функции.

*info*<br/>
(в) Структура, указывающая, как вызывается функция.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="idispeventimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventImpl::GetIDsOfNames

Карты одного члена и дополнительный набор имен аргументов к соответствующему набору множество DISPIDs, которые могут быть использованы при последующих вызовах [на IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke).

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>Примечания

Смотрите [IDispatch::GetIDsOfNames](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) в Windows SDK.

## <a name="idispeventimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventImpl::GetTypeInfo

Возвращает сведения о типе объекта, которые затем могут использоваться для получения сведений о типе интерфейса.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Примечания

## <a name="idispeventimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEventImpl::GetTypeInfoCount

Возвращает количество предоставляемых объектом интерфейсов для доступа к сведениям о типе (0 или 1).

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Примечания

Смотрите [IDispatch::GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) в Windows SDK.

## <a name="idispeventimplgetuserdefinedtype"></a><a name="getuserdefinedtype"></a>IDispEventImpl::GetUserDefinedType

Извлекает базовый тип пользовательского типа.

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>Параметры

*Pti*<br/>
(в) Указатель на интерфейс [ITypeInfo,](/windows/win32/api/oaidl/nn-oaidl-itypeinfo) содержащий пользовательский тип.

*Згт*<br/>
(в) Ручка к описанию типа, который необходимо извлечь.

### <a name="return-value"></a>Возвращаемое значение

Тип варианта.

### <a name="remarks"></a>Примечания

Смотрите [ITypeInfo::GetRefTypeInfo](/windows/win32/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo).

## <a name="idispeventimplidispeventimpl"></a><a name="idispeventimpl"></a>IDispEventImpl::IDispEventImpl

Конструктор. Хранит значения параметров шаблона класса *plibid,* *pdiid,* *wMajor*и *wMinor.*

```
IDispEventImpl();
```

## <a name="idispeventimpltihclass"></a><a name="tihclass"></a>IDispEventImpl::tihclass

Этот typedef является экземпляром параметра *tihclass*шаблона класса.

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>Примечания

По умолчанию класс `CComTypeInfoHolder`. `CComTypeInfoHolder`управляет информацией типа для класса.

## <a name="see-also"></a>См. также раздел

[структура _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl класс](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventSimpleImpl класс](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
