---
title: IPerPropertyБражИмпл класс
ms.date: 11/04/2016
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
ms.openlocfilehash: f8fb80cc38e775b9b26afa033647faac694e968a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326513"
---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyБражИмпл класс

Этот класс `IUnknown` реализует и позволяет клиенту получить доступ к информации на страницах свойств объекта.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IPerPropertyBrowsingImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IPerPropertyБражИмпл::GetDisplayString](#getdisplaystring)|Извлекает строку, описывающую данное свойство.|
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Извлекает массив строк, соответствующих значениям, которые может принять данное свойство.|
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Извлекает VARIANT, содержащий значение свойства, идентифицированного данной DISPID. DISPID связан с именем строки, извлеченным из `GetPredefinedStrings`. Реализация ATL возвращает E_NOTIMPL.|
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|Извлекает CLSID страницы свойств, связанных с данным свойством.|

## <a name="remarks"></a>Примечания

Интерфейс [IPerPropertyBrowsing](/windows/win32/api/ocidl/nn-ocidl-iperpropertybrowsing) позволяет клиенту получить доступ к информации на страницах свойств объекта. Класс `IPerPropertyBrowsingImpl` обеспечивает реализацию этого интерфейса `IUnknown` по умолчанию и реализует, отправляя информацию на устройство свалки в отладочных сборках.

> [!NOTE]
> Если вы используете Microsoft Access в качестве контейнерного `IPerPropertyBrowsingImpl`приложения, вы должны получить свой класс из. В противном случае Access не загрузит элемент управления.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="iperpropertybrowsingimplgetdisplaystring"></a><a name="getdisplaystring"></a>IPerPropertyБражИмпл::GetDisplayString

Извлекает строку, описывающую данное свойство.

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>Примечания

Смотрите [IPerPropertyBrowsing::GetDisplayString](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) в Windows SDK.

## <a name="iperpropertybrowsingimplgetpredefinedstrings"></a><a name="getpredefinedstrings"></a>IPerPropertyBrowsingImpl::GetPredefinedStrings

Заполняет каждый массив нулевыми элементами.

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>Возвращаемое значение

Реализация ATL [GetPredefinedValue](#getpredefinedvalue) возвращается E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IPerPropertyBrowsing::GetPredefinedStrings](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) в Windows SDK.

## <a name="iperpropertybrowsingimplgetpredefinedvalue"></a><a name="getpredefinedvalue"></a>IPerPropertyBrowsingImpl::GetPredefinedValue

Извлекает VARIANT, содержащий значение свойства, идентифицированного данной DISPID. DISPID связан с именем строки, извлеченным из `GetPredefinedStrings`.

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Реализация [ATL GetPredefinedStrings](#getpredefinedstrings) не получает соответствующих строк.

Смотрите [IPerPropertyBrowsing::GetPredefinedValue](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) в Windows SDK.

## <a name="iperpropertybrowsingimplmappropertytopage"></a><a name="mappropertytopage"></a>IPerPropertyBrowsingImpl::MapPropertyToPage

Извлекает CLSID страницы свойств, связанных с указанным свойством.

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>Примечания

ATL использует карту свойств объекта для получения этой информации.

Смотрите [IPerPropertyBrowsing::MapPropertyToPage](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[IPropertyPageImpl класс](../../atl/reference/ipropertypageimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl класс](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
