---
title: Ошибка компилятора C2040
ms.date: 11/04/2016
f1_keywords:
- C2040
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
ms.openlocfilehash: 8002d7168354b1213d01ca390a03b1baa5e35c88
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740420"
---
# <a name="compiler-error-c2040"></a>Ошибка компилятора C2040

operator: identifier1 отличается по уровням косвенного обращения от identifier2

Выражение, включающее заданные операнды, содержит несовместимые или неявно преобразованные типы операндов. Если оба операнда арифметические или неарифметические (например, массив или указатель), они используются без изменения. Если один из операндов арифметический, а другой — нет, арифметический операнд преобразуется в неарифметический.

В этом примере показано возникновение ошибки C2040 и приводятся сведения по ее устранению.

```cpp
// C2040.cpp
// Compile by using: cl /c /W3 C2040.cpp
bool test() {
   char c = '3';
   return c == "3"; // C2446, C2040
   // return c == '3'; // OK
}
```
