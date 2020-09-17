---
title: Класс Кобаррай
description: Справочник по API для `CObArray` `MFC` класса, в котором хранятся `CObject` указатели в массиве.
ms.date: 08/27/2020
f1_keywords:
- CObArray
- AFXCOLL/CObArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
ms.openlocfilehash: cbc1799a9634b3d8c09077b755b8a097289460fd
ms.sourcegitcommit: c8f1605354724a13566bc3b0fac3c5d98265f1d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2020
ms.locfileid: "89062151"
---
# <a name="cobarray-class"></a>Класс Кобаррай

Поддерживает массивы указателей `CObject` .

## <a name="syntax"></a>Синтаксис

```cpp
class CObArray : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кобаррай:: Кобаррай](#cobarray)|Конструирует пустой массив для `CObject` указателей.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кобаррай:: Add](#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|
|[Кобаррай:: Append](#append)|Добавляет другой массив к массиву. При необходимости размер массива увеличивается.|
|[Кобаррай:: Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[Кобаррай:: ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[Кобаррай:: Фриекстра](#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|
|[Кобаррай:: GetAt](#getat)|Возвращает значение по указанному индексу.|
|[Кобаррай:: NOCOUNT](#getcount)|Возвращает количество элементов в массиве.|
|[Кобаррай:: GetData](#getdata)|Разрешает доступ к элементам в массиве. Может иметь значение `NULL`.|
|[Кобаррай:: DataSize](#getsize)|Возвращает количество элементов в массиве.|
|[Кобаррай:: GetUpperBound](#getupperbound)|Возвращает самый большой допустимый индекс.|
|[Кобаррай:: Инсертат](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|
|[Кобаррай:: IsEmpty](#isempty)|Определяет, пуст ли массив.|
|[Кобаррай:: RemoveAll](#removeall)|Удаляет все элементы из этого массива.|
|[Кобаррай:: RemoveAt](#removeat)|Удаляет элемент по указанному индексу.|
|[Кобаррай:: SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|
|[Кобаррай:: Сетатгров](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|
|[Кобаррай:: SetSize](#setsize)|Задает число элементов, которые будут храниться в этом массиве.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Кобаррай::operator \[\]](#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Примечания

Эти массивы объектов похожи на массивы C, но они могут динамически сжиматься и увеличиваться по мере необходимости.

Индексы массивов всегда начинаются в позиции 0. Вы можете решить, следует ли исправить верхнюю границу или разрешить массиву расширять при добавлении элементов после текущей границы. Память выделяется непрерывно с верхней границей, даже если некоторые элементы имеют значение `NULL` .

В Win32 размер `CObArray` объекта ограничен только доступной памятью.

Как и в случае с массивом C, время доступа для `CObArray` индексированного элемента является константой и не зависит от размера массива.

`CObArray` включает макрос IMPLEMENT_SERIAL для поддержки сериализации и дампа его элементов. Если массив `CObject` указателей хранится в архиве с перегруженным оператором вставки или с `Serialize` функцией-членом, каждый `CObject` элемент в свою очередь сериализуется вместе с индексом массива.

Если требуется дамп отдельных `CObject` элементов в массиве, необходимо задать `CDumpContext` для глубины объекта значение 1 или больше.

При `CObArray` удалении объекта или удалении его элементов `CObject` удаляются только указатели, а не объекты, на которые они ссылаются.

> [!NOTE]
> Перед работой с массивом используйте функцию `SetSize`, чтобы определить его размер и выделить под него память. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

Наследование класса массива аналогично наследованию списка. Дополнительные сведения о наследовании класса списков специального назначения см. в статье [коллекции](../../mfc/collections.md)статей.

> [!NOTE]
> Если предполагается сериализовать массив, необходимо использовать макрос IMPLEMENT_SERIAL в реализации производного класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CObArray`

## <a name="requirements"></a>Требования

**Заголовок:** афксколл.h

## <a name="cobarrayadd"></a><a name="add"></a> Кобаррай:: Add

Добавляет новый элемент в конец массива, увеличивая массив на 1.

```cpp
INT_PTR Add(CObject* newElement);
```

### <a name="parameters"></a>Параметры

*невелемент*\
`CObject`Указатель, добавляемый к этому массиву.

### <a name="return-value"></a>Возвращаемое значение

Индекс добавленного элемента.

### <a name="remarks"></a>Примечания

Если параметр [SetSize](#setsize) использовался со значением *нгровби* больше 1, может быть выделен дополнительный объем памяти. Однако верхняя граница будет увеличена только до 1.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::Add` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`INT_PTR Add(BYTE newElement);`<br /><br />`throw(CMemoryException*);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`INT_PTR Add(DWORD newElement);`<br /><br />`throw(CMemoryException*);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`INT_PTR Add(void* newElement);`<br /><br />`throw(CMemoryException*);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`INT_PTR Add(LPCTSTR newElement); throw(CMemoryException*);`<br /><br />`INT_PTR Add(const CString& newElement);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`INT_PTR Add(UINT newElement);`<br /><br />`throw(CMemoryException*);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`INT_PTR Add(WORD newElement);`<br /><br />`throw(CMemoryException*);`|

### <a name="example"></a>Пример

  Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
Add example: A CObArray with 2 elements
[0] = a CAge at $442A 21
[1] = a CAge at $4468 40
```

## <a name="cobarrayappend"></a><a name="append"></a> Кобаррай:: Append

Вызовите эту функцию члена, чтобы добавить содержимое другого массива в конец заданного массива.

```cpp
INT_PTR Append(const CObArray& src);
```

### <a name="parameters"></a>Параметры

*src*\
Источник элементов, добавляемых в массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого добавленного элемента.

### <a name="remarks"></a>Примечания

Массивы должны быть одного типа.

При необходимости `Append` может выделить дополнительный объем памяти для размещения элементов, добавляемых в массив.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::Append` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`INT_PTR Append(const CByteArray& src);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`INT_PTR Append(const CDWordArray& src);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`INT_PTR Append(const CPtrArray& src);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`INT_PTR Append(const CStringArray& src);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`INT_PTR Append(const CUIntArray& src);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`INT_PTR Append(const CWordArray& src);`|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]

## <a name="cobarraycopy"></a><a name="copy"></a> Кобаррай:: Copy

Вызовите эту функцию члена, чтобы перезаписать элементы заданного массива элементами другого массива того же типа.

```cpp
void Copy(const CObArray& src);
```

### <a name="parameters"></a>Параметры

*src*\
Источник элементов, копируемых в массив.

### <a name="remarks"></a>Примечания

`Copy` не освобождает память. При необходимости `Copy` может выделить дополнительный объем памяти для размещения элементов, копируемых в массив.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::Copy` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`void Copy(const CByteArray& src);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void Copy(const CDWordArray& src);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void Copy(const CPtrArray& src);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void Copy(const CStringArray& src);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void Copy(const CUIntArray& src);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void Copy(const CWordArray& src);`|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]

## <a name="cobarraycobarray"></a><a name="cobarray"></a> Кобаррай:: Кобаррай

Конструирует пустой `CObject` массив указателей.

```cpp
CObArray();
```

### <a name="remarks"></a>Примечания

Массив растет по одному элементу за раз.

В следующей таблице показаны другие конструкторы, аналогичные `CObArray::CObArray` .

|Класс|Конструктор|
|-----------|-----------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`CByteArray();`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`CDWordArray();`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`CPtrArray();`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`CStringArray();`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`CUIntArray();`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`CWordArray();`|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]

## <a name="cobarrayelementat"></a><a name="elementat"></a> Кобаррай:: ElementAt

Возвращает временную ссылку на указатель элемента в массиве.

```cpp
CObject*& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*\
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному `GetUpperBound` .

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `CObject` указатель.

### <a name="remarks"></a>Примечания

Он используется для реализации оператора присваивания на стороне слева для массивов. Это расширенная функция, которая должна использоваться только для реализации специальных операторов массивов.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::ElementAt` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`BYTE& ElementAt(INT_PTR nIndex);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`DWORD& ElementAt(INT_PTR nIndex);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void*& ElementAt(INT_PTR nIndex);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`CString& ElementAt(INT_PTR nIndex);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`UINT& ElementAt(INT_PTR nIndex);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`WORD& ElementAt(INT_PTR nIndex);`|

### <a name="example"></a>Пример

См. пример для [кобаррай:: DataSize](#getsize).

## <a name="cobarrayfreeextra"></a><a name="freeextra"></a> Кобаррай:: Фриекстра

Освобождает все дополнительные памяти, которые были выделены, пока массив был увеличен.

```cpp
void FreeExtra();
```

### <a name="remarks"></a>Примечания

Эта функция не влияет на размер или верхнюю границу массива.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::FreeExtra` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`void FreeExtra();`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void FreeExtra();`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void FreeExtra();`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void FreeExtra();`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void FreeExtra();`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void FreeExtra();`|

### <a name="example"></a>Пример

  См. пример для [кобаррай:: GetData](#getdata).

## <a name="cobarraygetat"></a><a name="getat"></a> Кобаррай:: GetAt

Возвращает элемент массива по указанному индексу.

```cpp
CObject* GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*\
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному `GetUpperBound` .

### <a name="return-value"></a>Возвращаемое значение

`CObject`Элемент указателя, находящегося в данный момент в этом индексе.

### <a name="remarks"></a>Примечания

> [!NOTE]
> Передача отрицательного значения или значения, превышающего значение, возвращенное, `GetUpperBound` приведет к неудачному утверждению.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::GetAt` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`BYTE GetAt(INT_PTR nIndex) const;`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`DWORD GetAt(INT_PTR nIndex) const;`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void* GetAt(INT_PTR nIndex) const;`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`CString GetAt(INT_PTR nIndex) const;`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`UINT GetAt(INT_PTR nIndex) const;`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`WORD GetAt(INT_PTR nIndex) const;`|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]

## <a name="cobarraygetcount"></a><a name="getcount"></a> Кобаррай:: NOCOUNT

Возвращает число элементов массива.

```cpp
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в массиве.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить количество элементов в массиве. Поскольку индексы отсчитываются от нуля, размер равен 1 больше, чем самый крупный индекс.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::GetCount` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`INT_PTR GetCount() const;`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`INT_PTR GetCount() const;`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`INT_PTR GetCount() const;`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`INT_PTR GetCount() const;`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`INT_PTR GetCount() const;`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`INT_PTR GetCount() const;`|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]

## <a name="cobarraygetdata"></a><a name="getdata"></a> Кобаррай:: GetData

Используйте эту функцию члена для получения прямого доступа к элементам в массиве.

```cpp
const CObject** GetData() const;

CObject** GetData();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на массив `CObject` указателей.

### <a name="remarks"></a>Примечания

Если нет доступных элементов, `GetData` возвращает `NULL` значение.

Хотя прямой доступ к элементам массива позволяет быстрее работать, следует соблюдать осторожность при вызове `GetData` . любые ошибки, которые вы вносите непосредственно, влияют на элементы массива.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::GetData` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`const BYTE* GetData() const; BYTE* GetData();`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`const DWORD* GetData() const; DWORD* GetData();`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`const void** GetData() const; void** GetData();`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`const CString* GetData() const; CString* GetData();`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`const UINT* GetData() const; UINT* GetData();`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`const WORD* GetData() const; WORD* GetData();`|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]

## <a name="cobarraygetsize"></a><a name="getsize"></a> Кобаррай:: DataSize

Возвращает размер массива.

```cpp
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Примечания

Так как индексы отсчитываются от нуля, размер равен 1 больше, чем самый крупный индекс.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::GetSize` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`INT_PTR GetSize() const;`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`INT_PTR GetSize() const;`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`INT_PTR GetSize() const;`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`INT_PTR GetSize() const;`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`INT_PTR GetSize() const;`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`INT_PTR GetSize() const;`|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]

## <a name="cobarraygetupperbound"></a><a name="getupperbound"></a> Кобаррай:: GetUpperBound

Возвращает текущую верхнюю границу данного массива.

```cpp
INT_PTR GetUpperBound() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс верхней границы (от нуля).

### <a name="remarks"></a>Примечания

Поскольку индексы массива отсчитываются от нуля, эта функция возвращает значение 1, меньшее `GetSize` .

Условие `GetUpperBound() = -1` указывает, что массив не содержит элементов.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::GetUpperBound` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`INT_PTR GetUpperBound() const;`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`INT_PTR GetUpperBound() const;`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`INT_PTR GetUpperBound() const;`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`INT_PTR GetUpperBound() const;`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`INT_PTR GetUpperBound() const;`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`INT_PTR GetUpperBound() const;`|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]

## <a name="cobarrayinsertat"></a><a name="insertat"></a> Кобаррай:: Инсертат

Вставляет элемент (или все элементы в другом массиве) по указанному индексу.

```cpp
void InsertAt(
    INT_PTR nIndex,
    CObject* newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CObArray* pNewArray);
```

### <a name="parameters"></a>Параметры

*ниндекс*\
Целочисленный индекс, который может быть больше значения, возвращаемого методом `GetUpperBound` .

*невелемент*\
`CObject`Указатель, помещаемый в этот массив. Допускается *невелемент* значения `NULL` .

*нкаунт*\
Количество раз, когда этот элемент должен быть вставлен (значение по умолчанию — 1).

*нстартиндекс*\
Целочисленный индекс, который может быть больше значения, возвращаемого методом `GetUpperBound` .

*пневаррай*\
Другой массив, содержащий элементы для добавления в этот массив.

### <a name="remarks"></a>Примечания

Первая версия `InsertAt` вставляет один элемент (или несколько копий элемента) по указанному индексу в массиве. В процессе он смещается (путем увеличения индекса) существующего элемента в этом индексе и сдвигает все элементы над ним.

Вторая версия вставляет все элементы из другой `CObArray` коллекции, начиная с позиции *нстартиндекс* .

`SetAt`Функция, напротив, заменяет один указанный элемент массива и не сдвигает ни одного элемента.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::InsertAt` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`void InsertAt(INT_PTR nIndex, BYTE newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CByteArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void InsertAt(INT_PTR nIndex, DWORD newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CDWordArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void InsertAt(INT_PTR nIndex, void* newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CPtrArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void InsertAt(INT_PTR nIndex, LPCTSTR newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CStringArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void InsertAt(INT_PTR nIndex, UINT newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CUIntArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void InsertAt(INT_PTR nIndex, WORD newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CWordArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|

### <a name="example"></a>Пример

  Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
InsertAt example: A CObArray with 3 elements
[0] = a CAge at $45C8 21
[1] = a CAge at $4646 30
[2] = a CAge at $4606 40
```

## <a name="cobarrayisempty"></a><a name="isempty"></a> Кобаррай:: IsEmpty

Определяет, пуст ли массив.

```cpp
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если массив пуст; в противном случае — 0.

## <a name="cobarrayoperator--"></a><a name="operator_at"></a> Кобаррай::operator []

Эти операторы подстрочных индексов являются удобным заменой для `SetAt` `GetAt` функций и.

```cpp
CObject*& operator[](int_ptr nindex);
CObject* operator[](int_ptr nindex) const;
```

### <a name="remarks"></a>Примечания

Первый оператор, вызываемый для массивов, которых нет **`const`** , может использоваться либо справа (r-Value), либо слева (l-значение) оператора присваивания. Второй метод, который вызывается для **`const`** массивов, может использоваться только справа.

Отладочная версия библиотеки утверждает, находится ли индекс (в левой или правой части инструкции присваивания) вне границ.

В следующей таблице показаны другие операторы, аналогичные `CObArray::operator []` .

|Класс|Оператор|
|-----------|--------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`BYTE& operator [](INT_PTR nindex);`<br /><br />`BYTE operator [](INT_PTR nindex) const;`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`DWORD& operator [](INT_PTR nindex);`<br /><br />`DWORD operator [](INT_PTR nindex) const;`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void*& operator [](INT_PTR nindex);`<br /><br />`void* operator [](INT_PTR nindex) const;`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`CString& operator [](INT_PTR nindex);`<br /><br />`CString operator [](INT_PTR nindex) const;`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`UINT& operator [](INT_PTR nindex);`<br /><br />`UINT operator [](INT_PTR nindex) const;`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`WORD& operator [](INT_PTR nindex);`<br /><br />`WORD operator [](INT_PTR nindex) const;`|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]

## <a name="cobarrayremoveall"></a><a name="removeall"></a> Кобаррай:: RemoveAll

Удаляет все указатели из этого массива, но фактически не удаляет `CObject` объекты.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Если массив уже пуст, функция продолжает работать.

`RemoveAll`Функция освобождает всю память, используемую для хранения указателя.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::RemoveAll` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`void RemoveAll();`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void RemoveAll();`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void RemoveAll();`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void RemoveAll();`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void RemoveAll();`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void RemoveAll();`|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]

## <a name="cobarrayremoveat"></a><a name="removeat"></a> Кобаррай:: RemoveAt

Удаляет один или несколько элементов, начиная с указанного индекса в массиве.

```cpp
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Параметры

*ниндекс*\
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному `GetUpperBound` .

*нкаунт*\
Число удаляемых элементов.

### <a name="remarks"></a>Примечания

В процессе он сдвигает все элементы над удаленными элементами. Он уменьшает верхнюю границу массива, но не освобождает память.

Если попытаться удалить больше элементов, чем содержится в массиве над точкой удаления, то отладочная версия библиотеки будет утверждена.

`RemoveAt`Функция удаляет `CObject` указатель из массива, но сам объект не удаляется.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::RemoveAt` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|

### <a name="example"></a>Пример

  Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
RemoveAt example: A CObArray with 1 elements
[0] = a CAge at $4606 40
```

## <a name="cobarraysetat"></a><a name="setat"></a> Кобаррай:: SetAt

Задает элемент массива по указанному индексу.

```cpp
void SetAt(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*ниндекс*\
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному `GetUpperBound` .

*невелемент*\
Указатель на объект, вставляемый в этот массив. `NULL`Допустимое значение.

### <a name="remarks"></a>Примечания

`SetAt` не приводит к увеличению размера массива. Используйте, `SetAtGrow` Если требуется, чтобы массив был автоматически расти.

Убедитесь, что значение индекса соответствует допустимой позиции в массиве. Если он выходит за пределы допустимого диапазона, отладочная версия библиотеки утверждается.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::SetAt` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`void SetAt(INT_PTR nIndex, BYTE newElement);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void SetAt(INT_PTR nIndex, DWORD newElement);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void SetAt(INT_PTR nIndex, void* newElement);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void SetAt(INT_PTR nIndex, LPCTSTR newElement);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void SetAt(INT_PTR nIndex, UINT newElement);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void SetAt(INT_PTR nIndex, WORD newElement);`|

### <a name="example"></a>Пример

  Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
SetAt example: A CObArray with 2 elements
[0] = a CAge at $47E0 30
[1] = a CAge at $47A0 40
```

## <a name="cobarraysetatgrow"></a><a name="setatgrow"></a> Кобаррай:: Сетатгров

Задает элемент массива по указанному индексу.

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*ниндекс*\
Целочисленный индекс, который больше или равен 0.

*невелемент*\
Указатель на объект, добавляемый в этот массив. `NULL`Допустимое значение.

### <a name="remarks"></a>Примечания

При необходимости массив автоматически растет (то есть верхняя граница корректируется для размещения нового элемента).

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::SetAtGrow` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`void SetAtGrow(INT_PTR nIndex, BYTE newElement);`<br /><br />`throw(CMemoryException*);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void SetAtGrow(INT_PTR nIndex, DWORD newElement);`<br /><br />`throw(CMemoryException*);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void SetAtGrow(INT_PTR nIndex, void* newElement);`<br /><br />`throw( CMemoryException*);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void SetAtGrow(INT_PTR nIndex, LPCTSTR newElement);`<br /><br />`throw(CMemoryException*);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void SetAtGrow(INT_PTR nIndex, UINT newElement);`<br /><br />`throw(CMemoryException*);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void SetAtGrow(INT_PTR nIndex, WORD newElement);`<br /><br />`throw(CMemoryException*);`|

### <a name="example"></a>Пример

  Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
SetAtGrow example: A CObArray with 4 elements
[0] = a CAge at $47C0 21
[1] = a CAge at $4800 40
[2] = NULL
[3] = a CAge at $4840 65
```

## <a name="cobarraysetsize"></a><a name="setsize"></a> Кобаррай:: SetSize

Устанавливает размер пустого или существующего массива. При необходимости выделяет память.

```cpp
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Параметры

*нневсизе*\
Новый размер массива (число элементов). Должна быть не ниже 0.

*нгровби*\
Минимальное число слотов элементов для выделения при необходимости увеличения размера.

### <a name="remarks"></a>Примечания

Если новый размер меньше старого, массив усекается и освобождается вся неиспользуемая память. Для повышения эффективности вызовите метод, `SetSize` чтобы задать размер массива перед его использованием. Это предотвращает необходимость перераспределения и копирования массива при каждом добавлении элемента.

Параметр *нгровби* влияет на выделение внутренней памяти во время роста массива. Его использование никогда не влияет на размер массива, сообщаемый `GetSize` и `GetUpperBound` .

Если размер массива увеличился, все вновь выделенные `CObject *` указатели устанавливаются в значение `NULL` .

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::SetSize` .

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|

### <a name="example"></a>Пример

  См. пример для [кобаррай:: GetData](#getdata).

## <a name="see-also"></a>См. также раздел

[CObject, класс](../../mfc/reference/cobject-class.md)\
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)\
[Класс Кстрингаррай](../../mfc/reference/cstringarray-class.md)\
[Класс Кптраррай](../../mfc/reference/cptrarray-class.md)\
[Класс CByteArray](../../mfc/reference/cbytearray-class.md)\
[Класс Квордаррай](../../mfc/reference/cwordarray-class.md)\
[Класс Кдвордаррай](../../mfc/reference/cdwordarray-class.md)
