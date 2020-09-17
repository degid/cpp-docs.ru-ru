---
title: Класс CAtlArray
ms.date: 11/04/2016
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::Copy
- ATLCOLL/ATL::FreeExtra
- ATLCOLL/ATL::GetAt
- ATLCOLL/ATL::GetCount
- ATLCOLL/ATL::GetData
- ATLCOLL/ATL::InsertArrayAt
- ATLCOLL/ATL::InsertAt
- ATLCOLL/ATL::IsEmpty
- ATLCOLL/ATL::RemoveAll
- ATLCOLL/ATL::RemoveAt
- ATLCOLL/ATL::SetAt
- ATLCOLL/ATL::SetAtGrow
- ATLCOLL/ATL::SetCount
- ATLCOLL/ATL::INARGTYPE
- ATLCOLL/ATL::OUTARGTYPE
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
ms.openlocfilehash: c4a4cd509a5d3078c6587ba7b29179a68912a258
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833846"
---
# <a name="catlarray-class"></a>Класс CAtlArray

Этот класс реализует объект Array.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```

### <a name="parameters"></a>Параметры

*&*<br/>
Тип данных для сохранения в массиве.

*етраитс*<br/>
Код, используемый для копирования или перемещения элементов.

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

|Функция|Описание|
|-|-|
|[Добавление](#add)|Вызовите этот метод, чтобы добавить элемент в объект массива.|
|[Добавить](#append)|Вызовите этот метод, чтобы добавить содержимое одного массива в конец другого.|
|[AssertValid](#assertvalid)|Вызовите этот метод, чтобы убедиться, что объект массива является допустимым.|
|[CAtlArray](#catlarray)|Конструктор.|
|[~ CAtlArray](#dtor)|Деструктор|
|[Копировать](#copy)|Вызовите этот метод, чтобы скопировать элементы одного массива в другой.|
|[фриекстра](#freeextra)|Вызовите этот метод, чтобы удалить все пустые элементы из массива.|
|[GetAt](#getat)|Вызовите этот метод, чтобы получить один элемент из объекта массива.|
|[GetCount](#getcount)|Вызовите этот метод, чтобы получить количество элементов, хранящихся в массиве.|
|[GetData](#getdata)|Вызовите этот метод, чтобы вернуть указатель на первый элемент в массиве.|
|[инсертаррайат](#insertarrayat)|Вызовите этот метод, чтобы вставить один массив в другой.|
|[инсертат](#insertat)|Вызовите этот метод, чтобы вставить новый элемент (или несколько копий элемента) в объект массива.|
|[IsEmpty](#isempty)|Вызовите этот метод, чтобы проверить, пуст ли массив.|
|[RemoveAll](#removeall)|Вызовите этот метод, чтобы удалить все элементы из объекта Array.|
|[RemoveAt](#removeat)|Вызовите этот метод, чтобы удалить один или несколько элементов из массива.|
|[SetAt](#setat)|Вызовите этот метод, чтобы задать значение элемента в объекте массива.|
|[сетатгров](#setatgrow)|Вызовите этот метод, чтобы задать значение элемента в объекте массива, расширяя массив по мере необходимости.|
|[сеткаунт](#setcount)|Вызовите этот метод, чтобы задать размер объекта массива.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[Оператор &#91;&#93;](#operator_at)|Вызовите этот оператор, чтобы вернуть ссылку на элемент в массиве.|

### <a name="typedefs"></a>Определения типов

|Typedef|Описание|
|-|-|
|[инаргтипе](#inargtype)|Тип данных, используемый для добавления элементов в массив.|
|[аутаргтипе](#outargtype)|Тип данных, используемый для получения элементов из массива.|

## <a name="remarks"></a>Примечания

`CAtlArray` предоставляет методы для создания массива элементов определяемого пользователем типа и управления им. Несмотря на то, что аналогично стандартным массивам C, `CAtlArray` объект может динамически сжиматься и увеличиваться по мере необходимости. Индекс массива всегда начинается в позиции 0, а верхняя граница может быть фиксированной или разрешена для расширения по мере добавления новых элементов.

Для массивов с небольшим числом элементов можно использовать класс ATL [ксимплеаррай](../../atl/reference/csimplearray-class.md) .

`CAtlArray` тесно связан с `CArray` классом MFC и будет работать в проекте MFC, хотя и без поддержки сериализации.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** атлколл.h

## <a name="catlarrayadd"></a><a name="add"></a> CAtlArray:: Add

Вызовите этот метод, чтобы добавить элемент в объект массива.

```cpp
size_t Add(INARGTYPE element);
size_t Add();
```

### <a name="parameters"></a>Параметры

*дерев*<br/>
Элемент, добавляемый в массив.

### <a name="return-value"></a>Возвращаемое значение

Возвращает индекс добавленного элемента.

### <a name="remarks"></a>Примечания

Новый элемент добавляется в конец массива. Если элемент не указан, добавляется пустой элемент; то есть размер массива увеличивается, как будто был добавлен реальный элемент. В случае сбоя операции [атлсров](debugging-and-error-reporting-global-functions.md#atlthrow) вызывается с аргументом E_OUTOFMEMORY.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]

## <a name="catlarrayappend"></a><a name="append"></a> CAtlArray:: Append

Вызовите этот метод, чтобы добавить содержимое одного массива в конец другого.

```cpp
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Параметры

*асрк*<br/>
Добавляемый массив.

### <a name="return-value"></a>Возвращаемое значение

Возвращает индекс первого добавленного элемента.

### <a name="remarks"></a>Примечания

Элементы в переданном массиве добавляются в конец существующего массива. При необходимости будет выделена память для размещения новых элементов.

Массивы должны иметь один и тот же тип, и невозможно добавить массив к самому себе.

В отладочных сборках создается исключение АТЛАССЕРТ, если аргумент не является `CAtlArray` допустимым массивом или если *АСРК* ссылается на один и тот же объект. В сборках выпуска недопустимые аргументы могут привести к непредсказуемому поведению.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]

## <a name="catlarrayassertvalid"></a><a name="assertvalid"></a> CAtlArray:: AssertValid

Вызовите этот метод, чтобы убедиться, что объект массива является допустимым.

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>Примечания

Если объект массива является недопустимым, АТЛАССЕРТ выдаст утверждение. Этот метод доступен, только если определен _DEBUG.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]

## <a name="catlarraycatlarray"></a><a name="catlarray"></a> CAtlArray:: CAtlArray

Конструктор.

```cpp
CAtlArray() throw();
```

### <a name="remarks"></a>Примечания

Инициализирует объект массива.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]

## <a name="catlarraycatlarray"></a><a name="dtor"></a> CAtlArray:: ~ CAtlArray

Деструктор

```cpp
~CAtlArray() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все ресурсы, используемые объектом Array.

## <a name="catlarraycopy"></a><a name="copy"></a> CAtlArray:: Copy

Вызовите этот метод, чтобы скопировать элементы одного массива в другой.

```cpp
void Copy(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Параметры

*асрк*<br/>
Источник элементов для копирования в массив.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы перезаписать элементы одного массива элементами другого массива. При необходимости будет выделена память для размещения новых элементов. Невозможно скопировать элементы массива в сам себя.

Если существующее содержимое массива должно быть сохранены, используйте вместо него [CAtlArray:: Append](#append) .

В отладочных сборках создается исключение АТЛАССЕРТ, если существующий `CAtlArray` объект является недопустимым, или если *АСРК* ссылается на тот же объект. В сборках выпуска недопустимые аргументы могут привести к непредсказуемому поведению.

> [!NOTE]
> `CAtlArray::Copy` не поддерживает массивы, состоящие из элементов, созданных с помощью класса [каутоптр](../../atl/reference/cautoptr-class.md) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]

## <a name="catlarrayfreeextra"></a><a name="freeextra"></a> CAtlArray:: Фриекстра

Вызовите этот метод, чтобы удалить все пустые элементы из массива.

```cpp
void FreeExtra() throw();
```

### <a name="remarks"></a>Примечания

Все пустые элементы удаляются, но размер и верхняя граница массива остаются неизменными.

В отладочных сборках создается исключение АТЛАССЕРТ, если объект CAtlArray является недопустимым, или если размер массива превысит максимальный.

## <a name="catlarraygetat"></a><a name="getat"></a> CAtlArray:: GetAt

Вызовите этот метод, чтобы извлечь один элемент из объекта массива.

```cpp
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Значение индекса возвращаемого элемента массива.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на требуемый элемент массива.

### <a name="remarks"></a>Примечания

В отладочных сборках создается исключение АТЛАССЕРТ, если *IElement* превышает число элементов в массиве. В сборках выпуска недопустимый аргумент может привести к непредсказуемому поведению.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]

## <a name="catlarraygetcount"></a><a name="getcount"></a> CAtlArray:: NOCOUNT

Вызовите этот метод, чтобы получить количество элементов, хранящихся в массиве.

```cpp
size_t GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов, хранящихся в массиве.

### <a name="remarks"></a>Примечания

Как первый элемент массива находится в позиции 0, значение, возвращаемое, `GetCount` всегда равно 1 больше, чем самый крупный индекс.

### <a name="example"></a>Пример

См. пример для [CAtlArray:: GetAt](#getat).

## <a name="catlarraygetdata"></a><a name="getdata"></a> CAtlArray:: GetData

Вызовите этот метод, чтобы вернуть указатель на первый элемент в массиве.

```cpp
E* GetData() throw();
const E* GetData() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на место в памяти, в котором хранится первый элемент в массиве. Если нет доступных элементов, возвращается значение NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]

## <a name="catlarrayinargtype"></a><a name="inargtype"></a> CAtlArray:: ИНАРГТИПЕ

Тип данных, используемый для добавления элементов в массив.

```cpp
typedef ETraits::INARGTYPE INARGTYPE;
```

## <a name="catlarrayinsertarrayat"></a><a name="insertarrayat"></a> CAtlArray:: Инсертаррайат

Вызовите этот метод, чтобы вставить один массив в другой.

```cpp
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```

### <a name="parameters"></a>Параметры

*истарт*<br/>
Индекс, по которому будет вставлен массив.

*панев*<br/>
Вставляемый массив.

### <a name="remarks"></a>Примечания

Элементы из массива *ПАНЕВ* копируются в объект Array, начиная с element *истарт*. Существующие элементы массива перемещаются, чтобы избежать переписывания.

В отладочных сборках создается исключение АТЛАССЕРТ `CAtlArray` , если объект является недопустимым, или если указатель *ПАНЕВ* имеет значение null или является недопустимым.

> [!NOTE]
> `CAtlArray::InsertArrayAt` не поддерживает массивы, состоящие из элементов, созданных с помощью класса [каутоптр](../../atl/reference/cautoptr-class.md) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]

## <a name="catlarrayinsertat"></a><a name="insertat"></a> CAtlArray:: Инсертат

Вызовите этот метод, чтобы вставить новый элемент (или несколько копий элемента) в объект массива.

```cpp
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Индекс, по которому вставляются элемент или элементы.

*дерев*<br/>
Значение элемента или элементов для вставки.

*нкаунт*<br/>
Число добавляемых элементов.

### <a name="remarks"></a>Примечания

Вставляет в массив один или несколько элементов, начиная с индекса *IElement*. Существующие элементы перемещаются, чтобы избежать переписывания.

В отладочных сборках создается исключение АТЛАССЕРТ, если `CAtlArray` объект является недопустимым, число добавляемых элементов равно нулю, либо объединенное число элементов слишком велико для массива, содержащегося в массиве. В розничных сборках передача недопустимых параметров может привести к непредсказуемым результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]

## <a name="catlarrayisempty"></a><a name="isempty"></a> CAtlArray:: IsEmpty

Вызовите этот метод, чтобы проверить, пуст ли массив.

```cpp
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если массив пуст, и false в противном случае.

### <a name="remarks"></a>Примечания

Массив считается пустым, если он не содержит элементов. Поэтому, даже если массив содержит пустые элементы, он не пуст.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]

## <a name="catlarrayoperator-"></a><a name="operator_at"></a> CAtlArray::operator []

Вызовите этот оператор, чтобы вернуть ссылку на элемент в массиве.

```cpp
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Значение индекса возвращаемого элемента массива.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на требуемый элемент массива.

### <a name="remarks"></a>Примечания

Выполняет аналогичную функцию для [CAtlArray:: GetAt](#getat). В отличие от класса MFC [CArray](../../mfc/reference/carray-class.md)этот оператор нельзя использовать в качестве замены для [CAtlArray:: SetAt](#setat).

В отладочных сборках создается исключение АТЛАССЕРТ, если *IElement* превышает общее число элементов в массиве. В розничных сборках недопустимый параметр может привести к непредсказуемым результатам.

## <a name="catlarrayoutargtype"></a><a name="outargtype"></a> CAtlArray:: АУТАРГТИПЕ

Тип данных, используемый для получения элементов из массива.

```cpp
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```

## <a name="catlarrayremoveall"></a><a name="removeall"></a> CAtlArray:: RemoveAll

Вызовите этот метод, чтобы удалить все элементы из объекта Array.

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>Примечания

Удаляет все элементы из объекта Array.

Этот метод вызывает [CAtlArray:: сеткаунт](#setcount) для изменения размера массива и последующего освобождения выделенной памяти.

### <a name="example"></a>Пример

См. пример для [CAtlArray:: IsEmpty](#isempty).

## <a name="catlarrayremoveat"></a><a name="removeat"></a> CAtlArray:: RemoveAt

Вызовите этот метод, чтобы удалить один или несколько элементов из массива.

```cpp
void RemoveAt(size_t iElement, size_t nCount = 1);
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Индекс первого удаляемого элемента.

*нкаунт*<br/>
Число удаляемых элементов.

### <a name="remarks"></a>Примечания

Удаляет один или несколько элементов из массива. Все оставшиеся элементы сдвигаются вниз. Верхняя граница уменьшается, но память не освобождается до тех пор, пока не будет выполнен вызов [CAtlArray:: фриекстра](#freeextra) .

В отладочных сборках возникнет исключение АТЛАССЕРТ, если `CAtlArray` объект является недопустимым, или если суммарная сумма значений *IElement* и *нкаунт* превышает общее число элементов в массиве. В розничных сборках недопустимые параметры могут привести к непредсказуемым результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]

## <a name="catlarraysetat"></a><a name="setat"></a> CAtlArray:: SetAt

Вызовите этот метод, чтобы задать значение элемента в объекте массива.

```cpp
void SetAt(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Индекс, указывающий на заданный элемент массива.

*дерев*<br/>
Новое значение указанного элемента.

### <a name="remarks"></a>Примечания

В отладочных сборках создается исключение АТЛАССЕРТ, если *IElement* превышает число элементов в массиве. В розничных сборках недопустимый параметр может привести к непредсказуемым результатам.

### <a name="example"></a>Пример

См. пример для [CAtlArray:: GetAt](#getat).

## <a name="catlarraysetcount"></a><a name="setcount"></a> CAtlArray:: Сеткаунт

Вызовите этот метод, чтобы задать размер объекта массива.

```cpp
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```

### <a name="parameters"></a>Параметры

*нневсизе*<br/>
Требуемый размер массива.

*нгровби*<br/>
Значение, используемое для определения размера буфера. Значение-1 вызывает использование внутреннего вычисляемого значения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если размер массива успешно изменен; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Размер массива можно увеличить или уменьшить. При увеличении числа лишних пустых элементов добавляются в массив. При уменьшении размера элементы с большим индексом будут удалены и освобождены.

Используйте этот метод, чтобы задать размер массива перед его использованием. Если `SetCount` не используется, процесс добавления элементов (и последующее выделение памяти) снизит производительность и фрагментацию памяти.

### <a name="example"></a>Пример

См. пример для [CAtlArray:: GetData](#getdata).

## <a name="catlarraysetatgrow"></a><a name="setatgrow"></a> CAtlArray:: Сетатгров

Вызовите этот метод, чтобы задать значение элемента в объекте массива, расширяя массив по мере необходимости.

```cpp
void SetAtGrow(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Индекс, указывающий на заданный элемент массива.

*дерев*<br/>
Новое значение указанного элемента.

### <a name="remarks"></a>Примечания

Заменяет значение элемента, на которое указывает индекс. Если *IElement* больше текущего размера массива, массив автоматически увеличивается с помощью вызова [CAtlArray:: сеткаунт](#setcount). В отладочных сборках будет вызвано исключение АТЛАССЕРТ, если `CAtlArray` объект является недопустимым. В розничных сборках недопустимые параметры могут привести к непредсказуемым результатам.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]

## <a name="see-also"></a>См. также раздел

[Пример Ммкссварм](../../overview/visual-cpp-samples.md)<br/>
[Пример Динамикконсумер](../../overview/visual-cpp-samples.md)<br/>
[Образец UpdatePV](../../overview/visual-cpp-samples.md)<br/>
[Образец бегущей строки](../../overview/visual-cpp-samples.md)<br/>
[Класс CArray](../../mfc/reference/carray-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
