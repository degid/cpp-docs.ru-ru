---
title: Класс Кприватеобжектсекуритидеск
ms.date: 11/04/2016
f1_keywords:
- CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::ConvertToAutoInherit
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Create
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Get
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Set
helpviewer_keywords:
- CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
ms.openlocfilehash: f62d289418280a05f390bf9cdec23ea30632aed2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833508"
---
# <a name="cprivateobjectsecuritydesc-class"></a>Класс Кприватеобжектсекуритидеск

Этот класс представляет объект дескриптора безопасности закрытого объекта.

## <a name="syntax"></a>Синтаксис

```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кприватеобжектсекуритидеск:: Кприватеобжектсекуритидеск](#cprivateobjectsecuritydesc)|Конструктор.|
|[Кприватеобжектсекуритидеск:: ~ Кприватеобжектсекуритидеск](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кприватеобжектсекуритидеск:: Конверттоаутоинхерит](#converttoautoinherit)|Вызывайте этот метод для преобразования дескриптора безопасности и его списков управления доступом (ACL) в формат, который поддерживает автоматическое распространение наследуемых записей управления доступом (ACE).|
|[Кприватеобжектсекуритидеск:: Create](#create)|Вызовите этот метод, чтобы выделить и инициализировать самозависимый дескриптор безопасности для закрытого объекта, созданного вызывающим диспетчером ресурсов.|
|[Кприватеобжектсекуритидеск:: Get](#get)|Вызовите этот метод, чтобы получить сведения из дескриптора безопасности закрытого объекта.|
|[Кприватеобжектсекуритидеск:: Set](#set)|Вызовите этот метод, чтобы изменить дескриптор безопасности закрытого объекта.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator=](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

Этот класс, производный от [ксекуритидеск](../../atl/reference/csecuritydesc-class.md), предоставляет методы для создания дескриптора безопасности закрытого объекта и управления им.

Общие сведения о модели управления доступом в Windows см. в разделе [Управление доступом](/windows/win32/SecAuthZ/access-control) в Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ксекуритидеск](../../atl/reference/csecuritydesc-class.md)

`CPrivateObjectSecurityDesc`

## <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="cprivateobjectsecuritydescconverttoautoinherit"></a><a name="converttoautoinherit"></a> Кприватеобжектсекуритидеск:: Конверттоаутоинхерит

Вызывайте этот метод для преобразования дескриптора безопасности и его списков управления доступом (ACL) в формат, который поддерживает автоматическое распространение наследуемых записей управления доступом (ACE).

```
bool ConvertToAutoInherit(
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>Параметры

*ппарент*<br/>
Указатель на объект [ксекуритидеск](../../atl/reference/csecuritydesc-class.md) , ссылающийся на родительский контейнер объекта. Если родительский контейнер отсутствует, этот параметр имеет значение NULL.

*ObjectType*<br/>
Указатель на `GUID` структуру, которая определяет тип объекта, связанного с текущим объектом. Если у объекта нет идентификатора GUID, задайте для *ObjectType* значение null.

*бисдиректорйобжект*<br/>
Указывает, может ли новый объект содержать другие объекты. Значение true указывает, что новый объект является контейнером. Значение false указывает, что новый объект не является контейнером.

*женерикмаппинг*<br/>
Указатель на структуру [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) , указывающую сопоставление каждого универсального права с конкретными правами для объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Этот метод пытается определить, унаследованы ли элементы ACE в списке управления доступом на уровне пользователей (DACL) и списке управления доступом к системе (SACL) текущего дескриптора безопасности от родительского дескриптора безопасности. Он вызывает функцию [конверттоаутоинхеритприватеобжектсекурити](/windows/win32/api/securitybaseapi/nf-securitybaseapi-converttoautoinheritprivateobjectsecurity) .

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="cprivateobjectsecuritydesc"></a> Кприватеобжектсекуритидеск:: Кприватеобжектсекуритидеск

Конструктор.

```
CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Примечания

Выполняет инициализацию объекта `CPrivateObjectSecurityDesc`.

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="dtor"></a> Кприватеобжектсекуритидеск:: ~ Кприватеобжектсекуритидеск

Деструктор

```
~CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все выделенные ресурсы и удаляет дескриптор безопасности закрытого объекта.

## <a name="cprivateobjectsecuritydesccreate"></a><a name="create"></a> Кприватеобжектсекуритидеск:: Create

Вызовите этот метод, чтобы выделить и инициализировать самозависимый дескриптор безопасности для закрытого объекта, созданного вызывающим диспетчером ресурсов.

```
bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    bool bIsDirectoryObject,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();

bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    GUID* ObjectType,
    bool bIsContainerObject,
    ULONG AutoInheritFlags,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>Параметры

*ппарент*<br/>
Указатель на объект [ксекуритидеск](../../atl/reference/csecuritydesc-class.md) , ссылающийся на родительский каталог, в котором создается новый объект. Задайте значение NULL, если родительский каталог отсутствует.

*пкреатор*<br/>
Указатель на дескриптор безопасности, предоставленный создателем объекта. Если создатель объекта явно не передает сведения о безопасности для нового объекта, присвойте этому параметру значение NULL.

*бисдиректорйобжект*<br/>
Указывает, может ли новый объект содержать другие объекты. Значение true указывает, что новый объект является контейнером. Значение false указывает, что новый объект не является контейнером.

*токен*.<br/>
Ссылка на объект [CAccessToken](../../atl/reference/caccesstoken-class.md) для клиентского процесса, от лица которого создается объект.

*женерикмаппинг*<br/>
Указатель на структуру [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) , указывающую сопоставление каждого универсального права с конкретными правами для объекта.

*ObjectType*<br/>
Указатель на `GUID` структуру, которая определяет тип объекта, связанного с текущим объектом. Если у объекта нет идентификатора GUID, задайте для *ObjectType* значение null.

*бисконтаинеробжект*<br/>
Указывает, может ли новый объект содержать другие объекты. Значение true указывает, что новый объект является контейнером. Значение false указывает, что новый объект не является контейнером.

*аутоинхеритфлагс*<br/>
Набор битовых флагов, управляющих наследованием записей управления доступом (ACE) из *ппарент*. Дополнительные сведения см. в разделе [креатеприватеобжектсекуритекс](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Этот метод вызывает [креатеприватеобжектсеркурити](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurity) или [креатеприватеобжектсекуритекс](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex).

Второй метод позволяет указать идентификатор GUID типа объекта для нового объекта или управлять наследованием ACE.

> [!NOTE]
> Самозависимый дескриптор безопасности — это дескриптор безопасности, хранящий все сведения о безопасности в непрерывном блоке памяти.

## <a name="cprivateobjectsecuritydescget"></a><a name="get"></a> Кприватеобжектсекуритидеск:: Get

Вызовите этот метод, чтобы получить сведения из дескриптора безопасности закрытого объекта.

```
bool Get(
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```

### <a name="parameters"></a>Параметры

*Си*<br/>
Набор битовых флагов, указывающих на извлекаемые части дескриптора безопасности. Это значение может быть сочетанием битовых флагов [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) .

*пресулт*<br/>
Указатель на объект [ксекуритидеск](../../atl/reference/csecuritydesc-class.md) , который получает копию запрашиваемой информации из указанного дескриптора безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Дескриптор безопасности представляет собой структуру и связанные данные, содержащие сведения о безопасности защищаемого объекта.

## <a name="cprivateobjectsecuritydescoperator-"></a><a name="operator_eq"></a> Кприватеобжектсекуритидеск::operator=

Оператор присвоения.

```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Объект `CPrivateObjectSecurityDesc`, который присваивается текущему объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CPrivateObjectSecurityDesc` объект.

## <a name="cprivateobjectsecuritydescset"></a><a name="set"></a> Кприватеобжектсекуритидеск:: Set

Вызовите этот метод, чтобы изменить дескриптор безопасности закрытого объекта.

```
bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();

bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    ULONG AutoInheritFlags,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();
```

### <a name="parameters"></a>Параметры

*Си*<br/>
Набор битовых флагов, указывающих на устанавливаемые части дескриптора безопасности. Это значение может быть сочетанием битовых флагов [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) .

*Изменение*<br/>
Указатель на объект [ксекуритидеск](../../atl/reference/csecuritydesc-class.md) . Части этого дескриптора безопасности, определяемые параметром *Si* , применяются к дескриптору безопасности объекта.

*женерикмаппинг*<br/>
Указатель на структуру [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) , указывающую сопоставление каждого универсального права с конкретными правами для объекта.

*токен*.<br/>
Ссылка на объект [CAccessToken](../../atl/reference/caccesstoken-class.md) для клиентского процесса, от лица которого создается объект.

*аутоинхеритфлагс*<br/>
Набор битовых флагов, управляющих наследованием записей управления доступом (ACE) из *ппарент*. Дополнительные сведения см. в разделе [креатеприватеобжектсекуритекс](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Второй метод позволяет указать идентификатор GUID типа объекта объекта или управлять наследованием ACE.

## <a name="see-also"></a>См. также раздел

[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)<br/>
[Класс Ксекуритидеск](../../atl/reference/csecuritydesc-class.md)
