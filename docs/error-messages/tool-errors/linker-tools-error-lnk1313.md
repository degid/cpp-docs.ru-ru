---
title: Ошибка средств компоновщика LNK1313
ms.date: 11/04/2016
f1_keywords:
- LNK1313
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
ms.openlocfilehash: a2314f160dc6add45547082c7804ec5e2c8f2349
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194867"
---
# <a name="linker-tools-error-lnk1313"></a>Ошибка средств компоновщика LNK1313

> обнаружен модуль ijw/native, невозможно скомпоновать с чистыми модулями

## <a name="remarks"></a>Примечания

Текущая версия Visual C++ C++ не поддерживает связывание машинных или смешанных управляемых и собственных OBJ-файлов с файлами obj, скомпилированными с **параметром/clr: pure**.

Параметр компилятора **/clr: pure** является устаревшим в visual Studio 2015 и не поддерживается в visual Studio 2017.

## <a name="example"></a>Пример

```cpp
// LNK1313.cpp
// compile with: /c /clr:pure
// a pure module
int main() {}
```

## <a name="example"></a>Пример

```cpp
// LNK1313_b.cpp
// compile with: /c /clr
// an IJW module
void test(){}
```

## <a name="example"></a>Пример

Следующий пример кода образует ошибку LNK1313.

```cpp
// LNK1313_c.cpp
// compile with: /link LNK1313.obj LNK1313_b.obj
// LNK1313 warning expected
```
