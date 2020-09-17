---
title: Класс CPrimitiveElementTraits
ms.date: 11/04/2016
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
ms.openlocfilehash: 6b45d93420d1832091cc451a3e6eb309f61d07a3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331440"
---
# <a name="cprimitiveelementtraits-class"></a>Класс CPrimitiveElementTraits

Этот класс предоставляет методы и функции по умолчанию для класса сбора, состоящего из примитивных типов данных.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, которые будут храниться в объекте класса сбора.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CPrimitiveElementTraits::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объект класса сбора.|
|[CPrimitiveElementTraits:::OUTARGTYPE](#outargtype)|Тип данных для извлечения элементов из объекта класса сбора.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет статичные функции и методы по умолчанию для перемещения, копирования, сравнения и хэширования примитивных элементов типа данных, хранящихся в объекте класса сбора.

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultЭлементТхрытс](../../atl/reference/cdefaultelementtraits-class.md)

`CPrimitiveElementTraits`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cprimitiveelementtraitsinargtype"></a><a name="inargtype"></a>CPrimitiveElementTraits::INARGTYPE

Тип данных для добавления элементов в объект класса сбора.

```
typedef T INARGTYPE;
```

## <a name="cprimitiveelementtraitsoutargtype"></a><a name="outargtype"></a>CPrimitiveElementTraits:::OUTARGTYPE

Тип данных для извлечения элементов из объекта класса сбора.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>См. также раздел

[Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
