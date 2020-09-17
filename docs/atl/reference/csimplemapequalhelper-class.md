---
title: Класс CSimpleMapEqualHelper
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
ms.openlocfilehash: d137a35a517ea93139f036f6e9a7a8de06d518a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330753"
---
# <a name="csimplemapequalhelper-class"></a>Класс CSimpleMapEqualHelper

Этот класс является помощником для класса [CSimpleMap.](../../atl/reference/csimplemap-class.md)

## <a name="syntax"></a>Синтаксис

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>Параметры

*Tkey*<br/>
Ключевой элемент.

*TVal*<br/>
Элемент значения.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(Статик) Тесты два ключа для равенства.|
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(Статик) Тесты двух значений равенства.|

## <a name="remarks"></a>Примечания

Этот класс черт является дополнением к классу. `CSimpleMap` В нем приводятся `CSimpleMap` методы сравнения двух элементов объекта (в частности, ключевых и ценностных компонентов) для обеспечения равенства. По умолчанию ключи и значения сравниваются с помощью **оператора,()**, но если карта содержит сложные типы данных, которые не имеют своего собственного оператора равенства, этот класс может быть отменен, чтобы обеспечить дополнительную требуемую функциональность.

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

## <a name="csimplemapequalhelperisequalkey"></a><a name="isequalkey"></a>CSimpleMapEqualHelper::IsEqualKey

Тесты два ключа для равенства.

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>Параметры

*k1*<br/>
Первый ключ.

*k2*<br/>
Второй ключ.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если ключи равны, ложные в противном случае.

## <a name="csimplemapequalhelperisequalvalue"></a><a name="isequalvalue"></a>CSimpleMapEqualHelper::IsEqualValue

Тесты двух значений равенства.

```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```

### <a name="parameters"></a>Параметры

*Версия 1*<br/>
Первое значение в вычитании.

*Версия 2*<br/>
Второе значение в вычитании.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если значения равны, ложные в противном случае.

## <a name="see-also"></a>См. также раздел

[CSimpleMapEqualHelperFalse Класс](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
