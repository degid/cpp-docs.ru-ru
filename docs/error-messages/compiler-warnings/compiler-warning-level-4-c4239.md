---
title: Предупреждение компилятора (уровень 4) C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: 25b97cfb50847a0929f3d3a97b822209e6a11900
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686682"
---
# <a name="compiler-warning-level-4-c4239"></a>Предупреждение компилятора (уровень 4) C4239

использовано нестандартное расширение: "токен": преобразование из "тип" в "тип"

Это преобразование типа запрещено стандартом C++, но его можно использовать в качестве расширения. За этим предупреждением всегда следует по крайней мере одна строка объяснения, описывающая нарушенное правило языка.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C4239.

```cpp
// C4239.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

void func(void) {
   C & rC = C();   // C4239
   const C & rC2 = C();   // OK
   rC2;
}
```

Преобразование целочисленного типа в тип enum не допускается строго.

Следующий пример приводит к возникновению ошибки C4239.

```cpp
// C4239b.cpp
// compile with: /W4 /c
enum E { value };
struct S {
   E e : 2;
} s = { 5 };   // C4239
// try the following line instead
// } s = { (E)5 };
```
