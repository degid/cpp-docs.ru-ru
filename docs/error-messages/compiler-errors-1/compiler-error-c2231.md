---
title: Ошибка компилятора C2231
ms.date: 11/04/2016
f1_keywords:
- C2231
helpviewer_keywords:
- C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
ms.openlocfilehash: 50230b3a9b609d281cddf996783287c270f844d5
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301825"
---
# <a name="compiler-error-c2231"></a>Ошибка компилятора C2231

".": левый операнд указывает на "ключ класса", используйте "->"

Операнд, расположенный слева от операции выбора члена (.), является указателем, а не классом, структурой или объединением.

При компиляции следующего примера возникнет ошибка C2231:

```c
// C2231.c
struct S {
   int member;
} s, *ps = &s;
int main() {
   ps.member = 0;   // C2231

   // OK
   ps->member = 0;   // crash
   s.member = 0;
}
```
