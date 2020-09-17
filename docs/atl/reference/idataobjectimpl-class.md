---
title: Класс Идатаобжектимпл
ms.date: 11/04/2016
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
ms.openlocfilehash: 379dd3304d96afcd2b0e98ec4a98f1bac64d4ad9
ms.sourcegitcommit: 13f42c339fb7af935e3a93ac80e350d5e784c9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "87470775"
---
# <a name="idataobjectimpl-class"></a>Класс Идатаобжектимпл

Этот класс предоставляет методы для поддержки универсальных Передача данных и управления соединениями.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IDataObjectImpl` .

## <a name="members"></a>Элементы

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Идатаобжектимпл::D advise](#dadvise)|Устанавливает соединение между объектом данных и приемником уведомлений. Это позволяет приемнику уведомлений получать уведомления об изменениях в объекте.|
|[Идатаобжектимпл::D unadvise](#dunadvise)|Завершает соединение, установленное ранее с помощью `DAdvise` .|
|[Идатаобжектимпл:: Енумдадвисе](#enumdadvise)|Создает перечислитель для итерации по текущим вспомогательным соединениям.|
|[Идатаобжектимпл:: Енумформатетк](#enumformatetc)|Создает перечислитель для итерации по структурам `FORMATETC`, поддерживаемым объектом данных. Реализация ATL возвращает E_NOTIMPL.|
|[Идатаобжектимпл:: Фиредатачанже](#firedatachange)|Отправляет уведомление об изменении обратно в каждый приемник уведомлений.|
|[Идатаобжектимпл:: Жетканоникалформатетк](#getcanonicalformatetc)|Извлекает логически эквивалентную `FORMATETC` структуру более сложной. Реализация ATL возвращает E_NOTIMPL.|
|[Идатаобжектимпл:: GetData](#getdata)|Передает данные из объекта данных клиенту. Данные описываются в `FORMATETC` структуре и передаются через `STGMEDIUM` структуру.|
|[Идатаобжектимпл:: Жетдатахере](#getdatahere)|Аналогично `GetData` , за исключением того, что клиент должен выделить `STGMEDIUM` структуру. Реализация ATL возвращает E_NOTIMPL.|
|[Идатаобжектимпл:: Куерижетдата](#querygetdata)|Определяет, поддерживает ли объект данных указанную структуру `FORMATETC` для передачи данных. Реализация ATL возвращает E_NOTIMPL.|
|[Идатаобжектимпл:: SetData](#setdata)|Передает данные от клиента в объект данных. Реализация ATL возвращает E_NOTIMPL.|

## <a name="remarks"></a>Комментарии

Интерфейс [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) предоставляет методы для поддержки однородных передача данных. `IDataObject`использует стандартные структуры формата [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) и [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium-r1) для получения и хранения данных.

`IDataObject`также управляет подключениями к приемникам уведомлений, которые обрабатывали уведомления об изменении данных. Чтобы клиент получал уведомления об изменении данных из объекта данных, клиент должен реализовать интерфейс [иадвисесинк](/windows/win32/api/objidl/nn-objidl-iadvisesink) для объекта, который называется приемником уведомлений. Когда клиент вызывает `IDataObject::DAdvise` , устанавливается соединение между объектом данных и приемником уведомлений.

Класс `IDataObjectImpl` предоставляет реализацию по умолчанию `IDataObject` и реализует `IUnknown` , отправляя сведения в устройство дампа в отладочных сборках.

Руководство по **сопутствующим статьям** [ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл.h

## <a name="idataobjectimpldadvise"></a><a name="dadvise"></a>Идатаобжектимпл::D advise

Устанавливает соединение между объектом данных и приемником уведомлений.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Комментарии

Это позволяет приемнику уведомлений получать уведомления об изменениях в объекте.

Чтобы завершить подключение, вызовите [дунадвисе](#dunadvise).

См. раздел [IDataObject::D advise](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) в Windows SDK.

## <a name="idataobjectimpldunadvise"></a><a name="dunadvise"></a>Идатаобжектимпл::D unadvise

Прерывает подключение, установленное ранее с помощью [дадвисе](#dadvise).

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>Комментарии

См. раздел [IDataObject::D unadvise](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) в Windows SDK.

## <a name="idataobjectimplenumdadvise"></a><a name="enumdadvise"></a>Идатаобжектимпл:: Енумдадвисе

Создает перечислитель для итерации по текущим вспомогательным соединениям.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Комментарии

См. раздел [IDataObject:: енумдадвисе](/windows/win32/api/objidl/nf-objidl-idataobject-enumdadvise) в Windows SDK.

## <a name="idataobjectimplenumformatetc"></a><a name="enumformatetc"></a>Идатаобжектимпл:: Енумформатетк

Создает перечислитель для итерации по структурам `FORMATETC`, поддерживаемым объектом данных.

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>Комментарии

См. раздел [IDataObject:: енумформатетк](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

## <a name="idataobjectimplfiredatachange"></a><a name="firedatachange"></a>Идатаобжектимпл:: Фиредатачанже

Отправляет уведомление об изменении в каждый приемник уведомлений, управляемый в данный момент.

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="idataobjectimplgetcanonicalformatetc"></a><a name="getcanonicalformatetc"></a>Идатаобжектимпл:: Жетканоникалформатетк

Извлекает логически эквивалентную `FORMATETC` структуру более сложной.

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Комментарии

См. раздел [IDataObject:: жетканоникалформатетк](/windows/win32/api/objidl/nf-objidl-idataobject-getcanonicalformatetc) в Windows SDK.

## <a name="idataobjectimplgetdata"></a><a name="getdata"></a>Идатаобжектимпл:: GetData

Передает данные из объекта данных клиенту.

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>Комментарии

Параметр *пформатетЦин* должен указывать тип среды хранения TYMED_MFPICT.

См. раздел [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) в Windows SDK.

## <a name="idataobjectimplgetdatahere"></a><a name="getdatahere"></a>Идатаобжектимпл:: Жетдатахере

Аналогично `GetData` , за исключением того, что клиент должен выделить `STGMEDIUM` структуру.

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Комментарии

См. раздел [IDataObject:: жетдатахере](/windows/win32/api/objidl/nf-objidl-idataobject-getdatahere) в Windows SDK.

## <a name="idataobjectimplquerygetdata"></a><a name="querygetdata"></a>Идатаобжектимпл:: Куерижетдата

Определяет, поддерживает ли объект данных указанную структуру `FORMATETC` для передачи данных.

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Комментарии

См. раздел [IDataObject:: куерижетдата](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) в Windows SDK.

## <a name="idataobjectimplsetdata"></a><a name="setdata"></a>Идатаобжектимпл:: SetData

Передает данные от клиента в объект данных.

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Комментарии

См. раздел [IDataObject:: SetData](/windows/win32/api/objidl/nf-objidl-idataobject-setdata) в Windows SDK.

## <a name="see-also"></a>См. также статью

[Общие сведения о классах](../../atl/atl-class-overview.md)
