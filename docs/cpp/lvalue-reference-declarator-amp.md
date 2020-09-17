---
title: Декларатор ссылки lvalue:&amp;
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
ms.openlocfilehash: 30dd6ba9cb91395f72124cad71908a4e6bcdf7dd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225986"
---
# <a name="lvalue-reference-declarator-amp"></a>Декларатор ссылки lvalue:&amp;

Содержит адрес объекта, но синтаксически ведет себя подобно объекту.

## <a name="syntax"></a>Синтаксис

```
type-id & cast-expression
```

## <a name="remarks"></a>Примечания

Ссылку lvalue можно считать другим именем для объекта. Объявление ссылки lvalue состоит из необязательного списка спецификаторов, за которым следует декларатор ссылки. Ссылка должна быть инициализирована и не может быть изменена.

Любой объект, адрес которого можно преобразовать в некоторый тип указателя, можно также преобразовать в аналогичный ссылочный тип. Например, любой объект, адрес которого можно преобразовать в тип `char *`, можно также преобразовать в тип `char &`.

Не путайте объявления ссылок с использованием [оператора взятия адреса](../cpp/address-of-operator-amp.md). Если `&` *идентификатору* предшествует тип, например **`int`** или **`char`** , *идентификатор* объявляется как ссылка на тип. Когда `&` *идентификатору* не предшествует тип, использование является оператором взятия адреса.

## <a name="example"></a>Пример

В следующем примере демонстрируется декларатор ссылки путем объявления объекта `Person` и ссылки на этот объект. Поскольку `rFriend` является ссылкой на `myFriend`, при обновлении любой из этих переменных изменяется один и тот же объект.

```cpp
// reference_declarator.cpp
// compile with: /EHsc
// Demonstrates the reference declarator.
#include <iostream>
using namespace std;

struct Person
{
    char* Name;
    short Age;
};

int main()
{
   // Declare a Person object.
   Person myFriend;

   // Declare a reference to the Person object.
   Person& rFriend = myFriend;

   // Set the fields of the Person object.
   // Updating either variable changes the same object.
   myFriend.Name = "Bill";
   rFriend.Age = 40;

   // Print the fields of the Person object to the console.
   cout << rFriend.Name << " is " << myFriend.Age << endl;
}
```

```Output
Bill is 40
```

## <a name="see-also"></a>См. также статью

[Справочные материалы](../cpp/references-cpp.md)<br/>
[Аргументы функции ссылочного типа](../cpp/reference-type-function-arguments.md)<br/>
[Функции ссылочного типа возвращают](../cpp/reference-type-function-returns.md)<br/>
[Ссылки на указатели](../cpp/references-to-pointers.md)
