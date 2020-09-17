---
title: IDispatchImpl класс
ms.date: 11/04/2016
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
ms.openlocfilehash: 3b3899a0c4a49aa7fb1bd82af330f5f1cc7329c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329796"
---
# <a name="idispatchimpl-class"></a>IDispatchImpl класс

Обеспечивает реализацию по `IDispatch` умолчанию для части двойного интерфейса.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T,
        const IID* piid= &__uuidof(T),
        const GUID* plibid = &CAtlModule::m_libid,
        WORD wMajor = 1,
        WORD wMinor = 0,
        class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IDispatchImpl : public T
```

#### <a name="parameters"></a>Параметры

*T*<br/>
(в) Двойной интерфейс.

*пиид*<br/>
(в) Указатель на IID *T*.

*плибид*<br/>
(в) Указатель на LIBID библиотеки типов, содержащей информацию об интерфейсе. По умолчанию библиотека типа сервера передается.

*wMajor*<br/>
(в) Основная версия библиотеки типов. По умолчанию значение 1.

*wMinor*<br/>
(в) Незначительная версия библиотеки типов. По умолчанию значение составляет 0.

*tihclass*<br/>
(в) Класс используется для управления информацией типа для *T.* По умолчанию значение `CComTypeInfoHolder`находится .

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|Конструктор. Вызовы `AddRef` на защищенную переменную члена, которая управляет информацией типа для двойного интерфейса. Деструктор вызывает `Release`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|Сопоставляет набор имен соответствующему набору идентификаторов диспетчеризации.|
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|Извлекает информацию о типе для двойного интерфейса.|
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|Определяет, есть ли информация типа, доступная для двойного интерфейса.|
|[IDispatchImpl::Invoke](#invoke)|Обеспечивает доступ к методам и свойствам, подверженным двойному интерфейсу.|

## <a name="remarks"></a>Примечания

`IDispatchImpl`обеспечивает реализацию по `IDispatch` умолчанию для части любого двойного интерфейса на объекте. Двойной интерфейс происходит `IDispatch` от и использует только типы, совместимые с автоматизацией. Как и dispinterface, двойной интерфейс поддерживает раннюю привязку и поздняя привязка; однако, двойной интерфейс также поддерживает vtable привязки.

Следующий пример показывает типичную реализацию `IDispatchImpl`.

[!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]

По умолчанию `IDispatchImpl` класс просматривает информацию о типе *для T* в реестре. Для реализации незарегистрированного интерфейса `IDispatchImpl` можно использовать класс без доступа к реестру, используя заранее определенный номер версии. Если вы `IDispatchImpl` создаете объект, который имеет 0xFFFF как значение для *wMajor* и `IDispatchImpl` 0xFFFF как значение для *wMinor,* класс извлекает библиотеку типа из файла .dll вместо реестра.

`IDispatchImpl`содержит статический член `CComTypeInfoHolder` типа, который управляет информацией типа для двойного интерфейса. Если у вас есть несколько объектов, которые `CComTypeInfoHolder` реализуют один и тот же двойной интерфейс, используется только один экземпляр.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`T`

`IDispatchImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="idispatchimplgetidsofnames"></a><a name="getidsofnames"></a>IDispatchImpl::GetIDsOfNames

Сопоставляет набор имен соответствующему набору идентификаторов диспетчеризации.

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

## <a name="idispatchimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispatchImpl::GetTypeInfo

Извлекает информацию о типе для двойного интерфейса.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Примечания

Смотрите [IDispatch::GetTypeInfo](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo) в Windows SDK.

## <a name="idispatchimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispatchImpl::GetTypeInfoCount

Определяет, есть ли информация типа, доступная для двойного интерфейса.

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Примечания

Смотрите `IDispatch::GetTypeInfoCount` в Windows SDK.

## <a name="idispatchimplidispatchimpl"></a><a name="idispatchimpl"></a>IDispatchImpl::IDispatchImpl

Конструктор. Вызовы `AddRef` на защищенную переменную члена, которая управляет информацией типа для двойного интерфейса. Деструктор вызывает `Release`.

```
IDispatchImpl();
```

## <a name="idispatchimplinvoke"></a><a name="invoke"></a>IDispatchImpl::Invoke

Обеспечивает доступ к методам и свойствам, подверженным двойному интерфейсу.

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* pexcepinfo,
    UINT* puArgErr);
```

### <a name="remarks"></a>Примечания

Смотрите [IDispatch::Вызвать](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
