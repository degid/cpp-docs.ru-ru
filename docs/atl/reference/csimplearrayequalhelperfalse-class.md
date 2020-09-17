---
title: CSimpleArrayEqualHelperFalse Класс
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
ms.openlocfilehash: 5eca3145d64895e34b599fbf83834af142b65973
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330896"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse Класс

Этот класс является помощником для класса [CSimpleArray.](../../atl/reference/csimplearray-class.md)

## <a name="syntax"></a>Синтаксис

```
template <class T>
class CSimpleArrayEqualHelperFalse
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Производный класс.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(Статик) Возвращает ложно.|

## <a name="remarks"></a>Примечания

Этот класс черт является дополнением к классу. `CSimpleArray` Он всегда возвращает ложные, и, кроме того, будет звонить `ATLASSERT` с аргументом ложного, если он когда-либо упоминается. В ситуациях, когда тест на равенство недостаточно определен, этот класс позволяет массиву, содержащему элементы, работать правильно для большинства методов, но не в четко определенной манере для методов, которые зависят от сравнения, такие как [CSimpleArray::Найти](../../atl/reference/csimplearray-class.md#find).

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

## <a name="csimplearrayequalhelperfalseisequal"></a><a name="isequal"></a>CSimpleArrayEqualHelperFalse::IsEqual

Возвращает значение false.

```
static bool IsEqual(const T&, const T&);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение false.

### <a name="remarks"></a>Примечания

Этот метод всегда возвращается `ATLASSERT` ложным, и будет звонить с аргументом ложного, если ссылки. Цель состоит `CSimpleArrayEqualHelperFalse::IsEqual` в том, чтобы заставить методы, использующие сопоставления, потерпеть неудачу в четко определенной форме, когда тесты на равенство не были должным образом определены.

## <a name="see-also"></a>См. также раздел

[Класс CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
