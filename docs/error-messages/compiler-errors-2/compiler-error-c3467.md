---
title: Ошибка компилятора C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: bba505b01df8eb1b253fbecb0db93d94ae62d5ac
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756374"
---
# <a name="compiler-error-c3467"></a>Ошибка компилятора C3467

"тип": данный тип уже был переадресован

Компилятор обнаружил несколько объявлений перенаправления типа для одного типа. Для каждого типа допускается только одно объявление.

Дополнительные сведения см. в разделе [ПересылкаC++типов (/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Пример

В приведенном ниже примере создается компонент.

```cpp
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3467:

```cpp
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```
