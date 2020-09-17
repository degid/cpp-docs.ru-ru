---
title: Класс Каутоптраррай
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
ms.openlocfilehash: 11f39eac8b8d080fd840f6454f393e33ebcb9e1c
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167667"
---
# <a name="cautoptrarray-class"></a>Класс Каутоптраррай

Этот класс предоставляет методы, полезные при построении массива смарт-указателей.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```

### <a name="parameters"></a>Параметры

*&*<br/>
Тип указателя.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Каутоптраррай:: Каутоптраррай](#cautoptrarray)|Конструктор.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет конструктор и наследует методы от [CAtlArray](../../atl/reference/catlarray-class.md) и [каутоптрелементтраитс](../../atl/reference/cautoptrelementtraits-class.md) для облегчения создания объекта класса коллекции, в котором хранятся интеллектуальные указатели.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>Требования

**Заголовок:** атлколл.h

## <a name="cautoptrarraycautoptrarray"></a><a name="cautoptrarray"></a>Каутоптраррай:: Каутоптраррай

Конструктор.

```cpp
CAutoPtrArray() throw();
```

### <a name="remarks"></a>Примечания

Инициализирует массив интеллектуальных указателей.

## <a name="see-also"></a>См. также

[Класс CAtlArray](../../atl/reference/catlarray-class.md)<br/>
[Класс Каутоптрелементтраитс](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Класс Каутоптрлист](../../atl/reference/cautoptrlist-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
