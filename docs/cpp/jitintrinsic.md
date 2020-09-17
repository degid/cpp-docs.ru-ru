---
title: jitintrinsic
ms.date: 11/04/2016
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
ms.openlocfilehash: cecadcad15ee65a44ad5a8245efdb69903c89459
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233708"
---
# <a name="jitintrinsic"></a>jitintrinsic

Помечает функцию как значимую для 64-разрядной среды CLR. Этот модификатор используется с определенными функциями в библиотеках Microsoft.

## <a name="syntax"></a>Синтаксис

```
__declspec(jitintrinsic)
```

## <a name="remarks"></a>Примечания

**`jitintrinsic`** Добавляет MODOPT ( <xref:System.Runtime.CompilerServices.IsJitIntrinsic> ) в сигнатуру функции.

Пользователям не рекомендуется использовать этот **`__declspec`** модификатор, так как могут возникать непредвиденные результаты.

## <a name="see-also"></a>См. также статью

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
