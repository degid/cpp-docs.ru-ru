---
title: Функции &lt;forward_list&gt;
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 78b1eaa44ed464de67d8ec45fab3241179bb94b9
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424803"
---
# <a name="ltforward_listgt-functions"></a>Функции &lt;forward_list&gt;

## <a name="swap"></a>позиции

Меняет местами элементы двух прямых списков.

```cpp
void swap(forward_list <Type, Allocator>& left, forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `forward_list`.

*right*\
Объект типа `forward_list`.

### <a name="remarks"></a>Примечания

Шаблонная функция выполняет `left.swap(right)`.
