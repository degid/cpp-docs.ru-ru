---
title: Ошибка компилятора C3492
ms.date: 11/04/2016
f1_keywords:
- C3492
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
ms.openlocfilehash: bdaeb8797eb71b205f737d08e74430f161cb8caa
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686552"
---
# <a name="compiler-error-c3492"></a>Ошибка компилятора C3492

var: нельзя передавать член анонимного объединения

Вы не можете передавать член анонимного объединения

### <a name="to-correct-this-error"></a>Исправление ошибки

- Присвойте объединению имя и передайте полную структуру объединения в список передаваемых параметров лямбда-выражения.

## <a name="examples"></a>Примеры

В следующем примере возникает ошибка C3492, поскольку в нем передается член анонимного объединения:

```cpp
// C3492a.cpp

int main()
{
   union
   {
      char ch;
      int x;
   };

   ch = 'y';
   [&x](char ch) { x = ch; }(ch); // C3492
}
```

В следующем примере устраняется ошибка C3492 путем предоставления объединению имени и передачи полной структуры объединения в список передаваемых параметров лямбда-выражения:

```cpp
// C3492b.cpp

int main()
{
   union
   {
      char ch;
      int x;
   } u;

   u.ch = 'y';
   [&u](char ch) { u.x = ch; }(u.ch);
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
