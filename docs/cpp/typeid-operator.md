---
title: Оператор typeid
ms.date: 10/04/2019
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
ms.openlocfilehash: e17b88d81d9987ec586401e025e108cfbe88cb3b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223528"
---
# <a name="typeid-operator"></a>Оператор typeid

## <a name="syntax"></a>Синтаксис

```
typeid(type-id)
typeid(expression)
```

## <a name="remarks"></a>Примечания

**`typeid`** Оператор позволяет определить тип объекта во время выполнения.

Результатом **`typeid`** является `const type_info&` . Значение является ссылкой на `type_info` объект, представляющий либо *тип-ID* , либо тип *выражения*в зависимости от **`typeid`** используемой формы. Дополнительные сведения см. в разделе [класс type_info](../cpp/type-info-class.md).

**`typeid`** Оператор не работает с управляемыми типами (абстрактными деклараторами или экземплярами). Сведения о получении <xref:System.Type> указанного типа см. в разделе [typeid](../extensions/typeid-cpp-component-extensions.md).

**`typeid`** Оператор выполняет проверку во время выполнения, когда применяется к l-значению типа полиморфизма, где истинный тип объекта не может быть определен с помощью предоставленной статической информации. К таким случаям относятся следующие.

- Ссылка на класс

- Указатель, разыменование`*`

- Указатель в индексе ( `[ ]` ). (Нельзя использовать индекс с указателем на полиморфизм типа.)

Если *выражение* указывает на тип базового класса, но объект фактически является типом, производным от базового класса, то `type_info` ссылка на производный класс является результатом. *Выражение* должно указывать на полиморфизм типа (класс с виртуальными функциями). В противном случае результатом является `type_info` статический класс, на который ссылается *выражение*. Кроме того, указатель должен быть разыменован таким образом, чтобы использовался объект, на который он указывает. Без разыменования указателя результат будет `type_info` для указателя, а не того, на который он указывает. Например:

```cpp
// expre_typeid_Operator.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <typeinfo>

class Base {
public:
   virtual void vvfunc() {}
};

class Derived : public Base {};

using namespace std;
int main() {
   Derived* pd = new Derived;
   Base* pb = pd;
   cout << typeid( pb ).name() << endl;   //prints "class Base *"
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"
   delete pd;
}
```

Если *выражение* ссылается на указатель и значение этого указателя равно нулю, **`typeid`** вызывает [исключение bad_typeid](../cpp/bad-typeid-exception.md). Если указатель не указывает на допустимый объект, `__non_rtti_object` возникает исключение. Указывает, что попытка анализа RTTI, вызвавшего ошибку, вызвана тем, что объект является каким-то недопустимым. (Например, это неверный указатель, или код не был скомпилирован с помощью [/GR](../build/reference/gr-enable-run-time-type-information.md)).

Если *выражение* не является указателем, а не ссылкой на базовый класс объекта, результатом является `type_info` ссылка, представляющая статический тип *выражения*. *Статический тип* выражения ссылается на тип выражения, так как он известен во время компиляции. Семантика исполнения игнорируется при оценке статического типа выражения. Кроме того, ссылки по возможности игнорируются при определении статического типа выражения:

```cpp
// expre_typeid_Operator_2.cpp
#include <typeinfo>

int main()
{
   typeid(int) == typeid(int&); // evaluates to true
}
```

**`typeid`** также может использоваться в шаблонах для определения типа параметра шаблона:

```cpp
// expre_typeid_Operator_3.cpp
// compile with: /c
#include <typeinfo>
template < typename T >
T max( T arg1, T arg2 ) {
   cout << typeid( T ).name() << "s compared." << endl;
   return ( arg1 > arg2 ? arg1 : arg2 );
}
```

## <a name="see-also"></a>См. также статью

[Сведения о типах времени выполнения](../cpp/run-time-type-information.md)\
[Ключевые слова](../cpp/keywords-cpp.md)
