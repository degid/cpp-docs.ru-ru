---
title: Операторы доступа к членам:. и-&gt;
ms.date: 11/04/2016
f1_keywords:
- .
- ->
helpviewer_keywords:
- member access, expressions
- operators [C++], member access
- dot operator (.)
- -> operator
- member access, operators
- postfix operators [C++]
- . operator
- member access
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
ms.openlocfilehash: 05bab55e1646783e0f8ab9b414d608c912f60a0f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178019"
---
# <a name="member-access-operators--and--gt"></a>Операторы доступа к членам:. и-&gt;

## <a name="syntax"></a>Синтаксис

```
postfix-expression . name
postfix-expression -> name
```

## <a name="remarks"></a>Примечания

Операторы доступа к членам **.** и **->** используются для ссылки на члены структур, объединений и классов. Выражения доступа к членам имеют значение и тип выбранного члена.

Предусмотрено две формы выражения доступа к члену:

1. В первой форме *постфиксное выражение* представляет значение структуры, класса или типа объединения, а *имя Name* является членом указанной структуры, объединения или класса. Значением операции является *имя* и является l-значением, если *постфикс-выражение* является l-значением.

1. Во второй форме *постфиксное выражение* представляет указатель на структуру, объединение или класс, а *имя Name* является членом указанной структуры, объединения или класса. Значение равно *имени* и является l-значением. Оператор **->** отменяет ссылку на указатель. Таким образом, выражения `e->member` и `(*e).member` (где *e* представляет указатель) выдают идентичные результаты (за исключением случаев, когда операторы **->** или <strong>\*</strong> перегружены).

## <a name="example"></a>Пример

В следующем примере показаны обе формы оператора доступа к членам.

```cpp
// expre_Selection_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

struct Date {
   Date(int i, int j, int k) : day(i), month(j), year(k){}
   int month;
   int day;
   int year;
};

int main() {
   Date mydate(1,1,1900);
   mydate.month = 2;
   cout  << mydate.month << "/" << mydate.day
         << "/" << mydate.year << endl;

   Date *mydate2 = new Date(1,1,2000);
   mydate2->month = 2;
   cout  << mydate2->month << "/" << mydate2->day
         << "/" << mydate2->year << endl;
   delete mydate2;
}
```

```Output
2/1/1900
2/1/2000
```

## <a name="see-also"></a>См. также раздел

[Постфиксные выражения](../cpp/postfix-expressions.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Классы и структуры](../cpp/classes-and-structs-cpp.md)<br/>
[Члены структур и объединений](../c-language/structure-and-union-members.md)
