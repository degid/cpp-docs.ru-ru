---
title: Класс CSacl
ms.date: 11/04/2016
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
ms.openlocfilehash: d5a060555901361ef6c70c6a4f801605eafd92cf
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746549"
---
# <a name="csacl-class"></a>Класс CSacl

Этот класс представляет собой обертку для структуры SACL (список системного доступа к управлению).

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CSacl : public CAcl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSacl::CSacl](#csacl)|Конструктор.|
|[CSacl:::CSacl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSacl:AddAuditAce](#addauditace)|Добавляет к объекту `CSacl` вход управления доступом аудита (ACE).|
|[CSacl:GetAceCount](#getacecount)|Возвращает количество записей управления доступом (ACE) в объекте. `CSacl`|
|[CSacl::RemoveAce](#removeace)|Удаляет с `CSacl` объекта определенный ACE (вход управления доступом).|
|[CSacl::RemoveAllAces](#removeallaces)|Удаляет все аке, содержащиеся в объекте. `CSacl`|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CSacl::оператор](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

SACL содержит записи управления доступом (ACEs), которые определяют типы попыток доступа, которые генерируют записи аудита в журнале событий безопасности контроллера домена. Обратите внимание, что SACL генерирует записи журналов только на контроллере домена, где произошла попытка доступа, а не на каждом контроллере домена, который содержит копию объекта.

Для установки или извлечения SACL в дескрипторе безопасности объекта необходимо включили SE_SECURITY_NAME привилегию в маркере доступа запрашивающего потока. Группа администраторов имеет эту привилегию, предоставленную по умолчанию, и она может быть предоставлена другим пользователям или группам. Предоставленная привилегия не является всей необходимой: прежде чем операция, определяемая привилегией, может быть выполнена, для вхемного токена доступа безопасности должна быть включена в маркер доступа безопасности. Модель позволяет использовать привилегии только для определенных операций системы, а затем отключать, когда они больше не нужны. Примеры возможности SE_SECURITY_NAME [AtlSetSacl](security-global-functions.md#atlsetsacl) [см.](security-global-functions.md#atlgetsacl)

Используйте методы класса, предоставляемые для добавления, `SACL` удаления, создания и удаления aUSE из объекта. Смотрите также [AtlGetSacl](security-global-functions.md#atlgetsacl) и [AtlSetSacl](security-global-functions.md#atlsetsacl).

Для введения в модель управления доступом [Access Control](/windows/win32/SecAuthZ/access-control) в Windows см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Cacl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="csacladdauditace"></a><a name="addauditace"></a>CSacl:AddAuditAce

Добавляет к объекту `CSacl` вход управления доступом аудита (ACE).

```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Параметры

*Rsid*<br/>
Объект [CSid.](../../atl/reference/csid-class.md)

*AccessMask*<br/>
Указать маску прав доступа, которые будут проверены для указанного `CSid` объекта.

*bУспех*<br/>
Уточняется, следует ли проводить аудит попыток разрешенного доступа. Установите этот флаг на истину, чтобы позволить аудит; в противном случае, установить его ложным.

*bОтказ*<br/>
Уточняется, следует ли проводить аудит попыток отказа в доступе. Установите этот флаг на истину, чтобы позволить аудит; в противном случае, установить его ложным.

*Асефлагы*<br/>
Набор битовых флагов, которые контролируют наследование ACE.

*pObjectType*<br/>
Тип объекта.

*pУнаследовалныйОбъектТип*<br/>
Тип объекта наследования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если ACE `CSacl` добавлен к объекту, FALSE при сбое.

### <a name="remarks"></a>Примечания

Объект `CSacl` содержит записи управления доступом (ACEs), которые определяют типы попыток доступа, которые генерируют записи аудита в журнале событий безопасности. Этот метод добавляет такой `CSacl` ACE к объекту.

Смотрите [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) для описания различных флагов, которые могут быть установлены в параметре *AceFlags.*

## <a name="csaclcsacl"></a><a name="csacl"></a>CSacl::CSacl

Конструктор.

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Существующая `ACL` (список контроля доступа) структура.

### <a name="remarks"></a>Примечания

Объект `CSacl` может быть дополнительно создан `ACL` с использованием существующей структуры. Убедитесь, что этот параметр является списком управления доступом к системе (SACL), а не дискреционным списком контроля доступа (DACL). В отладке сборки, если DACL поставляется утверждение будет происходить. В релизе сборки любых записей из DACL игнорируются.

## <a name="csaclcsacl"></a><a name="dtor"></a>CSacl:::CSacl

Деструктор

```
~CSacl() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все ресурсы, приобретенные объектом, включая все записи управления доступом (ACEs).

## <a name="csaclgetacecount"></a><a name="getacecount"></a>CSacl:GetAceCount

Возвращает количество записей управления доступом (ACE) в объекте. `CSacl`

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество акций, `CSacl` содержащихся в объекте.

## <a name="csacloperator-"></a><a name="operator_eq"></a>CSacl::оператор

Оператор присвоения.

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
(Список `ACL` контроля доступа) для присвоения существующему объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на `CSacl` обновленный объект. Убедитесь, `ACL` что параметр на самом деле является списком управления доступом к системе (SACL), а не дискреционным списком контроля доступа (DACL). В отладке сборки будет происходить утверждение, а в сборках релиза `ACL` параметр будет проигнорирован.

## <a name="csaclremoveace"></a><a name="removeace"></a>CSacl::RemoveAce

Удаляет с `CSacl` объекта определенный ACE (вход управления доступом).

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс на вход ACE для удаления.

### <a name="remarks"></a>Примечания

Этот метод получен из [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

## <a name="csaclremoveallaces"></a><a name="removeallaces"></a>CSacl::RemoveAllAces

Удаляет все записи управления доступом (ACEs), `CSacl` содержащиеся в объекте.

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Примечания

Удаляет каждую `ACE` структуру (если `CSacl` таковая имеется) в объекте.

## <a name="see-also"></a>См. также раздел

[Класс CAcl](../../atl/reference/cacl-class.md)<br/>
[списки управления доступом;](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Тузов](/windows/win32/SecAuthZ/access-control-entries)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
