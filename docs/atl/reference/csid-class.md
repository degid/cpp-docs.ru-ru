---
title: CSid, класс
ms.date: 03/27/2019
f1_keywords:
- CSid
- ATLSECURITY/ATL::CSid
- ATLSECURITY/ATL::CSid::CSidArray
- ATLSECURITY/ATL::CSid::CSid
- ATLSECURITY/ATL::CSid::AccountName
- ATLSECURITY/ATL::CSid::Domain
- ATLSECURITY/ATL::CSid::EqualPrefix
- ATLSECURITY/ATL::CSid::GetLength
- ATLSECURITY/ATL::CSid::GetPSID
- ATLSECURITY/ATL::CSid::GetPSID_IDENTIFIER_AUTHORITY
- ATLSECURITY/ATL::CSid::GetSubAuthority
- ATLSECURITY/ATL::CSid::GetSubAuthorityCount
- ATLSECURITY/ATL::CSid::IsValid
- ATLSECURITY/ATL::CSid::LoadAccount
- ATLSECURITY/ATL::CSid::Sid
- ATLSECURITY/ATL::CSid::SidNameUse
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
ms.openlocfilehash: b6787c0e3f075935f19d51aa73bbd66da9cc0fcb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835601"
---
# <a name="csid-class"></a>CSid, класс

Этот класс является оболочкой для `SID` структуры идентификатора безопасности.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CSid
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[Код CSid:: Ксидаррай](#csidarray)|Массив объектов `CSid`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Код CSid:: CSid](#csid)|Конструктор.|
|[Код CSid:: ~ CSid](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Код CSid:: AccountName](#accountname)|Возвращает имя учетной записи, связанной с `CSid` объектом.|
|[CSid::D омаин](#domain)|Возвращает имя домена, связанного с `CSid` объектом.|
|[Код CSid:: Екуалпрефикс](#equalprefix)|`SID`Префиксы (идентификатор безопасности) для проверки на равенство.|
|[CSid:: DATALENGTH](#getlength)|Возвращает длину `CSid` объекта.|
|[Код CSid:: Жетпсид](#getpsid)|Возвращает указатель на `SID` структуру.|
|[CSid:: GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Возвращает указатель на `SID_IDENTIFIER_AUTHORITY` структуру.|
|[Код CSid:: Жетсубаусорити](#getsubauthority)|Возвращает указанную подавторство в `SID` структуре.|
|[Код CSid:: Жетсубаусоритикаунт](#getsubauthoritycount)|Возвращает число подавторов.|
|[Код CSid:: IsValid](#isvalid)|Проверяет `CSid` правильность объекта.|
|[Код CSid:: Лоадаккаунт](#loadaccount)|Обновляет `CSid` объект, учитывая имя учетной записи и домен, или существующую `SID` структуру.|
|[Код CSid:: SID](#sid)|Возвращает строку идентификатора.|
|[Код CSid:: Сиднамеусе](#sidnameuse)|Возвращает описание состояния `CSid` объекта.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator=](#operator_eq)|Оператор присвоения.|
|[Идентификатор безопасности оператора const *](#operator_const_sid__star)|Приводит `CSid` объект к указателю на `SID` структуру.|

### <a name="global-operators"></a>Глобальные операторы

|Имя|Описание|
|-|-|
|[operator==](#operator_eq_eq)|Проверяет два объекта дескриптора безопасности на равенство|
|[operator!=](#operator_neq)|Проверяет два объекта дескриптора безопасности на неравенство|
|[станции \<](#operator_lt)|Сравнивает относительное значение двух объектов дескрипторов безопасности.|
|[Оператор >](#operator_gt)|Сравнивает относительное значение двух объектов дескрипторов безопасности.|
|[станции \<=](#operator_lt__eq)|Сравнивает относительное значение двух объектов дескрипторов безопасности.|
|[Оператор >=](#operator_gt__eq)|Сравнивает относительное значение двух объектов дескрипторов безопасности.|

## <a name="remarks"></a>Примечания

`SID`Структура — это структура переменной длины, используемая для уникальной идентификации пользователей или групп.

Приложения не должны изменять `SID` структуру напрямую, а вместо этого использовать методы, предоставленные этим классом-оболочкой. См. также [атлжетовнерсид](security-global-functions.md#atlgetownersid), [атлсетграупсид](security-global-functions.md#atlsetgroupsid), [атлжетграупсид](security-global-functions.md#atlgetgroupsid)и [атлсетовнерсид](security-global-functions.md#atlsetownersid).

Общие сведения о модели управления доступом в Windows см. в разделе [Управление доступом](/windows/win32/SecAuthZ/access-control) в Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** атлсекурити.h

## <a name="csidaccountname"></a><a name="accountname"></a> Код CSid:: AccountName

Возвращает имя учетной записи, связанной с `CSid` объектом.

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает LPCTSTR, указывающий на имя учетной записи.

### <a name="remarks"></a>Примечания

Этот метод пытается найти имя для указанного `SID` (идентификатора безопасности). Полные сведения см. в разделе [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw).

Если не удается найти имя учетной записи для `SID` , `AccountName` возвращает пустую строку. Это может произойти, если время ожидания сети не позволяет этому методу найти имя. Это также происходит для идентификаторов безопасности без соответствующего имени учетной записи, например `SID` , который идентифицирует сеанс входа.

## <a name="csidcsid"></a><a name="csid"></a> Код CSid:: CSid

Конструктор.

```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Существующий `CSid` объект или `SID` Структура (идентификатор безопасности).

*идентифиераусорити*<br/>
Центр сертификации.

*нсубаусоритикаунт*<br/>
Число подавторов.

*псзаккаунтнаме*<br/>
Имя учетной записи.

*псзсистем*<br/>
Имя системы. Эта строка может быть именем удаленного компьютера. Если эта строка имеет значение NULL, вместо нее используется локальная система.

*Пустой pSid*<br/>
Указатель на `SID` структуру.

### <a name="remarks"></a>Примечания

Конструктор инициализирует `CSid` объект, настроив внутренний элемент данных на *сидтипеинвалид*или копируя параметры из существующей `CSid` или существующей `SID` учетной записи.

Если инициализация завершается неудачей, конструктор вызывает [класс катлексцептион](../../atl/reference/catlexception-class.md).

## <a name="csidcsid"></a><a name="dtor"></a> Код CSid:: ~ CSid

Деструктор

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все ресурсы, полученные объектом.

## <a name="csidcsidarray"></a><a name="csidarray"></a> Код CSid:: Ксидаррай

Массив объектов [CSid](../../atl/reference/csid-class.md) .

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>Примечания

Это определение типа определяет тип массива, который можно использовать для получения идентификаторов безопасности из списка ACL (список управления доступом). См. раздел [какл:: жетаклентриес](../../atl/reference/cacl-class.md#getaclentries).

## <a name="csiddomain"></a><a name="domain"></a> CSid::D омаин

Возвращает имя домена, связанного с `CSid` объектом.

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект, `LPCTSTR` указывающий на домен.

### <a name="remarks"></a>Примечания

Этот метод пытается найти имя для указанного `SID` (идентификатора безопасности). Полные сведения см. в разделе [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw).

Если не удается найти имя учетной записи для `SID` , `Domain` возвращает домен в виде пустой строки. Это может произойти, если время ожидания сети не позволяет этому методу найти имя. Это также происходит для идентификаторов безопасности без соответствующего имени учетной записи, например `SID` , который идентифицирует сеанс входа.

## <a name="csidequalprefix"></a><a name="equalprefix"></a> Код CSid:: Екуалпрефикс

`SID`Префиксы (идентификатор безопасности) для проверки на равенство.

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
`SID`Структура или сравниваемый объект (идентификатор безопасности) `CSid` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [екуалпрефикссид](/windows/win32/api/securitybaseapi/nf-securitybaseapi-equalprefixsid) в Windows SDK.

## <a name="csidgetlength"></a><a name="getlength"></a> CSid:: DATALENGTH

Возвращает длину `CSid` объекта.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину объекта в байтах `CSid` .

### <a name="remarks"></a>Примечания

Если структура недопустима `CSid` , возвращаемое значение не определено. Перед вызовом метода `GetLength` используйте функцию-член [CSid:: IsValid](#isvalid) , чтобы убедиться, что `CSid` является допустимым.

> [!NOTE]
> В разделе Отладка сборок функция вызывает ASSERT, если `CSid` объект является недопустимым.

## <a name="csidgetpsid"></a><a name="getpsid"></a> Код CSid:: Жетпсид

Возвращает указатель на `SID` структуру (идентификатор безопасности).

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес `CSid` базовой `SID` структуры объекта.

## <a name="csidgetpsid_identifier_authority"></a><a name="getpsid_identifier_authority"></a> CSid:: GetPSID_IDENTIFIER_AUTHORITY

Возвращает указатель на `SID_IDENTIFIER_AUTHORITY` структуру.

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается с ошибкой, возвращается адрес `SID_IDENTIFIER_AUTHORITY` структуры. В случае сбоя возвращаемое значение не определено. Сбой может произойти, если `CSid` объект является недопустимым. в этом случае метод [CSid:: IsValid](#isvalid) возвращает значение false. Функцию `GetLastError` можно вызывать для получения расширенных сведений об ошибках.

> [!NOTE]
> В разделе Отладка сборок функция вызывает ASSERT, если `CSid` объект является недопустимым.

## <a name="csidgetsubauthority"></a><a name="getsubauthority"></a> Код CSid:: Жетсубаусорити

Возвращает указанную подавторство в `SID` структуре (идентификатор безопасности).

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>Параметры

*нсубаусорити*<br/>
Подавтор.

### <a name="return-value"></a>Возвращаемое значение

Возвращает подавтор, на который ссылается *нсубаусорити.* Значение подавтора — это относительный идентификатор (RID).

### <a name="remarks"></a>Примечания

Параметр *нсубаусорити* задает значение индекса, определяющее элемент массива подавторов, который будет возвращен методом. Метод не выполняет проверочные тесты для этого значения. Приложение может вызвать код [CSid:: жетсубаусоритикаунт](#getsubauthoritycount) , чтобы определить диапазон допустимых значений.

> [!NOTE]
> В разделе Отладка сборок функция вызывает ASSERT, если `CSid` объект является недопустимым.

## <a name="csidgetsubauthoritycount"></a><a name="getsubauthoritycount"></a> Код CSid:: Жетсубаусоритикаунт

Возвращает число подавторов.

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершился удачно, возвращается значение счетчика подавторов.

Если метод завершается ошибкой, возвращаемое значение не определено. Метод завершается ошибкой, если `CSid` объект является недопустимым. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

> [!NOTE]
> В разделе Отладка сборок функция вызывает ASSERT, если `CSid` объект является недопустимым.

## <a name="csidisvalid"></a><a name="isvalid"></a> Код CSid:: IsValid

Проверяет `CSid` правильность объекта.

```
bool IsValid() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE `CSid` , если объект является допустимым, в противном случае — значение false. Расширенные сведения об ошибке для этого метода отсутствуют. не вызывайте `GetLastError` .

### <a name="remarks"></a>Примечания

`IsValid`Метод проверяет `CSid` объект, проверяя, что номер редакции находится в известном диапазоне, а число вложений меньше максимального.

## <a name="csidloadaccount"></a><a name="loadaccount"></a> Код CSid:: Лоадаккаунт

Обновляет `CSid` объект, учитывая имя учетной записи и домен, или существующую структуру SID (идентификатор безопасности).

```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*псзаккаунтнаме*<br/>
Имя учетной записи.

*псзсистем*<br/>
Имя системы. Эта строка может быть именем удаленного компьютера. Если эта строка имеет значение NULL, вместо нее используется локальная система.

*Пустой pSid*<br/>
Указатель на структуру [идентификатора безопасности](/windows/win32/api/winnt/ns-winnt-sid) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

### <a name="remarks"></a>Примечания

`LoadAccount` пытается найти идентификатор безопасности для указанного имени. Дополнительные сведения см. в разделе [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw) .

## <a name="csidoperator-"></a><a name="operator_eq"></a> CSid::operator=

Оператор присвоения.

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Значение `SID` (идентификатор безопасности) или `CSid` для назначения `CSid` объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на обновленный `CSid` объект.

## <a name="csidoperator-"></a><a name="operator_eq_eq"></a> CSid::operator==

Проверяет два объекта дескриптора безопасности на равенство.

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в левой части оператора = =.

*rhs*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в правой части оператора = =.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если дескрипторы безопасности равны; в противном случае — значение FALSE.

## <a name="csidoperator-"></a><a name="operator_neq"></a> CSid::operator!=

Проверяет два объекта дескриптора безопасности на неравенство.

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в левой части оператора! =.

*rhs*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в правой части оператора! =.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если дескрипторы безопасности не равны; в противном случае — значение FALSE.

## <a name="csidoperator-lt"></a><a name="operator_lt"></a> CSid::operator &lt;

Сравнивает относительное значение двух объектов дескрипторов безопасности.

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в левой части оператора! =.

*rhs*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в правой части оператора! =.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *LHS* меньше *RHS*; в противном случае — значение false.

## <a name="csidoperator-lt"></a><a name="operator_lt__eq"></a> CSid::operator &lt;=

Сравнивает относительное значение двух объектов дескрипторов безопасности.

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в левой части оператора! =.

*rhs*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в правой части оператора! =.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *LHS* меньше или равен *RHS*; в противном случае — значение false.

## <a name="csidoperator-gt"></a><a name="operator_gt"></a> CSid::operator &gt;

Сравнивает относительное значение двух объектов дескрипторов безопасности.

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в левой части оператора! =.

*rhs*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в правой части оператора! =.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *LHS* больше *RHS*; в противном случае — значение false.

## <a name="csidoperator-gt"></a><a name="operator_gt__eq"></a> CSid::operator &gt;=

Сравнивает относительное значение двух объектов дескрипторов безопасности.

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в левой части оператора! =.

*rhs*<br/>
`SID`(Идентификатор безопасности) или `CSid` отображается в правой части оператора! =.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *LHS* больше или равен *RHS*; в противном случае — значение false.

## <a name="csidoperator-const-sid-"></a><a name="operator_const_sid__star"></a> Идентификатор CSid::operator const \*

Приводит `CSid` объект к указателю на `SID` структуру (идентификатор безопасности).

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>Примечания

Возвращает адрес `SID` структуры.

## <a name="csidsid"></a><a name="sid"></a> Код CSid:: SID

Возвращает `SID` структуру (идентификатор безопасности) в виде строки.

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `SID` структуру в виде строки в формате, подходящем для вывода, хранения или передачи. Эквивалентно [функция ConvertSidToStringSid вернула](/windows/win32/api/sddl/nf-sddl-convertsidtostringsidw).

## <a name="csidsidnameuse"></a><a name="sidnameuse"></a> Код CSid:: Сиднамеусе

Возвращает описание состояния `CSid` объекта.

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение элемента данных, в котором хранится значение, описывающее состояние `CSid` объекта.

|Значение|Описание|
|-----------|-----------------|
|сидтипеусер|Указывает пользователя `SID` (идентификатор безопасности).|
|сидтипеграуп|Указывает группу `SID` .|
|сидтипедомаин|Указывает домен `SID` .|
|сидтипеалиас|Указывает псевдоним `SID` .|
|сидтипевеллкновнграуп|Указывает на `SID` хорошо известную группу.|
|сидтипеделетедаккаунт|Указывает `SID` для удаленной учетной записи.|
|сидтипеинвалид|Указывает на недопустимое `SID` .|
|сидтипеункновн|Указывает на неизвестный `SID` тип.|
|сидтипекомпутер|Указывает на `SID` компьютер.|

### <a name="remarks"></a>Примечания

Вызовите код [CSid:: лоадаккаунт](#loadaccount) , чтобы обновить `CSid` объект перед вызовом метода `SidNameUse` , чтобы вернуть его состояние. `SidNameUse` не изменяет состояние объекта (путем вызова метода `LookupAccountName` или `LookupAccountSid` ), но возвращает только текущее состояние.

## <a name="see-also"></a>См. также раздел

[Пример безопасности](../../overview/visual-cpp-samples.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)<br/>
[Операторы](../../atl/reference/atl-operators.md)
