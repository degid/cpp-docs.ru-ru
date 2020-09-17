---
title: 'Операторы равенства: == и !='
description: Синтаксис и неравенство и не равное оператору языка C++ Standard, а также использование.
ms.date: 07/23/2020
f1_keywords:
- '!='
- ==
- not_eq_cpp
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
ms.openlocfilehash: 567b83e99dce0354626f08a4788f1343314493b1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227547"
---
# <a name="equality-operators--and-"></a>Операторы равенства: == и !=

## <a name="syntax"></a>Синтаксис

> *выражение* **`==`** *выражение*\
> *выражение* **`!=`** *выражение*

## <a name="remarks"></a>Примечания

Бинарные операторы равенства сравнивают операнды для строгого равенства или неравенства.

Операторы равенства, равные ( **`==`** ) и не равные ( **`!=`** ), имеют более низкий приоритет, чем операторы отношения, но они ведут себя одинаково. Тип результата для этих операторов — **`bool`** .

Оператор Equal-to ( **`==`** ) возвращает **`true`** , если оба операнда имеют одинаковое значение; в противном случае возвращается **`false`** . Оператор "не равно" ( **`!=`** ) возвращает, **`true`** Если операнды имеют одинаковое значение; в противном случае возвращается **`false`** .

## <a name="operator-keyword-for-"></a>Ключевое слово оператора для! =

C++ указывает на **`not_eq`** альтернативное написание для **`!=`** . (Альтернативное написание для не предусмотрено **`==`** .) В языке C в качестве макроса в заголовке указывается альтернативное написание \<iso646.h> . В C++ альтернативным написанием является ключевое слово; использование \<iso646.h> или эквивалент C++ \<ciso646> не рекомендуется. В Microsoft C++ [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора или необходим для включения альтернативного написания.

## <a name="example"></a>Пример

```cpp
// expre_Equality_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main() {
   cout  << boolalpha
         << "The true expression 3 != 2 yields: "
         << (3 != 2) << endl
         << "The false expression 20 == 10 yields: "
         << (20 == 10) << endl;
}
```

Операторы равенства могут сравнивать указатели на члены одного типа. В таких сравнениях выполняются преобразования указателей на члены. Указатели на члены также можно сравнить с константным выражением, результатом которого является значение 0.

## <a name="see-also"></a>См. также статью

[Выражения с бинарными операторами](../cpp/expressions-with-binary-operators.md)<br/>
[Встроенные операторы C++, приоритет; и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Операторы отношения и равенства в C](../c-language/c-relational-and-equality-operators.md)
