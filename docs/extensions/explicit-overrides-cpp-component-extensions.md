---
title: Явные переопределения (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- overriding, override [C++]
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
ms.openlocfilehash: c199301794daaa140ede2fd99b0ae755cea70f97
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172377"
---
# <a name="explicit-overrides--ccli-and-ccx"></a>Явные переопределения (C++/CLI и C++/CX)

В этом разделе рассматривается явное переопределение элемента базового класса или интерфейса. Именованное (явное) переопределение должно использоваться только для переопределения метода производным методом с другим именем.

## <a name="all-runtimes"></a>Все среды выполнения

### <a name="syntax"></a>Синтаксис

```cpp
overriding-function-declarator = type::function [,type::function] { overriding-function-definition }
overriding-function-declarator = function { overriding-function-definition }
```

### <a name="parameters"></a>Параметры

*overriding-function-declarator*<br/>
Тип возвращаемого значения, имя и список аргументов функции переопределения.  Обратите внимание, что функция переопределения не обязательно должна иметь то же имя, что и переопределенная функция.

*type*<br/>
Базовый тип, содержащий функцию для переопределения.

*function*<br/>
Одно или несколько имен функций для переопределения, разделенные запятыми.

*overriding-function-definition*<br/>
Операторы тела функции, которые определяют функцию переопределения.

### <a name="remarks"></a>Примечания

Используйте явные переопределения для создания псевдонима для сигнатуры метода или для предоставления различных реализаций для методов с одинаковой сигнатурой.

Сведения об изменении поведения унаследованных типов и их членов см. в разделе [Спецификаторы переопределения](override-specifiers-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

### <a name="remarks"></a>Примечания

Сведения о явных переопределениях в машинном или скомпилированном коде с `/clr:oldSyntax` см. в разделе [Явные переопределения](../cpp/explicit-overrides-cpp.md).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере кода показано простое неявное переопределение и реализация элемента в базовом интерфейсе без использования явных переопределений.

```cpp
// explicit_override_1.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X : public I1 {
public:
   virtual void f() {
      System::Console::WriteLine("X::f override of I1::f");
   }
};

int main() {
   I1 ^ MyI = gcnew X;
   MyI -> f();
}
```

```Output
X::f override of I1::f
```

В следующем примере кода рассматривается реализация всех элементов интерфейса с распространенной подписью с использованием синтаксиса явного переопределения.

```cpp
// explicit_override_2.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

interface struct I2 {
   virtual void f();
};

ref struct X : public I1, I2 {
   virtual void f() = I1::f, I2::f {
      System::Console::WriteLine("X::f override of I1::f and I2::f");
   }
};

int main() {
   I1 ^ MyI = gcnew X;
   I2 ^ MyI2 = gcnew X;
   MyI -> f();
   MyI2 -> f();
}
```

```Output
X::f override of I1::f and I2::f
X::f override of I1::f and I2::f
```

В следующем примере кода демонстрируется, как переопределение функции может иметь имя, отличное от функции, которую она реализует.

```cpp
// explicit_override_3.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X : public I1 {
public:
   virtual void g() = I1::f {
      System::Console::WriteLine("X::g");
   }
};

int main() {
   I1 ^ a = gcnew X;
   a->f();
}
```

```Output
X::g
```

В следующем примере кода показана явная реализация интерфейса, реализующая типобезопасную коллекцию.

```cpp
// explicit_override_4.cpp
// compile with: /clr /LD
using namespace System;
ref class R : ICloneable {
   int X;

   virtual Object^ C() sealed = ICloneable::Clone {
      return this->Clone();
   }

public:
   R() : X(0) {}
   R(int x) : X(x) {}

   virtual R^ Clone() {
      R^ r = gcnew R;
      r->X = this->X;
      return r;
   }
};
```

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
