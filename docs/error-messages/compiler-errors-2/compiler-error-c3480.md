---
title: Ошибка компилятора C3480
ms.date: 11/04/2016
f1_keywords:
- C3480
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
ms.openlocfilehash: a2fa1a8b02cf05d332210f359ae3ff33ed7d6e35
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686310"
---
# <a name="compiler-error-c3480"></a>Ошибка компилятора C3480

"переменная": передаваемая переменная в лямбда-выражении должна быть из внешней области видимости функции

Передаваемая переменная в лямбда-выражении не относится к внешней области видимости функции.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите переменную из списка передаваемых параметров в лямбда-выражении.

## <a name="examples"></a>Примеры

Приведенный ниже пример вызывает ошибку C3480, так как переменная `global` не относится к внешней области видимости функции.

```cpp
// C3480a.cpp

int global = 0;
int main()
{
   [&global] { global = 5; }(); // C3480
}
```

В приведенном ниже примере ошибка C3480 устраняется путем удаления переменной `global` из списка передачи лямбда-выражения.

```cpp
// C3480b.cpp

int global = 0;
int main()
{
   [] { global = 5; }();
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
