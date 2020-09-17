---
title: Макросы и глобальные функции для шаблонов потребителей OLE DB
ms.date: 02/11/2019
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
- BEGIN_ACCESSOR
- BEGIN_ACCESSOR_MAP
- END_ACCESSOR
- END_ACCESSOR_MAP
- BEGIN_COLUMN_MAP
- BLOB_ENTRY
- BLOB_ENTRY_LENGTH
- BLOB_ENTRY_LENGTH_STATUS
- BLOB_ENTRY_STATUS
- BLOB_NAME
- BLOB_NAME_LENGTH
- BLOB_NAME_LENGTH_STATUS
- BLOB_NAME_STATUS
- BOOKMARK_ENTRY
- COLUMN_ENTRY
- COLUMN_ENTRY_EX
- COLUMN_ENTRY_LENGTH
- COLUMN_ENTRY_LENGTH_STATUS
- COLUMN_ENTRY_PS
- COLUMN_ENTRY_PS_LENGTH
- COLUMN_ENTRY_PS_LENGTH_STATUS
- COLUMN_ENTRY_PS_STATUS
- COLUMN_ENTRY_STATUS
- COLUMN_ENTRY_TYPE
- COLUMN_ENTRY_TYPE_SIZE
- COLUMN_NAME
- COLUMN_NAME_EX
- COLUMN_NAME_LENGTH
- COLUMN_NAME_LENGTH_STATUS
- COLUMN_NAME_PS
- COLUMN_NAME_PS_LENGTH
- COLUMN_NAME_PS_LENGTH_STATUS
- COLUMN_NAME_PS_STATUS
- COLUMN_NAME_STATUS
- COLUMN_NAME_TYPE
- COLUMN_NAME_TYPE_PS
- COLUMN_NAME_TYPE_SIZE
- COLUMN_NAME_TYPE_STATUS
- END_COLUMN_MAP
- DEFINE_COMMAND
- DEFINE_COMMAND_EX
- BEGIN_PARAM_MAP
- END_PARAM_MAP
- SET_PARAM_TYPE
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
- AtlTraceErrorRecords function
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR_MAP macro
- END_ACCESSOR macro
- END_ACCESSOR_MAP macro
- BEGIN_COLUMN_MAP macro
- BLOB_ENTRY macro
- BLOB_ENTRY_LENGTH macro
- BLOB_ENTRY_LENGTH_STATUS macro
- BLOB_ENTRY_STATUS macro
- BLOB_NAME macro
- BLOB_NAME_LENGTH macro
- BLOB_NAME_LENGTH_STATUS macro
- BLOB_NAME_STATUS macro
- BOOKMARK_ENTRY macro
- COLUMN_ENTRY macro
- COLUMN_ENTRY_EX macro
- COLUMN_ENTRY_LENGTH macro
- COLUMN_ENTRY_LENGTH_STATUS macro
- COLUMN_ENTRY_PS macro
- COLUMN_ENTRY_PS_LENGTH macro
- COLUMN_ENTRY_PS_LENGTH_STATUS macro
- COLUMN_ENTRY_PS_STATUS macro
- COLUMN_ENTRY_STATUS macro
- COLUMN_ENTRY_TYPE macro
- COLUMN_ENTRY_TYPE_SIZE macro
- COLUMN_NAME macro
- COLUMN_NAME_EX macro
- COLUMN_NAME_LENGTH macro
- COLUMN_NAME_LENGTH_STATUS macro
- COLUMN_NAME_PS macro
- COLUMN_NAME_PS_LENGTH macro
- COLUMN_NAME_PS_LENGTH_STATUS macro
- COLUMN_NAME_PS_STATUS macro
- COLUMN_NAME_STATUS macro
- COLUMN_NAME_TYPE macro
- COLUMN_NAME_TYPE_PS macro
- COLUMN_NAME_TYPE_SIZE macro
- COLUMN_NAME_TYPE_STATUS macro
- END_COLUMN_MAP macro
- DEFINE_COMMAND macro
- DEFINE_COMMAND_EX macro
- BEGIN_PARAM_MAP macro
- END_PARAM_MAP macro
- SET_PARAM_TYPE macro
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
ms.openlocfilehash: 07fbdf7dfcd82937721955c5ba08e2241df162e5
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846541"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>Макросы и глобальные функции для шаблонов потребителей OLE DB

OLE DB шаблоны потребителей включают следующие макросы и глобальные функции:

## <a name="global-functions"></a>Глобальные функции

| Имя | Описание |
|-|-|
|[AtlTraceErrorRecords](#atltraceerrorrecords)|При возвращении ошибки выводит OLE DB сведения о записи об ошибке на устройство дампа.|

## <a name="accessor-map-macros"></a>Макросы для карт методов доступа

| Имя | Описание |
|-|-|
|[BEGIN_ACCESSOR](#begin_accessor)|Помечает начало записи метода доступа.|
|[BEGIN_ACCESSOR_MAP](#begin_accessor_map)|Отмечает начало карты записей метода доступа.|
|[END_ACCESSOR](#end_accessor)|Помечает конец записи метода доступа.|
|[END_ACCESSOR_MAP](#end_accessor_map)|Помечает конец записей схемы метода доступа.|

## <a name="column-map-macros"></a>Макросы таблицы соответствия столбцов

| Имя | Описание |
|-|-|
|[BEGIN_COLUMN_MAP](#begin_column_map)|Помечает начало записей схемы столбцов в классе записей пользователя.|
|[BLOB_ENTRY](#blob_entry)|Используется для привязки большого двоичного объекта (BLOB).|
|[BLOB_ENTRY_LENGTH](#blob_entry_length)|Сообщает длину столбца данных большого двоичного объекта.|
|[BLOB_ENTRY_LENGTH_STATUS](#blob_entry_length_status)|Сообщает о длине и состоянии столбца данных большого двоичного объекта.|
|[BLOB_ENTRY_STATUS](#blob_entry_status)|Сообщает состояние столбца данных большого двоичного объекта.|
|[BLOB_NAME](#blob_name)|Используется для привязки большого двоичного объекта по имени столбца.|
|[BLOB_NAME_LENGTH](#blob_name_length)|Сообщает длину столбца данных большого двоичного объекта.|
|[BLOB_NAME_LENGTH_STATUS](#blob_name_length_status)|Сообщает о длине и состоянии столбца данных большого двоичного объекта.|
|[BLOB_NAME_STATUS](#blob_name_status)|Сообщает состояние столбца данных большого двоичного объекта.|
|[BOOKMARK_ENTRY](#bookmark_entry)|Представляет запись закладки для набора строк. Запись закладки — это особый тип записи в столбец.|
|[COLUMN_ENTRY](#column_entry)|Представляет привязку к определенному столбцу в базе данных.|
|[COLUMN_ENTRY_EX](#column_entry_ex)|Представляет привязку к определенному столбцу в базе данных. Поддерживает параметры *типа*, *длины*, *точности*, *масштаба*и *состояния* .|
|[COLUMN_ENTRY_LENGTH](#column_entry_length)|Представляет привязку к определенному столбцу в базе данных. Поддерживает переменную *длины* .|
|[COLUMN_ENTRY_LENGTH_STATUS](#column_entry_length_status)|Представляет привязку к определенному столбцу в базе данных. Поддерживает параметры *состояния* и *длины* .|
|[COLUMN_ENTRY_PS](#column_entry_ps)|Представляет привязку к определенному столбцу в базе данных. Поддерживает параметры *точности* и *масштабирования* .|
|[COLUMN_ENTRY_PS_LENGTH](#column_entry_ps_length)|Представляет привязку к определенному столбцу в базе данных. Поддерживает параметры переменной *длины* , *точности* и *масштаба* .|
|[COLUMN_ENTRY_PS_LENGTH_STATUS](#column_entry_ps_length_status)|Представляет привязку к определенному столбцу в базе данных. Поддерживает переменные *состояния* и *длины* , параметры *точности* и *масштабирования* .|
|[COLUMN_ENTRY_PS_STATUS](#column_entry_ps_status)|Представляет привязку к определенному столбцу в базе данных. Поддерживает переменные *состояния* , *точность* и параметры *масштабирования* .|
|[COLUMN_ENTRY_STATUS](#column_entry_status)|Представляет привязку к определенному столбцу в базе данных. Поддерживает переменную *состояния* .|
|[COLUMN_ENTRY_TYPE](#column_entry_type)|Представляет привязку к определенному столбцу в базе данных. Поддерживает параметр *типа* .|
|[COLUMN_ENTRY_TYPE_SIZE](#column_entry_type_size)|Представляет привязку к определенному столбцу в базе данных. Поддерживает параметры *типа* и *размера* .|
|[COLUMN_NAME](#column_name)|Представляет привязку к определенному столбцу в базе данных по имени.|
|[COLUMN_NAME_EX](#column_name_ex)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию типа данных, размера, точности, масштаба, длины столбца и состояния столбца.|
|[COLUMN_NAME_LENGTH](#column_name_length)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию длины столбца.|
|[COLUMN_NAME_LENGTH_STATUS](#column_name_length_status)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию длины и состояния столбца.|
|[COLUMN_NAME_PS](#column_name_ps)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию точности и масштаба.|
|[COLUMN_NAME_PS_LENGTH](#column_name_ps_length)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию точности, масштаба и длины столбца.|
|[COLUMN_NAME_PS_LENGTH_STATUS](#column_name_ps_length_status)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию точности, масштаба, длины столбца и состояния столбца.|
|[COLUMN_NAME_PS_STATUS](#column_name_ps_status)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию точности, масштаба и состояния столбца.|
|[COLUMN_NAME_STATUS](#column_name_status)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию состояния столбца.|
|[COLUMN_NAME_TYPE](#column_name_type)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию типа данных.|
|[COLUMN_NAME_TYPE_PS](#column_name_type_ps)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию типа данных, точности и масштаба.|
|[COLUMN_NAME_TYPE_SIZE](#column_name_type_size)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию типа и размера данных.|
|[COLUMN_NAME_TYPE_STATUS](#column_name_type_status)|Представляет привязку к определенному столбцу в базе данных по имени. Поддерживает спецификацию типа данных и состояния столбца.|
|[END_COLUMN_MAP](#end_column_map)|Помечает конец записей схемы столбцов.|

## <a name="command-macros"></a>Макросы команд

| Имя | Описание |
|-|-|
|[DEFINE_COMMAND](#define_command)|Указывает команду, которая будет использоваться для создания набора строк при использовании класса [CCommand](../../data/oledb/ccommand-class.md) . Принимает только строковые типы, соответствующие указанному типу приложения (ANSI или Unicode). Вместо DEFINE_COMMAND рекомендуется использовать [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) .|
|[DEFINE_COMMAND_EX](#define_command_ex)|Указывает команду, которая будет использоваться для создания набора строк при использовании класса [CCommand](../../data/oledb/ccommand-class.md) . Поддерживает приложения ANSI и Юникод.|

## <a name="parameter-map-macros"></a>Макросы схемы параметров

| Имя | Описание |
|-|-|
|[BEGIN_PARAM_MAP](#begin_param_map)|Помечает начало записей параметра Map в классе записей пользователя.|
|[END_PARAM_MAP](#end_param_map)|Помечает конец записей схемы параметров.|
|[SET_PARAM_TYPE](#set_param_type)|Указывает COLUMN_ENTRY макросы, которые следуют за SET_PARAM_TYPEным макросом в качестве входных, выходных данных или входных и выходных данных.|

### <a name="atltraceerrorrecords"></a><a name="atltraceerrorrecords"></a> атлтрацеерроррекордс

При возвращении ошибки выводит OLE DB сведения о записи об ошибке на устройство дампа.

#### <a name="syntax"></a>Синтаксис

```cpp
inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);
```

#### <a name="parameters"></a>Параметры

*херр*<br/>
окне Значение HRESULT, возвращаемое функцией-членом OLE DB шаблона потребителя.

#### <a name="remarks"></a>Примечания

Если *Херр* не S_OK, `AtlTraceErrorRecords` выводит OLE DB сведения о записи об ошибке на устройство дампа (вкладка **Отладка** окна вывод или файл). Сведения о записи об ошибке, полученные от поставщика, включают номер строки, источник, описание, файл справки, контекст и идентификатор GUID для каждой записи записи об ошибке. `AtlTraceErrorRecords` выводит эти сведения только в отладочных сборках. В сборках выпуска это пустая заглушка. Дополнительные сведения см. в разделе [класс CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md).

### <a name="begin_accessor"></a><a name="begin_accessor"></a> BEGIN_ACCESSOR

Помечает начало записи метода доступа.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_ACCESSOR(num, bAuto)
```

#### <a name="parameters"></a>Параметры

*num*<br/>
окне Число с нулевым смещением для метода доступа в этой карте метода доступа.

*бауто*<br/>
окне Указывает, является ли этот метод доступа автоматическим методом доступа или ручным методом доступа. Если **`true`** значение равно, метод доступа имеет значение Auto; значение **`false`** , если метод доступа является ручным. Автоматический метод доступа означает, что данные извлекаться для вас при операциях перемещения.

#### <a name="remarks"></a>Примечания

В случае нескольких методов доступа в наборе строк необходимо указать BEGIN_ACCESSOR_MAP и использовать макрос BEGIN_ACCESSOR для каждого отдельного метода доступа. Макрос BEGIN_ACCESSOR завершен с помощью макроса END_ACCESSOR. Макрос BEGIN_ACCESSOR_MAP завершен с помощью макроса END_ACCESSOR_MAP.

#### <a name="example"></a>Пример

См. [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="begin_accessor_map"></a><a name="begin_accessor_map"></a> BEGIN_ACCESSOR_MAP

Отмечает начало карты записей метода доступа.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_ACCESSOR_MAP(x, num)
```

#### <a name="parameters"></a>Параметры

*x*<br/>
[входные данные] Имя класса записей пользователя.

*num*<br/>
[входные данные] Число методов доступа в этой карте метода доступа.

#### <a name="remarks"></a>Примечания

В случае нескольких методов доступа в наборе строк необходимо указать BEGIN_ACCESSOR_MAP в начале и использовать макрос BEGIN_ACCESSOR для каждого отдельного метода доступа. Макрос BEGIN_ACCESSOR завершен с помощью макроса END_ACCESSOR. Схема метода доступа завершается с помощью макроса END_ACCESSOR_MAP.

Если в записи пользователя имеется только один метод доступа, используйте макрос [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).

#### <a name="example"></a>Пример

```cpp
class CArtistsAccessor
{
public:
// Data Elements
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];
   short m_nAge;

// Output binding map
BEGIN_ACCESSOR_MAP(CArtistsAccessor, 2)
   BEGIN_ACCESSOR(0, true)
      COLUMN_ENTRY(1, m_szFirstName)
      COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false) // Not an auto accessor
      COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsAccessor, L" \
   SELECT \
      FirstName, \
      LastName, \
      Age \
      FROM Artists")
};
```

### <a name="end_accessor"></a><a name="end_accessor"></a> END_ACCESSOR

Помечает конец записи метода доступа.

#### <a name="syntax"></a>Синтаксис

```cpp
END_ACCESSOR()
```

#### <a name="remarks"></a>Примечания

Для нескольких методов доступа в наборе строк необходимо указать BEGIN_ACCESSOR_MAP и использовать макрос BEGIN_ACCESSOR для каждого отдельного метода доступа. Макрос BEGIN_ACCESSOR завершен с помощью макроса END_ACCESSOR. Макрос BEGIN_ACCESSOR_MAP завершен с помощью макроса END_ACCESSOR_MAP.

#### <a name="example"></a>Пример

См. [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="end_accessor_map"></a><a name="end_accessor_map"></a> END_ACCESSOR_MAP

Помечает конец записей схемы метода доступа.

#### <a name="syntax"></a>Синтаксис

```cpp
END_ACCESSOR_MAP()
```

#### <a name="remarks"></a>Примечания

Для нескольких методов доступа в наборе строк необходимо указать BEGIN_ACCESSOR_MAP и использовать макрос BEGIN_ACCESSOR для каждого отдельного метода доступа. Макрос BEGIN_ACCESSOR завершен с помощью макроса END_ACCESSOR. Макрос BEGIN_ACCESSOR_MAP завершен с помощью макроса END_ACCESSOR_MAP.

#### <a name="example"></a>Пример

См. [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="begin_column_map"></a><a name="begin_column_map"></a> BEGIN_COLUMN_MAP

Отмечает начало карты записей столбцов.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_COLUMN_MAP(x)
```

#### <a name="parameters"></a>Параметры

*x*<br/>
[входные данные] Имя класса записей пользователя, производного от `CAccessor`.

#### <a name="remarks"></a>Примечания

Этот макрос используется при наличии одного метода доступа в наборе строк. При наличии нескольких методов доступа в наборе строк, используйте [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

Макрос BEGIN_COLUMN_MAP завершен с помощью макроса END_COLUMN_MAP. Этот макрос используется, если имеется только один метод доступа, необходимый для записи пользователя.

Столбцы соответствуют полям в наборе строк, который нужно привязать.

#### <a name="example"></a>Пример

Ниже приведен пример карты столбцов и параметров.

<!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->

### <a name="blob_entry"></a><a name="blob_entry"></a> BLOB_ENTRY

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки большого двоичного объекта ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))).

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)
```

#### <a name="parameters"></a>Параметры

*нординал*<br/>
окне Номер столбца.

*IID*<br/>
окне GUID интерфейса, например `IDD_ISequentialStream` , используемый для получения большого двоичного объекта.

*flags*<br/>
окне Флаги режима хранения, как определено в модели структурированного хранилища OLE (например, `STGM_READ` ).

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="example"></a>Пример

Узнайте [, как можно получить большой двоичный объект?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_length"></a><a name="blob_entry_length"></a> BLOB_ENTRY_LENGTH

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки большого двоичного объекта ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Аналогично [BLOB_ENTRY](../../data/oledb/blob-entry.md), за исключением того, что этот макрос также получает длину в байтах СТОЛБЦА большого двоичного объекта.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)
```

#### <a name="parameters"></a>Параметры

*нординал*<br/>
окне Номер столбца.

*IID*<br/>
окне GUID интерфейса, например `IDD_ISequentialStream` , используемый для получения большого двоичного объекта.

*flags*<br/>
окне Флаги режима хранения, как определено в модели структурированного хранилища OLE (например, `STGM_READ` ).

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
заполняет (Фактическая) Длина столбца большого двоичного объекта в байтах.

#### <a name="example"></a>Пример

Узнайте [, как можно получить большой двоичный объект?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_length_status"></a><a name="blob_entry_length_status"></a> BLOB_ENTRY_LENGTH_STATUS

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки большого двоичного объекта ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Аналогично [BLOB_ENTRY](../../data/oledb/blob-entry.md), за исключением того, что этот макрос также получает длину и состояние столбца большого двоичного объекта.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_ENTRY_LENGTH_STATUS(
    nOrdinal,
    IID,
    flags,
    data,
    length,
    status )
```

#### <a name="parameters"></a>Параметры

*нординал*<br/>
окне Номер столбца.

*IID*<br/>
окне GUID интерфейса, например `IDD_ISequentialStream` , используемый для получения большого двоичного объекта.

*flags*<br/>
окне Флаги режима хранения, как определено в модели структурированного хранилища OLE (например, `STGM_READ` ).

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
заполняет (Фактическая) Длина столбца большого двоичного объекта в байтах.

*status*<br/>
заполняет Состояние столбца данных большого двоичного объекта.

#### <a name="example"></a>Пример

Узнайте [, как можно получить большой двоичный объект?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_status"></a><a name="blob_entry_status"></a> BLOB_ENTRY_STATUS

Используется с BEGIN_COLUMN_MAP или BEGIN_ACCESSOR_MAP для привязки большого двоичного объекта ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Аналогично [BLOB_ENTRY](../../data/oledb/blob-entry.md), за исключением того, что этот макрос также получает состояние столбца большого двоичного объекта.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_ENTRY_STATUS(nOrdinal, IID, flags, data, status)
```

#### <a name="parameters"></a>Параметры

*нординал*<br/>
окне Номер столбца.

*IID*<br/>
окне GUID интерфейса, например `IDD_ISequentialStream` , используемый для получения большого двоичного объекта.

*flags*<br/>
окне Флаги режима хранения, как определено в модели структурированного хранилища OLE (например, `STGM_READ` ).

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*status*<br/>
заполняет Состояние поля BLOB-объекта.

#### <a name="example"></a>Пример

Узнайте [, как можно получить большой двоичный объект?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_name"></a><a name="blob_name"></a> BLOB_NAME

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки большого двоичного объекта ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Аналогично [BLOB_ENTRY](../../data/oledb/blob-entry.md), за исключением того, что этот макрос принимает имя столбца вместо номера столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_NAME(pszName, IID, flags, data )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*IID*<br/>
окне GUID интерфейса, например `IDD_ISequentialStream` , используемый для получения большого двоичного объекта.

*flags*<br/>
окне Флаги режима хранения, как определено в модели структурированного хранилища OLE (например, `STGM_READ` ).

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="example"></a>Пример

Узнайте [, как можно получить большой двоичный объект?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_name_length"></a><a name="blob_name_length"></a> BLOB_NAME_LENGTH

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки большого двоичного объекта ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Аналогично [BLOB_NAME](../../data/oledb/blob-name.md), за исключением того, что этот макрос также получает длину в байтах столбца данных большого двоичного объекта.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*IID*<br/>
окне GUID интерфейса, например `IDD_ISequentialStream` , используемый для получения большого двоичного объекта.

*flags*<br/>
окне Флаги режима хранения, как определено в модели структурированного хранилища OLE (например, `STGM_READ` ).

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
заполняет (Фактическая) Длина столбца большого двоичного объекта в байтах.

### <a name="blob_name_length_status"></a><a name="blob_name_length_status"></a> BLOB_NAME_LENGTH_STATUS

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки большого двоичного объекта ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Аналогично [BLOB_NAME](../../data/oledb/blob-name.md), за исключением того, что этот макрос также получает длину и состояние столбца данных большого двоичного объекта.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_NAME_LENGTH_STATUS(pszName, IID, flags, data, length, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*IID*<br/>
окне GUID интерфейса, например `IDD_ISequentialStream` , используемый для получения большого двоичного объекта.

*flags*<br/>
окне Флаги режима хранения, как определено в модели структурированного хранилища OLE (например, `STGM_READ` ).

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
заполняет (Фактическая) Длина столбца большого двоичного объекта в байтах.

*status*<br/>
заполняет Состояние поля BLOB-объекта.

### <a name="blob_name_status"></a><a name="blob_name_status"></a> BLOB_NAME_STATUS

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки большого двоичного объекта ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Аналогично [BLOB_NAME](../../data/oledb/blob-name.md), за исключением того, что этот макрос также получает состояние столбца данных большого двоичного объекта.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_NAME_STATUS(pszName, IID, flags, data, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*IID*<br/>
окне GUID интерфейса, например `IDD_ISequentialStream` , используемый для получения большого двоичного объекта.

*flags*<br/>
окне Флаги режима хранения, как определено в модели структурированного хранилища OLE (например, `STGM_READ` ).

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*status*<br/>
заполняет Состояние поля BLOB-объекта.

### <a name="bookmark_entry"></a><a name="bookmark_entry"></a> BOOKMARK_ENTRY

Привязывает столбец закладки.

#### <a name="syntax"></a>Синтаксис

```cpp
BOOKMARK_ENTRY(variable)
```

#### <a name="parameters"></a>Параметры

*variable*<br/>
окне Переменная, которая должна быть привязана к столбцу закладки.

#### <a name="example"></a>Пример

```cpp
class CArtistsBookmark
{
public:
// Data Elements
   CBookmark<4> m_bookmark;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

// Output binding map
BEGIN_COLUMN_MAP(CArtistsBookmark)
   BOOKMARK_ENTRY(m_bookmark)
   COLUMN_ENTRY(1, m_nAge)
   COLUMN_ENTRY(2, m_szFirstName)
   COLUMN_ENTRY(3, m_szLastName)
END_COLUMN_MAP()

   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_BOOKMARKS, true);
   }

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsBookmark, L" \
   SELECT \
      Age, \
      FirstName, \
      LastName \
      FROM Artists")
};
```

Дополнительные сведения см. [в разделе Использование закладок](using-bookmarks.md) и [класса CBookmark](../../data/oledb/cbookmark-class.md).

### <a name="column_entry"></a><a name="column_entry"></a> COLUMN_ENTRY

Представляет привязку набора строк к определенному столбцу в наборе строк.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY(nOrdinal, data)
```

#### <a name="parameters"></a>Параметры

См. раздел [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*.

*нординал*<br/>
окне Номер столбца.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="remarks"></a>Примечания

Макрос COLUMN_ENTRY используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

#### <a name="example"></a>Пример

См. примеры в разделах о макросах, [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="column_entry_ex"></a><a name="column_entry_ex"></a> COLUMN_ENTRY_EX

Представляет привязку набора строк к определенному столбцу в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>Параметры

См. раздел [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*.

*нординал*<br/>
окне Номер столбца.

*wType*<br/>
окне Тип данных.

*нленгс*<br/>
окне Размер данных в байтах.

*нпреЦисион*<br/>
окне Максимальная точность, используемая при получении данных, и *wType* — `DBTYPE_NUMERIC` . В противном случае этот параметр игнорируется.

*нскале*<br/>
окне Шкала, используемая при получении данных, *wType* — `DBTYPE_NUMERIC` или `DBTYPE_DECIMAL` .

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
окне Переменная, которая должна быть привязана к длине столбца.

*status*<br/>
окне Переменная, которая должна быть привязана к состоянию столбца.

#### <a name="remarks"></a>Примечания

Макрос COLUMN_ENTRY_EX используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

#### <a name="example"></a>Пример

См. [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="column_entry_length"></a><a name="column_entry_length"></a> COLUMN_ENTRY_LENGTH

Представляет привязку набора строк к определенному столбцу в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)
```

#### <a name="parameters"></a>Параметры

См. раздел [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*.

*нординал*<br/>
окне Номер столбца, начинающийся с единицы. Закладка соответствует нулю столбца.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
окне Переменная, которая должна быть привязана к длине столбца.

#### <a name="remarks"></a>Примечания

Этот макрос поддерживает переменную *длины* . Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_length_status"></a><a name="column_entry_length_status"></a> COLUMN_ENTRY_LENGTH_STATUS

Представляет привязку набора строк к определенному столбцу в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_LENGTH_STATUS(nOrdinal, data, length, status)
```

#### <a name="parameters"></a>Параметры

См. раздел [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*.

*нординал*<br/>
окне Номер столбца.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
окне Переменная, которая должна быть привязана к длине столбца.

*status*<br/>
окне Переменная, которая должна быть привязана к состоянию столбца.

#### <a name="remarks"></a>Примечания

Используйте этот макрос, если требуется поддержка переменных длины и состояния. Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_ps"></a><a name="column_entry_ps"></a> COLUMN_ENTRY_PS

Представляет привязку набора строк к определенному столбцу в наборе строк.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_PS(nOrdinal, nPrecision, nScale, data)
```

#### <a name="parameters"></a>Параметры

См. раздел [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*.

*нординал*<br/>
окне Номер столбца.

*нпреЦисион*<br/>
окне Максимальная точность столбца, который необходимо привязать.

*нскале*<br/>
окне Масштаб столбца, который необходимо привязать.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="remarks"></a>Примечания

Позволяет указать точность и масштаб столбца, который необходимо привязать. Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_ps_length"></a><a name="column_entry_ps_length"></a> COLUMN_ENTRY_PS_LENGTH

Представляет привязку набора строк к определенному столбцу в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_PS_LENGTH(nOrdinal, nPrecision, nScale, data, length)
```

#### <a name="parameters"></a>Параметры

См. раздел [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*.

*нординал*<br/>
окне Номер столбца, начинающийся с единицы. Закладка соответствует нулю столбца.

*нпреЦисион*<br/>
окне Максимальная точность столбца, который необходимо привязать.

*нскале*<br/>
окне Масштаб столбца, который необходимо привязать.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
окне Переменная, которая должна быть привязана к длине столбца.

#### <a name="remarks"></a>Примечания

Позволяет указать точность и масштаб столбца, который необходимо привязать. Этот макрос поддерживает переменную *длины* . Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_ps_length_status"></a><a name="column_entry_ps_length_status"></a> COLUMN_ENTRY_PS_LENGTH_STATUS

Представляет привязку набора строк к определенному столбцу в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_PS_LENGTH_STATUS(nOrdinal, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>Параметры

См. раздел [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*.

*нординал*<br/>
окне Номер столбца.

*нпреЦисион*<br/>
окне Максимальная точность столбца, который необходимо привязать.

*нскале*<br/>
окне Масштаб столбца, который необходимо привязать.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
окне Переменная, которая должна быть привязана к длине столбца.

*status*<br/>
окне Переменная, которая должна быть привязана к состоянию столбца.

#### <a name="remarks"></a>Примечания

Позволяет указать точность и масштаб столбца, который необходимо привязать. Используйте этот макрос, если требуется поддержка переменных длины и состояния. Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_ps_status"></a><a name="column_entry_ps_status"></a> COLUMN_ENTRY_PS_STATUS

Представляет привязку набора строк к определенному столбцу в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_PS_STATUS(nOrdinal, nPrecision, nScale, data, status)
```

#### <a name="parameters"></a>Параметры

См. раздел [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*.

*нординал*<br/>
окне Номер столбца.

*нпреЦисион*<br/>
окне Максимальная точность столбца, который необходимо привязать.

*нскале*<br/>
окне Масштаб столбца, который необходимо привязать.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*status*<br/>
окне Переменная, которая должна быть привязана к состоянию столбца.

#### <a name="remarks"></a>Примечания

Позволяет указать точность и масштаб столбца, который необходимо привязать. Этот макрос поддерживает переменную *состояния* . Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_status"></a><a name="column_entry_status"></a> COLUMN_ENTRY_STATUS

Представляет привязку набора строк к определенному столбцу в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_STATUS(nOrdinal, data, status)
```

#### <a name="parameters"></a>Параметры

См. раздел [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*.

*нординал*<br/>
окне Номер столбца.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*status*<br/>
окне Переменная, которая должна быть привязана к состоянию столбца.

#### <a name="remarks"></a>Примечания

Этот макрос поддерживает переменную *состояния* . Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_type"></a><a name="column_entry_type"></a> COLUMN_ENTRY_TYPE

Представляет привязку к определенному столбцу в базе данных. Поддерживает параметр *типа* .

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)
```

#### <a name="parameters"></a>Параметры

*нординал*<br/>
окне Номер столбца.

*wType*<br/>
окне Тип данных записи столбца.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="remarks"></a>Примечания

Этот макрос является специализированным вариантом макроса [COLUMN_ENTRY](../../data/oledb/column-entry.md) , который предоставляет средства для указания типа данных.

### <a name="column_entry_type_size"></a><a name="column_entry_type_size"></a> COLUMN_ENTRY_TYPE_SIZE

Представляет привязку к определенному столбцу в базе данных. Поддерживает параметры *типа* и *размера* .

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)
```

#### <a name="parameters"></a>Параметры

*нординал*<br/>
окне Номер столбца.

*wType*<br/>
окне Тип данных записи столбца.

*нленгс*<br/>
окне Размер записи столбца в байтах.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="remarks"></a>Примечания

Этот макрос является специализированным вариантом макроса [COLUMN_ENTRY](../../data/oledb/column-entry.md) , который предоставляет средства для указания размера и типа данных.

### <a name="column_name"></a><a name="column_name"></a> COLUMN_NAME

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [COLUMN_ENTRY](../../data/oledb/column-entry.md), за исключением того, что этот макрос принимает имя столбца вместо номера столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME(pszName, data)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="remarks"></a>Примечания

Макросы COLUMN_NAME_ * используются в тех же местах, что и [COLUMN_ENTRY](../../data/oledb/column-entry.md):

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_name_ex"></a><a name="column_name_ex"></a> COLUMN_NAME_EX

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает тип данных, размер, точность, масштаб, длину столбца и состояние столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_EX(pszName, wType, nLength, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*wType*<br/>
окне Тип данных.

*нленгс*<br/>
окне Размер данных в байтах.

*нпреЦисион*<br/>
окне Максимальная точность, используемая при получении данных, и *wType* — `DBTYPE_NUMERIC` . В противном случае этот параметр игнорируется.

*нскале*<br/>
окне Шкала, используемая при получении данных, *wType* — `DBTYPE_NUMERIC` или `DBTYPE_DECIMAL` .

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
окне Переменная, которая должна быть привязана к длине столбца.

*status*<br/>
окне Переменная, которая должна быть привязана к состоянию столбца.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="column_name_length"></a><a name="column_name_length"></a> COLUMN_NAME_LENGTH

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также имеет длину столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_LENGTH(pszName, data, length)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
окне Переменная, которая должна быть привязана к длине столбца.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="column_name_length_status"></a><a name="column_name_length_status"></a> COLUMN_NAME_LENGTH_STATUS

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает длину столбца и состояние столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_LENGTH_STATUS(pszName, data, length, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
окне Переменная, которая должна быть привязана к длине столбца.

*status*<br/>
окне Переменная, которая должна быть привязана к состоянию столбца.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="column_name_ps"></a><a name="column_name_ps"></a> COLUMN_NAME_PS

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также имеет точность и масштаб.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_PS(pszName, nPrecision, nScale, data )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*нпреЦисион*<br/>
окне Максимальная точность столбца, который необходимо привязать.

*нскале*<br/>
окне Масштаб столбца, который необходимо привязать.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="column_name_ps_length"></a><a name="column_name_ps_length"></a> COLUMN_NAME_PS_LENGTH

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также имеет точность, масштаб и длину столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_PS_LENGTH(pszName, nPrecision, nScale, data, length )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*нпреЦисион*<br/>
окне Максимальная точность столбца, который необходимо привязать.

*нскале*<br/>
окне Масштаб столбца, который необходимо привязать.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
окне Переменная, которая должна быть привязана к длине столбца.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="column_name_ps_length_status"></a><a name="column_name_ps_length_status"></a> COLUMN_NAME_PS_LENGTH_STATUS

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также имеет точность, масштаб, длину столбца и состояние столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_PS_LENGTH_STATUS(pszName, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*нпреЦисион*<br/>
окне Максимальная точность столбца, который необходимо привязать.

*нскале*<br/>
окне Масштаб столбца, который необходимо привязать.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*length*<br/>
окне Переменная, которая должна быть привязана к длине столбца.

*status*<br/>
окне Переменная, которая должна быть привязана к состоянию столбца.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="column_name_ps_status"></a><a name="column_name_ps_status"></a> COLUMN_NAME_PS_STATUS

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также имеет точность, масштаб и состояние столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_PS_STATUS(pszName, nPrecision, nScale, data, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*нпреЦисион*<br/>
окне Максимальная точность столбца, который необходимо привязать.

*нскале*<br/>
окне Масштаб столбца, который необходимо привязать.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*status*<br/>
окне Переменная, которая должна быть привязана к состоянию столбца.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="column_name_status"></a><a name="column_name_status"></a> COLUMN_NAME_STATUS

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает состояние столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_STATUS(pszName, data, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

*status*<br/>
окне Переменная, которая должна быть привязана к состоянию столбца.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="column_name_type"></a><a name="column_name_type"></a> COLUMN_NAME_TYPE

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает тип данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_TYPE(pszName, wType, data)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*wType*<br/>
окне Тип данных.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="column_name_type_ps"></a><a name="column_name_type_ps"></a> COLUMN_NAME_TYPE_PS

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает тип данных, точность и масштаб.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_TYPE_PS(pszName, wType, nPrecision, nScale, data)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*wType*<br/>
окне Тип данных.

*нпреЦисион*<br/>
окне Максимальная точность, используемая при получении данных, и *wType* — `DBTYPE_NUMERIC` . В противном случае этот параметр игнорируется.

*нскале*<br/>
окне Шкала, используемая при получении данных, *wType* — `DBTYPE_NUMERIC` или `DBTYPE_DECIMAL` .

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="column_name_type_size"></a><a name="column_name_type_size"></a> COLUMN_NAME_TYPE_SIZE

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает тип и размер данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*wType*<br/>
окне Тип данных.

*нленгс*<br/>
окне Размер данных в байтах.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="column_name_type_status"></a><a name="column_name_type_status"></a> COLUMN_NAME_TYPE_STATUS

Представляет привязку набора строк к определенному столбцу в наборе строк. Аналогично [column_name](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает данные о состоянии типа и столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_TYPE_STATUS(pszName, wType, status, data)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
окне Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив символ «L» перед именем, например: `L"MyColumn"` .

*wType*<br/>
окне Тип данных.

*status*<br/>
окне Переменная, которая должна быть привязана к состоянию столбца.

*data*<br/>
окне Соответствующий элемент данных в записи пользователя.

#### <a name="remarks"></a>Примечания

Сведения о том, где используются макросы COLUMN_NAME_ *, см. в разделе [column_name](../../data/oledb/column-name.md) .

### <a name="end_column_map"></a><a name="end_column_map"></a> END_COLUMN_MAP

Помечает конец записей схемы столбцов.

#### <a name="syntax"></a>Синтаксис

```cpp
END_COLUMN_MAP()
```

#### <a name="remarks"></a>Примечания

Он используется с одним методом доступа к набору строк. Макрос BEGIN_COLUMN_MAP завершен с помощью макроса END_COLUMN_MAP.

#### <a name="example"></a>Пример

См. [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).

### <a name="define_command"></a><a name="define_command"></a> DEFINE_COMMAND

Указывает команду, которая будет использоваться для создания набора строк при использовании класса [CCommand](../../data/oledb/ccommand-class.md) . Принимает только строковые типы, соответствующие указанному типу приложения (ANSI или Unicode).

> [!NOTE]
> Вместо DEFINE_COMMAND рекомендуется использовать [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) .

#### <a name="syntax"></a>Синтаксис

```cpp
DEFINE_COMMAND(x, szCommand)
```

#### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя класса записи (команды) пользователя.

*сзкомманд*<br/>
окне Командная строка, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md).

#### <a name="remarks"></a>Примечания

Указанная командная строка будет использоваться по умолчанию, если не указать текст команды в методе [CCommand:: Open](../../data/oledb/ccommand-open.md) .

Этот макрос принимает строки ANSI, если вы создаете приложение в формате ANSI, или строки в Юникоде, если приложение создается в Юникоде. Рекомендуется использовать [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) вместо DEFINE_COMMAND, поскольку первый принимает строки в Юникоде независимо от типа приложения ANSI или Unicode.

#### <a name="example"></a>Пример

См. [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="define_command_ex"></a><a name="define_command_ex"></a> DEFINE_COMMAND_EX

Указывает команду, которая будет использоваться для создания набора строк при использовании класса [CCommand](../../data/oledb/ccommand-class.md) . Поддерживает приложения в Юникоде и ANSI.

#### <a name="syntax"></a>Синтаксис

```cpp
DEFINE_COMMAND_EX(x, wszCommand)
```

#### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя класса записи (команды) пользователя.

*всзкомманд*<br/>
окне Командная строка, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md).

#### <a name="remarks"></a>Примечания

Указанная командная строка будет использоваться по умолчанию, если не указать текст команды в методе [CCommand:: Open](../../data/oledb/ccommand-open.md) .

Этот макрос принимает строки в Юникоде независимо от типа приложения. Этот макрос предпочтительнее [DEFINE_COMMAND](../../data/oledb/define-command.md) , так как он поддерживает Юникод, а также приложения ANSI.

#### <a name="example"></a>Пример

См. [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="begin_param_map"></a><a name="begin_param_map"></a> BEGIN_PARAM_MAP

Помечает начало записей схемы параметров.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_PARAM_MAP(x)
```

#### <a name="parameters"></a>Параметры

*x*<br/>
[входные данные] Имя класса записей пользователя.

#### <a name="remarks"></a>Примечания

Параметры используются [командами](/previous-versions/windows/desktop/ms724608(v=vs.85)).

#### <a name="example"></a>Пример

См. пример для макроса [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) .

### <a name="end_param_map"></a><a name="end_param_map"></a> END_PARAM_MAP

Помечает конец записей схемы параметров.

#### <a name="syntax"></a>Синтаксис

```cpp
END_PARAM_MAP()
```

#### <a name="example"></a>Пример

См. пример для макроса [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) .

### <a name="set_param_type"></a><a name="set_param_type"></a> SET_PARAM_TYPE

Указывает COLUMN_ENTRY макросы, которые следуют за входными, выходными и входными макросами SET_PARAM_TYPE.

#### <a name="syntax"></a>Синтаксис

```cpp
SET_PARAM_TYPE(type)
```

#### <a name="parameters"></a>Параметры

*type*<br/>
[входные данные] Тип, задаваемый для параметра.

#### <a name="remarks"></a>Примечания

Поставщики поддерживают только входные и выходные типы параметров, поддерживаемые в базовом источнике данных. Тип является сочетанием одного или нескольких `DBPARAMIO` значений (см. [структуры DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*):

- `DBPARAMIO_NOTPARAM` Метод доступа не имеет параметров. Как правило, `eParamIO` это значение устанавливается в методы доступа к строкам для напоминания пользователю о том, что параметры игнорируются.

- `DBPARAMIO_INPUT` Входной параметр.

- `DBPARAMIO_OUTPUT` Выходной параметр.

- `DBPARAMIO_INPUT | DBPARAMIO_OUTPUT` Параметр является как входным, так и выходным параметром.

#### <a name="example"></a>Пример

```cpp
class CArtistsProperty
{
public:
   short m_nReturn;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

BEGIN_PARAM_MAP(CArtistsProperty)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_nReturn)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_nAge)
END_PARAM_MAP()

BEGIN_COLUMN_MAP(CArtistsProperty)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
END_COLUMN_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsProperty, L" \
      { ? = SELECT Age FROM Artists WHERE Age < ? }")
};
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные функции для OLE DB шаблонов потребителей](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
