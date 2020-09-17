---
title: Оператор goto (C++)
ms.date: 11/04/2016
f1_keywords:
- goto_cpp
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
ms.openlocfilehash: e56ebfadea0d643ac68e2ace722a39587bd01312
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223711"
---
# <a name="goto-statement-c"></a>Оператор goto (C++)

**`goto`** Оператор безусловно передает управление оператору, помеченному указанным идентификатором.

## <a name="syntax"></a>Синтаксис

```
goto identifier;
```

## <a name="remarks"></a>Примечания

Оператор, метка которого задана в параметре `identifier`, должен находиться в текущей функции. Все имена, заданные в параметре `identifier`, являются членами внутреннего пространства имен и, следовательно, не пересекаются с другими идентификаторами.

Метка оператора имеет смысл только для **`goto`** инструкции; в противном случае метки операторов игнорируются. Повторное объявление меток невозможно.

**`goto`** Оператору не разрешено передавать управление в расположение, которое пропускает инициализацию любой переменной, которая находится в области этого расположения. В следующем примере создается C2362:

```cpp
int goto_fn(bool b)
{
    if (!b)
    {
        goto exit;  // C2362
    }
    else
    { /*...*/ }

    int error_code = 42;

exit:
    return error_code;
}
```

Рекомендуется использовать **`break`** **`continue`** операторы, и **`return`** вместо **`goto`** инструкции, когда это возможно. Однако, поскольку **`break`** инструкция завершается только из одного уровня цикла, может потребоваться использовать **`goto`** оператор для выхода из глубоко вложенного цикла.

Дополнительные сведения о метках и **`goto`** инструкции см. в разделе [Операторы с метками](../cpp/labeled-statements.md).

## <a name="example"></a>Пример

В этом примере **`goto`** оператор передает управление в точку, помеченную, `stop` когда `i` равно 3.

```cpp
// goto_statement.cpp
#include <stdio.h>
int main()
{
    int i, j;

    for ( i = 0; i < 10; i++ )
    {
        printf_s( "Outer loop executing. i = %d\n", i );
        for ( j = 0; j < 2; j++ )
        {
            printf_s( " Inner loop executing. j = %d\n", j );
            if ( i == 3 )
                goto stop;
        }
    }

    // This message does not print:
    printf_s( "Loop exited. i = %d\n", i );

    stop:
    printf_s( "Jumped to stop. i = %d\n", i );
}
```

```Output
Outer loop executing. i = 0
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 1
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 2
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 3
Inner loop executing. j = 0
Jumped to stop. i = 3
```

## <a name="see-also"></a>См. также статью

[Операторы перехода](../cpp/jump-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
