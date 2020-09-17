---
title: Класс CDefaultHashTraits
ms.date: 11/04/2016
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
ms.openlocfilehash: 43932092621d44cfc8b07270df92e2765665f23f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327086"
---
# <a name="cdefaulthashtraits-class"></a>Класс CDefaultHashTraits

Этот класс обеспечивает статическую функцию для расчета значений хэша.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CDefaultHashTraits
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, которые будут храниться в коллекции.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDefaultHashTraits::Хэш](#hash)|(Статик) Вызовите эту функцию, чтобы вычислить значение хэша для данного элемента.|

## <a name="remarks"></a>Примечания

Этот класс содержит единую статическую функцию, которая возвращает хэш-значение для данного элемента. Этот класс используется [классом CDefaultElementTraits.](../../atl/reference/cdefaultelementtraits-class.md)

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cdefaulthashtraitshash"></a><a name="hash"></a>CDefaultHashTraits::Хэш

Вызовите эту функцию, чтобы вычислить значение хэша для данного элемента.

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>Параметры

*Элемент*<br/>
Элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение хэша.

### <a name="remarks"></a>Примечания

Алгоритм хэширования по умолчанию очень прост: значение возврата — это число элементов. Переопределить эту функцию, если требуется более сложный алгоритм.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
