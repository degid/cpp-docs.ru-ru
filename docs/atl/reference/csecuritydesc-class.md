---
title: Класс CSecurityDesc
ms.date: 11/04/2016
f1_keywords:
- CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::FromString
- ATLSECURITY/ATL::CSecurityDesc::GetControl
- ATLSECURITY/ATL::CSecurityDesc::GetDacl
- ATLSECURITY/ATL::CSecurityDesc::GetGroup
- ATLSECURITY/ATL::CSecurityDesc::GetOwner
- ATLSECURITY/ATL::CSecurityDesc::GetPSECURITY_DESCRIPTOR
- ATLSECURITY/ATL::CSecurityDesc::GetSacl
- ATLSECURITY/ATL::CSecurityDesc::IsDaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsDaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsDaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsDaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsGroupDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsOwnerDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsSaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsSaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::MakeAbsolute
- ATLSECURITY/ATL::CSecurityDesc::MakeSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::SetControl
- ATLSECURITY/ATL::CSecurityDesc::SetDacl
- ATLSECURITY/ATL::CSecurityDesc::SetGroup
- ATLSECURITY/ATL::CSecurityDesc::SetOwner
- ATLSECURITY/ATL::CSecurityDesc::SetSacl
- ATLSECURITY/ATL::CSecurityDesc::ToString
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
ms.openlocfilehash: 926e4e0a795982479188d90ed866bf5e2584c187
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330974"
---
# <a name="csecuritydesc-class"></a>Класс CSecurityDesc

Этот класс является оберткой для `SECURITY_DESCRIPTOR` структуры.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CSecurityDesc
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSecurityDesc::БезопасностьДеск](#csecuritydesc)|Конструктор.|
|[CSecurityDesc:: »CSecurityDesc](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSecurityDesc::От Стринги](#fromstring)|Преобразует дескриптор безопасности строки формата в действительный, функциональный дескриптор безопасности.|
|[CSecurityDesc:GetControl](#getcontrol)|Извлекает контрольную информацию из дескриптора безопасности.|
|[CSecurityDesc::GetDacl](#getdacl)|Извлекает дискреционный список контроля доступа (DACL) из дескриптора безопасности.|
|[CSecurityDesc:GetGroup](#getgroup)|Извлекает основную групповую информацию из дескриптора безопасности.|
|[CSecurityDesc::GetOwner](#getowner)|Извлекает информатон владельца из дескриптора безопасности.|
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Возвращает указатель в `SECURITY_DESCRIPTOR` структуру.|
|[CSecurityDesc::GetSacl](#getsacl)|Извлекает информацию о системе контроля доступа (SACL) из дескриптора безопасности.|
|[CSecurityDesc::IsDaclAutoУнаследовал](#isdaclautoinherited)|Определяет, настроен ли DACL для поддержки автоматического распространения.|
|[CSecurityDesc::IsaclDefaulted](#isdacldefaulted)|Определяет, настроен ли дескриптор безопасности с помощью DACL по умолчанию.|
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Определяет, содержит ли дескриптор безопасности DACL.|
|[CSecurityDesc::DaclProtected](#isdaclprotected)|Определяет, настроен ли DACL для предотвращения изменений.|
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Определяет, был ли установлен по умолчанию идентификатор групповой безопасности безопасности дескриптора безопасности (SID).|
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Определяет, был ли установлен по умолчанию владелец дескриптора безопасности SID.|
|[CSecurityDesc::IsSaclAutoУнаследовал](#issaclautoinherited)|Определяет, настроен ли SACL для поддержки автоматического распространения.|
|[CSecurityDesc::IsaclDefaulted](#issacldefaulted)|Определяет, настроен ли дескриптор безопасности с помощью SACL по умолчанию.|
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Определяет, содержит ли дескриптор безопасности SACL.|
|[CSecurityDesc::IsaclProtected](#issaclprotected)|Определяет, настроен ли SACL для предотвращения изменений.|
|[CSecurityDesc::Собственное относительное](#isselfrelative)|Определяет, находится ли дескриптор безопасности в самоотносительном формате.|
|[CSecurityDesc:MakeAbsolute](#makeabsolute)|Вызовите этот метод для преобразования дескриптора безопасности в абсолютный формат.|
|[CSecurityDesc:MakeSelf Relative](#makeselfrelative)|Вызовите этот метод, чтобы преобразовать дескриптор безопасности в самоотносительный формат.|
|[CSecurityDesc:SetControl](#setcontrol)|Устанавливает управляющие биты дескриптора безопасности.|
|[CSecurityDesc::SetDacl](#setdacl)|Устанавливает информацию в DACL. Если DACL уже присутствует в дескрипторе безопасности, он заменяется.|
|[CSecurityDesc:SetGroup](#setgroup)|Устанавливает основную групповую информацию дескриптора безопасности абсолютного формата, заменяя любую уже присутствуюую первичную групповую информацию.|
|[CSecurityDesc::SetOwner](#setowner)|Устанавливает владельцу информацию о дескрипторе безопасности абсолютного формата, заменяя любую уже присутствуюую информацию о владельце.|
|[CSecurityDesc::SetSacl](#setsacl)|Устанавливает информацию в SACL. Если SACL уже присутствует в дескрипторе безопасности, он заменяется.|
|[CSecurityDesc::ToString](#tostring)|Преобразует дескриптор безопасности в формат строки.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CSecurityDesc::оператор const SECURITY_DESCRIPTOR](#operator_const_security_descriptor__star)|Возвращает указатель в `SECURITY_DESCRIPTOR` структуру.|
|[CSecurityDesc::оператор](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

Структура `SECURITY_DESCRIPTOR` содержит информацию о безопасности, связанную с объектом. Приложения используют эту структуру для настройки и запроса состояния безопасности объекта. Смотрите также [AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor).

Приложения не должны `SECURITY_DESCRIPTOR` изменять структуру напрямую, а вместо этого должны использовать предоставленные методы класса.

Для введения в модель управления доступом [Access Control](/windows/win32/SecAuthZ/access-control) в Windows см.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="csecuritydesccsecuritydesc"></a><a name="csecuritydesc"></a>CSecurityDesc::БезопасностьДеск

Конструктор.

```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Объект `CSecurityDesc` или `SECURITY_DESCRIPTOR` структура для присвоения новому `CSecurityDesc` объекту.

### <a name="remarks"></a>Примечания

Объект `CSecurityDesc` может быть создан по `SECURITY_DESCRIPTOR` желанию с `CSecurityDesc` помощью структуры или ранее определенного объекта.

## <a name="csecuritydesccsecuritydesc"></a><a name="dtor"></a>CSecurityDesc:: »CSecurityDesc

Деструктор

```
virtual ~CSecurityDesc() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все выделенные ресурсы.

## <a name="csecuritydescfromstring"></a><a name="fromstring"></a>CSecurityDesc::От Стринги

Преобразует дескриптор безопасности строки формата в действительный, функциональный дескриптор безопасности.

```
bool FromString(LPCTSTR pstr) throw(...);
```

### <a name="parameters"></a>Параметры

*pstr*<br/>
Указатель на нулевую строку, содержащую [дескриптор безопасности строки формата,](/windows/win32/SecAuthZ/security-descriptor-string-format) который будет преобразован.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно на успех. Бросает исключение при сбое.

### <a name="remarks"></a>Примечания

Строка может быть создана с помощью [CSecurityDesc::ToString](#tostring). Преобразование дескриптора безопасности в строку упрощает хранение и передачу.

Этот метод вызывает [ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/win32/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptorw).

## <a name="csecuritydescgetcontrol"></a><a name="getcontrol"></a>CSecurityDesc:GetControl

Извлекает контрольную информацию из дескриптора безопасности.

```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```

### <a name="parameters"></a>Параметры

*psdc*<br/>
Указатель на `SECURITY_DESCRIPTOR_CONTROL` структуру, которая получает информацию о контроле дескриптора безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если метод успешно, ложно, если он не удается.

### <a name="remarks"></a>Примечания

Этот метод вызывает [GetSecurityDescriptorControl](/windows/win32/api/securitybaseapi/nf-securitybaseapi-getsecuritydescriptorcontrol).

## <a name="csecuritydescgetdacl"></a><a name="getdacl"></a>CSecurityDesc::GetDacl

Извлекает дискреционный список контроля доступа (DACL) из дескриптора безопасности.

```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pDacl*<br/>
Указатель на `CDacl` структуру, в которой хранится копия DACL дескриптора безопасности. Если существует дискреционный ACL, метод устанавливает *pDacl* по адресу дискреционного ACL дескриптора безопасности. Если дискреционного ACL не существует, значение не сохраняется.

*pbPresent*<br/>
Указатель на значение, указывающее на наличие дискреционного ACL в указанном дескрипторе безопасности. Если дескриптор безопасности содержит дискреционный ACL, этот параметр установлен в истину. Если дескриптор безопасности не содержит дискреционный ACL, этот параметр устанавливается как ложный.

*pbDefaulted*<br/>
Указатель на флаг, установленный значением SE_DACL_DEFAULTED `SECURITY_DESCRIPTOR_CONTROL` флага в структуре, если для дескриптора безопасности существует дискреционный ACL. Если этот флаг верен, дискреционный ACL был извлечен с помощью механизма по умолчанию; если ложно, дискреционный ACL был явно указан пользователем.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если метод успешно, ложно, если он не удается.

## <a name="csecuritydescgetgroup"></a><a name="getgroup"></a>CSecurityDesc:GetGroup

Извлекает основную групповую информацию из дескриптора безопасности.

```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*Psid*<br/>
Указатель на [CSid](../../atl/reference/csid-class.md) (идентификатор безопасности), который получает копию группы, хранящуюся в CDacl.

*pbDefaulted*<br/>
Указатель на флаг, установленный значением SE_GROUP_DEFAULTED `SECURITY_DESCRIPTOR_CONTROL` флага в структуре при возврате метода.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если метод успешно, ложно, если он не удается.

## <a name="csecuritydescgetowner"></a><a name="getowner"></a>CSecurityDesc::GetOwner

Извлекает информатон владельца из дескриптора безопасности.

```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*Psid*<br/>
Указатель на [CSid](../../atl/reference/csid-class.md) (идентификатор безопасности), который получает копию группы, хранящуюся в CDacl.

*pbDefaulted*<br/>
Указатель на флаг, установленный значением SE_OWNER_DEFAULTED `SECURITY_DESCRIPTOR_CONTROL` флага в структуре при возврате метода.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если метод успешно, ложно, если он не удается.

## <a name="csecuritydescgetpsecurity_descriptor"></a><a name="getpsecurity_descriptor"></a>CSecurityDesc::GetPSECURITY_DESCRIPTOR

Возвращает указатель в `SECURITY_DESCRIPTOR` структуру.

```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель в [SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor) структуру.

## <a name="csecuritydescgetsacl"></a><a name="getsacl"></a>CSecurityDesc::GetSacl

Извлекает информацию о системе контроля доступа (SACL) из дескриптора безопасности.

```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSacl*<br/>
Указатель на `CSacl` структуру, в которой хранится копия SACL дескриптора безопасности. Если система ACL существует, метод устанавливает *pSacl* на адрес системы дескриптора безопасности ACL. Если система ACL не существует, значение не сохраняется.

*pbPresent*<br/>
Указатель на флаг, установленный методом, чтобы указать наличие системы ACL в указанном дескрипторе безопасности. Если дескриптор безопасности содержит систему ACL, этот параметр установлен в истину. Если дескриптор безопасности не содержит систему ACL, этот параметр устанавливается как ложный.

*pbDefaulted*<br/>
Указатель на флаг, установленный значением SE_SACL_DEFAULTED `SECURITY_DESCRIPTOR_CONTROL` флага в структуре, если система ACL существует для дескриптора безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если метод успешно, ложно, если он не удается.

## <a name="csecuritydescisdaclautoinherited"></a><a name="isdaclautoinherited"></a>CSecurityDesc::IsDaclAutoУнаследовал

Определяет, настроен ли дискреционный список контроля доступа (DACL) для поддержки автоматического распространения.

```
bool IsDaclAutoInherited() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если дескриптор безопасности содержит DACL, который настроен для поддержки автоматического распространения наследственных записей управления доступом (ACEs) к существующим дочерним объектам. В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Система устанавливает этот бит, когда он выполняет автоматический алгоритм наследования объекта и существующих объектов ребенка.

## <a name="csecuritydescisdacldefaulted"></a><a name="isdacldefaulted"></a>CSecurityDesc::IsaclDefaulted

Определяет, настроен ли дескриптор безопасности со списком дискреционных доступа по умолчанию (DACL).

```
bool IsDaclDefaulted() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если дескриптор безопасности содержит DACL по умолчанию, ложное в противном случае.

### <a name="remarks"></a>Примечания

Этот флаг может повлиять на то, как система относится к DACL, в отношении наследования входа в контроль доступа (ACE). Например, если создатель объекта не указывает DACL, объект получает DACL по умолчанию из токена доступа создателя. Система игнорирует этот флаг, если флаг SE_DACL_PRESENT не установлен.

Этот флаг используется для определения того, как окончательный DACL на объекте должен быть вычислен и физически не хранится в управлении дескриптором безопасности объекта.

Чтобы установить этот флаг, используйте метод [CSecurityDesc::SetDacl.](#setdacl)

## <a name="csecuritydescisdaclpresent"></a><a name="isdaclpresent"></a>CSecurityDesc::IsDaclPresent

Определяет, содержит ли дескриптор безопасности дискреционный список контроля доступа (DACL).

```
bool IsDaclPresent() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если дескриптор безопасности содержит DACL, ложное в противном случае.

### <a name="remarks"></a>Примечания

Если этот флаг не установлен, или если этот флаг установлен и DACL является NULL, дескриптор безопасности позволяет полный доступ для всех.

Этот флаг используется для хранения информации о безопасности, указанной абонентом, до тех пор, пока дескриптор безопасности не будет связан с охраняемым объектом. После того, как дескриптор безопасности связан с охраняемым объектом, SE_DACL_PRESENT флаг всегда устанавливается в управлении дескриптора безопасности.

Чтобы установить этот флаг, используйте метод [CSecurityDesc::SetDacl.](#setdacl)

## <a name="csecuritydescisdaclprotected"></a><a name="isdaclprotected"></a>CSecurityDesc::DaclProtected

Определяет, настроен ли дискреционный список контроля доступа (DACL) для предотвращения изменений.

```
bool IsDaclProtected() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если DACL настроен для предотвращения безопасности дескриптор от изменения наследуемых записей управления доступом (ACEs). В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Чтобы установить этот флаг, используйте метод [CSecurityDesc::SetDacl.](#setdacl)

Этот метод поддерживает автоматическое распространение наследственных АКЕ.

## <a name="csecuritydescisgroupdefaulted"></a><a name="isgroupdefaulted"></a>CSecurityDesc::IsGroupDefaulted

Определяет, был ли установлен по умолчанию идентификатор групповой безопасности безопасности дескриптора безопасности (SID).

```
bool IsGroupDefaulted() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если механизм по умолчанию, а не исходный поставщик дескриптора безопасности, при условии, что группа дескриптора безопасности SID. В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Чтобы установить этот флаг, используйте метод [CSecurityDesc::SetGroup.](#setgroup)

## <a name="csecuritydescisownerdefaulted"></a><a name="isownerdefaulted"></a>CSecurityDesc::IsOwnerDefaulted

Определяет, был ли установлен по умолчанию идентификатор безопасности дескриптора безопасности (SID).

```
bool IsOwnerDefaulted() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если механизм по умолчанию, а не первоначальный поставщик дескриптора безопасности, при условии, что владелец дескриптора безопасности SID. В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Чтобы установить этот флаг, используйте метод [CSecurityDesc::SetOwner.](#setowner)

## <a name="csecuritydescissaclautoinherited"></a><a name="issaclautoinherited"></a>CSecurityDesc::IsSaclAutoУнаследовал

Определяет, настроен ли список управления доступом системы (SACL) для поддержки автоматического распространения.

```
bool IsSaclAutoInherited() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если дескриптор безопасности содержит SACL, который настроен для поддержки автоматического распространения наследственных записей управления доступом (ACEs) к существующим дочерним объектам. В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Система устанавливает этот бит, когда он выполняет автоматический алгоритм наследования объекта и существующих объектов ребенка.

## <a name="csecuritydescissacldefaulted"></a><a name="issacldefaulted"></a>CSecurityDesc::IsaclDefaulted

Определяет, настроен ли дескриптор безопасности со списком контроля доступа системы по умолчанию (SACL).

```
bool IsSaclDefaulted() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если дескриптор безопасности содержит sACL по умолчанию, ложное в противном случае.

### <a name="remarks"></a>Примечания

Этот флаг может повлиять на то, как система относится к SACL, в отношении наследования входа в доступ (ACE). Система игнорирует этот флаг, если флаг SE_SACL_PRESENT не установлен.

Чтобы установить этот флаг, используйте метод [CSecurityDesc::SetSacl.](#setsacl)

## <a name="csecuritydescissaclpresent"></a><a name="issaclpresent"></a>CSecurityDesc::IsSaclPresent

Определяет, содержит ли дескриптор безопасности список управления доступом системы (SACL).

```
bool IsSaclPresent() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если дескриптор безопасности содержит SACL, ложное в противном случае.

### <a name="remarks"></a>Примечания

Чтобы установить этот флаг, используйте метод [CSecurityDesc::SetSacl.](#setsacl)

## <a name="csecuritydescissaclprotected"></a><a name="issaclprotected"></a>CSecurityDesc::IsaclProtected

Определяет, настроен ли список управления доступом системы (SACL) для предотвращения изменений.

```
bool IsSaclProtected() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если SACL настроен для предотвращения безопасности дескриптор от изменения наследуемых записей управления доступом (ACEs). В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Чтобы установить этот флаг, используйте метод [CSecurityDesc::SetSacl.](#setsacl)

Этот метод поддерживает автоматическое распространение наследственных АКЕ.

## <a name="csecuritydescisselfrelative"></a><a name="isselfrelative"></a>CSecurityDesc::Собственное относительное

Определяет, находится ли дескриптор безопасности в самоотносительном формате.

```
bool IsSelfRelative() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если дескриптор безопасности находится в самоотносительном формате со всей информацией о безопасности в сопредельном блоке памяти. Возвращает ложно, если дескриптор безопасности находится в абсолютном формате. Для получения дополнительной информации [см.](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)

## <a name="csecuritydescmakeabsolute"></a><a name="makeabsolute"></a>CSecurityDesc:MakeAbsolute

Вызовите этот метод для преобразования дескриптора безопасности в абсолютный формат.

```
bool MakeAbsolute() throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если метод успешно, ложнов в противном случае.

### <a name="remarks"></a>Примечания

Дескриптор безопасности в абсолютном формате содержит указатели на содержащуюся в нем информацию, а не на саму информацию. Дескриптор безопасности в самоотносительном формате содержит информацию в смежном блоке памяти. В самоотносительном дескрипторе `SECURITY_DESCRIPTOR` безопасности всегда запускается структура, но другие компоненты дескриптора безопасности могут следовать за структурой в любом порядке. Вместо использования адресов памяти компоненты самородственники дескриптора безопасности идентифицируются смещениями с начала дескриптора безопасности. Этот формат полезен, когда дескриптор безопасности должен храниться на диске или передаваться с помощью протокола связи. Для получения дополнительной информации [см.](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)

## <a name="csecuritydescmakeselfrelative"></a><a name="makeselfrelative"></a>CSecurityDesc:MakeSelf Relative

Вызовите этот метод, чтобы преобразовать дескриптор безопасности в самоотносительный формат.

```
bool MakeSelfRelative() throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если метод успешно, ложнов в противном случае.

### <a name="remarks"></a>Примечания

Дескриптор безопасности в абсолютном формате содержит указатели на содержащуюся в нем информацию, а не содержащие саму информацию. Дескриптор безопасности в самоотносительном формате содержит информацию в смежном блоке памяти. В самоотносительном дескрипторе `SECURITY_DESCRIPTOR` безопасности всегда запускается структура, но другие компоненты дескриптора безопасности могут следовать за структурой в любом порядке. Вместо адресов памяти компоненты дескриптора безопасности идентифицируются смещениями с начала дескриптора безопасности. Этот формат полезен, когда дескриптор безопасности должен храниться на диске или передаваться с помощью протокола связи. Для получения дополнительной информации [см.](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)

## <a name="csecuritydescoperator-"></a><a name="operator_eq"></a>CSecurityDesc::оператор

Оператор присвоения.

```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Структура `SECURITY_DESCRIPTOR` или `CSecurityDesc` объект для присвоения объекту. `CSecurityDesc`

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CSecurityDesc` объект.

## <a name="csecuritydescoperator-const-security_descriptor-"></a><a name="operator_const_security_descriptor__star"></a>CSecurityDesc::оператор const SECURITY_DESCRIPTOR

Отбрасывает значение указателю на `SECURITY_DESCRIPTOR` структуру.

```
operator const SECURITY_DESCRIPTOR *() const throw();
```

## <a name="csecuritydescsetcontrol"></a><a name="setcontrol"></a>CSecurityDesc:SetControl

Устанавливает управляющие биты дескриптора безопасности.

```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest,
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```

### <a name="parameters"></a>Параметры

*ControlBitsOfInterest*<br/>
Маска SECURITY_DESCRIPTOR_CONTROL, которая указывает устанавливаемые управляющие биты. Список флагов, которые можно установить, [можно](/windows/win32/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol)установить, см.

*ControlBitsToSet*<br/>
Маска SECURITY_DESCRIPTOR_CONTROL, которая указывает на новые значения для контрольных битов, указанные в маске *ControlBitsOfInterest.* Этот параметр может быть комбинацией флагов, перечисленных для параметра *ControlBitsOfInterest.*

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Этот метод вызывает [SetSecurityDescriptorControl](/windows/win32/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol).

## <a name="csecuritydescsetdacl"></a><a name="setdacl"></a>CSecurityDesc::SetDacl

Устанавливает информацию в дискреционный список контроля доступа (DACL). Если DACL уже присутствует в дескрипторе безопасности, он заменяется.

```
inline void SetDacl(
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Параметры

*Dacl*<br/>
Ссылка `CDacl` на объект, определяющий DACL для дескриптора безопасности. Этот параметр не должен быть NULL. Чтобы установить NULL DACL в дескриптор безопасности, первая форма метода должна быть использована с *bPresent* набор омрачяние ложным.

*bPresent*<br/>
Опознавательный флаг, указывающий на наличие DACL в дескрипторе безопасности. Если этот параметр соответствует действительности, метод `SECURITY_DESCRIPTOR_CONTROL` устанавливает SE_DACL_PRESENT флаг в структуре и использует значения в параметрах *Dacl* и *bDefaulted.* Если это неверно, метод очищает SE_DACL_PRESENT флаг, и *bDefaulted* игнорируется.

*bDefaulted*<br/>
Определяет флаг с указанием источника DACL. Если этот флаг верен, dACL был извлечен каким-то механизмом по умолчанию. Если dACL является ложным, он был явно указан пользователем. Метод хранит это значение в SE_DACL_DEFAULTED `SECURITY_DESCRIPTOR_CONTROL` флаге структуры. Если этот параметр не указан, флаг SE_DACL_DEFAULTED очищается.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Существует важное различие между пустым и несуществующим DACL. Когда DACL пуст, он не содержит записей управления доступом и права доступа не были явно предоставлены. В результате, доступ к объекту неявно отказано. С другой стороны, если у объекта нет DACL, объекту не назначается защита, и любой запрос на доступ предоставляется.

## <a name="csecuritydescsetgroup"></a><a name="setgroup"></a>CSecurityDesc:SetGroup

Устанавливает основную групповую информацию дескриптора безопасности абсолютного формата, заменяя любую уже присутствуюую первичную групповую информацию.

```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Параметры

*Sid*<br/>
Ссылка на объект [CSid](../../atl/reference/csid-class.md) для новой основной группы дескриптора безопасности. Этот параметр не должен быть NULL. Дескриптор безопасности может быть помечен как не имеющий DACL или SACL, но он должен иметь группу и владельца, даже это это NULL SID (который является встроенным SID с особым значением).

*bDefaulted*<br/>
Указывает, была ли информация первичной группы получена из механизма по умолчанию. Если это значение верно, то это информация по умолчанию, и `SECURITY_DESCRIPTOR_CONTROL` метод хранит это значение как SE_GROUP_DEFAULTED флаг в структуре. Если этот параметр равен нулю, SE_GROUP_DEFAULTED флаг очищается.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

## <a name="csecuritydescsetowner"></a><a name="setowner"></a>CSecurityDesc::SetOwner

Устанавливает владельцу информацию о дескрипторе безопасности абсолютного формата. Он заменяет любую информацию о владельце уже присутствует.

```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Параметры

*Sid*<br/>
Объект [CSid](../../atl/reference/csid-class.md) для нового основного владельца дескриптора безопасности. Этот параметр не должен быть NULL.

*bDefaulted*<br/>
Указывает, получена ли информация владельца из механизма по умолчанию. Если это значение верно, это информация по умолчанию. Метод хранит это значение как SE_OWNER_DEFAULTED `SECURITY_DESCRIPTOR_CONTROL` флаг в структуре. Если этот параметр равен нулю, флаг SE_OWNER_DEFAULTED очищается.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

## <a name="csecuritydescsetsacl"></a><a name="setsacl"></a>CSecurityDesc::SetSacl

Устанавливает информацию в списке управления доступом к системе (SACL). Если SACL уже присутствует в дескрипторе безопасности, он заменяется.

```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Параметры

*Sacl*<br/>
Указатель на `CSacl` объект, определяющий SACL для дескриптора безопасности. Этот параметр не должен быть NULL, и должен быть объектом CSacl. В отличие от DACLs, нет никакой разницы между NULL и пустым SACL, так как объекты SACL не указывают права доступа, только информация о аудите.

*bDefaulted*<br/>
Определяет флаг с указанием источника SACL. Если этот флаг верен, SACL был извлечен каким-то механизмом по умолчанию. Если sACL является ложным, он был явно указан пользователем. Метод хранит это значение в SE_SACL_DEFAULTED `SECURITY_DESCRIPTOR_CONTROL` флаге структуры. Если этот параметр не указан, флаг SE_SACL_DEFAULTED очищается.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

## <a name="csecuritydesctostring"></a><a name="tostring"></a>CSecurityDesc::ToString

Преобразует дескриптор безопасности в формат строки.

```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```

### <a name="parameters"></a>Параметры

*pstr*<br/>
Указатель на нулевую строку, которая получит [дескриптор безопасности строки формата.](/windows/win32/SecAuthZ/security-descriptor-string-format)

*Si*<br/>
Определяет комбинацию SECURITY_INFORMATION бижутов, чтобы указать компоненты дескриптора безопасности для включения в строку вывода.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

После того, как дескриптор безопасности находится в строке формате, он может быть более легко хранить или передаваться. Используйте `CSecurityDesc::FromString` метод для преобразования строки обратно в дескриптор безопасности.

Параметр *si* может содержать следующие SECURITY_INFORMATION флаги:

|Значение|Значение|
|-----------|-------------|
|OWNER_SECURITY_INFORMATION|Включите владельца.|
|GROUP_SECURITY_INFORMATION|Включите основную группу.|
|DACL_SECURITY_INFORMATION|Включите DACL.|
|SACL_SECURITY_INFORMATION|Включите SACL.|

Если DACL является NULL и SE_DACL_PRESENT элемент управления установлен в дескрипторе безопасности ввода, метод выходит из строя.

Если DACL является NULL, а SE_DACL_PRESENT элемент управления не установлен в дескрипторе безопасности ввода, в резкейстроке дескриптора безопасности не имеет компонента D:. Для [Security Descriptor String Format](/windows/win32/SecAuthZ/security-descriptor-string-format) получения более подробной информации можно узнать подробнее.

Этот метод вызывает [ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/win32/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptorw).

## <a name="see-also"></a>См. также раздел

[Пример безопасности](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
