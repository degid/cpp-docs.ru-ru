---
title: 'Оператор логического отрицания: !'
description: Синтаксис и использование оператора логического отрицания в стандартном языке C++.
ms.date: 07/23/2020
f1_keywords:
- '!'
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: fdd2e7a71b791375f898372d058a5eeb2afc59f1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223685"
---
# <a name="logical-negation-operator-"></a>Оператор логического отрицания: !

## <a name="syntax"></a>Синтаксис

> **`!`***приведение выражения*

## <a name="remarks"></a>Примечания

Оператор логического отрицания ( **`!`** ) меняет значение операнда на противоположное. Операнд должен иметь арифметический тип или тип указателя (либо выражение, результатом которого является арифметический тип или тип указателя). Операнд неявно преобразуется в тип **`bool`** . Результат имеет значение, **`true`** Если преобразованный операнд имеет значение **`false`** ; результат равен, **`false`** Если преобразованный операнд имеет значение **`true`** . Результат имеет тип **`bool`** .

Для выражения `e` унарное выражение `!e` эквивалентно выражению `(e == 0)` , за исключением случаев, когда задействованы перегруженные операторы.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора для!

C++ указывает на **`not`** альтернативное написание для **`!`** . В языке C в качестве макроса в заголовке указывается альтернативное написание \<iso646.h> . В C++ альтернативным написанием является ключевое слово; использование \<iso646.h> или эквивалент C++ \<ciso646> не рекомендуется. В Microsoft C++ [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора или необходим для включения альтернативного написания.

## <a name="example"></a>Пример

```cpp
// expre_Logical_NOT_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    if (!i)
        cout << "i is zero" << endl;
}
```

## <a name="see-also"></a>См. также раздел

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Встроенные операторы, приоритет и ассоциативность C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Унарные арифметические операторы](../c-language/unary-arithmetic-operators.md)<br/>
