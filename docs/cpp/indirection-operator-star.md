---
title: 'Оператор косвенного обращения: *'
ms.date: 11/04/2016
helpviewer_keywords:
- '* operator'
- indirection operator
- operators [C++], indirection
- indirection operator [C++], syntax
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
ms.openlocfilehash: 8f27cfd943455d52b04c41ef2d2d83e6e03a84c0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178286"
---
# <a name="indirection-operator-"></a>Оператор косвенного обращения: *

## <a name="syntax"></a>Синтаксис

```
* cast-expression
```

## <a name="remarks"></a>Примечания

Унарный оператор косвенного обращения (<strong>\*</strong>) отменяет ссылку на указатель; то есть преобразует значение указателя в l-значение. Операнд косвенного оператора должен быть указателем на тип. Результат косвенного выражения — тип, производным которого является тип указателя. Использование оператора <strong>\*</strong> в этом контексте отличается от его значения бинарным оператором, что является умножением.

Если операнд указывает на функцию, результатом является указатель функции. Если он указывает на место хранения, результатом является l-значение, указывающее на место хранения.

Косвенный оператор может использоваться кумулятивно для разыменования указателей на указатели. Пример:

```cpp
// expre_Indirection_Operator.cpp
// compile with: /EHsc
// Demonstrate indirection operator
#include <iostream>
using namespace std;
int main() {
   int n = 5;
   int *pn = &n;
   int **ppn = &pn;

   cout  << "Value of n:\n"
         << "direct value: " << n << endl
         << "indirect value: " << *pn << endl
         << "doubly indirect value: " << **ppn << endl
         << "address of n: " << pn << endl
         << "address of n via indirection: " << *ppn << endl;
}
```

Если значение указателя недопустимо, результат становится неопределенным. Ниже приведены наиболее распространенные условия, при которых значение указателя становится недопустимым.

- Указатель является пустым указателем.

- Указатель определяет адрес локального элемента, не видимого во время обращения.

- Указатель определяет адрес, выравнивание которого не подходит для типа указываемого объекта.

- Указатель определяет адрес, который не используется выполняемой программой.

## <a name="see-also"></a>См. также раздел

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Оператор address-of: &](../cpp/address-of-operator-amp.md)<br/>
[Операторы косвенного обращения и адреса операнда](../c-language/indirection-and-address-of-operators.md)
