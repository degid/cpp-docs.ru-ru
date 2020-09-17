---
title: IServiceProviderImpl класс
ms.date: 11/04/2016
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
ms.openlocfilehash: ef0ee4f77441cb8d19ea2d6dcada1fed9faf2782
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329419"
---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl класс

Этот класс обеспечивает реализацию `IServiceProvider` интерфейса по умолчанию.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IServiceProviderImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IServiceProviderImpl:::КвиСервис](#queryservice)|Создает или получает доступ к указанной службе и возвращает указатель интерфейса в указанный интерфейс службы.|

## <a name="remarks"></a>Примечания

Интерфейс `IServiceProvider` находит услугу, указанную в графическом интерфейсе, и возвращает указатель интерфейса для запрашиваемого интерфейса в службе. Класс `IServiceProviderImpl` обеспечивает реализацию этого интерфейса по умолчанию.

`IServiceProviderImpl`определяет один метод: [queryService](#queryservice), который создает или получает доступ к указанной службе и возвращает указатель интерфейса к указанному интерфейсу для службы.

`IServiceProviderImpl`использует карту обслуживания, начиная с [BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) и заканчивая [END_SERVICE_MAP.](service-map-macros.md#end_service_map)

Карта службы содержит две записи: [SERVICE_ENTRY,](service-map-macros.md#service_entry)в котором указывается указанный идентификатор службы (SID), поддерживаемый объектом, и [SERVICE_ENTRY_CHAIN,](service-map-macros.md#service_entry_chain)который вызывает `QueryService` цепь к другому объекту.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IServiceProvider`

`IServiceProviderImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="iserviceproviderimplqueryservice"></a><a name="queryservice"></a>IServiceProviderImpl:::КвиСервис

Создает или получает доступ к указанной службе и возвращает указатель интерфейса в указанный интерфейс службы.

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Параметры

*guidService*<br/>
(в) Указатель на идентификатор службы (SID).

*riid*<br/>
(в) Идентификатор интерфейса, к которому абонент должен получить доступ.

*ppvObj*<br/>
(ваут) Косвенный указатель на запрашиваемый интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращается значение HRESULT является одним из следующих:

|Возвращаемое значение|Значение|
|------------------|-------------|
|S_OK|Служба была успешно создана или извлечена.|
|E_INVALIDARG|Один или несколько аргументов являются недопустимыми.|
|E_OUTOFMEMORY|Памяти недостаточно для создания службы.|
|E_UNEXPECTED|Произошла неизвестная ошибка.|
|E_NOINTERFACE|Запрашиваемый интерфейс не является частью этой службы, или служба неизвестна.|

### <a name="remarks"></a>Примечания

`QueryService`возвращает непрямой указатель на запрашиваемый интерфейс в указанной службе. Звонящее отвечает за освобождение этого указателя, когда он больше не требуется.

При звонке `QueryService`вы проходите как идентификатор службы *(guidService),* так и идентификатор интерфейса *(riid).* *Служба guidService* определяет службу, к которой вы хотите получить доступ, а *риид* определяет интерфейс, который является частью службы. Взамен вы получаете непрямой указатель на интерфейс.

Объект, реализуемый в интерфейсе, может также реализовать интерфейсы, которые являются частью других служб. Рассмотрим следующее:

- Некоторые из этих интерфейсов могут быть необязательными. Не все интерфейсы, определенные в описании службы, обязательно присутствуют на каждой реализации службы или на каждом возвращенном объекте.

- В отличие `QueryInterface`от вызовов, передача другого идентификатора службы не обязательно означает, что возвращается другой объект компонентной модели (COM).

- Возвращаемый объект может иметь дополнительные интерфейсы, которые не являются частью определения службы.

Две разные службы, такие как SID_SMyService и SID_SYourService, могут указать использование одного и того же интерфейса, даже если реализация интерфейса может не иметь ничего общего между этими двумя службами. Это работает, потому `QueryService` что вызов (SID_SMyService, IID_IDispatch) `QueryService` может вернуть другой объект, чем (SID_SYourService, IID_IDispatch). Идентификация объекта не предполагается при указании другого идентификатора службы.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
