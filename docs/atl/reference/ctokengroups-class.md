---
title: Класс cTokengroups
ms.date: 11/04/2016
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
ms.openlocfilehash: ccfa628f4a099f7e13eb09d272c72c2bdd846f37
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746383"
---
# <a name="ctokengroups-class"></a>Класс cTokengroups

Этот класс является оберткой для `TOKEN_GROUPS` структуры.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CTokenGroups
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CTokenGroups:CTokenGroups](#ctokengroups)|Конструктор.|
|[CTokenGroups:: «CTokenGroups](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTokenGroups::Добавить](#add)|Добавляет `CSid` или `TOKEN_GROUPS` существующую `CTokenGroups` структуру к объекту.|
|[CTokenGroups::Delete](#delete)|Удаляет из `CSid` `CTokenGroups` объекта атрибуты a и связанные с ним атрибуты.|
|[CTokenGroups::DeleteAll](#deleteall)|Удаляет все `CSid` объекты и связанные `CTokenGroups` с ними атрибуты из объекта.|
|[CTokenGroups::GetCount](#getcount)|Возвращает количество `CSid` объектов и связанных `CTokenGroups` атрибутов, содержащихся в объекте.|
|[CtokenGroups::GetLength](#getlength)|Возвращает размер `CTokenGroups` объекта.|
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|Извлекает указатель на `TOKEN_GROUPS` структуру.|
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|Извлекает `CSid` объекты и атрибуты, принадлежащие объекту. `CTokenGroups`|
|[CTokenGroups:Lookupsid](#lookupsid)|Извлекает атрибуты, связанные с объектом. `CSid`|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CTokenGroups::оператор const TOKEN_GROUPS](#operator_const_token_groups__star)|Отбрасывает `CTokenGroups` объект указателю на `TOKEN_GROUPS` структуру.|
|[CTokenGroups::оператор](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

[Токен доступа](/windows/win32/SecAuthZ/access-tokens) — это объект, описывающий контекст безопасности процесса или потока и выделенный каждому пользователю, зарегистрированного на систему Windows.

Класс `CTokenGroups` представляет собой обертку для [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) структуры, содержащую информацию об идентификаторах безопасности группы (SID) в маркере доступа.

Для введения в модель управления доступом [Access Control](/windows/win32/SecAuthZ/access-control) в Windows см.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="ctokengroupsadd"></a><a name="add"></a>CTokenGroups::Добавить

Добавляет `CSid` или `TOKEN_GROUPS` существующую `CTokenGroups` структуру к объекту.

```cpp
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>Параметры

*Rsid*<br/>
Объект [CSid.](../../atl/reference/csid-class.md)

*dwАтрибуты*<br/>
Атрибуты, связанные `CSid` с объектом.

*rTokenGroups*<br/>
Структура [TOKEN_GROUPS.](/windows/win32/api/winnt/ns-winnt-token_groups)

### <a name="remarks"></a>Примечания

Эти методы добавляют `CSid` один или несколько объектов и связанные с ними атрибуты к объекту. `CTokenGroups`

## <a name="ctokengroupsctokengroups"></a><a name="ctokengroups"></a>CTokenGroups:CTokenGroups

Конструктор.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Объект `CTokenGroups` или [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) структуру, `CTokenGroups` с помощью которой можно построить объект.

### <a name="remarks"></a>Примечания

Объект `CTokenGroups` может быть создан по `TOKEN_GROUPS` желанию с `CTokenGroups` помощью структуры или ранее определенного объекта.

## <a name="ctokengroupsctokengroups"></a><a name="dtor"></a>CTokenGroups:: «CTokenGroups

Деструктор

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все выделенные ресурсы.

## <a name="ctokengroupsdelete"></a><a name="delete"></a>CTokenGroups::Delete

Удаляет из `CSid` `CTokenGroups` объекта атрибуты a и связанные с ним атрибуты.

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>Параметры

*Rsid*<br/>
Объект [CSid,](../../atl/reference/csid-class.md) для которого следует удалить идентификатор безопасности (SID) и атрибуты.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, `CSid` если удален, ложное в противном случае.

## <a name="ctokengroupsdeleteall"></a><a name="deleteall"></a>CTokenGroups::DeleteAll

Удаляет все `CSid` объекты и связанные `CTokenGroups` с ними атрибуты из объекта.

```cpp
void DeleteAll() throw();
```

## <a name="ctokengroupsgetcount"></a><a name="getcount"></a>CTokenGroups::GetCount

Возвращает количество `CSid` объектов, `CTokenGroups`содержащихся в .

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество объектов [CSid](../../atl/reference/csid-class.md) и связанные `CTokenGroups` с ними атрибуты, содержащиеся в объекте.

## <a name="ctokengroupsgetlength"></a><a name="getlength"></a>CtokenGroups::GetLength

Возвращает размер `CTokenGroup` объекта.

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает общий размер `CTokenGroup` объекта в байтах.

## <a name="ctokengroupsgetptoken_groups"></a><a name="getptoken_groups"></a>CTokenGroups::GetPTOKEN_GROUPS

Извлекает указатель на `TOKEN_GROUPS` структуру.

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Извлекает указатель на [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) структуру, принадлежащую объекту `CTokenGroups` маркера доступа.

## <a name="ctokengroupsgetsidsandattributes"></a><a name="getsidsandattributes"></a>CTokenGroups::GetSidsAndAttributes

Извлекает `CSid` объекты и (по желанию) `CTokenGroups` атрибуты, принадлежащие объекту.

```cpp
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSids*<br/>
Указатель на массив объектов [CSid.](../../atl/reference/csid-class.md)

*pAttributes*<br/>
Указатель на массив DWORDs. Если этот параметр опущен или NULL, атрибуты не извлекаются.

### <a name="remarks"></a>Примечания

Этот метод будет перечислять все `CSid` объекты, `CTokenGroups` содержащиеся в объекте, и размещать их и (по желанию) атрибут флаги в объекты массива.

## <a name="ctokengroupslookupsid"></a><a name="lookupsid"></a>CTokenGroups:Lookupsid

Извлекает атрибуты, связанные с объектом. `CSid`

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>Параметры

*Rsid*<br/>
Объект [CSid.](../../atl/reference/csid-class.md)

*pdwАтрибуты*<br/>
Указатель на DWORD, который `CSid` будет принимать атрибут объекта. Если пропущен или NULL, атрибут не будет извлечен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, `CSid` если найдено, ложное в противном случае.

### <a name="remarks"></a>Примечания

Установка *pdwAttributes* на NULL обеспечивает способ подтверждения `CSid` существования атрибута без доступа к атрибуту. Обратите внимание, что этот метод не должен использоваться для проверки прав доступа. Вместо этого приложения должны использовать метод [CAccessToken::CheckTokenMembership.](../../atl/reference/caccesstoken-class.md#checktokenmembership)

## <a name="ctokengroupsoperator-"></a><a name="operator_eq"></a>CTokenGroups::оператор

Оператор присвоения.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Объект `CTokenGroups` или [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) структуру для `CTokenGroups` присвоения объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CTokenGroups` объект.

## <a name="ctokengroupsoperator-const-token_groups-"></a><a name="operator_const_token_groups__star"></a>CTokenGroups::оператор const TOKEN_GROUPS

Отбрасывает значение указателю на `TOKEN_GROUPS` структуру.

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>Примечания

Отбрасывает значение указателю на [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) структуру.

## <a name="see-also"></a>См. также раздел

[Пример безопасности](../../overview/visual-cpp-samples.md)<br/>
[Класс CSid](../../atl/reference/csid-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
