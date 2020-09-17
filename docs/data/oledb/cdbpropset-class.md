---
title: Класс CDBPropSet
ms.date: 11/04/2016
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
- CDBPropSet.operator=
- ATL::CDBPropSet::operator=
- ATL.CDBPropSet.operator=
- CDBPropSet::operator=
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- CDBPropSet::SetGUID
helpviewer_keywords:
- CDBPropSet class
- AddProperty method
- CDBPropSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
- AddProperty method
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
ms.openlocfilehash: 48aa2e3e26bed7c9306ca3005231e464d7b7555b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838261"
---
# <a name="cdbpropset-class"></a>Класс CDBPropSet

Наследует от `DBPROPSET` структуры и добавляет конструктор, который инициализирует ключевые поля, а также `AddProperty` метод доступа.

## <a name="syntax"></a>Синтаксис

```cpp
class CDBPropSet : public tagDBPROPSET
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[AddProperty](#addproperty)|Добавляет свойство в набор свойств.|
|[кдбпропсет](#cdbpropset)|Конструктор.|
|[сетгуид](#setguid)|Задает `guidPropertySet` поле `DBPROPSET` структуры.|

### <a name="operators"></a>Операторы

| Имя | Описание |
|-|-|
|[operator=](#op_equal)|Присваивает содержимому одного свойства значение другого.|

## <a name="remarks"></a>Примечания

Поставщики OLE DB и потребители используют `DBPROPSET` структуры для передачи массивов `DBPROP` структур. Каждая `DBPROP` структура представляет одно свойство, которое можно задать.

## <a name="cdbpropsetaddproperty"></a><a name="addproperty"></a> Кдбпропсет:: AddProperty

Добавляет свойство в набор свойств.

### <a name="syntax"></a>Синтаксис

```cpp
bool AddProperty(DWORD dwPropertyID,
   constVARIANT& var,
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCSTR szValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCWSTR szValue,DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   bool bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   BYTE bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   short nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   long nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   float fltValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   double dblValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   CY cyValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();
```

#### <a name="parameters"></a>Параметры

*двпропертид*<br/>
окне Идентификатор добавляемого свойства. Используется для инициализации `dwPropertyID` `DBPROP` структуры, добавленной в набор свойств.

*var*<br/>
окне Вариант, используемый для инициализации значения свойства для структуры, `DBPROP` добавленной в набор свойств.

*сзвалуе*<br/>
окне Строка, используемая для инициализации значения свойства для `DBPROP` структуры, добавленной в набор свойств.

*bValue*<br/>
окне `BYTE` Логическое значение или, используемое для инициализации значения свойства для `DBPROP` структуры, добавленной в набор свойств.

*Nзначение*<br/>
окне Целочисленное значение, используемое для инициализации значения свойства для `DBPROP` структуры, добавленной в набор свойств.

*флтвалуе*<br/>
окне Значение с плавающей запятой, используемое для инициализации значения свойства для `DBPROP` структуры, добавленной в набор свойств.

*дблвалуе*<br/>
окне Значение двойной точности с плавающей запятой, используемое для инициализации значения свойства для `DBPROP` структуры, добавленной в набор свойств.

*цивалуе*<br/>
окне Значение валюты CY, используемое для инициализации значения свойства для `DBPROP` структуры, добавленной в набор свойств.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если свойство было успешно добавлено. В противном случае — **`false`** .

## <a name="cdbpropsetcdbpropset"></a><a name="cdbpropset"></a> Кдбпропсет:: Кдбпропсет

Конструктор. Инициализирует `rgProperties` поля, `cProperties` и `guidPropertySet` структуры [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) .

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropSet(const GUID& guid);

CDBPropSet(const CDBPropSet& propset);

CDBPropSet();
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID, используемый для инициализации `guidPropertySet` поля.

*Prop*<br/>
окне Другой `CDBPropSet` объект для создания копии.

## <a name="cdbpropsetsetguid"></a><a name="setguid"></a> Кдбпропсет:: Сетгуид

Задает `guidPropertySet` поле в `DBPROPSET` структуре.

### <a name="syntax"></a>Синтаксис

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID, используемый для задания `guidPropertySet` поля структуры [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) .

### <a name="remarks"></a>Примечания

Это поле также может быть задано [конструктором](../../data/oledb/cdbpropset-cdbpropset.md) .

## <a name="cdbpropsetoperator-"></a><a name="op_equal"></a> Кдбпропсет::operator=

Присваивает содержимое одного свойства набору другому набору свойств.

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropSet& operator =(CDBPropSet& propset) throw();
```

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс Кдбпропидсет](../../data/oledb/cdbpropidset-class.md)<br/>
[Структура DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 
 [Структура DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85))
