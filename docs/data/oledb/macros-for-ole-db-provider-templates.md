---
title: Макросы для шаблонов поставщика OLE DB
ms.date: 02/11/2019
f1_keywords:
- BEGIN_PROPERTY_SET
- BEGIN_PROPERTY_SET_EX
- BEGIN_PROPSET_MAP
- CHAIN_PROPERTY_SET
- END_PROPERTY_SET
- END_PROPSET_MAP
- PROPERTY_INFO_ENTRY
- PROPERTY_INFO_ENTRY_EX
- PROPERTY_INFO_ENTRY_VALUE
- BEGIN_PROVIDER_COLUMN_MAP
- END_PROVIDER_COLUMN_MAP
- PROVIDER_COLUMN_ENTRY
- PROVIDER_COLUMN_ENTRY_FIXED
- PROVIDER_COLUMN_ENTRY_GN
- PROVIDER_COLUMN_ENTRY_LENGTH
- PROVIDER_COLUMN_ENTRY_STR
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
- PROVIDER_COLUMN_ENTRY_WSTR
- BEGIN_SCHEMA_MAP
- END_SCHEMA_MAP
- SCHEMA_ENTRY
helpviewer_keywords:
- OLE DB provider templates, macros
- macros, OLE DB Provider Templates
- Provider Template macros (OLE DB)
- OLE DB Provider Template macros
- BEGIN_PROPERTY_SET macro
- BEGIN_PROPERTY_SET_EX macro
- BEGIN_PROPSET_MAP macro
- CHAIN_PROPERTY_SET macro
- END_PROPERTY_SET macro
- END_PROPSET_MAP macro
- PROPERTY_INFO_ENTRY macro
- PROPERTY_INFO_ENTRY_EX macro
- PROPERTY_INFO_ENTRY_VALUE macro
- BEGIN_PROVIDER_COLUMN_MAP macro
- END_PROVIDER_COLUMN_MAP macro
- PROVIDER_COLUMN_ENTRY macro
- PROVIDER_COLUMN_ENTRY_FIXED macro
- PROVIDER_COLUMN_ENTRY_GN macro
- PROVIDER_COLUMN_ENTRY_LENGTH macro
- PROVIDER_COLUMN_ENTRY_STR macro
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH macro
- PROVIDER_COLUMN_ENTRY_WSTR macro
- BEGIN_SCHEMA_MAP macro
- END_SCHEMA_MAP macro
- SCHEMA_ENTRY macro
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
ms.openlocfilehash: 53ea92c2eece31829a7554c0f9accf2e56d727a9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840730"
---
# <a name="macros-for-ole-db-provider-templates"></a>Макросы для шаблонов поставщика OLE DB

Макросы поставщика OLE DB шаблонов предоставляют функциональные возможности в следующих категориях:

## <a name="property-set-map-macros"></a>Макросы для задания схемы набора свойств

| Имя | Описание |
|-|-|
|[BEGIN_PROPERTY_SET](#begin_property_set)|Помечает начало набора свойств.|
|[BEGIN_PROPERTY_SET_EX](#begin_property_set_ex)|Помечает начало набора свойств.|
|[BEGIN_PROPSET_MAP](#begin_propset_map)|Помечает начало набора свойств, который может быть скрыт или определен вне области действия поставщика.|
|[CHAIN_PROPERTY_SET](#chain_property_set)|Объединяет группы свойств.|
|[END_PROPERTY_SET](#end_property_set)|Помечает конец набора свойств.|
|[END_PROPSET_MAP](#end_propset_map)|Помечает конец схемы набора свойств.|
|[PROPERTY_INFO_ENTRY](#property_info_entry)|Присваивает конкретному свойству в свойстве значение по умолчанию.|
|[PROPERTY_INFO_ENTRY_EX](#property_info_entry_ex)|Присваивает конкретному свойству, заданному свойству, значение, предоставленное вами. Также позволяет задавать флаги и параметры.|
|[PROPERTY_INFO_ENTRY_VALUE](#property_info_entry_value)|Присваивает конкретному свойству, заданному свойству, значение, предоставленное вами.|

## <a name="column-map-macros"></a>Макросы таблицы соответствия столбцов

| Имя | Описание |
|-|-|
|[BEGIN_PROVIDER_COLUMN_MAP](#begin_provider_column_map)|Помечает начало записей схемы столбца поставщика.|
|[END_PROVIDER_COLUMN_MAP](#end_provider_column_map)|Помечает конец записей схемы столбца поставщика.|
|[PROVIDER_COLUMN_ENTRY](#provider_column_entry)|Представляет конкретный столбец, поддерживаемый поставщиком.|
|[PROVIDER_COLUMN_ENTRY_FIXED](#provider_column_entry_fixed)|Представляет конкретный столбец, поддерживаемый поставщиком. Можно указать тип данных столбца.|
|[PROVIDER_COLUMN_ENTRY_GN](#provider_column_entry_gn)|Представляет конкретный столбец, поддерживаемый поставщиком. Можно указать размер столбца, тип данных, точность, масштаб и идентификатор GUID набора строк схемы.|
|[PROVIDER_COLUMN_ENTRY_LENGTH](#provider_column_entry_length)|Представляет конкретный столбец, поддерживаемый поставщиком. Можно указать размер столбца.|
|[PROVIDER_COLUMN_ENTRY_STR](#provider_column_entry_str)|Представляет конкретный столбец, поддерживаемый поставщиком. Предполагается, что столбец имеет тип String.|
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](#provider_column_entry_type_length)|Представляет конкретный столбец, поддерживаемый поставщиком. Как и PROVIDER_COLUMN_ENTRY_LENGTH, но также позволяет указать тип данных столбца и размер.|
|[PROVIDER_COLUMN_ENTRY_WSTR](#provider_column_entry_wstr)|Представляет конкретный столбец, поддерживаемый поставщиком. Предполагается, что тип столбца является строкой символов Юникода.|

## <a name="schema-rowset-macros"></a>Макросы наборов строк схемы

| Имя | Описание |
|-|-|
|[BEGIN_SCHEMA_MAP](#begin_schema_map)|Помечает начало гиперкарты схемы.|
|[END_SCHEMA_MAP](#end_schema_map)|Помечает конец гиперкарты схемы.|
|[SCHEMA_ENTRY](#schema_entry)|Связывает идентификатор GUID с классом.|

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

### <a name="begin_property_set"></a><a name="begin_property_set"></a> BEGIN_PROPERTY_SET

Помечает начало свойства, заданного в сопоставлении набора свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID свойства.

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_property_set_ex"></a><a name="begin_property_set_ex"></a> BEGIN_PROPERTY_SET_EX

Помечает начало свойства, заданного в сопоставлении набора свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_PROPERTY_SET_EX(guid, flags)
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID свойства.

*flags*<br/>
окне UPROPSET_HIDDEN для любых наборов свойств, которые не нужно предоставлять, или UPROPSET_PASSTHROUGH для поставщика, предоставляющего свойства, определенные за пределами области поставщика.

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_propset_map"></a><a name="begin_propset_map"></a> BEGIN_PROPSET_MAP

Помечает начало записей схемы набора свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_PROPSET_MAP(Class)
```

#### <a name="parameters"></a>Параметры

*Class*<br/>
окне Класс, в котором задано это свойство. Набор свойств можно указать в следующих объектах OLE DB:

- [Объекты источника данных](/previous-versions/windows/desktop/ms721278(v=vs.85))

- [Объекты сеанса](/previous-versions/windows/desktop/ms711572(v=vs.85))

- [Команды](/previous-versions/windows/desktop/ms724608(v=vs.85))

#### <a name="example"></a>Пример

Ниже приведен пример схемы набора свойств.

[!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]

### <a name="chain_property_set"></a><a name="chain_property_set"></a> CHAIN_PROPERTY_SET

Этот макрос объединяет группы свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
CHAIN_PROPERTY_SET(ChainClass)
```

#### <a name="parameters"></a>Параметры

*чаинкласс*<br/>
окне Имя класса для сцепления свойств. Это класс, созданный мастером проектов ATL, который уже содержит карту (такую как сеанс, команда или класс объектов источника данных).

#### <a name="remarks"></a>Примечания

Можно связать набор свойств из другого класса с собственным классом, а затем получить доступ к свойствам непосредственно из класса.

> [!CAUTION]
> Используйте этот макрос с осторожностью. Неправильное использование может привести к сбою потребителя при OLE DB тестов соответствия.

### <a name="end_property_set"></a><a name="end_property_set"></a> END_PROPERTY_SET

Помечает конец набора свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
END_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID свойства.

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="end_propset_map"></a><a name="end_propset_map"></a> END_PROPSET_MAP

Помечает конец записей сопоставлений набора свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
END_PROPSET_MAP()
```

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry"></a><a name="property_info_entry"></a> PROPERTY_INFO_ENTRY

Представляет конкретное свойство в наборе свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
PROPERTY_INFO_ENTRY(dwPropID)
```

#### <a name="parameters"></a>Параметры

*dwPropID*<br/>
[входные данные] Значение [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) , которое может использоваться вместе с GUID набора свойств для идентификации свойства.

#### <a name="remarks"></a>Примечания

Этот макрос задает в качестве значения свойства типа `DWORD` значение по умолчанию, определенное в ATLDB.H. Чтобы задать свойству нужное вам значение, используйте [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md). Чтобы задать `VARTYPE` и [DBPROPFLAGS](/previous-versions/windows/desktop/ms724342(v=vs.85)) для свойства одновременно, используйте [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry_ex"></a><a name="property_info_entry_ex"></a> PROPERTY_INFO_ENTRY_EX

Представляет конкретное свойство в наборе свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID, vt, dwFlags, value, options)
```

#### <a name="parameters"></a>Параметры

*dwPropID*<br/>
[входные данные] Значение [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) , которое может использоваться вместе с GUID набора свойств для идентификации свойства.

*vt*<br/>
[входные данные] `VARTYPE` этой записи свойства. (Определен в втипес.h)

*dwFlags*<br/>
[входные данные] Значение [DBPROPFLAGS](/previous-versions/windows/desktop/ms724342(v=vs.85)) , описывающее эту запись свойства.

*value*<br/>
[входные данные] Значение свойства с типом `DWORD`.

*options*<br/>
DBPROPOPTIONS_REQUIRED или DBPROPOPTIONS_SETIFCHEAP. Как правило, поставщику не нужно задавать *Параметры* , так как он задается потребителем.

#### <a name="remarks"></a>Примечания

С помощью этого макроса можно напрямую указать значение свойства типа `DWORD` , а также параметры и флаги. Чтобы задать свойству значение по умолчанию, определенное в ATLDB. H, используйте [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Чтобы задать свойству значение по своему усмотрению без параметров или флагов, используйте [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md).

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry_value"></a><a name="property_info_entry_value"></a> PROPERTY_INFO_ENTRY_VALUE

Представляет конкретное свойство в наборе свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
PROPERTY_INFO_ENTRY_VALUE(dwPropID, value)
```

#### <a name="parameters"></a>Параметры

*dwPropID*<br/>
[входные данные] Значение [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) , которое может использоваться вместе с GUID набора свойств для идентификации свойства.

*value*<br/>
[входные данные] Значение свойства с типом `DWORD`.

#### <a name="remarks"></a>Примечания

С помощью этого макроса можно напрямую указать значение свойства типа `DWORD` . Чтобы задать для свойства значение по умолчанию, определенное в ATLDB. H, используйте [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Чтобы задать значение, флаги и параметры для свойства, используйте [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_provider_column_map"></a><a name="begin_provider_column_map"></a> BEGIN_PROVIDER_COLUMN_MAP

Помечает начало записей схемы столбца поставщика.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_PROVIDER_COLUMN_MAP(theClass)
```

#### <a name="parameters"></a>Параметры

*секласс*<br/>
окне Имя класса, которому принадлежит эта схема.

#### <a name="example"></a>Пример

Ниже приведен пример схемы столбца поставщика.

[!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]

### <a name="end_provider_column_map"></a><a name="end_provider_column_map"></a> END_PROVIDER_COLUMN_MAP

Помечает конец записей схемы столбца поставщика.

#### <a name="syntax"></a>Синтаксис

```cpp
END_PROVIDER_COLUMN_MAP()
```

#### <a name="example"></a>Пример

См. [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry"></a><a name="provider_column_entry"></a> PROVIDER_COLUMN_ENTRY

Представляет конкретный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY (name, ordinal, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
окне Имя столбца.

*ordinal*<br/>
окне Номер столбца. Если столбец не является столбцом закладки, то номер столбца не должен быть равен 0.

*участниками*<br/>
окне Переменная члена, `dataClass` соответствующая столбцу.

### <a name="provider_column_entry_fixed"></a><a name="provider_column_entry_fixed"></a> PROVIDER_COLUMN_ENTRY_FIXED

Представляет конкретный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_FIXED(name, ordinal, dbtype, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
окне Имя столбца.

*ordinal*<br/>
окне Номер столбца. Если столбец не является столбцом закладки, то номер столбца не должен быть равен 0.

*типом*<br/>
окне Тип данных в [DbType](/previous-versions/windows/desktop/ms711251(v=vs.85)).

*участниками*<br/>
окне Переменная члена в `dataClass` , в которой хранятся данные.

#### <a name="remarks"></a>Примечания

Позволяет указать тип данных столбца.

#### <a name="example"></a>Пример

См. [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_gn"></a><a name="provider_column_entry_gn"></a> PROVIDER_COLUMN_ENTRY_GN

Представляет конкретный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_GN (name, ordinal, flags, colSize, dbtype, precision, scale, guid)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
окне Имя столбца.

*ordinal*<br/>
окне Номер столбца. Если столбец не является столбцом закладки, то номер столбца не должен быть равен 0.

*flags*<br/>
окне Указывает, как возвращаются данные. См `dwFlags` . описание в разделе [структуры DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*колсизе*<br/>
окне Размер столбца.

*типом*<br/>
окне Указывает тип данных значения. См `wType` . описание в разделе [структуры DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*precision*<br/>
окне Указывает точность, используемую при получении данных, если *DbType* имеет DBTYPE_NUMERIC или DBTYPE_DECIMAL. См `bPrecision` . описание в разделе [структуры DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*масштаб*<br/>
окне Указывает масштаб, используемый при получении данных, если dbType имеет DBTYPE_NUMERIC или DBTYPE_DECIMAL. См `bScale` . описание в разделе [структуры DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*guid*<br/>
Идентификатор GUID набора строк схемы. Список наборов строк схемы и их идентификаторов GUID см. в разделе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) в *справочнике программиста OLE DB* .

#### <a name="remarks"></a>Примечания

Позволяет указать размер столбца, тип данных, точность, масштаб и идентификатор GUID набора строк схемы.

### <a name="provider_column_entry_length"></a><a name="provider_column_entry_length"></a> PROVIDER_COLUMN_ENTRY_LENGTH

Представляет конкретный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_LENGTH(name, ordinal, size, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
окне Имя столбца.

*ordinal*<br/>
окне Номер столбца. Если столбец не является столбцом закладки, то номер столбца не должен быть равен 0.

*size*<br/>
окне Размер столбца в байтах.

*участниками*<br/>
окне Переменная члена в `dataClass` , в которой хранятся данные столбца.

#### <a name="remarks"></a>Примечания

Позволяет указать размер столбца.

#### <a name="example"></a>Пример

См. [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_str"></a><a name="provider_column_entry_str"></a> PROVIDER_COLUMN_ENTRY_STR

Представляет конкретный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_STR(name, ordinal, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
окне Имя столбца.

*ordinal*<br/>
окне Номер столбца. Если столбец не является столбцом закладки, то номер столбца не должен быть равен 0.

*участниками*<br/>
окне Переменная члена в классе данных, в которой хранятся данные.

#### <a name="remarks"></a>Примечания

Используйте этот макрос, если предполагается [DBTYPE_STR](/previous-versions/windows/desktop/ms711251(v=vs.85))данных столбца.

#### <a name="example"></a>Пример

См. [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_type_length"></a><a name="provider_column_entry_type_length"></a> PROVIDER_COLUMN_ENTRY_TYPE_LENGTH

Представляет конкретный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(name, ordinal, dbtype, size, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
окне Имя столбца.

*ordinal*<br/>
окне Номер столбца. Если столбец не является столбцом закладки, то номер столбца не должен быть равен 0.

*типом*<br/>
окне Тип данных в [DbType](/previous-versions/windows/desktop/ms711251(v=vs.85)).

*size*<br/>
окне Размер столбца в байтах.

*участниками*<br/>
окне Переменная члена в классе данных, в которой хранятся данные.

#### <a name="remarks"></a>Примечания

Аналогично [PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md) , но также позволяет указать тип данных столбца, а также размер.

### <a name="provider_column_entry_wstr"></a><a name="provider_column_entry_wstr"></a> PROVIDER_COLUMN_ENTRY_WSTR

Представляет конкретный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_WSTR(name, ordinal, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
окне Имя столбца.

*ordinal*<br/>
окне Номер столбца. Если столбец не является столбцом закладки, то номер столбца не должен быть равен 0.

*участниками*<br/>
окне Переменная члена в классе данных, в которой хранятся данные.

#### <a name="remarks"></a>Примечания

Используйте этот макрос, если данные столбца представляют собой строку символов Юникода, заканчивающуюся нулем, [DBTYPE_WSTR](/previous-versions/windows/desktop/ms711251(v=vs.85)).

### <a name="begin_schema_map"></a><a name="begin_schema_map"></a> BEGIN_SCHEMA_MAP

Обозначает начало гиперкарты схемы.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_SCHEMA_MAP(SchemaClass);
```

#### <a name="parameters"></a>Параметры

*счемакласс*<br/>
Класс, содержащий карту. Обычно это будет класс сеанса.

#### <a name="remarks"></a>Примечания

Дополнительные сведения о наборах строк схемы см. в разделе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) в Windows SDK.

### <a name="end_schema_map"></a><a name="end_schema_map"></a> END_SCHEMA_MAP

Обозначает конец гиперкарты схемы.

#### <a name="syntax"></a>Синтаксис

```cpp
END_SCHEMA_MAP()
```

#### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md).

### <a name="schema_entry"></a><a name="schema_entry"></a> SCHEMA_ENTRY

Связывает идентификатор GUID с классом.

#### <a name="syntax"></a>Синтаксис

```cpp
SCHEMA_ENTRY(guid,
   rowsetClass);
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
Идентификатор GUID набора строк схемы. Список наборов строк схемы и их идентификаторов GUID см. в разделе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) в *справочнике программиста OLE DB* .

*rowsetClass*<br/>
Класс, который будет создан для представления набора строк схемы.

#### <a name="remarks"></a>Примечания

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) может выполнить запрос к карте для отображения списка идентификаторов GUID или создать набор строк, если ему присвоен идентификатор GUID. Набор строк схемы `IDBSchemaRowsetImpl` создается аналогично `CRowsetImpl` классу, производному от стандартного, за исключением того, что он должен предоставлять `Execute` метод со следующей сигнатурой:

```cpp
HRESULT Execute (LONG* pcRowsAffected,
    ULONG cRestrictions,
    const VARIANT* rgRestrictions);
```

Эта `Execute` функция заполняет данные набора строк. Мастер проектов ATL создает, как описано в [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) в *справочнике программиста OLE DB*, три начальных набора строк схемы в проекте для каждой из трех обязательных OLE DB схем:

- DBSCHEMA_TABLES

- DBSCHEMA_COLUMNS

- DBSCHEMA_PROVIDER_TYPES

Мастер также добавляет три соответствующие записи в карту схемы. Дополнительные сведения об использовании мастера для создания поставщика см. в разделе [Создание поставщика шаблонов OLE DB](../../data/oledb/creating-an-ole-db-provider.md) .

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
[Справочник по шаблонам поставщиков OLE DB](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[Макросы для шаблонов поставщиков OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)
