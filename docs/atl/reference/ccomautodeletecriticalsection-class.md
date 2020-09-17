---
title: Класс Ккомаутоделетекритикалсектион
ms.date: 11/04/2016
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
ms.openlocfilehash: f44dbff7d353cb09142ac742b526d3541e9b2265
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224335"
---
# <a name="ccomautodeletecriticalsection-class"></a>Класс Ккомаутоделетекритикалсектион

Этот класс предоставляет методы для получения и освобождения владения объектом критической секции.

## <a name="syntax"></a>Синтаксис

```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```

## <a name="remarks"></a>Примечания

`CComAutoDeleteCriticalSection`является производным от класса [ккомсафеделетекритикалсектион](../../atl/reference/ccomsafedeletecriticalsection-class.md). Однако `CComAutoDeleteCriticalSection` переопределяет метод [Term](ccomsafedeletecriticalsection-class.md#term) на **`private`** доступ, что приводит к принудительной очистке внутренней памяти только в том случае, если экземпляры этого класса выходят за пределы области или явно удаляются из памяти.

Этот класс не предоставляет дополнительных методов по отношению к базовому классу. Дополнительные сведения о вспомогательных классах критической секции см. в разделе [ккомсафеделетекритикалсектион](../../atl/reference/ccomsafedeletecriticalsection-class.md) и [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md)

[ккомсафеделетекритикалсектион](../../atl/reference/ccomsafedeletecriticalsection-class.md)

`CComAutoDeleteCriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** атлкоре.h

## <a name="see-also"></a>См. также статью

[Класс Ккомсафеделетекритикалсектион](../../atl/reference/ccomsafedeletecriticalsection-class.md)<br/>
[Класс Ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
