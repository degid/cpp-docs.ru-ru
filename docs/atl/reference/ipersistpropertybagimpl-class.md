---
title: IPersistPropertyBagImpl Класс
ms.date: 11/04/2016
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
ms.openlocfilehash: f656ecc76b175eae523059c60bb8a3efc6f0b312
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326488"
---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl Класс

Этот класс `IUnknown` реализует и позволяет объекту сохранить свои свойства в пакете свойств, поставляемых клиентом.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IPersistPropertyBagImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Извлекает CLSID объекта.|
|[IPersistPropertyBagImpl::InitNew](#initnew)|Инициализирует вновь созданный объект. Реализация ATL возвращает S_OK.|
|[IPersistPropertyBagImpl::Load](#load)|Загружает свойства объекта из сумки с свойств, поставляемой клиентом.|
|[IPersistPropertyBagImpl::Сохранить](#save)|Сохраняет свойства объекта в сумке с клиентами.|

## <a name="remarks"></a>Примечания

Интерфейс [IPersistPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768205\(v=vs.85\)) позволяет объекту сохранять свои свойства в пакете свойств, поставляемых клиентом. Класс `IPersistPropertyBagImpl` обеспечивает реализацию этого интерфейса `IUnknown` по умолчанию и реализует, отправляя информацию на устройство свалки в отладочных сборках.

`IPersistPropertyBag`работает совместно с [IPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768196\(v=vs.85\)) и [IErrorLog](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768231\(v=vs.85\)). Эти два последних интерфейса должны быть реализованы клиентом. Через, `IPropertyBag`клиент сохраняет и загружает индивидуальные свойства объекта. Через, `IErrorLog`как объект, так и клиент может сообщить о любых обнаруженных ошибках.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ipersistpropertybagimplgetclassid"></a><a name="getclassid"></a>IPersistPropertyBagImpl::GetClassID

Извлекает CLSID объекта.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Примечания

Смотрите [IPersist::GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) в Windows SDK.

## <a name="ipersistpropertybagimplinitnew"></a><a name="initnew"></a>IPersistPropertyBagImpl::InitNew

Инициализирует вновь созданный объект.

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Примечания

Смотрите [IPersistPropertyBag::InitNew](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768204\(v=vs.85\)) в Windows SDK.

## <a name="ipersistpropertybagimplload"></a><a name="load"></a>IPersistPropertyBagImpl::Load

Загружает свойства объекта из сумки с свойств, поставляемой клиентом.

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>Примечания

ATL использует карту свойств объекта для получения этой информации.

Смотрите [IPersistPropertyBag::Загрузка](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768206\(v=vs.85\)) в Windows SDK.

## <a name="ipersistpropertybagimplsave"></a><a name="save"></a>IPersistPropertyBagImpl::Сохранить

Сохраняет свойства объекта в сумке с клиентами.

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>Примечания

ATL использует карту свойств объекта для хранения этой информации. По умолчанию этот метод сохраняет все свойства, независимо от значения *fSaveAllProperties.*

Смотрите [IPersistPropertyBag::Сохранить](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768207\(v=vs.85\)) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
