---
title: Универсальные классы (C++/CLI)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- classes [C++], generic
- generic classes [C++], about generic classes
- data types [C++], generic
- generic classes
- generics [C++], declaring generic classes
ms.assetid: 0beb99e1-1ec4-4fee-9836-ce9657d67a3a
ms.openlocfilehash: 894bbffcc73693e5d0976831d65df54b09c853d2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216028"
---
# <a name="generic-classes-ccli"></a>Универсальные классы (C++/CLI)

Универсальный класс объявляется в следующем формате:

## <a name="syntax"></a>Синтаксис

```cpp
[attributes]
generic <class-key type-parameter-identifier(s)>
[constraint-clauses]
[accessibility-modifiers] ref class identifier  [modifiers]
[: base-list]
{
class-body
} [declarators] [;]
```

## <a name="remarks"></a>Примечания

В приведенном синтаксисе используются следующие элементы.

*attributes*<br/>
(Необязательно) Дополнительные описательные данные. Дополнительные сведения об атрибутах и классах атрибутов см. в разделе "Атрибуты".

*class-key*<br/>
Либо **`class`****`typename`**

*type-parameter-identifier(s)*  — разделенный запятыми список идентификаторов, определяющих имена параметров типа.

*constraint-clauses*<br/>
Список (не разделенный запятыми) предложений **where**, определяющих ограничения параметров типа. Имеет следующий вид:

> **где** *Type-Parameter-идентификатор* **:** *constraint-List*  **...**

*constraint-list*<br/>
*Class-или-Interface*[ `,` *...*]

*accessibility-modifiers*<br/>
Модификаторы доступа для универсального класса. Для среда выполнения Windows единственным допустимым модификатором является **`private`** . Для среды CLR допустимые модификаторы: **`private`** и **`public`** .

*identifier*<br/>
Имя универсального класса — любой допустимый идентификатор C++.

*модификаторы*<br/>
(Необязательно) Допустимые модификаторы: **sealed** и **abstract**.

*base-list*<br/>
Список, содержащий один базовый класс и любые реализованные интерфейсы, разделенные запятыми.

*class-body*<br/>
Тело класса, содержащее поля, функции-члены и т. д.

*declarators*<br/>
Объявления любых переменных данного типа. Например: `^` *identifier*[ `,` ...]

Можно объявлять универсальные классы, такие как (Обратите внимание, что **`class`** вместо) может использоваться ключевое слово **`typename`** . В этом примере `ItemType`, `KeyType` и `ValueType` — это неизвестные типы, определенные в типах. `HashTable<int, int>` — сконструированный тип универсального типа `HashTable<KeyType, ValueType>`. Из одного универсального типа можно создать несколько разных сконструированных типов. Сконструированные типы, созданные из универсальных классов, обрабатываются так же, как и любой другой тип ссылочного класса.

```cpp
// generic_classes_1.cpp
// compile with: /clr
using namespace System;
generic <typename ItemType>
ref struct Stack {
   // ItemType may be used as a type here
   void Add(ItemType item) {}
};

generic <typename KeyType, typename ValueType>
ref class HashTable {};

// The keyword class may be used instead of typename:
generic <class ListItem>
ref class List {};

int main() {
   HashTable<int, Decimal>^ g1 = gcnew HashTable<int, Decimal>();
}
```

**`int`** **`double`** В качестве аргумента универсального типа можно использовать оба типа значений (встроенные типы, такие как или, или определяемые пользователем типы значений) и ссылочные типы. Синтаксис в рамках универсального определения одинаково независим. Синтаксически неизвестный тип обрабатывается так, как если бы он был ссылочным типом. Однако среда выполнения может определить, является ли фактически используемый тип типом значения, и подставить соответствующий созданный код для прямого доступа к членам. Типы значений, используемые в качестве аргументов универсального типа, не упаковываются и поэтому снижение производительности, связанное с упаковкой-преобразованием, не оказывает на них негативного влияния. В теле универсального шаблона необходимо использовать синтаксис `T^` и `->` вместо `.`. Любое использование [ref new, gcnew](ref-new-gcnew-cpp-component-extensions.md) для типа параметра будет соответственно интерпретироваться средой выполнения как простое создание типа значения, если аргумент типа является типом значения.

Можно также объявить универсальный класс с [ограничениями для параметров универсального типа (C++/CLI)](constraints-on-generic-type-parameters-cpp-cli.md) для типов, которые могут использоваться для параметра типа. В следующем примере любой тип, используемый для `ItemType`, должен реализовывать интерфейс `IItem`. Попытка использовать **`int`** , например, не реализующая `IItem` , вызовет ошибку времени компиляции, так как аргумент типа не удовлетворяет ограничению.

```cpp
// generic_classes_2.cpp
// compile with: /clr /c
interface class IItem {};
generic <class ItemType>
where ItemType : IItem
ref class Stack {};
```

Универсальные классы в одном пространстве имен не могут быть перегружены только изменением числа или типов параметров типа. Однако, если все классы находятся в разных пространствах имен, они могут быть перегружены. Например, рассмотрим два класса — `MyClass` и `MyClass<ItemType>` — в пространствах имен `A` и `B`. Эти два класса могут быть перегружены в третьем пространстве имен C.

```cpp
// generic_classes_3.cpp
// compile with: /clr /c
namespace A {
   ref class MyClass {};
}

namespace B {
   generic <typename ItemType>
   ref class MyClass2 { };
}

namespace C {
   using namespace A;
   using namespace B;

   ref class Test {
      static void F() {
         MyClass^ m1 = gcnew MyClass();   // OK
         MyClass2<int>^ m2 = gcnew MyClass2<int>();   // OK
      }
   };
}
```

Базовый класс и базовые интерфейсы не могут быть параметрами типа. Однако базовый класс может содержать параметр типа в качестве аргумента, как показано в следующем примере.

```cpp
// generic_classes_4.cpp
// compile with: /clr /c
generic <typename ItemType>
interface class IInterface {};

generic <typename ItemType>
ref class MyClass : IInterface<ItemType> {};
```

Конструкторы и деструкторы выполняются один раз для каждого экземпляра объекта (как обычно); статические конструкторы выполняются один раз для каждого сконструированного типа.

## <a name="fields-in-generic-classes"></a>Поля в универсальных классах

В этом разделе показано использование экземпляра и статических полей в универсальных классах.

### <a name="instance-variables"></a>Переменные экземпляра

Переменные экземпляра универсального класса могут иметь типы и инициализаторы переменных, в том числе любые параметры типа из включающего класса.

## <a name="example"></a>Пример

В следующем примере три различных экземпляра универсального класса (MyClass \<ItemType> ) создаются с помощью соответствующих аргументов типа ( **`int`** , **`double`** и **String**).

```cpp
// generics_instance_fields1.cpp
// compile with: /clr
// Instance fields on generic classes
using namespace System;

generic <typename ItemType>
ref class MyClass {
// Field of the type ItemType:
public :
   ItemType field1;
   // Constructor using a parameter of the type ItemType:
   MyClass(ItemType p) {
   field1 = p;
   }
};

int main() {
   // Instantiate an instance with an integer field:
   MyClass<int>^ myObj1 = gcnew MyClass<int>(123);
   Console::WriteLine("Integer field = {0}", myObj1->field1);

   // Instantiate an instance with a double field:
   MyClass<double>^ myObj2 = gcnew MyClass<double>(1.23);
   Console::WriteLine("Double field = {0}", myObj2->field1);

   // Instantiate an instance with a String field:
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>("ABC");
   Console::WriteLine("String field = {0}", myObj3->field1);
   }
```

```Output
Integer field = 123
Double field = 1.23
String field = ABC
```

## <a name="static-variables"></a>Статические переменные

При создании универсального типа создаются новые экземпляры всех статических переменных и выполняется любой статический конструктор для данного типа.

Статические переменные могут использовать любые параметры типа из включающего класса.

## <a name="example"></a>Пример

В следующем примере показано использование статических полей и статического конструктора в универсальном классе.

```cpp
// generics_static2.cpp
// compile with: /clr
using namespace System;

interface class ILog {
   void Write(String^ s);
};

ref class DateTimeLog : ILog {
public:
   virtual void Write(String^ s) {
      Console::WriteLine( "{0}\t{1}", DateTime::Now, s);
   }
};

ref class PlainLog : ILog {
public:
   virtual void Write(String^ s) { Console::WriteLine(s); }
};

generic <typename LogType>
where LogType : ILog
ref class G {
   static LogType s_log;

public:
   G(){}
   void SetLog(LogType log) { s_log = log; }
   void F() { s_log->Write("Test1"); }
   static G() { Console::WriteLine("Static constructor called."); }
};

int main() {
   G<PlainLog^>^ g1 = gcnew G<PlainLog^>();
   g1->SetLog(gcnew PlainLog());
   g1->F();

   G<DateTimeLog^>^ g2 = gcnew G<DateTimeLog^>();
   g2->SetLog(gcnew DateTimeLog());

   // prints date
   // g2->F();
}
```

```Output
Static constructor called.
Static constructor called.
Static constructor called.
Test1
```

## <a name="methods-in-generic-classes"></a>Методы в универсальных классах

Методы в универсальных классах сами могут быть универсальными; неуниверсальные методы будут неявно параметризованы параметром типа класса.

Для методов в универсальных классах применяются следующие специальные правила.

- Методы в универсальных классах могут использовать параметры типа в качестве параметров, возвращаемых типов или локальных переменных.

- Методы в универсальных классах могут использовать открытые или закрытые сконструированные типы в качестве параметров, возвращаемых типов или локальных переменных.

### <a name="non-generic-methods-in-generic-classes"></a>Неуниверсальные методы в универсальных классах

Методы в универсальных классах, не имеющие дополнительных параметров типа, обычно называются неуниверсальными, хотя неявно параметризуются включающим универсальным классом.

В сигнатуре неуниверсального метода может присутствовать один или несколько параметров типа включающего класса непосредственно или в виде открытого сконструированного типа. Пример:

`void MyMethod(MyClass<ItemType> x) {}`

Эти параметры типа также могут использоваться в теле таких методов.

## <a name="example"></a>Пример

В приведенном ниже примере объявляется неуниверсальный метод `ProtectData` внутри универсального класса `MyClass<ItemType>`. В сигнатуре этого метода в открытом сконструированном типе используется параметр типа класса `ItemType`.

```cpp
// generics_non_generic_methods1.cpp
// compile with: /clr
// Non-generic methods within a generic class.
using namespace System;

generic <typename ItemType>
ref class MyClass {
public:
   String^ name;
   ItemType data;

   MyClass(ItemType x) {
      data = x;
   }

   // Non-generic method using the type parameter:
   virtual void ProtectData(MyClass<ItemType>^ x) {
      data = x->data;
   }
};

// ItemType defined as String^
ref class MyMainClass: MyClass<String^> {
public:
   // Passing "123.00" to the constructor:
   MyMainClass(): MyClass<String^>("123.00") {
      name = "Jeff Smith";
   }

   virtual void ProtectData(MyClass<String^>^ x) override {
      x->data = String::Format("${0}**", x->data);
   }

   static void Main() {
      MyMainClass^ x1 = gcnew MyMainClass();

      x1->ProtectData(x1);
      Console::WriteLine("Name: {0}", x1->name);
      Console::WriteLine("Amount: {0}", x1->data);
   }
};

int main() {
   MyMainClass::Main();
}
```

```Output
Name: Jeff Smith
Amount: $123.00**
```

## <a name="generic-methods-in-generic-classes"></a>Универсальные методы в универсальных классах

Универсальные методы можно объявлять в универсальных и неуниверсальных классах. Пример:

## <a name="example"></a>Пример

```cpp
// generics_method2.cpp
// compile with: /clr /c
generic <typename Type1>
ref class G {
public:
   // Generic method having a type parameter
   // from the class, Type1, and its own type
   // parameter, Type2
   generic <typename Type2>
   void Method1(Type1 t1, Type2 t2) { F(t1, t2); }

   // Non-generic method:
   // Can use the class type param, Type1, but not Type2.
   void Method2(Type1 t1) { F(t1, t1); }

   void F(Object^ o1, Object^ o2) {}
};
```

Неуниверсальный метод является, однако, универсальным в том смысле, что он параметризуется параметром типа класса, но не содержит дополнительных параметров типа.

Все типы методов в универсальных классах могут быть универсальными, включая статические, экземплярные и виртуальные.

## <a name="example"></a>Пример

В приведенном ниже примере показано объявление и использование универсальных методов в универсальных классах.

```cpp
// generics_generic_method2.cpp
// compile with: /clr
using namespace System;
generic <class ItemType>
ref class MyClass {
public:
   // Declare a generic method member.
   generic <class Type1>
   String^ MyMethod(ItemType item, Type1 t) {
      return String::Concat(item->ToString(), t->ToString());
   }
};

int main() {
   // Create instances using different types.
   MyClass<int>^ myObj1 = gcnew MyClass<int>();
   MyClass<String^>^ myObj2 = gcnew MyClass<String^>();
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>();

   // Calling MyMethod using two integers.
   Console::WriteLine("MyMethod returned: {0}",
            myObj1->MyMethod<int>(1, 2));

   // Calling MyMethod using an integer and a string.
   Console::WriteLine("MyMethod returned: {0}",
            myObj2->MyMethod<int>("Hello #", 1));

   // Calling MyMethod using two strings.
   Console::WriteLine("MyMethod returned: {0}",
       myObj3->MyMethod<String^>("Hello ", "World!"));

   // generic methods can be called without specifying type arguments
   myObj1->MyMethod<int>(1, 2);
   myObj2->MyMethod<int>("Hello #", 1);
   myObj3->MyMethod<String^>("Hello ", "World!");
}
```

```Output
MyMethod returned: 12
MyMethod returned: Hello #1
MyMethod returned: Hello World!
```

## <a name="using-nested-types-in-generic-classes"></a>Использование вложенных типов в универсальных классах

Так же как и в обычных классах, в универсальном классе можно объявлять разные типы. Объявление вложенного класса неявно параметризуется параметрами типа объявления внешнего класса. Таким образом, для каждого сконструированного внешнего типа определяется отдельный вложенный класс. Например, в объявлении

```cpp
// generic_classes_5.cpp
// compile with: /clr /c
generic <typename ItemType>
ref struct Outer {
   ref class Inner {};
};
```

Тип `Outer<int>::Inner` не совпадает с типом `Outer<double>::Inner`.

Как и в случае с универсальными методами, в универсальных классах дополнительные параметры типа можно задавать для вложенных типов. Если во внутреннем и внешнем классах используются одинаковые имена параметров типа, параметр внутреннего типа скрывает параметр внешнего типа.

```cpp
// generic_classes_6.cpp
// compile with: /clr /c
generic <typename ItemType>
ref class Outer {
   ItemType outer_item;   // refers to outer ItemType

   generic <typename ItemType>
   ref class Inner {
      ItemType inner_item;   // refers to Inner ItemType
   };
};
```

Поскольку обратиться к параметру внешнего типа невозможно, компилятор в этой ситуации выдает предупреждение.

После именования сконструированных вложенных универсальных типов параметр внешнего типа не включается в список параметров внутреннего типа, даже если внутренний тип неявно параметризуется параметром внешнего типа. В приведенном выше случае имя сконструированного типа будет `Outer<int>::Inner<string>`.

В приведенном ниже примере показано создание и чтение связанного списка с помощью вложенных типов в универсальных классах.

## <a name="example"></a>Пример

```cpp
// generics_linked_list.cpp
// compile with: /clr
using namespace System;
generic <class ItemType>
ref class LinkedList {
// The node class:
public:
   ref class Node {
   // The link field:
   public:
      Node^ next;
      // The data field:
      ItemType item;
   } ^first, ^current;
};

ref class ListBuilder {
public:
   void BuildIt(LinkedList<double>^ list) {
      /* Build the list */
      double m[5] = {0.1, 0.2, 0.3, 0.4, 0.5};
      Console::WriteLine("Building the list:");

      for (int n=0; n<=4; n++) {
         // Create a new node:
         list->current = gcnew LinkedList<double>::Node();

         // Assign a value to the data field:
         list->current->item = m[n];

         // Set the link field "next" to be the same as
         // the "first" field:
         list->current->next = list->first;

         // Redirect "first" to the new node:
         list->first = list->current;

         // Display node's data as it builds:
         Console::WriteLine(list->current->item);
      }
   }

   void ReadIt(LinkedList<double>^ list) {
      // Read the list
      // Make "first" the "current" link field:
      list->current = list->first;
      Console::WriteLine("Reading nodes:");

      // Read nodes until current == null:
      while (list->current != nullptr) {
         // Display the node's data field:
         Console::WriteLine(list->current->item);

         // Move to the next node:
         list->current = list->current->next;
      }
   }
};

int main() {
   // Create a list:
   LinkedList<double>^ aList = gcnew LinkedList<double>();

   // Initialize first node:
   aList->first = nullptr;

   // Instantiate the class, build, and read the list:
   ListBuilder^ myListBuilder = gcnew ListBuilder();
   myListBuilder->BuildIt(aList);
   myListBuilder->ReadIt(aList);
}
```

```Output
Building the list:
0.1
0.2
0.3
0.4
0.5
Reading nodes:
0.5
0.4
0.3
0.2
0.1
```

## <a name="properties-events-indexers-and-operators-in-generic-classes"></a>Свойства, события, индексаторы и операторы в универсальных классах

- Свойства, события, индексаторы и операторы могут использовать параметры типа включающего универсального класса в качестве возвращаемых значений, параметров или локальных переменных, например, если `ItemType` является параметром типа класса:

    ```cpp
    public ItemType MyProperty {}
    ```

- Сами свойства, события, индексаторы и операторы не могут быть параметризованы.

## <a name="example"></a>Пример

В следующем примере показано объявление свойства экземпляра в универсальном классе.

```cpp
// generics_generic_properties1.cpp
// compile with: /clr
using namespace System;

generic <typename ItemType>
ref class MyClass {
private:
   property ItemType myField;

public:
   property ItemType MyProperty {
      ItemType get() {
         return myField;
      }
      void set(ItemType value) {
         myField = value;
      }
   }
};

int main() {
   MyClass<String^>^ c = gcnew MyClass<String^>();
   MyClass<int>^ c1 = gcnew MyClass<int>();

   c->MyProperty = "John";
   c1->MyProperty = 234;

   Console::Write("{0}, {1}", c->MyProperty, c1->MyProperty);
}
```

```Output
John, 234
```

## <a name="example"></a>Пример

В следующем примере показан универсальный класс с событием.

```cpp
// generics_generic_with_event.cpp
// compile with: /clr
// Declare a generic class with an event and
// invoke events.
using namespace System;

// declare delegates
generic <typename ItemType>
delegate void ClickEventHandler(ItemType);

// generic class that defines events
generic <typename ItemType>
ref class EventSource {
public:
   // declare the event OnClick
   event ClickEventHandler<ItemType>^ OnClick;
   void FireEvents(ItemType item) {
      // raises events
      OnClick(item);
   }
};

// generic class that defines methods that will called when
// event occurs
generic <typename ItemType>
ref class EventReceiver {
public:
   void OnMyClick(ItemType item) {
   Console::WriteLine("OnClick: {0}", item);
   }
};

int main() {
   EventSource<String^>^ MyEventSourceString =
                   gcnew EventSource<String^>();
   EventSource<int>^ MyEventSourceInt = gcnew EventSource<int>();
   EventReceiver<String^>^ MyEventReceiverString =
                   gcnew EventReceiver<String^>();
   EventReceiver<int>^ MyEventReceiverInt = gcnew EventReceiver<int>();

   // hook handler to event
   MyEventSourceString->OnClick += gcnew ClickEventHandler<String^>(
       MyEventReceiverString, &EventReceiver<String^>::OnMyClick);
   MyEventSourceInt->OnClick += gcnew ClickEventHandler<int>(
             MyEventReceiverInt, &EventReceiver<int>::OnMyClick);

   // invoke events
   MyEventSourceString->FireEvents("Hello");
   MyEventSourceInt->FireEvents(112);

   // unhook handler to event
   MyEventSourceString->OnClick -= gcnew ClickEventHandler<String^>(
        MyEventReceiverString, &EventReceiver<String^>::OnMyClick);
   MyEventSourceInt->OnClick -= gcnew ClickEventHandler<int>(
        MyEventReceiverInt, &EventReceiver<int>::OnMyClick);
}
```

## <a name="generic-structs"></a>Универсальные структуры

Правила объявления и использования универсальных структур — те же, что и для универсальных классов, за исключением различий, описанных в справочнике по языку Visual C++.

## <a name="example"></a>Пример

В следующем примере объявляется универсальная структура, `MyGenStruct` с одним полем, `myField` и в это поле присваиваются значения различных типов ( **`int`** , **`double`** , `String^` ).

```cpp
// generics_generic_struct1.cpp
// compile with: /clr
using namespace System;

generic <typename ItemType>
ref struct MyGenStruct {
public:
   ItemType myField;

   ItemType AssignValue(ItemType item) {
      myField = item;
      return myField;
   }
};

int main() {
   int myInt = 123;
   MyGenStruct<int>^ myIntObj = gcnew MyGenStruct<int>();
   myIntObj->AssignValue(myInt);
   Console::WriteLine("The field is assigned the integer value: {0}",
            myIntObj->myField);

   double myDouble = 0.123;
   MyGenStruct<double>^ myDoubleObj = gcnew MyGenStruct<double>();
   myDoubleObj->AssignValue(myDouble);
   Console::WriteLine("The field is assigned the double value: {0}",
            myDoubleObj->myField);

   String^ myString = "Hello Generics!";
   MyGenStruct<String^>^ myStringObj = gcnew MyGenStruct<String^>();
   myStringObj->AssignValue(myString);
   Console::WriteLine("The field is assigned the string: {0}",
            myStringObj->myField);
}
```

```Output
The field is assigned the integer value: 123
The field is assigned the double value: 0.123
The field is assigned the string: Hello Generics!
```

## <a name="see-also"></a>См. также

[Универсальные шаблоны](generics-cpp-component-extensions.md)
