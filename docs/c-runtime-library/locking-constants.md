---
title: Константы _locking
ms.date: 11/04/2016
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
ms.openlocfilehash: 8cfc1f933179e043f464a69f3ac5cf4ca25763e0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830830"
---
# <a name="_locking-constants"></a>Константы _locking

## <a name="syntax"></a>Синтаксис

```
#include <sys/locking.h>
```

## <a name="remarks"></a>Примечания

Аргумент *mode* в вызове функции `_locking` определяет, какое действие блокировки будет выполняться.

Аргумент *mode* должен быть одной из следующих констант манифеста.

|Значение|Описание|
|-|-|
| `_LK_LOCK`  | Блокирует указанные байты. Если заблокировать байты не удается, функция попытается повторить блокировку снова через 1 секунду. Если после 10 попыток байты все равно не удается заблокировать, функция возвращает ошибку.  |
| `_LK_RLCK`  | Эквивалентно `_LK_LOCK`.  |
|`_LK_NBLCK`  | Блокирует указанные байты. Если байты не удается заблокировать, функция возвращает ошибку.  |
| `_LK_NBRLCK`  | Эквивалентно `_LK_NBLCK`.  |
| `_LK_UNLCK`  | Разблокирует указанные байты. (Байты должны быть ранее заблокированы.)  |

## <a name="see-also"></a>См. также раздел

[_locking](../c-runtime-library/reference/locking.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)
