---
title: Ошибка компилятора C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: f217e0b94e27c0f85879e80b3ae887cb4f76f486
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216366"
---
# <a name="compiler-error-c2084"></a>Ошибка компилятора C2084

Функция "*функция*" уже имеет тело

Функция уже определена.

До Visual Studio 2002,

- Компилятор принимает несколько специализаций шаблонов, которые разрешаются в один и тот же фактический тип, хотя дополнительные определения никогда не будут доступны. Теперь компилятор обнаруживает эти несколько определений.

- **`__int32`** и **`int`** обрабатывались как отдельные типы. Теперь компилятор обрабатывает **`__int32`** как синоним для **`int`** . Это означает, что компилятор обнаруживает несколько определений, если функция перегружена в **`__int32`** и, **`int`** и выдает ошибку.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2084:

```cpp
// C2084.cpp
void Func(int);
void Func(int) {}   // define function
void Func(int) {}   // C2084 second definition
```

Чтобы исправить эту ошибку, Удалите повторяющееся определение:

```cpp
// C2084b.cpp
// compile with: /c
void Func(int);
void Func(int) {}
```
