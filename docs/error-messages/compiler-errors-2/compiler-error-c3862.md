---
title: Ошибка компилятора C3862
ms.date: 11/04/2016
f1_keywords:
- C3862
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
ms.openlocfilehash: 0b9c1e1213949d7d700094caa6687232df881ce6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165487"
---
# <a name="compiler-error-c3862"></a>Ошибка компилятора C3862

> "*функция*": невозможно скомпилировать неуправляемую функцию с параметрами/clr: pure или/CLR: Сейф

## <a name="remarks"></a>Примечания

Параметры компилятора **/clr: pure** и **/clr: Сейф** являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017.

Компиляция с **/clr: pure** или **/clr: Сейф** приведет к созданию образа только MSIL, изображения без машинного (неуправляемого) кода.  Поэтому нельзя использовать директиву pragma `unmanaged` в компиляции **/clr: pure** или **/clr: Сейф** .

Дополнительные сведения см. в статьях [/CLR (компиляция общеязыковой среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md) и [управляемые, неуправляемые](../../preprocessor/managed-unmanaged.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3862:

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```
