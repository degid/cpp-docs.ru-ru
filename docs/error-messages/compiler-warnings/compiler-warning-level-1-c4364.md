---
title: Предупреждение компилятора (уровень 1) C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: 7f1c71cb3cd6a99d4ed9960032813e7cebca7591
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685083"
---
# <a name="compiler-warning-level-1-c4364"></a>Предупреждение компилятора (уровень 1) C4364

\#используется для сборки "File", которая ранее встречалась в расположении (line_number) без атрибута as_friend; as_friend не применяется

`#using`Директива была повторена для данного файла метаданных, но **`as_friend`** Квалификатор не использовался в первом экземпляре; компилятор будет игнорировать второй **`as_friend`** .

Дополнительные сведения см. в разделе [дружественные сборки (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="examples"></a>Примеры

В приведенном ниже примере создается компонент.

```cpp
// C4364.cpp
// compile with: /clr /LD
ref class A {};
```

Следующий пример приводит к возникновению ошибки C4364.

```cpp
// C4364_b.cpp
// compile with: /clr /W1 /c
#using " C4364.dll"
#using " C4364.dll" as_friend   // C4364
```
