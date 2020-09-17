---
title: Ошибка компилятора C3641
ms.date: 11/04/2016
f1_keywords:
- C3641
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
ms.openlocfilehash: 44356fb1a1818a02102d23e6b308457f2f39506b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200516"
---
# <a name="compiler-error-c3641"></a>Ошибка компилятора C3641

> "*функция*": недопустимое соглашение о вызовах "calling_convention" для функции, скомпилированной с параметрами/clr: pure или/CLR: Сейф

## <a name="remarks"></a>Примечания

Параметры компилятора **/clr: pure** и **/clr: Сейф** являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017.

Только соглашение о вызовах [__clrcall](../../cpp/clrcall.md) разрешено с [/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3641:

```cpp
// C3641.cpp
// compile with: /clr:pure /c
void __cdecl f() {}   // C3641
```
