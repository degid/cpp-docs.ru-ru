---
title: Глобальные функции регистрации сервера
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
ms.openlocfilehash: 4a84c311e34f1bc37b2f51e2152b6fcf2e46e2a3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835224"
---
# <a name="server-registration-global-functions"></a>Глобальные функции регистрации сервера

Эти функции обеспечивают поддержку регистрации и отмены регистрации объектов сервера в сопоставлении объектов.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, нельзя использовать в приложениях, выполняемых в среда выполнения Windows.

|Имя|Описание|
|-|-|
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Эта функция вызывается для регистрации каждого из объектов в карте объектов.|
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Эта функция вызывается для отмены регистрации каждого из объектов в карте объектов.|
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Эта функция вызывается для регистрации объектов класса.|
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Эта функция вызывается для отмены объектов класса из модуля COM.|
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Эта функция вызывается для получения объекта класса.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlcommoduleregisterserver"></a><a name="atlcommoduleregisterserver"></a> атлкоммодулерегистерсервер

Эта функция вызывается для регистрации каждого из объектов в карте объектов.

```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Параметры

*пкоммодуле*<br/>
Указатель на модуль COM.

*брегтипелиб*<br/>
Значение TRUE, если библиотека типов должна быть зарегистрирована.

*пклсид*<br/>
Указывает на идентификатор CLSID регистрируемого объекта. Если значение равно NULL, будут зарегистрированы все объекты в сопоставлении объектов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

`AtlComModuleRegisterServer` просматривает автоматически сформированную карту объектов ATL и регистрирует каждый объект на карте. Если *пклсид* не равен null, регистрируется только объект, на который ссылается *пклсид* . в противном случае регистрируются все объекты.

Эта функция вызывается методом [катлкоммодуле:: регистерсервер](catlcommodule-class.md#registerserver).

## <a name="atlcommoduleunregisterserver"></a><a name="atlcommoduleunregisterserver"></a> атлкоммодулеунрегистерсервер

Эта функция вызывается для отмены регистрации каждого из объектов в карте объектов.

```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Параметры

*пкоммодуле*<br/>
Указатель на модуль COM.

*бунрегтипелиб*<br/>
Значение TRUE, если библиотека типов должна быть зарегистрирована.

*пклсид*<br/>
Указывает на CLSID объекта, регистрация которого будет отменена. Если значение NULL для всех объектов в сопоставлении объектов будет отменена регистрация.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

`AtlComModuleUnregisterServer` проходит по карте объектов ATL и отменяет регистрацию каждого объекта в сопоставлении. Если *пклсид* не равно null, то отменяется только объект, на который ссылается *пклсид* . в противном случае отменяется регистрация всех объектов.

Эта функция вызывается методом [катлкоммодуле:: унрегистерсервер](catlcommodule-class.md#unregisterserver).

## <a name="atlcommoduleregisterclassobjects"></a><a name="atlcommoduleregisterclassobjects"></a> атлкоммодулерегистерклассобжектс

Эта функция вызывается для регистрации объектов класса.

```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*пкоммодуле*<br/>
Указатель на модуль COM.

*двклсконтекст*<br/>
Задает контекст, в котором будет выполняться объект класса. Возможные значения: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER. Дополнительные сведения см. в разделе [клскткс](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx) .

*dwFlags*<br/>
Определяет типы соединения с объектом класса. Возможные значения: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE. Дополнительные сведения см. в разделе [регклс](/windows/win32/api/combaseapi/ne-combaseapi-regcls) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используется [CComModule:: регистерклассобжектс](ccommodule-class.md#registerclassobjects) (устарела в ATL 7,0) и [CAtlExeModuleT:: регистерклассобжектс](catlexemodulet-class.md#registerclassobjects).

## <a name="atlcommodulerevokeclassobjects"></a><a name="atlcommodulerevokeclassobjects"></a> атлкоммодулеревокеклассобжектс

Эта функция вызывается для удаления фабрики или фабрик класса из таблицы запущенных объектов.

```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```

### <a name="parameters"></a>Параметры

*пкоммодуле*<br/>
Указатель на модуль COM.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используется [CComModule:: ревокеклассобжектс](ccommodule-class.md#revokeclassobjects) (устарела в ATL 7,0) и [CAtlExeModuleT:: ревокеклассобжектс](catlexemodulet-class.md#revokeclassobjects).

## <a name="atlcommodulegetclassobject"></a><a name="atlcommodulegetclassobject"></a> атлкоммодулежетклассобжект

Эта функция вызывается для получения фабрики класса.

```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```

### <a name="parameters"></a>Параметры

*пкоммодуле*<br/>
Указатель на модуль COM.

*рклсид*<br/>
Идентификатор CLSID создаваемого объекта.

*riid*<br/>
IID запрашиваемого интерфейса.

*ппв*<br/>
Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс, *ППВ* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используется [CComModule:: жетклассобжект](ccommodule-class.md#getclassobject) (устарела в ATL 7,0) и [CAtlDllModuleT:: жетклассобжект](catldllmodulet-class.md#getclassobject).

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
