---
title: Класс CSimpleMap
ms.date: 11/04/2016
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
ms.openlocfilehash: eed41c2250728d257b6d303e79c3afd36a543dbb
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747640"
---
# <a name="csimplemap-class"></a>Класс CSimpleMap

Этот класс обеспечивает поддержку простого массива отображения.

## <a name="syntax"></a>Синтаксис

```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>
class CSimpleMap
```

#### <a name="parameters"></a>Параметры

*Tkey*<br/>
Тип ключевого элемента.

*TVal*<br/>
Тип элемента значения.

*TEqual*<br/>
Объект черты, определяющий тест на `T`равенство для элементов типа.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CSimpleMap::_ArrayElementType](#_arrayelementtype)|Тип для типа значения.|
|[CSimpleMap::_ArrayKeyType](#_arraykeytype)|Тип для ключевого типа.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSimpleMap::CSimpleMap](#csimplemap)|Конструктор.|
|[CSimpleMap::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleMap::Добавить](#add)|Добавляет ключ и связанное с ним значение в массив карты.|
|[CSimpleMap::FindKey](#findkey)|Находит определенный ключ.|
|[CSimpleMap::FindVal](#findval)|Находит определенное значение.|
|[CSimpleMap:GetKeyAt](#getkeyat)|Извлекает указанный ключ.|
|[CSimpleMap::GetSize](#getsize)|Возвращает количество записей в массиве отображения.|
|[CSimpleMap:GetValueat](#getvalueat)|Извлекает указанное значение.|
|[CSimpleMap::Поиск](#lookup)|Возвращает значение, связанное с данным ключом.|
|[CSimpleMap::Удалить](#remove)|Удаляет значение ключа и соответствия.|
|[CSimpleMap::RemoveAll](#removeall)|Удаляет все ключи и значения.|
|[CSimpleMap::RemoveAt](#removeat)|Удаляет определенный ключ и соответствующее значение.|
|[CSimpleMap::ReverseLookup](#reverselookup)|Возвращает ключ, связанный с данным значением.|
|[CSimpleMap::SetAt](#setat)|Устанавливает значение, связанное с данным ключом.|
|[CSimpleMap::SetatIndex](#setatindex)|Устанавливает конкретный ключ и значение.|

## <a name="remarks"></a>Примечания

`CSimpleMap`обеспечивает поддержку простого массива отображения любого данного типа, `T`управления неупорядоченным набором ключевых элементов и связанных с ними значений.

Параметр `TEqual` обеспечивает средство определения функции равенства для `T`двух элементов типа. Создавая класс, похожий на [CSimpleMapEqualHelper,](../../atl/reference/csimplemapequalhelper-class.md)можно изменить поведение теста на равенство для любого данного массива. Например, при работе с массивом указателей может быть полезно определить равенство как в зависимости от значений, на которые ссылаются указатели. Реализация по умолчанию использует **оператора .()**.

И `CSimpleMap` [CSimpleArray](../../atl/reference/csimplearray-class.md) предусмотрены для совместимости с предыдущими релизами ATL, а более полные и эффективные реализации коллекции обеспечиваются [CAtlArray](../../atl/reference/catlarray-class.md) и [CAtlMap.](../../atl/reference/catlmap-class.md)

В отличие от других картвизаток в ATL и MFC, этот класс реализован с простым массивом, и поиск поиска требует линейного поиска. `CAtlMap`следует использовать, когда массив содержит большое количество элементов.

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

## <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]

## <a name="csimplemapadd"></a><a name="add"></a>CSimpleMap::Добавить

Добавляет ключ и связанное с ним значение в массив карты.

```
BOOL Add(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ.

*Валь*<br/>
Связанное значение.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если ключ и значение были успешно добавлены, FALSE в противном случае.

### <a name="remarks"></a>Примечания

Каждая добавленная пара ключей и добавленной стоимости приводит к освобождению и перераспределению памяти массива отображения, чтобы гарантировать, что данные для каждого из них всегда хранятся смежным образом. То есть второй ключевой элемент всегда непосредственно следует за первым ключевым элементом в памяти и так далее.

## <a name="csimplemap_arrayelementtype"></a><a name="_arrayelementtype"></a>CSimpleMap::_ArrayElementType

Typedef для ключевого типа.

```
typedef TVal _ArrayElementType;
```

## <a name="csimplemap_arraykeytype"></a><a name="_arraykeytype"></a>CSimpleMap::_ArrayKeyType

Тип для типа значения.

```
typedef TKey _ArrayKeyType;
```

## <a name="csimplemapcsimplemap"></a><a name="csimplemap"></a>CSimpleMap::CSimpleMap

Конструктор.

```
CSimpleMap();
```

### <a name="remarks"></a>Примечания

Инициализирует членов данных.

## <a name="csimplemapcsimplemap"></a><a name="dtor"></a>CSimpleMap::

Деструктор

```
~CSimpleMap();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

## <a name="csimplemapfindkey"></a><a name="findkey"></a>CSimpleMap::FindKey

Находит определенный ключ.

```
int FindKey(const TKey& key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, который нужно найти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает индекс ключа, если найдено, в противном случае возвращается -1.

## <a name="csimplemapfindval"></a><a name="findval"></a>CSimpleMap::FindVal

Находит определенное значение.

```
int FindVal(const TVal& val) const;
```

### <a name="parameters"></a>Параметры

*Валь*<br/>
Значение, поиск которого следует выполнить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает индекс значения, если он найден, в противном случае возвращается -1.

## <a name="csimplemapgetkeyat"></a><a name="getkeyat"></a>CSimpleMap:GetKeyAt

Извлекает ключ в указанном индексе.

```
TKey& GetKeyAt(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс возвращаемого ключевого поля.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ключ, на который ссылается *nIndex*.

### <a name="remarks"></a>Примечания

Индекс, пройденный *nIndex,* должен быть действителен для того, чтобы значение возврата было значимым.

## <a name="csimplemapgetsize"></a><a name="getsize"></a>CSimpleMap::GetSize

Возвращает количество записей в массиве отображения.

```
int GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество записей (ключ и значение — одна запись) в массиве отображения.

## <a name="csimplemapgetvalueat"></a><a name="getvalueat"></a>CSimpleMap:GetValueat

Извлекает значение в конкретном индексе.

```
TVal& GetValueAt(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс значения для возврата.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, на что ссылается *nIndex*.

### <a name="remarks"></a>Примечания

Индекс, пройденный *nIndex,* должен быть действителен для того, чтобы значение возврата было значимым.

## <a name="csimplemaplookup"></a><a name="lookup"></a>CSimpleMap::Поиск

Возвращает значение, связанное с данным ключом.

```
TVal Lookup(const TKey& key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ.

### <a name="return-value"></a>Возвращаемое значение

Возвращает связанное значение. Если не найдено совпадающий ключ, NULL возвращается.

## <a name="csimplemapremove"></a><a name="remove"></a>CSimpleMap::Удалить

Удаляет значение ключа и соответствия.

```
BOOL Remove(const TKey& key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если ключ, и соответствующие значения, были успешно удалены, FALSE в противном случае.

## <a name="csimplemapremoveall"></a><a name="removeall"></a>CSimpleMap::RemoveAll

Удаляет все ключи и значения.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Удаляет все ключи и значения с объекта массива отображения.

## <a name="csimplemapremoveat"></a><a name="removeat"></a>CSimpleMap::RemoveAt

Удаляет ключ и связанное с ним значение в указанном индексе.

```
BOOL RemoveAt(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс ключа и связанное с ним значение для удаления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE, если указанный индекс является недействительным индексом.

## <a name="csimplemapreverselookup"></a><a name="reverselookup"></a>CSimpleMap::ReverseLookup

Возвращает ключ, связанный с данным значением.

```
TKey ReverseLookup(const TVal& val) const;
```

### <a name="parameters"></a>Параметры

*Валь*<br/>
Значение.

### <a name="return-value"></a>Возвращаемое значение

Возвращает связанный ключ. Если не найдено совпадающий ключ, NULL возвращается.

## <a name="csimplemapsetat"></a><a name="setat"></a>CSimpleMap::SetAt

Устанавливает значение, связанное с данным ключом.

```
BOOL SetAt(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ.

*Валь*<br/>
Новое значение для присвоения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если ключ был найден, и значение было успешно изменено, FALSE в противном случае.

## <a name="csimplemapsetatindex"></a><a name="setatindex"></a>CSimpleMap::SetatIndex

Устанавливает ключ и значение в указанном индексе.

```
BOOL SetAtIndex(
    int nIndex,
    const TKey& key,
    const TVal& val);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс, ссылаясь на значение сопряжения ключа и значения, должен измениться.

*key*<br/>
Новый ключ.

*Валь*<br/>
Новое значение.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE в случае успеха, FALSE, если индекс не действителен.

### <a name="remarks"></a>Примечания

Обновления как ключ и значение, на что указывает *nIndex*.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
