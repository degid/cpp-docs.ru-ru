---
title: Глобальные функции реестра и библиотеки типов
ms.date: 03/27/2019
f1_keywords:
- atlbase/ATL::AtlGetPerUserRegistration
- afxpriv/ATL::AfxRegCreateKey
- afxpriv/ATL::AfxRegDeleteKey
- atlbase/ATL::AtlRegisterTypeLib
- afxpriv/ATL::AfxRegOpenKey
- afxpriv/ATL::AfxRegOpenKeyEx
- afxdisp/ATL::AfxUnregisterPreviewHandler
- atlbase/ATL::AtlSetPerUserRegistration
- atlbase/ATL::AtlUnRegisterTypeLib
- atlbase/ATL::AtlLoadTypeLib
- atlbase/ATL::AtlUpdateRegistryFromResourceD
- atlbase/ATL::RegistryDataExchange
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
ms.openlocfilehash: 0f29f8cac62a7452781e8fde697cdf992db00b8c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834622"
---
# <a name="registry-and-typelib-global-functions"></a>Глобальные функции реестра и библиотеки типов

Эти функции обеспечивают поддержку загрузки и регистрации библиотеки типов.

> [!IMPORTANT]
> Функции, перечисленные в следующих таблицах, нельзя использовать в приложениях, выполняемых в среда выполнения Windows.

|Имя|Описание|
|-|-|
|[AfxRegCreateKey](#afxregcreatekey)|Создает указанный раздел реестра.|
|[AfxRegDeleteKey](#afxregdeletekey)|Удаляет указанный раздел реестра.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|Вспомогательный метод для регистрации обработчика просмотра.|
|[афксунрегистерпревиевхандлер](#afxunregisterpreviewhandler)| Вспомогательный метод для отмены регистрации обработчика просмотра. |
|[AtlRegisterTypeLib](#atlregistertypelib)|Эта функция вызывается для регистрации библиотеки типов.|
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Эта функция вызывается для отмены регистрации библиотеки типов|
|[AfxRegOpenKey](#afxregopenkey)|Открывает указанный раздел реестра.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|Открывает указанный раздел реестра.|
|[AtlLoadTypeLib](#atlloadtypelib)|Эта функция вызывается для загрузки библиотеки типов.|
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Эта функция вызывается для обновления реестра из предоставленного ресурса.|
|[RegistryDataExchange](#registrydataexchange)|Эта функция вызывается для чтения из системного реестра или записи в него. Вызывается [макросами обмена данными реестра](../../atl/reference/registry-data-exchange-macros.md).|

Эти функции определяют, какой узел в реестре использует программа для хранения информации.

|Имя|Описание|
|-|-|
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Получает значение, указывающее, перенаправляет ли приложение доступ к реестру к узлу **HKEY_CURRENT_USER** ( **HKCU**).|
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Определяет, будет ли приложение перенаправлять доступ к реестру на узел **HKEY_CURRENT_USER** ( **HKCU**).|

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a> атлжетперусеррегистратион

Используйте эту функцию, чтобы определить, будет ли приложение перенаправлять доступ к реестру на узел **HKEY_CURRENT_USER** (**HKCU**).

### <a name="syntax"></a>Синтаксис

```
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);
```

### <a name="parameters"></a>Параметры

*пенаблед*<br/>
заполняет Значение TRUE указывает, что данные реестра направляются на узел **HKCU** ; Значение FALSE указывает, что приложение записывает сведения о реестре в узел по умолчанию. Узел по умолчанию — **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>Возвращаемое значение

S_OK, если метод выполнен успешно, в противном случае — код ошибки HRESULT при возникновении ошибки.

### <a name="remarks"></a>Примечания

По умолчанию перенаправление реестра отключено. Если этот параметр включен, доступ к реестру перенаправляется в **HKEY_CURRENT_USER \софтваре\классес**.

Перенаправление не является глобальным. Это перенаправление реестра влияет только на платформы MFC и ATL.

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="afxregcreatekey"></a><a name="afxregcreatekey"></a> афксрегкреатекэй

Создает указанный раздел реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Маркер открытого раздела реестра.

*лпсубкэй*<br/>
Имя ключа, которое открывается или создается этой функцией.

*фкресулт*<br/>
Указатель на переменную, которая получает маркер для открытого или созданного ключа.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение будет ERROR_SUCCESS. Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в файле Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxregdeletekey"></a><a name="afxregdeletekey"></a> афксрегделетекэй

Удаляет указанный раздел реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Маркер открытого раздела реестра.

*лпсубкэй*<br/>
Имя удаляемого ключа.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение будет ERROR_SUCCESS. Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в файле Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxregisterpreviewhandler"></a>

Вспомогательный метод для регистрации обработчика просмотра.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);
```

### <a name="parameters"></a>Параметры

*лпсзклсид*<br/>
Указывает CLSID обработчика.

*лпсзшорттипенаме*<br/>
Указывает идентификатор ProgID обработчика.

*лпсзфилтерекст*<br/>
Указывает расширение файла, зарегистрированное в этом обработчике.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="atlregistertypelib"></a><a name="atlregistertypelib"></a> атлрегистертипелиб

Эта функция вызывается для регистрации библиотеки типов.

```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Параметры

*хинсттипелиб*<br/>
Маркер для экземпляра модуля.

*лпсзиндекс*<br/>
Строка в формате " \\ \n", где N — это целочисленный индекс ресурса библиотеки типов. Может иметь значение NULL, если индекс не требуется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используется [атлкоммодулеунрегистерсервер](server-registration-global-functions.md#atlcommoduleunregisterserver) и [Катлкоммодуле:: регистертипелиб](../../atl/reference/catlcommodule-class.md#registertypelib).

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="afxregopenkey"></a><a name="afxregopenkey"></a> афксрегопенкэй

Открывает указанный раздел реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Маркер открытого раздела реестра.

*лпсубкэй*<br/>
Имя ключа, которое открывается или создается этой функцией.

*фкресулт*<br/>
Указатель на переменную, которая получает маркер для созданного ключа.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение будет ERROR_SUCCESS. Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в файле Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxregopenkeyex"></a><a name="afxregopenkeyex"></a> афксрегопенкэйекс

Открывает указанный раздел реестра.

### <a name="syntax"></a>Синтаксис

```
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Маркер открытого раздела реестра.

*лпсубкэй*<br/>
Имя ключа, которое открывается или создается этой функцией.

*улоптионс*<br/>
Этот параметр зарезервирован и должен быть равен нулю.

*самдесиред*<br/>
Маска, указывающая необходимые права доступа к ключу.

*фкресулт*<br/>
Указатель на переменную, которая получает маркер открытого ключа.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение будет ERROR_SUCCESS. Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в файле Winerror.h.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxunregisterpreviewhandler"></a><a name="afxunregisterpreviewhandler"></a> афксунрегистерпревиевхандлер

Вспомогательный метод для отмены регистрации обработчика просмотра.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);
```

### <a name="parameters"></a>Параметры

*лпсзклсид*<br/>
Указывает CLSID регистрируемого обработчика.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a> атлсетперусеррегистратион

Определяет, будет ли приложение перенаправлять доступ к реестру на узел **HKEY_CURRENT_USER** (**HKCU**).

### <a name="syntax"></a>Синтаксис

```
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
окне Значение TRUE указывает, что данные реестра направляются на узел **HKCU** ; Значение FALSE указывает, что приложение записывает сведения о реестре в узел по умолчанию. Узел по умолчанию — **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>Возвращаемое значение

S_OK, если метод выполнен успешно, в противном случае — код ошибки HRESULT при возникновении ошибки.

### <a name="remarks"></a>Примечания

По умолчанию перенаправление реестра отключено. Если этот параметр включен, доступ к реестру перенаправляется в **HKEY_CURRENT_USER \софтваре\классес**.

Перенаправление не является глобальным. Это перенаправление реестра влияет только на платформы MFC и ATL.

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlunregistertypelib"></a><a name="atlunregistertypelib"></a> атлунрегистертипелиб

Эта функция вызывается для отмены регистрации библиотеки типов.

### <a name="syntax"></a>Синтаксис

```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Параметры

*хинсттипелиб*<br/>
Маркер для экземпляра модуля.

*лпсзиндекс*<br/>
Строка в формате " \\ \n", где N — это целочисленный индекс ресурса библиотеки типов. Может иметь значение NULL, если индекс не требуется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используется [катлкоммодуле:: унрегистертипелиб](../../atl/reference/catlcommodule-class.md#unregistertypelib) и [атлкоммодулеунрегистерсервер](server-registration-global-functions.md#atlcommoduleunregisterserver).

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlloadtypelib"></a><a name="atlloadtypelib"></a> атллоадтипелиб

Эта функция вызывается для загрузки библиотеки типов.

### <a name="syntax"></a>Синтаксис

```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```

### <a name="parameters"></a>Параметры

*хинсттипелиб*<br/>
Обработчик для модуля, связанного с библиотекой типов.

*лпсзиндекс*<br/>
Строка в формате " \\ \n", где N — это целочисленный индекс ресурса библиотеки типов. Может иметь значение NULL, если индекс не требуется.

*пбстрпас*<br/>
При успешном возвращении содержит полный путь к модулю, связанному с библиотекой типов.

*пптипелиб*<br/>
При успешном возвращении содержит указатель на указатель на загруженную библиотеку типов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция используется [атлрегистертипелиб](#atlregistertypelib) и [атлунрегистертипелиб](#atlunregistertypelib).

## <a name="atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a> атлупдатерегистрифромресаурцед

Эта функция объявлена устаревшей Visual Studio 2013 и удалена в Visual Studio 2015.

```
<removed>
```

## <a name="registrydataexchange"></a><a name="registrydataexchange"></a> регистридатаексчанже

Эта функция вызывается для чтения из системного реестра или записи в него.

### <a name="syntax"></a>Синтаксис

```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```

### <a name="parameters"></a>Параметры

*Лутор*<br/>
Указатель на текущий объект.

*рдксоп*<br/>
Значение перечисления, указывающее, какую операцию должна выполнить функция. Допустимые значения см. в таблице в разделе "Примечания".

*питем*<br/>
Указатель на данные, которые должны быть считаны или записаны в реестр. Данные также могут представлять ключ, который необходимо удалить из реестра. Значение по умолчанию — NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Макросы [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) и [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) расширяются до функции, которая вызывает `RegistryDataExchange` .

Возможные значения перечисления, указывающие операцию, которую должна выполнить функция, показаны в следующей таблице.

|Значение перечисления|Операция|
|----------------|---------------|
|ереадфромрег|Чтение данных из реестра.|
|евритеторег|Запись данных в реестр.|
|еделетефромрег|Удалите ключ из реестра.|

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="see-also"></a>См. также

[Функции](atl-functions.md)<br/>
[Макросы обмена данными в реестре](registry-data-exchange-macros.md)
