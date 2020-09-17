---
title: IObjectSafetyImpl класс
ms.date: 11/04/2016
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
ms.openlocfilehash: 6eee7585bc3c5587e106ab6b0cefb4b7129df59f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329652"
---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl класс

Этот класс обеспечивает реализацию `IObjectSafety` интерфейса по умолчанию, позволяющую клиенту получать и устанавливать уровни безопасности объекта.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T,DWORD dwSupportedSafety>
class IObjectSafetyImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `IObjectSafetyImpl`.

*dwSupportedSafety*<br/>
Определяет поддерживаемые варианты безопасности для управления. Может использоваться одно из следующих значений:

- INTERFACESAFE_FOR_UNTRUSTED_CALLER интерфейс, идентифицированный параметром `riid` [SetInterfaceSafetyOptions,](#setinterfacesafetyoptions) должен быть безопасным для сценариев.

- INTERFACESAFE_FOR_UNTRUSTED_DATA интерфейс, идентифицированный `riid` по параметру, `SetInterfaceSafetyOptions` должен быть безопасным для ненадежных данных во время инициализации.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Извлекает параметры безопасности, поддерживаемые объектом, а также параметры безопасности, установленные в настоящее время для объекта.|
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Делает объект безопасным для инициализации или скриптов.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|Хранит текущий уровень безопасности объекта.|

## <a name="remarks"></a>Примечания

Класс `IObjectSafetyImpl` обеспечивает реализацию `IObjectSafety`по умолчанию . Интерфейс `IObjectSafety` позволяет клиенту получить и установить уровень безопасности объекта. Например, веб-браузер `IObjectSafety::SetInterfaceSafetyOptions` может вызвать, чтобы сделать контроль безопасным для инициализации или безопасным для скриптов.

Обратите внимание, что использование [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) макроса с категориями CATID_SafeForScripting и CATID_SafeForInitializing компонентов обеспечивает альтернативный способ определения того, что компонент является безопасным.

**Похожие статьи** [ATL Учебник](../../atl/active-template-library-atl-tutorial.md), Создание проекта [ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IObjectSafety`

`IObjectSafetyImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="iobjectsafetyimplgetinterfacesafetyoptions"></a><a name="getinterfacesafetyoptions"></a>IObjectSafetyImpl::GetInterfaceSafetyOptions

Извлекает параметры безопасности, поддерживаемые объектом, а также параметры безопасности, установленные в настоящее время для объекта.

```
HRESULT GetInterfaceSafetyOptions(
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```

### <a name="remarks"></a>Примечания

Реализация возвращает соответствующие значения для любого интерфейса, `IUnknown::QueryInterface`поддерживаемого реализацией объекта.

> [!IMPORTANT]
> Любой объект, который поддерживает, `IObjectSafety` отвечает за свою собственную безопасность и безопасность любого объекта, который он делегирует. Программист должен учитывать проблемы, возникающие в связи с запуском кода в контексте пользователя, кросс-сайтом сценариев и выполнять соответствующую проверку зоны.

Смотрите [IObjectSafety::GetInterfaceSafetyOptions](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768223\(v=vs.85\)) в Windows SDK.

## <a name="iobjectsafetyimplm_dwcurrentsafety"></a><a name="m_dwcurrentsafety"></a>IObjectSafetyImpl::m_dwCurrentSafety

Хранит текущий уровень безопасности объекта.

```
DWORD m_dwCurrentSafety;
```

## <a name="iobjectsafetyimplsetinterfacesafetyoptions"></a><a name="setinterfacesafetyoptions"></a>IObjectSafetyImpl::SetInterfaceSafetyOptions

Делает объект безопасным для инициализации или скрипта, установив [m_dwCurrentSafety](#m_dwcurrentsafety) член омрачаемому значению.

```
HRESULT SetInterfaceSafetyOptions(
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```

### <a name="remarks"></a>Примечания

Реализация возвращает E_NOINTERFACE для любого интерфейса, не `IUnknown::QueryInterface`поддерживаемого реализацией объекта.

> [!IMPORTANT]
> Любой объект, который поддерживает, `IObjectSafety` отвечает за свою собственную безопасность и безопасность любого объекта, который он делегирует. Программист должен учитывать проблемы, возникающие в связи с запуском кода в контексте пользователя, кросс-сайтом сценариев и выполнять соответствующую проверку зоны.

Смотрите [IObjectSafety::SetInterfaceSafetyOptions](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768225\(v=vs.85\)) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Интерфейс IObjectSafety](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768224\(v=vs.85\))<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
