---
title: Вспомогательные функции классов коллекции
ms.date: 11/04/2016
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
ms.openlocfilehash: 04b142cde12a9795f217559f875eef7fcec3b0f2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841432"
---
# <a name="collection-class-helpers"></a>Вспомогательные функции классов коллекции

Классы коллекций `CMap` , `CList` и `CArray` используют общие вспомогательные функции для таких целей, как сравнение, копирование и сериализация элементов. В рамках реализации классов, основанных на `CMap` , `CList` и `CArray` , необходимо переопределить эти функции при необходимости с помощью версий, адаптированных к типу данных, хранящихся в карте, списке или массиве. Дополнительные сведения о переопределении вспомогательных функций, таких как `SerializeElements` , см. в статье [коллекции статей: как создать строго типизированную коллекцию](../../mfc/how-to-make-a-type-safe-collection.md). Обратите внимание, что `ConstructElements` и `DestructElements` являются устаревшими.

Библиотека Microsoft Foundation Class предоставляет следующие глобальные функции в афкстемпл.h, помогающие настроить классы коллекций.

### <a name="collection-class-helpers"></a>Вспомогательные функции классов коллекции

|Имя|Описание|
|-|-|
|[CompareElements](#compareelements)|Указывает, совпадают ли элементы.|
|[CopyElements](#copyelements)|Копирует элементы из одного массива в другой.|
|[DumpElements](#dumpelements)|Предоставляет потоковый вывод диагностики.|
|[хашкэй](#hashkey)|Вычисляет хэш-ключ.|
|[SerializeElements](#serializeelements)|Сохраняет или извлекает элементы из архива или из него.|

## <a name="compareelements"></a><a name="compareelements"></a> компарилементс

Вызывается непосредственно [CList:: Find] (CList-Class. md # not_found. md # clist__find и косвенно с помощью [cmap__lookup](cmap-class.md#lookup) и [cmap__operator &#91;&#93;](cmap-class.md#operator_at).

```
template<class TYPE, class ARG_TYPE>
BOOL AFXAPI
CompareElements(
    const TYPE* pElement1,
    const ARG_TYPE* pElement2);
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Тип первого сравниваемого элемента.

*pElement1*<br/>
Указатель на первый сравниваемый элемент.

*ARG_TYPE*<br/>
Тип второго сравниваемого элемента.

*pElement2*<br/>
Указатель на второй сравниваемый элемент.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект, на который указывает *pElement1* , равен объекту, на который указывает *pElement2*; в противном случае — 0.

### <a name="remarks"></a>Примечания

`CMap`Вызовы используют `CMap` *ключ* параметров шаблона и *ARG_KEY*.

Реализация по умолчанию возвращает результат сравнения * \* pElement1* и * \* pElement2*. Переопределите эту функцию таким образом, чтобы она сравнивает элементы способом, подходящим для вашего приложения.

Язык C++ определяет оператор сравнения ( `==` ) для простых типов ( **`char`** , **`int`** , **`float`** и т. д.), но не определяет оператор сравнения для классов и структур. Если вы хотите использовать `CompareElements` или для создания экземпляра одного из классов коллекций, использующих его, необходимо либо определить оператор сравнения, либо перегрузку `CompareElements` с версией, возвращающей соответствующие значения.

### <a name="requirements"></a>Требования

   **Заголовок:** afxtempl.h

## <a name="copyelements"></a><a name="copyelements"></a> копелементс

Эта функция вызывается напрямую с помощью [CArray:: Append](carray-class.md#append) и [CArray:: Copy](carray-class.md#copy).

```
template<class TYPE>
void AFXAPI CopyElements(
    TYPE* pDest,
    const TYPE* pSrc,
    INT_PTR nCount);
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип копируемых элементов.

*pDest*<br/>
Указатель на место назначения, куда будут копироваться элементы.

*pSrc*<br/>
Указатель на источник копируемых элементов.

*нкаунт*<br/>
Число копируемых элементов.

### <a name="remarks"></a>Примечания

Реализация по умолчанию использует оператор простого присваивания ( **=** ) для выполнения операции копирования. Если копируемый тип не имеет перегруженного оператора =, то реализация по умолчанию выполняет побитовое копирование.

Сведения о реализации этой и других вспомогательных функций см. в статье [коллекции статей: как создать строго типизированную коллекцию](../how-to-make-a-type-safe-collection.md).

### <a name="requirements"></a>Требования

  **Заголовок** афкстемпл.h

## <a name="dumpelements"></a><a name="dumpelements"></a> думпелементс

Предоставляет потоковый вывод диагностических данных в текстовом виде для элементов коллекции при переопределении.

```
template<class TYPE>
void  AFXAPI DumpElements(
    CDumpContext& dc,
    const TYPE* pElements,
    INT_PTR nCount);
```

### <a name="parameters"></a>Параметры

*Постоянный*<br/>
Контекст дампа для дампа элементов.

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов.

*пелементс*<br/>
Указатель на элементы для создания дампа.

*нкаунт*<br/>
Количество элементов для дампа.

### <a name="remarks"></a>Примечания

`CArray::Dump`Функции, `CList::Dump` и `CMap::Dump` вызывают этот метод, если глубина дампа больше 0.

Реализация по умолчанию не выполняет никаких действий. Если элементы коллекции являются производными от `CObject` , переопределение обычно перебирает элементы коллекции, вызывая `Dump` для каждого элемента в свою очередь.

### <a name="requirements"></a>Требования

  **Заголовок** афкстемпл.h

## <a name="hashkey"></a><a name="hashkey"></a> хашкэй

Вычисляет хэш-значение для заданного ключа.

```
template<class ARG_KEY>
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key);
```

### <a name="parameters"></a>Параметры

*ARG_KEY*<br/>
Параметр шаблона, указывающий тип данных, используемый для доступа к ключам карт.

*key*<br/>
Ключ, хэш-значение которого необходимо вычислить.

### <a name="return-value"></a>Возвращаемое значение

Хэш-значение ключа.

### <a name="remarks"></a>Примечания

Эта функция вызывается напрямую [кмап:: ремовекэй](cmap-class.md#removekey) и косвенно с помощью [Кмап:: Lookup](cmap-class.md#lookup) и [кмап::operator &#91;&#93;](cmap-class.md#operator_at).

Реализация по умолчанию создает хэш-значение путем сдвига *ключа* вправо на четыре позиции. Переопределите эту функцию, чтобы она возвращала хэш-значения, соответствующие вашему приложению.

### <a name="example"></a>Пример

```cpp
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
```

### <a name="requirements"></a>Требования

  **Заголовок** афкстемпл.h

## <a name="serializeelements"></a><a name="serializeelements"></a> сериализилементс

[CArray](carray-class.md), [CList](clist-class.md)и [кмап](cmap-class.md) вызывают эту функцию для сериализации элементов.

```
template<class TYPE>
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);
```

### <a name="parameters"></a>Параметры

*TYPE*<br/>
Параметр шаблона, указывающий тип элементов.

*AR*<br/>
Архивный объект для архивации в или из.

*пелементс*<br/>
Указатель на элементы, для которых выполняется архивация.

*нкаунт*<br/>
Число архивируемых элементов

### <a name="remarks"></a>Примечания

Реализация по умолчанию выполняет побитовую операцию чтения или записи.

Сведения о реализации этой и других вспомогательных функций см. в статье [коллекции статей: как создать строго типизированную коллекцию](../how-to-make-a-type-safe-collection.md).

### <a name="example"></a>Пример

См. пример в разделе [коллекции статей: как создать строго типизированную коллекцию](../how-to-make-a-type-safe-collection.md).

### <a name="requirements"></a>Требования

  **Заголовок** афкстемпл.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[Класс Кмап](cmap-class.md)<br/>
[Класс CList](clist-class.md)<br/>
[Класс CArray](carray-class.md)
