---
title: ISpecifyPropertyPagesImpl класс
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: 06b6b60227a659bd35e042952c7464971fc40bdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326402"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl класс

Этот класс `IUnknown` реализует и обеспечивает реализацию интерфейса [ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) по умолчанию.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `ISpecifyPropertyPagesImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Заполняет подсчитанный массив значений UUID. Каждый UUID соответствует CLSID для одной из страниц свойств, которые могут быть отображены в листе свойства объекта.|

## <a name="remarks"></a>Примечания

Интерфейс [ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) позволяет клиенту получить список CLSID для страниц свойств, поддерживаемых объектом. Класс `ISpecifyPropertyPagesImpl` обеспечивает реализацию этого интерфейса `IUnknown` по умолчанию и реализует, отправляя информацию на устройство свалки в отладочных сборках.

> [!NOTE]
> Не разоблачайте интерфейс, `ISpecifyPropertyPages` если объект не поддерживает страницы свойств.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ispecifypropertypagesimplgetpages"></a><a name="getpages"></a>ISpecifyPropertyPagesImpl::GetPages

Заполняет массив в [структуре CAUUID](/windows/win32/api/ocidl/ns-ocidl-cauuid) CLSID для страниц свойств, которые могут отображаться в листе свойства объекта.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>Примечания

ATL использует карту свойств объекта для получения каждого CLSID.

Смотрите [ISpecifyPropertyPages::GetPages](/windows/win32/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[IPropertyPageImpl класс](../../atl/reference/ipropertypageimpl-class.md)<br/>
[IPerPropertyБражИмпл класс](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
