---
title: CSimpleMapEqualHelperFalse Класс
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
ms.openlocfilehash: b6bf1d4e3be849004e13e593fb5f4b5cb87f8123
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330740"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse Класс

Этот класс является помощником для класса [CSimpleMap.](../../atl/reference/csimplemap-class.md)

## <a name="syntax"></a>Синтаксис

```
template <class TKey, class TVal>
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Статик) Тесты два ключа для равенства.|
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Статик) Возвращает ложно.|

## <a name="remarks"></a>Примечания

Этот класс черт является дополнением к классу. `CSimpleMap` Он предоставляет метод сравнения двух элементов, содержащихся в объекте, `CSimpleMap` в частности двух элементов значения или двух ключевых элементов.

Сравнение значения всегда будет возвращаться ложным, `ATLASSERT` и, кроме того, будет звонить с аргументом ложного, если он когда-либо упоминается. В ситуациях, когда тест на равенство недостаточно определен, этот класс позволяет карте, содержащей пары ключей/значений, работать правильно для большинства методов, но не в четко определенной манере для методов, которые зависят от сравнения, такие как [CSimpleMap::FindVal](../../atl/reference/csimplemap-class.md#findval).

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

## <a name="csimplemapequalhelperfalseisequalkey"></a><a name="isequalkey"></a>CSimpleMapEqualHelperFalse::IsEqualKey

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

### <a name="remarks"></a>Примечания

Этот метод вызывает [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).

## <a name="csimplemapequalhelperfalseisequalvalue"></a><a name="isequalvalue"></a>CSimpleMapEqualHelperFalse::IsEqualValue

Возвращает значение false.

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение false.

### <a name="remarks"></a>Примечания

Этот метод всегда возвращается `ATLASSERT` ложным, и будет звонить с аргументом ложного, если он когда-либо упоминается. Цель состоит `CSimpleMapEqualHelperFalse::IsEqualValue` в том, чтобы заставить методы, использующие сопоставления, потерпеть неудачу в четко определенной форме, когда тесты на равенство не были должным образом определены.

## <a name="see-also"></a>См. также раздел

[Класс CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
