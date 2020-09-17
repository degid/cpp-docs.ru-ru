---
title: Класс Каутовекторптр
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
ms.openlocfilehash: 65d37396b02d2c11c758915b201eef09cf1935b5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226650"
---
# <a name="cautovectorptr-class"></a>Класс Каутовекторптр

Этот класс представляет объект интеллектуального указателя, используя операторы создания и удаления Vector.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CAutoVectorPtr
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип указателя.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Каутовекторптр:: Каутовекторптр](#cautovectorptr)|Конструктор.|
|[Каутовекторптр:: ~ Каутовекторптр](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Каутовекторптр:: allocate](#allocate)|Вызовите этот метод, чтобы выделить память, необходимую для массива объектов, на который указывает `CAutoVectorPtr` .|
|[Каутовекторптр:: Attach](#attach)|Вызовите этот метод, чтобы стать владельцем существующего указателя.|
|[Каутовекторптр::D етач](#detach)|Вызовите этот метод, чтобы освободить владение указателем.|
|[Каутовекторптр:: Free](#free)|Вызовите этот метод, чтобы удалить объект, на который указывает `CAutoVectorPtr` .|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Каутовекторптр::operator T *](#operator_t__star)|Оператор CAST.|
|[Каутовекторптр::operator=](#operator_eq)|Оператор присваивания.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Каутовекторптр:: m_p](#m_p)|Переменная члена данных указателя.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы для создания и управления интеллектуальным указателем, что поможет защититься от утечек памяти за счет автоматического освобождения ресурсов, если он выходит за пределы области. `CAutoVectorPtr`аналогичен `CAutoPtr` , единственное отличие заключается в том, что `CAutoVectorPtr` для выделения и освобождения памяти вместо операторов C++ и Vector используется [вектор new&#91;&#93;](../../standard-library/new-operators.md#op_new_arr) и [&#91;&#93;векторного удаления](../../standard-library/new-operators.md#op_delete_arr) **`new`** **`delete`** . См. [каутовекторптрелементтраитс](../../atl/reference/cautovectorptrelementtraits-class.md) , если требуются классы коллекций `CAutoVectorPtr` .

Пример использования класса интеллектуального указателя см. в разделе [каутоптр](../../atl/reference/cautoptr-class.md) .

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="cautovectorptrallocate"></a><a name="allocate"></a>Каутовекторптр:: allocate

Вызовите этот метод, чтобы выделить память, необходимую для массива объектов, на который указывает `CAutoVectorPtr` .

```
bool Allocate(size_t nElements) throw();
```

### <a name="parameters"></a>Параметры

*нелементс*<br/>
Количество элементов в массиве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если память успешно выделена, и false в случае сбоя.

### <a name="remarks"></a>Примечания

В отладочных сборках произойдет сбой утверждения, если переменная члена [каутовекторптр:: m_p](#m_p) указывает на существующее значение. то есть он не равен NULL.

## <a name="cautovectorptrattach"></a><a name="attach"></a>Каутовекторптр:: Attach

Вызовите этот метод, чтобы стать владельцем существующего указателя.

```cpp
void Attach(T* p) throw();
```

### <a name="parameters"></a>Параметры

*ш*<br/>
`CAutoVectorPtr`Объект будет становиться владельцем этого указателя.

### <a name="remarks"></a>Примечания

Когда `CAutoVectorPtr` объект получает владение указателем, он автоматически удаляет указатель и все выделенные данные, когда оно выходит за пределы области. Если вызывается [каутовекторптр::D етач](#detach) , программист снова получит ответственность за освобождение ресурсов, выделенных для памяти.

В отладочных сборках произойдет сбой утверждения, если переменная члена [каутовекторптр:: m_p](#m_p) указывает на существующее значение. то есть он не равен NULL.

## <a name="cautovectorptrcautovectorptr"></a><a name="cautovectorptr"></a>Каутовекторптр:: Каутовекторптр

Конструктор.

```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Параметры

*ш*<br/>
Существующий указатель.

### <a name="remarks"></a>Примечания

`CAutoVectorPtr`Объект можно создать с помощью существующего указателя. в этом случае он передает владение указателем.

## <a name="cautovectorptrcautovectorptr"></a><a name="dtor"></a>Каутовекторптр:: ~ Каутовекторптр

Деструктор

```
~CAutoVectorPtr() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы. Вызывает [каутовекторптр:: Free](#free).

## <a name="cautovectorptrdetach"></a><a name="detach"></a>Каутовекторптр::D етач

Вызовите этот метод, чтобы освободить владение указателем.

```
T* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию указателя.

### <a name="remarks"></a>Примечания

Освобождает владение указателем, устанавливает для переменной-члена [каутовекторптр:: M_P](#m_p) значение NULL и возвращает копию указателя. После вызова `Detach` разработчик должен освободить все выделенные ресурсы, для которых `CAutoVectorPtr` объект мог быть ранее принят в обязанности.

## <a name="cautovectorptrfree"></a><a name="free"></a>Каутовекторптр:: Free

Вызовите этот метод, чтобы удалить объект, на который указывает `CAutoVectorPtr` .

```cpp
void Free() throw();
```

### <a name="remarks"></a>Примечания

Объект, на который указывает, `CAutoVectorPtr` освобождается, и переменной-члену [каутовекторптр:: m_p](#m_p) присваивается значение null.

## <a name="cautovectorptrm_p"></a><a name="m_p"></a>Каутовекторптр:: m_p

Переменная члена данных указателя.

```
T* m_p;
```

### <a name="remarks"></a>Примечания

Эта переменная члена содержит сведения об указателе.

## <a name="cautovectorptroperator-"></a><a name="operator_eq"></a>Каутовекторптр::operator=

Оператор присваивания.

```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Параметры

*ш*<br/>
Указатель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на **каутовекторптр \< T > **.

### <a name="remarks"></a>Примечания

Оператор присваивания отсоединяет `CAutoVectorPtr` объект от любого текущего указателя и присоединяет новый указатель, *p*, на его месте.

## <a name="cautovectorptroperator-t-"></a><a name="operator_t__star"></a>Каутовекторптр::operator T *

Оператор CAST.

```
operator T*() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает указатель на тип данных Object, определенный в шаблоне класса.

## <a name="see-also"></a>См. также статью

[Класс Каутоптр](../../atl/reference/cautoptr-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
