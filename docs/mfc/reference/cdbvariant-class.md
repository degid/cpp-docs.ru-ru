---
title: Класс Кдбвариант
ms.date: 11/04/2016
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
helpviewer_keywords:
- CDBVariant [MFC], CDBVariant
- CDBVariant [MFC], Clear
- CDBVariant [MFC], m_dwType
- CDBVariant [MFC], m_boolVal
- CDBVariant [MFC], m_chVal
- CDBVariant [MFC], m_dblVal
- CDBVariant [MFC], m_fltVal
- CDBVariant [MFC], m_iVal
- CDBVariant [MFC], m_lVal
- CDBVariant [MFC], m_pbinary
- CDBVariant [MFC], m_pdate
- CDBVariant [MFC], m_pstring
- CDBVariant [MFC], m_pstringA
- CDBVariant [MFC], m_pstringW
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
ms.openlocfilehash: 45a478a5ca6cfb4d9b976a29eae2ae7d98fdd6ee
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223087"
---
# <a name="cdbvariant-class"></a>Класс Кдбвариант

Представляет вариантный тип данных для классов MFC ODBC.

## <a name="syntax"></a>Синтаксис

```
class CDBVariant
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кдбвариант:: Кдбвариант](#cdbvariant)|Формирует объект `CDBVariant`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кдбвариант:: Clear](#clear)|Очищает `CDBVariant` объект.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Кдбвариант:: m_dwType](#m_dwtype)|Содержит тип данных текущего сохраненного значения. Введите `DWORD`.|

### <a name="public-union-members"></a>Члены открытых объединений

|Имя|Описание|
|----------|-----------------|
|[Кдбвариант:: m_boolVal](#m_boolval)|Содержит значение типа **bool**.|
|[Кдбвариант:: m_chVal](#m_chval)|Содержит значение типа **`unsigned char`** .|
|[Кдбвариант:: m_dblVal](#m_dblval)|Содержит значение типа **`double`** .|
|[Кдбвариант:: m_fltVal](#m_fltval)|Содержит значение типа **`float`** .|
|[Кдбвариант:: m_iVal](#m_ival)|Содержит значение типа **`short`** .|
|[Кдбвариант:: m_lVal](#m_lval)|Содержит значение типа **`long`** .|
|[Кдбвариант:: m_pbinary](#m_pbinary)|Содержит указатель на объект типа `CLongBinary` .|
|[Кдбвариант:: m_pdate](#m_pdate)|Содержит указатель на объект типа **TIMESTAMP_STRUCT**.|
|[Кдбвариант:: m_pstring](#m_pstring)|Содержит указатель на объект типа `CString` .|
|[Кдбвариант:: m_pstringA](#m_pstringa)|Хранит указатель на объект ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) .|
|[Кдбвариант:: m_pstringW](#m_pstringw)|Хранит указатель на широкий объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) .|

## <a name="remarks"></a>Примечания

`CDBVariant`не имеет базового класса.

`CDBVariant`похоже на [COleVariant](../../mfc/reference/colevariant-class.md); Однако не `CDBVariant` использует OLE. `CDBVariant`позволяет сохранить значение, не беспокоясь о типе данных значения. `CDBVariant`отслеживает тип данных текущего значения, который хранится в объединении.

Класс [CRecordset](../../mfc/reference/crecordset-class.md) использует `CDBVariant` объекты в трех функциях элементов: `GetFieldValue` , `GetBookmark` и `SetBookmark` . Например, `GetFieldValue` позволяет динамически выбирать данные в столбце. Поскольку тип данных столбца может быть неизвестным во время выполнения, `GetFieldValue` использует `CDBVariant` объект для хранения данных столбца.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDBVariant`

## <a name="requirements"></a>Требования

**Заголовок:** афксдб.h

## <a name="cdbvariantcdbvariant"></a><a name="cdbvariant"></a>Кдбвариант:: Кдбвариант

Создает объект NULL `CDBVariant` .

```
CDBVariant();
```

### <a name="remarks"></a>Примечания

Задает элемент данных [m_dwType](#m_dwtype) для DBVT_NULL.

## <a name="cdbvariantclear"></a><a name="clear"></a>Кдбвариант:: Clear

Вызовите эту функцию члена, чтобы очистить `CDBVariant` объект.

```cpp
void Clear();
```

### <a name="remarks"></a>Примечания

Если значение элемента данных [m_dwType](#m_dwtype) DBVT_DATE, DBVT_STRING или DBVT_BINARY, `Clear` освобождает память, связанную с элементом-указателем объединения. `Clear`Задает `m_dwType` значение DBVT_NULL.

`CDBVariant`Деструктор вызывает `Clear` .

## <a name="cdbvariantm_boolval"></a><a name="m_boolval"></a>Кдбвариант:: m_boolVal

Сохраняет значение типа BOOL.

### <a name="remarks"></a>Примечания

`m_boolVal`Элемент данных принадлежит объединению. Прежде чем обращаться к `m_boolVal` , сначала проверьте значение [кдбвариант:: m_dwType](#m_dwtype). Если параметр `m_dwType` имеет значение DBVT_BOOL, то `m_boolVal` будет содержать допустимое значение. в противном случае при доступе `m_boolVal` будут получены ненадежные результаты.

## <a name="cdbvariantm_chval"></a><a name="m_chval"></a>Кдбвариант:: m_chVal

Сохраняет значение типа **`unsigned char`** .

### <a name="remarks"></a>Примечания

`m_chVal`Элемент данных принадлежит объединению. Прежде чем обращаться к `m_chVal` , сначала проверьте значение [кдбвариант:: m_dwType](#m_dwtype). Если параметр `m_dwType` имеет значение DBVT_UCHAR, то `m_chVal` содержит допустимое значение. в противном случае при доступе `m_chVal` будут получены ненадежные результаты.

## <a name="cdbvariantm_dblval"></a><a name="m_dblval"></a>Кдбвариант:: m_dblVal

Сохраняет значение типа **`double`** .

### <a name="remarks"></a>Примечания

`m_dblVal`Элемент данных принадлежит объединению. Прежде чем обращаться к `m_dblVal` , сначала проверьте значение [кдбвариант:: m_dwType](#m_dwtype). Если параметр `m_dwType` имеет значение DBVT_DOUBLE, то `m_dblVal` содержит допустимое значение. в противном случае при доступе `m_dblVal` будут получены ненадежные результаты.

## <a name="cdbvariantm_dwtype"></a><a name="m_dwtype"></a>Кдбвариант:: m_dwType

Этот элемент данных содержит тип данных для значения, хранящегося в данный момент в `CDBVariant` элементе данных объединения объекта.

### <a name="remarks"></a>Примечания

Перед обращением к этому объединению необходимо проверить значение, `m_dwType` чтобы определить, к какому элементу данных Union будет осуществляться доступ. В следующей таблице перечислены возможные значения для `m_dwType` и соответствующего элемента Union Data.

|m_dwType|Элемент данных Union|
|---------------|-----------------------|
|DBVT_NULL|Нет допустимого члена Union для доступа.|
|DBVT_BOOL|[m_boolVal](#m_boolval)|
|DBVT_UCHAR|[m_chVal](#m_chval)|
|DBVT_SHORT|[m_iVal](#m_ival)|
|DBVT_LONG|[m_lVal](#m_lval)|
|DBVT_SINGLE|[m_fltVal](#m_fltval)|
|DBVT_DOUBLE|[m_dblVal](#m_dblval)|
|DBVT_DATE|[m_pdate](#m_pdate)|
|DBVT_STRING|[m_pstring](#m_pstring)|
|DBVT_BINARY|[m_pbinary](#m_pbinary)|
|DBVT_ASTRING|[m_pstringA](#m_pstringa)|
|DBVT_WSTRING|[m_pstringW](#m_pstringw)|

## <a name="cdbvariantm_fltval"></a><a name="m_fltval"></a>Кдбвариант:: m_fltVal

Сохраняет значение типа **`float`** .

### <a name="remarks"></a>Примечания

`m_fltVal`Элемент данных принадлежит объединению. Прежде чем обращаться к `m_fltVal` , сначала проверьте значение [кдбвариант:: m_dwType](#m_dwtype). Если параметр `m_dwType` имеет значение DBVT_SINGLE, то `m_fltVal` содержит допустимое значение. в противном случае при доступе `m_fltVal` будут получены ненадежные результаты.

## <a name="cdbvariantm_ival"></a><a name="m_ival"></a>Кдбвариант:: m_iVal

Сохраняет значение типа **`short`** .

### <a name="remarks"></a>Примечания

`m_iVal`Элемент данных принадлежит объединению. Прежде чем обращаться к `m_iVal` , сначала проверьте значение [кдбвариант:: m_dwType](#m_dwtype). Если параметр `m_dwType` имеет значение DBVT_SHORT, то `m_iVal` содержит допустимое значение. в противном случае при доступе `m_iVal` будут получены ненадежные результаты.

## <a name="cdbvariantm_lval"></a><a name="m_lval"></a>Кдбвариант:: m_lVal

Сохраняет значение типа **`long`** .

### <a name="remarks"></a>Примечания

`m_lVal`Элемент данных принадлежит объединению. Прежде чем обращаться к `m_lVal` , сначала проверьте значение [кдбвариант:: m_dwType](#m_dwtype). Если параметр `m_dwType` имеет значение DBVT_LONG, то `m_lVal` содержит допустимое значение. в противном случае при доступе `m_lVal` будут получены ненадежные результаты.

## <a name="cdbvariantm_pbinary"></a><a name="m_pbinary"></a>Кдбвариант:: m_pbinary

Хранит указатель на объект типа [CLongBinary](../../mfc/reference/clongbinary-class.md).

### <a name="remarks"></a>Примечания

`m_pbinary`Элемент данных принадлежит объединению. Прежде чем обращаться к `m_pbinary` , сначала проверьте значение [кдбвариант:: m_dwType](#m_dwtype). Если параметр `m_dwType` имеет значение DBVT_BINARY, то `m_pbinary` содержит допустимый указатель; в противном случае при доступе `m_pbinary` будут получены ненадежные результаты.

## <a name="cdbvariantm_pdate"></a><a name="m_pdate"></a>Кдбвариант:: m_pdate

Хранит указатель на объект типа TIMESTAMP_STRUCT.

### <a name="remarks"></a>Примечания

`m_pdate`Элемент данных принадлежит объединению. Прежде чем обращаться к `m_pdate` , сначала проверьте значение [кдбвариант:: m_dwType](#m_dwtype). Если параметр `m_dwType` имеет значение DBVT_DATE, то `m_pdate` содержит допустимый указатель; в противном случае при доступе `m_pdate` будут получены ненадежные результаты.

Дополнительные сведения о типе данных TIMESTAMP_STRUCT см. в разделе [типы данных](/sql/odbc/reference/appendixes/c-data-types) в приложении D *Справочника программиста по ODBC* в Windows SDK.

## <a name="cdbvariantm_pstring"></a><a name="m_pstring"></a>Кдбвариант:: m_pstring

Хранит указатель на объект типа [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Примечания

`m_pstring`Элемент данных принадлежит объединению. Прежде чем обращаться к `m_pstring` , сначала проверьте значение [кдбвариант:: m_dwType](#m_dwtype). Если параметр `m_dwType` имеет значение DBVT_STRING, то `m_pstring` содержит допустимый указатель; в противном случае при доступе `m_pstring` будут получены ненадежные результаты.

## <a name="cdbvariantm_pstringa"></a><a name="m_pstringa"></a>Кдбвариант:: m_pstringA

Хранит указатель на объект ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Примечания

`m_pstringA`Элемент данных принадлежит объединению. Прежде чем обращаться к `m_pstringA` , сначала проверьте значение [кдбвариант:: m_dwType](#m_dwtype). Если параметр `m_dwType` имеет значение DBVT_ASTRING, то `m_pstringA` содержит допустимый указатель; в противном случае при доступе `m_pstringA` будут получены ненадежные результаты.

## <a name="cdbvariantm_pstringw"></a><a name="m_pstringw"></a>Кдбвариант:: m_pstringW

Хранит указатель на широкий объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Примечания

`m_pstringW`Элемент данных принадлежит объединению. Прежде чем обращаться к `m_pstringW` , сначала проверьте значение [кдбвариант:: m_dwType](#m_dwtype). Если параметр `m_dwType` имеет значение DBVT_WSTRING, то `m_pstringW` содержит допустимый указатель; в противном случае при доступе `m_pstringW` будут получены ненадежные результаты.

## <a name="see-also"></a>См. также статью

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)
