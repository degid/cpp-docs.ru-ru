---
title: ISupportErrorInfoImpl класс
ms.date: 06/13/2019
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
ms.openlocfilehash: 4c60b58ba697f00b146077a2cdecd727fe2cac02
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326370"
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl класс

Этот класс обеспечивает реализацию [интерфейса ISupportErrorInfo](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) по умолчанию и может использоваться, когда только один интерфейс генерирует ошибки на объекте.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>Параметры

*пиид*<br/>
Указатель на IID интерфейса, поддерживающего [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo).

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsОшибкаОшибкаИнфо](#interfacesupportserrorinfo)|Указывает, поддерживает ли `riid` интерфейс, идентифицированный по поддерживает интерфейс [IErrorInfo.](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)|

## <a name="remarks"></a>Примечания

[Интерфейс ISupportErrorInfo](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) гарантирует, что информация об ошибках может быть возвращена клиенту. Объекты, `IErrorInfo` которые `ISupportErrorInfo`используют должны реализовать.

Класс `ISupportErrorInfoImpl` обеспечивает реализацию `ISupportErrorInfo` по умолчанию и может использоваться, когда только один интерфейс генерирует ошибки на объекте. Пример:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="isupporterrorinfoimplinterfacesupportserrorinfo"></a><a name="interfacesupportserrorinfo"></a>ISupportErrorInfoImpl::InterfaceSupportsОшибкаОшибкаИнфо

Указывает, поддерживает ли `riid` интерфейс, идентифицированный по поддерживает интерфейс [IErrorInfo.](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>Примечания

Смотрите [ISupportErrorInfo::InterfaceSupportsErrorInfo](/windows/win32/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
