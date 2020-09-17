---
title: Класс CDynamicAccessor
ms.date: 11/04/2016
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
- ATL::CDynamicAccessor::AddBindEntry
- CDynamicAccessor.AddBindEntry
- CDynamicAccessor::AddBindEntry
- ATL.CDynamicAccessor.AddBindEntry
- CDynamicAccessor::CDynamicAccessor
- ATL::CDynamicAccessor::CDynamicAccessor
- ATL.CDynamicAccessor.CDynamicAccessor
- CDynamicAccessor.CDynamicAccessor
- ATL::CDynamicAccessor::Close
- ATL.CDynamicAccessor.Close
- CDynamicAccessor.Close
- CDynamicAccessor::Close
- ATL.CDynamicAccessor.GetBlobHandling
- CDynamicAccessor::GetBlobHandling
- ATL::CDynamicAccessor::GetBlobHandling
- GetBlobHandling
- CDynamicAccessor.GetBlobHandling
- ATL::CDynamicAccessor::GetBlobSizeLimit
- CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor::GetBlobSizeLimit
- GetBlobSizeLimit
- ATL.CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor.GetBookmark
- GetBookmark
- CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetBookmark
- ATL::CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetColumnCount
- ATL::CDynamicAccessor::GetColumnCount
- CDynamicAccessor::GetColumnCount
- CDynamicAccessor.GetColumnCount
- GetColumnCount
- CDynamicAccessor.GetColumnFlags
- ATL::CDynamicAccessor::GetColumnFlags
- ATL.CDynamicAccessor.GetColumnFlags
- CDynamicAccessor::GetColumnFlags
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
- ATL::CDynamicAccessor::GetColumnName
- GetColumnName
- ATL.CDynamicAccessor.GetColumnName
- CDynamicAccessor::GetColumnName
- CDynamicAccessor.GetColumnName
- ATL.CDynamicAccessor.GetColumnType
- CDynamicAccessor::GetColumnType
- GetColumnType
- CDynamicAccessor.GetColumnType
- ATL::CDynamicAccessor::GetColumnType
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
- CDynamicAccessor.GetOrdinal
- ATL::CDynamicAccessor::GetOrdinal
- CDynamicAccessor::GetOrdinal
- ATL.CDynamicAccessor.GetOrdinal
- GetOrdinal
- ATL::CDynamicAccessor::GetStatus
- CDynamicAccessor.GetStatus
- ATL.CDynamicAccessor.GetStatus
- CDynamicAccessor::GetStatus
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
- ATL::CDynamicAccessor::SetLength
- CDynamicAccessor.SetLength
- CDynamicAccessor::SetLength
- ATL.CDynamicAccessor.SetLength
- CDynamicAccessor::SetStatus
- ATL::CDynamicAccessor::SetStatus
- CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
helpviewer_keywords:
- CDynamicAccessor class
- AddBindEntry method
- CDynamicAccessor class, constructor
- Close method
- GetBlobHandling method
- GetBlobSizeLimit method
- GetBookmark method
- GetColumnCount method
- GetColumnFlags method
- GetColumnInfo method
- GetColumnName method
- GetColumnType method
- GetLength method
- GetOrdinal method
- GetStatus method
- GetValue method
- SetBlobHandling method
- SetBlobSizeLimit method
- SetLength method
- SetStatus method
- SetValue method
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
ms.openlocfilehash: ecbc332fcdb7fee8f748a02b2f111d4d1abf3c0b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838208"
---
# <a name="cdynamicaccessor-class"></a>Класс CDynamicAccessor

Позволяет получить доступ к источнику данных, если нет сведений о схеме базы данных (базовой структуре базы данных).

## <a name="syntax"></a>Синтаксис

```cpp
class CDynamicAccessor : public CAccessorBase
```

## <a name="requirements"></a>Требования

**Заголовок**: Atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|-|-|
|[AddBindEntry](#addbindentry)|Добавляет запись привязки к выходным столбцам при переопределении метода доступа по умолчанию.|
|[CDynamicAccessor](#cdynamicaccessor)|Создает и инициализирует `CDynamicAccessor` объект.|
|[Закрыть](#close)|Отменяет привязку всех столбцов, освобождает выделенную память и освобождает указатель интерфейса [IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) в классе.|
|[жетблобхандлинг](#getblobhandling)|Возвращает значение обработки большого двоичного объекта для текущей строки.|
|[жетблобсизелимит](#getblobsizelimit)|Возвращает максимальный размер большого двоичного объекта в байтах.|
|[Выкладка](#getbookmark)|Извлекает закладку для текущей строки.|
|[GetColumnCount](#getcolumncount)|Возвращает количество столбцов в наборе строк.|
|[жетколумнфлагс](#getcolumnflags)|Получает характеристики столбца.|
|[GetColumnInfo](#getcolumninfo)|Получает метаданные столбца.|
|[GetColumnName](#getcolumnname)|Извлекает имя указанного столбца.|
|[жетколумнтипе](#getcolumntype)|Возвращает тип данных указанного столбца.|
|[GetLength](#getlength)|Возвращает максимально возможную длину столбца в байтах.|
|[GetOrdinal](#getordinal)|Возвращает индекс столбца по заданному имени столбца.|
|[GetStatus](#getstatus)|Получает состояние указанного столбца.|
|[GetValue](#getvalue)|Извлекает данные из буфера.|
|[сетблобхандлинг](#setblobhandling)|Задает значение обработки большого двоичного объекта для текущей строки.|
|[сетблобсизелимит](#setblobsizelimit)|Задает максимальный размер большого двоичного объекта в байтах.|
|[SetLength](#setlength)|Задает длину столбца в байтах.|
|[SetStatus](#setstatus)|Задает состояние указанного столбца.|
|[SetValue](#setvalue)|Сохраняет данные в буфер.|

## <a name="remarks"></a>Примечания

Используйте `CDynamicAccessor` методы для получения таких сведений о столбцах, как имена столбцов, число столбцов, тип данных и т. д. Затем эти сведения о столбце используются для динамического создания метода доступа во время выполнения.

Сведения о столбцах хранятся в буфере, который создается и управляется этим классом. Получение данных из буфера с помощью функции [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md).

Обсуждение и примеры использования динамических классов методов доступа см. в разделе [Использование динамических методов доступа](../../data/oledb/using-dynamic-accessors.md).

## <a name="cdynamicaccessoraddbindentry"></a><a name="addbindentry"></a> CDynamicAccessor:: AddBindEntry

Добавляет запись привязки к выходным столбцам.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT AddBindEntry(const DBCOLUMNINFO& info) throw();
```

#### <a name="parameters"></a>Параметры

*контактные*<br/>
окне `DBCOLUMNINFO` Структура, содержащая сведения о столбцах. См. раздел "структуры DBCOLUMNINFO" в [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Используйте этот метод при переопределении метода доступа по умолчанию, созданного с помощью `CDynamicAccessor` (см. раздел [как извлечь данные?](../../data/oledb/fetching-data.md)).

## <a name="cdynamicaccessorcdynamicaccessor"></a><a name="cdynamicaccessor"></a> CDynamicAccessor:: CDynamicAccessor

Создает и инициализирует `CDynamicAccessor` объект.

### <a name="syntax"></a>Синтаксис

```cpp
CDynamicAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,
   DBLENGTH nBlobSize = 8000);
```

#### <a name="parameters"></a>Параметры

*еблобхандлинг*<br/>
Указывает способ обработки данных больших двоичных объектов (BLOB). Значение по умолчанию — DBBLOBHANDLING_DEFAULT. Описание значений ДББЛОБХАНДЛИНЖЕНУМ см. в разделе [сетблобхандлинг](../../data/oledb/cdynamicaccessor-setblobhandling.md) .

*нблобсизе*<br/>
Максимальный размер большого двоичного объекта в байтах; данные столбца по этому значению рассматриваются как большой двоичный объект. Значение по умолчанию — 8 000. Дополнительные сведения см. в разделе [сетблобсизелимит](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) .

### <a name="remarks"></a>Примечания

При использовании конструктора для инициализации `CDynamicAccessor` объекта можно указать, как он будет привязывать большие двоичные объекты. BLOB-объекты могут содержать двоичные данные, такие как графика, звук или скомпилированный код. Поведение по умолчанию состоит в том, чтобы обрабатывать столбцы более 8 000 байт в виде больших двоичных объектов и пытаться привязать их к `ISequentialStream` объекту. Однако можно указать другое значение в качестве размера большого двоичного объекта.

Кроме того, можно указать, как `CDynamicAccessor` обрабатывает данные столбцов, которые обрабатываются как данные большого двоичного объекта. он может обрабатывать данные больших двоичных объектов по умолчанию; он может пропустить (не привязывает) данные большого двоичного объекта или привязать данные большого двоичного объекта в памяти, выделенной поставщиком.

## <a name="cdynamicaccessorclose"></a><a name="close"></a> CDynamicAccessor:: Close

Отменяет привязку всех столбцов, освобождает выделенную память и освобождает указатель интерфейса [IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) в классе.

### <a name="syntax"></a>Синтаксис

```cpp
void Close() throw();
```

## <a name="cdynamicaccessorgetblobhandling"></a><a name="getblobhandling"></a> CDynamicAccessor:: Жетблобхандлинг

Возвращает значение обработки большого двоичного объекта для текущей строки.

### <a name="syntax"></a>Синтаксис

```cpp
const DBBLOBHANDLINGENUM GetBlobHandling() const;
```

### <a name="remarks"></a>Примечания

Возвращает значение обработки BLOB-объекта *еблобхандлинг* , заданное параметром [сетблобхандлинг](../../data/oledb/cdynamicaccessor-setblobhandling.md).

## <a name="cdynamicaccessorgetblobsizelimit"></a><a name="getblobsizelimit"></a> CDynamicAccessor:: Жетблобсизелимит

Возвращает максимальный размер большого двоичного объекта в байтах.

### <a name="syntax"></a>Синтаксис

```cpp
const DBLENGTH GetBlobSizeLimit() const;
```

### <a name="remarks"></a>Примечания

Возвращает значение обработки BLOB-объекта *нблобсизе* , заданное параметром [сетблобсизелимит](../../data/oledb/cdynamicaccessor-setblobsizelimit.md).

## <a name="cdynamicaccessorgetbookmark"></a><a name="getbookmark"></a> CDynamicAccessor:: onbookmark

Извлекает закладку для текущей строки.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetBookmark(CBookmark< >* pBookmark) const throw();
```

#### <a name="parameters"></a>Параметры

*пбукмарк*<br/>
заполняет Указатель на объект [CBookmark](../../data/oledb/cbookmark-class.md) .

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Чтобы `DBPROP_IRowsetLocate` получить закладку, необходимо задать значение VARIANT_TRUE.

## <a name="cdynamicaccessorgetcolumncount"></a><a name="getcolumncount"></a> CDynamicAccessor:: GetColumnCount

Возвращает число столбцов.

### <a name="syntax"></a>Синтаксис

```cpp
DBORDINAL GetColumnCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Число извлеченных столбцов.

## <a name="cdynamicaccessorgetcolumnflags"></a><a name="getcolumnflags"></a> CDynamicAccessor:: Жетколумнфлагс

Получает характеристики столбца.

### <a name="syntax"></a>Синтаксис

```cpp
bool GetColumnFlags(DBORDINAL nColumn,
   DBCOLUMNFLAGS* pFlags) const throw();
```

#### <a name="parameters"></a>Параметры

*нколумн*<br/>
окне Номер столбца. Номера столбцов начинаются с 1. Значение 0 указывает на столбец Bookmark, если он есть.

*пфлагс*<br/>
заполняет Указатель на битовую маску, описывающую характеристики столбца. См. раздел "перечислимый тип DBCOLUMNFLAGS" в [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, **`true`** Если характеристики столбца успешно получены. В противном случае возвращается значение **`false`** .

### <a name="remarks"></a>Примечания

Номер столбца смещается с единицы. Нулевой столбец является особым случаем. Это закладка, если она доступна.

## <a name="cdynamicaccessorgetcolumninfo"></a><a name="getcolumninfo"></a> CDynamicAccessor:: GetColumnInfo

Возвращает метаданные столбца, требуемые большинством объектов-получателей.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetColumnInfo(IRowset* pRowset,
   DBORDINAL* pColumns,
   DBCOLUMNINFO** ppColumnInfo,
   OLECHAR** ppStringsBuffer) throw();
```

#### <a name="parameters"></a>Параметры

*провсет*<br/>
окне Указатель на интерфейс [IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85)) .

*пколумнс*<br/>
заполняет Указатель на память, в которую будет возвращено количество столбцов в наборе строк; Это число включает столбец Bookmark, если он есть.

*ппколумнинфо*<br/>
заполняет Указатель на память, в которую возвращается массив `DBCOLUMNINFO` структур. См. раздел "структуры DBCOLUMNINFO" в [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) в *справочнике программиста OLE DB*.

*ппстрингсбуффер*<br/>
заполняет Указатель на память, в которую возвращается указатель на хранилище для всех строковых значений (имена, используемые в пределах *columnid* или for *pwszName*) в одном блоке выделения.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Сведения о типах данных, и, см. в разделе [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) в *справочнике программиста OLE DB* `DBORDINAL` `DBCOLUMNINFO` `OLECHAR` .

## <a name="cdynamicaccessorgetcolumnname"></a><a name="getcolumnname"></a> CDynamicAccessor:: GetColumnName

Извлекает имя указанного столбца.

### <a name="syntax"></a>Синтаксис

```cpp
LPOLESTR GetColumnName(DBORDINAL nColumn) const throw();
```

#### <a name="parameters"></a>Параметры

*нколумн*<br/>
окне Номер столбца. Номера столбцов начинаются с 1. Значение 0 указывает на столбец Bookmark, если он есть.

### <a name="return-value"></a>Возвращаемое значение

Имя заданного столбца.

## <a name="cdynamicaccessorgetcolumntype"></a><a name="getcolumntype"></a> CDynamicAccessor:: Жетколумнтипе

Возвращает тип данных указанного столбца.

### <a name="syntax"></a>Синтаксис

```cpp
bool GetColumnType(DBORDINAL nColumn,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>Параметры

*нколумн*<br/>
окне Номер столбца. Номера столбцов начинаются с 1. Значение 0 указывает на столбец Bookmark, если он есть.

*птипе*<br/>
заполняет Указатель на тип данных указанного столбца.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение **`true`** On Success или **`false`** On failure.

## <a name="cdynamicaccessorgetlength"></a><a name="getlength"></a> CDynamicAccessor:: DATALENGTH

Извлекает длину указанного столбца.

### <a name="syntax"></a>Синтаксис

```cpp
bool GetLength(DBORDINAL nColumn,
   DBLENGTH* pLength) const throw();

bool GetLength(const CHAR* pColumnName,
   DBLENGTH* pLength) const throw();

bool GetLength(const WCHAR* pColumnName,
   DBLENGTH* pLength) const throw();
```

#### <a name="parameters"></a>Параметры

*нколумн*<br/>
окне Номер столбца. Номера столбцов начинаются с 1. Значение 0 указывает на столбец Bookmark, если он есть.

*пколумннаме*<br/>
окне Указатель на строку символов, содержащую имя столбца.

*пленгс*<br/>
заполняет Указатель на целое число, содержащее длину столбца в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение **`true`** , если указанный столбец найден. В противном случае эта функция возвращает значение **`false`** .

### <a name="remarks"></a>Примечания

Первое переопределение принимает номер столбца, а второе и третье переопределения принимают имя столбца в формате ANSI или Unicode соответственно.

## <a name="cdynamicaccessorgetordinal"></a><a name="getordinal"></a> CDynamicAccessor:: Ordinal

Возвращает номер столбца по заданному имени столбца.

### <a name="syntax"></a>Синтаксис

```cpp
bool GetOrdinal(const CHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();

bool GetOrdinal(const WCHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();
```

#### <a name="parameters"></a>Параметры

*пколумннаме*<br/>
окне Указатель на строку символов, содержащую имя столбца.

*пординал*<br/>
заполняет Указатель на номер столбца.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, **`true`** если найден столбец с указанным именем. В противном случае эта функция возвращает значение **`false`** .

## <a name="cdynamicaccessorgetstatus"></a><a name="getstatus"></a> CDynamicAccessor::/Status

Получает состояние указанного столбца.

### <a name="syntax"></a>Синтаксис

```cpp
bool GetStatus(DBORDINAL nColumn,
   DBSTATUS* pStatus) const throw();

bool GetStatus(const CHAR* pColumnName,
   DBSTATUS* pStatus) const throw();

bool GetStatus(const WCHAR* pColumnName,
   DBSTATUS* pStatus) const throw();
```

#### <a name="parameters"></a>Параметры

*нколумн*<br/>
окне Номер столбца. Номера столбцов начинаются с 1. Значение 0 указывает на столбец Bookmark, если он есть.

*пколумннаме*<br/>
окне Указатель на строку символов, содержащую имя столбца.

*пстатус*<br/>
заполняет Указатель на переменную, содержащую состояние столбца. Дополнительные сведения см. в разделе [дбстатус](/previous-versions/windows/desktop/ms722617(v=vs.85)) в *справочнике программиста OLE DB* .

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение **`true`** , если указанный столбец найден. В противном случае эта функция возвращает значение **`false`** .

## <a name="cdynamicaccessorgetvalue"></a><a name="getvalue"></a> CDynamicAccessor:: GetValue

Извлекает данные для указанного столбца.

### <a name="syntax"></a>Синтаксис

```cpp
void* GetValue(DBORDINAL nColumn) const throw();

void* GetValue(const CHAR* pColumnName) const throw();

void* GetValue(const WCHAR* pColumnName) const throw();

template < class ctype >
bool GetValue(DBORDINAL nColumn, ctype* pData) const throw();

template < class ctype >
bool GetValue(const CHAR* pColumnName, ctype* pData) const throw();

template < class ctype >
bool GetValue(const WCHAR* pColumnName, ctype* pData) const throw();
```

#### <a name="parameters"></a>Параметры

*CType*<br/>
окне Шаблонный параметр, обрабатывающий любой тип данных, за исключением строкового типа ( `CHAR*` , `WCHAR*` ), требующего специальной обработки. `GetValue` использует соответствующий тип данных в зависимости от того, что указано здесь.

*нколумн*<br/>
окне Номер столбца. Номера столбцов начинаются с 1. Значение 0 указывает на столбец Bookmark, если он есть.

*пколумннаме*<br/>
окне Имя столбца.

*pData*<br/>
заполняет Указатель на содержимое указанного столбца.

### <a name="return-value"></a>Возвращаемое значение

Если необходимо передать строковые данные, используйте нешаблонные версии `GetValue` . Нешаблонные версии этого метода возвращают **`void*`** , что указывает на часть буфера, которая содержит указанные данные столбца. Возвращает значение NULL, если столбец не найден.

Для всех других типов данных проще использовать шаблонные версии `GetValue` . Версии в шаблоне возвращают **`true`** успешное выполнение или при **`false`** сбое.

### <a name="remarks"></a>Примечания

Используйте нешаблонные версии для возврата столбцов, содержащих строки, и шаблонных версий для столбцов, содержащих другие типы данных.

В режиме отладки будет получено утверждение, если размер *pData* не равен размеру столбца, на который он указывает.

## <a name="cdynamicaccessorsetblobhandling"></a><a name="setblobhandling"></a> CDynamicAccessor:: Сетблобхандлинг

Задает значение обработки большого двоичного объекта для текущей строки.

### <a name="syntax"></a>Синтаксис

```cpp
bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);
```

#### <a name="parameters"></a>Параметры

*еблобхандлинг*<br/>
Указывает способ обработки данных большого двоичного объекта. Этот параметр может принимать перечисленные ниже значения.

- DBBLOBHANDLING_DEFAULT: обрабатывайте данные столбца, превышающие *нблобсизе* (как задано `SetBlobSizeLimit` ), как данные большого двоичного объекта, и извлеките их через `ISequentialStream` `IStream` объект или. Этот параметр попытается привязать каждый столбец, содержащий данные, превышающие *нблобсизе* , или список DBTYPE_IUNKNOWN как данные большого двоичного объекта.

- DBBLOBHANDLING_NOSTREAMS: обрабатывайте данные столбцов, превышающие *нблобсизе* (заданные в `SetBlobSizeLimit` ) как данные большого двоичного объекта, и извлеките их с помощью ссылки в выделенной для потребителя памяти. Этот параметр полезен для таблиц, имеющих более одного столбца больших двоичных объектов, и поставщик поддерживает только один `ISequentialStream` объект для каждого метода доступа.

- DBBLOBHANDLING_SKIP: пропустить (не привязывать) столбцы, уточняющие их как содержащие большие двоичные объекты (метод доступа не будет выполнять привязку или извлечь значение столбца, но он по-прежнему будет получать состояние и длину столбца).

### <a name="remarks"></a>Примечания

Перед вызовом `SetBlobHandling` следует вызвать метод `Open`.

Метод-конструктор [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) устанавливает значение обработки BLOB-объекта DBBLOBHANDLING_DEFAULT.

## <a name="cdynamicaccessorsetblobsizelimit"></a><a name="setblobsizelimit"></a> CDynamicAccessor:: Сетблобсизелимит

Задает максимальный размер большого двоичного объекта в байтах.

### <a name="syntax"></a>Синтаксис

```cpp
void SetBlobSizeLimit(DBLENGTH nBlobSize);
```

#### <a name="parameters"></a>Параметры

*нблобсизе*<br/>
Указывает предельный размер большого двоичного объекта.

### <a name="remarks"></a>Примечания

Задает максимальный размер большого двоичного объекта в байтах; данные столбца, превышающие это значение, рассматриваются как большие ДВОИЧные объекты. Некоторые поставщики предоставляют очень большие размеры столбцов (например, 2 ГБ). Вместо того, чтобы пытаться выделить память для столбца такого размера, обычно вы пытаетесь привязать эти столбцы как большие двоичные объекты. Таким образом, вам не придется выделять всю память, но вы все равно можете читать все данные, не опасаясь усечения. Однако в некоторых случаях может потребоваться принудительно `CDynamicAccessor` привязать большие столбцы к собственным типам данных. Для этого вызовите метод `SetBlobSizeLimit` перед вызовом `Open` .

Метод-конструктор [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) устанавливает максимальный размер большого двоичного объекта равным значению по умолчанию 8 000 байт.

## <a name="cdynamicaccessorsetlength"></a><a name="setlength"></a> CDynamicAccessor:: SetLength

Задает длину указанного столбца.

### <a name="syntax"></a>Синтаксис

```cpp
bool SetLength(DBORDINAL nColumn,
   DBLENGTH nLength)throw();

bool SetLength(const CHAR* pColumnName,
   DBLENGTH nLength) throw();

bool SetLength(const WCHAR* pColumnName,
   DBLENGTH nLength) throw();
```

#### <a name="parameters"></a>Параметры

*нколумн*<br/>
окне Номер столбца. Номера столбцов начинаются с 1. Значение 0 указывает на столбец Bookmark, если он есть.

*нленгс*<br/>
окне Длина столбца в байтах.

*пколумннаме*<br/>
окне Указатель на строку символов, содержащую имя столбца.

### <a name="return-value"></a>Возвращаемое значение

Возвращает **`true`** значение, если указанная длина столбца установлена успешно. В противном случае эта функция возвращает значение **`false`** .

## <a name="cdynamicaccessorsetstatus"></a><a name="setstatus"></a> CDynamicAccessor:: SetStatus

Задает состояние указанного столбца.

### <a name="syntax"></a>Синтаксис

```cpp
bool SetStatus(DBORDINAL nColumn,
   DBSTATUS status)throw();

bool SetStatus(const CHAR* pColumnName,
   DBSTATUS status) throw();

bool SetStatus(const WCHAR* pColumnName,
   DBSTATUS status) throw();
```

#### <a name="parameters"></a>Параметры

*нколумн*<br/>
окне Номер столбца. Номера столбцов начинаются с 1. Значение 0 указывает на столбец Bookmark, если он есть.

*status*<br/>
окне Состояние столбца. Дополнительные сведения см. в разделе [дбстатус](/previous-versions/windows/desktop/ms722617(v=vs.85)) в *справочнике программиста OLE DB* .

*пколумннаме*<br/>
окне Указатель на строку символов, содержащую имя столбца.

### <a name="return-value"></a>Возвращаемое значение

Возвращает, **`true`** если указанный столбец имеет состояние "успешно задано". В противном случае эта функция возвращает значение **`false`** .

## <a name="cdynamicaccessorsetvalue"></a><a name="setvalue"></a> CDynamicAccessor:: SetValue

Хранит данные в указанном столбце.

### <a name="syntax"></a>Синтаксис

```cpp
template <class ctype>
bool SetValue(
   DBORDINAL nColumn,
   constctype& data) throw( );

template <class ctype>
bool SetValue(
   const CHAR * pColumnName,
   const ctype& data) throw( );

template <class ctype>
bool SetValue(
   const WCHAR *pColumnName,
   const ctype& data) throw( );
```

#### <a name="parameters"></a>Параметры

*CType*<br/>
окне Шаблонный параметр, обрабатывающий любой тип данных, за исключением строкового типа ( `CHAR*` , `WCHAR*` ), требующего специальной обработки. `GetValue` использует соответствующий тип данных в зависимости от того, что указано здесь.

*пколумннаме*<br/>
окне Указатель на строку символов, содержащую имя столбца.

*data*<br/>
окне Указатель на память, содержащую данные.

*нколумн*<br/>
окне Номер столбца. Номера столбцов начинаются с 1. Значение 0 указывает на столбец Bookmark, если он есть.

### <a name="return-value"></a>Возвращаемое значение

Если вы хотите задать строковые данные, используйте нешаблонные версии `GetValue` . Нешаблонные версии этого метода возвращают **`void*`** , что указывает на часть буфера, которая содержит указанные данные столбца. Возвращает значение NULL, если столбец не найден.

Для всех других типов данных проще использовать шаблонные версии `GetValue` . Версии в шаблоне возвращают **`true`** успешное выполнение или при **`false`** сбое.

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс Какцессор](../../data/oledb/caccessor-class.md)<br/>
[Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)
