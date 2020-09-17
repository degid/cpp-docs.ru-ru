---
title: Глобальные функции безопасности
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::AtlGetDacl
- atlsecurity/ATL::AtlSetDacl
- atlsecurity/ATL::AtlGetGroupSid
- atlsecurity/ATL::AtlSetGroupSid
- atlsecurity/ATL::AtlGetOwnerSid
- atlsecurity/ATL::AtlSetOwnerSid
- atlsecurity/ATL::AtlGetSacl
- atlsecurity/ATL::AtlSetSacl
- atlsecurity/ATL::AtlGetSecurityDescriptor
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
ms.openlocfilehash: 0b42fe10ef1de517677b35a9fe54d0c6a04ff748
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834496"
---
# <a name="security-global-functions"></a>Глобальные функции безопасности

Эти функции обеспечивают поддержку изменения идентификаторов безопасности и объектов ACL.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, нельзя использовать в приложениях, выполняемых в среда выполнения Windows.

|Имя|Описание|
|-|-|
|[AtlGetDacl](#atlgetdacl)|Вызывайте эту функцию для получения данных списка управления доступом на уровне пользователя (DACL) указанного объекта.|
|[AtlSetDacl](#atlsetdacl)|Вызывайте эту функцию для задания данных списка управления доступом на уровне пользователя (DACL) указанного объекта.|
|[AtlGetGroupSid](#atlgetgroupsid)|Вызывайте эту функцию для извлечения идентификатора безопасности (SID) группы для объекта.|
|[AtlSetGroupSid](#atlsetgroupsid)|Вызывайте эту функцию для задания идентификатора безопасности (SID) группы для объекта.|
|[AtlGetOwnerSid](#atlgetownersid)|Вызывайте эту функцию для извлечения идентификатора безопасности (SID) владельца для объекта.|
|[AtlSetOwnerSid](#atlsetownersid)|Вызывайте эту функцию для задания идентификатора безопасности (SID) владельца для объекта.|
|[AtlGetSacl](#atlgetsacl)|Вызывайте эту функцию для получения данных системного списка управления доступом (SACL) указанного объекта.|
|[AtlSetSacl](#atlsetsacl)|Вызывайте эту функцию для задания данных системного списка управления доступом (SACL) указанного объекта.|
|[AtlGetSecurityDescriptor](#atlgetsecuritydescriptor)|Вызывайте эту функцию для извлечения дескриптора безопасности заданного объекта.|

## <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="atlgetdacl"></a><a name="atlgetdacl"></a> атлжетдакл

Вызывайте эту функцию для получения данных списка управления доступом на уровне пользователя (DACL) указанного объекта.

> [!IMPORTANT]
> Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
Обработчик объекта, для которого необходимо получить сведения о безопасности.

*ObjectType*<br/>
Задает значение из перечисления [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) , которое указывает тип объекта, определяемого параметром *хобжект* .

*пдакл*<br/>
Указатель на объект DACL, который будет содержать полученные сведения о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

В отладочных сборках возникнет ошибка утверждения, если *хобжект* или *пдакл* являются недопустимыми.

## <a name="atlsetdacl"></a><a name="atlsetdacl"></a> атлсетдакл

Вызывайте эту функцию для задания данных списка управления доступом на уровне пользователя (DACL) указанного объекта.

> [!IMPORTANT]
> Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
Обработчик объекта, для которого задаются сведения о безопасности.

*ObjectType*<br/>
Задает значение из перечисления [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) , которое указывает тип объекта, определяемого параметром *хобжект* .

*рдакл*<br/>
Список DACL, содержащий новые сведения о безопасности.

*двинхеританцефловконтрол*<br/>
Управление потоком наследования. Это значение может быть равно 0 (по умолчанию), PROTECTED_DACL_SECURITY_INFORMATION или UNPROTECTED_DACL_SECURITY_INFORMATION.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

В отладочных сборках возникнет ошибка утверждения, если *хобжект* является недопустимым или если *двинхеританцефловконтрол* не является одним из трех разрешенных значений.

### <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="atlgetgroupsid"></a><a name="atlgetgroupsid"></a> атлжетграупсид

Вызывайте эту функцию для извлечения идентификатора безопасности (SID) группы для объекта.

> [!IMPORTANT]
> Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
Обработчик объекта, из которого извлекаются сведения о безопасности.

*ObjectType*<br/>
Задает значение из перечисления [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) , которое указывает тип объекта, определяемого параметром *хобжект* .

*Пустой pSid*<br/>
Указатель на `CSid` объект, который будет содержать новые сведения о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="atlsetgroupsid"></a><a name="atlsetgroupsid"></a> атлсетграупсид

Вызывайте эту функцию для задания идентификатора безопасности (SID) группы для объекта.

> [!IMPORTANT]
> Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
Обработчик объекта, для которого задаются сведения о безопасности.

*ObjectType*<br/>
Задает значение из перечисления [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) , которое указывает тип объекта, определяемого параметром *хобжект* .

*рсид*<br/>
`CSid`Объект, содержащий новые сведения о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="atlgetownersid"></a><a name="atlgetownersid"></a> атлжетовнерсид

Вызывайте эту функцию для извлечения идентификатора безопасности (SID) владельца для объекта.

> [!IMPORTANT]
> Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
Обработчик объекта, из которого извлекаются сведения о безопасности.

*ObjectType*<br/>
Задает значение из перечисления [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) , которое указывает тип объекта, определяемого параметром *хобжект* .

*Пустой pSid*<br/>
Указатель на `CSid` объект, который будет содержать новые сведения о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="atlsetownersid"></a><a name="atlsetownersid"></a> атлсетовнерсид

Вызывайте эту функцию для задания идентификатора безопасности (SID) владельца для объекта.

> [!IMPORTANT]
> Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
Обработчик объекта, для которого задаются сведения о безопасности.

*ObjectType*<br/>
Задает значение из перечисления [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) , которое указывает тип объекта, определяемого параметром *хобжект* .

*рсид*<br/>
`CSid`Объект, содержащий новые сведения о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="atlgetsacl"></a><a name="atlgetsacl"></a> атлжетсакл

Вызывайте эту функцию для получения данных системного списка управления доступом (SACL) указанного объекта.

> [!IMPORTANT]
> Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
Обработчик объекта, из которого извлекаются сведения о безопасности.

*ObjectType*<br/>
Задает значение из перечисления [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) , которое указывает тип объекта, определяемого параметром *хобжект* .

*псакл*<br/>
Указатель на объект SACL, который будет содержать полученные сведения о безопасности.

*брекуестнидедпривилежес*<br/>
Если значение — true, функция попытается включить привилегию SE_SECURITY_NAME и восстановить ее по завершении.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Если метод должен `AtlGetSacl` вызываться много раз на множестве различных объектов, более эффективно включить SE_SECURITY_NAME привилегии один раз перед вызовом функции, при этом параметру *брекуестнидедпривилежес* присвоено значение false.

### <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="atlsetsacl"></a><a name="atlsetsacl"></a> атлсетсакл

Вызывайте эту функцию для задания данных системного списка управления доступом (SACL) указанного объекта.

> [!IMPORTANT]
> Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
inline bool AtlSetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSacl& rSacl,
    DWORD dwInheritanceFlowControl = 0,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Параметры

*хобжект*<br/>
Обработчик объекта, для которого задаются сведения о безопасности.

*ObjectType*<br/>
Задает значение из перечисления [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) , которое указывает тип объекта, определяемого параметром *хобжект* .

*рсакл*<br/>
Список SACL, содержащий новые сведения о безопасности.

*двинхеританцефловконтрол*<br/>
Управление потоком наследования. Это значение может быть равно 0 (по умолчанию), PROTECTED_SACL_SECURITY_INFORMATION или UNPROTECTED_SACL_SECURITY_INFORMATION.

*брекуестнидедпривилежес*<br/>
Если значение — true, функция попытается включить привилегию SE_SECURITY_NAME и восстановить ее по завершении.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

В отладочных сборках возникнет ошибка утверждения, если *хобжект* является недопустимым или если *двинхеританцефловконтрол* не является одним из трех разрешенных значений.

Если метод должен `AtlSetSacl` вызываться много раз на множестве различных объектов, более эффективно включить SE_SECURITY_NAME привилегии один раз перед вызовом функции, при этом параметру *брекуестнидедпривилежес* присвоено значение false.

### <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="atlgetsecuritydescriptor"></a><a name="atlgetsecuritydescriptor"></a> атлжетсекуритидескриптор

Вызывайте эту функцию для извлечения дескриптора безопасности заданного объекта.

> [!IMPORTANT]
> Эта функция не может использоваться в приложениях, выполняемых в среда выполнения Windows.

```
inline bool AtlGetSecurityDescriptor(
    LPCTSTR pszObjectName,
    SE_OBJECT_TYPE ObjectType,
    CSecurityDesc* pSecurityDescriptor,
    SECURITY_INFORMATION requestedInfo = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION,
bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Параметры

*псзобжектнаме*<br/>
Указатель на строку, завершающуюся нулем, которая указывает имя объекта, из которого извлекаются сведения о безопасности.

*ObjectType*<br/>
Задает значение из перечисления [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) , которое указывает тип объекта, определяемого параметром *псзобжектнаме* .

*псекуритидескриптор*<br/>
Объект, который получает запрошенный дескриптор безопасности.

*рекуестединфо*<br/>
Набор [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) разрядных флагов, указывающих тип получаемых сведений о безопасности. Этот параметр может быть сочетанием следующих значений.

*брекуестнидедпривилежес*<br/>
Если значение — true, функция попытается включить привилегию SE_SECURITY_NAME и восстановить ее по завершении.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Если метод должен `AtlGetSecurityDescriptor` вызываться много раз на множестве различных объектов, более эффективно включить SE_SECURITY_NAME привилегии один раз перед вызовом функции, при этом параметру *брекуестнидедпривилежес* присвоено значение false.

### <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
