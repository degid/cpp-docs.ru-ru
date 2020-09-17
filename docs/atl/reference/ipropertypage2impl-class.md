---
title: IPropertyPage2Impl класс
ms.date: 11/04/2016
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
ms.openlocfilehash: d112a2411a9debbf2eb77e6b851f4500e8d32ab8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329595"
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl класс

Этот класс `IUnknown` реализует и наследует реализацию [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)по умолчанию.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IPropertyPage2Impl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IPropertyPage2Impl::EditProperty](#editproperty)|Определяет, какой элемент управления свойствами будет получать фокус при активации страницы свойств. Реализация ATL возвращает E_NOTIMPL.|

## <a name="remarks"></a>Примечания

Интерфейс [IPropertyPage2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) расширяет [IPropertyPage,](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) `EditProperty` добавляя метод. Этот метод позволяет клиенту выбрать определенное свойство в объекте страницы свойства.

Класс `IPropertyPage2Impl` просто возвращает `IPropertyPage2::EditProperty`E_NOTIMPL для . Тем не менее, он наследует реализацию [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) по умолчанию и `IUnknown` реализует, отправляя информацию на устройство свалки в отладочных сборках.

При создании страницы свойств ваш класс обычно `IPropertyPageImpl`происходит от . Чтобы обеспечить дополнительную `IPropertyPage2`поддержку, изменить определение `EditProperty` класса и переопределить метод.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPropertyPage`

[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="ipropertypage2impleditproperty"></a><a name="editproperty"></a>IPropertyPage2Impl::EditProperty

Определяет, какой элемент управления свойствами будет получать фокус при активации страницы свойств.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Смотрите [IPropertyPage2:: EditProperty](/windows/win32/api/ocidl/nf-ocidl-ipropertypage2-editproperty) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[IPerPropertyБражИмпл класс](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl класс](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
