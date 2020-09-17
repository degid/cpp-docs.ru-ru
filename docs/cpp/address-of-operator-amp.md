---
title: Оператор взятия адреса:&amp;
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
ms.openlocfilehash: 836802684e24c721f97dc4c5558d87b9a5e69bc8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227690"
---
# <a name="address-of-operator-amp"></a>Оператор взятия адреса:&amp;

## <a name="syntax"></a>Синтаксис

```
& cast-expression
```

## <a name="remarks"></a>Примечания

Унарный оператор взятия адреса ( **&** ) принимает адрес своего операнда. Операнд оператора взятия адреса может быть либо указателем функции, либо l-значением, обозначающим объект, который не является битовым полем.

Оператор взятия адреса может применяться только к переменным фундаментального типа или типа структуры, класса или объединения, которые были объявлены в области видимости файла, а также к ссылкам на массив с индексом. В таких выражениях из выражения взятия адреса можно вычитать (или прибавлять к нему) константное выражение, которое не содержит выражения взятия адреса.

Если этот оператор применяется к функциям или l-значениям, то результатом является тип указателя (r-значение), производный от типа операнда. Например, если операнд имеет тип **`char`** , результат выражения будет иметь тип pointer, равный **`char`** . Оператор взятия адреса, применяемый к **`const`** **`volatile`** объектам или, принимает значение `const type *` или `volatile type *` , где **Type** — это тип исходного объекта.

Если оператор взятия адреса применяется к полному имени, результат зависит от того, указывает ли *полное имя* на статический член. Если да, то результатом является указатель на тип, заданный в определении этого члена. Если элемент не является статическим, результатом является указатель на *имя* члена класса, указанного в *квалификаторе квалифицированного имени класса*. ( *Полное имя класса*см. в разделе [основные выражения](../cpp/primary-expressions.md) .) В следующем фрагменте кода показано, как результат отличается в зависимости от того, является ли элемент статическим:

```cpp
// expre_Address_Of_Operator.cpp
// C2440 expected
class PTM {
public:
    int iValue;
    static float fValue;
};

int main() {
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static
   float *spfValue     = &PTM::fValue;  // OK
}
```

В этом примере выражение `&PTM::fValue` имеет результатом тип `float *`, а не `float PTM::*`, поскольку `fValue` является статическим членом.

Адрес перегруженной функции можно принимать только в том случае, если очевидно, к какой именно версии этой функции привязана ссылка. Сведения о получении адреса определенной перегруженной функции см. в разделе [Перегрузка функции](function-overloading.md) .

Применение оператора взятия адреса к типу ссылки дает тот же результат, что и применение к объекту, к которому привязана ссылка. Пример:

## <a name="example"></a>Пример

```cpp
// expre_Address_Of_Operator2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
int main() {
   double d;        // Define an object of type double.
   double& rd = d;  // Define a reference to the object.

   // Obtain and compare their addresses
   if( &d == &rd )
      cout << "&d equals &rd" << endl;
}
```

## <a name="output"></a>Выходные данные

```Output
&d equals &rd
```

В следующем примере оператор взятия адреса используется для того, чтобы передать указатель в качестве аргумента функции:

```cpp
// expre_Address_Of_Operator3.cpp
// compile with: /EHsc
// Demonstrate address-of operator &

#include <iostream>
using namespace std;

// Function argument is pointer to type int
int square( int *n ) {
   return (*n) * (*n);
}

int main() {
   int mynum = 5;
   cout << square( &mynum ) << endl;   // pass address of int
}
```

## <a name="output"></a>Вывод

```Output
25
```

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Декларатор ссылки Lvalue: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Операторы косвенного обращения и адреса](../c-language/indirection-and-address-of-operators.md)
