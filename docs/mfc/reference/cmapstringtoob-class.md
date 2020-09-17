---
title: Класс CMapStringToOb
ms.date: 11/04/2016
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
ms.openlocfilehash: 6520d1c38701647ae51450b9b9800a7cd2701b7a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754591"
---
# <a name="cmapstringtoob-class"></a>Класс CMapStringToOb

Класс коллекции словаря, который сопоставляет уникальные объекты `CString` с указателями `CObject` .

## <a name="syntax"></a>Синтаксис

```
class CMapStringToOb : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Cmapstringtoob:Cmapstringtoob](#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Cmapstringtoob:GetCount](#getcount)|Возвращает количество элементов на этой карте.|
|[CMapStringToob::GethashTableSize](#gethashtablesize)|Определяет текущее количество элементов в таблице хэша.|
|[CmapstringToob::GetNextAssoc](#getnextassoc)|Получает следующий элемент для итерации.|
|[Cmapstringtoob:GetSize](#getsize)|Возвращает количество элементов на этой карте.|
|[Cmapstringtoob:GetStartposition](#getstartposition)|Возвращает положение первого элемента.|
|[CMapStringToob::HashKey](#hashkey)|Рассчитывает хэш-значение указанного ключа.|
|[CMapStringToob::InithashTable](#inithashtable)|Инициализирует хэш-таблицу.|
|[Cmapstringtoob::Пустой](#isempty)|Тесты на состояние пустой карты (без элементов).|
|[CMapstringToob::Lookup](#lookup)|Ищет пустоту указатель на основе ключа указателя пустоты. Значение указателя, а не сущность, на которое он указывает, используется для сравнения ключей.|
|[CMapstringToob:LookupKey](#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|
|[Cmapstringtoob::Removeall](#removeall)|Удаляет все элементы с этой карты.|
|[Cmapstringtoob::RemoveKey](#removekey)|Удаляет элемент, указанный ключом.|
|[Cmapstringtoob::Setat](#setat)|Вставляет элемент на карту; заменяет существующий элемент при обнаружении соответствующего ключа.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Cmapstringtoob:оператор \[\]](#operator_at)|Вставляет элемент в карту - `SetAt`замена оператора для .|

## <a name="remarks"></a>Примечания

После того как `CString` -  `CObject*` вы вставили пару (элемент) в карту, вы можете эффективно `CString` извлечь или удалить пару с помощью строки или значения в качестве ключа. Вы также можете итерировать все элементы на карте.

Переменная типа POSITION используется для альтернативного доступа к входу во всех вариациях карты. Вы можете использовать POSITION, чтобы "запомнить" запись и итерировать через карту. Вы можете подумать, что эта итерация является последовательной по ключевой стоимости; Нет. Последовательность извлеченных элементов неопределенным.

`CMapStringToOb` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Каждый элемент сериализуется по очереди, если карта хранится в архиве, либо с перегруженной вставкой () **<<** оператором или с функцией `Serialize` члена.

Если вам нужна диагностическая дампа отдельных `CString` элементов `CObject` на карте (значение и содержимое), необходимо установить глубину контекста дампа до 1 или более.

Когда `CMapStringToOb` объект удаляется или когда его элементы `CString` удаляются, объекты и указатели `CObject` удаляются. Объекты, на `CObject` которые ссылаются указатели, не уничтожаются.

Производные класса карты аналогичны производным от списка. Смотрите статью [Коллекции](../../mfc/collections.md) для иллюстрации произвобления класса специального списка.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToOb`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

## <a name="cmapstringtoobcmapstringtoob"></a><a name="cmapstringtoob"></a>Cmapstringtoob:Cmapstringtoob

Строит пустую `CString` `CObject*` карту.

```
CMapStringToOb(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Определяет детализацию распределения памяти для расширения карты.

### <a name="remarks"></a>Примечания

По мере роста карты память распределяется в единицах записей *nBlockSize.*

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb:: CMapStringToOb`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr (INT_PTR** `nBlockSize` **No 10);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapptrToWord (INT_PTR** `nBlockSize` **No 10);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapstringToPtr (INT_PTR** `nBlockSize` **No 10);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapstringTostring (INT_PTR** `nBlockSize` **No 10);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CmapwordToob (INT_PTR** `nBlockSize` **No 10);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr (INT_PTR** `nBlockSize` **No 10);**|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

## <a name="cmapstringtoobgetcount"></a><a name="getcount"></a>Cmapstringtoob:GetCount

Определяет, сколько элементов на карте.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов на этой карте.

### <a name="remarks"></a>Примечания

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::GetCount`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetCount () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetCount () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetCount () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetCount () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetCount () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]

## <a name="cmapstringtoobgethashtablesize"></a><a name="gethashtablesize"></a>CMapStringToob::GethashTableSize

Определяет текущее количество элементов в таблице хэша.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов в таблице хэша.

### <a name="remarks"></a>Примечания

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::GetHashTableSize`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT GetHashTableSize ( ) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT GetHashTableSize ( ) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT GetHashTableSize ( ) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT GetHashTableSize ( ) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT GetHashTableSize ( ) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT GetHashTableSize ( ) const;**|

## <a name="cmapstringtoobgetnextassoc"></a><a name="getnextassoc"></a>CmapstringToob::GetNextAssoc

Извлекает элемент карты на *rNextPosition,* затем обновляет *rNextPosition* для обозначения следующего элемента на карте.

```cpp
void GetNextAssoc(
    POSITION& rNextPosition,
    CString& rKey,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Параметры

*rNextPosition*<br/>
Уотка указывает ссылку на значение POSITION, возвращенное предыдущим `GetNextAssoc` или `GetStartPosition` коллом.

*rKey*<br/>
Опознавательный возвращенный ключ извлеченного элемента (строки).

*Rvalue*<br/>
Определяет возвращенное значение извлеченного элемента `CObject` (указатель). Подробнее об этом параметре читайте в комментарии.

### <a name="remarks"></a>Примечания

Эта функция наиболее полезна для итерации всех элементов на карте. Обратите внимание, что последовательность положения не обязательно совпадает с последовательностью значения ключа.

Если извлеченный элемент является последним на карте, то новое значение *rNextPosition* устанавливается на NULL.

Для параметра *rValue* обязательно отбросьте свой тип объекта **в\*CObject,** что и требуется компилятору, как показано в следующем примере:

[!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]

Это не относится `GetNextAssoc` к картам, основанным на шаблонах.

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::GetNextAssoc`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**пустота GetNextAssoc (POSITION&** *rNextPosition* **, пустота\* ** *rKey* **,\* пустота** *rValue* **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**пустота GetNextAssoc (POSITION&** *rNextPosition* **, пустота\* ** *rKey* **, WORD&** *rValue* **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**пустота GetNextAssoc (POSITION&** *rNextPosition* **, CString&** *rKey* **, пустота\* ** *rValue* **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**пустота GetNextAssoc (POSITION&** *rNextPosition* **, CString&** *rKey* **, CString&** *rValue* **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void GetNextAssoc ( POSITION&** *rNextPosition* **, WORD&** *rKey* **, CObject\* ** *rValue* **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**пустота GetNextAssoc (POSITION&** *rNextPosition* **, WORD&** *rKey* **, void\* ** *rValue* **) const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]

Результаты этой программы следующие:

```Output
Lisa : a CAge at $4724 11
Marge : a CAge at $47A8 35
Homer : a CAge at $4766 36
Bart : a CAge at $45D4 13
```

## <a name="cmapstringtoobgetsize"></a><a name="getsize"></a>Cmapstringtoob:GetSize

Возвращает количество элементов карты.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов на карте.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить количество элементов на карте.

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::GetSize`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetSize() Const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetSize() Const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetSize() Const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetSize() Const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetSize() Const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetSize() Const;**|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]

## <a name="cmapstringtoobgetstartposition"></a><a name="getstartposition"></a>Cmapstringtoob:GetStartposition

Начинаети итерацию карты, вернув значение POSITION, `GetNextAssoc` которое может быть передано вызову.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, указывающее исходное положение для итерации карты; или NULL, если карта пуста.

### <a name="remarks"></a>Примечания

Последовательность итерации не предсказуема; поэтому "первый элемент на карте" не имеет особого значения.

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::GetStartPosition`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**POSITION GetStartPosition( ) конст;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**POSITION GetStartPosition( ) конст;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**POSITION GetStartPosition( ) конст;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**POSITION GetStartPosition( ) конст;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**POSITION GetStartPosition( ) конст;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**POSITION GetStartPosition( ) конст;**|

### <a name="example"></a>Пример

Смотрите пример [CMapStringToOb::GetNextAssoc](#getnextassoc).

## <a name="cmapstringtoobhashkey"></a><a name="hashkey"></a>CMapStringToob::HashKey

Рассчитывает хэш-значение указанного ключа.

```
UINT HashKey(LPCTSTR key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, стоимость хэша которого должна быть рассчитана.

### <a name="return-value"></a>Возвращаемое значение

Значение хэша ключа

### <a name="remarks"></a>Примечания

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::HashKey`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey ( пустота** <strong>\*</strong> `key` **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey ( пустота** <strong>\*</strong> `key` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT HashKey ( LPCTSTR** `key` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT HashKey ( LPCTSTR** `key` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT HashKey ( WORD** `key` **) конст;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT HashKey ( WORD** `key` **) конст;**|

## <a name="cmapstringtoobinithashtable"></a><a name="inithashtable"></a>CMapStringToob::InithashTable

Инициализирует хэш-таблицу.

```cpp
void InitHashTable(
    UINT hashSize,
    BOOL bAllocNow = TRUE);
```

### <a name="parameters"></a>Параметры

*hashSize*<br/>
Количество записей в таблице хэша.

*bAllocNow*<br/>
Если TRUE, выделяет хэш-таблицу после инициализации; в противном случае таблица выделяется при необходимости.

### <a name="remarks"></a>Примечания

Для наилучшей производительности размер таблицы хэша должен быть простой номер. Чтобы свести к минимуму коллизии, размер должен быть примерно на 20 процентов больше, чем самый большой ожидаемый набор данных.

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::InitHashTable`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**недействительным InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **и TRUE );**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**недействительным InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **и TRUE );**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**недействительным InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **и TRUE );**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**недействительным InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **и TRUE );**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**недействительным InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **и TRUE );**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**недействительным InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **и TRUE );**|

## <a name="cmapstringtoobisempty"></a><a name="isempty"></a>Cmapstringtoob::Пустой

Определяет, пуста ли карта.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если эта карта не содержит элементов; в противном случае 0.

### <a name="example"></a>Пример

Смотрите пример [для RemoveAll](#removeall).

### <a name="remarks"></a>Примечания

В следующей таблице показаны другие функции членов, похожие на **CMapStringToOb:: IsEmpty**.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL IsEmpty() Const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL IsEmpty() Const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL IsEmpty() Const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL IsEmpty() Const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL IsEmpty() Const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL IsEmpty() Const;**|

## <a name="cmapstringtooblookup"></a><a name="lookup"></a>CMapstringToob::Lookup

Возвращает `CObject` указатель на `CString` основе значения.

```
BOOL Lookup(
    LPCTSTR key,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Определяет клавишу строки, которая определяет элемент, который следует изыскнуть.

*Rvalue*<br/>
Определяет возвращенное значение из иссмотретьэлемента.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент был найден; в противном случае 0.

### <a name="remarks"></a>Примечания

`Lookup`использует алгоритм хэширования, чтобы быстро найти элемент карты `CString` с ключом, который точно соответствует (значение).

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::LookUp`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL Lookup (пустота,** <strong>\*</strong> `key` **\* пустота)** `rValue` **const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL Lookup (пустота** <strong>\*</strong> `key` **, WORD&)** `rValue` **const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL Lookup (LPCTSTR** `key` **,\* недействительным)** `rValue` **const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL Lookup (LPCTSTR** `key` **, CString&** `rValue` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL Lookup ( WORD** `key` **, CObject\* ** `rValue` ) **const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL Lookup ( WORD** `key` **, пустота\* ** `rValue` ) **const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]

## <a name="cmapstringtooblookupkey"></a><a name="lookupkey"></a>CMapstringToob:LookupKey

Возвращает ссылку на ключ, связанный с указанным значением ключа.

```
BOOL LookupKey(
    LPCTSTR key,
    LPCTSTR& rKey) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Определяет клавишу строки, которая определяет элемент, который следует изыскнуть.

*rKey*<br/>
Ссылка на связанный ключ.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если ключ был найден; в противном случае 0.

### <a name="remarks"></a>Примечания

Использование ссылки на ключ небезопасно, если используется после удаления связанного элемента с карты или после того, как карта была уничтожена.

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb:: LookupKey`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL LookupKey (LPCTSTR,** `key` **LPCTSTR&** `rKey` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL LookupKey (LPCTSTR,** `key` **LPCTSTR&** `rKey` **) const;**|

## <a name="cmapstringtooboperator--"></a><a name="operator_at"></a>Cmapstringtoob::оператор

Удобная замена `SetAt` функции члена.

```
CObject*& operator[ ](lpctstr key);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на указатель `CObject` на объект; или NULL, если карта пуста или *ключ* находится вне зоны досягаемости.

### <a name="remarks"></a>Примечания

Таким образом, он может быть использован только на левой стороне оператора назначения (l-значение). Если нет элемента карты с указанным ключом, создается новый элемент.

Нет "правой стороны" (r-value) эквивалентного этому оператору, поскольку существует вероятность того, что ключ может не быть найден на карте. Используйте `Lookup` функцию члена для поиска элементов.

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::operator []`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|<strong>пустота\* \[& оператора \* (пустота</strong> `key` ** \);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**& оператор\[WORD (пустой** <strong>\*</strong> `key` ** \);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**пустота\* \[& оператора (lpctstr** `key` ** \);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Оператор cString\[& (lpctstr** `key` ** \);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*&\[оператора (слово** `key` ** \);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**пустота\* \[& оператора (слово** `key` ** \);**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]

Результаты этой программы следующие:

```Output
Operator [] example: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $4A02 11
[Bart] = a CAge at $497E 13
```

## <a name="cmapstringtoobremoveall"></a><a name="removeall"></a>Cmapstringtoob::Removeall

Удаляет все элементы с этой карты `CString` и уничтожает ключевые объекты.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Объекты, `CObject` на которые ссылается каждый ключ, не уничтожаются. Функция `RemoveAll` может привести к утечке памяти, `CObject` если вы не гарантируете, что упомянутые объекты будут уничтожены.

Функция работает правильно, если карта уже пуста.

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::RemoveAll`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**пустота RemoveAll();**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**пустота RemoveAll();**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**пустота RemoveAll();**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**пустота RemoveAll();**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**пустота RemoveAll();**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**пустота RemoveAll();**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]

## <a name="cmapstringtoobremovekey"></a><a name="removekey"></a>Cmapstringtoob::RemoveKey

Смотрит запись карты, соответствующую предоставленного ключу; затем, если ключ найден, удаляет запись.

```
BOOL RemoveKey(LPCTSTR key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Опознавательный состав строки, используемой для поиска карты.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если запись была найдена и успешно удалена; в противном случае 0.

### <a name="remarks"></a>Примечания

Это может привести к `CObject` утечке памяти, если объект не будет удален в другом месте.

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::RemoveKey`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL RemoveKey (пустота);** <strong>\*</strong> `key` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL RemoveKey (пустота);** <strong>\*</strong> `key` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL RemoveKey (LPCTSTR);** `key` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL RemoveKey (LPCTSTR);** `key` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL RemoveKey** `key` **(WORD);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL RemoveKey** `key` **(WORD);**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]

Результаты этой программы следующие:

```Output
RemoveKey example: A CMapStringToOb with 3 elements
[Marge] = a CAge at $49A0 35
[Homer] = a CAge at $495E 36
[Bart] = a CAge at $4634 13
```

## <a name="cmapstringtoobsetat"></a><a name="setat"></a>Cmapstringtoob::Setat

Основное средство для вставки элемента в карту.

```cpp
void SetAt(
    LPCTSTR key,
    CObject* newValue);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Определяет строку, которая является ключом нового элемента.

*newValue*<br/>
Определяет указатель, `CObject` который является значением нового элемента.

### <a name="remarks"></a>Примечания

Во-первых, ключ посмотрел вверх. Если ключ найден, то соответствующее значение изменяется; в противном случае создается новый элемент ключевой ценности.

В следующей таблице показаны другие функции участника, которые аналогичны `CMapStringToOb::SetAt`.

|Class|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**пустота SetAt (пустота,** <strong>\*</strong> `key` **пустота);** <strong>\*</strong> `newValue` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**пустота SetAt (пустота** <strong>\*</strong> `key` , **WORD);** **, WORD** `newValue`|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**недействительным SetAt (LPCTSTR** `key` , **недействительным);** **, void** <strong>\*</strong> `newValue`|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**апотизм SetAt (LPCTSTR** `key` **, LPCTSTR);** `newValue` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**пустота SetAt (WORD** `key` **, CObject** <strong>\*</strong> `newValue` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**пустота SetAt (WORD** `key` **, пустота);** <strong>\*</strong> `newValue` **);**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]

Результаты этой программы следующие:

```Output
before Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $493C 11
[Bart] = a CAge at $4654 13
after Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $49C0 12
[Bart] = a CAge at $4654 13
```

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[Класс CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)<br/>
[Класс CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)<br/>
[Класс CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)<br/>
[Класс CmapWordToob](../../mfc/reference/cmapwordtoob-class.md)<br/>
[Класс CmapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)
