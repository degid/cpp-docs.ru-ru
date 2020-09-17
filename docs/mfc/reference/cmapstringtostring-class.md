---
title: Класс Кмапстрингтостринг
ms.date: 11/04/2016
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
- AFXCOLL/CMapStringToString::CMapStringToString
- AFXCOLL/CMapStringToString::GetCount
- AFXCOLL/CMapStringToString::GetHashTableSize
- AFXCOLL/CMapStringToString::GetNextAssoc
- AFXCOLL/CMapStringToString::GetSize
- AFXCOLL/CMapStringToString::GetStartPosition
- AFXCOLL/CMapStringToString::HashKey
- AFXCOLL/CMapStringToString::InitHashTable
- AFXCOLL/CMapStringToString::IsEmpty
- AFXCOLL/CMapStringToString::Lookup
- AFXCOLL/CMapStringToString::LookupKey
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToString::RemoveAll
- AFXCOLL/CMapStringToString::RemoveKey
- AFXCOLL/CMapStringToString::SetAt
helpviewer_keywords:
- CMapStringToString [MFC], CPair
- CMapStringToString [MFC], CMapStringToString
- CMapStringToString [MFC], GetCount
- CMapStringToString [MFC], GetHashTableSize
- CMapStringToString [MFC], GetNextAssoc
- CMapStringToString [MFC], GetSize
- CMapStringToString [MFC], GetStartPosition
- CMapStringToString [MFC], HashKey
- CMapStringToString [MFC], InitHashTable
- CMapStringToString [MFC], IsEmpty
- CMapStringToString [MFC], Lookup
- CMapStringToString [MFC], LookupKey
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToString [MFC], RemoveAll
- CMapStringToString [MFC], RemoveKey
- CMapStringToString [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
ms.openlocfilehash: 28422c26ba2ca77657bfcf166592d2bc69169891
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223009"
---
# <a name="cmapstringtostring-class"></a>Класс Кмапстрингтостринг

Поддерживает сопоставления объектов `CString` , зашифрованных объектами `CString` .

## <a name="syntax"></a>Синтаксис

```
class CMapStringToString : public CObject
```

## <a name="members"></a>Участники

Функции элементов `CMapStringToString` похожи на функции членов класса [кмапстрингтуб](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Когда указатель отображается в `CObject` качестве возвращаемого значения или параметра функции Output, замените указатель на **`char`** . Когда указатель отображается в `CObject` качестве параметра функции ввода, замените указатель на **`char`** .

`BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`

, например, преобразуется в

`BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`

### <a name="public-structures"></a>Открытые структуры

|Имя|Описание|
|----------|-----------------|
|[Кмапстрингтостринг:: Кпаир](#cpair)|Вложенная структура, содержащая значение ключа и значение связанного объекта String.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кмапстрингтостринг:: Кмапстрингтостринг](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кмапстрингтостринг:: NOCOUNT](../../mfc/reference/cmapstringtoob-class.md#getcount)|Возвращает число элементов в этой карте.|
|[Кмапстрингтостринг:: Жесаштаблесизе](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Определяет текущее количество элементов в хэш-таблице.|
|[Кмапстрингтостринг:: Жетнекстассок](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Возвращает следующий элемент для итерации.|
|[Кмапстрингтостринг:: DataSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Возвращает число элементов в этой карте.|
|[Кмапстрингтостринг:: Жетстартпоситион](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Возвращает расположение первого элемента.|
|[Кмапстрингтостринг:: Хашкэй](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Вычисляет хэш-значение указанного ключа.|
|[Кмапстрингтостринг:: Инисаштабле](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Инициализирует хэш-таблицу.|
|[Кмапстрингтостринг:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Проверяет условие на пустую карту (нет элементов).|
|[Кмапстрингтостринг:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Ищет указатель void на основе ключа указателя void. Значение указателя, а не сущность, на которое он указывает, используется для сравнения ключей.|
|[Кмапстрингтостринг:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|
|[Кмапстрингтостринг::P Жетфирстассок](#pgetfirstassoc)|Возвращает указатель на первую `CString` карту в сопоставлении.|
|[Кмапстрингтостринг::P Жетнекстассок](#pgetnextassoc)|Возвращает указатель на следующее `CString` для итерации.|
|[Кмапстрингтостринг::P Поиск](#plookup)|Возвращает указатель на объект `CString` , значение которого соответствует указанному значению.|
|[Кмапстрингтостринг:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Удаляет все элементы из этой схемы.|
|[Кмапстрингтостринг:: Ремовекэй](../../mfc/reference/cmapstringtoob-class.md#removekey)|Удаляет элемент, указанный ключом.|
|[Кмапстрингтостринг:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Вставляет элемент в карту; заменяет существующий элемент, если найден соответствующий ключ.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Кмапстрингтостринг::operator \[\]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в Map — подстановку оператора для `SetAt` .|

## <a name="remarks"></a>Примечания

`CMapStringToString` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Каждый элемент сериализуется в свою очередь, если схема хранится в архиве с перегруженным **<<** оператором вставки () или с `Serialize` функцией-членом.

Если требуется дамп отдельных `CString` -  `CString` элементов, необходимо установить глубину контекста дампа в 1 или более.

При `CMapStringToString` удалении объекта или удалении его элементов `CString` объекты удаляются соответствующим образом.

Дополнительные сведения о см `CMapStringToString` . в статье [коллекции](../../mfc/collections.md)статей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToString`

## <a name="requirements"></a>Требования

**Заголовок:** афксколл.h

## <a name="cmapstringtostringcpair"></a><a name="cpair"></a>Кмапстрингтостринг:: Кпаир

Содержит значение ключа и значение связанного строкового объекта.

### <a name="remarks"></a>Примечания

Это вложенная структура в классе [кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md).

Структура состоит из двух полей:

- `key`Фактическое значение типа ключа.

- `value`Значение связанного объекта.

Он используется для хранения возвращаемых значений из [кмапстрингтостринг::P Lookup](#plookup), [Кмапстрингтостринг::P жетфирстассок](#pgetfirstassoc)и [кмапстрингтостринг::P жетнекстассок](#pgetnextassoc).

### <a name="example"></a>Пример

  Пример использования см. в примере для [кмапстрингтостринг::P Lookup](#plookup).

## <a name="cmapstringtostringpgetfirstassoc"></a><a name="pgetfirstassoc"></a>Кмапстрингтостринг::P Жетфирстассок

Возвращает первую запись объекта Map.

```
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на первую запись в сопоставлении; см. раздел [кмапстрингтостринг:: кпаир](#cpair). Если схема пуста, значение равно NULL.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы вернуть указатель на первый элемент в объекте Map.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]

## <a name="cmapstringtostringpgetnextassoc"></a><a name="pgetnextassoc"></a>Кмапстрингтостринг::P Жетнекстассок

Извлекает элемент Map, на который указывает *пассокрек*.

```
const CPair *PGetNextAssoc(const CPair* pAssoc) const;

CPair *PGetNextAssoc(const CPair* pAssoc);
```

### <a name="parameters"></a>Параметры

*пассок*<br/>
Указывает на запись Map, возвращенную предыдущим вызовом [пжетнекстассок](#pgetnextassoc) или [пжетфирстассок](#pgetfirstassoc) .

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующую запись в сопоставлении; см. раздел [кмапстрингтостринг:: кпаир](#cpair). Если элемент является последним в сопоставлении, значение равно NULL.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы выполнить итерацию всех элементов в сопоставлении. Получите первый элемент, вызвав метод `PGetFirstAssoc` , а затем выполните итерацию по карте с последовательными вызовами `PGetNextAssoc` .

### <a name="example"></a>Пример

  См. пример для [кмапстрингтостринг::P жетфирстассок](#pgetfirstassoc).

## <a name="cmapstringtostringplookup"></a><a name="plookup"></a>Кмапстрингтостринг::P Поиск

Выполняет поиск значения, сопоставленного с заданным ключом.

```
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Указатель на ключ для искомого элемента.

### <a name="return-value"></a>Возвращаемое значение

Указатель на указанный ключ.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы найти элемент Map с ключом, который точно соответствует заданному ключу.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]

## <a name="see-also"></a>См. также раздел

[Пример СОБРАНий MFC](../../overview/visual-cpp-samples.md)<br/>
[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)
