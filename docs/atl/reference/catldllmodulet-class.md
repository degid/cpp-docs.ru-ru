---
title: Класс CAtlDllModuleT
ms.date: 11/04/2016
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
ms.openlocfilehash: e0896a28c24877465213a71ac5207c537c731003
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168775"
---
# <a name="catldllmodulet-class"></a>Класс CAtlDllModuleT

Этот класс представляет модуль для библиотеки DLL.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный `CAtlDllModuleT`от.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlDllModuleT:: CAtlDllModuleT](#catldllmodulet)|Конструктор.|
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlDllModuleT::D Ллканунлоаднов](#dllcanunloadnow)|Проверяет, можно ли выгрузить библиотеку DLL.|
|[CAtlDllModuleT::D Ллжетклассобжект](#dllgetclassobject)|Возвращает фабрику класса.|
|[CAtlDllModuleT::D Ллмаин](#dllmain)|Необязательная точка входа в библиотеку динамической компоновки (DLL).|
|[CAtlDllModuleT::D Ллрегистерсервер](#dllregisterserver)|Добавляет записи в системный реестр для объектов в библиотеке DLL.|
|[CAtlDllModuleT::D Ллунрегистерсервер](#dllunregisterserver)|Удаляет записи в системном реестре для объектов в библиотеке DLL.|
|[CAtlDllModuleT:: Жетклассобжект](#getclassobject)|Возвращает фабрику класса. Вызывается методом [DllGetClassObject](#dllgetclassobject).|

## <a name="remarks"></a>Примечания

`CAtlDllModuleT`представляет модуль для библиотеки динамической компоновки (DLL) и предоставляет функции, используемые всеми проектами DLL. Эта специализация класса [катлмодулет](../../atl/reference/catlmodulet-class.md) включает поддержку регистрации.

Дополнительные сведения о модулях в ATL см. в разделе [Классы модулей ATL](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[катлмодуле](../../atl/reference/catlmodule-class.md)

[катлмодулет](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catldllmoduletcatldllmodulet"></a><a name="catldllmodulet"></a>CAtlDllModuleT:: CAtlDllModuleT

Конструктор.

```cpp
CAtlDllModuleT() throw();
```

## <a name="catldllmoduletcatldllmodulet"></a><a name="dtor"></a>CAtlDllModuleT:: ~ CAtlDllModuleT

Деструктор

```cpp
~CAtlDllModuleT() throw();
```

## <a name="catldllmoduletdllcanunloadnow"></a><a name="dllcanunloadnow"></a>CAtlDllModuleT::D Ллканунлоаднов

Проверяет, можно ли выгрузить библиотеку DLL.

```cpp
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK, если библиотека DLL может быть выгружена, или S_FALSE в случае невозможности.

## <a name="catldllmoduletdllgetclassobject"></a><a name="dllgetclassobject"></a>CAtlDllModuleT::D Ллжетклассобжект

Возвращает фабрику класса.

```cpp
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Параметры

*рклсид*<br/>
Идентификатор CLSID создаваемого объекта.

*riid*<br/>
IID запрашиваемого интерфейса.

*ппв*<br/>
Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс, *ППВ* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="catldllmoduletdllmain"></a><a name="dllmain"></a>CAtlDllModuleT::D Ллмаин

Необязательная точка входа в библиотеку динамической компоновки (DLL).

```cpp
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>Параметры

*Параметр dwReason*<br/>
Если задано значение DLL_PROCESS_ATTACH, вызовы уведомлений DLL_THREAD_ATTACH и DLL_THREAD_DETACH отключаются.

*lpReserved*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Отключение вызовов уведомлений DLL_THREAD_ATTACH и DLL_THREAD_DETACH может быть полезной оптимизацией для многопоточных приложений, которые имеют много библиотек DLL, часто создают и удаляют потоки, а библиотеки DLL не нуждаются в таких уведомлениях на уровне потока, как вложение или отсоединение.

## <a name="catldllmoduletdllregisterserver"></a><a name="dllregisterserver"></a>CAtlDllModuleT::D Ллрегистерсервер

Добавляет записи в системный реестр для объектов в библиотеке DLL.

```cpp
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Параметры

*брегтипелиб*<br/>
Значение TRUE, если библиотека типов должна быть зарегистрирована. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="catldllmoduletdllunregisterserver"></a><a name="dllunregisterserver"></a>CAtlDllModuleT::D Ллунрегистерсервер

Удаляет записи в системном реестре для объектов в библиотеке DLL.

```cpp
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Параметры

*бунрегтипелиб*<br/>
Значение TRUE, если библиотека типов должна быть удалена из реестра. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="catldllmoduletgetclassobject"></a><a name="getclassobject"></a>CAtlDllModuleT:: Жетклассобжект

Создает объект указанного идентификатора CLSID.

```cpp
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Параметры

*рклсид*<br/>
Идентификатор CLSID создаваемого объекта.

*riid*<br/>
IID запрашиваемого интерфейса.

*ппв*<br/>
Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс, *ППВ* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Этот метод вызывается методом [CAtlDllModuleT::D ллжетклассобжект](#dllgetclassobject) и включен для обеспечения обратной совместимости.

## <a name="see-also"></a>См. также

[Класс Катлмодулет](../../atl/reference/catlmodulet-class.md)<br/>
[Класс CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
