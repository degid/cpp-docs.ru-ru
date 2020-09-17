---
title: Класс CTokenPrivileges
ms.date: 11/04/2016
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
ms.openlocfilehash: 75c09f723860540aa54cf3744cde7e61d9202f79
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747359"
---
# <a name="ctokenprivileges-class"></a>Класс CTokenPrivileges

Этот класс является оберткой для `TOKEN_PRIVILEGES` структуры.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CTokenPrivileges
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CTokenПривилегии::CTokenПривилегии](#ctokenprivileges)|Конструктор.|
|[CTokenПривилегии:::CTokenПривилегии](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTokenПривилегии::Добавить](#add)|Добавляет одну или несколько `CTokenPrivileges` привилегий к объекту.|
|[CTokenПривилегии::Delete](#delete)|Удаляет привилегию `CTokenPrivileges` из объекта.|
|[CTokenПривилегии::DeleteAll](#deleteall)|Удаляет все привилегии `CTokenPrivileges` из объекта.|
|[CTokenПривилегии::GetCount](#getcount)|Возвращает количество записей привилегий `CTokenPrivileges` в объекте.|
|[CTokenПривилегии::GetDisplayNames](#getdisplaynames)|Получает имена отображений для `CTokenPrivileges` привилегий, содержащихся в объекте.|
|[CTokenПривилегии::GetLength](#getlength)|Возвращает размер буфера в байтах, необходимых для удержания `TOKEN_PRIVILEGES` структуры, представленной объектом. `CTokenPrivileges`|
|[CTokenПривилегии::GetLuidsAndAttributes](#getluidsandattributes)|Извлекает локальные уникальные идентификаторы (LUID) и атрибут флаги с `CTokenPrivileges` объекта.|
|[CTokenПривилегии::GetNamesAndАтрибуты](#getnamesandattributes)|Извлекает имена привилегий и `CTokenPrivileges` атрибут флаги из объекта.|
|[CTokenПривилегии::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Возвращает указатель в `TOKEN_PRIVILEGES` структуру.|
|[CTokenПривилегии::LookupPrivilege](#lookupprivilege)|Извлекает атрибут, связанный с данным именем привилегии.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CTokenПривилегии::оператор const TOKEN_PRIVILEGES](#operator_const_token_privileges__star)|Отбрасывает значение указателю на `TOKEN_PRIVILEGES` структуру.|
|[CTokenПривилегии::оператор](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

[Токен доступа](/windows/win32/SecAuthZ/access-tokens) — это объект, описывающий контекст безопасности процесса или потока и выделенный каждому пользователю, зарегистрированного на систему Windows.

Токен доступа используется для описания различных привилегий безопасности, предоставляемых каждому пользователю. Привилегия состоит из 64-битного числа, называемого локально уникальным идентификатором [(LUID)](/windows/win32/api/winnt/ns-winnt-luid)и строкой дескриптора.

Класс `CTokenPrivileges` представляет собой обертку для [структуры TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) и содержит 0 или более привилегий. Привилегии могут быть добавлены, удалены или запрошены с помощью методов поставляемого класса.

Для введения в модель управления доступом [Access Control](/windows/win32/SecAuthZ/access-control) в Windows см.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="ctokenprivilegesadd"></a><a name="add"></a>CTokenПривилегии::Добавить

Добавляет одну или несколько `CTokenPrivileges` привилегий к объекту маркера доступа.

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Параметры

*pszPrivilege*<br/>
Указатель на строку с нулевым завершением, которая определяет название привилегии, как это определено в WINNT. H файл заголовка.

*bEnable*<br/>
Если это так, то привилегия включена. Если это нетак, привилегия отключена.

*rПривилегии*<br/>
Ссылка на [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) структуру. Привилегии и атрибуты копируются из этой `CTokenPrivileges` структуры и добавляются к объекту.

### <a name="return-value"></a>Возвращаемое значение

Первая форма этого метода возвращается верно, если привилегии успешно добавлены, ложно в противном случае.

## <a name="ctokenprivilegesctokenprivileges"></a><a name="ctokenprivileges"></a>CTokenПривилегии::CTokenПривилегии

Конструктор.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Объект `CTokenPrivileges` для присвоения новому объекту.

*rПривилегии*<br/>
Структура [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) для присвоения `CTokenPrivileges` новому объекту.

### <a name="remarks"></a>Примечания

Объект `CTokenPrivileges` может быть создан по `TOKEN_PRIVILEGES` желанию с `CTokenPrivileges` помощью структуры или ранее определенного объекта.

## <a name="ctokenprivilegesctokenprivileges"></a><a name="dtor"></a>CTokenПривилегии:::CTokenПривилегии

Деструктор

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все выделенные ресурсы.

## <a name="ctokenprivilegesdelete"></a><a name="delete"></a>CTokenПривилегии::Delete

Удаляет привилегию из `CTokenPrivileges` объекта маркера доступа.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>Параметры

*pszPrivilege*<br/>
Указатель на строку с нулевым завершением, которая определяет название привилегии, как это определено в WINNT. H файл заголовка. Например, этот параметр может указать постоянную SE_SECURITY_NAME или соответствующую строку "SeSecurityPrivilege".

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если привилегия была успешно удалена, ложнов в противном случае.

### <a name="remarks"></a>Примечания

Этот метод полезен в качестве инструмента для создания ограниченных токенов.

## <a name="ctokenprivilegesdeleteall"></a><a name="deleteall"></a>CTokenПривилегии::DeleteAll

Удаляет все привилегии `CTokenPrivileges` из объекта маркера доступа.

```cpp
void DeleteAll() throw();
```

### <a name="remarks"></a>Примечания

Удаляет все привилегии, `CTokenPrivileges` содержащиеся в объекте маркера доступа.

## <a name="ctokenprivilegesgetdisplaynames"></a><a name="getdisplaynames"></a>CTokenПривилегии::GetDisplayNames

Извлекает имена отображений `CTokenPrivileges` для привилегий, содержащихся в объекте маркера доступа.

```cpp
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>Параметры

*pDisplayNames*<br/>
Указатель на массив объектов `CString`. `CNames`определяется как typedef: `CTokenPrivileges::CAtlArray<CString>`.

### <a name="remarks"></a>Примечания

Параметр `pDisplayNames` является указателем на `CString` массив объектов, которые будут получать имена отображения, соответствующие привилегиям, содержащимся в объекте. `CTokenPrivileges` Этот метод получает имена отображений только для привилегий, указанных в разделе Определенные привилегии WINNT. H.

Этот метод получает отображаемое имя: например, если имя атрибута SE_REMOTE_SHUTDOWN_NAME, отображение — «Выключение силы из удаленной системы». Чтобы получить название системы, используйте [CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes).

## <a name="ctokenprivilegesgetcount"></a><a name="getcount"></a>CTokenПривилегии::GetCount

Возвращает количество записей привилегий `CTokenPrivileges` в объекте.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество привилегий, содержащихся в объекте. `CTokenPrivileges`

## <a name="ctokenprivilegesgetlength"></a><a name="getlength"></a>CTokenПривилегии::GetLength

Возвращает длину `CTokenPrivileges` объекта.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество байтов, необходимых для `TOKEN_PRIVILEGES` хранения `CTokenPrivileges` структуры, представленной объектом, включая все содержащиеся в нем записи о привилегиях.

## <a name="ctokenprivilegesgetluidsandattributes"></a><a name="getluidsandattributes"></a>CTokenПривилегии::GetLuidsAndAttributes

Извлекает локальные уникальные идентификаторы (LUID) и атрибут флаги с `CTokenPrivileges` объекта.

```cpp
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pPrivileges*<br/>
Указатель на массив объектов [LUID.](/windows/win32/api/winnt/ns-winnt-luid) `CLUIDArray`является typedef определяется как `CAtlArray<LUID> CLUIDArray`.

*pAttributes*<br/>
Указатель на массив объектов DWORD. Если этот параметр опущен или NULL, атрибуты не извлекаются. `CAttributes`является typedef определяется как `CAtlArray <DWORD> CAttributes`.

### <a name="remarks"></a>Примечания

Этот метод перечислит все привилегии, содержащиеся `CTokenPrivileges` в объекте маркера доступа, и разместит отдельные ФЛАГи LUID и (по желанию) флаги атрибутов в объекты массива.

## <a name="ctokenprivilegesgetnamesandattributes"></a><a name="getnamesandattributes"></a>CTokenПривилегии::GetNamesAndАтрибуты

Извлекает имя и атрибут `CTokenPrivileges` флаги из объекта.

```cpp
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pNames*<br/>
Указатель на массив `CString` объектов. `CNames`является typedef определяется как `CAtlArray <CString> CNames`.

*pAttributes*<br/>
Указатель на массив объектов DWORD. Если этот параметр опущен или NULL, атрибуты не извлекаются. `CAttributes`является typedef определяется как `CAtlArray <DWORD> CAttributes`.

### <a name="remarks"></a>Примечания

Этот метод перечислит все привилегии, содержащиеся `CTokenPrivileges` в объекте, размещая имя и (по желанию) флаги атрибутов в объекты массива.

Этот метод получает имя атрибута, а не отображаемое имя: например, если имя атрибута SE_REMOTE_SHUTDOWN_NAME, имя системы — SeRemoteShutdownPrivilege. Чтобы получить отображаемое имя, используйте метод [CTokenPrivileges::GetDisplayNames](#getdisplaynames).

## <a name="ctokenprivilegesgetptoken_privileges"></a><a name="getptoken_privileges"></a>CTokenПривилегии::GetPTOKEN_PRIVILEGES

Возвращает указатель в `TOKEN_PRIVILEGES` структуру.

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель в [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) структуру.

## <a name="ctokenprivilegeslookupprivilege"></a><a name="lookupprivilege"></a>CTokenПривилегии::LookupPrivilege

Извлекает атрибут, связанный с данным именем привилегии.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pszPrivilege*<br/>
Указатель на строку с нулевым завершением, которая определяет название привилегии, как это определено в WINNT. H файл заголовка. Например, этот параметр может указать постоянную SE_SECURITY_NAME или соответствующую строку "SeSecurityPrivilege".

*pdwАтрибуты*<br/>
Указатель на перемену, которая получает атрибуты.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если атрибут успешно извлечен, ложно в противном случае.

## <a name="ctokenprivilegesoperator-"></a><a name="operator_eq"></a>CTokenПривилегии::оператор

Оператор присвоения.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rПривилегии*<br/>
[Структура TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) для присвоения объекту. `CTokenPrivileges`

*rhs*<br/>
Объект `CTokenPrivileges` для присвоения объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CTokenPrivileges` объект.

## <a name="ctokenprivilegesoperator-const-token_privileges-"></a><a name="operator_const_token_privileges__star"></a>CTokenPrivileges::оператор const TOKEN_PRIVILEGES\*

Отбрасывает значение указателю на `TOKEN_PRIVILEGES` структуру.

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>Примечания

Отбрасывает значение указателю на [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) структуру.

## <a name="see-also"></a>См. также раздел

[Пример безопасности](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)<br/>
[ЛУИД](/windows/win32/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
