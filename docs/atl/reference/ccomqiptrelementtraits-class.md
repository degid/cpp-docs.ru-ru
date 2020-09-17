---
title: Класс CCom-IPtrElementTraits
ms.date: 11/04/2016
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
ms.openlocfilehash: 19f2669c157310be02f746672b22f6c0ed005075
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327412"
---
# <a name="ccomqiptrelementtraits-class"></a>Класс CCom-IPtrElementTraits

Этот класс предоставляет методы, статические функции и полезные при создании коллекций указателей интерфейса COM.

## <a name="syntax"></a>Синтаксис

```
template<typename I, const IID* piid=& __uuidof(I)>
class CComQIPtrElementTraits :
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>Параметры

*Я*<br/>
Интерфейс COM с указанием типа указателя для хранения.

*пиид*<br/>
Указатель на IID *I*.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CCom-IPtrElementTraits::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объект класса сбора.|

## <a name="remarks"></a>Примечания

Этот класс получает методы и обеспечивает полезную типографпри равен при создании класса коллекции объектов указатель интерфейса [CCom-IPtr](../../atl/reference/ccomqiptr-class.md) COM. Этот класс используется как [классами CInterfaceArray,](../../atl/reference/cinterfacearray-class.md) так и [CInterfaceList.](../../atl/reference/cinterfacelist-class.md)

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultЭлементТхрытс](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="ccomqiptrelementtraitsinargtype"></a><a name="inargtype"></a>CCom-IPtrElementTraits::INARGTYPE

Тип данных для добавления элементов в объект класса сбора.

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>См. также раздел

[Класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
