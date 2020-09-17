---
title: Предупреждение компилятора (уровень 1) C4683
ms.date: 08/27/2018
f1_keywords:
- C4683
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
ms.openlocfilehash: f86cf8f6d894d6efaa1b49977634956dc1979a98
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175433"
---
# <a name="compiler-warning-level-1-c4683"></a>Предупреждение компилятора (уровень 1) C4683

> "*функция*": источник события имеет параметр "out"; Будьте внимательны при подключении нескольких обработчиков событий

## <a name="remarks"></a>Примечания

Если несколько приемников событий ожидают передачи данных в источник событий COM, значение параметра out можно игнорировать.

Имейте в виду, что утечка памяти произойдет в следующих ситуациях:

1. , Если метод имеет параметр out, выделенный внутренним образом, например BSTR *.

2. Значение, если событие содержит более одного обработчика (является многоадресным событием).

Причина утечки заключается в том, что параметр out будет задан более чем одним обработчиком, но возвращен в узел вызова только последним обработчиком.

## <a name="example"></a>Пример

В следующем примере создается C4683 и демонстрируется его устранение.

```cpp
// C4683.cpp
// compile with: /W1 /LD
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="xx") ];

[ object ]
__interface I {
   HRESULT f([out] int* pi);
   // try the following line instead
   // HRESULT f(int* pi);
};

[ coclass, event_source(com) ]
struct E {
   __event __interface I;   // C4683
};
```
