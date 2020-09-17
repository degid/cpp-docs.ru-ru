---
title: Предупреждение компилятора (уровень 4) C4840
ms.date: 09/13/2018
f1_keywords:
- C4840
helpviewer_keywords:
- C4840
ms.openlocfilehash: 649083d66d0c7a0ef11c742e56cbfb70e2e9b75f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185208"
---
# <a name="compiler-warning-level-4-c4840"></a>Предупреждение компилятора (уровень 4) C4840

> непереносимое использование класса "*Type*" в качестве аргумента функции Variadic

## <a name="remarks"></a>Примечания

Классы или структуры, которые передаются в функцию Variadic, должны быть простыми копируемыми. При передаче таких объектов компилятор просто выполняет побитовое копирование и не вызывает конструктор или деструктор.

Это предупреждение доступно начиная с Visual Studio 2017.

## <a name="example"></a>Пример

В следующем примере создается C4840 и демонстрируется его устранение.

```cpp
// C4840.cpp
// compile by using: cl /EHsc /W4 C4840.cpp
#include <stdio.h>

int main()
{
    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);

    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                       // as an argument to a variadic function
    // To correct the error, you can perform a static cast
    // to convert the object before passing it:
    printf("%i\n", static_cast<int>(s));
}
```

Для строк, созданных и управляемых с помощью `CStringW`, необходимо использовать предоставленный `operator LPCWSTR()` для приведения объекта `CStringW` к указателю строки в стиле C, ожидаемому строкой формата:

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
