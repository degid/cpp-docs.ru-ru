---
title: Класс Ктипедптраррай
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrArray
- AFXTEMPL/CTypedPtrArray
- AFXTEMPL/CTypedPtrArray::Add
- AFXTEMPL/CTypedPtrArray::Append
- AFXTEMPL/CTypedPtrArray::Copy
- AFXTEMPL/CTypedPtrArray::ElementAt
- AFXTEMPL/CTypedPtrArray::GetAt
- AFXTEMPL/CTypedPtrArray::InsertAt
- AFXTEMPL/CTypedPtrArray::SetAt
- AFXTEMPL/CTypedPtrArray::SetAtGrow
helpviewer_keywords:
- CTypedPtrArray [MFC], Add
- CTypedPtrArray [MFC], Append
- CTypedPtrArray [MFC], Copy
- CTypedPtrArray [MFC], ElementAt
- CTypedPtrArray [MFC], GetAt
- CTypedPtrArray [MFC], InsertAt
- CTypedPtrArray [MFC], SetAt
- CTypedPtrArray [MFC], SetAtGrow
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
ms.openlocfilehash: db24e3992e5db70895ccc2908dba108de843bcdc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215950"
---
# <a name="ctypedptrarray-class"></a>Класс Ктипедптраррай

Предоставляет типобезопасную "программу-оболочку" для объектов класса `CPtrArray` или `CObArray`.

## <a name="syntax"></a>Синтаксис

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrArray : public BASE_CLASS
```

#### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс класса массива типизированных указателей; должен быть классом массива ( `CObArray` или `CPtrArray` ).

*TYPE*<br/>
Тип элементов, хранящихся в массиве базового класса.

## <a name="members"></a>Элементы

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Ктипедптраррай:: Add](#add)|Добавляет новый элемент в конец массива. При необходимости расширяет массив|
|[Ктипедптраррай:: Append](#append)|Добавляет содержимое одного массива в конец другого. При необходимости расширяет массив|
|[Ктипедптраррай:: Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[Ктипедптраррай:: ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[Ктипедптраррай:: GetAt](#getat)|Возвращает значение по указанному индексу.|
|[Ктипедптраррай:: Инсертат](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|
|[Ктипедптраррай:: SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|
|[Ктипедптраррай:: Сетатгров](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Ктипедптраррай::operator \[\]](#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Примечания

При использовании `CTypedPtrArray` , а не `CPtrArray` или `CObArray` , средство проверки типов C++ помогает устранить ошибки, вызванные несовпадением типов указателей.

Кроме того, `CTypedPtrArray` оболочка выполняет большую часть приведения, которая потребуется, если вы использовали `CObArray` или `CPtrArray` .

Поскольку все `CTypedPtrArray` функции являются встроенными, использование этого шаблона не оказывает существенного влияния на размер и скорость кода.

Дополнительные сведения об использовании `CTypedPtrArray` см. в статье [коллекции](../../mfc/collections.md) статей и [классы на основе шаблонов](../../mfc/template-based-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BASE_CLASS`

`CTypedPtrArray`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

## <a name="ctypedptrarrayadd"></a><a name="add"></a>Ктипедптраррай:: Add

Эта функция члена вызывает `BASE_CLASS` **:: Add**.

```
INT_PTR Add(TYPE newElement);
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элемента, добавляемого в массив.

*невелемент*<br/>
Элемент, добавляемый в этот массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс добавленного элемента.

### <a name="remarks"></a>Примечания

Более подробные примечания см. в разделе [кобаррай:: Add](../../mfc/reference/cobarray-class.md#add).

## <a name="ctypedptrarrayappend"></a><a name="append"></a>Ктипедптраррай:: Append

Эта функция члена вызывает `BASE_CLASS` :: Append * *.

```
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс класса массива типизированных указателей; должен быть классом массива ( [кобаррай](../../mfc/reference/cobarray-class.md) или [кптраррай](../../mfc/reference/cptrarray-class.md)).

*TYPE*<br/>
Тип элементов, хранящихся в массиве базового класса.

*src*<br/>
Источник элементов, добавляемых в массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого добавленного элемента.

### <a name="remarks"></a>Примечания

Более подробные примечания см. в разделе [кобаррай:: Append](../../mfc/reference/cobarray-class.md#append).

## <a name="ctypedptrarraycopy"></a><a name="copy"></a>Ктипедптраррай:: Copy

Эта функция члена вызывает `BASE_CLASS` **:: Copy**.

```cpp
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс класса массива типизированных указателей; должен быть классом массива ( [кобаррай](../../mfc/reference/cobarray-class.md) или [кптраррай](../../mfc/reference/cptrarray-class.md)).

*TYPE*<br/>
Тип элементов, хранящихся в массиве базового класса.

*src*<br/>
Источник элементов, копируемых в массив.

### <a name="remarks"></a>Примечания

Более подробные примечания см. в разделе [кобаррай:: Copy](../../mfc/reference/cobarray-class.md#copy).

## <a name="ctypedptrarrayelementat"></a><a name="elementat"></a>Ктипедптраррай:: ElementAt

Эта встроенная функция вызывает `BASE_CLASS` **:: ElementAt**.

```
TYPE& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов, хранящихся в этом массиве.

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному `BASE_CLASS` **:: GetUpperBound**.

### <a name="return-value"></a>Возвращаемое значение

Временная ссылка на элемент в расположении, заданном параметром *ниндекс*. Этот элемент имеет тип, заданный *типом*параметра шаблона.

### <a name="remarks"></a>Примечания

Более подробные примечания см. в разделе [кобаррай:: ElementAt](../../mfc/reference/cobarray-class.md#elementat).

## <a name="ctypedptrarraygetat"></a><a name="getat"></a>Ктипедптраррай:: GetAt

Эта встроенная функция вызывает `BASE_CLASS` **:: GetAt**.

```
TYPE GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов, хранящихся в массиве.

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному `BASE_CLASS` **:: GetUpperBound**.

### <a name="return-value"></a>Возвращаемое значение

Копия элемента в расположении, заданном параметром *ниндекс*. Этот элемент имеет тип, заданный *типом*параметра шаблона.

### <a name="remarks"></a>Примечания

Более подробные примечания см. в разделе [кобаррай:: GetAt](../../mfc/reference/cobarray-class.md#getat)

## <a name="ctypedptrarrayinsertat"></a><a name="insertat"></a>Ктипедптраррай:: Инсертат

Эта функция члена вызывает `BASE_CLASS` **:: инсертат**.

```cpp
void InsertAt(
    INT_PTR nIndex,
    TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который может быть больше значения, возвращенного [кобаррай:: GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).

*TYPE*<br/>
Тип элементов, хранящихся в массиве базового класса.

*невелемент*<br/>
Указатель объекта, помещаемый в этот массив. Допускается *невелемент* значения **null** .

*нкаунт*<br/>
Количество раз, когда этот элемент должен быть вставлен (значение по умолчанию — 1).

*нстартиндекс*<br/>
Целочисленный индекс, который может быть больше значения, возвращаемого методом `CObArray::GetUpperBound` .

*BASE_CLASS*<br/>
Базовый класс класса массива типизированных указателей; должен быть классом массива ( [кобаррай](../../mfc/reference/cobarray-class.md) или [кптраррай](../../mfc/reference/cptrarray-class.md)).

*пневаррай*<br/>
Другой массив, содержащий элементы для добавления в этот массив.

### <a name="remarks"></a>Примечания

Более подробные примечания см. в разделе [кобаррай:: инсертат](../../mfc/reference/cobarray-class.md#insertat).

## <a name="ctypedptrarrayoperator--"></a><a name="operator_at"></a>Ктипедптраррай::operator []

Эти встроенные операторы вызывают `BASE_CLASS` **::operator []**.

```
TYPE& operator[ ](int_ptr nindex);
TYPE operator[ ](int_ptr nindex) const;
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов, хранящихся в массиве.

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному `BASE_CLASS` **:: GetUpperBound**.

### <a name="remarks"></a>Примечания

Первый оператор, вызываемый для массивов, которые не являются **`const`** , можно использовать как справа (r-значение), так и слева (l-значение) оператора присваивания. Второй метод, вызываемый для **`const`** массивов, может использоваться только справа.

Отладочная версия библиотеки утверждает, находится ли индекс (в левой или правой части инструкции присваивания) вне границ.

## <a name="ctypedptrarraysetat"></a><a name="setat"></a>Ктипедптраррай:: SetAt

Эта функция члена вызывает `BASE_CLASS` **:: SetAt**.

```cpp
void SetAt(
    INT_PTR nIndex,
    TYPE ptr);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному функцией [кобаррай:: GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).

*TYPE*<br/>
Тип элементов, хранящихся в массиве базового класса.

*ptr*<br/>
Указатель на элемент, который необходимо вставить в массив в Ниндекс. Разрешено значение NULL.

### <a name="remarks"></a>Примечания

Более подробные примечания см. в разделе [кобаррай:: SetAt](../../mfc/reference/cobarray-class.md#setat).

## <a name="ctypedptrarraysetatgrow"></a><a name="setatgrow"></a>Ктипедптраррай:: Сетатгров

Эта функция члена вызывает `BASE_CLASS` **:: сетатгров**.

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    TYPE newElement);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0.

*TYPE*<br/>
Тип элементов, хранящихся в массиве базового класса.

*невелемент*<br/>
Указатель на объект, добавляемый в этот массив. Разрешено значение **null** .

### <a name="remarks"></a>Примечания

Более подробные примечания см. в разделе [кобаррай:: сетатгров](../../mfc/reference/cobarray-class.md#setatgrow).

## <a name="see-also"></a>См. также раздел

[Пример СОБРАНий MFC](../../overview/visual-cpp-samples.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс Кптраррай](../../mfc/reference/cptrarray-class.md)<br/>
[Класс Кобаррай](../../mfc/reference/cobarray-class.md)
