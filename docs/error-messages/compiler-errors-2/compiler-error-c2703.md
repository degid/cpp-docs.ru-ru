---
title: Ошибка компилятора C2703
description: Описывает ошибку компилятора Microsoft C/C++ C2703.
ms.date: 08/24/2020
f1_keywords:
- C2703
helpviewer_keywords:
- C2703
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
ms.openlocfilehash: 4d5b5ccad1cd15c1a107c81423e2372e14165776
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898604"
---
# <a name="compiler-error-c2703"></a>Ошибка компилятора C2703

> Недопустимый `__leave` оператор

## <a name="remarks"></a>Примечания

**`__leave`** Оператор должен находиться внутри **`__try`** блока.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2703:

```cpp
// C2703.cpp
int main() {
   __leave;   // C2703
   __try {
      // try the following line instead
      __leave;
   }
   __finally {}
}
```

## <a name="see-also"></a>См. также

[`__leave`Ключевое слово](../../cpp/try-except-statement.md#__leave)\
[`try-except` баланс](../../cpp/try-except-statement.md)\
[Инструкция `try-finally`](../../cpp/try-finally-statement.md)
