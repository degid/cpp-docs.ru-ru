---
title: abstract (C++/CLI and C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- abstract
- abstract_cpp
helpviewer_keywords:
- abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
ms.openlocfilehash: 1e729589f78c56111717a87a27f9c7370dca7b90
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214299"
---
# <a name="abstract--ccli-and-ccx"></a>abstract (C++/CLI and C++/CX)

Ключевое слово **abstract** объявляет, что:

- Тип можно использовать в качестве базового типа, но экземпляр самого тип не может быть создан.

- Функция-член типа может определяться только в производном типе.

## <a name="all-platforms"></a>Все платформы

### <a name="syntax"></a>Синтаксис

*class-declaration* *class-identifier* **abstract {}**

**`virtual`** Абстрактный *возвращаемый тип* - *функция-идентификатор* **();**

### <a name="remarks"></a>Примечания

В первом примере синтаксиса объявляется абстрактный класс. Компонент *объявления класса* может быть либо машинным объявлением c++ (** `class` * * * или **`struct`** ), либо объявлением расширения c++ (** ref class * * или **ref struct**), если `/ZW` `/clr` указан параметр компилятора или.

Во втором примере синтаксиса объявляется абстрактная виртуальная функция-член. Объявление функции абстрактной — то же, что и объявление ее чистой виртуальной функцией. Объявление функции-члена абстрактной также приводит к тому, что включающий класс объявляется как абстрактный.

Ключевое слово **abstract** поддерживается в машинном коде и в коде платформы, то есть он может компилироваться как с параметром компилятора `/ZW` или `/clr`, так и без него.

Во время компиляции можно определить, является ли тип абстрактным, с помощью признака типа `__is_abstract(type)`. Дополнительные сведения см. в статье [Compiler Support for Type Traits (C++/CLI and C++/CX)](compiler-support-for-type-traits-cpp-component-extensions.md) (Поддержка характеристик типов компилятором (C++/CLI and C++/CX)).

Ключевое слово **abstract** является контекстно-зависимым описателем переопределения. Подробные сведения о контекстно-зависимых ключевых словах см. в статье [Context-Sensitive Keywords (C++/CLI and C++/CX)](context-sensitive-keywords-cpp-component-extensions.md) (Контекстно-зависимые ключевые слова (C++/CLI and C++/CX)). Дополнительные сведения о спецификаторах переопределения см. [в разделе инструкции. объявление описателей переопределения в компиляциях в собственном](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)режиме.

## <a name="windows-runtime"></a>Среда выполнения Windows

Подробные сведения см. в статье [Ref classes and structs (C++/CX)](../cppcx/ref-classes-and-structs-c-cx.md) (Ссылочные классы и структуры (C++/CX)).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере кода возникает ошибка, поскольку класс `X` помечен как **abstract**.

```cpp
// abstract_keyword.cpp
// compile with: /clr
ref class X abstract {
public:
   virtual void f() {}
};

int main() {
   X ^ MyX = gcnew X;   // C3622
}
```

В следующем примере кода возникает ошибка, поскольку он создает экземпляр собственного класса, помеченного как **abstract**. Эта ошибка будет возникать как с параметром компилятора `/clr`, так и без него.

```cpp
// abstract_keyword_2.cpp
class X abstract {
public:
   virtual void f() {}
};

int main() {
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'
                    // cannot be instantiated. See declaration of 'X'}
```

В следующем примере кода возникает ошибка, поскольку функция `f` включает определение, но помечена как **abstract**. Последняя инструкция в примере показывает, что объявление абстрактной виртуальной функции эквивалентно объявлению чистой виртуальной функции.

```cpp
// abstract_keyword_3.cpp
// compile with: /clr
ref class X {
public:
   virtual void f() abstract {}   // C3634
   virtual void g() = 0 {}   // C3634
};
```

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
