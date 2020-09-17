---
title: Сопоставление служб макросов
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
ms.openlocfilehash: 1fa163098d89dd949c17ee7cd5e4ddc46cd2a091
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835211"
---
# <a name="service-map-macros"></a>Сопоставление служб макросов

Эти макросы определяют схемы служб и записи.

|Имя|Описание|
|-|-|
|[BEGIN_SERVICE_MAP](#begin_service_map)|Помечает начало схемы службы ATL.|
|[END_SERVICE_MAP](#end_service_map)|Помечает конец схемы службы ATL.|
|[SERVICE_ENTRY](#service_entry)|Указывает, что объект поддерживает конкретный идентификатор службы.|
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|Указывает, что [исервицепровидеримпл:: QueryService](#queryservice) следует связать с указанным объектом.|

## <a name="requirements"></a>Требования

**Заголовок:** атлком.h

## <a name="begin_service_map"></a><a name="begin_service_map"></a> BEGIN_SERVICE_MAP

Помечает начало схемы услуги.

```
BEGIN_SERVICE_MAP(theClass)
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
окне Указывает класс, содержащий схему услуги.

### <a name="remarks"></a>Примечания

Используйте схему Услуги для реализации функциональности поставщика услуг в объекте COM. Сначала необходимо создать класс, производный от [исервицепровидеримпл](../../atl/reference/iserviceproviderimpl-class.md). Существует два типа записей:

- [SERVICE_ENTRY](#service_entry)   Указывает поддержку для указанного идентификатора службы (SID).

- [SERVICE_ENTRY_CHAIN](#service_entry_chain)   Указывает, что [исервицепровидеримпл:: QueryService](#queryservice) следует связать с другим, указанным объектом.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]

## <a name="end_service_map"></a><a name="end_service_map"></a> END_SERVICE_MAP

Помечает конец схемы услуги.

```
END_SERVICE_MAP()
```

### <a name="example"></a>Пример

См. пример для [BEGIN_SERVICE_MAP](#begin_service_map).

## <a name="service_entry"></a><a name="service_entry"></a> SERVICE_ENTRY

Указывает, что объект поддерживает идентификатор службы, указанный в *SID*.

```
SERVICE_ENTRY( SID )
```

### <a name="parameters"></a>Параметры

*SID*<br/>
Идентификатор службы.

### <a name="example"></a>Пример

См. пример для [BEGIN_SERVICE_MAP](#begin_service_map).

## <a name="service_entry_chain"></a><a name="service_entry_chain"></a> SERVICE_ENTRY_CHAIN

Указывает, что [исервицепровидеримпл:: QueryService](#queryservice) следует связать с объектом, указанным в *Punk*.

```
SERVICE_ENTRY_CHAIN( punk )
```

### <a name="parameters"></a>Параметры

*Punk*<br/>
Указатель на интерфейс **IUnknown** , к которому необходимо привязать цепочку.

### <a name="example"></a>Пример

См. пример для [BEGIN_SERVICE_MAP](#begin_service_map).

## <a name="iserviceproviderimplqueryservice"></a><a name="queryservice"></a> Исервицепровидеримпл:: QueryService

Создает или обращается к указанной службе и возвращает указатель интерфейса на указанный интерфейс для службы.

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Параметры

*гуидсервице*<br/>
окне Указатель на идентификатор службы (SID).

*riid*<br/>
окне Идентификатор интерфейса, к которому вызывающий объект должен получить доступ.

*ппвобж*<br/>
заполняет Косвенный указатель на запрошенный интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращенное значение HRESULT является одним из следующих:

|Возвращаемое значение|Значение|
|------------------|-------------|
|S_OK|Служба успешно создана или получена.|
|E_INVALIDARG|Один или несколько аргументов являются недопустимыми.|
|E_OUTOFMEMORY|Недостаточно памяти для создания службы.|
|E_UNEXPECTED|Произошла неизвестная ошибка.|
|E_NOINTERFACE|Запрошенный интерфейс не является частью этой службы, или служба неизвестна.|

### <a name="remarks"></a>Примечания

`QueryService` Возвращает непрямой указатель на запрошенный интерфейс в указанной службе. Вызывающий объект отвечает за освобождение этого указателя, когда он больше не требуется.

При вызове `QueryService` вы передаете идентификатор службы (*гуидсервице*) и идентификатор интерфейса (*riid*). *Гуидсервице* указывает службу, к которой необходимо получить доступ, а *riid* определяет интерфейс, который является частью службы. В случае возврата вы получаете косвенный указатель на интерфейс.

Объект, реализующий интерфейс, может также реализовывать интерфейсы, которые являются частью других служб. Рассмотрим следующий пример.

- Некоторые из этих интерфейсов могут быть необязательными. Не все интерфейсы, определенные в описании службы, всегда приводятся при каждой реализации службы или при каждом возвращенном объекте.

- В отличие от вызовов `QueryInterface` , передача другого идентификатора службы не обязательно означает, что возвращается другой объект модели COM.

- Возвращаемый объект может иметь дополнительные интерфейсы, не входящие в определение службы.

Две различные службы, такие как SID_SMyService и SID_SYourService, могут указывать использование одного интерфейса, даже несмотря на то, что реализация интерфейса может вообще не иметь ничего общего между двумя службами. Это работает, поскольку вызов `QueryService` (SID_SMyService, IID_IDispatch) может возвращать другой объект, чем `QueryService` (SID_SYourService, IID_IDispatch). При указании другого идентификатора службы удостоверение объекта не предполагается.

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
