---
title: Выражение do-while (C++)
ms.date: 11/04/2016
f1_keywords:
- do_cpp
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
ms.openlocfilehash: f52c065210a8861dc065508248a506770b039b1d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189277"
---
# <a name="do-while-statement-c"></a>Выражение do-while (C++)

Выполняет *инструкцию* повторно, пока указанное условие завершения ( *выражение*) не примет значение 0.

## <a name="syntax"></a>Синтаксис

```
do
   statement
while ( expression ) ;
```

## <a name="remarks"></a>Примечания

Проверка условия завершения выполняется после каждого выполнения цикла. Таким образом, цикл **do-while** выполняется один или несколько раз в зависимости от значения выражения завершения. Выполнение оператора **do-while** также может прерваться, если в теле оператора выполняется оператор [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md) или [return](../cpp/return-statement-cpp.md).

Выражение *expression* должно иметь арифметический тип или тип указателя. Выполнение происходит следующим образом:

1. Выполняется тело оператора.

1. Затем вычисляется значение *expression*. Если выражение *expression* имеет значение false, выполнение оператора **do-while** завершается и управление передается следующему оператору программы. Если *expression* имеет значение true (то есть не равно нулю), процесс повторяется с шага 1.

## <a name="example"></a>Пример

В следующем примере показан оператор **do-while** :

```cpp
// do_while_statement.cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        printf_s("\n%d",i++);
    } while (i < 3);
}
```

## <a name="see-also"></a>См. также раздел

[Операторы итерации](../cpp/iteration-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор while (C++)](../cpp/while-statement-cpp.md)<br/>
[Оператор for (C++)](../cpp/for-statement-cpp.md)<br/>
[Основанный на диапазоне оператор for (C++)](../cpp/range-based-for-statement-cpp.md)
