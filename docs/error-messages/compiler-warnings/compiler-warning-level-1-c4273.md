---
title: Предупреждение компилятора (уровень 1) C4273
ms.date: 11/04/2016
f1_keywords:
- C4273
helpviewer_keywords:
- C4273
ms.assetid: cc18611d-9454-40a4-ad73-69823d5888fb
ms.openlocfilehash: 08508ce11943605e3a7432491f8c4dd1d1175e2f
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686539"
---
# <a name="compiler-warning-level-1-c4273"></a>Предупреждение компилятора (уровень 1) C4273

"функция": несовместимая компоновка DLL

Два определения в файле различаются по использованию [DllImport](../../cpp/dllexport-dllimport.md).

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C4273.

```cpp
// C4273.cpp
// compile with: /W1 /c
char __declspec(dllimport) c;
char c;   // C4273, delete this line or the line above to resolve
```

Следующий пример приводит к возникновению ошибки C4273.

```cpp
// C4273_b.cpp
// compile with: /W1 /clr /c
#include <stdio.h>
extern "C" int printf_s(const char *, ...);   // C4273
```
