---
title: Ошибка средств компоновщика LNK1313
ms.date: 11/04/2016
f1_keywords:
- LNK1313
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
ms.openlocfilehash: 03ff61a1f3501b3ea106138e957a657ed064e645
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90683446"
---
# <a name="linker-tools-error-lnk1313"></a>Ошибка средств компоновщика LNK1313

> обнаружен модуль ijw/native, невозможно скомпоновать с чистыми модулями

## <a name="remarks"></a>Примечания

Текущая версия Visual C++ не поддерживает связывание машинных или смешанных управляемых и собственных OBJ-файлов с файлами obj, скомпилированными с **параметром/clr: pure**.

Параметр компилятора **/clr: pure** является устаревшим в visual Studio 2015 и не поддерживается в visual Studio 2017.

## <a name="examples"></a>Примеры

```cpp
// LNK1313.cpp
// compile with: /c /clr:pure
// a pure module
int main() {}
```

```cpp
// LNK1313_b.cpp
// compile with: /c /clr
// an IJW module
void test(){}
```

Следующий пример кода образует ошибку LNK1313.

```cpp
// LNK1313_c.cpp
// compile with: /link LNK1313.obj LNK1313_b.obj
// LNK1313 warning expected
```
