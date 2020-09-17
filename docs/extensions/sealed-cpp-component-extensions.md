---
title: sealed (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- sealed_cpp
- sealed
helpviewer_keywords:
- sealed keyword [C++]
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
ms.openlocfilehash: ab5d5b32ceb87a3b1ccf08d170889dd4825f6c17
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181802"
---
# <a name="sealed--ccli-and-ccx"></a>sealed (C++/CLI и C++/CX)

**sealed** — это контекстно-зависимое ключевое слово для ссылочных классов, которое означает, что виртуальный элемент нельзя переопределить или что тип не может использоваться в качестве базового типа.

> [!NOTE]
> В стандарте языка ISO C++11 представлено ключевое слово [final](../cpp/final-specifier.md). Используйте **final** в стандартных классах, а **sealed** — в ссылочных классах.

## <a name="all-runtimes"></a>Все среды выполнения

## <a name="syntax"></a>Синтаксис

```cpp
ref class identifier sealed {...};
virtual return-type identifier() sealed {...};
```

### <a name="parameters"></a>Параметры

*identifier*<br/>
Имя функции или класса.

*return-type*<br/>
Тип, который возвращается функцией.

## <a name="remarks"></a>Примечания

В первом примере синтаксиса запечатан (sealed) класс. Во втором примере запечатана виртуальная функция.

Используйте ключевое слово **sealed** для ссылочных классов и их виртуальных функций-членов. Дополнительные сведения см. в статье [Спецификаторы переопределения и компиляция в машинный код](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

Во время компиляции можно определить, запечатан ли тип, используя признак типа `__is_sealed(type)`. Подробные сведения см. в статье [Compiler Support for Type Traits (C++/CLI and C++/CX)](compiler-support-for-type-traits-cpp-component-extensions.md) (Поддержка характеристик типов компилятором (C++/CLI and C++/CX)).

**sealed** — контекстно-зависимое ключевое слово.  Дополнительные сведения см. в статье [Context-Sensitive Keywords (C++/CLI and C++/CX)](context-sensitive-keywords-cpp-component-extensions.md) (Контекстно-зависимые ключевые слова (C++/CLI и C++/CX)).

## <a name="windows-runtime"></a>Среда выполнения Windows

См. статью о [ссылочных классах и структурах](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

(Отсутствуют комментарии для этой возможности языка, которая применяется только в среде CLR).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере кода показано влияние **sealed** на виртуальный элемент.

```cpp
// sealed_keyword.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
   virtual void g();
};

ref class X : I1 {
public:
   virtual void f() {
      System::Console::WriteLine("X::f override of I1::f");
   }

   virtual void g() sealed {
      System::Console::WriteLine("X::f override of I1::g");
   }
};

ref class Y : public X {
public:
   virtual void f() override {
      System::Console::WriteLine("Y::f override of I1::f");
   }

   /*
   // the following override generates a compiler error
   virtual void g() override {
      System::Console::WriteLine("Y::g override of I1::g");
   }
   */
};

int main() {
   I1 ^ MyI = gcnew X;
   MyI -> f();
   MyI -> g();

   I1 ^ MyI2 = gcnew Y;
   MyI2 -> f();
}
```

```Output
X::f override of I1::f
X::f override of I1::g
Y::f override of I1::f
```

В следующем примере кода показано, как пометить класс запечатанным.

```cpp
// sealed_keyword_2.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X sealed : I1 {
public:
   virtual void f() override {}
};

ref class Y : public X {   // C3246 base class X is sealed
public:
   virtual void f() override {}
};
```

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
