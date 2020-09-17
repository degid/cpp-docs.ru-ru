---
title: Класс CSimpleArray
ms.date: 11/04/2016
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
ms.openlocfilehash: d3386687757412d09e4df29e84f691f1615c472a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746475"
---
# <a name="csimplearray-class"></a>Класс CSimpleArray

Этот класс предоставляет методы управления простым массивом.

## <a name="syntax"></a>Синтаксис

```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>
class CSimpleArray
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных для хранения в массиве.

*TEqual*<br/>
Объект черты, определяющий тест на равенство для элементов типа *T*.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSimpleArray::CSimpleArray](#csimplearray)|Конструктор для простого массива.|
|[CSimpleArray:::CSimpleArray](#dtor)|Деструктор для простого массива.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleArray::Добавить](#add)|Добавляет новый элемент в массив.|
|[CSimpleArray::Найти](#find)|Находит элемент в массиве.|
|[CSimpleArray::GetData](#getdata)|Возвращает указатель на данные, хранящиеся в массиве.|
|[CSimpleArray::GetSize](#getsize)|Возвращает количество элементов, хранящихся в массиве.|
|[CSimpleArray::Удалить](#remove)|Удаляет данный элемент из массива.|
|[CSimpleArray::RemoveAll](#removeall)|Удаляет все элементы из массива.|
|[CSimpleArray::RemoveAt](#removeat)|Удаляет указанный элемент из массива.|
|[CSimpleArray:SetAtIndex](#setatindex)|Устанавливает указанный элемент в массиве.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CSimpleArray::operator\[\]](#operator_at)|Получает элемент из массива.|
|[CSimpleArray::оператор](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

`CSimpleArray`предоставляет методы для создания и управления простым `T`массивом любого данного типа.

Параметр `TEqual` обеспечивает средство определения функции равенства для `T`двух элементов типа. Создавая класс, похожий на [CSimpleArrayEqualHelper,](../../atl/reference/csimplearrayequalhelper-class.md)можно изменить поведение теста на равенство для любого данного массива. Например, при работе с массивом указателей может быть полезно определить равенство как в зависимости от значений, на которые ссылаются указатели. Реализация по умолчанию использует **оператора ()**.

И `CSimpleArray` [CSimpleMap](../../atl/reference/csimplemap-class.md) предназначены для небольшого количества элементов. [CAtlArray](../../atl/reference/catlarray-class.md) и [CAtlMap](../../atl/reference/catlmap-class.md) следует использовать, когда массив содержит большое количество элементов.

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

## <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]

## <a name="csimplearrayadd"></a><a name="add"></a>CSimpleArray::Добавить

Добавляет новый элемент в массив.

```
BOOL Add(const T& t);
```

### <a name="parameters"></a>Параметры

*t*<br/>
Элемент для добавления в массив.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если элемент успешно добавлен в массив, FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]

## <a name="csimplearraycsimplearray"></a><a name="csimplearray"></a>CSimpleArray::CSimpleArray

Конструктор для объекта массива.

```
CSimpleArray(const CSimpleArray<T, TEqual>& src);
CSimpleArray();
```

### <a name="parameters"></a>Параметры

*src*<br/>
Существующий объект `CSimpleArray`.

### <a name="remarks"></a>Примечания

Инициализирует элементы данных, создавая новый пустой `CSimpleArray` объект или копию существующего `CSimpleArray` объекта.

## <a name="csimplearraycsimplearray"></a><a name="dtor"></a>CSimpleArray:::CSimpleArray

Деструктор

```
~CSimpleArray();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

## <a name="csimplearrayfind"></a><a name="find"></a>CSimpleArray::Найти

Находит элемент в массиве.

```
int Find(const T& t) const;
```

### <a name="parameters"></a>Параметры

*t*<br/>
Элемент для поиска.

### <a name="return-value"></a>Возвращаемое значение

Возвращает индекс найденного элемента или -1, если элемент не найден.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]

## <a name="csimplearraygetdata"></a><a name="getdata"></a>CSimpleArray::GetData

Возвращает указатель на данные, хранящиеся в массиве.

```
T* GetData() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель к данным в массиве.

## <a name="csimplearraygetsize"></a><a name="getsize"></a>CSimpleArray::GetSize

Возвращает количество элементов, хранящихся в массиве.

```
int GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов, хранящихся в массиве.

## <a name="csimplearrayoperator-"></a><a name="operator_at"></a>CSimpleArray::оператор\[\]

Получает элемент из массива.

```
T& operator[](int nindex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает элемент массива, на который ссылается *nIndex.*

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]

## <a name="csimplearrayoperator-"></a><a name="operator_eq"></a>CSimpleArray::оператор

Оператор присвоения.

```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Массив для копирования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `CSimpleArray` обновленный объект.

### <a name="remarks"></a>Примечания

Копирует все элементы объекта, `CSimpleArray` на который ссылается *src,* в текущий объект массива, заменяя все существующие данные.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]

## <a name="csimplearrayremove"></a><a name="remove"></a>CSimpleArray::Удалить

Удаляет данный элемент из массива.

```
BOOL Remove(const T& t);
```

### <a name="parameters"></a>Параметры

*t*<br/>
Элемент для удаления из массива.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если элемент найден и удален, FALSE в противном случае.

### <a name="remarks"></a>Примечания

При удалении элемента остальные элементы массива перенумерованы для заполнения пустого пространства.

## <a name="csimplearrayremoveall"></a><a name="removeall"></a>CSimpleArray::RemoveAll

Удаляет все элементы из массива.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Удаляет все элементы, которые в настоящее время хранятся в массиве.

## <a name="csimplearrayremoveat"></a><a name="removeat"></a>CSimpleArray::RemoveAt

Удаляет указанный элемент из массива.

```
BOOL RemoveAtint nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс, указывающий на элемент для удаления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если элемент был удален, FALSE, если индекс был недействительным.

### <a name="remarks"></a>Примечания

При удалении элемента остальные элементы массива перенумерованы для заполнения пустого пространства.

## <a name="csimplearraysetatindex"></a><a name="setatindex"></a>CSimpleArray:SetAtIndex

Установите указанный элемент в массиве.

```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс элемента для изменения.

*t*<br/>
Значение, присваиваемое указанному элементу.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE в случае успеха, FALSE, если индекс не действителен.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
