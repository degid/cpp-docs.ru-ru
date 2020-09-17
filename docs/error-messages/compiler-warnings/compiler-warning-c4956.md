---
title: Предупреждение компилятора C4956
ms.date: 11/04/2016
f1_keywords:
- C4956
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
ms.openlocfilehash: 474bdfa6eb670f39a2876b0c1490e7254cf216e7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164910"
---
# <a name="compiler-warning-c4956"></a>Предупреждение компилятора C4956

> "*тип*": этот тип не поддается проверке

## <a name="remarks"></a>Примечания

Это предупреждение создается, если указано [/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) , но код содержит тип, не подлежащий проверке. Параметр компилятора **/clr: Сейф** является устаревшим в visual Studio 2015 и не поддерживается в visual Studio 2017.

Дополнительные сведения см. в разделе [чистый и проверяемый кодC++(/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Это предупреждение выдается в качестве ошибки, и его можно отключить с помощью прагмы [warning](../../preprocessor/warning.md) или параметра компилятора [/wd](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Пример

В следующем примере возникает ошибка C4956.

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```
