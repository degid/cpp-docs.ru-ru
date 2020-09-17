---
title: Класс CComModule
ms.date: 08/19/2019
f1_keywords:
- CComModule
- ATLBASE/ATL::CComModule
- ATLBASE/ATL::CComModule::GetClassObject
- ATLBASE/ATL::CComModule::GetModuleInstance
- ATLBASE/ATL::CComModule::GetResourceInstance
- ATLBASE/ATL::CComModule::GetTypeLibInstance
- ATLBASE/ATL::CComModule::Init
- ATLBASE/ATL::CComModule::RegisterClassHelper
- ATLBASE/ATL::CComModule::RegisterClassObjects
- ATLBASE/ATL::CComModule::RegisterServer
- ATLBASE/ATL::CComModule::RegisterTypeLib
- ATLBASE/ATL::CComModule::RevokeClassObjects
- ATLBASE/ATL::CComModule::Term
- ATLBASE/ATL::CComModule::UnregisterClassHelper
- ATLBASE/ATL::CComModule::UnregisterServer
- ATLBASE/ATL::CComModule::UpdateRegistryClass
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CComModule::m_csObjMap
- ATLBASE/ATL::CComModule::m_csTypeInfoHolder
- ATLBASE/ATL::CComModule::m_csWindowCreate
- ATLBASE/ATL::CComModule::m_hInst
- ATLBASE/ATL::CComModule::m_hInstResource
- ATLBASE/ATL::CComModule::m_hInstTypeLib
- ATLBASE/ATL::CComModule::m_pObjMap
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
ms.openlocfilehash: 5e30f847ff99a80ab19b880728472a339fd4cbe5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747930"
---
# <a name="ccommodule-class"></a>Класс CComModule

По состоянию на ATL 7.0, `CComModule` является амортизированы: см. [ATL Module Classes](../../atl/atl-module-classes.md)

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CComModule : public _ATL_MODULE
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComModule::GetClassObject](#getclassobject)|Создает объект указанного CLSID. Только для DLLs.|
|[CComModule::GetModuleInstance](#getmoduleinstance)|Возвращает `m_hInst`.|
|[CComModule::GetResourceInstance](#getresourceinstance)|Возвращает `m_hInstResource`.|
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|Возвращает `m_hInstTypeLib`.|
|[CComModule::Init](#init)|Инициализирует членов данных.|
|[CComModule:RegisterClassHelper](#registerclasshelper)|Вводит регистрацию стандартного класса объекта в системном реестре.|
|[CComModule::RegisterClassObjects](#registerclassobjects)|Регистрирует объект класса. Только для EXEs.|
|[CComModule::RegisterServer](#registerserver)|Обновляет системный реестр для каждого объекта на карте объекта.|
|[CComModule::RegisterTypeLib](#registertypelib)|Регистрирует библиотеку типов.|
|[CComModule::RevokeClassObjects](#revokeclassobjects)|Отменяет объект класса. Только для EXEs.|
|[CComModule::Срок](#term)|Выпускает членов данных.|
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|Удаляет регистрацию стандартного класса объекта из системного реестра.|
|[CComModule::UnregisterServer](#unregisterserver)|Отменить регистрацию каждого объекта на карте объекта.|
|[CComModule::UpdateRegistryClass](#updateregistryclass)|Регистрация или нерегистрация регистрации стандартного класса объекта.|
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Запускает скрипт, содержащийся в указанном ресурсе, для регистрации или отрегистрации объекта.|
|[CComModule:UpdateRegistryFromРесурсы](#updateregistryfromresources)|Статически ссылки на компонент реестра ATL. Запускает скрипт, содержащийся в указанном ресурсе, для регистрации или отрегистрации объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComModule::m_csObjMap](#m_csobjmap)|Обеспечивает синхронизированный доступ к информации о карте объекта.|
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|Обеспечивает синхронизированный доступ к информации библиотеки типов.|
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|Обеспечивает синхронизированный доступ к информации о классе окон и статическим данным, используемым при создании окна.|
|[CComModule::m_hInst](#m_hinst)|Содержит ручку экземпляра модуля.|
|[CComModule::m_hInstResource](#m_hinstresource)|По умолчанию содержит ручку в экземпляр модуля.|
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|По умолчанию содержит ручку в экземпляр модуля.|
|[CComModule::m_pObjMap](#m_pobjmap)|Указывает на карту объекта, поддерживаемую экземпляром модуля.|

## <a name="remarks"></a>Примечания

> [!NOTE]
> Этот класс является амортизированным, и мастера генерации кода ATL теперь используют классы [cAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) и [CAtlModule.](../../atl/reference/catlmodule-class.md) Для получения дополнительной информации смотрите [классы модулей ATL.](../../atl/atl-module-classes.md) Информация, которая следует для использования с приложениями, созданными с более старыми релизами ATL. `CComModule`по-прежнему является частью ATL для обратных возможностей.

`CComModule`реализует модуль сервера COM, что позволяет клиенту получить доступ к компонентам модуля. `CComModule`поддерживает как DLL (в процессе) и EXE (местные) модули.

Экземпляр `CComModule` использует карту объекта для поддержания набора определений объектов класса. Эта карта объектов `_ATL_OBJMAP_ENTRY` реализована как массив структур и содержит информацию для:

- Ввод и удаление описаний объектов в системном реестре.

- Мгновенное воспроизведение объектов через фабрику класса.

- Установление связи между клиентом и корневым объектом в компоненте.

- Выполнение управления объектами класса в течение всей жизни.

При запуске ATL COM AppWizard мастер `_Module`автоматически генерирует, `CComModule` глобальный экземпляр или класс, полученный из него. Для получения дополнительной информации о ATL [Creating an ATL Project](../../atl/reference/creating-an-atl-project.md)проект Мастера, см.

В дополнение `CComModule`к, ATL предоставляет [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), который реализует квартиру-модель модуля для EXEs и Windows услуг. Извлекайте `CComAutoThreadModule` свой модуль из того момента, когда вы хотите создавать объекты в нескольких квартирах.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CComModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccommodulegetclassobject"></a><a name="getclassobject"></a>CComModule::GetClassObject

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Параметры

*rclsid*<br/>
(в) CLSID объекта, который будет создан.

*riid*<br/>
(в) IID запрашиваемого интерфейса.

*Ppv*<br/>
(ваут) Указатель на указатель интерфейса, идентифицированный *riid*. Если объект не поддерживает этот интерфейс, *ppv* настроен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Создает объект указанного CLSID и получает указатель интерфейса к этому объекту.

`GetClassObject`доступен только для DLLs.

## <a name="ccommodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CComModule::GetModuleInstance

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Возвращаемое значение

HINSTANCE идентифицирует этот модуль.

### <a name="remarks"></a>Примечания

Возвращает m_hInst [данных.](#m_hinst)

## <a name="ccommodulegetresourceinstance"></a><a name="getresourceinstance"></a>CComModule::GetResourceInstance

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Возвращаемое значение

An HINSTANCE.

### <a name="remarks"></a>Примечания

Возвращает m_hInstResource [участнике](#m_hinstresource) данных.

## <a name="ccommodulegettypelibinstance"></a><a name="gettypelibinstance"></a>CComModule::GetTypeLibInstance

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HINSTANCE GetTypeLibInstance() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

An HINSTANCE.

### <a name="remarks"></a>Примечания

Возвращает m_hInstTypeLib [данных.](#m_hinsttypelib)

## <a name="ccommoduleinit"></a><a name="init"></a>CComModule::Init

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
(в) Указатель на массив записей карты объектов.

*H*<br/>
(в) HINSTANCE перешли `DLLMain` к `WinMain`или .

*плибид*<br/>
(в) Указатель на LIBID библиотеки типов, связанных с проектом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Инициализирует всех участников данных.

## <a name="ccommodulem_csobjmap"></a><a name="m_csobjmap"></a>CComModule::m_csObjMap

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
CRITICAL_SECTION m_csObjMap;
```

### <a name="remarks"></a>Примечания

Обеспечивает синхронизированный доступ к карте объекта.

## <a name="ccommodulem_cstypeinfoholder"></a><a name="m_cstypeinfoholder"></a>CComModule::m_csTypeInfoHolder

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
CRITICAL_SECTION m_csTypeInfoHolder;
```

### <a name="remarks"></a>Примечания

Обеспечивает синхронизированный доступ к библиотеке типов.

## <a name="ccommodulem_cswindowcreate"></a><a name="m_cswindowcreate"></a>CComModule::m_csWindowCreate

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
CRITICAL_SECTION m_csWindowCreate;
```

### <a name="remarks"></a>Примечания

Обеспечивает синхронизированный доступ к информации о классе окон и статическим данным, используемым при создании окна.

## <a name="ccommodulem_hinst"></a><a name="m_hinst"></a>CComModule::m_hInst

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HINSTANCE m_hInst;
```

### <a name="remarks"></a>Примечания

Содержит ручку экземпляра модуля.

Метод [Init](#init) `m_hInst` устанавливается на `DLLMain` ручку, передаваемую или `WinMain`.

## <a name="ccommodulem_hinstresource"></a><a name="m_hinstresource"></a>CComModule::m_hInstResource

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HINSTANCE m_hInstResource;
```

### <a name="remarks"></a>Примечания

По умолчанию содержит ручку в экземпляр модуля.

Метод [Init](#init) `m_hInstResource` устанавливается на `DLLMain` ручку, передаваемую или `WinMain`. Можно явно установить `m_hInstResource` на рукоятку ресурс.

Метод [GetResourceInstance](#getresourceinstance) возвращает ручку, хранящуюся в. `m_hInstResource`

## <a name="ccommodulem_hinsttypelib"></a><a name="m_hinsttypelib"></a>CComModule::m_hInstTypeLib

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HINSTANCE m_hInstTypeLib;
```

### <a name="remarks"></a>Примечания

По умолчанию содержит ручку в экземпляр модуля.

Метод [Init](#init) `m_hInstTypeLib` устанавливается на `DLLMain` ручку, передаваемую или `WinMain`. Можно явно установить `m_hInstTypeLib` на рукоятку библиотеку типов.

Метод [GetTypeLibInstance](#gettypelibinstance) возвращает ручку, хранящуюся в. `m_hInstTypeLib`

## <a name="ccommodulem_pobjmap"></a><a name="m_pobjmap"></a>CComModule::m_pObjMap

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```

### <a name="remarks"></a>Примечания

Указывает на карту объекта, поддерживаемую экземпляром модуля.

## <a name="ccommoduleregisterclasshelper"></a><a name="registerclasshelper"></a>CComModule:RegisterClassHelper

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
ATL_DEPRECATED HRESULT RegisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
(в) CLSID объекта, который должен быть зарегистрирован.

*lpszProgID*<br/>
(в) ProgID, связанный с объектом.

*lpszVerIndProgID*<br/>
(в) Версия-независимая ProgID, связанная с объектом.

*nDescID*<br/>
(в) Идентификатор ресурса строки для описания объекта.

*dwFlags*<br/>
(в) Определяет модель потока для входа в реестр. Возможные значения: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH или AUTPRXFLAG.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Вводит регистрацию стандартного класса объекта в системном реестре.

Вызовы метода `RegisterClassHelper` [UpdateRegistryClass](#updateregistryclass) .

## <a name="ccommoduleregisterclassobjects"></a><a name="registerclassobjects"></a>CComModule::RegisterClassObjects

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>Параметры

*dwClsКонтекст*<br/>
(в) Определяет контекст, в котором должен быть запущен объект класса. Возможные значения : CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER. Для описания этих значений [см.](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx)

*dwFlags*<br/>
(в) Определяет типы соединения с объектом класса. Возможные значения — REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE. Для описания этих значений [см.](/windows/win32/api/combaseapi/ne-combaseapi-regcls)

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Регистрирует объект класса EXE с помощью OLE, чтобы другие приложения могли подключиться к нему. Этот метод доступен только для EXEs.

## <a name="ccommoduleregisterserver"></a><a name="registerserver"></a>CComModule::RegisterServer

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Параметры

*bRegTypeLib*<br/>
(в) Указывается, будет ли зарегистрирована библиотека типов. Значение по умолчанию — FALSE.

*pCLSID*<br/>
(в) Указывает на CLSID зарегистрированного объекта. Если NULL (значение по умолчанию) все объекты на карте объектов будут зарегистрированы.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

В зависимости от параметра *pCLSID* обновляется системный реестр для одного объекта класса или для всех объектов на карте объекта.

Если *bRegTypeLib* является правдой, информация о библиотеке типов также будет обновляться.

Ознакомьтесь [с OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) информации о том, как добавить запись на карту объекта.

`RegisterServer`будет автоматически вызываться `DLLRegisterServer` для DLL `WinMain` или для выполнения `/RegServer` EXE с опцией командной строки.

## <a name="ccommoduleregistertypelib"></a><a name="registertypelib"></a>CComModule::RegisterTypeLib

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```

### <a name="parameters"></a>Параметры

*lpszИндекс*<br/>
(в) Строка в `"\\N"`формате , где `N` находится инкемге индекс ресурса TYPELIB.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Добавляет информацию о библиотеке типа в системный реестр.

Если экземпляр модуля содержит несколько библиотек типов, используйте вторую версию этого метода, чтобы указать, какой тип библиотеки следует использовать.

## <a name="ccommodulerevokeclassobjects"></a><a name="revokeclassobjects"></a>CComModule::RevokeClassObjects

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Удаляет объект класса. Этот метод доступен только для EXEs.

## <a name="ccommoduleterm"></a><a name="term"></a>CComModule::Срок

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```cpp
void Term() throw();
```

### <a name="remarks"></a>Примечания

Выпускает всех участников данных.

## <a name="ccommoduleunregisterclasshelper"></a><a name="unregisterclasshelper"></a>CComModule::UnregisterClassHelper

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
ATL_DEPRECATED HRESULT UnregisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
(в) CLSID объекта, который должен быть незарегистрированным.

*lpszProgID*<br/>
(в) ProgID, связанный с объектом.

*lpszVerIndProgID*<br/>
(в) Версия-независимая ProgID, связанная с объектом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Удаляет регистрацию стандартного класса объекта из системного реестра.

Вызовы метода `UnregisterClassHelper` [UpdateRegistryClass](#updateregistryclass) .

## <a name="ccommoduleunregisterserver"></a><a name="unregisterserver"></a>CComModule::UnregisterServer

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```

### <a name="parameters"></a>Параметры

*bUnRegTypeLib*<br/>
Если true, библиотека типа также не зарегистрирована.

*pCLSID*<br/>
Указывает на CLSID объекта, который должен быть незарегистрированным. Если NULL (значение по умолчанию) все объекты на карте объектов будут незарегистрированы.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

В зависимости от параметра *pCLSID,* отменяемые либо один объект класса, либо все объекты на карте объекта.

`UnregisterServer`будет автоматически вызываться `DLLUnregisterServer` для DLL `WinMain` или для выполнения `/UnregServer` EXE с опцией командной строки.

Ознакомьтесь [с OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) информации о том, как добавить запись на карту объекта.

## <a name="ccommoduleupdateregistryclass"></a><a name="updateregistryclass"></a>CComModule::UpdateRegistryClass

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags,
    BOOL bRegister);

ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    LPCTSTR szDesc,
    DWORD dwFlags,
    BOOL bRegister);
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
CLSID объекта, который должен быть зарегистрирован или незарегистрирован.

*lpszProgID*<br/>
ProgID, связанный с объектом.

*lpszVerIndProgID*<br/>
Версия-независимая ProgID, связанная с объектом.

*nDescID*<br/>
Идентификатор ресурса строки для описания объекта.

*szDesc*<br/>
Строка, содержащая описание объекта.

*dwFlags*<br/>
Определяет модель потока для входа в реестр. Возможные значения: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH или AUTPRXFLAG.

*bРегистрация*<br/>
Указывает, должен ли объект быть зарегистрирован.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если *bRegister* является правдой, этот метод входит в стандартную регистрацию класса объекта в реестре системы.

Если *bRegister* является FALSE, он удаляет регистрацию объекта.

В зависимости от стоимости `UpdateRegistryClass` *bRegister*, звонки либо [RegisterClassHelper](#registerclasshelper) или [UnregisterClassHelper](#unregisterclasshelper).

Указывая [DECLARE_REGISTRY](registry-macros.md#declare_registry) макрос, `UpdateRegistryClass` будет вызываться автоматически при обработке карты объекта.

## <a name="ccommoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CComModule:UpdateRegistryFromResourceD

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
virtual HRESULT UpdateRegistryFromResourceD(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw ();
```

### <a name="parameters"></a>Параметры

*lpszRes*<br/>
(в) Имя ресурса.

*nResID*<br/>
(в) Идентификатор ресурса.

*bРегистрация*<br/>
(в) Указывает, должен ли объект быть зарегистрирован.

*pMapE записи*<br/>
(в) Указатель на значения замены карты, связанные со сменными параметрами скрипта. ATL автоматически `%MODULE%`использует . Для использования дополнительных сменных параметров, см. В противном случае используйте значение NULL по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Запускает скрипт, содержащийся в ресурсе, указанном *lpszRes* или *nResID.*

Если *bRegister* является правдой, этот метод регистрирует объект в системном реестре; в противном случае он отменяет регистры объекта.

Указывая [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) или [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) `UpdateRegistryFromResourceD` макрос, будет автоматически вызываться при обработке карты объекта.

> [!NOTE]
> Чтобы заменить значения замены во время выполнения, не укажите DECLARE_REGISTRY_RESOURCE или DECLARE_REGISTRY_RESOURCEID макрос. Вместо этого создайте `_ATL_REGMAP_ENTRIES` массив структур, где каждая запись содержит переменный заполнитель в паре со значением для замены заполнителя во время выполнения. Затем `UpdateRegistryFromResourceD`позвоните, передавая массив для параметра *pMapE записей.* Это добавляет все значения замены в `_ATL_REGMAP_ENTRIES` структурах на карту замены Регистратора.

> [!NOTE]
> Чтобы статически ссылку на atL реестра компонента (регистратор), см [UpdateRegistryFromResourceS](#updateregistryfromresources).

Для получения дополнительной информации о сменных параметров и сценариев, [см.](../../atl/atl-registry-component-registrar.md)

## <a name="ccommoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CComModule:UpdateRegistryFromРесурсы

По состоянию на ATL 7.0, `CComModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
virtual HRESULT UpdateRegistryFromResourceS(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceS(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Параметры

*lpszRes*<br/>
(в) Имя ресурса.

*nResID*<br/>
(в) Идентификатор ресурса.

*bРегистрация*<br/>
(в) Указывает, должен ли быть зарегистрирован скрипт ресурса.

*pMapE записи*<br/>
(в) Указатель на значения замены карты, связанные со сменными параметрами скрипта. ATL автоматически `%MODULE%`использует . Для использования дополнительных сменных параметров, см. В противном случае используйте значение NULL по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Как и [UpdateRegistryFromResourceD,](#updateregistryfromresourced) за исключением `UpdateRegistryFromResourceS` создает статическую ссылку на компонент реестра ATL (регистратор).

`UpdateRegistryFromResourceS`будет вызываться автоматически при обработке карты объекта `#define _ATL_STATIC_REGISTRY` при условии, что вы добавите к своему *pch.h* *(stdafx.h* в Visual Studio 2017 и ранее).

> [!NOTE]
> Чтобы заменить значения замены во время выполнения, не укажите [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) или [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) макрос. Вместо этого создайте `_ATL_REGMAP_ENTRIES` массив структур, где каждая запись содержит переменный заполнитель в паре со значением для замены заполнителя во время выполнения. Затем `UpdateRegistryFromResourceS`позвоните, передавая массив для параметра *pMapE записей.* Это добавляет все значения замены в `_ATL_REGMAP_ENTRIES` структурах на карту замены Регистратора.

Для получения дополнительной информации о сменных параметров и сценариев, [см.](../../atl/atl-registry-component-registrar.md)

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
