---
title: Ошибка компилятора C2450
ms.date: 11/04/2016
f1_keywords:
- C2450
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
ms.openlocfilehash: 55c7f7ba8708e1475404a474f85df7dbe37fcec0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220357"
---
# <a name="compiler-error-c2450"></a>Ошибка компилятора C2450

Недопустимое выражение switch типа "тип"

**`switch`** Результатом вычисления выражения является недопустимый тип. Он должен иметь целочисленный тип или тип класса с однозначным преобразованием в целочисленный тип. Если он имеет определяемый пользователем тип, необходимо указать оператор преобразования.

Следующий пример приводит к возникновению ошибки C2450:

```cpp
// C2450.cpp
class X {
public:
   int i;
} x;

class Y {
public:
   int i;
   operator int() { return i; }   // conversion operator
} y;

int main() {
   int j = 1;
   switch ( x ) {   // C2450, x is not type int
   // try the following line instead
   // switch ( y ) {
      default:  ;
   }
}
```
