---
title: interface class (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- interface_CPP
helpviewer_keywords:
- interface class keyword
- interface struct keyword
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
ms.openlocfilehash: 8a637332110fa18a7a5803d7512c643e29d66eab
ms.sourcegitcommit: 68ae6f9ea17f32734b32bb06ffeec12d8d33f0fe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87807749"
---
# <a name="interface-class--ccli-and-ccx"></a>interface class (C++/CLI и C++/CX)

Объявляет интерфейс.  Дополнительные сведения о собственных интерфейсах см. в разделе [__interface](../cpp/interface.md).

## <a name="all-runtimes"></a>Все среды выполнения

### <a name="syntax"></a>Синтаксис

```cpp
interface_access interface class name : inherit_access base_interface {};
interface_access interface struct name : inherit_access base_interface {};
```

### <a name="parameters"></a>Параметры

*interface_access*<br/>
Доступность интерфейса за пределами данной сборки.  Возможные значения: **`public`** и **`private`** .  **`private`** значение по умолчанию —. Вложенные интерфейсы не могут содержать спецификатор *interface_access*.

*name*<br/>
Имя интерфейса.

*inherit_access*<br/>
Доступность *base_interface*.  Единственным разрешенным доступом к базовому интерфейсу является **`public`** (по умолчанию).

*base_interface*<br/>
(Необязательно) Базовый интерфейс для *имени* интерфейса.

### <a name="remarks"></a>Примечания

**interface struct** — это эквивалент **interface class**.

Интерфейс может содержать объявления для функций, событий и свойств.  Все элементы интерфейса имеют специальные возможности уровня public. Интерфейс также может содержать статические элементы данных, функции, события и свойства. Статические элементы должны быть определены в интерфейсе.

Интерфейс определяет, каким образом можно реализовать класс. Интерфейс не является классом, а классы могут только реализовывать интерфейсы. Если класс определяет функцию, представленную в интерфейсе, функция реализовывается без переопределения. Таким образом поиск по имени не включает в себя элементы интерфейса.

Класс или структура, которые является производными от интерфейса, должны реализовывать все элементы интерфейса. При реализации *имени* интерфейса необходимо также реализовать интерфейсы из списка `base_interface`.

Дополнительные сведения можно найти в разделе

- [Практическое руководство. Определение статического конструктора интерфейса (C++выполняет)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)

- [Универсальные интерфейсы (C++/CLI)](generic-interfaces-visual-cpp.md)

Сведения о других типах среды CLR см. в статье о [классах и структурах](classes-and-structs-cpp-component-extensions.md).

Во время компиляции можно определить, является ли тип интерфейсом, с помощью `__is_interface_class(type)`. Дополнительные сведения см. в статье [Compiler Support for Type Traits (C++/CLI and C++/CX)](compiler-support-for-type-traits-cpp-component-extensions.md) (Поддержка характеристик типов компилятором (C++/CLI and C++/CX)).

В среде разработки можно получить справку F1 по этим ключевым словам, выделив ключевое слово ( **`interface class`** например,) и нажав клавишу F1.

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="remarks"></a>Примечания

(Отсутствуют комментарии для этой возможности языка, которая применяется только в среде выполнения Windows).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

### <a name="remarks"></a>Примечания

(Отсутствуют комментарии для этой возможности языка, которая применяется только в среде CLR).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере кода демонстрируется, как интерфейс может определять поведение функции часов.

```cpp
// mcppv2_interface_class.cpp
// compile with: /clr
using namespace System;

public delegate void ClickEventHandler(int, double);

// define interface with nested interface
public interface class Interface_A {
   void Function_1();

   interface class Interface_Nested_A {
      void Function_2();
   };
};

// interface with a base interface
public interface class Interface_B : Interface_A {
   property int Property_Block;
   event ClickEventHandler^ OnClick;
   static void Function_3() { Console::WriteLine("in Function_3"); }
};

// implement nested interface
public ref class MyClass : public Interface_A::Interface_Nested_A {
public:
   virtual void Function_2() { Console::WriteLine("in Function_2"); }
};

// implement interface and base interface
public ref class MyClass2 : public Interface_B {
private:
   int MyInt;

public:
   // implement non-static function
   virtual void Function_1() { Console::WriteLine("in Function_1"); }

   // implement property
   property int Property_Block {
      virtual int get() { return MyInt; }
      virtual void set(int value) { MyInt = value; }
   }
   // implement event
   virtual event ClickEventHandler^ OnClick;

   void FireEvents() {
      OnClick(7, 3.14159);
   }
};

// class that defines method called when event occurs
ref class EventReceiver {
public:
   void OnMyClick(int i, double d) {
      Console::WriteLine("OnClick: {0}, {1}", i, d);
   }
};

int main() {
   // call static function in an interface
   Interface_B::Function_3();

   // instantiate class that implements nested interface
   MyClass ^ x = gcnew MyClass;
   x->Function_2();

   // instantiate class that implements interface with base interface
   MyClass2 ^ y = gcnew MyClass2;
   y->Function_1();
   y->Property_Block = 8;
   Console::WriteLine(y->Property_Block);

   EventReceiver^ MyEventReceiver = gcnew EventReceiver();

   // hook handler to event
   y->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);

   // invoke events
   y->FireEvents();

   // unhook handler to event
   y->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);

   // call implemented function via interface handle
   Interface_A^ hi = gcnew MyClass2();
   hi->Function_1();
}
```

```Output
in Function_3

in Function_2

in Function_1

8

OnClick: 7, 3.14159

in Function_1
```

В следующем примере кода показаны два способа реализации функций с одной и той же сигнатурой, объявленной в нескольких интерфейсах, и где эти интерфейсы используются классом.

```cpp
// mcppv2_interface_class_2.cpp
// compile with: /clr /c
interface class I {
   void Test();
   void Test2();
};

interface class J : I {
   void Test();
   void Test2();
};

ref struct R : I, J {
   // satisfies the requirement to implement Test in both interfaces
   virtual void Test() {}

   // implement both interface functions with explicit overrides
   virtual void A() = I::Test2 {}
   virtual void B() = J::Test2 {}
};
```

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
