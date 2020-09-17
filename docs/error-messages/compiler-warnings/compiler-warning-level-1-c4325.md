---
title: Предупреждение компилятора (уровень 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 551680bc1d24097200a1e641bc4238f883ad94dd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230705"
---
# <a name="compiler-warning-level-1-c4325"></a>Предупреждение компилятора (уровень 1) C4325

> атрибуты для стандартного раздела "*раздел*" пропущены

## <a name="remarks"></a>Примечания

Вы не можете изменить атрибуты стандартного раздела. Пример:

```cpp
#pragma section(".sdata", long)
```

Это приведет к перезаписи `.sdata` стандартного раздела, который использует **`short`** тип данных с **`long`** типом данных.

Стандартные разделы, атрибуты которых вы не можете изменить:

- . Data

- . sdata

- . BSS

- . SBSS

- .text

- . const

- . сконст

- . rdata

- . срдата

Дополнительные разделы можно добавить позже.

## <a name="see-also"></a>См. также раздел

[раздела](../../preprocessor/section.md)
