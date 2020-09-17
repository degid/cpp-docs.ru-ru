---
title: literal (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- literal
- literal_cpp
helpviewer_keywords:
- literal keyword [C++]
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
ms.openlocfilehash: 2470d5680f7538af2db7bda3611abad11b827970
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214260"
---
# <a name="literal-ccli-and-ccx"></a>literal (C++/CLI и C++/CX)

Переменная (элемент данных), помеченная как **literal** в компиляции **/clr** является нативной эквивалентой переменной **static const**.

## <a name="all-platforms"></a>Все платформы

### <a name="remarks"></a>Примечания

(Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="remarks"></a>Примечания

(Отсутствуют комментарии для этой возможности языка, которая применяется только в среде выполнения Windows).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

## <a name="remarks"></a>Примечания

Элемент данных, помеченный как **literal**, необходимо инициализировать при объявлении, а его значение должно быть целочисленной константой, перечислением или строковым типом. Преобразование из типа выражения инициализации в тип статического константного элемента данных не должно требовать определенного пользователем преобразования.

Во время выполнения для полей литералов память не выделяется; компилятор только вставляет свое значение в метаданные класса.

Переменная, помеченная как **static const**, не будет доступна в метаданных другим компиляторам.

Подробные сведения см. в статьях [Классы хранения](../cpp/storage-classes-cpp.md) и [const](../cpp/const-cpp.md).

**literal** — контекстно-зависимое ключевое слово. Подробные сведения см. в статье [Context-Sensitive Keywords (C++/CLI and C++/CX)](context-sensitive-keywords-cpp-component-extensions.md) (Контекстно-зависимые ключевые слова (C++/CLI and C++/CX)).

## <a name="example"></a>Пример

В этом примере показано, что предполагается **литеральная** переменная **`static`** .

```cpp
// mcppv2_literal.cpp
// compile with: /clr
ref struct X {
   literal int i = 4;
};

int main() {
   int value = X::i;
}
```

## <a name="example"></a>Пример

В следующем примере показано влияние литералов в метаданных.

```cpp
// mcppv2_literal2.cpp
// compile with: /clr /LD
public ref struct A {
   literal int lit = 0;
   static const int sc = 1;
};
```

Обратите внимание на разницу в метаданных для `sc` и `lit`: директива `modopt` применяется к `sc` и поэтому она может игнорироваться другими компиляторами.

```
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)
```

```
.field public static literal int32 lit = int32(0x0000000A)
```

## <a name="example"></a>Пример

В следующем примере, написанном на языке C#, приводится ссылка на метаданные, созданные в предыдущем примере, и показывается влияние переменных **literal** и **static const**:

```csharp
// mcppv2_literal3.cs
// compile with: /reference:mcppv2_literal2.dll
// A C# program
class B {
   public static void Main() {
      // OK
      System.Console.WriteLine(A.lit);
      System.Console.WriteLine(A.sc);

      // C# does not enforce C++ const
      A.sc = 9;
      System.Console.WriteLine(A.sc);

      // C# enforces const for a literal
      A.lit = 9;   // CS0131

      // you can assign a C++ literal variable to a C# const variable
      const int i = A.lit;
      System.Console.WriteLine(i);

      // but you cannot assign a C++ static const variable
      // to a C# const variable
      const int j = A.sc;   // CS0133
      System.Console.WriteLine(j);
   }
}
```

## <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
