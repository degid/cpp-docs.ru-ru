---
title: Ошибка компилятора C2803
ms.date: 11/04/2016
f1_keywords:
- C2803
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
ms.openlocfilehash: d39f737ba02f3fa9c9d5f61594ddf730db6739a5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760664"
---
# <a name="compiler-error-c2803"></a>Ошибка компилятора C2803

"operator оператор" должен иметь хотя бы один формальный параметр типа класса

Перегруженный оператор не имеет параметра типа класса.

Необходимо передать хотя бы один параметр по ссылке (не используя указатели, но ссылки) или по значению, чтобы иметь возможность писать "a < b" (а и b типа класса A).

Если оба параметра являются указателями, это будет чистое сравнение адресов указателей и не будет использовать определенное пользователем преобразование.

Следующий пример приводит к возникновению ошибки C2803:

```cpp
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```
