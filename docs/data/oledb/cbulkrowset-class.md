---
title: Класс CBulkRowset
ms.date: 11/04/2016
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
- CBulkRowset::AddRefRows
- CBulkRowset.AddRefRows
- ATL.CBulkRowset<TAccessor>.AddRefRows
- ATL::CBulkRowset::AddRefRows
- CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset.AddRefRows
- ATL::CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset<TAccessor>.CBulkRowset
- ATL::CBulkRowset::CBulkRowset
- CBulkRowset.CBulkRowset
- CBulkRowset::CBulkRowset
- ATL.CBulkRowset.CBulkRowset
- ATL::CBulkRowset<TAccessor>::CBulkRowset
- CBulkRowset<TAccessor>::CBulkRowset
- ATL.CBulkRowset.MoveFirst
- CBulkRowset<TAccessor>.MoveFirst
- ATL.CBulkRowset<TAccessor>.MoveFirst
- ATL::CBulkRowset::MoveFirst
- ATL::CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset::MoveFirst
- CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset.MoveFirst
- CBulkRowset.MoveLast
- ATL.CBulkRowset.MoveLast
- ATL::CBulkRowset<TAccessor>::MoveLast
- CBulkRowset::MoveLast
- CBulkRowset<TAccessor>.MoveLast
- ATL::CBulkRowset::MoveLast
- ATL.CBulkRowset<TAccessor>.MoveLast
- CBulkRowset<TAccessor>::MoveLast
- ATL.CBulkRowset<TAccessor>.MoveNext
- ATL::CBulkRowset::MoveNext
- CBulkRowset::MoveNext
- ATL.CBulkRowset.MoveNext
- CBulkRowset.MoveNext
- ATL::CBulkRowset<TAccessor>::MoveNext
- CBulkRowset<TAccessor>.MoveNext
- CBulkRowset<TAccessor>::MoveNext
- CBulkRowset::MovePrev
- CBulkRowset<TAccessor>::MovePrev
- ATL::CBulkRowset<TAccessor>::MovePrev
- CBulkRowset<TAccessor>.MovePrev
- ATL::CBulkRowset::MovePrev
- CBulkRowset.MovePrev
- ATL.CBulkRowset.MovePrev
- ATL.CBulkRowset<TAccessor>.MovePrev
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset<TAccessor>.ReleaseRows
- ATL::CBulkRowset<TAccessor>::ReleaseRows
- ATL.CBulkRowset.ReleaseRows
- CBulkRowset<TAccessor>::ReleaseRows
- ATL::CBulkRowset::ReleaseRows
- CBulkRowset::ReleaseRows
- CBulkRowset.ReleaseRows
- ATL.CBulkRowset.SetRows
- CBulkRowset::SetRows
- CBulkRowset<TAccessor>.SetRows
- ATL.CBulkRowset<TAccessor>.SetRows
- CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset::SetRows
- CBulkRowset.SetRows
- SetRows
helpviewer_keywords:
- CBulkRowset class
- AddRefRows method
- CBulkRowset class, constructor
- MoveFirst method
- MoveLast method
- MoveNext method
- MovePrev method
- MoveToBookmark method
- MoveToRatio method
- ReleaseRows method
- SetRows method
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
ms.openlocfilehash: 5c1c7bc381d30f701bad123807689b08ea47f65d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838468"
---
# <a name="cbulkrowset-class"></a>Класс CBulkRowset

Извлекает и манипулирует строками для работы с данными в небольшого объема, получая несколько дескрипторов строк с помощью одного вызова.

## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor>
class CBulkRowset : public CRowset<TAccessor>
```

### <a name="parameters"></a>Параметры

*такцессор*<br/>
Класс метода доступа.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[аддрефровс](#addrefrows)|Увеличивает значение счетчика ссылок.|
|[CBulkRowset](#cbulkrowset)|Конструктор.|
|[MoveFirst](#movefirst)|Извлекает первую строку данных, выполняя при необходимости новую небольшую выборку.|
|[MoveLast](#movelast)|Переходит к последней строке.|
|[MoveNext](#movenext)|Извлекает следующую строку данных.|
|[мовепрев](#moveprev)|Переходит к предыдущей строке.|
|[моветобукмарк](#movetobookmark)|Извлекает строку, помеченную закладкой или строкой с указанным смещением, из этой закладки.|
|[моветоратио](#movetoratio)|Извлекает строки, начиная с части, расположенной в наборе строк.|
|[ReleaseRows](#releaserows)|Устанавливает текущую строку ( `m_nCurrentRow` ) в ноль и освобождает все строки.|
|[сетровс](#setrows)|Задает число дескрипторов строк, получаемых одним вызовом.|

## <a name="example"></a>Пример

В следующем примере демонстрируется использование `CBulkRowset` класса.

[!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]

## <a name="cbulkrowsetaddrefrows"></a><a name="addrefrows"></a> CBulkRowset:: Аддрефровс

Вызывает метод [IRowset:: аддрефровс](/previous-versions/windows/desktop/ms719619(v=vs.85)) , чтобы увеличить число ссылок для всех строк, которые в настоящее время извлечены из набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT AddRefRows() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cbulkrowsetcbulkrowset"></a><a name="cbulkrowset"></a> CBulkRowset:: CBulkRowset

Создает новый `CBulkRowset` объект и устанавливает число строк по умолчанию равным 10.

### <a name="syntax"></a>Синтаксис

```cpp
CBulkRowset();
```

## <a name="cbulkrowsetmovefirst"></a><a name="movefirst"></a> CBulkRowset:: MoveFirst

Извлекает первую строку данных.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT MoveFirst() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cbulkrowsetmovelast"></a><a name="movelast"></a> CBulkRowset:: MoveLast

Переходит к последней строке.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT MoveLast() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cbulkrowsetmovenext"></a><a name="movenext"></a> CBulkRowset:: MoveNext

Извлекает следующую строку данных.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT MoveNext() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. По достижении конца набора строк возвращает DB_S_ENDOFROWSET.

## <a name="cbulkrowsetmoveprev"></a><a name="moveprev"></a> CBulkRowset:: Мовепрев

Переходит к предыдущей строке.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT MovePrev() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cbulkrowsetmovetobookmark"></a><a name="movetobookmark"></a> CBulkRowset:: Моветобукмарк

Извлекает строку, помеченную закладкой, или строку с указанным смещением (*лскип*) из этой закладки.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,
   DBCOUNTITEM lSkip = 0) throw();
```

#### <a name="parameters"></a>Параметры

*bookmark*<br/>
окне Закладка, помечающая расположение, из которого необходимо извлечь данные.

*лскип*<br/>
окне Число строк из закладки в целевую строку. Если *лскип* равен нулю, первая строка выбирается в качестве строки с закладкой. Если значение *лскип* равно 1, первая строка получается после строки с закладкой. Если *лскип* имеет значение-1, первая строка извлекается перед строкой с закладкой.

### <a name="return-value"></a>Возвращаемое значение

См. раздел [IRowset:: GetData](/previous-versions/windows/desktop/ms716988(v=vs.85)) в *справочнике по OLE DB программиста*.

## <a name="cbulkrowsetmovetoratio"></a><a name="movetoratio"></a> CBulkRowset:: Моветоратио

Извлекает строки, начиная с части, расположенной в наборе строк.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,
   DBCOUNTITEM nDenominator)throw();
```

#### <a name="parameters"></a>Параметры

*ннумератор*<br/>
окне Числитель, используемый для определения дробной части, из которой извлекать данные.

*нденоминатор*<br/>
окне Знаменатель, используемый для определения относительной дробной части, из которой следует извлечь данные.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`MoveToRatio` выбирает строки примерно в соответствии со следующей формулой:

`(nNumerator *  RowsetSize ) / nDenominator`

Где `RowsetSize` — Размер набора строк, измеряемый в строках. Точность этой формулы зависит от конкретного поставщика. Дополнительные сведения см. в разделе [IRowsetScroll:: жетровсатратио](/previous-versions/windows/desktop/ms709602(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="cbulkrowsetreleaserows"></a><a name="releaserows"></a> CBulkRowset:: ReleaseRows

Вызывает метод [IRowset:: ReleaseRows](/previous-versions/windows/desktop/ms719771(v=vs.85)) , чтобы уменьшить число ссылок для всех строк, которые в настоящее время извлечены из набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT ReleaseRows() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cbulkrowsetsetrows"></a><a name="setrows"></a> CBulkRowset:: Сетровс

Задает число дескрипторов строк, извлекаемых каждым вызовом.

### <a name="syntax"></a>Синтаксис

```cpp
void SetRows(DBROWCOUNT nRows) throw();
```

#### <a name="parameters"></a>Параметры

*nRows*<br/>
окне Новый размер набора строк (число строк).

### <a name="remarks"></a>Примечания

При вызове этой функции она должна быть перед открытием набора строк.

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
