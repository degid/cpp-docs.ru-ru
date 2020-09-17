---
title: delegate (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- delegate_cpp
- delegate
helpviewer_keywords:
- delegate keyword [C++]
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
ms.openlocfilehash: 77cd17eb8c164a08af9ec783f8aba422785609b6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219733"
---
# <a name="delegate--ccli-and-ccx"></a>delegate (C++/CLI и C++/CX)

Объявляет тип, представляющий указатель на функцию.

## <a name="all-runtimes"></a>Все среды выполнения

Среда выполнения Windows, как и среда CLR, поддерживает делегаты.

### <a name="remarks"></a>Примечания

**delegate** — контекстно-зависимое ключевое слово. Дополнительные сведения см. в статье [Context-Sensitive Keywords (C++/CLI and C++/CX)](context-sensitive-keywords-cpp-component-extensions.md) (Контекстно-зависимые ключевые слова (C++/CLI и C++/CX)).

Используйте признак типа `__is_delegate()` для определения во время компиляции является ли тип делегатом. Дополнительные сведения см. в статье [Compiler Support for Type Traits (C++/CLI and C++/CX)](compiler-support-for-type-traits-cpp-component-extensions.md) (Поддержка характеристик типов компилятором (C++/CLI and C++/CX)).

## <a name="windows-runtime"></a>Среда выполнения Windows

C++/CX поддерживает делегаты со следующим синтаксисом.

### <a name="syntax"></a>Синтаксис

```cpp
access
delegate
return-type
delegate-type-identifier
(
[ parameters ]
)
```

### <a name="parameters"></a>Параметры

*имеет*<br/>
используемых Доступность делегата, который может быть **`public`** (по умолчанию) или **`private`** . Прототип функции также может быть дополнен **`const`** **`volatile`** ключевыми словами или.

*Тип возвращаемого значения*<br/>
Тип возвращаемого значения прототипа функции.

*delegate-type-identifier*<br/>
Имя объявленного типа делегата.

*parameters*<br/>
Типы и идентификаторы прототипа функции (необязательно).

### <a name="remarks"></a>Примечания

Используйте параметр *delegate-type-identifier* для объявления события с таким же прототипом, что и у делегата. Дополнительные сведения см. в статье [Delegates (C++/CX)](../cppcx/delegates-c-cx.md) (Делегаты (C++/CX)).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

Среда CLR поддерживает делегаты со следующим синтаксисом.

### <a name="syntax"></a>Синтаксис

```cpp
access
delegate
function_declaration
```

### <a name="parameters"></a>Параметры

*имеет*<br/>
Доступность делегата за пределами сборки может быть public или private (необязательно).  По умолчанию — private.  Внутри класса делегат может иметь любой уровень доступа.

*function_declaration*<br/>
Сигнатура функции, которую можно привязать к делегату. Типом возвращаемого значения делегата может быть любой управляемый тип. По соображениям взаимодействия рекомендуется, чтобы тип возвращаемого значения делегата был типом CLS.

Чтобы определить непривязанный делегат, первым параметром в *function_declaration* должен быть тип **`this`** указателя для объекта.

### <a name="remarks"></a>Примечания

Делегаты являются многоадресной рассылкой: "указатель функции" можно привязать к одному или нескольким методам в управляемом классе. Ключевое слово **delegate** определяет тип делегата многоадресной рассылки с помощью сигнатуры определенного метода.

Делегат также можно привязать к методу класса значения, такому как статический метод.

Делегат имеет следующие характеристики.

- Он наследует от `System::MulticastDelegate`.

- Он имеет конструктор, который принимает два аргумента: указатель на управляемый класс или NULL (в случае привязки к статическому методу) и полный метод указанного типа.

- Он содержит метод `Invoke`, сигнатура которого соответствует объявленной сигнатуре делегата.

При обращении к делегату его функции вызываются в порядке, в котором они были присоединены.

Возвращаемое значение делегата — это возвращаемое значение из его последней присоединенной функции-члена.

Делегаты не могут быть перегружены.

Делегаты можно привязать или отменить их привязку.

При создании экземпляра привязанного делегата первый аргумент должен быть ссылкой на объект. Второй аргумент созданного экземпляра делегата должен быть или адресом метода объекта управляемого класса, или указателем на метод типа значения. Второй аргумент созданного экземпляра делегата должен присвоить имя методу с помощью полного синтаксиса области класса и применить оператор address-of.

При создании экземпляра непривязанного делегата первый аргумент должен быть или адресом метода объекта управляемого класса, или указателем на метод типа значения. Аргумент должен присвоить имя методу с помощью полного синтаксиса области класса и применить оператор address-of.

При создании делегата статической или глобальной функции необходим только один параметр: функция (при необходимости адрес функции).

Дополнительные сведения о делегатах см. в следующих статьях.

- [Практическое руководство. Определение и использование делегатов (C++/CLI)](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)

- [Универсальные методы-делегаты (C++/CLI)](generic-delegates-visual-cpp.md)

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере показано, как объявить, инициализировать и вызвать делегаты.

```cpp
// mcppv2_delegate.cpp
// compile with: /clr
using namespace System;

// declare a delegate
public delegate void MyDel(int i);

ref class A {
public:
   void func1(int i) {
      Console::WriteLine("in func1 {0}", i);
   }

   void func2(int i) {
      Console::WriteLine("in func2 {0}", i);
   }

   static void func3(int i) {
      Console::WriteLine("in static func3 {0}", i);
   }
};

int main () {
   A ^ a = gcnew A;

   // declare a delegate instance
   MyDel^ DelInst;

   // test if delegate is initialized
   if (DelInst)
      DelInst(7);

   // assigning to delegate
   DelInst = gcnew MyDel(a, &A::func1);

   // invoke delegate
   if (DelInst)
      DelInst(8);

   // add a function
   DelInst += gcnew MyDel(a, &A::func2);

   DelInst(9);

   // remove a function
   DelInst -= gcnew MyDel(a, &A::func1);

   // invoke delegate with Invoke
   DelInst->Invoke(10);

   // make delegate to static function
   MyDel ^ StaticDelInst = gcnew MyDel(&A::func3);
   StaticDelInst(11);
}
```

```Output
in func1 8

in func1 9

in func2 9

in func2 10

in static func3 11
```

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
