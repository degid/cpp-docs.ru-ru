---
title: Предупреждение компилятора (уровень 3) C4161
ms.date: 08/27/2018
f1_keywords:
- C4161
helpviewer_keywords:
- C4161
ms.assetid: 03d3be61-83f1-4009-8310-8758ab67055f
ms.openlocfilehash: 94ff4b645ec704c1b17d3c74aba434cf3ac7f05e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199008"
---
# <a name="compiler-warning-level-3-c4161"></a>Предупреждение компилятора (уровень 3) C4161

> #<a name="pragma-pragmapop--more-pops-than-pushes"></a>pragma *pragma*(POP...): больше точек присутствия, чем push-уведомлений

## <a name="remarks"></a>Примечания

Так как число извлечений из стека превышает число занесений для директивы *pragma*, стек может работать непредвиденным образом. Чтобы избежать этого предупреждения, убедитесь, что число извлечений из стека не превышает число занесений.

## <a name="example"></a>Пример

При компиляции следующего примера будет выдано предупреждение C4161:

```cpp
// C4161.cpp
// compile with: /W3 /LD
#pragma pack(push, id)
#pragma pack(pop, id)
#pragma pack(pop, id)   // C4161, an extra pop

#pragma bss_seg(".my_data1")
int j;

#pragma bss_seg(push, stack1, ".my_data2")
int l;

#pragma bss_seg(pop, stack1)
int m;

#pragma bss_seg(pop, stack1)   // C4161
```
