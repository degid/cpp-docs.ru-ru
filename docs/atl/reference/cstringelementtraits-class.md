---
title: Класс CStringElementTraits
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
ms.openlocfilehash: 078cfd5ff93bfcd8acc747904ea05e6a2e762bc1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330623"
---
# <a name="cstringelementtraits-class"></a>Класс CStringElementTraits

Этот класс предоставляет статические функции, `CString` используемые классами сбора, храствующими объектами.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, которые будут храниться в коллекции.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CStringElementTraits::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объект класса сбора.|
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Тип данных для извлечения элементов из объекта класса сбора.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStringElementTraits::CompareElements](#compareelements)|(Статик) Вызовите эту функцию, чтобы сравнить два элемента строки для равенства.|
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Статик) Вызовите эту функцию для сравнения двух элементов строки.|
|[CStringElementTraits::CopyElements](#copyelements)|(Статик) Вызовите эту `CString` функцию для копирования элементов, хранящихся в объекте класса коллекции.|
|[CStringElementTraits::Хэш](#hash)|(Статик) Вызовите эту функцию, чтобы вычислить значение хэша для данного элемента строки.|
|[CStringElementTraits::ПереместитьЭлементы](#relocateelements)|(Статик) Вызовите эту `CString` функцию для перемещения элементов, хранящихся в объекте класса коллекции.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет статические функции для копирования, перемещения и сравнения строк и для создания значения хэша. Эти функции полезны при использовании класса сбора для хранения строковых данных. Используйте [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) при необходимости проведения нечувствительных сравнений. Используйте [CStringRefElementTraits,](../../atl/reference/cstringrefelementtraits-class.md) когда объекты строки должны рассматриваться в качестве ссылок.

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="requirements"></a>Требования

**Заголовок:** cstringt.h

## <a name="cstringelementtraitscompareelements"></a><a name="compareelements"></a>CStringElementTraits::CompareElements

Вызовите эту статическую функцию, чтобы сравнить два элемента строки для равенства.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый элемент строки.

*str2*<br/>
Второй элемент строки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если элементы равны, ложные в противном случае.

## <a name="cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>CStringElementTraits::CompareElementsOrdered

Вызовите эту статическую функцию, чтобы сравнить два элемента строки.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый элемент строки.

*str2*<br/>
Второй элемент строки.

### <a name="return-value"></a>Возвращаемое значение

Ноль, если строки идентичны, < 0, если *str1* меньше, чем *str2,* или > 0, если *str1* больше, чем *str2.* Для выполнения сравнений используется метод [CStringT::Compare.](../../atl-mfc-shared/reference/cstringt-class.md#compare)

## <a name="cstringelementtraitscopyelements"></a><a name="copyelements"></a>CStringElementTraits::CopyElements

Вызовите эту `CString` статическую функцию для копирования элементов, хранящихся в объекте класса коллекции.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Параметры

*pDest*<br/>
Указатель на первый элемент, который будет получать скопированные данные.

*Psrc*<br/>
Указатель на первый элемент для копирования.

*nЭлементы*<br/>
Число элементов для копирования.

### <a name="remarks"></a>Примечания

Элементы источника и назначения не должны пересекаться.

## <a name="cstringelementtraitshash"></a><a name="hash"></a>CStringElementTraits::Хэш

Вызовите эту статическую функцию, чтобы вычислить значение хэша для данного элемента строки.

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Элемент строки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает хэш-значение, рассчитанное с использованием содержимого строки.

## <a name="cstringelementtraitsinargtype"></a><a name="inargtype"></a>CStringElementTraits::INARGTYPE

Тип данных для добавления элементов в объект класса сбора.

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsoutargtype"></a><a name="outargtype"></a>CStringElementTraits::OUTARGTYPE

Тип данных для извлечения элементов из объекта класса сбора.

```
typedef T& OUTARGTYPE;
```

## <a name="cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a>CStringElementTraits::ПереместитьЭлементы

Вызовите эту статическую функцию для перемещения `CString` элементов, хранящихся в объекте класса коллекции.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Параметры

*pDest*<br/>
Указатель на первый элемент, который будет получать переложевы данные.

*Psrc*<br/>
Указатель на первый элемент для перемещения.

*nЭлементы*<br/>
Количество элементов для перемещения.

### <a name="remarks"></a>Примечания

Эта статическая функция вызывает [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), который достаточен для большинства типов данных. Если движимые объекты содержат указатели на их собственные члены, эту статическую функцию необходимо будет переопределить.

## <a name="see-also"></a>См. также раздел

[Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)<br/>
[Класс CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
