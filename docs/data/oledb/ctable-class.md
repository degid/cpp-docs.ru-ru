---
title: Класс CTable
ms.date: 11/04/2016
f1_keywords:
- ATL::CTable
- ATL.CTable
- CTable
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
helpviewer_keywords:
- CTable class
- Open method
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
ms.openlocfilehash: a967ef8fa2832afd56442ae4f988ba080d0b2872
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845644"
---
# <a name="ctable-class"></a>Класс CTable

Предоставляет средства для прямого доступа к простому набору строк (один без параметров).

## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CNoAccessor,
            template <typename T> class TRowset = CRowset>
class CTable :
   public CAccessorRowset <TAccessor, TRowset>
```

### <a name="parameters"></a>Параметры

*такцессор*<br/>
Класс метода доступа.

*тровсет*<br/>
Класс набора строк.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[Открыть](#open)|Открывает таблицу.|

## <a name="remarks"></a>Примечания

Сведения о том, как выполнить команду для доступа к набору строк, см. в разделе [CCommand](../../data/oledb/ccommand-class.md) .

## <a name="ctableopen"></a><a name="open"></a> CTable:: Open

Открывает таблицу.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Open(const CSession& session,
   LPCWSTR wszTableName,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();

HRESULT Open(const CSession& session,
   LPCSTR szTableName,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();

HRESULT Open(const CSession& session,
   DBID& dbid,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();
```

#### <a name="parameters"></a>Параметры

*сессии*<br/>
окне Сеанс, для которого открыта таблица.

*всзтабленаме*<br/>
окне Имя открываемой таблицы, передаваемое в виде строки Юникода.

*сзтабленаме*<br/>
окне Имя открываемой таблицы, передаваемое как строка ANSI.

*DBID*<br/>
окне `DBID` Открываемой таблицы.

*pPropSet*<br/>
окне Указатель на массив структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , содержащий свойства и значения, которые необходимо задать. См. раздел [наборы свойств и группы свойств](/previous-versions/windows/desktop/ms713696(v=vs.85)) в *справочнике по OLE DB программисту* в Windows SDK. Значение по умолчанию NULL указывает на отсутствие свойств.

*улпропсетс*<br/>
окне Число структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) , переданных в аргументе *ппропсет* .

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [IOpenRowset:: OPENROWSET](/previous-versions/windows/desktop/ms716724(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
