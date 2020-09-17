---
title: Оператор const_cast
ms.date: 11/04/2016
f1_keywords:
- const_cast_cpp
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
ms.openlocfilehash: 36de296d1e871ca759108497922973ddea8e3382
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227560"
---
# <a name="const_cast-operator"></a>Оператор const_cast

Удаляет **`const`** атрибуты, **`volatile`** и **`__unaligned`** из класса.

## <a name="syntax"></a>Синтаксис

```
const_cast <type-id> (expression)
```

## <a name="remarks"></a>Примечания

Указатель на любой тип объекта или указатель на член данных можно явно преобразовать в тип, идентичный, за исключением **`const`** **`volatile`** **`__unaligned`** квалификаторов, и. Для указателей и ссылок результат будет указывать на исходный объект. Для указателей на данные-члены результат будет указывать на тот же член, что и исходный указатель (uncast) на данные-член. В зависимости от типа объекта, на который осуществляется ссылка, операция записи с помощью результирующего указателя, ссылки или указателя на данные-член может привести к неопределенному поведению.

Нельзя использовать **`const_cast`** оператор для непосредственного переопределения состояния константы константной переменной.

**`const_cast`** Оператор преобразует нулевое значение указателя в значение указателя null целевого типа.

## <a name="example"></a>Пример

```cpp
// expre_const_cast_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class CCTest {
public:
   void setNumber( int );
   void printNumber() const;
private:
   int number;
};

void CCTest::setNumber( int num ) { number = num; }

void CCTest::printNumber() const {
   cout << "\nBefore: " << number;
   const_cast< CCTest * >( this )->number--;
   cout << "\nAfter: " << number;
}

int main() {
   CCTest X;
   X.setNumber( 8 );
   X.printNumber();
}
```

В строке **`const_cast`** , содержащей, тип данных **`this`** указателя — `const CCTest *` . **`const_cast`** Оператор изменяет тип данных **`this`** указателя на `CCTest *` , позволяя `number` изменять элемент. Приведение выполняется только для оставшейся части оператора, в котором оно указано.

## <a name="see-also"></a>См. также статью

[Операторы приведения](../cpp/casting-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
