---
title: Класс CSimpleArrayEqualHelper
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: 386b005777b3e31dd74916a41bc5af2ab82df210
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330883"
---
# <a name="csimplearrayequalhelper-class"></a>Класс CSimpleArrayEqualHelper

Этот класс является помощником для класса [CSimpleArray.](../../atl/reference/csimplearray-class.md)

## <a name="syntax"></a>Синтаксис

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Производный класс.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleArrayУравнойХелсер::Аум](#isequal)|(Статик) Тестирует `CSimpleArray` два элемента объекта на равенство.|

## <a name="remarks"></a>Примечания

Этот класс черт является дополнением к классу. `CSimpleArray` Он предоставляет метод сравнения двух элементов, хранящихся в объекте. `CSimpleArray` По умолчанию элементы сравниваются с использованием **оператора ()**, но если массив содержит сложные типы данных, которые не имеют своего оператора равенства, вам нужно будет переопределить этот класс.

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

## <a name="csimplearrayequalhelperisequal"></a><a name="isequal"></a>CSimpleArrayУравнойХелсер::Аум

Тестирует `CSimpleArray` два элемента объекта на равенство.

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>Параметры

*T1*<br/>
Объект типа T.

*t2*<br/>
Объект типа T.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если элементы равны, ложные в противном случае.

## <a name="see-also"></a>См. также раздел

[Класс CSimpleArray](../../atl/reference/csimplearray-class.md)<br/>
[CSimpleArrayEqualHelperFalse Класс](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
