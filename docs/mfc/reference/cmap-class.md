---
title: Класс CMap
ms.date: 11/04/2016
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
ms.openlocfilehash: fbb34d4db41ef11cd01a6a8a7f20cafa0e737268
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749076"
---
# <a name="cmap-class"></a>Класс CMap

Класс коллекции словарей, который сопоставляет уникальные ключи значениям.

## <a name="syntax"></a>Синтаксис

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>Параметры

*Ключ*<br/>
Класс объекта, используемого в качестве ключа к карте.

*ARG_KEY*<br/>
Тип данных, используемый для аргументов *KEY;* обычно ссылка на *KEY*.

*Значение*<br/>
Класс объекта, хранящегося на карте.

*ARG_VALUE*<br/>
Тип данных, используемый для аргументов *VALUE;* обычно ссылка на *VALUE*.

## <a name="members"></a>Участники

### <a name="public-structures"></a>Общественные структуры

|Имя|Описание|
|----------|-----------------|
|[CMap::CPair](#cpair)|Вложенная структура, содержащая ключевое значение и значение связанного объекта.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMap::CMap](#cmap)|Строит коллекцию, в которой отобирают ключи к значениям.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMap::GetCount](#getcount)|Возвращает количество элементов на этой карте.|
|[CMap::GetHashTableSize](#gethashtablesize)|Возвращает количество элементов в таблице хэша.|
|[CMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для итерации.|
|[CMap::GetSize](#getsize)|Возвращает количество элементов на этой карте.|
|[CMap::GetStartPosition](#getstartposition)|Возвращает положение первого элемента.|
|[CMap::InitHashTable](#inithashtable)|Инициализирует хэш-таблицу и определяет его размер.|
|[CMap::IsEmpty](#isempty)|Тесты на состояние пустой карты (без элементов).|
|[CMap::Lookup](#lookup)|Ищет значение, отображено к заданного ключу.|
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|Возвращает указатель на первый элемент.|
|[CMap::PGetNextAssoc](#pgetnextassoc)|Получает указатель на следующий элемент для итерации.|
|[CMap::PLookup](#plookup)|Возвращает указатель на ключ, значение которого соответствует указанному значению.|
|[CMap::RemoveAll](#removeall)|Удаляет все элементы с этой карты.|
|[CMap::RemoveKey](#removekey)|Удаляет элемент, указанный ключом.|
|[CMap::SetAt](#setat)|Вставляет элемент на карту; заменяет существующий элемент при обнаружении соответствующего ключа.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CMap:оператор \[\]](#operator_at)|Вставляет элемент в карту - `SetAt`замена оператора для .|

## <a name="remarks"></a>Примечания

После того как вы вставили пару ключей (элемент) в карту, вы можете эффективно получить или удалить пару, используя ключ, чтобы получить к ней доступ. Вы также можете итерировать все элементы на карте.

Для альтернативного доступа к записям используется переменная типа POSITION. Вы можете использовать POSITION, чтобы "запомнить" запись и итерировать через карту. Вы можете подумать, что эта итерация является последовательной по ключевой стоимости; Нет. Последовательность извлеченных элементов неопределенным.

Некоторые функции членов этого класса вызывают функции глобального помощника, `CMap` которые должны быть настроены для большинства видов использования класса. Смотрите [раздел "Помощники класса коллекций"](../../mfc/reference/collection-class-helpers.md) в разделе Макрос и Глобалс **справочника MFC.**

`CMap`переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) для поддержки сериализации и демпинга его элементов. Если карта хранится в `Serialize`архиве с использованием, каждый элемент карты сериализируется по очереди. Выполнение функции `SerializeElements` помощника по умолчанию делает bitwise запись. Для получения информации о сериализации элементов сбора указателей, полученных из `CObject` или других типов, определенных пользователем, см. [How to: Make a Type-Safe Collection](../../mfc/how-to-make-a-type-safe-collection.md)

Если вам нужна диагностическая дампа отдельных элементов на карте (ключи и значения), необходимо установить глубину контекста дампа до 1 или более.

Когда `CMap` объект удаляется или когда его элементы удаляются, клавиши и значения удаляются.

Производные класса карты аналогичны производным от списка. Смотрите статью [Коллекции](../../mfc/collections.md) для иллюстрации произвобления класса специального списка.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

## <a name="cmapcmap"></a><a name="cmap"></a>CMap::CMap

Строит пустую карту.

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Определяет детализацию распределения памяти для расширения карты.

### <a name="remarks"></a>Примечания

По мере роста карты память распределяется в единицах записей *nBlockSize.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

## <a name="cmapcpair"></a><a name="cpair"></a>CMap::CPair

Содержит ключевое значение и значение связанного объекта.

### <a name="remarks"></a>Примечания

Это вложенная структура в классе [CMap.](../../mfc/reference/cmap-class.md)

Структура состоит из двух полей:

- `key`Фактическое значение ключевого типа.

- `value`Значение связанного объекта.

Он используется для хранения значений возврата от [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), и [CMap::PGetNextAssoc](#pgetnextassoc).

### <a name="example"></a>Пример

Для примера использования с [:Pм.](#plookup)

## <a name="cmapgetcount"></a><a name="getcount"></a>CMap::GetCount

Извлекает количество элементов на карте.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов.

### <a name="example"></a>Пример

Смотрите пример [CMap::Lookup](#lookup).

## <a name="cmapgethashtablesize"></a><a name="gethashtablesize"></a>CMap::GetHashTableSize

Определяет количество элементов в таблице хэша для карты.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в хэш-таблице.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

## <a name="cmapgetnextassoc"></a><a name="getnextassoc"></a>CMap::GetNextAssoc

Извлекает элемент карты `rNextPosition`на, `rNextPosition` затем обновляется для обозначения следующего элемента на карте.

```cpp
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Параметры

*rNextPosition*<br/>
Уотка указывает ссылку на значение POSITION, возвращенное предыдущим `GetNextAssoc` или `GetStartPosition` коллом.

*Ключ*<br/>
Параметры шаблона, определяющие тип ключа карты.

*rKey*<br/>
Определяет возвращенный ключ извлеченного элемента.

*Значение*<br/>
Параметры шаблона, определяющие тип значения карты.

*Rvalue*<br/>
Определяет возвращенное значение извлеченного элемента.

### <a name="remarks"></a>Примечания

Эта функция наиболее полезна для итерации всех элементов на карте. Обратите внимание, что последовательность положения не обязательно совпадает с последовательностью значения ключа.

Если извлеченный элемент является последним на карте, то новое значение *rNextPosition* устанавливается на NULL.

### <a name="example"></a>Пример

Смотрите пример [CMap::SetAt](#setat).

## <a name="cmapgetsize"></a><a name="getsize"></a>CMap::GetSize

Возвращает количество элементов карты.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов на карте.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить количество элементов на карте.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapgetstartposition"></a><a name="getstartposition"></a>CMap::GetStartPosition

Начинаети итерацию карты, вернув значение POSITION, `GetNextAssoc` которое может быть передано вызову.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, указывающее исходное положение для итерации карты; или NULL, если карта пуста.

### <a name="remarks"></a>Примечания

Последовательность итерации не предсказуема; поэтому "первый элемент на карте" не имеет особого значения.

### <a name="example"></a>Пример

Смотрите пример [CMap::SetAt](#setat).

## <a name="cmapinithashtable"></a><a name="inithashtable"></a>CMap::InitHashTable

Инициализирует хэш-таблицу.

```cpp
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>Параметры

*hashSize*<br/>
Количество записей в таблице хэша.

*bAllocNow*<br/>
Если TRUE, выделяет хэш-таблицу после инициализации; в противном случае таблица выделяется при необходимости.

### <a name="remarks"></a>Примечания

Для наилучшей производительности размер таблицы хэша должен быть простой номер. Чтобы свести к минимуму коллизии, размер должен быть примерно на 20 процентов больше, чем самый большой ожидаемый набор данных.

### <a name="example"></a>Пример

Смотрите пример [CMap::Lookup](#lookup).

## <a name="cmapisempty"></a><a name="isempty"></a>CMap::IsEmpty

Определяет, пуста ли карта.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если эта карта не содержит элементов; в противном случае 0.

### <a name="example"></a>Пример

Смотрите пример [для CMap::RemoveAll](#removeall).

## <a name="cmaplookup"></a><a name="lookup"></a>CMap::Lookup

Ищет значение, отображено к заданного ключу.

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Параметры

*ARG_KEY*<br/>
Параметры шаблона, определяющие тип *значения ключа.*

*key*<br/>
Определяет ключ, который определяет элемент, который следует изыскнуть.

*Значение*<br/>
Определяет тип значения, поднимая иссмотреть.

*Rvalue*<br/>
Получает значение "загнан".

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент был найден; в противном случае 0.

### <a name="remarks"></a>Примечания

`Lookup`использует алгоритм хэширования, чтобы быстро найти элемент карты с ключом, который точно соответствует данному ключу.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapoperator--"></a><a name="operator_at"></a>CMap::оператор

Удобная замена `SetAt` функции члена.

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>Параметры

*Значение*<br/>
Параметры шаблона, определяющие тип значения карты.

*ARG_KEY*<br/>
Параметры шаблона, определяющие тип значения ключа.

*key*<br/>
Ключ, используемый для получения значения с карты.

### <a name="remarks"></a>Примечания

Таким образом, он может быть использован только на левой стороне оператора назначения (l-значение). Если нет элемента карты с указанным ключом, создается новый элемент.

Нет "правой стороны" (r-value) эквивалентного этому оператору, поскольку существует вероятность того, что ключ может не быть найден на карте. Используйте `Lookup` функцию члена для поиска элементов.

### <a name="example"></a>Пример

Смотрите пример [CMap::Lookup](#lookup).

## <a name="cmappgetfirstassoc"></a><a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc

Возвращает первую запись объекта карты.

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на первую запись на карте; [см. CMap::CPair](#cpair). Если карта не содержит записей, значение NULL.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы вернуть указатель первого элемента объекта карты.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

## <a name="cmappgetnextassoc"></a><a name="pgetnextassoc"></a>CMap::PGetNextAssoc

Извлекает элемент карты, на который указывает *pAssocRec*.

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>Параметры

*pAssocRet*<br/>
Очки на запись карты, возвращенную предыдущим вызовом [PGetNextAssoc](#pgetnextassoc) или [CMap::PGetFirstAssoc.](#pgetfirstassoc)

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующую запись на карте; [см. CMap::CPair](#cpair). Если элемент является последним на карте, значение NULL.

### <a name="remarks"></a>Примечания

Назовите этот метод итератом через все элементы карты. Извлеките первый элемент `PGetFirstAssoc` с вызовом, а затем итерировать через карту с последовательными вызовами. `PGetNextAssoc`

### <a name="example"></a>Пример

Смотрите пример [CMap::PGetFirstAssoc](#pgetfirstassoc).

## <a name="cmapplookup"></a><a name="plookup"></a>CMap::PLookup

Находит значение, отображеное на заданном ключе.

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ для элемента, который будет искать.

### <a name="return-value"></a>Возвращаемое значение

Указатель на ключевую структуру; [см. CMap::CPair](#cpair). Если совпадение `CMap::PLookup` не найдено, возвращает NULL.

### <a name="remarks"></a>Примечания

Вызовите этот метод для поиска элемента карты с ключом, который точно соответствует заданного ключа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

## <a name="cmapremoveall"></a><a name="removeall"></a>CMap::RemoveAll

Удаляет все значения с этой карты, позвонив в функцию `DestructElements`глобального помощника.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Функция работает правильно, если карта уже пуста.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

## <a name="cmapremovekey"></a><a name="removekey"></a>CMap::RemoveKey

Смотрит запись карты, соответствующую предоставленного ключу; затем, если ключ найден, удаляет запись.

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>Параметры

*ARG_KEY*<br/>
Параметры шаблона, определяющие тип ключа.

*key*<br/>
Ключ для удаления элемента.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если запись была найдена и успешно удалена; в противном случае 0.

### <a name="remarks"></a>Примечания

Функция `DestructElements` помощника используется для удаления записи.

### <a name="example"></a>Пример

Смотрите пример [CMap::SetAt](#setat).

## <a name="cmapsetat"></a><a name="setat"></a>CMap::SetAt

Основное средство для вставки элемента в карту.

```cpp
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>Параметры

*ARG_KEY*<br/>
Параметры шаблона, определяющие тип *ключевого* параметра.

*key*<br/>
Определяет ключ нового элемента.

*ARG_VALUE*<br/>
Параметры шаблона, определяющие тип параметра *newValue.*

*newValue*<br/>
Определяет значение нового элемента.

### <a name="remarks"></a>Примечания

Во-первых, ключ посмотрел вверх. Если ключ найден, то соответствующее значение изменяется; в противном случае создается новая пара ключ-значение.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец COLLECT](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
