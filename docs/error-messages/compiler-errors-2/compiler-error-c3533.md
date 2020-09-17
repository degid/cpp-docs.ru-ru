---
title: Ошибка компилятора C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: 4e3c773d0498a35c7b5d053268bff26f9943103b
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686773"
---
# <a name="compiler-error-c3533"></a>Ошибка компилятора C3533

"тип": параметр не может иметь тип, содержащий "Auto"

Метод или параметр шаблона не может быть объявлен с **`auto`** ключевым словом, если действует параметр компилятора [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) .

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Удалите **`auto`** ключевое слово из объявления параметра.

## <a name="examples"></a>Примеры

В следующем примере создается C3533, поскольку он объявляет параметр функции с **`auto`** ключевым словом и компилируется с помощью параметра **/Zc: Auto**.

```cpp
// C3533a.cpp
// Compile with /Zc:auto
void f(auto j) {} // C3533
```

В следующем примере демонстрируется C3533 в режиме C++ 14, так как он объявляет параметр шаблона с **`auto`** ключевым словом и компилируется с помощью параметра **/Zc: Auto**. (В C++ 17 это допустимое определение шаблона класса с одним нетипизированным параметром шаблона, тип которого выведен.)

```cpp
// C3533b.cpp
// Compile with /Zc:auto
template<auto T> class C {}; // C3533
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)<br/>
[/Zc: Auto (вывод типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)
