---
title: Предупреждение компилятора (уровень 4) C4690
ms.date: 07/03/2018
f1_keywords:
- C4690
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
ms.openlocfilehash: c7facdde54b44ba2ce07db0447b251d7014f76c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324588"
---
# <a name="compiler-warning-level-4-c4690"></a>Предупреждение компилятора (уровень 4) C4690

> \[ emitidl (pop)]: занесений

## <a name="remarks"></a>Примечания

Атрибут [emitidl](../../windows/emitidl.md) был извлечен на один раз больше, чем занесен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C4690: Чтобы устранить эту проблему, убедитесь, что атрибут извлекается точно так, как столько раз, он помещается.

```cpp
// C4690.cpp
// compile with: /c /W4
[emitidl(pop)];   // C4690
class x {};
```
