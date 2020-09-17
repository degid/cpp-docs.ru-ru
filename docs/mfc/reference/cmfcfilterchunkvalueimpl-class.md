---
title: Класс CMFCFilterChunkValueImpl
ms.date: 11/04/2016
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
helpviewer_keywords:
- CMFCFilterChunkValueImpl [MFC], CMFCFilterChunkValueImpl
- CMFCFilterChunkValueImpl [MFC], Clear
- CMFCFilterChunkValueImpl [MFC], CopyChunk
- CMFCFilterChunkValueImpl [MFC], CopyFrom
- CMFCFilterChunkValueImpl [MFC], GetChunkGUID
- CMFCFilterChunkValueImpl [MFC], GetChunkPID
- CMFCFilterChunkValueImpl [MFC], GetChunkType
- CMFCFilterChunkValueImpl [MFC], GetString
- CMFCFilterChunkValueImpl [MFC], GetValue
- CMFCFilterChunkValueImpl [MFC], GetValueNoAlloc
- CMFCFilterChunkValueImpl [MFC], IsValid
- CMFCFilterChunkValueImpl [MFC], SetBoolValue
- CMFCFilterChunkValueImpl [MFC], SetDwordValue
- CMFCFilterChunkValueImpl [MFC], SetFileTimeValue
- CMFCFilterChunkValueImpl [MFC], SetInt64Value
- CMFCFilterChunkValueImpl [MFC], SetIntValue
- CMFCFilterChunkValueImpl [MFC], SetLongValue
- CMFCFilterChunkValueImpl [MFC], SetSystemTimeValue
- CMFCFilterChunkValueImpl [MFC], SetTextValue
- CMFCFilterChunkValueImpl [MFC], SetChunk
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
ms.openlocfilehash: c89d41f7db43d9504bfc22cbf35a59fcceb511e2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752361"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>Класс CMFCFilterChunkValueImpl

Это класс, который упрощает логику пары как куска, так и стоимости свойства.

## <a name="syntax"></a>Синтаксис

```
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCFilterChunkValueImpl:: CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Уничтожает объект.|
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Создает объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::Clear](#clear)|Очищает ChunkValue.|
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Копирует этот кусок в структуру, описывающую характеристики куска.|
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Инициализирует это значение фрагмента из другого значения.|
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|Извлекает кусок GUID.|
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Извлекает кусок PID (идентификатор свойства).|
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Получает тип куска.|
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Извлекает значение строки.|
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Извлекает значение в качестве выделенного пропварианта.|
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Возвращает нераспределенное (внутреннее значение) значение.|
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|Проверяет, является ли это значение свойства действительным или нет.|
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Перегружен. Устанавливает свойство ключом к Boolean.|
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Устанавливает свойство ключом к DWORD.|
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Устанавливает свойство ключом к времени файла.|
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Устанавливает свойство ключом к int64.|
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Устанавливает свойство ключом к Int.|
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|Устанавливает свойство ключом к LONG.|
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Устанавливает свойство ключом к SystemTime.|
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Устанавливает свойство ключом к строке Unicode.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|Функция помощника, которая устанавливает общие свойства куска.|

## <a name="remarks"></a>Примечания

Чтобы использовать, вы просто создаете CMFCFilterChunkValueValueImpl класса правильного вида

Пример

CMFCFilterChunkValueImpl кусок;

hr й кусок. SetBoolValue (PKEY_IsAttachment, правда);

или диспетчер конфигурации служб

hr й кусок. SetFileTimeValue (PKEY_ItemDate, ftLastModified);

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ATL::IFilterChunkValue`

[CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cmfcfilterchunkvalueimplclear"></a><a name="clear"></a>CMFCFilterChunkValueImpl::Clear

Очищает ChunkValue.

```cpp
void Clear();
```

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="cmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl

Создает объект.

```
CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="_dtorcmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl:: CMFCFilterChunkValueImpl

Уничтожает объект.

```
virtual ~CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplcopychunk"></a><a name="copychunk"></a>CMFCFilterChunkValueImpl::CopyChunk

Копирует этот кусок в структуру, описывающую характеристики куска.

```
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```

### <a name="parameters"></a>Параметры

*pStatChunk*<br/>
Указатель к значению назначения, описывающий характеристики куска.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplcopyfrom"></a><a name="copyfrom"></a>CMFCFilterChunkValueImpl::CopyFrom

Инициализирует это значение фрагмента из другого значения.

```cpp
void CopyFrom (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Определяет исходное значение для копирования.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplgetchunkguid"></a><a name="getchunkguid"></a>CMFCFilterChunkValueImpl::GetChunkGUID

Извлекает кусок GUID.

```
REFGUID GetChunkGUID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на GUID, идентифицирующий кусок.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplgetchunkpid"></a><a name="getchunkpid"></a>CMFCFilterChunkValueImpl::GetChunkPID

Извлекает кусок PID (идентификатор свойства).

```
DWORD GetChunkPID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD, содержащее идентификатор свойства.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplgetchunktype"></a><a name="getchunktype"></a>CMFCFilterChunkValueImpl::GetChunkType

Извлекает тип куска.

```
CHUNKSTATE GetChunkType() const;
```

### <a name="return-value"></a>Возвращаемое значение

ЗНАЧЕНИЕ CHUNKSTATE, в котором указывается, является ли текущий кусок свойством типа текста или свойством типа значения.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplgetstring"></a><a name="getstring"></a>CMFCFilterChunkValueImpl::GetString

Извлекает значение строки.

```
CString &GetString();
```

### <a name="return-value"></a>Возвращаемое значение

Строка, содержащая значение фрагмента.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplgetvalue"></a><a name="getvalue"></a>CMFCFilterChunkValueImpl::GetValue

Извлекает значение в качестве выделенного пропварианта.

```
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```

### <a name="parameters"></a>Параметры

*ppPropVariant*<br/>
Когда функция возвращается, этот параметр содержит значение фрагмента.

### <a name="return-value"></a>Возвращаемое значение

S_OK, если PROPVARIANT был успешно выделен и значение куска было успешно скопировано на *ppPropVariant;* в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplgetvaluenoalloc"></a><a name="getvaluenoalloc"></a>CMFCFilterChunkValueImpl::GetValueNoAlloc

Возвращает нераспределенное (внутреннее значение) значение.

```
PROPVARIANT GetValueNoAlloc ();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текущее значение фрагмента.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplisvalid"></a><a name="isvalid"></a>CMFCFilterChunkValueImpl::IsValid

Проверяет, является ли это значение свойства действительным или нет.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если текущее значение куска является действительным; в противном случае FALSE.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplsetboolvalue"></a><a name="setboolvalue"></a>CMFCFilterChunkValueImpl::SetBoolValue

Перегружен. Устанавливает свойство ключом к Boolean.

```
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    VARIANT_BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*Pkey*<br/>
Определяет ключ от свойств.

*bVal*<br/>
Определяет значение фрагмента для установки.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент свойство типа текста или свойство типа значения. Значения флага взяты из перечисления CHUNKSTATE.

*locale*<br/>
Язык и подязык, связанные с куском текста. Локт локал используется индексаторами документов для выполнения надлежащего нарушения текста. Если фрагмент не является ни текстовым шрифтом, ни типом значения с VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле игнорируется.

*cwcLenИсточник*<br/>
Длина символов исходного текста, из которого был получен текущий кусок. Нулевое значение означает соответствие символа по символу между исходным текстом и производным текстом. Ненулевое значение означает, что такой прямой корреспонденции не существует.

*cwcStartИсточник*<br/>
Смещение, из которого начинается исходный текст для производного куска.

*chunkBreakType*<br/>
Тип разрыва, отделяя предыдущий фрагмент от текущего фрагмента. Значения от CHUNK_BREAKTYPE перечисления.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplsetchunk"></a><a name="setchunk"></a>CMFCFilterChunkValueImpl::SetChunk

Функция помощника, которая устанавливает общие свойства куска.

```
HRESULT SetChunk(
    REFPROPERTYKEY pkey,
    CHUNKSTATE chunkType=CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*Pkey*<br/>
Определяет ключ от свойств.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент свойство типа текста или свойство типа значения. Значения флага взяты из перечисления CHUNKSTATE.

*locale*<br/>
Язык и подязык, связанные с куском текста. Локт локал используется индексаторами документов для выполнения надлежащего нарушения текста. Если фрагмент не является ни текстовым шрифтом, ни типом значения с VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле игнорируется.

*cwcLenИсточник*<br/>
Длина символов исходного текста, из которого был получен текущий кусок. Нулевое значение означает соответствие символа по символу между исходным текстом и производным текстом. Ненулевое значение означает, что такой прямой корреспонденции не существует.

*cwcStartИсточник*<br/>
Смещение, из которого начинается исходный текст для производного куска.

*chunkBreakType*<br/>
Тип разрыва, отделяя предыдущий фрагмент от текущего фрагмента. Значения от CHUNK_BREAKTYPE перечисления.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplsetdwordvalue"></a><a name="setdwordvalue"></a>CMFCFilterChunkValueImpl::SetDwordValue

Установите свойство ключом к DWORD.

```
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,
    DWORD dwVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*Pkey*<br/>
Определяет ключ от свойств.

*dwVal*<br/>
Определяет значение фрагмента для установки.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент свойство типа текста или свойство типа значения. Значения флага взяты из перечисления CHUNKSTATE.

*locale*<br/>
Язык и подязык, связанные с куском текста. Локт локал используется индексаторами документов для выполнения надлежащего нарушения текста. Если фрагмент не является ни текстовым шрифтом, ни типом значения с VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле игнорируется.

*cwcLenИсточник*<br/>
Длина символов исходного текста, из которого был получен текущий кусок. Нулевое значение означает соответствие символа по символу между исходным текстом и производным текстом. Ненулевое значение означает, что такой прямой корреспонденции не существует.

*cwcStartИсточник*<br/>
Смещение, из которого начинается исходный текст для производного куска.

*chunkBreakType*<br/>
Тип разрыва, отделяя предыдущий фрагмент от текущего фрагмента. Значения от CHUNK_BREAKTYPE перечисления.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplsetfiletimevalue"></a><a name="setfiletimevalue"></a>CMFCFilterChunkValueImpl::SetFileTimeValue

Установите свойство ключом к времени файла.

```
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,
    FILETIME dtVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*Pkey*<br/>
Определяет ключ от свойств.

*dtVal*<br/>
Определяет значение фрагмента для установки.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент свойство типа текста или свойство типа значения. Значения флага взяты из перечисления CHUNKSTATE.

*locale*<br/>
Язык и подязык, связанные с куском текста. Локт локал используется индексаторами документов для выполнения надлежащего нарушения текста. Если фрагмент не является ни текстовым шрифтом, ни типом значения с VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле игнорируется.

*cwcLenИсточник*<br/>
Длина символов исходного текста, из которого был получен текущий кусок. Нулевое значение означает соответствие символа по символу между исходным текстом и производным текстом. Ненулевое значение означает, что такой прямой корреспонденции не существует.

*cwcStartИсточник*<br/>
Смещение, из которого начинается исходный текст для производного куска.

*chunkBreakType*<br/>
Тип разрыва, отделяя предыдущий фрагмент от текущего фрагмента. Значения от CHUNK_BREAKTYPE перечисления.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplsetint64value"></a><a name="setint64value"></a>CMFCFilterChunkValueImpl::SetInt64Value

Установите свойство ключом к int64.

```
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,
    __int64 nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*Pkey*<br/>
Определяет ключ от свойств.

*nVal*<br/>
Определяет значение фрагмента для установки.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент свойство типа текста или свойство типа значения. Значения флага взяты из перечисления CHUNKSTATE.

*locale*<br/>
Язык и подязык, связанные с куском текста. Локт локал используется индексаторами документов для выполнения надлежащего нарушения текста. Если фрагмент не является ни текстовым шрифтом, ни типом значения с VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле игнорируется.

*cwcLenИсточник*<br/>
Длина символов исходного текста, из которого был получен текущий кусок. Нулевое значение означает соответствие символа по символу между исходным текстом и производным текстом. Ненулевое значение означает, что такой прямой корреспонденции не существует.

*cwcStartИсточник*<br/>
Смещение, из которого начинается исходный текст для производного куска.

*chunkBreakType*<br/>
Тип разрыва, отделяя предыдущий фрагмент от текущего фрагмента. Значения от CHUNK_BREAKTYPE перечисления.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplsetintvalue"></a><a name="setintvalue"></a>CMFCFilterChunkValueImpl::SetIntValue

Установите свойство ключом к Int.

```
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,
    int nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*Pkey*<br/>
Определяет ключ от свойств.

*nVal*<br/>
Определяет значение фрагмента для установки.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент свойство типа текста или свойство типа значения. Значения флага взяты из перечисления CHUNKSTATE.

*locale*<br/>
Язык и подязык, связанные с куском текста. Локт локал используется индексаторами документов для выполнения надлежащего нарушения текста. Если фрагмент не является ни текстовым шрифтом, ни типом значения с VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле игнорируется.

*cwcLenИсточник*<br/>
Длина символов исходного текста, из которого был получен текущий кусок. Нулевое значение означает соответствие символа по символу между исходным текстом и производным текстом. Ненулевое значение означает, что такой прямой корреспонденции не существует.

*cwcStartИсточник*<br/>
Смещение, из которого начинается исходный текст для производного куска.

*chunkBreakType*<br/>
Тип разрыва, отделяя предыдущий фрагмент от текущего фрагмента. Значения от CHUNK_BREAKTYPE перечисления.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplsetlongvalue"></a><a name="setlongvalue"></a>CMFCFilterChunkValueImpl::SetLongValue

Установите свойство ключом к LONG.

```
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,
    long lVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*Pkey*<br/>
Определяет ключ от свойств.

*lVal*<br/>
Определяет значение фрагмента для установки.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент свойство типа текста или свойство типа значения. Значения флага взяты из перечисления CHUNKSTATE.

*locale*<br/>
Язык и подязык, связанные с куском текста. Локт локал используется индексаторами документов для выполнения надлежащего нарушения текста. Если фрагмент не является ни текстовым шрифтом, ни типом значения с VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле игнорируется.

*cwcLenИсточник*<br/>
Длина символов исходного текста, из которого был получен текущий кусок. Нулевое значение означает соответствие символа по символу между исходным текстом и производным текстом. Ненулевое значение означает, что такой прямой корреспонденции не существует.

*cwcStartИсточник*<br/>
Смещение, из которого начинается исходный текст для производного куска.

*chunkBreakType*<br/>
Тип разрыва, отделяя предыдущий фрагмент от текущего фрагмента. Значения от CHUNK_BREAKTYPE перечисления.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplsetsystemtimevalue"></a><a name="setsystemtimevalue"></a>CMFCFilterChunkValueImpl::SetSystemTimeValue

Устанавливает свойство ключом к SystemTime.

```
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,
    const SYSTEMTIME& systemTime,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*Pkey*<br/>
Определяет ключ от свойств.

*Systemtime*<br/>
Определяет значение фрагмента для установки.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент свойство типа текста или свойство типа значения. Значения флага взяты из перечисления CHUNKSTATE.

*locale*<br/>
Язык и подязык, связанные с куском текста. Локт локал используется индексаторами документов для выполнения надлежащего нарушения текста. Если фрагмент не является ни текстовым шрифтом, ни типом значения с VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле игнорируется.

*cwcLenИсточник*<br/>
Длина символов исходного текста, из которого был получен текущий кусок. Нулевое значение означает соответствие символа по символу между исходным текстом и производным текстом. Ненулевое значение означает, что такой прямой корреспонденции не существует.

*cwcStartИсточник*<br/>
Смещение, из которого начинается исходный текст для производного куска.

*chunkBreakType*<br/>
Тип разрыва, отделяя предыдущий фрагмент от текущего фрагмента. Значения от CHUNK_BREAKTYPE перечисления.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="cmfcfilterchunkvalueimplsettextvalue"></a><a name="settextvalue"></a>CMFCFilterChunkValueImpl::SetTextValue

Устанавливает свойство ключом к строке Unicode.

```
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,
    LPCTSTR pszValue,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Параметры

*Pkey*<br/>
Определяет ключ от свойств.

*pszValue*<br/>
Определяет значение фрагмента для установки.

*chunkType*<br/>
Флаги указывают, содержит ли этот фрагмент свойство типа текста или свойство типа значения. Значения флага взяты из перечисления CHUNKSTATE.

*locale*<br/>
Язык и подязык, связанные с куском текста. Локт локал используется индексаторами документов для выполнения надлежащего нарушения текста. Если фрагмент не является ни текстовым шрифтом, ни типом значения с VT_LPWSTR, VT_LPSTR или VT_BSTR, это поле игнорируется.

*cwcLenИсточник*<br/>
Длина символов исходного текста, из которого был получен текущий кусок. Нулевое значение означает соответствие символа по символу между исходным текстом и производным текстом. Ненулевое значение означает, что такой прямой корреспонденции не существует.

*cwcStartИсточник*<br/>
Смещение, из которого начинается исходный текст для производного куска.

*chunkBreakType*<br/>
Тип разрыва, отделяя предыдущий фрагмент от текущего фрагмента. Значения от CHUNK_BREAKTYPE перечисления.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае код ошибки.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
