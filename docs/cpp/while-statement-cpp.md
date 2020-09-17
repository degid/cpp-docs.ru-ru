---
title: Оператор while (C++)
ms.date: 11/04/2016
f1_keywords:
- while_cpp
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
ms.openlocfilehash: 168b1fc20d165c44c3230a8d1094c99b689ddbb9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233552"
---
# <a name="while-statement-c"></a>Оператор while (C++)

Выполняет *инструкцию* повторно, пока *выражение* не примет значение 0.

## <a name="syntax"></a>Синтаксис

```
while ( expression )
   statement
```

## <a name="remarks"></a>Примечания

Перед каждым выполнением цикла выполняется проверка *выражения* . Таким образом, **`while`** цикл выполняется ноль или более раз. *выражение* должно иметь целочисленный тип, тип указателя или тип класса с однозначным преобразованием в целочисленный или тип указателя.

**`while`** Цикл также может завершиться, когда выполняется [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md)или [return](../cpp/return-statement-cpp.md) в теле оператора. Используйте [Continue](../cpp/continue-statement-cpp.md) , чтобы завершить текущую итерацию без выхода из **`while`** цикла. **`continue`** передает управление следующей итерации **`while`** цикла.

В следующем коде используется **`while`** цикл для удаления конечных подчеркивания из строки.

```cpp
// while_statement.cpp

#include <string.h>
#include <stdio.h>
char *trim( char *szSource )
{
    char *pszEOS = 0;

    //  Set pointer to character before terminating NULL
    pszEOS = szSource + strlen( szSource ) - 1;

    //  iterate backwards until non '_' is found
    while( (pszEOS >= szSource) && (*pszEOS == '_') )
        *pszEOS-- = '\0';

    return szSource;
}
int main()
{
    char szbuf[] = "12345_____";

    printf_s("\nBefore trim: %s", szbuf);
    printf_s("\nAfter trim: %s\n", trim(szbuf));
}
```

Условие завершения вычисляется в начале цикла. Если символов подчеркивания в конце строки нет, цикл никогда не выполняется.

## <a name="see-also"></a>См. также статью

[Операторы итерации](../cpp/iteration-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор do-while (C)](../cpp/do-while-statement-cpp.md)<br/>
[Оператор for (C++)](../cpp/for-statement-cpp.md)<br/>
[Основанное на диапазоне выражение for (C++)](../cpp/range-based-for-statement-cpp.md)
