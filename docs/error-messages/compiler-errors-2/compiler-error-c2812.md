---
title: Ошибка компилятора C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: cec92982646c64e6c5b669df328e4836d4f44df8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202108"
---
# <a name="compiler-error-c2812"></a>Ошибка компилятора C2812

> \#import не поддерживается с параметрами/clr: pure и/CLR: Сейф

## <a name="remarks"></a>Примечания

Параметры компилятора **/clr: pure** и **/clr: Сейф** являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017.

[директива #import](../../preprocessor/hash-import-directive-cpp.md) не поддерживается с **параметрами/clr: pure** и **/clr: Сейф** , поскольку `#import` требует использования библиотек поддержки собственного компилятора.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2812.

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```
