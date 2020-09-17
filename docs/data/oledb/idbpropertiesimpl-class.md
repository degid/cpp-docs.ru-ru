---
title: Класс IDBPropertiesImpl
ms.date: 11/04/2016
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
- IDBPropertiesImpl.SetProperties
- IDBPropertiesImpl::SetProperties
helpviewer_keywords:
- IDBPropertiesImpl class
- GetProperties method
- GetPropertyInfo method
- SetProperties method
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
ms.openlocfilehash: 16f1a3f8ae9b50e43bfd67d9ac8c65507bf4f147
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834340"
---
# <a name="idbpropertiesimpl-class"></a>Класс IDBPropertiesImpl

Предоставляет реализацию для `IDBProperties` интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class ATL_NO_VTABLE IDBPropertiesImpl
   : public IDBProperties, public CUtlProps<T>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IDBPropertiesImpl` .

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Элементы

### <a name="interface-methods"></a>Методы интерфейса

| Имя | Описание |
|-|-|
|[GetProperties](#getproperties)|Возвращает значения свойств в источнике данных, сведения об источнике данных и группах свойств инициализации, которые в настоящее время заданы для объекта источника данных, или значения свойств в группе свойств инициализации, которые в данный момент установлены в перечислителе.|
|[GetPropertyInfo](#getpropertyinfo)|Возвращает сведения обо всех свойствах, поддерживаемых поставщиком.|
|[SetProperties](#setproperties)|Задает свойства в группах свойств источника данных и инициализации, для объектов источника данных или группы свойств инициализации для перечислителей.|

## <a name="remarks"></a>Примечания

[Интерфейс IDBProperties](/previous-versions/windows/desktop/ms719607(v=vs.85)) является обязательным интерфейсом для объектов источника данных и необязательным интерфейсом для перечислителей. Однако если перечислитель предоставляет [IDBInitialize](/previous-versions/windows/desktop/ms713706(v=vs.85)), он должен предоставить `IDBProperties` . `IDBPropertiesImpl` реализует с `IDBProperties` помощью статической функции, определенной [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

## <a name="idbpropertiesimplgetproperties"></a><a name="getproperties"></a> Свойства IDBPropertiesImpl:: Properties

Возвращает значения свойств в источнике данных, сведения об источнике данных и группах свойств инициализации, которые в настоящее время заданы для объекта источника данных, или значения свойств в группе свойств инициализации, которые в данный момент установлены в перечислителе.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetProperties)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcProperties,
   DBPROPSET ** prgProperties);
```

#### <a name="parameters"></a>Параметры

См. раздел [интерфейс IDBProperties:: Properties](/previous-versions/windows/desktop/ms714344(v=vs.85)) в *справочнике программиста OLE DB*.

Некоторые параметры соответствуют *OLE DB ссылочным параметрам программиста* с разными именами, которые описаны в `IDBProperties::GetProperties` :

|OLE DB параметры шаблона|*OLE DB ссылочные параметры программиста*|
|--------------------------------|------------------------------------------------|
|*cPropertySets*|*кпропертидсетс*|
|*rgPropertySets*|*ргпропертидсетс*|
|*пкпропертиес*|*пкпропертисетс*|
|*пргпропертиес*|*пргпропертисетс*|

### <a name="remarks"></a>Примечания

Если поставщик инициализирован, этот метод возвращает значения свойств в DBPROPSET_DATASOURCE, DBPROPSET_DATASOURCEINFO, DBPROPSET_DBINITных группах свойств, которые в данный момент заданы для объекта источника данных. Если поставщик не инициализирован, он возвращает только DBPROPSET_DBINIT свойства группы.

## <a name="idbpropertiesimplgetpropertyinfo"></a><a name="getpropertyinfo"></a> IDBPropertiesImpl:: GetPropertyInfo

Возвращает сведения о свойстве, поддерживаемые источником данных.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetPropertyInfo)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcPropertyInfoSets,
   DBPROPINFOSET ** prgPropertyInfoSets,
   OLECHAR ** ppDescBuffer);
```

#### <a name="parameters"></a>Параметры

См. раздел [интерфейс IDBProperties:: GetPropertyInfo](/previous-versions/windows/desktop/ms718175(v=vs.85)) в *справочнике программиста OLE DB*.

Некоторые параметры соответствуют *OLE DB ссылочным параметрам программиста* с разными именами, которые описаны в `IDBProperties::GetPropertyInfo` :

|OLE DB параметры шаблона|*OLE DB ссылочные параметры программиста*|
|--------------------------------|------------------------------------------------|
|*cPropertySets*|*кпропертидсетс*|
|*rgPropertySets*|*ргпропертидсетс*|

### <a name="remarks"></a>Примечания

Использует [идбинитиализеимпл:: m_pCUtlPropInfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md) для реализации этой функции.

## <a name="idbpropertiesimplsetproperties"></a><a name="setproperties"></a> IDBPropertiesImpl:: SetProperties

Задает свойства в группах свойств источника данных и инициализации, для объектов источника данных или группы свойств инициализации для перечислителей.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Параметры

См. раздел [интерфейс IDBProperties:: SetProperties](/previous-versions/windows/desktop/ms723049(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Если поставщик инициализирован, этот метод задает значения свойств в DBPROPSET_DATASOURCE, DBPROPSET_DATASOURCEINFO, DBPROPSET_DBINIT групп свойств для объекта источника данных. Если поставщик не инициализирован, он устанавливает DBPROPSET_DBINIT только свойства группы.

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
