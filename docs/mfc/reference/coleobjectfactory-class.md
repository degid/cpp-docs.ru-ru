---
title: Класс COleObjectFactory
ms.date: 11/04/2016
f1_keywords:
- COleObjectFactory
- AFXDISP/COleObjectFactory
- AFXDISP/COleObjectFactory::COleObjectFactory
- AFXDISP/COleObjectFactory::GetClassID
- AFXDISP/COleObjectFactory::IsLicenseValid
- AFXDISP/COleObjectFactory::IsRegistered
- AFXDISP/COleObjectFactory::Register
- AFXDISP/COleObjectFactory::RegisterAll
- AFXDISP/COleObjectFactory::Revoke
- AFXDISP/COleObjectFactory::RevokeAll
- AFXDISP/COleObjectFactory::UnregisterAll
- AFXDISP/COleObjectFactory::UpdateRegistry
- AFXDISP/COleObjectFactory::UpdateRegistryAll
- AFXDISP/COleObjectFactory::GetLicenseKey
- AFXDISP/COleObjectFactory::OnCreateObject
- AFXDISP/COleObjectFactory::VerifyLicenseKey
- AFXDISP/COleObjectFactory::VerifyUserLicense
helpviewer_keywords:
- COleObjectFactory [MFC], COleObjectFactory
- COleObjectFactory [MFC], GetClassID
- COleObjectFactory [MFC], IsLicenseValid
- COleObjectFactory [MFC], IsRegistered
- COleObjectFactory [MFC], Register
- COleObjectFactory [MFC], RegisterAll
- COleObjectFactory [MFC], Revoke
- COleObjectFactory [MFC], RevokeAll
- COleObjectFactory [MFC], UnregisterAll
- COleObjectFactory [MFC], UpdateRegistry
- COleObjectFactory [MFC], UpdateRegistryAll
- COleObjectFactory [MFC], GetLicenseKey
- COleObjectFactory [MFC], OnCreateObject
- COleObjectFactory [MFC], VerifyLicenseKey
- COleObjectFactory [MFC], VerifyUserLicense
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
ms.openlocfilehash: 165ba7c1918c3ccc5d5d7e0bc067fba86678a3e7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753802"
---
# <a name="coleobjectfactory-class"></a>Класс COleObjectFactory

Реализует фабрику класса OLE, которая создает OLE-объекты, такие как серверы, объекты автоматизации и документы.

## <a name="syntax"></a>Синтаксис

```
class COleObjectFactory : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeObjectFactory::COleObjectFactory](#coleobjectfactory)|Формирует объект `COleObjectFactory`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeObjectFactory::GetClassID](#getclassid)|Возвращает идентификатор класса OLE объектов, которые создает эта фабрика.|
|[ColeObjectFactory::IsLicenseValid](#islicensevalid)|Определяет, действительна ли лицензия управления.|
|[ColeObjectFactory::Зарегистрировано](#isregistered)|Указывает, зарегистрирована ли фабрика объектов с системой OL LLL.|
|[ColeObjectFactory::Регистрация](#register)|Регистрирует этот объект фабрики с системой OLE DLLs.|
|[ColeObjectFactory:RegisterAll](#registerall)|Регистрирует все объекты приложения с помощью dLL системы OLE.|
|[ColeObjectFactory::Revoke](#revoke)|Отменяет регистрацию этого объекта фабрики с помощью системы OL DLLs.|
|[ColeObjectFactory::RevokeAll](#revokeall)|Отменяет регистрацию объектов приложения с помощью системы OLL.|
|[ColeObjectFactory::UnregisterAll](#unregisterall)|Отрегистрирует все заводы объектов приложения.|
|[ColeObjectFactory::Update](#updateregistry)|Регистрирует этот объект завода с реестром системы OLE.|
|[ColeObjectFactory::UpdateRegistryAll](#updateregistryall)|Регистрирует все объекты приложения заводы с реестром системы OLE.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[ColeObjectFactory::GetLicenseKey](#getlicensekey)|Запрашивает уникальный ключ от DLL управления.|
|[ColeObjectFactory::OnCreateObject](#oncreateobject)|Вызывается фреймворком для создания нового объекта типа этой фабрики.|
|[ColeObjectFactory::VerifyLicenseKey](#verifylicensekey)|Проверяется, что ключ, встроенный в элемент управления, соответствует ключу, встроенного в контейнер.|
|[ColeObjectFactory::VerifyUserLicense](#verifyuserlicense)|Проверяется, что элемент управления лицензирован для использования в проектно-сохранном времени.|

## <a name="remarks"></a>Примечания

Класс `COleObjectFactory` имеет функции члена для выполнения следующих функций:

- Управление регистрацией объектов.

- Обновление регистра системы OLE, а также регистрация времени выполнения, которая информирует OLE о том, что объекты работают и готовы к приему сообщений.

- Обеспечение лицензирования путем ограничения использования элемента управления лицензированным разработчикам во время проектирования и лицензированных приложений во время выполнения.

- Регистрация заводов контрольных объектов в реестре систем OLE.

Для получения дополнительной информации о создании объектов смотрите статьи [Data Objects and Data Sources (OLE)](../../mfc/data-objects-and-data-sources-ole.md) и Data Objects and Data [Sources: Creation and Destruction](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Подробнее о регистрации читайте в статье [Регистрация](../../mfc/registration.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleObjectFactory`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="coleobjectfactorycoleobjectfactory"></a><a name="coleobjectfactory"></a>ColeObjectFactory::COleObjectFactory

Строит `COleObjectFactory` объект, инициирует его как незарегистрированный объект завода, и добавляет его в список заводов.

```
COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    LPCTSTR lpszProgID);

COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    int nFlags,
    LPCTSTR lpszProgID);
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
Ссылка на идентификатор класса OLE, который представляет эта фабрика объектов.

*pRuntimeClass*<br/>
Указатель на класс времени выполнения объектов C-класса, который может создать эта фабрика.

*bMultiInstance*<br/>
Указывает, может ли один экземпляр приложения поддерживать несколько моментций. Если true, несколько экземпляров приложения запускаются для каждого запроса на создание объекта.

*nФлаги*<br/>
Содержит один или несколько из следующих флагов:

- `afxRegDefault`Устанавливает модель резьбы в ThreadingModel-Квартира.

- `afxRegInsertable`Позволяет элементуправления отображаться в диалоговом окне **объекта вставки** для объектов OLE.

- `afxRegApartmentThreading`Устанавливает модель резьбы в реестре на ThreadingModel-Квартира.

- `afxRegFreeThreading`Устанавливает модель потоков в реестре на ThreadingModel-Free.

   Вы можете объединить `afxRegApartmentThreading` два `afxRegFreeThreading` флага и установить ThreadingModel-Оба. Подробнее о регистрации моделей потоков читайте в [см. InprocServer32.](/windows/win32/com/inprocserver32)

*lpszProgID*<br/>
Указатель на строку, содержащую идентификатор словесной программы, например "Microsoft Excel".

### <a name="remarks"></a>Примечания

Однако для использования объекта необходимо зарегистрировать его.

Для получения дополнительной информации [см. ключ CLSID](/windows/win32/com/clsid-key-hklm) в SDK Windows.

## <a name="coleobjectfactorygetclassid"></a><a name="getclassid"></a>ColeObjectFactory::GetClassID

Возвращает ссылку на идентификатор класса OLE, который представляет эта фабрика.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на идентификатор класса OLE, который представляет эта фабрика.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см. ключ CLSID](/windows/win32/com/clsid-key-hklm) в SDK Windows.

## <a name="coleobjectfactorygetlicensekey"></a><a name="getlicensekey"></a>ColeObjectFactory::GetLicenseKey

Запрашивает уникальный лицензионный ключ от DLL управления и хранит его в BSTR, на который указывает *pbstrKey.*

```
virtual BOOL GetLicenseKey(
    DWORD dwReserved,
    BSTR* pbstrKey);
```

### <a name="parameters"></a>Параметры

*dwReserved*<br/>
Зарезервировано для последующего использования.

*pbstrKey*<br/>
Указатель на BSTR, который будет хранить ключ лицензии.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если строка с ключом лицензии не является NULL; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация этой функции по умолчанию возвращает 0 и ничего не хранит в BSTR. Если вы используете MFC ActiveX ControlWizard для создания проекта, ControlWizard поставляет переопределение, которое получает ключ лицензии управления.

## <a name="coleobjectfactoryislicensevalid"></a><a name="islicensevalid"></a>ColeObjectFactory::IsLicenseValid

Определяет, действительна ли лицензия управления.

```
BOOL IsLicenseValid();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если успех; в противном случае ложно.

## <a name="coleobjectfactoryisregistered"></a><a name="isregistered"></a>ColeObjectFactory::Зарегистрировано

Возвращает ненулевое значение, если фабрика зарегистрирована с DLL системы OLE.

```
virtual BOOL IsRegistered() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если завод зарегистрирован; в противном случае 0.

## <a name="coleobjectfactoryoncreateobject"></a><a name="oncreateobject"></a>ColeObjectFactory::OnCreateObject

Вызывается инфраструктурой для создания нового объекта.

```
virtual CCmdTarget* OnCreateObject();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на созданный объект. Он может выбросить исключение памяти, если он не удается.

### <a name="remarks"></a>Примечания

Переопределить эту функцию, чтобы создать объект из чего-то другого, чем [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) передается конструктору.

## <a name="coleobjectfactoryregister"></a><a name="register"></a>ColeObjectFactory::Регистрация

Регистрирует этот объект фабрики с системой OLE DLLs.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если завод успешно зарегистрирован; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается [CWinApp::InitInstance,](../../mfc/reference/cwinapp-class.md#initinstance) когда приложение запущено.

## <a name="coleobjectfactoryregisterall"></a><a name="registerall"></a>ColeObjectFactory:RegisterAll

Регистрирует все объекты приложения с помощью DLL системы OLE.

```
static BOOL PASCAL RegisterAll();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если заводы успешно зарегистрированы; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается [CWinApp::InitInstance,](../../mfc/reference/cwinapp-class.md#initinstance) когда приложение запущено.

## <a name="coleobjectfactoryrevoke"></a><a name="revoke"></a>ColeObjectFactory::Revoke

Отменяет регистрацию этого объекта фабрики с помощью системы OL DLLs.

```cpp
void Revoke();
```

### <a name="remarks"></a>Примечания

Платформа вызывает эту функцию автоматически до завершения приложения. При необходимости позвоните по номеру из переопределения [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).

## <a name="coleobjectfactoryrevokeall"></a><a name="revokeall"></a>ColeObjectFactory::RevokeAll

Отменяет регистрацию всех объектов приложения с помощью системы OLL.

```
static void PASCAL RevokeAll();
```

### <a name="remarks"></a>Примечания

Платформа вызывает эту функцию автоматически до завершения приложения. При необходимости позвоните по номеру из переопределения [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).

## <a name="coleobjectfactoryunregisterall"></a><a name="unregisterall"></a>ColeObjectFactory::UnregisterAll

Отрегистрирует все заводы объектов приложения.

```
static BOOL PASCAL UnregisterAll();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

## <a name="coleobjectfactoryupdateregistry"></a><a name="updateregistry"></a>ColeObjectFactory::Update

Регистрирует все объекты приложения заводы с реестром системы OLE.

```cpp
void UpdateRegistry(LPCTSTR lpszProgID = NULL);
virtual BOOL UpdateRegistry(BOOL bRegister);
```

### <a name="parameters"></a>Параметры

*lpszProgID*<br/>
Указатель на строку, содержащую идентификатор читаемой для человека программы, например "Excel.Document.5".

*bРегистрация*<br/>
Определяет, должна ли быть зарегистрирована фабрика объектов контрольного класса.

### <a name="remarks"></a>Примечания

Краткое обсуждение двух форм для этой функции следует:

- **Обновление** `lpszProgID` **()** Регистрирует этот объект завода с реестром системы OLE. Эта функция обычно вызывается [CWinApp::InitInstance,](../../mfc/reference/cwinapp-class.md#initinstance) когда приложение запущено.

- **Обновление** `bRegister` **()** Эта форма функции переизмещена. Если *bRegister* является правдой, эта функция регистрирует класс управления системным реестром. В противном случае он отменяет класс.

   Если вы используете MFC ActiveX ControlWizard для создания проекта, ControlWizard поставляет переопределение этой чистой виртуальной функции.

## <a name="coleobjectfactoryupdateregistryall"></a><a name="updateregistryall"></a>ColeObjectFactory::UpdateRegistryAll

Регистрирует все объекты приложения заводы с реестром системы OLE.

```
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Параметры

*bРегистрация*<br/>
Определяет, должна ли быть зарегистрирована фабрика объектов контрольного класса.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если заводы успешно обновляются; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается [CWinApp::InitInstance,](../../mfc/reference/cwinapp-class.md#initinstance) когда приложение запущено.

## <a name="coleobjectfactoryverifylicensekey"></a><a name="verifylicensekey"></a>ColeObjectFactory::VerifyLicenseKey

Проверяется, что контейнер имеет лицензию на использование управления OLE.

```
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```

### <a name="parameters"></a>Параметры

*bstrKey*<br/>
BSTR, хранящей версию лицензионной строки контейнера.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если лицензия времени выполнения действительна; в противном случае 0.

### <a name="remarks"></a>Примечания

Версия по умолчанию вызывает [GetLicenseKey,](#getlicensekey) чтобы получить копию строки лицензии управления и сравнивает ее со строкой в *bstrKey.* Если две строки совпадают, функция возвращает ненулевое значение; в противном случае он возвращает 0.

Эту функцию можно переопределить, чтобы обеспечить индивидуальную проверку лицензии.

Функция [VerifyUserLicense](#verifyuserlicense) проверяет лицензию времени проектирования.

## <a name="coleobjectfactoryverifyuserlicense"></a><a name="verifyuserlicense"></a>ColeObjectFactory::VerifyUserLicense

Проверяет лицензию на проектирование для управления OLE.

```
virtual BOOL VerifyUserLicense();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если лицензия времени проектирования действительна; в противном случае 0.

## <a name="see-also"></a>См. также раздел

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)
