---
title: Логический оператор AND:&amp;&amp;
description: Синтаксис операторов и использование логического оператора языка C++ Standard и.
ms.date: 07/23/2020
f1_keywords:
- '&&'
- and_cpp
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
ms.openlocfilehash: 431e76a2943c2373d6191f1fbe9f14c54cfaa6c1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223698"
---
# <a name="logical-and-operator-ampamp"></a>Логический оператор AND:&amp;&amp;

## <a name="syntax"></a>Синтаксис

> *выражение* **`&&`** *выражение*

## <a name="remarks"></a>Примечания

Логический оператор AND ( **&&** ) возвращает **`true`** значение, если оба операнда являются **`true`** и возвращают **`false`** в противном случае. Перед вычислением операнды неявно преобразуются в тип **`bool`** , а результат имеет тип **`bool`** . Логическое И имеет ассоциативность в направлении слева направо.

Операнды логического оператора AND не должны иметь одинаковый тип, но они должны иметь тип Boolean, интеграл или указатель. В качестве операндов часто используются реляционные выражения и выражения равенства.

Первый операнд полностью вычисляется и все побочные эффекты выполняются до того, как будет выполнено вычисление логического выражения и.

Второй операнд вычисляется только в том случае, если первый операнд принимает значение **`true`** (отличное от нуля). Эта оценка устраняет необходимость недостаточной оценки второго операнда, если логическое выражение и имеет значение **`false`** . Такое сокращенное вычисление можно использовать для предотвращения разыменования пустого указателя, как показано в следующем примере.

```cpp
char *pch = 0;
// ...
(pch) && (*pch = 'a');
```

Если `pch` имеет значение NULL (0), правая часть выражения никогда не вычисляется. Эта сокращенная Оценка делает назначение через пустой указатель невозможным.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора для &&

C++ указывает на **`and`** альтернативное написание для **`&&`** . В языке C в качестве макроса в заголовке указывается альтернативное написание \<iso646.h> . В C++ альтернативным написанием является ключевое слово; использование \<iso646.h> или эквивалент C++ \<ciso646> не рекомендуется. В Microsoft C++ [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора или необходим для включения альтернативного написания.

## <a name="example"></a>Пример

```cpp
// expre_Logical_AND_Operator.cpp
// compile with: /EHsc
// Demonstrate logical AND
#include <iostream>

using namespace std;

int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b && b < c yields "
         << (a < b && b < c) << endl
         << "The false expression "
         << "a > b && b < c yields "
         << (a > b && b < c) << endl;
}
```

## <a name="see-also"></a>См. также раздел

[Встроенные операторы, приоритет и ассоциативность C++](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Логические операторы в C](../c-language/c-logical-operators.md)
