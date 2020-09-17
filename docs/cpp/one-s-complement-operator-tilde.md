---
title: 'Оператор дополнения до единицы: ~'
description: Синтаксис и использование оператора дополнения для одного языка C++ Standard.
ms.date: 07/23/2020
f1_keywords:
- "~"
- compl_cpp
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
ms.openlocfilehash: 89c67855cd67df2af315cea941b487e7462889b2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227248"
---
# <a name="ones-complement-operator-"></a>Оператор дополнения до единицы: ~

## <a name="syntax"></a>Синтаксис

```cpp
~ cast-expression
```

## <a name="remarks"></a>Примечания

Оператор дополнения до единицы ( **`~`** ), иногда называемый оператором *побитового дополнения* , возвращает побитовое дополнение его операнда. То есть каждый бит, равный в операнде 1, в результате становится равным 0, а каждый бит, равный в операнде 0, в результате становится равным 1. Операнд оператора дополнения до единицы должен быть целочисленного типа.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора для ~

C++ указывает на **`compl`** альтернативное написание для **`~`** . В языке C в качестве макроса в заголовке указывается альтернативное написание \<iso646.h> . В C++ альтернативным написанием является ключевое слово; использование \<iso646.h> или эквивалент C++ \<ciso646> не рекомендуется. В Microsoft C++ [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора или необходим для включения альтернативного написания.

## <a name="example"></a>Пример

```cpp
// expre_One_Complement_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main () {
   unsigned short y = 0xFFFF;
   cout << hex << y << endl;
   y = ~y;   // Take one's complement
   cout << hex << y << endl;
}
```

В этом примере новое значение, присвоенное переменной `y`, является дополнением до единицы значения 0xFFFF без знака, т. е. значением 0x0000.

Над целочисленными операндами выполняется восходящее приведение целого типа. Тип операнда, который повышается до, является результирующим типом. Дополнительные сведения о целочисленном повышении см. в разделе [стандартные преобразования](standard-conversions.md).

## <a name="see-also"></a>См. также статью

[Выражения с унарными операторами](expressions-with-unary-operators.md)<br/>
[Встроенные операторы, приоритет и ассоциативность C++](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Унарные арифметические операторы](../c-language/unary-arithmetic-operators.md)
