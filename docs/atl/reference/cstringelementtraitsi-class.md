---
title: Класс CStringElementTraitsI
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
ms.openlocfilehash: 32980e19443cb17a3a688c85ff21195c60ed2124
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330591"
---
# <a name="cstringelementtraitsi-class"></a>Класс CStringElementTraitsI

Этот класс предоставляет статические функции, связанные со строками, хранящимися в объектах класса коллекции. Он похож на [CStringElementTraits,](../../atl/reference/cstringelementtraits-class.md)но выполняет нечувствительные сравнения.

## <a name="syntax"></a>Синтаксис

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, которые будут храниться в коллекции.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CStringElementTraitsI::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объект класса сбора.|
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|Тип данных для извлечения элементов из объекта класса сбора.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStringElementTraitsI:СравнениеЭлементы](#compareelements)|Вызовите эту статическую функцию, чтобы сравнить два элемента строки для равенства, игнорируя различия в случае.|
|[CStringElementTraitsI:CompareElementsOrdered](#compareelementsordered)|Вызовите эту статическую функцию, чтобы сравнить два элемента строки, игнорируя различия в случае.|
|[CStringElementTraitsI:Хэш](#hash)|Вызовите эту статическую функцию, чтобы вычислить значение хэша для данного элемента строки.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет статические функции для сравнения строк и для создания значения хэша. Эти функции полезны при использовании класса сбора для хранения строковых данных. Используйте [CStringRefElementTraits,](../../atl/reference/cstringrefelementtraits-class.md) когда объекты строки должны рассматриваться в качестве ссылок.

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cstringelementtraitsicompareelements"></a><a name="compareelements"></a>CStringElementTraitsI:СравнениеЭлементы

Вызовите эту статическую функцию, чтобы сравнить два элемента строки для равенства, игнорируя различия в случае.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый элемент строки.

*str2*<br/>
Второй элемент строки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если элементы равны, ложные в противном случае.

### <a name="remarks"></a>Примечания

Сравнения являются случаями нечувствительными.

## <a name="cstringelementtraitsicompareelementsordered"></a><a name="compareelementsordered"></a>CStringElementTraitsI:CompareElementsOrdered

Вызовите эту статическую функцию, чтобы сравнить два элемента строки, игнорируя различия в случае.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый элемент строки.

*str2*<br/>
Второй элемент строки.

### <a name="return-value"></a>Возвращаемое значение

Ноль, если строки идентичны, < 0, если *str1* меньше, чем *str2,* или > 0, если *str1* больше, чем *str2.* Для выполнения сравнений используется метод [CStringT::Compare.](../../atl-mfc-shared/reference/cstringt-class.md#compare)

### <a name="remarks"></a>Примечания

Сравнения являются случаями нечувствительными.

## <a name="cstringelementtraitsihash"></a><a name="hash"></a>CStringElementTraitsI:Хэш

Вызовите эту статическую функцию, чтобы вычислить значение хэша для данного элемента строки.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Элемент строки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает хэш-значение, рассчитанное с использованием содержимого строки.

## <a name="cstringelementtraitsiinargtype"></a><a name="inargtype"></a>CStringElementTraitsI::INARGTYPE

Тип данных для добавления элементов в объект класса сбора.

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsioutargtype"></a><a name="outargtype"></a>CStringElementTraitsI::OUTARGTYPE

Тип данных для извлечения элементов из объекта класса сбора.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>См. также раздел

[Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)
