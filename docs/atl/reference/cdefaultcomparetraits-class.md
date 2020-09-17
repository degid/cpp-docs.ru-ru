---
title: Класс CDefaultCompareTraits
ms.date: 11/04/2016
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
ms.openlocfilehash: 8262800ef613424c37c53931d97dd4b1b1a71321
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327065"
---
# <a name="cdefaultcomparetraits-class"></a>Класс CDefaultCompareTraits

Этот класс предоставляет функции сравнения элементов по умолчанию.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CDefaultCompareTraits
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, которые будут храниться в коллекции.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDefaultCompareTraits::CompareElements](#compareelements)|(Статик) Назовите эту функцию для сравнения двух элементов для равенства.|
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Статик) Вызовите эту функцию, чтобы определить больший и меньший элемент.|

## <a name="remarks"></a>Примечания

Этот класс содержит две статические функции для сравнения элементов, хранящихся в объекте класса коллекции. Этот класс используется [классом CDefaultElementTraits.](../../atl/reference/cdefaultelementtraits-class.md)

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cdefaultcomparetraitscompareelements"></a><a name="compareelements"></a>CDefaultCompareTraits::CompareElements

Назовите эту функцию для сравнения двух элементов для равенства.

```
static bool CompareElements(const T& element1, const T& element2);
```

### <a name="parameters"></a>Параметры

*элемент1*<br/>
Первый элемент

*элемент2*<br/>
Второй элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если элементы равны, ложные в противном случае.

### <a name="remarks"></a>Примечания

Выполнение этой функции по умолчанию — это оператор равенства ()**==** Для объектов, не относясь от простых типов данных, эту функцию, возможно, потребуется переопределить.

## <a name="cdefaultcomparetraitscompareelementsordered"></a><a name="compareelementsordered"></a>CDefaultCompareTraits::CompareElementsOrdered

Вызовите эту функцию, чтобы определить больший и меньший элемент.

```
static int CompareElementsOrdered(const T& element1, const T& element2);
```

### <a name="parameters"></a>Параметры

*элемент1*<br/>
Первый элемент

*элемент2*<br/>
Второй элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает несколько седжеров на основе следующей таблицы:

|Условие|Возвращаемое значение|
|---------------|------------------|
|*элемент1* < *элемент2*|<0|
|*элемент1* == *элемент2*|0|
|*элемент1* > *элемент2*|> 0|

### <a name="remarks"></a>Примечания

В реализации этой функции **\<** по **>** умолчанию используются операторы и операторы. **==** Для объектов, не относясь от простых типов данных, эту функцию, возможно, потребуется переопределить.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
