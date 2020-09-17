---
title: Класс CAutoPtrList
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
ms.openlocfilehash: 48c7ad6fe13c5f5fbbe5829c25ce1c27896841be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318806"
---
# <a name="cautoptrlist-class"></a>Класс CAutoPtrList

Этот класс предоставляет полезные методы при построении списка интеллектуальных указателей.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<typename E>
class CAutoPtrList :
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>Параметры

*E*<br/>
Тип указателя.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAutoPtrlist:CAutoPtrlist](#cautoptrlist)|Конструктор.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет конструктор и получает методы из [CAtlList](../../atl/reference/catllist-class.md) и [CAutoPtrElementTraits,](../../atl/reference/cautoptrelementtraits-class.md) чтобы помочь создать объект списка хранения интеллектуальных указателей. Класс [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) предоставляет аналогичную функцию для объекта массива.

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Catllist](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cautoptrlistcautoptrlist"></a><a name="cautoptrlist"></a>CAutoPtrlist:CAutoPtrlist

Конструктор.

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Размер блока, с значением по умолчанию 10.

### <a name="remarks"></a>Примечания

Размер блока — это мера объема памяти, выделенного при необходимости нового элемента. Большие размеры блоков уменьшают вызовы для процедур распределения памяти, но используют больше ресурсов.

## <a name="see-also"></a>См. также раздел

[Класс CAtlList](../../atl/reference/catllist-class.md)<br/>
[Класс CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
