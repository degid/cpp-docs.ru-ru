---
title: IObjectWithSiteImpl класс
ms.date: 11/04/2016
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
ms.openlocfilehash: 034e5dd42f6e10286520bb2a08effc40b0aca71a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329647"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl класс

Этот класс предоставляет методы, позволяющие объекту общаться со своим сайтом.

## <a name="syntax"></a>Синтаксис

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IObjectWithSiteImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IObjectWithSiteImpl::GetSite](#getsite)|Запрашивает сайт для указателя интерфейса.|
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Обеспечивает объект указателем сайта. `IUnknown`|
|[IObjectWithSiteImpl::SetSite](#setsite)|Обеспечивает объект указателем сайта. `IUnknown`|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Управляет `IUnknown` указателем сайта.|

## <a name="remarks"></a>Примечания

Интерфейс [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) позволяет объекту общаться со своим сайтом. Класс `IObjectWithSiteImpl` обеспечивает реализацию этого интерфейса `IUnknown` по умолчанию и реализует, отправляя информацию на устройство свалки в отладочных сборках.

`IObjectWithSiteImpl`определяет два метода. Клиент сначала `SetSite`звонит, проходя `IUnknown` указатель сайта. Этот указатель хранится внутри объекта, а затем может `GetSite`быть извлечен через вызов.

Как правило, вы `IObjectWithSiteImpl` получаете свой класс от создания объекта, который не является элементом управления. Для управления, получить свой класс от [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), который также предоставляет указатель сайта. Не извлекайте свой `IObjectWithSiteImpl` `IOleObjectImpl`класс из обоих и .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="iobjectwithsiteimplgetsite"></a><a name="getsite"></a>IObjectWithSiteImpl::GetSite

Запросы сайта для указателя на интерфейс, идентифицированный `riid`.

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>Примечания

Если сайт поддерживает этот интерфейс, указатель `ppvSite`возвращается через . В `ppvSite` противном случае, устанавливается на NULL.

Смотрите [IObjectWithSite::GetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-getsite) в Windows SDK.

## <a name="iobjectwithsiteimplm_spunksite"></a><a name="m_spunksite"></a>IObjectWithSiteImpl::m_spUnkSite

Управляет `IUnknown` указателем сайта.

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>Примечания

`m_spUnkSite`первоначально получает этот указатель через звонок к [SetSite.](#setsite)

## <a name="iobjectwithsiteimplsetchildsite"></a><a name="setchildsite"></a>IObjectWithSiteImpl::SetChildSite

Обеспечивает объект указателем сайта. `IUnknown`

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>Параметры

*pUnkSite*<br/>
(в) Указатель на `IUnknown` указатель интерфейса сайта, управляющего этим объектом. Если NULL, объект `IUnknown::Release` должен вызвать на любой существующий сайт, в какой момент объект больше не знает своего сайта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="iobjectwithsiteimplsetsite"></a><a name="setsite"></a>IObjectWithSiteImpl::SetSite

Обеспечивает объект указателем сайта. `IUnknown`

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>Примечания

Смотрите [IObjectWithSite::SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite) в SDK Windows.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
