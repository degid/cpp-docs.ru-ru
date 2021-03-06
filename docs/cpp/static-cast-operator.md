---
title: Оператор static_cast
ms.date: 11/04/2016
f1_keywords:
- static_cast_cpp
helpviewer_keywords:
- static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
ms.openlocfilehash: 8551d41417647ee4f759e2547e2c1909c59d78cd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213207"
---
# <a name="static_cast-operator"></a>Оператор static_cast

Преобразует *выражение* в тип *типа-ID,* основанный только на типах, имеющихся в выражении.

## <a name="syntax"></a>Синтаксис

```
static_cast <type-id> ( expression )
```

## <a name="remarks"></a>Примечания

В стандартном языке C++, проверка типа во время выполнения не выполняется, что обеспечивает безопасность преобразования. В C ++/CX выполняются проверки во время компиляции и во время выполнения. Дополнительные сведения см. в разделе [Приведение](casting.md).

**`static_cast`** Оператор можно использовать для таких операций, как преобразование указателя на базовый класс в указатель на производный класс. Такие преобразования не всегда являются безопасными.

В целом, **`static_cast`** Если требуется преобразовать числовые типы данных, такие как enums, в ints или ints в float, а также вы уверены, какие типы данных участвуют в преобразовании. **`static_cast`** преобразования не так надежны **`dynamic_cast`** , как преобразования, поскольку не **`static_cast`** выполняет проверку типов во время выполнения **`dynamic_cast`** . В случае **`dynamic_cast`** неоднозначного указателя произойдет сбой, а **`static_cast`** возвращается, как если бы ничего не возникало. это может быть опасно. Хотя **`dynamic_cast`** преобразования являются более безопасными, **`dynamic_cast`** работают только с указателями или ссылками, а проверка типов во время выполнения является дополнительной нагрузкой. Дополнительные сведения см. в разделе [оператор dynamic_cast](../cpp/dynamic-cast-operator.md).

В следующем примере строка `D* pd2 = static_cast<D*>(pb);` небезопасна, поскольку `D` может иметь поля и методы, не входящие в `B`. Однако строка `B* pb2 = static_cast<B*>(pd);` является безопасным преобразованием, поскольку `D` всегда содержит все `B`.

```cpp
// static_cast_Operator.cpp
// compile with: /LD
class B {};

class D : public B {};

void f(B* pb, D* pd) {
   D* pd2 = static_cast<D*>(pb);   // Not safe, D can have fields
                                   // and methods that are not in B.

   B* pb2 = static_cast<B*>(pd);   // Safe conversion, D always
                                   // contains all of B.
}
```

В отличие от [dynamic_cast](../cpp/dynamic-cast-operator.md), при преобразовании не выполняется проверка во время выполнения **`static_cast`** `pb` . Объект, на который указывает `pb`, может не быть объектом типа `D`, и в этом случае использование `*pd2` может привести ужасным последствиям. Например, вызов функции, являющейся членом класса `D`, но не класса `B`, может привести к нарушению прав доступа.

**`dynamic_cast`** Операторы и **`static_cast`** перемещают указатель на всю иерархию классов. Однако **`static_cast`** полагается исключительно на информацию, предоставленную в инструкции CAST, и поэтому может быть ненадежной. Пример:

```cpp
// static_cast_Operator_2.cpp
// compile with: /LD /GR
class B {
public:
   virtual void Test(){}
};
class D : public B {};

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);
   D* pd2 = static_cast<D*>(pb);
}
```

Если `pb` действительно указывает на объект типа `D`, `pd1` и `pd2` получат одно и то же значение. Также они получат одно и то же значение, если `pb == 0`.

Если `pb` указывает на объект типа, `B` а не на полный `D` класс, то **`dynamic_cast`** будет достаточно, чтобы вернуть ноль. Однако **`static_cast`** полагается на утверждение программиста, которое `pb` указывает на объект типа `D` и просто возвращает указатель на этот предполагаемый `D` объект.

Следовательно, **`static_cast`** может выполнить обратное преобразование неявных преобразований, в этом случае результаты будут неопределенными. Программисту остается убедиться, что результаты **`static_cast`** преобразования являются надежными.

Это поведение также применяется к типам, отличным от типов класса. Например, **`static_cast`** можно использовать для преобразования из типа int в **`char`** . Однако в результате **`char`** может быть недостаточно битов для хранения всего **`int`** значения. Опять же, программисту остается убедиться, что результаты **`static_cast`** преобразования являются надежными.

**`static_cast`** Оператор также можно использовать для выполнения любого неявного преобразования, включая стандартные преобразования и пользовательские преобразования. Пример:

```cpp
// static_cast_Operator_3.cpp
// compile with: /LD /GR
typedef unsigned char BYTE;

void f() {
   char ch;
   int i = 65;
   float f = 2.5;
   double dbl;

   ch = static_cast<char>(i);   // int to char
   dbl = static_cast<double>(f);   // float to double
   i = static_cast<BYTE>(ch);
}
```

**`static_cast`** Оператор может явно преобразовать целочисленное значение в тип перечисления. Если значение типа целого не оказывается в диапазоне значений перечисления, получаемое значение перечисления не определено.

**`static_cast`** Оператор преобразует нулевое значение указателя в значение указателя null целевого типа.

Любое выражение может быть явно преобразовано в тип void **`static_cast`** оператором. Тип void назначения может дополнительно включать **`const`** **`volatile`** атрибут, или **`__unaligned`** .

**`static_cast`** Оператор не может привести к отделам **`const`** **`volatile`** атрибуты, или **`__unaligned`** . Сведения об удалении этих атрибутов см. в разделе [оператор const_cast](../cpp/const-cast-operator.md) .

**C++/CLI:** Из-за опасности возникновения непроверенных приведений на вершине повторного обнаружения сборщика мусора использование класса **`static_cast`** должно быть только в критическом для производительности коде, только если вы уверены, что он будет работать правильно. Если необходимо использовать **`static_cast`** в режиме выпуска, замените его [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) в отладочных сборках, чтобы убедиться в успешном выполнении.

## <a name="see-also"></a>См. также раздел

[Операторы приведения](../cpp/casting-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
