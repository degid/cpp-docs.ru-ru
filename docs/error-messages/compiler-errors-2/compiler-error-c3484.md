---
title: Ошибка компилятора C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: ded4a183f69e4903afb4c9dfeae22f7751ef76ad
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686284"
---
# <a name="compiler-error-c3484"></a>Ошибка компилятора C3484

требуется "->" перед типом возврата

Необходимо указать `->` перед типом возврата лямбда-выражения.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Укажите `->` перед типом возврата.

## <a name="examples"></a>Примеры

В следующем примере возникает ошибка C3484:

```cpp
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

В следующем примере устраняется ошибка C3484 путем предоставления `->` перед типом возврата лямбда-выражения:

```cpp
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
