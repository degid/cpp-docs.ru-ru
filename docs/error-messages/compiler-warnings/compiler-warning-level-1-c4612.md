---
title: Предупреждение компилятора (уровень 1) C4612
ms.date: 08/27/2018
f1_keywords:
- C4612
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
ms.openlocfilehash: f9478caef9eaba9c72dc282179100daf2d94c6d5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185988"
---
# <a name="compiler-warning-level-1-c4612"></a>Предупреждение компилятора (уровень 1) C4612

> ошибка в имени включаемого файла

## <a name="remarks"></a>Примечания

Это предупреждение возникает с **#pragma include_alias** , когда имя файла указано неправильно или отсутствует.

Аргументы инструкции **#pragma include_alias** могут использовать форму кавычек ("*filename*") или форму угловой скобки (\<*filename*>), но обе должны использовать одну и ту же форму.

## <a name="example"></a>Пример

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```
