---
title: Класс CComSafeArray
ms.date: 05/06/2019
f1_keywords:
- CComSafeArray
- ATLSAFE/ATL::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::Add
- ATLSAFE/ATL::CComSafeArray::Attach
- ATLSAFE/ATL::CComSafeArray::CopyFrom
- ATLSAFE/ATL::CComSafeArray::CopyTo
- ATLSAFE/ATL::CComSafeArray::Create
- ATLSAFE/ATL::CComSafeArray::Destroy
- ATLSAFE/ATL::CComSafeArray::Detach
- ATLSAFE/ATL::CComSafeArray::GetAt
- ATLSAFE/ATL::CComSafeArray::GetCount
- ATLSAFE/ATL::CComSafeArray::GetDimensions
- ATLSAFE/ATL::CComSafeArray::GetLowerBound
- ATLSAFE/ATL::CComSafeArray::GetSafeArrayPtr
- ATLSAFE/ATL::CComSafeArray::GetType
- ATLSAFE/ATL::CComSafeArray::GetUpperBound
- ATLSAFE/ATL::CComSafeArray::IsSizable
- ATLSAFE/ATL::CComSafeArray::MultiDimGetAt
- ATLSAFE/ATL::CComSafeArray::MultiDimSetAt
- ATLSAFE/ATL::CComSafeArray::Resize
- ATLSAFE/ATL::CComSafeArray::SetAt
- ATLSAFE/ATL::CComSafeArray::m_psa
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
ms.openlocfilehash: d1e72d364858ea31541d574ed77bdc8ccca7d748
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327390"
---
# <a name="ccomsafearray-class"></a>Класс CComSafeArray

Этот класс является оберткой для `SAFEARRAY` структуры.

## <a name="syntax"></a>Синтаксис

```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных для сохранения в массиве.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComSafeArray::CComSafeArray](#ccomsafearray)|Конструктор.|
|[CComSafeArray:::CComSafeArray](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComSafeArray::Добавить](#add)|Добавляет один или несколько `SAFEARRAY` элементов, `CComSafeArray`или структуры, в .|
|[CComSafeArray::Attach](#attach)|Прикрепляет `SAFEARRAY` структуру `CComSafeArray` к объекту.|
|[CComSafeArray::CopyFrom](#copyfrom)|Копирует содержимое `SAFEARRAY` структуры в `CComSafeArray` объект.|
|[CComSafeРэй::CopyTo](#copyto)|Создает копию объекта `CComSafeArray`.|
|[CComSafeArray::Create](#create)|Создает объект `CComSafeArray`.|
|[CComSafeArray::Destroy](#destroy)|Уничтожает объект `CComSafeArray` .|
|[CComSafeArray::Detach](#detach)|Отсоединяет сяск `SAFEARRAY` `CComSafeArray` от объекта.|
|[CComSafeArray:GetAt](#getat)|Получает один элемент из одномерного массива.|
|[CComSafeArray::GetCount](#getcount)|Возвращает число элементов в массиве.|
|[CComSafeArray:GetDimensions](#getdimensions)|Возвращает число измерений в массиве.|
|[CComSafeArray::GetLowerBound](#getlowerbound)|Возвращает нижнюю границу заданного измерения массива.|
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|Возвращает адрес элемента данных `m_psa` .|
|[CComSafeArray::GetType](#gettype)|Возвращает тип данных, хранящихся в массиве.|
|[CComSafeArray::GetUpperBound](#getupperbound)|Возвращает верхнюю границу любого измерения массива.|
|[CComSafeArray::IsSizable](#issizable)|Проверяет, можно ли изменить размер объекта `CComSafeArray` .|
|[Ccomsafearray::Multidimgetat](#multidimgetat)|Получает один элемент из многомерного массива.|
|[CcomSafearray::Multidimsetat](#multidimsetat)|Задает значение элемента в многомерном массиве.|
|[CComSafeArray::Resize](#resize)|Изменяет размер объекта `CComSafeArray` .|
|[CComSafeArray::SetAt](#setat)|Задает значение элемента в одномерном массиве.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CComSafeArray:оператор LPSAFEARRAY](#operator_lpsafearray)|Бросает значение указателю. `SAFEARRAY`|
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|Получает элемент из массива.|
|[CComSafeArray::оператор](#operator_eq)|Оператор присвоения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComSafeArray::m_psa](#m_psa)|Этот член данных содержит `SAFEARRAY` адрес структуры.|

## <a name="remarks"></a>Примечания

`CComSafeArray` предоставляет оболочку для класса [SAFEARRAY Data Type](/windows/win32/api/oaidl/ns-oaidl-safearray) , упрощая создание одно- и многомерных массивов практически любого поддерживаемого типа VARIANT и управление ими.

`CComSafeArray` упрощает передачу массивов между процессами и обеспечивает дополнительную безопасность путем проверки значений индекса массива на соответствие верхней и нижней границам.

Нижняя граница `CComSafeArray` может начинаться с любого определенного пользователем значения. Однако нижняя граница массивов, доступ к которым осуществляется через C++, должна быть равна 0. В других языках, например Visual Basic, могут использоваться другие ограничивающие значения (например, от −10 до 10).

Используйте [CComSafeArray::Create](#create) для создания объекта `CComSafeArray` , и [CComSafeArray::Destroy](#destroy) — для его удаления.

`CComSafeArray` может содержать следующее подмножество типов данных VARIANT.

|VARTYPE|Описание|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|INT|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|FLOAT|
|VT_R8|double|
|VT_DECIMAL|указатель типа decimal|
|VT_VARIANT|указатель типа variant|
|VT_CY|Currency - тип данных|

## <a name="requirements"></a>Требования

**Заголовок:** atlsafe.h

## <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]

## <a name="ccomsafearrayadd"></a><a name="add"></a>CComSafeArray::Добавить

Добавляет один или несколько `SAFEARRAY` элементов, `CComSafeArray`или структуры, в .

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Параметры

*psaSrc*<br/>
Указатель на объект `SAFEARRAY`.

*ulCount*<br/>
Количество объектов для добавления в массив.

*Pt*<br/>
Указатель на один или несколько объектов, которые будут добавлены в массив.

*T*<br/>
Ссылка на объект, который будет добавлен в массив.

*bCopy*<br/>
Указывает, должна ли быть создана копия данных. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Новые объекты придатились к `SAFEARRAY` концу существующего объекта. Добавление объекта к многомерной `SAFEARRAY` объекту не поддерживается. При добавлении существующего массива объектов оба массива должны содержать элементы одного и того же типа.

Флаг *bCopy* учитывается при добавлении элементов типа BSTR или VARIANT в массив. Значение TRUE по умолчанию гарантирует, что новая копия состоит из данных при добавлении элемента в массив.

## <a name="ccomsafearrayattach"></a><a name="attach"></a>CComSafeArray::Attach

Прикрепляет `SAFEARRAY` структуру `CComSafeArray` к объекту.

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Параметры

*psaSrc*<br/>
Указатель на `SAFEARRAY` структуру.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Прикрепляет `SAFEARRAY` структуру `CComSafeArray` к объекту, делая существующие `CComSafeArray` методы доступными.

## <a name="ccomsafearrayccomsafearray"></a><a name="ccomsafearray"></a>CComSafeArray::CComSafeArray

Конструктор.

```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Параметры

*привязка*<br/>
Структура `SAFEARRAYBOUND`.

*ulCount*<br/>
Количество элементов в массиве.

*lLBound*<br/>
Нижнее значение границы; то есть индекс первого элемента в массиве.

*pBound*<br/>
Указатель на `SAFEARRAYBOUND` структуру.

*uDims*<br/>
Количество размеров в массиве.

*saSrc*<br/>
Ссылка на `SAFEARRAY` структуру или `CComSafeArray` объект. В любом случае конструктор использует эту ссылку, чтобы сделать копию массива, поэтому массив не упоминается после строительства.

*psaSrc*<br/>
Указатель на `SAFEARRAY` структуру. Конструктор использует этот адрес, чтобы сделать копию массива, поэтому массив не упоминается после строительства.

### <a name="remarks"></a>Примечания

Создает объект `CComSafeArray`.

## <a name="ccomsafearrayccomsafearray"></a><a name="dtor"></a>CComSafeArray:::CComSafeArray

Деструктор

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

## <a name="ccomsafearraycopyfrom"></a><a name="copyfrom"></a>CComSafeArray::CopyFrom

Копирует содержимое `SAFEARRAY` структуры в `CComSafeArray` объект.

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Параметры

*ppArray*<br/>
Указатель на `SAFEARRAY` копирование.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Этот метод копирует содержимое `SAFEARRAY` объекта `CComSafeArray` в текущем объекте. Существующее содержимое массива заменено.

## <a name="ccomsafearraycopyto"></a><a name="copyto"></a>CComSafeРэй::CopyTo

Создает копию объекта `CComSafeArray`.

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Параметры

*ppArray*<br/>
Указатель на место, в котором `SAFEARRAY`для создания нового .

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Этот метод копирует содержимое `CComSafeArray` объекта `SAFEARRAY` в структуру.

## <a name="ccomsafearraycreate"></a><a name="create"></a>CComSafeArray::Создание

Создает объект `CComSafeArray`.

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>Параметры

*pBound*<br/>
Указатель на объект `SAFEARRAYBOUND`.

*uDims*<br/>
Число измерений в массиве.

*ulCount*<br/>
Количество элементов в массиве.

*lLBound*<br/>
Нижнее значение границы; то есть индекс первого элемента в массиве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Объект `CComSafeArray` может быть создан `SAFEARRAYBOUND` из существующей структуры и количества измерений, или путем указания количества элементов в массиве и нижней границе. Если к массиву можно получить доступ с c,, нижняя граница должна быть 0. Другие языки могут допускать другие значения для нижней границы (например, Visual Basic поддерживает массивы с элементами с диапазоном, например -10 до 10).

## <a name="ccomsafearraydestroy"></a><a name="destroy"></a>CComSafeArray::Destroy

Уничтожает объект `CComSafeArray` .

```
HRESULT Destroy();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Уничтожает `CComSafeArray` существующий объект и все данные, которые он содержит.

## <a name="ccomsafearraydetach"></a><a name="detach"></a>CComSafeArray::Detach

Отсоединяет сяск `SAFEARRAY` `CComSafeArray` от объекта.

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель объекту. `SAFEARRAY`

### <a name="remarks"></a>Примечания

Этот метод отделяет `SAFEARRAY` объект `CComSafeArray` от объекта.

## <a name="ccomsafearraygetat"></a><a name="getat"></a>CComSafeArray:GetAt

Получает один элемент из одномерного массива.

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>Параметры

*Lindex*<br/>
Индексное число значения в массиве для возврата.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на необходимый элемент массива.

## <a name="ccomsafearraygetcount"></a><a name="getcount"></a>CComSafeArray::GetCount

Возвращает число элементов в массиве.

```
ULONG GetCount(UINT uDim = 0) const;
```

### <a name="parameters"></a>Параметры

*uDim*<br/>
Измерение массива.

### <a name="return-value"></a>Возвращаемое значение

Возвращает число элементов в массиве.

### <a name="remarks"></a>Примечания

При использовании многомерного массива этот метод возвращает количество элементов только в определенном измерении.

## <a name="ccomsafearraygetdimensions"></a><a name="getdimensions"></a>CComSafeArray:GetDimensions

Возвращает число измерений в массиве.

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число измерений в массиве.

## <a name="ccomsafearraygetlowerbound"></a><a name="getlowerbound"></a>CComSafeArray::GetLowerBound

Возвращает нижнюю границу заданного измерения массива.

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Параметры

*uDim*<br/>
Измерение массива, для которого можно получить нижнюю границу. Если опущено, по умолчанию 0.

### <a name="return-value"></a>Возвращаемое значение

Возвращает нижнюю границу.

### <a name="remarks"></a>Примечания

Если нижняя граница растрачивается 0, это указывает на C-подобный массив, первым элементом которого является элемент номер 0. В случае ошибки, например, недействительного аргумента `AtlThrow` измерения, этот метод вызывается с помощью HRESULT, описывающего ошибку.

## <a name="ccomsafearraygetsafearrayptr"></a><a name="getsafearrayptr"></a>CComSafeArray::GetSafeArrayPtr

Возвращает адрес элемента данных `m_psa` .

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на [CComSafeArray::m_psa](#m_psa) данных.

## <a name="ccomsafearraygettype"></a><a name="gettype"></a>CComSafeArray::GetType

Возвращает тип данных, хранящихся в массиве.

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает тип данных, хранящихся в массиве, который может быть любым из следующих типов:

|VARTYPE|Описание|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|INT|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|FLOAT|
|VT_R8|double|
|VT_DECIMAL|указатель типа decimal|
|VT_VARIANT|указатель типа variant|
|VT_CY|Currency - тип данных|

## <a name="ccomsafearraygetupperbound"></a><a name="getupperbound"></a>CComSafeArray::GetUpperBound

Возвращает верхнюю границу любого измерения массива.

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Параметры

*uDim*<br/>
Измерение массива, для которого можно получить верхнюю границу. Если опущено, по умолчанию 0.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верхнюю границу. Это значение является инклюзивным, максимально действительным индексом для этого измерения.

### <a name="remarks"></a>Примечания

В случае ошибки, например, недействительного аргумента `AtlThrow` измерения, этот метод вызывается с помощью HRESULT, описывающего ошибку.

## <a name="ccomsafearrayissizable"></a><a name="issizable"></a>CComSafeArray::IsSizable

Проверяет, можно ли изменить размер объекта `CComSafeArray` .

```
bool IsSizable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, `CComSafeArray` если можно изменить размер, FALSE, если он не может.

## <a name="ccomsafearraym_psa"></a><a name="m_psa"></a>CComSafeArray::m_psa

Сохраняет адрес `SAFEARRAY` структуры, доступ к нему.

```
LPSAFEARRAY m_psa;
```

## <a name="ccomsafearraymultidimgetat"></a><a name="multidimgetat"></a>Ccomsafearray::Multidimgetat

Получает один элемент из многомерного массива.

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>Параметры

*alIndex*<br/>
Указатель на вектор индексов для каждого измерения массива. Самым левым (наиболее `alIndex[0]`значительным) измерением является .

*T*<br/>
Ссылка на возвращенные данные.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="ccomsafearraymultidimsetat"></a><a name="multidimsetat"></a>CcomSafearray::Multidimsetat

Задает значение элемента в многомерном массиве.

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>Параметры

*alIndex*<br/>
Указатель на вектор индексов для каждого измерения массива. Самое правильное (наименее `alIndex`значимое) измерение – это «0».

*T*<br/>
Определяет значение нового элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Это многомерная версия [CComSafeArray::SetAt](#setat).

## <a name="ccomsafearrayoperator-"></a><a name="operator_at"></a>CComSafeArray:оператор\[\]

Получает элемент из массива.

```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```

### <a name="parameters"></a>Параметры

*lИндекс, n-индекс*<br/>
Индексное число требуемого элемента в массиве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает соответствующий элемент массива.

### <a name="remarks"></a>Примечания

Выполняет аналогичную функцию [CComSafeArray::GetAt](#getat), однако этот оператор работает только с одномерными массивами.

## <a name="ccomsafearrayoperator-"></a><a name="operator_eq"></a>CComSafeArray::оператор

Оператор присвоения.

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Параметры

*saSrc*<br/>
Ссылка на объект `CComSafeArray`.

*psaSrc*<br/>
Указатель на объект `SAFEARRAY`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает тип данных, хранящихся в массиве.

## <a name="ccomsafearrayoperator-lpsafearray"></a><a name="operator_lpsafearray"></a>CComSafeArray:оператор LPSAFEARRAY

Бросает значение указателю. `SAFEARRAY`

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>Возвращаемое значение

Бросает значение указателю. `SAFEARRAY`

## <a name="ccomsafearrayresize"></a><a name="resize"></a>CComSafeArray::Resize

Изменяет размер объекта `CComSafeArray` .

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>Параметры

*pBound*<br/>
Указатель на `SAFEARRAYBOUND` структуру, содержащую информацию о количестве элементов и нижней границе массива.

*ulCount*<br/>
Запрошенное количество объектов в массиве повторного размера.

*lLBound*<br/>
Нижняя граница.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Этот метод изменяет только самое правильное измерение. Он не будет изменять `IsResizable` массивы, которые возвращаются как FALSE.

## <a name="ccomsafearraysetat"></a><a name="setat"></a>CComSafeArray::SetAt

Задает значение элемента в одномерном массиве.

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Параметры

*Lindex*<br/>
Индексное число элемента массива для установки.

*T*<br/>
Новое значение указанного элемента.

*bCopy*<br/>
Указывает, должна ли быть создана копия данных. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Примечания

Флаг *bCopy* учитывается при добавлении элементов типа BSTR или VARIANT в массив. Значение TRUE по умолчанию гарантирует, что новая копия состоит из данных при добавлении элемента в массив.

## <a name="see-also"></a>См. также раздел

[SAFEARRAY Data Type](/windows/win32/api/oaidl/ns-oaidl-safearray)<br/>
[CComSafeArray::Create](#create)<br/>
[CComSafeArray::Destroy](#destroy)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
