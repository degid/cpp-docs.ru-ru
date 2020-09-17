---
title: Класс IRowsetImpl
ms.date: 11/04/2016
f1_keywords:
- IRowsetImpl
- IRowsetImpl::AddRefRows
- IRowsetImpl.AddRefRows
- ATL::IRowsetImpl::AddRefRows
- ATL.IRowsetImpl.AddRefRows
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
- ATL.IRowsetImpl.GetData
- ATL::IRowsetImpl::GetData
- IRowsetImpl::GetData
- IRowsetImpl.GetData
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
- GetNextRows
- ATL.IRowsetImpl.GetNextRows
- ATL::IRowsetImpl::GetNextRows
- IRowsetImpl::GetNextRows
- IRowsetImpl.GetNextRows
- IRowsetImpl.IRowsetImpl
- ATL::IRowsetImpl::IRowsetImpl
- ATL.IRowsetImpl.IRowsetImpl
- IRowsetImpl::IRowsetImpl
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
- ATL.IRowsetImpl.ReleaseRows
- IRowsetImpl::ReleaseRows
- ATL::IRowsetImpl::ReleaseRows
- IRowsetImpl.ReleaseRows
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
- ATL.IRowsetImpl.m_bCanFetchBack
- ATL::IRowsetImpl::m_bCanFetchBack
- IRowsetImpl.m_bCanFetchBack
- IRowsetImpl::m_bCanFetchBack
- m_bCanFetchBack
- IRowsetImpl::m_bCanScrollBack
- ATL::IRowsetImpl::m_bCanScrollBack
- IRowsetImpl.m_bCanScrollBack
- ATL.IRowsetImpl.m_bCanScrollBack
- m_bCanScrollBack
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
- IRowsetImpl::m_iRowset
- IRowsetImpl.m_iRowset
- ATL::IRowsetImpl::m_iRowset
- ATL.IRowsetImpl.m_iRowset
- m_iRowset
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
helpviewer_keywords:
- IRowsetImpl class
- AddRefRows method
- CreateRow method
- GetData method [OLE DB]
- GetDBStatus method
- GetNextRows method
- IRowsetImpl constructor
- RefRows method
- ReleaseRows method
- RestartPosition method
- SetDBStatus method
- m_bCanFetchBack
- m_bCanScrollBack
- m_bReset
- m_iRowset
- m_rgRowHandles
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
ms.openlocfilehash: 470755744783272245ca3aa8e4b57e2943db5fae
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840405"
---
# <a name="irowsetimpl-class"></a>Класс IRowsetImpl

Предоставляет реализацию интерфейса `IRowset`.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   class T,
   class RowsetInterface,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <
      RowClass::KeyType,
      RowClass*>>
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IRowsetImpl` .

*ровсетинтерфаце*<br/>
Класс, производный от `IRowsetImpl` .

*ровкласс*<br/>
Единица хранения для `HROW` .

*мапкласс*<br/>
Единица хранения для всех дескрипторов строк, удерживаемых поставщиком.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[аддрефровс](#addrefrows)|Добавляет счетчик ссылок в дескриптор существующей строки.|
|[креатеров](#createrow)|Вызывается методом [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) для выделения нового `HROW` . Не вызывается непосредственно пользователем.|
|[GetData](#getdata)|Извлекает данные из копии набора строк для строки.|
|[жетдбстатус](#getdbstatus)|Возвращает состояние указанного поля.|
|[GetNextRows](#getnextrows)|Последовательно извлекает строки с запоминанием предыдущей позиции.|
|[IRowsetImpl](#irowsetimpl)|Конструктор. Не вызывается непосредственно пользователем.|
|[рефровс](#refrows)|Вызывается с помощью [аддрефровс](../../data/oledb/irowsetimpl-addrefrows.md) и [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md). Не вызывается непосредственно пользователем.|
|[ReleaseRows](#releaserows)|Высвобождает строки.|
|[Свойство RestartPosition](#restartposition)|Перемещает расположение следующей выборки в исходное расположение; то есть его расположение при первом создании набора строк.|
|[сетдбстатус](#setdbstatus)|Задает флаги состояния для указанного поля.|

### <a name="data-members"></a>Элементы данных

| Имя | Описание |
|-|-|
|[m_bCanFetchBack](#bcanfetchback)|Указывает, поддерживает ли поставщик обратную выборку.|
|[m_bCanScrollBack](#bcanscrollback)|Указывает, может ли поставщик прокручивать курсор назад.|
|[m_bReset](#breset)|Указывает, сброшен ли поставщик позицию курсора. Это имеет особое значение при прокрутке в обратном направлении или в обратном направлении в [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md).|
|[m_iRowset](#irowset)|Индекс набора строк, представляющий курсор.|
|[m_rgRowHandles](#rgrowhandles)|Список дескрипторов строк.|

## <a name="remarks"></a>Примечания

[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85)) — это базовый интерфейс набора строк.

## <a name="irowsetimpladdrefrows"></a><a name="addrefrows"></a> IRowsetImpl:: Аддрефровс

Добавляет счетчик ссылок в дескриптор существующей строки.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(AddRefRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowset:: аддрефровс](/previous-versions/windows/desktop/ms719619(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetimplcreaterow"></a><a name="createrow"></a> IRowsetImpl:: Креатеров

Вспомогательный метод, вызываемый [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) для выделения нового `HROW` .

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CreateRow(DBROWOFFSET lRowsOffset,
   DBCOUNTITEM& cRowsObtained,
   HROW* rgRows);
```

#### <a name="parameters"></a>Параметры

*лровсоффсет*<br/>
Позиции курсора создаваемой строки.

*кровсобтаинед*<br/>
Ссылка, которая передается обратно пользователю, указывая количество созданных строк.

*ргровс*<br/>
Массив s, `HROW` возвращенный вызывающему объекту с вновь созданными дескрипторами строк.

### <a name="remarks"></a>Примечания

Если строка существует, этот метод вызывает [аддрефровс](../../data/oledb/irowsetimpl-addrefrows.md) и возвращает. В противном случае он выделяет новый экземпляр переменной шаблона Ровкласс и добавляет его в [m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md).

## <a name="irowsetimplgetdata"></a><a name="getdata"></a> IRowsetImpl:: GetData

Извлекает данные из копии набора строк для строки.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pDstData);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowset:: GetData](/previous-versions/windows/desktop/ms716988(v=vs.85)) в *справочнике по OLE DB программиста*.

Некоторые параметры соответствуют *OLE DB ссылочным параметрам программиста* с разными именами, которые описаны в `IRowset::GetData` :

|OLE DB параметры шаблона|*OLE DB ссылочные параметры программиста*|
|--------------------------------|------------------------------------------------|
|*пдстдата*|*pData*|

### <a name="remarks"></a>Примечания

Также обрабатывает преобразование данных с помощью OLE DB библиотеки DLL преобразования данных.

## <a name="irowsetimplgetdbstatus"></a><a name="getdbstatus"></a> IRowsetImpl:: Жетдбстатус

Возвращает флаги состояния ДБСТАТУС для указанного поля.

### <a name="syntax"></a>Синтаксис

```cpp
virtual DBSTATUS GetDBStatus(RowClass* currentRow,
   ATLCOLUMNINFO* columnNames);
```

#### <a name="parameters"></a>Параметры

*куррентров*<br/>
окне Текущая строка.

*columnNames*<br/>
окне Столбец, для которого запрашивается состояние.

### <a name="return-value"></a>Возвращаемое значение

Флаги [дбстатус](/previous-versions/windows/desktop/ms722617(v=vs.85)) для столбца.

## <a name="irowsetimplgetnextrows"></a><a name="getnextrows"></a> IRowsetImpl:: GetNextRows

Последовательно извлекает строки с запоминанием предыдущей позиции.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetNextRows )(HCHAPTER hReserved,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowset:: GetNextRows](/previous-versions/windows/desktop/ms709827(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetimplirowsetimpl"></a><a name="irowsetimpl"></a> IRowsetImpl:: IRowsetImpl

Конструктор.

### <a name="syntax"></a>Синтаксис

```cpp
IRowsetImpl();
```

### <a name="remarks"></a>Примечания

Обычно не требуется вызывать этот метод напрямую.

## <a name="irowsetimplrefrows"></a><a name="refrows"></a> IRowsetImpl:: Рефровс

Вызывается методами [аддрефровс](../../data/oledb/irowsetimpl-addrefrows.md) и [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) для увеличения или освобождения счетчика ссылок до существующего маркера строки.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT RefRows(DBCOUNTITEM cRows,
   const HROWrghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[],
   BOOL bAdd);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowset:: аддрефровс](/previous-versions/windows/desktop/ms719619(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="irowsetimplreleaserows"></a><a name="releaserows"></a> IRowsetImpl:: ReleaseRows

Высвобождает строки.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(ReleaseRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWOPTIONS rgRowOptions[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowset:: ReleaseRows](/previous-versions/windows/desktop/ms719771(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetimplrestartposition"></a><a name="restartposition"></a> IRowsetImpl:: свойство RestartPosition

Перемещает расположение следующей выборки в исходное расположение; то есть его расположение при первом создании набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowset:: свойство RestartPosition](/previous-versions/windows/desktop/ms712877(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Расположение набора строк не определено до `GetNextRow` вызова метода. Можно перемещаться назад в ровет, вызывая `RestartPosition` , а затем получая или прокручивать обратную сторону.

## <a name="irowsetimplsetdbstatus"></a><a name="setdbstatus"></a> IRowsetImpl:: Сетдбстатус

Задает флаги состояния ДБСТАТУС для указанного поля.

### <a name="syntax"></a>Синтаксис

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,
   RowClass* currentRow,
   ATLCOLUMNINFO* columnInfo);
```

#### <a name="parameters"></a>Параметры

*статусфлагс*<br/>
Флаги [дбстатус](/previous-versions/windows/desktop/ms722617(v=vs.85)) , которые необходимо задать для столбца.

*куррентров*<br/>
Текущая строка.

*columnInfo*<br/>
Столбец, для которого задается состояние.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Поставщик переопределяет эту функцию, чтобы обеспечить специальную обработку DBSTATUS_S_ISNULL и DBSTATUS_S_DEFAULT.

## <a name="irowsetimplm_bcanfetchback"></a><a name="bcanfetchback"></a> IRowsetImpl:: m_bCanFetchBack

Указывает, поддерживает ли поставщик обратную выборку.

### <a name="syntax"></a>Синтаксис

```cpp
unsigned m_bCanFetchBack:1;
```

### <a name="remarks"></a>Примечания

Связано со `DBPROP_CANFETCHBACKWARDS` свойством в `DBPROPSET_ROWSET` группе. Поставщик должен поддерживать `DBPROP_CANFETCHBACKWARDS` `m_bCanFetchBackwards` **`true`** .

## <a name="irowsetimplm_bcanscrollback"></a><a name="bcanscrollback"></a> IRowsetImpl:: m_bCanScrollBack

Указывает, может ли поставщик прокручивать курсор назад.

### <a name="syntax"></a>Синтаксис

```cpp
unsigned  m_bCanScrollBack:1;
```

### <a name="remarks"></a>Примечания

Связано со `DBPROP_CANSCROLLBACKWARDS` свойством в `DBPROPSET_ROWSET` группе. Поставщик должен поддерживать `DBPROP_CANSCROLLBACKWARDS` `m_bCanFetchBackwards` **`true`** .

## <a name="irowsetimplm_breset"></a><a name="breset"></a> IRowsetImpl:: m_bReset

Битовый флаг, используемый для определения положения курсора в наборе строк.

### <a name="syntax"></a>Синтаксис

```cpp
unsigned m_bReset:1;
```

### <a name="remarks"></a>Примечания

Если потребитель вызывает [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) с отрицательным `lOffset` или *CRowset* и `m_bReset` имеет значение true, `GetNextRows` переходит к концу набора строк. Если `m_bReset` имеет значение false, потребитель получает код ошибки в соответствие со спецификацией OLE DB. `m_bReset`Флаг получает значение, **`true`** когда набор строк создается впервые и когда потребитель вызывает [IRowsetImpl:: свойство RestartPosition](../../data/oledb/irowsetimpl-restartposition.md). Он получает значение **`false`** при вызове метода `GetNextRows` .

## <a name="irowsetimplm_irowset"></a><a name="irowset"></a> IRowsetImpl:: m_iRowset

Индекс набора строк, представляющий курсор.

### <a name="syntax"></a>Синтаксис

```cpp
DBROWOFFSET m_iRowset;
```

## <a name="irowsetimplm_rgrowhandles"></a><a name="rgrowhandles"></a> IRowsetImpl:: m_rgRowHandles

Схема дескрипторов строк, которые в настоящее время содержатся в поставщике в ответ на `GetNextRows` .

### <a name="syntax"></a>Синтаксис

```cpp
MapClass m_rgRowHandles;
```

### <a name="remarks"></a>Примечания

Дескрипторы строк удаляются путем вызова метода `ReleaseRows` . Определение *мапкласс*см. в [обзоре IRowsetImpl](../../data/oledb/irowsetimpl-class.md) .

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Класс CSimpleRow](../../data/oledb/csimplerow-class.md)
