---
title: Класс ColeSafeArray
ms.date: 08/29/2019
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
ms.openlocfilehash: 10e9975bac776429a38bfc707215a9465ce35c2e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753771"
---
# <a name="colesafearray-class"></a>Класс ColeSafeArray

Класс для работы с массивами произвольных типов и измерений.

## <a name="syntax"></a>Синтаксис

```
class COleSafeArray : public tagVARIANT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeSafeArray::COleSafeArray](#colesafearray)|Формирует объект `COleSafeArray`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeSafeArray::AccessData](#accessdata)|Извлекает указатель на данные массива.|
|[COleSafeArray::AllocData](#allocdata)|Выделяет память для массива.|
|[ColeSafeArray::АллокДескриптор](#allocdescriptor)|Выделяет память для дескриптора безопасного массива.|
|[ColeSafeArray::Attach](#attach)|Предоставляет объекту `VARIANT` контроль над `COleSafeArray` существующим массивом.|
|[ColeSafeArray::Clear](#clear)|Освобождает все данные в `VARIANT`базовом .|
|[ColeSafeArray::Copy](#copy)|Создает копию существующего массива.|
|[ColeSafeArray::Создание](#create)|Создает безопасный массив.|
|[ColeSafeArray::CreateOneDim](#createonedim)|Создает одномерный `COleSafeArray` объект.|
|[ColeSafeArray::Destroy](#destroy)|Уничтожает существующий массив.|
|[ColeSafeArray::DestroyData](#destroydata)|Уничтожает данные в безопасном массиве.|
|[ColeSafeArray::DэстройДескриптор](#destroydescriptor)|Уничтожает дескриптор безопасного массива.|
|[ColeSafeArray: :Detach](#detach)|Отсоединяет массив VARIANT от `COleSafeArray` объекта (чтобы данные не освобождался).|
|[ColeSafeArray::GetByteArray](#getbytearray)|Копирует содержимое безопасного массива в [CByteArray](../../mfc/reference/cbytearray-class.md).|
|[ColeSafeArray::GetDim](#getdim)|Возвращает число измерений в массиве.|
|[ColeSafeArray::GetElement](#getelement)|Извлекает один элемент безопасного массива.|
|[ColeSafeArray::GetElemSize](#getelemsize)|Возвращает размер, в байтах, одного элемента в безопасном массиве.|
|[ColeSafeArray::GetLBound](#getlbound)|Возвращает нижнюю границу для любого измерения безопасного массива.|
|[ColeSafeArray::GetOneDimSize](#getonedimsize)|Возвращает количество элементов в одномерном `COleSafeArray` объекте.|
|[ColeSafeArray::GetUBound](#getubound)|Возвращает верхнюю границу для любого измерения безопасного массива.|
|[ColeSafeArray::Lock](#lock)|Приравливывает количество блокировки массива и помещает указатель на данные массива в дескрипторе массива.|
|[ColeSafeArray::PtrOfIndex](#ptrofindex)|Возвращает указатель на индексированный элемент.|
|[ColeSafeArray::PutElement](#putelement)|Помещает в массив один элемент.|
|[ColeSafeArray::Redim](#redim)|Изменяет наименее значимую (самую правой) границу безопасного массива.|
|[ColeSafeArray::ResizeoneDim](#resizeonedim)|Изменяет количество элементов в `COleSafeArray` одномерном объекте.|
|[ColeSafeArray::UnaccessData](#unaccessdata)|Декретирует количество блокировки массива и аннулирует указатель, извлеченный `AccessData`.|
|[ColeSafeArray::Разблокировка](#unlock)|Устрашает количество блокировки массива, чтобы он мог быть освобожден или уменьшен.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[COleSafeArray:оператор LPCVARIANT](#operator_lpcvariant)|Доступ к основной `VARIANT` структуре `COleSafeArray` объекта.|
|[COleSafeArray::оператор LPVARIANT](#operator_lpvariant)|Доступ к основной `VARIANT` структуре `COleSafeArray` объекта.|
|[COleSafeArray::оператор](#operator_eq)|Копирует значения в `COleSafeArray` объект`SAFEARRAY` `VARIANT`(, `COleVariant` `COleSafeArray` , или массив).|
|[COleSafeArray::оператор](#operator_eq_eq)|Сравнивает два варианта`SAFEARRAY` `VARIANT`массива (, `COleVariant`или `COleSafeArray` массивы).|
|[COleSafeArray::оператор&lt;&lt;](#operator_lt_lt)|Выводы содержимого `COleSafeArray` объекта в контекст еспатого.|

## <a name="remarks"></a>Примечания

`COleSafeArray`вытекает из `VARIANT` структуры OLE. Функции `SAFEARRAY` членов OLE `COleSafeArray`доступны через, а также набор функций членов, специально предназначенных для одномерных массивов байтов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="colesafearrayaccessdata"></a><a name="accessdata"></a>ColeSafeArray::AccessData

Извлекает указатель на данные массива.

```cpp
void AccessData(void** ppvData);
```

### <a name="parameters"></a>Параметры

*ppvData*<br/>
Указатель указателя на указатель на данные массива.

### <a name="remarks"></a>Примечания

При ошибке функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException.](../../mfc/reference/coleexception-class.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

## <a name="colesafearrayallocdata"></a><a name="allocdata"></a>COleSafeArray::AllocData

Выделяет память для безопасного массива.

```cpp
void AllocData();
```

### <a name="remarks"></a>Примечания

При ошибке функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException.](../../mfc/reference/coleexception-class.md)

## <a name="colesafearrayallocdescriptor"></a><a name="allocdescriptor"></a>ColeSafeArray::АллокДескриптор

Выделяет память для дескриптора безопасного массива.

```cpp
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>Параметры

*dwDims*<br/>
Количество размеров в безопасном массиве.

### <a name="remarks"></a>Примечания

При ошибке функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException.](../../mfc/reference/coleexception-class.md)

## <a name="colesafearrayattach"></a><a name="attach"></a>ColeSafeArray::Attach

Предоставляет объекту контроль над `VARIANT` данными `COleSafeArray` в существующем массиве.

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Параметры

*varSrc*<br/>
Объект `VARIANT` . Параметр *varSrc* должен иметь [VT_ARRAY](/windows/win32/api/wtypes/ne-wtypes-varenum)VARTYPE.

### <a name="remarks"></a>Примечания

Тип `VARIANT`источника установлен на VT_EMPTY. Эта функция очищает текущие данные массива, если таковые имеются.

### <a name="example"></a>Пример

  Смотрите пример [COleSafeArray::AccessData](#accessdata).

## <a name="colesafearrayclear"></a><a name="clear"></a>ColeSafeArray::Clear

Очищает безопасный массив.

```cpp
void Clear();
```

### <a name="remarks"></a>Примечания

Функция очищает безопасный массив, `VARTYPE` устанавливая объект на VT_EMPTY. Текущее содержимое освобождается и массив освобождается.

## <a name="colesafearraycolesafearray"></a><a name="colesafearray"></a>ColeSafeArray::COleSafeArray

Формирует объект `COleSafeArray`.

```
COleSafeArray();

COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);

COleSafeArray(const COleSafeArray& saSrc);
COleSafeArray(const VARIANT& varSrc);
COleSafeArray(LPCVARIANT pSrc);
COleSafeArray(const COleVariant& varSrc);
```

### <a name="parameters"></a>Параметры

*saSrc*<br/>
Существующий `COleSafeArray` объект `SAFEARRAY` или для копирования `COleSafeArray` в новый объект.

*vtSrc*<br/>
VARTYPE нового `COleSafeArray` объекта.

*psaSrc*<br/>
Указатель на `SAFEARRAY` скопированный в `COleSafeArray` новый объект указатель.

*varSrc*<br/>
Существующий `VARIANT` `COleVariant` или объект, который должен `COleSafeArray` быть скопирован в новый объект.

*Psrc*<br/>
Указатель на `VARIANT` объект, который должен быть `COleSafeArray` скопирован в новый объект.

### <a name="remarks"></a>Примечания

Все эти конструкторы создают `COleSafeArray` новые объекты. Если параметра нет, `COleSafeArray` создается пустой объект (VT_EMPTY). Если скопирован из другого массива, который `COleSafeArray`VARTYPE известен неявно (a, `COleVariant`, или), `VARIANT`VARTYPE исходного массива сохраняется и не требуется указывать. `COleSafeArray` Если `COleSafeArray` он скопирован из другого массива, о каком VARTYPE не известен (),`SAFEARRAY`VARTYPE должен быть указан в параметре *vtSrc.*

При ошибке функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException.](../../mfc/reference/coleexception-class.md)

## <a name="colesafearraycopy"></a><a name="copy"></a>ColeSafeArray::Copy

Создает копию существующего безопасного массива.

```cpp
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>Параметры

*ppsa*<br/>
Указатель на место, в котором можно вернуть новый дескриптор массива.

### <a name="remarks"></a>Примечания

При ошибке функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException.](../../mfc/reference/coleexception-class.md)

## <a name="colesafearraycreate"></a><a name="create"></a>ColeSafeArray::Создание

Выделяет и инициализирует данные для массива.

```cpp
void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    DWORD* rgElements);

void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    SAFEARRAYBOUND* rgsabounds);
```

### <a name="parameters"></a>Параметры

*vtSrc*<br/>
Базовый тип массива (т.е. VARTYPE каждого элемента массива). VARTYPE ограничен подмножеством типов вариантов. Ни VT_ARRAY, ни VT_BYREF флаг не могут быть установлены. VT_EMPTY и VT_NULL не являются действительными базовыми типами для массива. Все остальные типы являются законными.

*dwDims*<br/>
Количество измерений в массиве. Это может быть изменено после создания массива с [помощью Redim.](#redim)

*rgElements*<br/>
Указатель на массив количества элементов для каждого измерения в массиве.

*rgsabounds*<br/>
Указатель на вектор границ (по одному для каждого измерения) для выделения для массива.

### <a name="remarks"></a>Примечания

Эта функция позволит очистить текущие данные массива, если это необходимо. При ошибке функция бросает [CMemoryException.](../../mfc/reference/cmemoryexception-class.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraycreateonedim"></a><a name="createonedim"></a>ColeSafeArray::CreateOneDim

Создает новый одномерный `COleSafeArray` объект.

```cpp
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>Параметры

*vtSrc*<br/>
Базовый тип массива (т.е. VARTYPE каждого элемента массива).

*dwElements*<br/>
Количество элементов в массиве. Это может быть изменено после создания массива с [помощью ResizeOneDim](#resizeonedim).

*pvSrcData*<br/>
Указатель на данные для копирования в массив.

*nLBound*<br/>
Нижняя граница массива.

### <a name="remarks"></a>Примечания

Функция выделяет и инициализирует данные для массива, копируя указанные данные, если указатель *pvSrcData* не является NULL.

При ошибке функция бросает [CMemoryException.](../../mfc/reference/cmemoryexception-class.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

## <a name="colesafearraydestroy"></a><a name="destroy"></a>ColeSafeArray::Destroy

Уничтожает существующий дескриптор массива и все данные в массиве.

```cpp
void Destroy();
```

### <a name="remarks"></a>Примечания

Если объекты хранятся в массиве, каждый объект освобождается. При ошибке функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException.](../../mfc/reference/coleexception-class.md)

## <a name="colesafearraydestroydata"></a><a name="destroydata"></a>ColeSafeArray::DestroyData

Уничтожает все данные в безопасном массиве.

```cpp
void DestroyData();
```

### <a name="remarks"></a>Примечания

Если объекты хранятся в массиве, каждый объект освобождается. При ошибке функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException.](../../mfc/reference/coleexception-class.md)

## <a name="colesafearraydestroydescriptor"></a><a name="destroydescriptor"></a>ColeSafeArray::DэстройДескриптор

Уничтожает дескриптор безопасного массива.

```cpp
void DestroyDescriptor();
```

### <a name="remarks"></a>Примечания

При ошибке функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException.](../../mfc/reference/coleexception-class.md)

## <a name="colesafearraydetach"></a><a name="detach"></a>ColeSafeArray: :Detach

Отсеивает данные `VARIANT` с `COleSafeArray` объекта.

```
VARIANT Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Базовое `VARIANT` значение объекта. `COleSafeArray`

### <a name="remarks"></a>Примечания

Функция отсоединяет данные в безопасном массиве, установив VARTYPE объекта на VT_EMPTY. Это ответственность абонента, чтобы освободить массив, позвонив функции Windows [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear).

При ошибке функция бросает [COleException.](../../mfc/reference/coleexception-class.md)

### <a name="example"></a>Пример

  Смотрите пример [COleSafeArray::PutElement](#putelement).

## <a name="colesafearraygetbytearray"></a><a name="getbytearray"></a>ColeSafeArray::GetByteArray

Копирует содержимое безопасного массива `CByteArray`в .

```cpp
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>Параметры

*Байт*<br/>
Ссылка на объект [CByteArray.](../../mfc/reference/cbytearray-class.md)

## <a name="colesafearraygetdim"></a><a name="getdim"></a>ColeSafeArray::GetDim

Возвращает количество измерений `COleSafeArray` в объекте.

```
DWORD GetDim();
```

### <a name="return-value"></a>Возвращаемое значение

Количество размеров в безопасном массиве.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraygetelement"></a><a name="getelement"></a>ColeSafeArray::GetElement

Извлекает один элемент безопасного массива.

```cpp
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Параметры

*rgIndices*<br/>
Указатель на массив индексов для каждого измерения массива.

*pvData*<br/>
Указатель на место для размещения элемента массива.

### <a name="remarks"></a>Примечания

Эта функция автоматически вызывает `SafeArrayLock` `SafeArrayUnlock` функции окон и до и после извлечения элемента. Если элемент данных является строкой, объектом или вариантом, функция копирует элемент правильным образом. Параметр *pvData* должен указывать на достаточно большой буфер, чтобы содержать элемент.

При ошибке функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException.](../../mfc/reference/coleexception-class.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

## <a name="colesafearraygetelemsize"></a><a name="getelemsize"></a>ColeSafeArray::GetElemSize

Извлекает размер элемента `COleSafeArray` в объект.

```
DWORD GetElemSize();
```

### <a name="return-value"></a>Возвращаемое значение

Размер, в байтах, элементов безопасного массива.

## <a name="colesafearraygetlbound"></a><a name="getlbound"></a>ColeSafeArray::GetLBound

Возвращает нижнюю границу для `COleSafeArray` любого измерения объекта.

```cpp
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>Параметры

*dwDim*<br/>
Измерение массива, для которого можно получить нижнюю границу.

*pLBound*<br/>
Указатель на место, чтобы вернуть нижнюю границу.

### <a name="remarks"></a>Примечания

При ошибке функция бросает [COleException.](../../mfc/reference/coleexception-class.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

## <a name="colesafearraygetonedimsize"></a><a name="getonedimsize"></a>ColeSafeArray::GetOneDimSize

Возвращает количество элементов в одномерном `COleSafeArray` объекте.

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в одномерном безопасном массиве.

### <a name="example"></a>Пример

  Смотрите пример [для COleSafeArray::CreateOneDim](#createonedim).

## <a name="colesafearraygetubound"></a><a name="getubound"></a>ColeSafeArray::GetUBound

Возвращает верхнюю границу для любого измерения безопасного массива.

```cpp
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>Параметры

*dwDim*<br/>
Измерение массива, для которого можно получить верхнюю границу.

*pUBound*<br/>
Указатель на место, чтобы вернуть верхнюю границу.

### <a name="remarks"></a>Примечания

При ошибке функция бросает [COleException.](../../mfc/reference/coleexception-class.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

## <a name="colesafearraylock"></a><a name="lock"></a>ColeSafeArray::Lock

Приравливывает количество блокировки массива и размещает указатель на данные массива в дескрипторе массива.

```cpp
void Lock();
```

### <a name="remarks"></a>Примечания

По ошибке, он бросает [COleException](../../mfc/reference/coleexception-class.md).

Указатель в дескрипторе массива `Unlock` действителен до тех пор, пока не будет вызван. Вызовы `Lock` могут быть вложены; требуется `Unlock` равное количество вызовов.

Массив не может быть удален, пока он заблокирован.

## <a name="colesafearrayoperator-lpcvariant"></a><a name="operator_lpcvariant"></a>COleSafeArray:оператор LPCVARIANT

Вызовите этого оператора литья, чтобы получить доступ к базовой `VARIANT` структуре для этого `COleSafeArray` объекта.

```
operator LPCVARIANT() const;
```

## <a name="colesafearrayoperator-lpvariant"></a><a name="operator_lpvariant"></a>COleSafeArray::оператор LPVARIANT

Вызовите этого оператора литья, чтобы получить доступ к базовой `VARIANT` структуре для этого `COleSafeArray` объекта.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Примечания

Обратите внимание, что `VARIANT` изменение значения в структуре, доступ к которой будет `COleSafeArray` добавлен указателем этой функции, изменит значение этого объекта.

## <a name="colesafearrayoperator-"></a><a name="operator_eq"></a>COleSafeArray::оператор

Эти перегруженные операторы назначения копируют `COleSafeArray` исходное значение в этом объекте.

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>Примечания

Краткое описание каждого оператора:

- **оператор** *(saSrc* **)** Копирует существующий `COleSafeArray` объект в этот объект.

- **оператор No** *(varSrc* **)** Копирует `VARIANT` существующий `COleVariant` или массив в этот объект.

- **оператор** *(pSrc* **)** Копирует `VARIANT` объект массива, доступ к объекту, доступ к нему со *стороны pSrc.*

## <a name="colesafearrayoperator-"></a><a name="operator_eq_eq"></a>COleSafeArray::оператор

Этот оператор сравнивает два`SAFEARRAY` `VARIANT`массива (, `COleVariant`, или `COleSafeArray` массивы) и возвращает ненулевой, если они равны; в противном случае 0.

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>Примечания

Два массива равны, если они имеют равное количество измерений, равный размер в каждом измерении и равные значения элементов.

## <a name="colesafearrayoperator-ltlt"></a><a name="operator_lt_lt"></a>COleSafeArray::оператор&lt;&lt;

Оператор `COleSafeArray` вставки (<<) поддерживает диагностический `COleSafeArray` демпинг и хранение объекта в архиве.

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

## <a name="colesafearrayptrofindex"></a><a name="ptrofindex"></a>ColeSafeArray::PtrOfIndex

Возвращает указатель элемента, указанного значениями индекса.

```cpp
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>Параметры

*rgIndices*<br/>
Массив значений индекса, которые идентифицируют элемент массива. Все индексы элемента должны быть указаны.

*ppvData*<br/>
На веревке указатель на элемент, определенный значениями в *rgIndices.*

## <a name="colesafearrayputelement"></a><a name="putelement"></a>ColeSafeArray::PutElement

Помещает в массив один элемент.

```cpp
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Параметры

*rgIndices*<br/>
Указатель на массив индексов для каждого измерения массива.

*pvData*<br/>
Указатель на данные, которые требуется поместить в массив. VT_DISPATCH, VT_UNKNOWN и VT_BSTR типами вариантов являются указатели и не требуют другого уровня косвенности.

### <a name="remarks"></a>Примечания

Эта функция автоматически вызывает функции Windows [SafeArrayLock](/windows/win32/api/oleauto/nf-oleauto-safearraylock) и [SafeArrayUnlock](/windows/win32/api/oleauto/nf-oleauto-safearrayunlock) до и после назначения элемента. Если строка, объект или вариант являются элементом данных, функция выполняет правильное копирование, а если существующим элементом — правильное удаление.

Обратите внимание, для массива можно настроить несколько блокировок, поэтому вы можете поместить в него элементы, недоступные для других операций.

При ошибке функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) или [COleException.](../../mfc/reference/coleexception-class.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

## <a name="colesafearrayredim"></a><a name="redim"></a>ColeSafeArray::Redim

Изменяет наименее значимую (самую правой) границу безопасного массива.

```cpp
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>Параметры

*psaboundНовые*<br/>
Указатель на новую структуру связанного безопасного массива, содержащую новую связанную массивную структуру. Изменяются только наименее значительное измерение массива.

### <a name="remarks"></a>Примечания

При ошибке функция бросает [COleException.](../../mfc/reference/coleexception-class.md)

## <a name="colesafearrayresizeonedim"></a><a name="resizeonedim"></a>ColeSafeArray::ResizeoneDim

Изменяет количество элементов в `COleSafeArray` одномерном объекте.

```cpp
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>Параметры

*dwElements*<br/>
Количество элементов в одномерном безопасном массиве.

### <a name="remarks"></a>Примечания

При ошибке функция бросает [COleException.](../../mfc/reference/coleexception-class.md)

### <a name="example"></a>Пример

  Смотрите пример [для COleSafeArray::CreateOneDim](#createonedim).

## <a name="colesafearrayunaccessdata"></a><a name="unaccessdata"></a>ColeSafeArray::UnaccessData

Декретирует количество блокировки массива и аннулирует указатель, извлеченный `AccessData`.

```cpp
void UnaccessData();
```

### <a name="remarks"></a>Примечания

При ошибке функция бросает [COleException.](../../mfc/reference/coleexception-class.md)

### <a name="example"></a>Пример

  Смотрите пример [COleSafeArray::AccessData](#accessdata).

## <a name="colesafearrayunlock"></a><a name="unlock"></a>ColeSafeArray::Разблокировка

Устрашает количество блокировки массива, чтобы он мог быть освобожден или уменьшен.

```cpp
void Unlock();
```

### <a name="remarks"></a>Примечания

Эта функция вызывается после завершения доступа к данным в массиве. По ошибке, он бросает [COleException](../../mfc/reference/coleexception-class.md).

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleVariant](../../mfc/reference/colevariant-class.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)<br/>
[Класс CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
