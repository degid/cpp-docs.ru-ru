---
title: Класс Кстрингрефелементтраитс
ms.date: 11/04/2016
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
ms.openlocfilehash: 6fa8772033a5a82940cf30b2a73d6ea356269d67
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226559"
---
# <a name="cstringrefelementtraits-class"></a>Класс Кстрингрефелементтраитс

Этот класс предоставляет статические функции, связанные со строками, хранящимися в объектах класса коллекции. Строковые объекты обрабатываются как ссылки.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class CStringRefElementTraits : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, сохраняемых в коллекции.

## <a name="members"></a>Элементы

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кстрингрефелементтраитс:: Компарилементс](#compareelements)|Вызовите эту статическую функцию, чтобы сравнить два строковых элемента на равенство.|
|[Кстрингрефелементтраитс:: Компарилементсордеред](#compareelementsordered)|Вызовите эту статическую функцию, чтобы сравнить два строковых элемента.|
|[Кстрингрефелементтраитс:: hash](#hash)|Вызовите эту статическую функцию, чтобы вычислить хэш-значение для заданного строкового элемента.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет статические функции для сравнения строк и создания хэш-значения. Эти функции полезны при использовании класса коллекции для хранения данных, основанных на строках. В отличие от [кстринжелементтраитс](../../atl/reference/cstringelementtraits-class.md) и [кстринжелементтраитси](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` `CString` аргументы передаются как **`const`** `CString&` ссылки.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[целементтраитсбасе](../../atl/reference/celementtraitsbase-class.md)

`CStringRefElementTraits`

## <a name="requirements"></a>Требования

**Заголовок:** атлколл.h

## <a name="cstringrefelementtraitscompareelements"></a><a name="compareelements"></a>Кстрингрефелементтраитс:: Компарилементс

Вызовите эту статическую функцию, чтобы сравнить два строковых элемента на равенство.

```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```

### <a name="parameters"></a>Параметры

*Element1*<br/>
Первый элемент строки.

*element2*<br/>
Второй строковый элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если элементы равны, и false в противном случае.

## <a name="cstringrefelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>Кстрингрефелементтраитс:: Компарилементсордеред

Вызовите эту статическую функцию, чтобы сравнить два строковых элемента.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый элемент строки.

*str2*<br/>
Второй строковый элемент.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны, < 0, если значение *str1* меньше *str2*, или > 0, если *str1* больше *str2*. Для выполнения сравнений используется метод [CStringT:: Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) .

## <a name="cstringrefelementtraitshash"></a><a name="hash"></a>Кстрингрефелементтраитс:: hash

Вызовите эту статическую функцию, чтобы вычислить хэш-значение для заданного строкового элемента.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Параметры

*str*<br/>
Строковый элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает хэш-значение, вычисленное с использованием содержимого строки.

## <a name="see-also"></a>См. также статью

[Класс Целементтраитсбасе](../../atl/reference/celementtraitsbase-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
