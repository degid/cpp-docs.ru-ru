---
title: Ошибка компилятора C3490
ms.date: 11/04/2016
f1_keywords:
- C3490
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
ms.openlocfilehash: 76729f49358e2a05b425730517e88ba14f2909c6
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685728"
---
# <a name="compiler-error-c3490"></a>Ошибка компилятора C3490

"переменная" не может быть изменен, поскольку доступ к нему осуществляется через константный объект

Лямбда-выражение, объявленное в **`const`** методе, не может изменять неизменяемые данные элемента.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите **`const`** модификатор из объявления метода.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C3490, так как изменяет переменную-член `_i` в **`const`** методе:

```cpp
// C3490a.cpp
// compile with: /c

class C
{
   void f() const
   {
      auto x = [=]() { _i = 20; }; // C3490
   }

   int _i;
};
```

В следующем примере разрешается C3490 путем удаления **`const`** модификатора из объявления метода:

```cpp
// C3490b.cpp
// compile with: /c

class C
{
   void f()
   {
      auto x = [=]() { _i = 20; };
   }

   int _i;
};
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
