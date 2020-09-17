---
title: Предупреждение компилятора (уровень 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 1958aec4d6642188af1467ab4cab1ecf55c29165
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223321"
---
# <a name="compiler-warning-level-1-c4076"></a>Предупреждение компилятора (уровень 1) C4076

> "*Модификатор типа*": не может использоваться с типом "*TypeName*"

## <a name="remarks"></a>Примечания

Модификатор типа ( **`signed`** или **`unsigned`** ) не может использоваться с типом, не являющимся целым числом. *Модификатор типа* игнорируется.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4076; чтобы устранить эту проблему, удалите **`unsigned`** Модификатор типа:

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```
