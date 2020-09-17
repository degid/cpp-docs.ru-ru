---
title: Класс CArray
ms.date: 11/04/2016
f1_keywords:
- CArray
- AFXTEMPL/CArray
- AFXTEMPL/CArray::CArray
- AFXTEMPL/CArray::Add
- AFXTEMPL/CArray::Append
- AFXTEMPL/CArray::Copy
- AFXTEMPL/CArray::ElementAt
- AFXTEMPL/CArray::FreeExtra
- AFXTEMPL/CArray::GetAt
- AFXTEMPL/CArray::GetCount
- AFXTEMPL/CArray::GetData
- AFXTEMPL/CArray::GetSize
- AFXTEMPL/CArray::GetUpperBound
- AFXTEMPL/CArray::InsertAt
- AFXTEMPL/CArray::IsEmpty
- AFXTEMPL/CArray::RemoveAll
- AFXTEMPL/CArray::RemoveAt
- AFXTEMPL/CArray::SetAt
- AFXTEMPL/CArray::SetAtGrow
- AFXTEMPL/CArray::SetSize
helpviewer_keywords:
- CArray [MFC], CArray
- CArray [MFC], Add
- CArray [MFC], Append
- CArray [MFC], Copy
- CArray [MFC], ElementAt
- CArray [MFC], FreeExtra
- CArray [MFC], GetAt
- CArray [MFC], GetCount
- CArray [MFC], GetData
- CArray [MFC], GetSize
- CArray [MFC], GetUpperBound
- CArray [MFC], InsertAt
- CArray [MFC], IsEmpty
- CArray [MFC], RemoveAll
- CArray [MFC], RemoveAt
- CArray [MFC], SetAt
- CArray [MFC], SetAtGrow
- CArray [MFC], SetSize
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
ms.openlocfilehash: f73666f3a20488d14a82b7c56d682f3f5b2386df
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87195178"
---
# <a name="carray-class"></a>Класс CArray

Поддерживает массивы, которые подобны массивам C, но могут динамически уменьшаться и увеличиваться по мере необходимости.

## <a name="syntax"></a>Синтаксис

```
template <class TYPE, class ARG_TYPE = const TYPE&>
class CArray : public CObject
```

#### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип объектов, хранящихся в массиве. *Тип* — это параметр, возвращаемый методом `CArray` .

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип аргумента, который используется для доступа к объектам, хранящимся в массиве. Часто является ссылкой на *тип*. *ARG_TYPE* — это параметр, который передается в `CArray` .

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CArray:: CArray](#carray)|Создает пустой массив.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CArray:: Add](#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|
|[CArray:: Append](#append)|Добавляет еще один массив в массив; При необходимости расширяет массив|
|[CArray:: Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[CArray:: ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[CArray:: Фриекстра](#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|
|[CArray:: GetAt](#getat)|Возвращает значение по указанному индексу.|
|[CArray:: NOCOUNT](#getcount)|Возвращает количество элементов в массиве.|
|[CArray:: GetData](#getdata)|Разрешает доступ к элементам в массиве. Может иметь значение NULL.|
|[CArray:: DataSize](#getsize)|Возвращает количество элементов в массиве.|
|[CArray:: GetUpperBound](#getupperbound)|Возвращает самый большой допустимый индекс.|
|[CArray:: Инсертат](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|
|[CArray:: IsEmpty](#isempty)|Определяет, является ли массив пустым.|
|[CArray:: RemoveAll](#removeall)|Удаляет все элементы из этого массива.|
|[CArray:: RemoveAt](#removeat)|Удаляет элемент по указанному индексу.|
|[CArray:: SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|
|[CArray:: Сетатгров](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|
|[CArray:: SetSize](#setsize)|Задает число элементов, которые будут храниться в этом массиве.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator&#91;&#93;](#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Примечания

Индексы массивов всегда начинаются в позиции 0. Вы можете решить, следует ли исправить верхнюю границу или разрешить массиву расширять при добавлении элементов после текущей границы. Память выделяется непрерывно с верхней границей, даже если некоторые элементы имеют значение null.

> [!NOTE]
> Большинство методов, которые изменяют размер `CArray` объекта или добавляют в него элементы, используют [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) для перемещения элементов. Это проблема, так как `memcpy_s` не совместима ни с одним из объектов, требующих вызова конструктора. Если элементы в несовместимы `CArray` с `memcpy_s` , необходимо создать новый `CArray` соответствующий размер. Затем необходимо использовать [CArray:: Copy](#copy) и [CArray:: SetAt](#setat) для заполнения нового массива, так как эти методы используют оператор присваивания вместо `memcpy_s` .

Как и в случае с массивом C, время доступа для `CArray` индексированного элемента является константой и не зависит от размера массива.

> [!TIP]
> Перед использованием массива используйте [SetSize](#setsize) , чтобы установить его размер и выделить память для него. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

Если требуется дамп отдельных элементов в массиве, необходимо задать для глубины объекта [CDumpContext](../../mfc/reference/cdumpcontext-class.md) значение 1 или больше.

Некоторые функции элементов этого класса вызывают глобальные вспомогательные функции, которые необходимо настроить для большинства случаев использования `CArray` класса. См. раздел [вспомогательные методы класса коллекций](../../mfc/reference/collection-class-helpers.md) разделов в разделе макросы и глобальные классы MFC.

Наследование класса массива подобно порождению списка.

Дополнительные сведения об использовании `CArray` см. в статье [коллекции](../../mfc/collections.md)статей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CArray`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

## <a name="carrayadd"></a><a name="add"></a>CArray:: Add

Добавляет новый элемент в конец массива, увеличивая массив на 1.

```
INT_PTR Add(ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип аргументов, ссылающихся на элементы в этом массиве.

*невелемент*<br/>
Элемент, добавляемый в этот массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс добавленного элемента.

### <a name="remarks"></a>Примечания

Если параметр [SetSize](#setsize) был использован со `nGrowBy` значением больше 1, может быть выделен дополнительный объем памяти. Однако верхняя граница будет увеличена только до 1.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]

## <a name="carrayappend"></a><a name="append"></a>CArray:: Append

Вызовите эту функцию члена, чтобы добавить содержимое одного массива в конец другого.

```
INT_PTR Append(const CArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов, добавляемых в массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого добавленного элемента.

### <a name="remarks"></a>Примечания

Массивы должны быть одного типа.

При необходимости `Append` может выделить дополнительный объем памяти для размещения элементов, добавляемых в массив.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]

## <a name="carraycarray"></a><a name="carray"></a>CArray:: CArray

Создает пустой массив.

```
CArray();
```

### <a name="remarks"></a>Примечания

Массив растет по одному элементу за раз.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]

## <a name="carraycopy"></a><a name="copy"></a>CArray:: Copy

Используйте эту функцию члена, чтобы скопировать элементы одного массива в другой.

```cpp
void Copy(const CArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов, копируемых в массив.

### <a name="remarks"></a>Примечания

Вызовите эту функцию члена, чтобы перезаписать элементы одного массива элементами другого массива.

`Copy`не освобождает память; Однако при необходимости `Copy` может выделить дополнительный объем памяти для размещения элементов, копируемых в массив.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]

## <a name="carrayelementat"></a><a name="elementat"></a>CArray:: ElementAt

Возвращает временную ссылку на указанный элемент в массиве.

```
TYPE& ElementAt(INT_PTR nIndex);
const TYPE& ElementAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращаемому функцией [GetUpperBound](#getupperbound).

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент массива.

### <a name="remarks"></a>Примечания

Он используется для реализации оператора присваивания слева для массивов.

### <a name="example"></a>Пример

  См. пример для к параметру " [DataSize](#getsize)".

## <a name="carrayfreeextra"></a><a name="freeextra"></a>CArray:: Фриекстра

Освобождает все дополнительные памяти, которые были выделены, пока массив был увеличен.

```cpp
void FreeExtra();
```

### <a name="remarks"></a>Примечания

Эта функция не влияет на размер или верхнюю границу массива.

### <a name="example"></a>Пример

  См. пример для [GetData](#getdata).

## <a name="carraygetat"></a><a name="getat"></a>CArray:: GetAt

Возвращает элемент массива по указанному индексу.

```
TYPE& GetAt(INT_PTR nIndex);
const TYPE& GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов массива.

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращаемому функцией [GetUpperBound](#getupperbound).

### <a name="return-value"></a>Возвращаемое значение

Элемент массива в данный момент по этому индексу.

### <a name="remarks"></a>Примечания

Передача отрицательного значения или значения, превышающего значение, возвращенное, `GetUpperBound` приведет к неудачному утверждению.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]

## <a name="carraygetcount"></a><a name="getcount"></a>CArray:: NOCOUNT

Возвращает число элементов массива.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в массиве.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить количество элементов в массиве. Поскольку индексы отсчитываются от нуля, размер равен 1 больше, чем самый крупный индекс. Вызов этого метода приведет к формированию того же результата, что и метод [CArray:: resize](#getsize) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]

## <a name="carraygetdata"></a><a name="getdata"></a>CArray:: GetData

Используйте эту функцию члена для получения прямого доступа к элементам в массиве.

```
const TYPE* GetData() const;
TYPE* GetData();
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов массива.

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент массива.

### <a name="remarks"></a>Примечания

Если нет доступных элементов, `GetData` возвращает значение null.

Хотя прямой доступ к элементам массива позволяет быстрее работать, следует соблюдать осторожность при вызове `GetData` . любые ошибки, которые вы вносите непосредственно, влияют на элементы массива.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]

## <a name="carraygetsize"></a><a name="getsize"></a>CArray:: DataSize

Возвращает размер массива.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Примечания

Поскольку индексы отсчитываются от нуля, размер равен 1 больше, чем самый крупный индекс. Вызов этого метода приведет к формированию того же результата, что и метод [CArray:: NOCOUNT](#getcount) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]

## <a name="carraygetupperbound"></a><a name="getupperbound"></a>CArray:: GetUpperBound

Возвращает текущую верхнюю границу данного массива.

```
INT_PTR GetUpperBound() const;
```

### <a name="remarks"></a>Примечания

Поскольку индексы массива отсчитываются от нуля, эта функция возвращает значение 1, меньшее `GetSize` .

Условие `GetUpperBound( )` =-1 указывает, что массив не содержит элементов.

### <a name="example"></a>Пример

  См. пример для [CArray:: GetAt](#getat).

## <a name="carrayinsertat"></a><a name="insertat"></a>CArray:: Инсертат

Первая версия `InsertAt` вставляет один элемент (или несколько копий элемента) по указанному индексу в массиве.

```cpp
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CArray* pNewArray);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который может быть больше значения, возвращаемого методом `GetUpperBound` .

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элементов в этом массиве.

*невелемент*<br/>
Элемент, помещаемый в этот массив.

*нкаунт*<br/>
Количество раз, когда этот элемент должен быть вставлен (значение по умолчанию — 1).

*нстартиндекс*<br/>
Целочисленный индекс, который может быть больше значения, возвращаемого функцией [GetUpperBound](#getupperbound).

*пневаррай*<br/>
Другой массив, содержащий элементы для добавления в этот массив.

### <a name="remarks"></a>Примечания

В процессе он смещается (путем увеличения индекса) существующего элемента в этом индексе и сдвигает все элементы над ним.

Вторая версия вставляет все элементы из другой `CArray` коллекции, начиная с позиции *нстартиндекс* .

`SetAt`Функция, напротив, заменяет один указанный элемент массива и не сдвигает ни одного элемента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]

## <a name="carrayisempty"></a><a name="isempty"></a>CArray:: IsEmpty

Определяет, является ли массив пустым.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если массив не содержит элементов; в противном случае — 0.

## <a name="carrayoperator-"></a><a name="operator_at"></a>CArray::operator\[\]

Эти операторы подстрочных индексов являются удобным заменой для функций [SetAt](#setat) и [GetAt](#getat) .

```
TYPE& operator[](int_ptr nindex);
const TYPE& operator[](int_ptr nindex) const;
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов в этом массиве.

*ниндекс*<br/>
Индекс элемента, к которому осуществляется доступ.

### <a name="remarks"></a>Примечания

Первый оператор, вызываемый для массивов, не являющихся **`const`** , может использоваться либо справа (r-Value), либо слева (l-значение) оператора присваивания. Второй метод, который вызывается для **`const`** массивов, может использоваться только справа.

Отладочная версия библиотеки утверждает, находится ли индекс (в левой или правой части инструкции присваивания) вне границ.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]

## <a name="carrayrelocateelements"></a><a name="relocateelements"></a>CArray:: Релокатилементс

Перемещает данные в новый буфер, когда массив должен увеличиваться или сжиматься.

```
template<class TYPE, class ARG_TYPE>
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,
    const TYPE* pData,
    INT_PTR nCount);
```

### <a name="parameters"></a>Параметры

*пневдата*<br/>
Новый буфер для массива элементов.

*pData*<br/>
Старый массив элементов.

*нкаунт*<br/>
Число элементов в старом массиве.

### <a name="remarks"></a>Примечания

*пневдата* всегда достаточно велик, чтобы вместить все элементы *pData* .

Реализация [CArray](../../mfc/reference/carray-class.md) использует этот метод для копирования старых данных в новый буфер, когда массив должен увеличиваться или сжиматься (при вызове [SetSize](#setsize) или [фриекстра](#freeextra) ). Реализация по умолчанию просто копирует данные.

Для массивов, в которых элемент содержит указатель на один из своих собственных элементов, или другая структура содержит указатель на один из элементов массива, указатели не обновляются в виде обычного копирования. В этом случае можно исправить указатели, реализовав специализацию `RelocateElements` с соответствующими типами. Вы также отвечаете за копирование данных.

## <a name="carrayremoveall"></a><a name="removeall"></a>CArray:: RemoveAll

Удаляет все элементы из этого массива.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Если массив уже пуст, функция продолжает работать.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]

## <a name="carrayremoveat"></a><a name="removeat"></a>CArray:: RemoveAt

Удаляет один или несколько элементов, начиная с указанного индекса в массиве.

```cpp
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращаемому функцией [GetUpperBound](#getupperbound).

*нкаунт*<br/>
Число удаляемых элементов.

### <a name="remarks"></a>Примечания

В процессе он сдвигает все элементы над удаленными элементами. Он уменьшает верхнюю границу массива, но не освобождает память.

Если попытаться удалить больше элементов, чем содержится в массиве над точкой удаления, то отладочная версия библиотеки будет утверждена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]

## <a name="carraysetat"></a><a name="setat"></a>CArray:: SetAt

Задает элемент массива по указанному индексу.

```cpp
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращаемому функцией [GetUpperBound](#getupperbound).

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип аргументов, используемых для ссылок на элементы массива.

*невелемент*<br/>
Новое значение элемента, которое должно храниться в указанной позиции.

### <a name="remarks"></a>Примечания

`SetAt`не приведет к увеличению размера массива. Используйте [сетатгров](#setatgrow) , если требуется, чтобы массив был автоматически расти.

Необходимо убедиться, что значение индекса соответствует допустимой позиции в массиве. Если он выходит за пределы допустимого диапазона, отладочная версия библиотеки утверждает.

### <a name="example"></a>Пример

  См. пример для [GetAt](#getat).

## <a name="carraysetatgrow"></a><a name="setatgrow"></a>CArray:: Сетатгров

Задает элемент массива по указанному индексу.

```cpp
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0.

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элементов в массиве.

*невелемент*<br/>
Элемент, добавляемый в этот массив. Разрешено значение NULL.

### <a name="remarks"></a>Примечания

При необходимости массив автоматически растет (то есть верхняя граница корректируется для размещения нового элемента).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]

## <a name="carraysetsize"></a><a name="setsize"></a>CArray:: SetSize

Устанавливает размер пустого или существующего массива. При необходимости выделяет память.

```cpp
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Параметры

*нневсизе*<br/>
Новый размер массива (число элементов). Должна быть не ниже 0.

*нгровби*<br/>
Минимальное число слотов элементов для выделения при необходимости увеличения размера.

### <a name="remarks"></a>Примечания

Если новый размер меньше старого, массив усекается и освобождается вся неиспользуемая память.

Используйте эту функцию, чтобы задать размер массива перед началом использования массива. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

Параметр *нгровби* влияет на выделение внутренней памяти во время роста массива. Его использование никогда не влияет на размер [массива, сообщаемый методом IsArray](#getsize) и [GetUpperBound](#getupperbound). Если используется значение по умолчанию, MFC выделяет память способом вычисления, чтобы избежать фрагментации памяти и оптимизировать эффективность в большинстве случаев.

### <a name="example"></a>Пример

  См. пример для [GetData](#getdata).

## <a name="see-also"></a>См. также раздел

[Пример СОБРАНий MFC](../../overview/visual-cpp-samples.md)<br/>
[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс Кобаррай](../../mfc/reference/cobarray-class.md)<br/>
[Вспомогательные методы класса коллекции](../../mfc/reference/collection-class-helpers.md)
