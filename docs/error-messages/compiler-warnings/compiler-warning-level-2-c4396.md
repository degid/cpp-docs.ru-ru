---
title: Предупреждение компилятора (уровень 2) C4396
ms.date: 11/04/2016
f1_keywords:
- C4396
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
ms.openlocfilehash: fec6875fdb2e8a60e71fe08da1ed4e8fa82e4641
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206046"
---
# <a name="compiler-warning-level-2-c4396"></a>Предупреждение компилятора (уровень 2) C4396

"имя": если дружественное объявление ссылается на специализацию функции-шаблона, встроенный спецификатор использовать невозможно

В специализации шаблона функции нельзя указывать спецификаторы [inline](../../cpp/inline-functions-cpp.md) . В этом случае при компиляции возникает предупреждение C4396, а спецификатор inline пропускается.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите **`inline`** описатель, **`__inline`** или **`__forceinline`** из объявления дружественной функции.

## <a name="example"></a>Пример

В следующем примере кода показано недопустимое объявление дружественной функции с **`inline`** описателем.

```cpp
// C4396.cpp
// compile with: /W2 /c

class X;
template<class T> void Func(T t, int i);

class X {
    friend inline void Func<char>(char t, int i);  //C4396
// try the following line instead
//    friend void Func<char>(char t, int i);
    int i;
};
```
