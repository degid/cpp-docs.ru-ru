---
title: Предупреждение компилятора (уровень 1) C4382
ms.date: 11/04/2016
f1_keywords:
- C4382
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
ms.openlocfilehash: 7b8dbf77defab2a711ad931057c740193908474b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186976"
---
# <a name="compiler-warning-level-1-c4382"></a>Предупреждение компилятора (уровень 1) C4382

> Создание "*типа*": тип с деструктором __clrcall или конструктором копии может быть перехвачен только в модуле/CLR: pure

## <a name="remarks"></a>Примечания

Параметр компилятора **/clr: pure** является устаревшим в visual Studio 2015 и не поддерживается в visual Studio 2017.

При компиляции с параметром **/CLR** (не **/clr: pure**) обработка исключений ждет, что функции-члены в собственном типе будут [__cdecl](../../cpp/cdecl.md) , а не [__clrcall](../../cpp/clrcall.md). Собственные типы с функциями-членами, использующие соглашение о вызовах `__clrcall`, не могут быть перехвачены в модуле, скомпилированном с **параметром/CLR**.

Если исключение будет перехвачено в модуле, скомпилированном с **параметром/clr: pure**, это предупреждение можно игнорировать.

Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4382.

```cpp
// C4382.cpp
// compile with: /clr /W1 /c
struct S {
   __clrcall ~S() {}
};

struct T {
   ~T() {}
};

int main() {
   S s;
   throw s;   // C4382

   S * ps = &s;
   throw ps;   // OK

   T t;
   throw t;   // OK
}
```
