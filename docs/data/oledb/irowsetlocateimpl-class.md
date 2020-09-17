---
title: Класс IRowsetLocateImpl
ms.date: 11/04/2016
f1_keywords:
- IRowsetLocateImpl
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
- GetRowsAt
- IRowsetLocateImpl.GetRowsAt
- ATL::IRowsetLocateImpl::GetRowsAt
- IRowsetLocateImpl::GetRowsAt
- ATL.IRowsetLocateImpl.GetRowsAt
- IRowsetLocateImpl::GetRowsByBookmark
- IRowsetLocateImpl.GetRowsByBookmark
- GetRowsByBookmark
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
- m_rgBookmarks
- IRowsetLocateImpl::m_rgBookmarks
- ATL.IRowsetLocateImpl.m_rgBookmarks
- ATL::IRowsetLocateImpl::m_rgBookmarks
- IRowsetLocateImpl.m_rgBookmarks
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
- Compare method
- GetRowsAt method
- GetRowsByBookmark method
- Hash method
- m_rgbookmarks
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
ms.openlocfilehash: a45b7ef1a31c3ecf34b15ee35bce48559465a905
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840314"
---
# <a name="irowsetlocateimpl-class"></a>Класс IRowsetLocateImpl

Реализует интерфейс OLE DB [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) , который извлекает произвольные строки из набора строк.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   class T,
   class RowsetInterface,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,
   class BookmarkKeyType = LONG,
   class BookmarkType = LONG,
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >>
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<
       T,
       RowsetInterface,
       RowClass,
       MapClass>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IRowsetLocateImpl` .

*ровсетинтерфаце*<br/>
Класс, производный от `IRowsetImpl` .

*ровкласс*<br/>
Единица хранения для `HROW` .

*мапкласс*<br/>
Единица хранения для всех дескрипторов строк, удерживаемых поставщиком.

*букмарккэйтипе*<br/>
Тип закладки, например LONG или String. Длина обычных закладок должна быть не меньше двух байт. (Однобайтовая длина зарезервирована для OLE DB [стандартных закладок](/previous-versions/windows/desktop/ms712954(v=vs.85)) `DBBMK_FIRST` , `DBBMK_LAST` и `DBBMK_INVALID` .)

*букмарктипе*<br/>
Механизм сопоставления для поддержания связей между закладками и данными.

*букмаркмапкласс*<br/>
Единица хранения для всех дескрипторов строк, удерживаемых закладкой.

## <a name="requirements"></a>Требования

**Заголовок**: ATLDB.h

## <a name="members"></a>Элементы

### <a name="interface-methods"></a>Методы интерфейса

| Имя | Описание |
|-|-|
|[Сравнить](#compare)|Сравнивает две закладки.|
|[GetRowsAt](#getrowsat)|Извлекает строки, начиная со строки, указанной смещением, из закладки.|
|[жетровсбибукмарк](#getrowsbybookmark)|Извлекает строки, соответствующие указанным закладкам.|
|[Хэш](#hash)|Возвращает хэш-значения для указанных закладок.|

### <a name="data-members"></a>Элементы данных

| Имя | Описание |
|-|-|
|[m_rgBookmarks](#rgbookmarks)|Массив закладок.|

## <a name="remarks"></a>Примечания

`IRowsetLocateImpl` — Это реализация OLE DB шаблонов интерфейса [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) . `IRowsetLocate` используется для выборки произвольных строк из набора строк. Набор строк, который не реализует этот интерфейс, является `sequential` набором строк. Если имеется `IRowsetLocate` в наборе строк, столбец 0 является закладкой для строк; при чтении этого столбца будет получено значение закладки, которое можно использовать для перемещения в ту же строку.

`IRowsetLocateImpl` используется для реализации поддержки закладок в поставщиках. Закладки — это заполнители (индексы в наборе строк), позволяющие потребителю быстро возвращаться к строке, обеспечивая высокую скорость доступа к данным. Поставщик определяет, какие закладки могут уникально идентифицировать строку. С помощью `IRowsetLocateImpl` методов можно сравнивать закладки, получать строки по смещению, получать строки по закладкам и возвращать хэш-значения для закладок.

Чтобы обеспечить поддержку OLE DB закладок в наборе строк, сделайте набор строк производным от этого класса.

Сведения о реализации поддержки закладок см. в статье [Поддержка поставщиков для закладок](../../data/oledb/provider-support-for-bookmarks.md) в *Visual C++ руководстве программиста* и [закладок](/previous-versions/windows/desktop/ms709728(v=vs.85)) в *справочнике по OLE DB программиста* в пакете SDK для платформы.

## <a name="irowsetlocateimplcompare"></a><a name="compare"></a> IRowsetLocateImpl:: Compare

Сравнивает две закладки.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (Compare )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmark1,
   const BYTE* pBookmark1,
   DBBKMARK cbBookmark2,
   const BYTE* pBookmark2,
   DBCOMPARE* pComparison);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowsetLocate:: Compare](/previous-versions/windows/desktop/ms709539(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Любая из закладок может быть стандартной стандартной [закладкой](/previous-versions/windows/desktop/ms712954(v=vs.85)) OLE DB ( `DBBMK_FIRST` , `DBBMK_LAST` или `DBBMK_INVALID` ). Значение, возвращаемое в, `pComparison` указывает связь между двумя закладками:

- DBCOMPARE_LT (предшествует `cbBookmark1` `cbBookmark2` ).

- DBCOMPARE_EQ ( `cbBookmark1` равно `cbBookmark2` .)

- DBCOMPARE_GT ( `cbBookmark1` находится после `cbBookmark2` ).

- DBCOMPARE_NE (закладки равны и не упорядочены).

- DBCOMPARE_NOTCOMPARABLE (закладки нельзя сравнивать.)

## <a name="irowsetlocateimplgetrowsat"></a><a name="getrowsat"></a> IRowsetLocateImpl:: GetRowsAt

Извлекает строки, начиная со строки, указанной смещением, из закладки.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetRowsAt )(HWATCHREGION /* hReserved1 */,
   HCHAPTER hReserved2,
   DBBKMARK cbBookmark,
   const BYTE* pBookmark,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowsetLocate:: GetRowsAt](/previous-versions/windows/desktop/ms723031(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Чтобы получить из позиции курсора вместо этого, используйте [IRowset:: GetRowsAt](/previous-versions/windows/desktop/ms723031(v=vs.85)).

`IRowsetLocateImpl::GetRowsAt` не изменяет позицию курсора.

## <a name="irowsetlocateimplgetrowsbybookmark"></a><a name="getrowsbybookmark"></a> IRowsetLocateImpl:: Жетровсбибукмарк

Извлекает одну или несколько строк, соответствующих указанным закладкам.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetRowsByBookmark )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const DBBKMARK rgcbBookmarks[],
   const BYTE* rgpBookmarks,
   HROW rghRows[],
   DBROWSTATUS* rgRowStatus[]);
```

#### <a name="parameters"></a>Параметры

*хресервед*<br/>
окне Соответствует параметру *параметру hChapter* в [IRowsetLocate:: жетровсбибукмарк](/previous-versions/windows/desktop/ms725420(v=vs.85)).

Другие параметры см. в разделе [IRowsetLocate:: жетровсбибукмарк](/previous-versions/windows/desktop/ms725420(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Закладка может быть значением, определенным пользователем, или OLE DB [стандартной закладками](/previous-versions/windows/desktop/ms712954(v=vs.85)) ( `DBBMK_FIRST` или `DBBMK_LAST` ). Не изменяет позицию курсора.

## <a name="irowsetlocateimplhash"></a><a name="hash"></a> IRowsetLocateImpl:: hash

Возвращает хэш-значения для указанных закладок.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (Hash )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmarks,
   const DBBKMARK* rgcbBookmarks[],
   const BYTE* rgpBookmarks[],
   DBHASHVALUE rgHashValues[],
   DBROWSTATUS rgBookmarkStatus[]);
```

#### <a name="parameters"></a>Параметры

*хресервед*<br/>
окне Соответствует параметру *параметру hChapter* в [IRowsetLocate:: hash](/previous-versions/windows/desktop/ms709697(v=vs.85)).

Другие параметры см. в разделе [IRowsetLocate:: hash](/previous-versions/windows/desktop/ms709697(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetlocateimplm_rgbookmarks"></a><a name="rgbookmarks"></a> IRowsetLocateImpl:: m_rgBookmarks

Массив закладок.

### <a name="syntax"></a>Синтаксис

```cpp
CAtlArray<DBROWCOUNT> m_rgBookmarks;
```

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetLocate: IRowset](/previous-versions/windows/desktop/ms721190(v=vs.85)) 
 [Поддержка закладок поставщиком](../../data/oledb/provider-support-for-bookmarks.md)<br/>
[Закладки](/previous-versions/windows/desktop/ms709728(v=vs.85))
