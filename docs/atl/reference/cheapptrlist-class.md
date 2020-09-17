---
title: Класс CHeapPtrlist
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
ms.openlocfilehash: 0500ab8f76049aeaf1c89355ea5450a93243b734
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326861"
---
# <a name="cheapptrlist-class"></a>Класс CHeapPtrlist

Этот класс предоставляет полезные методы при построении списка указателей кучи.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<typename E, class Allocator = ATL::CCRTAllocator>
class CHeapPtrList
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```

#### <a name="parameters"></a>Параметры

*E*<br/>
Тип объекта, который будет храниться в классе коллекции.

*Распределителя*<br/>
Класс распределения памяти для использования. По умолчанию [ccRTAllocator](../../atl/reference/ccrtallocator-class.md).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtrlist::CHeapPtrlist](#cheapptrlist)|Конструктор.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет конструктор и получает методы из [CAtlList](../../atl/reference/catllist-class.md) и [CHeapPtrElementTraits,](../../atl/reference/cheapptrelementtraits-class.md) чтобы помочь в создании объекта сбора класса хранения кучи указателей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Catllist](../../atl/reference/catllist-class.md)

`CHeapPtrList`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cheapptrlistcheapptrlist"></a><a name="cheapptrlist"></a>CHeapPtrlist::CHeapPtrlist

Конструктор.

```
CHeapPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Размер блока.

### <a name="remarks"></a>Примечания

Размер блока — это мера объема памяти, выделенного при необходимости нового элемента. Большие размеры блоков уменьшают вызовы для процедур распределения памяти, но используют больше ресурсов.

## <a name="see-also"></a>См. также раздел

[Класс CAtlList](../../atl/reference/catllist-class.md)<br/>
[Класс CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Класс CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
