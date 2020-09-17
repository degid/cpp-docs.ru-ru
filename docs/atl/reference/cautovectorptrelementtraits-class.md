---
title: Класс CAutoVectorPtrElementTraits
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
ms.openlocfilehash: 956fe39c4d3ba89bb9def2f996dca59905753edb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318746"
---
# <a name="cautovectorptrelementtraits-class"></a>Класс CAutoVectorPtrElementTraits

Этот класс предоставляет методы, статические функции и полезные для создания коллекций интеллектуальных указателей с использованием новых векторных операторов и удаляют их.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class CAutoVectorPtrElementTraits :
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип указателя.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объект класса сбора.|
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|Тип данных для извлечения элементов из объекта класса сбора.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы, статические функции и типы для сособничания созданию объектов класса коллекции, содержащих интеллектуальные указатели. В отличие от [CAutoPtrElementTraits,](../../atl/reference/cautoptrelementtraits-class.md)этот класс использует вектор новых и удалить операторов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultЭлементТхрытс](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoVectorPtrElementTraits`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cautovectorptrelementtraitsinargtype"></a><a name="inargtype"></a>CAutoVectorPtrElementTraits::INARGTYPE

Тип данных для добавления элементов в объект класса сбора.

```
typedef CAutoVectorPtr<T>& INARGTYPE;
```

## <a name="cautovectorptrelementtraitsoutargtype"></a><a name="outargtype"></a>CAutoVectorPtrElementTraits::OUTARGTYPE

Тип данных для извлечения элементов из объекта класса сбора.

```
typedef T*& OUTARGTYPE;
```

## <a name="see-also"></a>См. также раздел

[Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Класс CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
