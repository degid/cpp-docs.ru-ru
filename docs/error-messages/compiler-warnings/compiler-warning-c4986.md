---
title: Предупреждение компилятора C4986
ms.date: 11/04/2016
f1_keywords:
- C4986
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
ms.openlocfilehash: ae782ea0a11bd72c867ea9532a62d0b14cd98453
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684396"
---
# <a name="compiler-warning-c4986"></a>Предупреждение компилятора C4986

"функция": спецификация исключения не соответствует предыдущему объявлению

Это предупреждение может быть создано при наличии спецификации исключения в одном объявлении, а не в другом.

По умолчанию C4986 отключен. Дополнительные сведения см. в разделе [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C4986.

```cpp
class X { };
void f1() throw (X*);
// ...
void f1()
{
    // ...
}
```

Следующий пример устраняет это предупреждение.

```cpp
class X { };
void f1() throw (X*);
// ...
void f1() throw (X*)
{
    // ...
}
```
