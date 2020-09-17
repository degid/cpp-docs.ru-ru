---
title: IDBSchemaRowsetImpl - класс
ms.date: 11/04/2016
f1_keywords:
- IDBSchemaRowsetImpl
- CheckRestrictions
- IDBSchemaRowsetImpl::CheckRestrictions
- IDBSchemaRowsetImpl.CheckRestrictions
- IDBSchemaRowsetImpl::CreateSchemaRowset
- ATL::IDBSchemaRowsetImpl::CreateSchemaRowset
- CreateSchemaRowset
- IDBSchemaRowsetImpl.CreateSchemaRowset
- ATL.IDBSchemaRowsetImpl.CreateSchemaRowset
- IDBSchemaRowsetImpl::SetRestrictions
- SetRestrictions
- IDBSchemaRowsetImpl.SetRestrictions
- ATL::IDBSchemaRowsetImpl::GetRowset
- ATL.IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl<SessionClass>::GetRowset
- IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl::GetRowset
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset
- GetRowset
- ATL::IDBSchemaRowsetImpl::GetSchemas
- GetSchemas
- IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- ATL.IDBSchemaRowsetImpl.GetSchemas
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- IDBSchemaRowsetImpl.GetSchemas
- IDBSchemaRowsetImpl::GetSchemas
helpviewer_keywords:
- IDBSchemaRowsetImpl class
- CheckRestrictions method
- CreateSchemaRowset method
- SetRestrictions method
- GetRowset method
- GetSchemas method
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
ms.openlocfilehash: eea0ebeaf83b9203cf57f7b35fe3dd1ec2d63d81
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844006"
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl - класс

Предоставляет реализацию для наборов строк схемы.

## <a name="syntax"></a>Синтаксис

```cpp
template <class SessionClass>
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset
```

### <a name="parameters"></a>Параметры

*сессионкласс*<br/>
Класс, по которому наследуется `IDBSchemaRowsetImpl` . Как правило, этот класс будет классом сеанса пользователя.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[CheckRestrictions](#checkrestrictions)|Проверяет допустимость ограничений относительно набора строк схемы.|
|[CreateSchemaRowset](#createschemarowset)|Реализует функцию создателя COM-объекта для объекта, указанного параметром шаблона.|
|[SetRestrictions](#setrestrictions)|Указывает, какие ограничения поддерживаются в определенном наборе строк схемы.|

### <a name="interface-methods"></a>Методы интерфейса

| Имя | Описание |
|-|-|
|[GetRowset](#getrowset)|Возвращает набор строк схемы.|
|[GetSchemas](#getschemas)|Возвращает список наборов строк схемы, доступных для [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).|

## <a name="remarks"></a>Примечания

Этот класс реализует интерфейс [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) и шаблонизируемую функцию создателя [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md).

OLE DB использует наборы строк схемы для возврата сведений о данных в поставщике. Такие данные часто называют метаданными. По умолчанию поставщик всегда должен поддерживать `DBSCHEMA_TABLES` , `DBSCHEMA_COLUMNS` и `DBSCHEMA_PROVIDER_TYPES` , как описано в [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) в *справочнике программиста OLE DB*. Наборы строк схемы назначаются в карте схемы. Сведения о карте записей схемы см. в разделе [SCHEMA_ENTRY](../../data/oledb/schema-entry.md).

Мастер поставщиков OLE DB в мастере объектов ATL автоматически создает код для наборов строк схемы в проекте. (По умолчанию мастер поддерживает наборы строк обязательных схем, которые были ранее упомянуты.) При создании объекта-получателя с помощью мастера объектов ATL мастер использует наборы строк схемы для привязки правильных данных к поставщику. Если наборы строк схемы не реализованы для представления правильных метаданных, мастер не выполнит привязку правильных данных.

Сведения о поддержке наборов строк схемы в поставщике см. в разделе [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md).

Дополнительные сведения о наборах строк схемы см. в разделе [Наборы строк схемы](/previous-versions/windows/desktop/ms712921(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="idbschemarowsetimplcheckrestrictions"></a><a name="checkrestrictions"></a> IDBSchemaRowsetImpl:: Чеккрестриктионс

Проверяет допустимость ограничений относительно набора строк схемы.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CheckRestrictions(REFGUID rguidSchema,
   ULONG cRestrictions,  const VARIANT rgRestrictions[]);
```

#### <a name="parameters"></a>Параметры

*ргуидсчема*<br/>
[входные данные] Ссылка на запрошенный GUID набора строк схемы (например, `DBSCHEMA_TABLES`).

*cRestrictions*<br/>
[входные данные] Число ограничений, переданных потребителем для набора строк схемы.

*ргрестриктионс*<br/>
[входные данные] Массив длиной *cRestrictions* для задаваемых значений ограничений. Дополнительные сведения см. в описании параметра *ргрестриктионс* в [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).

### <a name="remarks"></a>Примечания

Используйте `CheckRestrictions` для проверки допустимости ограничений для набора строк схемы. Он проверяет ограничения для `DBSCHEMA_TABLES` `DBSCHEMA_COLUMNS` `DBSCHEMA_PROVIDER_TYPES` наборов строк схемы, и. Вызовите его, чтобы определить, правильно ли вызван потребитель `IDBSchemaRowset::GetRowset` . Если необходима поддержка наборов строк схемы, отличных от перечисленных выше, создайте собственную функцию для выполнения этой задачи.

`CheckRestrictions` Определяет, вызывает ли потребитель [набор строк](../../data/oledb/idbschemarowsetimpl-getrowset.md) с правильным ограничением и правильным типом ограничения (например, VT_BSTR для строки), который поддерживает поставщик. Он также определяет, поддерживается ли правильное количество ограничений. По умолчанию `CheckRestrictions` будет обращаться к поставщику через вызов [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) , ограничения которого он поддерживает в заданном наборе строк. Затем он сравнит ограничения от потребителя с ограничениями, поддерживаемыми поставщиком. Результатом будет успешное или неудачное выполнение.

Дополнительные сведения о наборах строк схемы см. в разделе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) в *справочнике программиста OLE DB* в Windows SDK.

## <a name="idbschemarowsetimplcreateschemarowset"></a><a name="createschemarowset"></a> IDBSchemaRowsetImpl:: Креатесчемаровсет

Реализует функцию создателя COM-объекта для объекта, указанного параметром шаблона.

### <a name="syntax"></a>Синтаксис

```cpp
template template <class SchemaRowsetClass>
HRESULT CreateSchemaRowset(IUnknown *pUnkOuter,
   ULONG cRestrictions,
   const VARIANT rgRestrictions[],
   REFIID riid,
   ULONG cPropertySets,
   DBPROPSET rgPropertySets[],
   IUnknown** ppRowset,
   SchemaRowsetClass*& pSchemaRowset);
```

#### <a name="parameters"></a>Параметры

*пункаутер*<br/>
окне Внешний [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) при статистической обработке; в противном случае — null.

*cRestrictions*<br/>
[входные данные] Число ограничений, применяемых к набору строк.

*ргрестриктионс*<br/>
[входные данные] Массив `cRestrictions`**VARIANT**, применяемых к набору строк.

*riid*<br/>
окне Интерфейс для [QueryInterface](../../atl/queryinterface.md) для выходных данных `IUnknown` .

*cPropertySets*<br/>
[входные данные] Число задаваемых наборов свойств.

*rgPropertySets*<br/>
[входные данные] Массив структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , определяющих задаваемые свойства.

*ppRowset*<br/>
заполняет Исходящий `IUnknown` запрос, запрошенный *riid*. Это `IUnknown` интерфейс для объекта набора строк схемы.

*псчемаровсет*<br/>
[выходные данные] Указатель на экземпляр класса набора строк схемы. Как правило, этот параметр не используется, но может применяться, если необходимо выполнить дополнительные действия в наборе строк схемы перед передачей его в COM-объект. Время существования *псчемаровсет* привязывается *ппровсет*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Эта функция реализует универсальный создатель для всех типов наборов строк схемы. Как правило, пользователь не вызывает эту функцию. Ее вызывает реализация карты схемы.

## <a name="idbschemarowsetimplsetrestrictions"></a><a name="setrestrictions"></a> IDBSchemaRowsetImpl:: SetRestrictions

Указывает, какие ограничения поддерживаются в определенном наборе строк схемы.

### <a name="syntax"></a>Синтаксис

```cpp
void SetRestrictions(ULONG cRestrictions,
   GUID* /* rguidSchema */,
   ULONG* rgRestrictions);
```

#### <a name="parameters"></a>Параметры

*cRestrictions*<br/>
окне Число ограничений в массиве *ргрестриктионс* и число идентификаторов GUID в массиве *ргуидсчема* .

*ргуидсчема*<br/>
[входные данные] Массив GUID наборов строк схемы, для которого требуется извлечь ограничения. Каждый элемент массива содержит GUID одного набора строк схемы (например, `DBSCHEMA_TABLES`).

*ргрестриктионс*<br/>
[входные данные] Массив длиной *cRestrictions* для задаваемых значений ограничений. Каждый элемент соответствует ограничениям в наборе строк схемы, определяемом по GUID. Если набор строк схемы не поддерживается поставщиком, элементу присваивается нулевое значение. В противном случае значение **ULONG** значение содержит битовую маску, которая представляет ограничения, поддерживаемые в этом наборе строк схемы. Дополнительные сведения о том, какие ограничения соответствуют определенному набору строк схемы, см. в таблице идентификаторов GUID набора строк схемы в [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) в *справочнике по OLE DB программисту* в Windows SDK.

### <a name="remarks"></a>Примечания

`IDBSchemaRowset`Объект вызывает метод, `SetRestrictions` чтобы определить, какие ограничения поддерживаются в определенном наборе строк схемы (он вызывается методами [GetSchema](../../data/oledb/idbschemarowsetimpl-getschemas.md) через переданный указатель). Ограничения позволяют выбирать только совпадающие строки (например, поиск всех столбцов в таблице MyTable). Ограничения являются необязательными, и если не поддерживается ни одно ограничение (по умолчанию), всегда возвращаются все данные.

Реализация по умолчанию этого метода устанавливает для элементов массива *ргрестриктионс* значение 0. Чтобы задать ограничения, отличные от используемых по умолчанию, нужно переопределить установку по умолчанию в классе сеанса.

Сведения о реализации поддержки наборов строк схемы см. в разделе [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md).

Пример поставщика, поддерживающего наборы строк схемы, см. в примере [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) .

Дополнительные сведения о наборах строк схемы см. в разделе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) в *справочнике программиста OLE DB* в Windows SDK.

## <a name="idbschemarowsetimplgetrowset"></a><a name="getrowset"></a> IDBSchemaRowsetImpl:: Rowset

Возвращает набор строк схемы.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetRowset)(IUnknown *pUnkOuter,
   REFGUID rguidSchema,
   ULONG cRestrictions,
   const VARIANT rgRestrictions[],
   REFIID riid,
   ULONG cPropertySets,
   DBPROPSET rgPropertySets[],
   IUnknown **ppRowset);
```

#### <a name="parameters"></a>Параметры

*пункаутер*<br/>
окне Внешний `IUnknown` при статистической обработке; в противном случае — null.

*ргуидсчема*<br/>
[входные данные] Ссылка на запрошенный GUID набора строк схемы (например, `DBSCHEMA_TABLES`).

*cRestrictions*<br/>
[входные данные] Число ограничений, применяемых к набору строк.

*ргрестриктионс*<br/>
[входные данные] Массив типов `cRestrictions`**VARIANT**, которые представляют ограничения.

*riid*<br/>
[входные данные] IID для запроса созданного набора строк схемы.

*cPropertySets*<br/>
[входные данные] Число задаваемых наборов свойств.

*rgPropertySets*<br/>
[входные/выходные данные] Массив структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , задаваемых в созданном наборе строк схемы.

*ppRowset*<br/>
[выходные данные] Указатель на запрошенный интерфейс в созданном наборе строк схемы.

### <a name="remarks"></a>Примечания

Для реализаций этого метода пользователь должен иметь карту схемы в классе сеанса. С помощью сведений о схеме схемы `GetRowset` создает заданный объект набора строк, если параметр *ргуидсчема* РАВЕН одному из идентификаторов GUID записей Map. Описание карты записей см. в разделе [SCHEMA_ENTRY](../../data/oledb/schema-entry.md) .

См. раздел [IDBSchemaRowset:: Rowset](/previous-versions/windows/desktop/ms722634(v=vs.85)) в Windows SDK.

## <a name="idbschemarowsetimplgetschemas"></a><a name="getschemas"></a> IDBSchemaRowsetImpl:: GetSchema

Возвращает список наборов строк схемы, доступных для [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetSchema s )(ULONG * pcSchemas,
   GUID ** prgSchemas,
   ULONG** prgRest);
```

#### <a name="parameters"></a>Параметры

*pcSchemas*<br/>
[выходные данные] Указатель на **ULONG** , заполняемый количеством схем.

*prgSchemas*<br/>
[выходные данные] Указатель на массив идентификаторов GUID, который заполняется указателем на массив идентификаторов GUID набора строк схемы.

*prgRest*<br/>
[выходные данные] Указатель на массив **ULONG**, который должен быть заполнен массивом ограничений.

### <a name="remarks"></a>Примечания

Этот метод возвращает массив всех наборов строк схемы, поддерживаемых поставщиком. См. раздел [IDBSchemaRowset:: GetSchema](/previous-versions/windows/desktop/ms719605(v=vs.85)) в Windows SDK.

Для реализаций этой функции пользователь должен иметь карту схемы в классе сеанса. Затем с помощью сведений о карте схемы выдается массив идентификаторов GUID для схемы на карте. Он представляет схемы, поддерживаемые поставщиком.

## <a name="see-also"></a>См. также раздел

[Классы наборов строк схемы и классы typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)<br/>
[Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md)<br/>
[SCHEMA_ENTRY](../../data/oledb/schema-entry.md)<br/>
[UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider)
