---
title: Предупреждение компилятора (уровень 1) C4399
ms.date: 11/04/2016
f1_keywords:
- C4399
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
ms.openlocfilehash: a556fbffad41d04b3eb0ea1acfd5e8739ddd5b68
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186807"
---
# <a name="compiler-warning-level-1-c4399"></a>Предупреждение компилятора (уровень 1) C4399

> "*символ*": символ для каждого процесса не должен помечаться __declspec (dllimport) при компиляции с параметром/clr: pure

## <a name="remarks"></a>Примечания

Параметр компилятора **/clr: pure** является устаревшим в visual Studio 2015 и не поддерживается в visual Studio 2017.

Данные из машинного образа или образа с собственными конструкциями и структурами CLR не могут быть импортированы в чистый образ. Чтобы устранить это предупреждение, Скомпилируйте с **параметром/CLR** (не **/clr: pure**) или удалите `__declspec(dllimport)`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4399.

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```
