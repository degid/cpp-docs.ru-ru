---
title: Ошибка компилятора C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 97d6dc0544176d90b90702a7d1f1648e8e98d756
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686630"
---
# <a name="compiler-error-c3821"></a>Ошибка компилятора C3821

"функция": управляемый тип или функция не могут использоваться в неуправляемой функции

Функции со встроенной сборкой или [setjmp](../../c-runtime-library/reference/setjmp.md) не могут содержать типы значений или управляемые классы. Чтобы устранить эту ошибку, удалите встроенную сборку и `setjmp` или удалите управляемые объекты.

C3821 также может возникать при попытке использовать автоматическое хранилище в функции vararg.  Дополнительные сведения см. в разделе [списки аргументов переменных (...) (c++/CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md) и [Семантика стека c++ для ссылочных типов](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C3821.

```cpp
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

Следующий пример приводит к возникновению ошибки C3821.

```cpp
// C3821b.cpp
// compile with: /clr
// processor: /x86
ref class A {
   public:
   int i;
};

int main() {
   // cannot use managed classes in this function
   A ^a;

   __asm {
      nop
   }
} // C3821
```
