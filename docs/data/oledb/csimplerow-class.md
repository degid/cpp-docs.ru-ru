---
title: Класс CSimpleRow
ms.date: 11/04/2016
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
- CSimpleRow::AddRefRow
- AddRefRow
- ATL.CSimpleRow.AddRefRow
- ATL::CSimpleRow::AddRefRow
- CSimpleRow.AddRefRow
- CSimpleRow.Compare
- CSimpleRow::Compare
- ATL::CSimpleRow::CSimpleRow
- CSimpleRow.CSimpleRow
- ATL.CSimpleRow.CSimpleRow
- CSimpleRow::CSimpleRow
- ATL::CSimpleRow::ReleaseRow
- CSimpleRow::ReleaseRow
- ReleaseRow
- CSimpleRow.ReleaseRow
- ATL.CSimpleRow.ReleaseRow
- CSimpleRow.m_dwRef
- CSimpleRow::m_dwRef
- CSimpleRow::m_iRowset
- CSimpleRow.m_iRowset
helpviewer_keywords:
- CSimpleRow class
- AddRefRow method
- Compare method
- CSimpleRow class, constructor
- ReleaseRow method
- m_dwRef
- m_iRowset
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
ms.openlocfilehash: c332fc0c653bbde3a69421b8166d4d099eaeeaf4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841081"
---
# <a name="csimplerow-class"></a>Класс CSimpleRow

Предоставляет реализацию по умолчанию для маркера строки, который используется в классе [IRowsetImpl](../../data/oledb/irowsetimpl-class.md) .

## <a name="syntax"></a>Синтаксис

```cpp
class CSimpleRow
```

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[аддрефров](#addrefrow)|Добавляет счетчик ссылок в дескриптор существующей строки.|
|[Сравнить](#compare)|Сравнивает две строки, чтобы определить, ссылаются ли они на один и тот же экземпляр строки.|
|[CSimpleRow](#csimplerow)|Конструктор.|
|[релеасеров](#releaserow)|Высвобождает строки.|

### <a name="data-members"></a>Элементы данных

| Имя | Описание |
|-|-|
|[m_dwRef](#dwref)|Счетчик ссылок на существующий маркер строки.|
|[m_iRowset](#irowset)|Индекс набора строк, представляющего курсор.|

## <a name="remarks"></a>Примечания

Маркер строки логически является уникальным тегом для результирующей строки. `IRowsetImpl` создает новый `CSimpleRow` для каждой строки, запрошенной в [IRowsetImpl:: GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md). `CSimpleRow` также можно заменить собственной реализацией маркера строки, так как это аргумент шаблона по умолчанию для `IRowsetImpl` . Единственным требованием для замены этого класса является то, чтобы класс замены предоставил конструктор, принимающий один параметр типа **Long**.

## <a name="csimplerowaddrefrow"></a><a name="addrefrow"></a> CSimpleRow:: Аддрефров

Добавляет счетчик ссылок к существующему маркеру строки в безопасном для потоков режиме.

### <a name="syntax"></a>Синтаксис

```cpp
DWORD AddRefRow();
```

## <a name="csimplerowcompare"></a><a name="compare"></a> CSimpleRow:: Compare

Сравнивает две строки, чтобы определить, ссылаются ли они на один и тот же экземпляр строки.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Compare(CSimpleRow* pRow);
```

#### <a name="parameters"></a>Параметры

*pRow*<br/>
Указатель на объект `CSimpleRow`.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, обычно S_OK, указывающее, что две строки являются одним и тем же экземпляром строки, или S_FALSE, указывая, что две строки различаются. Другие возможные возвращаемые значения см. в разделе [ировсетидентити:: IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) в *справочнике по программисту OLE DB* .

## <a name="csimplerowcsimplerow"></a><a name="csimplerow"></a> CSimpleRow:: CSimpleRow

Конструктор.

### <a name="syntax"></a>Синтаксис

```cpp
CSimpleRow(DBCOUNTITEM iRowsetCur);
```

#### <a name="parameters"></a>Параметры

*ировсеткур*<br/>
окне Индекс текущего набора строк.

### <a name="remarks"></a>Примечания

Задает для [m_iRowset](../../data/oledb/csimplerow-m-irowset.md) значение *ировсеткур*.

## <a name="csimplerowreleaserow"></a><a name="releaserow"></a> CSimpleRow:: Релеасеров

Освобождает строки в безопасном для потоков режиме.

### <a name="syntax"></a>Синтаксис

```cpp
DWORD ReleaseRow();
```

## <a name="csimplerowm_dwref"></a><a name="dwref"></a> CSimpleRow:: m_dwRef

Счетчик ссылок на существующий маркер строки.

### <a name="syntax"></a>Синтаксис

```cpp
DWORD m_dwRef;
```

## <a name="csimplerowm_irowset"></a><a name="irowset"></a> CSimpleRow:: m_iRowset

Индекс набора строк, представляющего курсор.

### <a name="syntax"></a>Синтаксис

```cpp
KeyType m_iRowset;
```

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)
