---
title: Класс Катлкоммодуле
ms.date: 11/04/2016
f1_keywords:
- CAtlComModule
- ATLBASE/ATL::CAtlComModule
- ATLBASE/ATL::CAtlComModule::CAtlComModule
- ATLBASE/ATL::CAtlComModule::RegisterServer
- ATLBASE/ATL::CAtlComModule::RegisterTypeLib
- ATLBASE/ATL::CAtlComModule::UnregisterServer
- ATLBASE/ATL::CAtlComModule::UnRegisterTypeLib
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
ms.openlocfilehash: 4b8c98630b27c35ed6a7e32318c6ebad8a82a5c5
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168835"
---
# <a name="catlcommodule-class"></a>Класс Катлкоммодуле

Этот класс реализует модуль COM-сервера.

## <a name="syntax"></a>Синтаксис

```cpp
class CAtlComModule : public _ATL_COM_MODULE
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Катлкоммодуле:: Катлкоммодуле](#catlcommodule)|Конструктор.|
|[Катлкоммодуле:: ~ Катлкоммодуле](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Катлкоммодуле:: Регистерсервер](#registerserver)|Вызовите этот метод, чтобы обновить системный реестр для каждого объекта в сопоставлении объектов.|
|[Катлкоммодуле:: Регистертипелиб](#registertypelib)|Вызовите этот метод, чтобы зарегистрировать библиотеку типов.|
|[Катлкоммодуле:: Унрегистерсервер](#unregisterserver)|Вызовите этот метод, чтобы отменить регистрацию каждого объекта в сопоставлении объектов.|
|[Катлкоммодуле:: Унрегистертипелиб](#unregistertypelib)|Вызовите этот метод, чтобы отменить регистрацию библиотеки типов.|

## <a name="remarks"></a>Примечания

`CAtlComModule`реализует модуль COM-сервера, позволяющий клиенту обращаться к компонентам модуля.

Этот класс заменяет устаревший класс [CComModule](../../atl/reference/ccommodule-class.md) , используемый в более ранних версиях ATL. Дополнительные сведения см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)

`CAtlComModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catlcommodulecatlcommodule"></a><a name="catlcommodule"></a>Катлкоммодуле:: Катлкоммодуле

Конструктор.

```cpp
CAtlComModule() throw();
```

### <a name="remarks"></a>Примечания

Инициализирует модуль.

## <a name="catlcommodulecatlcommodule"></a><a name="dtor"></a>Катлкоммодуле:: ~ Катлкоммодуле

Деструктор

```cpp
~CAtlComModule();
```

### <a name="remarks"></a>Примечания

Освобождает все фабрики классов.

## <a name="catlcommoduleregisterserver"></a><a name="registerserver"></a>Катлкоммодуле:: Регистерсервер

Вызовите этот метод, чтобы обновить системный реестр для каждого объекта в сопоставлении объектов.

```cpp
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Параметры

*брегтипелиб*<br/>
Значение TRUE, если библиотека типов должна быть зарегистрирована. Значение по умолчанию — FALSE.

*пклсид*<br/>
Указывает на идентификатор CLSID регистрируемого объекта. При значении NULL (значение по умолчанию) будут зарегистрированы все объекты в сопоставлении объектов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает глобальную функцию [атлкоммодулерегистерсервер](server-registration-global-functions.md#atlcommoduleregisterserver).

## <a name="catlcommoduleregistertypelib"></a><a name="registertypelib"></a>Катлкоммодуле:: Регистертипелиб

Вызовите этот метод, чтобы зарегистрировать библиотеку типов.

```cpp
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```

### <a name="parameters"></a>Параметры

*лпсзиндекс*<br/>
Строка в формате "\\\n", где N — это целочисленный индекс ресурса TypeLib.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Добавляет сведения о библиотеке типов в системный реестр. Если экземпляр модуля содержит несколько библиотек типов, используйте первую версию этого метода, чтобы указать, какую библиотеку типов следует использовать.

## <a name="catlcommoduleunregisterserver"></a><a name="unregisterserver"></a>Катлкоммодуле:: Унрегистерсервер

Вызовите этот метод, чтобы отменить регистрацию каждого объекта в сопоставлении объектов.

```cpp
HRESULT UnregisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Параметры

*брегтипелиб*<br/>
Значение TRUE, если требуется отменить регистрацию библиотеки типов. Значение по умолчанию — FALSE.

*пклсид*<br/>
Указывает на CLSID объекта, регистрация которого будет отменена. Если NULL (значение по умолчанию), регистрация всех объектов в сопоставлении объектов будет отменена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает глобальную функцию [атлкоммодулеунрегистерсервер](server-registration-global-functions.md#atlcommoduleunregisterserver).

## <a name="catlcommoduleunregistertypelib"></a><a name="unregistertypelib"></a>Катлкоммодуле:: Унрегистертипелиб

Вызовите этот метод, чтобы отменить регистрацию библиотеки типов.

```cpp
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```

### <a name="parameters"></a>Параметры

*лпсзиндекс*<br/>
Строка в формате "\\\n", где N — это целочисленный индекс ресурса TypeLib.

### <a name="remarks"></a>Примечания

Удаляет сведения о библиотеке типов из системного реестра. Если экземпляр модуля содержит несколько библиотек типов, используйте первую версию этого метода, чтобы указать, какую библиотеку типов следует использовать.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="see-also"></a>См. также

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
