---
title: Класс CDacl
ms.date: 11/04/2016
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
ms.openlocfilehash: 713e78635fe261615a82ab518cdb2c68ac0eeed4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747736"
---
# <a name="cdacl-class"></a>Класс CDacl

Этот класс представляет собой обертку для структуры DACL (дискреционный список контроля доступа).

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CDacl : public CAcl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDacl:CDacl](#cdacl)|Конструктор.|
|[CDacl::CDacl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDacl::AddAllowedAce](#addallowedace)|Добавляет разрешенный ACE (вход управления `CDacl` доступом) к объекту.|
|[CDacl::AddDeniedAce](#adddeniedace)|Добавляет отказано ACE `CDacl` к объекту.|
|[CDacl:GetAceCount](#getacecount)|Возвращает количество AE (записи управления доступом) в объекте. `CDacl`|
|[CDacl::RemoveAce](#removeace)|Удаляет с `CDacl` объекта определенный ACE (вход управления доступом).|
|[CDacl::RemoveAllAces](#removeallaces)|Удаляет все аке, содержащиеся в объекте. `CDacl`|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CDacl:оператор](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

Дескриптор безопасности объекта может содержать DACL. DACL содержит ноль или более a(записи контроля доступа), которые идентифицируют пользователей и группы, которые могут получить доступ к объекту. Если DACL пуст (т.е. содержит ноль AES), доступ явно не предоставляется, поэтому доступ неявно отклоняется. Однако, если дескриптор безопасности объекта не имеет DACL, объект не защищен и каждый имеет полный доступ.

Чтобы получить DACL объекта, вы должны быть владельцем объекта или иметь READ_CONTROL доступ к объекту. Чтобы изменить DACL объекта, необходимо иметь WRITE_DAC доступ к объекту.

Используйте методы класса, предоставляемые для создания, добавления, удаления и удаления aAC из `CDacl` объекта. Смотрите также [AtlGetDacl](security-global-functions.md#atlgetdacl) и [AtlSetDacl](security-global-functions.md#atlsetdacl).

Для введения в модель управления доступом [Access Control](/windows/win32/SecAuthZ/access-control) в Windows см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Cacl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="cdacladdallowedace"></a><a name="addallowedace"></a>CDacl::AddAllowedAce

Добавляет разрешенный ACE (вход управления `CDacl` доступом) к объекту.

```
bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Параметры

*Rsid*<br/>
Объект [CSid.](../../atl/reference/csid-class.md)

*AccessMask*<br/>
Указать маску прав доступа, которые должны `CSid` быть разрешены для указанного объекта.

*Асефлагы*<br/>
Набор битовых флагов, которые контролируют наследование ACE.

*pObjectType*<br/>
Тип объекта.

*pУнаследовалныйОбъектТип*<br/>
Тип объекта наследования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если ACE `CDacl` добавлен к объекту, FALSE при сбое.

### <a name="remarks"></a>Примечания

Объект `CDacl` содержит ноль или более AE (записи управления доступом), которые идентифицируют пользователей и группы, которые могут получить доступ к объекту. Этот метод добавляет ACE, который `CDacl` позволяет получить доступ к объекту.

Смотрите [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) для описания различных флагов, `AceFlags` которые могут быть установлены в параметре.

## <a name="cdacladddeniedace"></a><a name="adddeniedace"></a>CDacl::AddDeniedAce

Добавляет отказано В ACE (вход `CDacl` управления доступом) к объекту.

```
bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Параметры

*Rsid*<br/>
Объект `CSid` .

*AccessMask*<br/>
Указано, что маска прав доступа будет отказано в указанном `CSid` объекте.

*Асефлагы*<br/>
Набор битовых флагов, которые контролируют наследование ACE. По умолчанию до 0 в первой форме метода.

*pObjectType*<br/>
Тип объекта.

*pУнаследовалныйОбъектТип*<br/>
Тип объекта наследования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если ACE `CDacl` добавлен к объекту, FALSE при сбое.

### <a name="remarks"></a>Примечания

Объект `CDacl` содержит ноль или более AE (записи управления доступом), которые идентифицируют пользователей и группы, которые могут получить доступ к объекту. Этот метод добавляет ACE, который `CDacl` лишает доступа к объекту.

Смотрите [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) для описания различных флагов, `AceFlags` которые могут быть установлены в параметре.

## <a name="cdaclcdacl"></a><a name="cdacl"></a>CDacl:CDacl

Конструктор.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Существующая `ACL` (список контроля доступа) структура.

### <a name="remarks"></a>Примечания

Объект `CDacl` может быть дополнительно создан `ACL` с использованием существующей структуры. Важно отметить, что в качестве этого параметра следует передавать только DACL (дискреционный список контроля доступа), а не SACL (список системного доступа-управления). В отладке сборки, прохождение SACL вызовет ASSERT. При сборке релизов прохождение SACL приведет к игнорированию ACL (записей управления доступом) в ACL, и никаких ошибок не произойдет.

## <a name="cdaclcdacl"></a><a name="dtor"></a>CDacl::CDacl

Деструктор

```
~CDacl () throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все ресурсы, приобретенные объектом, включая все ACEs (записи контроля доступа) с помощью [CDacl::RemoveAllAces](#removeallaces).

## <a name="cdaclgetacecount"></a><a name="getacecount"></a>CDacl:GetAceCount

Возвращает количество AE (записи управления доступом) в объекте. `CDacl`

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество акций, `CDacl` содержащихся в объекте.

## <a name="cdacloperator-"></a><a name="operator_eq"></a>CDacl:оператор

Оператор присвоения.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
ACL (список контроля доступа) для присвоения существующему объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на `CDacl` обновленный объект.

### <a name="remarks"></a>Примечания

Вы должны убедиться, что вы только пройти DACL (дискреционный список контроля доступа) к этой функции. Передача SACL (список управления системой) этой функции вызовет ASSERT в отладке сборки, но не вызовет ошибок в сборках релизов.

## <a name="cdaclremoveace"></a><a name="removeace"></a>CDacl::RemoveAce

Удаляет с `CDacl` объекта определенный ACE (вход управления доступом).

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс на вход ACE для удаления.

### <a name="remarks"></a>Примечания

Этот метод получен из [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

## <a name="cdaclremoveallaces"></a><a name="removeallaces"></a>CDacl::RemoveAllAces

Удаляет все элементы акции (записи контроля `CDacl` доступа), содержащиеся в объекте.

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Примечания

Удаляет все `ACE` (вход-контроль доступа) (если таковые имеются) в объекте. `CDacl`

## <a name="see-also"></a>См. также раздел

[Пример безопасности](../../overview/visual-cpp-samples.md)<br/>
[Класс CAcl](../../atl/reference/cacl-class.md)<br/>
[списки управления доступом;](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Тузов](/windows/win32/SecAuthZ/access-control-entries)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
