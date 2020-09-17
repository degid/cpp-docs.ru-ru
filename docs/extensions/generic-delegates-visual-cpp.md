---
title: Универсальные методы-делегаты (C++/CLI)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- generic delegates
- delegates, generic [C++]
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
ms.openlocfilehash: 980beb21325e78baa9c6f3691f7b814c5266b79a
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686617"
---
# <a name="generic-delegates-ccli"></a>Универсальные методы-делегаты (C++/CLI)

Параметры универсального типа можно использовать с делегатами. Дополнительные сведения о делегатах (C++/CLI и C++/CX) см. [здесь](delegate-cpp-component-extensions.md).

## <a name="syntax"></a>Синтаксис

```cpp
[attributes]
generic < [class | typename] type-parameter-identifiers>
[type-parameter-constraints-clauses]
[accessibility-modifiers] delegate result-type identifier
([formal-parameters]);
```

### <a name="parameters"></a>Параметры

*attributes*<br/>
(Необязательно) Дополнительные описательные данные. Дополнительные сведения об атрибутах и классах атрибутов см. в разделе "Атрибуты".

*type-parameter-identifier(s)*<br/>
Разделенный запятыми список идентификаторов параметров типа.

*type-parameter-constraints-clauses*<br/>
Принимает вид, определенный в статье [Constraints on Generic Type Parameters (C++/CLI)](constraints-on-generic-type-parameters-cpp-cli.md) (Ограничения, применяемые к параметрам универсальных типов (C++/CLI)).

*accessibility-modifiers*<br/>
Используемых Модификаторы доступа (например **`public`** , **`private`** ).

*Тип результата*<br/>
Возвращаемый тип делегата.

*identifier*<br/>
Имя делегата.

*formal-parameters*<br/>
(Необязательно) Список параметров делегата.

## <a name="examples"></a>Примеры

Параметры типа делегата определяются в точке создания объекта делегата. Делегат и связанный с ним метод должны иметь одинаковую сигнатуру. В следующем примере показано объявление универсального делегата.

```cpp
// generics_generic_delegate1.cpp
// compile with: /clr /c
generic <class ItemType>
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);
```

В приведенном ниже примере показано, что:

- один и тот же объект делегата нельзя использовать с разными сконструированными типами; для разных типов следует создать разные объекты делегатов;

- универсальный делегат может быть связан с универсальным методом;

- если универсальный метод вызывается без указания аргументов типа, компилятор пытается определить аргументы типа для вызова.

```cpp
// generics_generic_delegate2.cpp
// compile with: /clr
generic <class ItemType>
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);

generic <class ItemType>
ref struct MyGenClass {
   ItemType MyMethod(ItemType i, ItemType % j) {
      return ItemType();
   }
};

ref struct MyClass {
   generic <class ItemType>
   static ItemType MyStaticMethod(ItemType i, ItemType % j) {
      return ItemType();
   }
};

int main() {
   MyGenClass<int> ^ myObj1 = gcnew MyGenClass<int>();
   MyGenClass<double> ^ myObj2 = gcnew MyGenClass<double>();
   GenDelegate<int>^ myDelegate1 =
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);

   GenDelegate<double>^ myDelegate2 =
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);

   GenDelegate<int>^ myDelegate =
      gcnew GenDelegate<int>(&MyClass::MyStaticMethod<int>);
}
```

В следующем примере объявляется универсальный делегат `GenDelegate<ItemType>`, а затем создается его экземпляр путем связывания с методом `MyMethod`, использующим параметр типа `ItemType`. Создаются и вызываются два экземпляра делегата (целое число и число двойной точности).

```cpp
// generics_generic_delegate.cpp
// compile with: /clr
using namespace System;

// declare generic delegate
generic <typename ItemType>
delegate ItemType GenDelegate (ItemType p1, ItemType% p2);

// Declare a generic class:
generic <typename ItemType>
ref class MyGenClass {
public:
   ItemType MyMethod(ItemType p1, ItemType% p2) {
      p2 = p1;
      return p1;
    }
};

int main() {
   int i = 0, j = 0;
   double m = 0.0, n = 0.0;

   MyGenClass<int>^ myObj1 = gcnew MyGenClass<int>();
   MyGenClass<double>^ myObj2 = gcnew MyGenClass<double>();

   // Instantiate a delegate using int.
   GenDelegate<int>^ MyDelegate1 =
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);

   // Invoke the integer delegate using MyMethod.
   i = MyDelegate1(123, j);

   Console::WriteLine(
      "Invoking the integer delegate: i = {0}, j = {1}", i, j);

   // Instantiate a delegate using double.
   GenDelegate<double>^ MyDelegate2 =
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);

   // Invoke the integer delegate using MyMethod.
   m = MyDelegate2(0.123, n);

   Console::WriteLine(
      "Invoking the double delegate: m = {0}, n = {1}", m, n);
}
```

```Output
Invoking the integer delegate: i = 123, j = 123
Invoking the double delegate: m = 0.123, n = 0.123
```

## <a name="see-also"></a>См. также

[Универсальные шаблоны](generics-cpp-component-extensions.md)
