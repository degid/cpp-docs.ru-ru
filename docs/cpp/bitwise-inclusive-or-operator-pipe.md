---
title: 'Оператор побитового инклюзивного или: &#124;'
description: Побитовый оператор или синтаксис оператора на языке C++ Standard, а также использование.
ms.date: 07/23/2020
f1_keywords:
- '|'
- bitor_cpp
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
ms.openlocfilehash: 76f80c2101b3acfac71dc4d8ad1be4a999f69aa5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229094"
---
# <a name="bitwise-inclusive-or-operator-124"></a>Оператор побитового инклюзивного или: &#124;

## <a name="syntax"></a>Синтаксис

> *expression1* **`|`** *expression2*

## <a name="remarks"></a>Примечания

Оператор побитового включающего или ( **`|`** ) сравнивает каждый бит своего первого операнда с соответствующим битом второго операнда. Если любой из битов равен единице, соответствующий бит результата устанавливается равным единице, а в противном случае — нулю.

Оба операнда оператора должны иметь целочисленные типы. Обычные арифметические преобразования, охваченные [стандартными](standard-conversions.md) преобразованиями, применяются к операндам.

## <a name="operator-keyword-for-124"></a>Ключевое слово оператора для &#124;

C++ указывает на **`bitor`** альтернативное написание для **`|`** . В языке C в качестве макроса в заголовке указывается альтернативное написание \<iso646.h> . В C++ альтернативным написанием является ключевое слово; использование \<iso646.h> или эквивалент C++ \<ciso646> не рекомендуется. В Microsoft C++ [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора или необходим для включения альтернативного написания.

## <a name="example"></a>Пример

```cpp
// expre_Bitwise_Inclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise inclusive OR
#include <iostream>
using namespace std;

int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...
}
```

## <a name="see-also"></a>См. также раздел

[Встроенные операторы, приоритет и ассоциативность C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Побитовые операторы в C](../c-language/c-bitwise-operators.md)
