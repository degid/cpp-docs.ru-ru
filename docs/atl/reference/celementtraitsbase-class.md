---
title: Класс CElementTraitsBase
ms.date: 11/04/2016
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
ms.openlocfilehash: 5a29e8778cf2f3400df25b55574950a005bad995
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327006"
---
# <a name="celementtraitsbase-class"></a>Класс CElementTraitsBase

Этот класс предоставляет методы копирования и перемещения по умолчанию для класса коллекции.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CElementTraitsBase
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, которые будут храниться в коллекции.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CElementTraitsBase::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объект класса сбора.|
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Тип данных для извлечения элементов из объекта класса сбора.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CElementTraitsBase::CopyElements](#copyelements)|Вызовите этот метод для копирования элементов, хранящихся в объекте класса коллекции.|
|[CElementTraitsBase::ПереместитьЭлементы](#relocateelements)|Вызовите этот метод для перемещения элементов, хранящихся в объекте класса сбора.|

## <a name="remarks"></a>Примечания

Этот базовый класс определяет методы копирования и перемещения элементов в классе коллекции. Он используется в классах [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)и [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="celementtraitsbasecopyelements"></a><a name="copyelements"></a>CElementTraitsBase::CopyElements

Вызовите этот метод для копирования элементов, хранящихся в объекте класса коллекции.

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

## <a name="celementtraitsbaseinargtype"></a><a name="inargtype"></a>CElementTraitsBase::INARGTYPE

Тип данных для добавления элементов в коллекцию.

```
typedef const T& INARGTYPE;
```

## <a name="celementtraitsbaseoutargtype"></a><a name="outargtype"></a>CElementTraitsBase::OUTARGTYPE

Тип данных для извлечения элементов из коллекции.

```
typedef T& OUTARGTYPE;
```

## <a name="celementtraitsbaserelocateelements"></a><a name="relocateelements"></a>CElementTraitsBase::ПереместитьЭлементы

Вызовите этот метод для перемещения элементов, хранящихся в объекте класса сбора.

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

Этот метод называет [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), который достаточен для большинства типов данных. Если движимые объекты содержат указатели для своих членов, этот метод необходимо будет переопределить.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
