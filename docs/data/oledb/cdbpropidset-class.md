---
title: Класс CDBPropIDSet
ms.date: 11/04/2016
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
- CDBPropIDSet.AddPropertyID
- CDBPropIDSet::AddPropertyID
- AddPropertyID
- ATL.CDBPropIDSet.AddPropertyID
- ATL::CDBPropIDSet::AddPropertyID
- ATL::CDBPropIDSet::CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet.operator=
- ATL.CDBPropIDSet.operator=
- ATL::CDBPropIDSet::operator=
- CDBPropIDSet::operator=
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
helpviewer_keywords:
- CDBPropIDSet class
- AddPropertyID method
- CDBPropIDSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
ms.openlocfilehash: 24cc621e522ed1939fe3127d97e8d54b75fa1618
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838299"
---
# <a name="cdbpropidset-class"></a>Класс CDBPropIDSet

Наследует от `DBPROPIDSET` структуры и добавляет конструктор, который инициализирует ключевые поля, а также метод доступа [аддпропертид](../../data/oledb/cdbpropidset-addpropertyid.md) .

## <a name="syntax"></a>Синтаксис

```cpp
class CDBPropIDSet : public tagDBPROPIDSET
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[аддпропертид](#addpropertyid)|Добавляет свойство в набор ИДЕНТИФИКАТОРов свойств.|
|[кдбпропидсет](#cdbpropidset)|Конструктор.|
|[сетгуид](#setguid)|Задает идентификатор GUID для набора ИДЕНТИФИКАТОРов свойств.|

### <a name="operators"></a>Операторы

| Имя | Описание |
|-|-|
|[operator=](#op_equal)|Присваивает содержимому одного идентификатора свойства другое значение.|

## <a name="remarks"></a>Примечания

OLE DB потребители используют `DBPROPIDSET` структуры для передачи массива идентификаторов свойств, для которых потребитель хочет получить сведения о свойстве. Свойства, определенные в одной структуре [дбпропидсет](/previous-versions/windows/desktop/ms717981(v=vs.85)) , принадлежат одному набору свойств.

## <a name="cdbpropidsetaddpropertyid"></a><a name="addpropertyid"></a> Кдбпропидсет:: Аддпропертид

Добавляет идентификатор свойства в набор ИДЕНТИФИКАТОРов свойств.

### <a name="syntax"></a>Синтаксис

```cpp
bool AddPropertyID(DBPROPID propid) throw();
```

#### <a name="parameters"></a>Параметры

*PropID*<br/>
окне Идентификатор свойства, добавляемого к набору ИДЕНТИФИКАТОРов свойств.

## <a name="cdbpropidsetcdbpropidset"></a><a name="cdbpropidset"></a> Кдбпропидсет:: Кдбпропидсет

Конструктор. Инициализирует `rgProperties` поля, `cProperties` и (при необходимости) `guidPropertySet` структуры [дбпропидсет](/previous-versions/windows/desktop/ms717981(v=vs.85)) .

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropIDSet(const GUID& guid);

CDBPropIDSet(const CDBPropIDSet& propidset);

CDBPropIDSet();
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID, используемый для инициализации `guidPropertySet` поля.

*пропидсет*<br/>
окне Другой `CDBPropIDSet` объект для создания копии.

## <a name="cdbpropidsetsetguid"></a><a name="setguid"></a> Кдбпропидсет:: Сетгуид

Задает поле GUID в `DBPROPIDSET` структуре.

### <a name="syntax"></a>Синтаксис

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID, используемый для задания `guidPropertySet` поля структуры [дбпропидсет](/previous-versions/windows/desktop/ms717981(v=vs.85)) .

### <a name="remarks"></a>Примечания

Это поле также может быть задано [конструктором](../../data/oledb/cdbpropidset-cdbpropidset.md) . Вызывайте эту функцию, если для этого класса используется конструктор по умолчанию.

## <a name="cdbpropidsetoperator-"></a><a name="op_equal"></a> Кдбпропидсет::operator=

Присваивает содержимому одного идентификатора свойства значение другого набора свойств ID.

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();
```

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
