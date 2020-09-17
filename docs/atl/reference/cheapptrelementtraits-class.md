---
title: Класс CHeapPtrElementTraits
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
ms.openlocfilehash: f09da968b264463eba759372e4e0756397e9978e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326874"
---
# <a name="cheapptrelementtraits-class"></a>Класс CHeapPtrElementTraits

Этот класс предоставляет методы, статические функции и полезные при создании коллекций указателей кучи.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<typename T, class Allocator = ATL::CCRTAllocator>
class CHeapPtrElementTraits :
   public CDefaultElementTraits<ATL::CHeapPtr<T, Allocator>>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта, который будет храниться в классе коллекции.

*Распределителя*<br/>
Класс распределения памяти для использования. По умолчанию [ccRTAllocator](../../atl/reference/ccrtallocator-class.md).

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CHeapPtrElementTraits::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объект класса сбора.|
|[CHeapPtrElementTraits::OUTARGTYPE](#outargtype)|Тип данных для извлечения элементов из объекта класса сбора.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы, статические функции и типы для сособничания созданию объектов класса коллекции, содержащих кучи указателей. Класс `CHeapPtrList` происходит от `CHeapPtrElementTraits`.

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultЭлементТхрытс](../../atl/reference/cdefaultelementtraits-class.md)

`CHeapPtrElementTraits`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cheapptrelementtraitsinargtype"></a><a name="inargtype"></a>CHeapPtrElementTraits::INARGTYPE

Тип данных для добавления элементов в объект класса сбора.

```
typedef CHeapPtr<T, Allocator>& INARGTYPE;
```

## <a name="cheapptrelementtraitsoutargtype"></a><a name="outargtype"></a>CHeapPtrElementTraits::OUTARGTYPE

Тип данных для извлечения элементов из объекта класса сбора.

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>См. также раздел

[Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Класс CComHeapPtr](../../atl/reference/ccomheapptr-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
