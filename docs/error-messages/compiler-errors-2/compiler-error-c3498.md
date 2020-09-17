---
title: Ошибка компилятора C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: f1b978a585f3404cd3a881f25d6ef6a0f66b212d
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686159"
---
# <a name="compiler-error-c3498"></a>Ошибка компилятора C3498

"var": невозможно записать переменную с управляемым или Винрттипе

Нельзя записать переменную, имеющую управляемый тип или тип среды выполнения Windows в лямбда-выражении.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Передайте управляемую переменную или переменную среды выполнения Windows в список параметров лямбда-выражения.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C3498, так как переменная, имеющая управляемый тип, присутствует в списке записи лямбда-выражения:

```cpp
// C3498a.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [&s](String ^ r)
      { return String::Concat(s, r); } (", World!"); // C3498
}
```

Следующий пример разрешает C3498, передав управляемую переменную `s` в список параметров лямбда-выражения:

```cpp
// C3498b.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [](String ^ s, String ^ r)
      { return String::Concat(s, r); } (s, ", World!");
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
