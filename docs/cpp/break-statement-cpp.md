---
title: Оператор break (C++)
ms.date: 11/04/2016
f1_keywords:
- break_cpp
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
ms.openlocfilehash: 30ca602ecc65099adff7300f730c500a31fe0ed5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227612"
---
# <a name="break-statement-c"></a>Оператор break (C++)

**`break`** Оператор завершает выполнение ближайшего включающего цикла или условного оператора, в котором он отображается. Управление передается оператору, который расположен после оператора, при его наличии.

## <a name="syntax"></a>Синтаксис

```
break;
```

## <a name="remarks"></a>Примечания

**`break`** Оператор используется с оператором условного [переключения](../cpp/switch-statement-cpp.md) и с операторами [Do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md)и [while](../cpp/while-statement-cpp.md) .

В **`switch`** операторе **`break`** инструкция заставляет программу выполнить следующую инструкцию за пределами **`switch`** оператора. Без **`break`** инструкции выполняется каждая инструкция из сопоставленной **`case`** метки в конец **`switch`** оператора, включая **`default`** предложение.

В циклах **`break`** оператор завершает выполнение ближайшего включающего **`do`** **`for`** оператора, или **`while`** . Управление передается оператору, который расположен после завершенного оператора, при его наличии.

Внутри вложенных операторов **`break`** оператор завершает только **`do`** **`for`** оператор,, **`switch`** или **`while`** , который непосредственно заключает его в блок. Оператор или можно использовать **`return`** **`goto`** для перемещения управления из более глубоко вложенных структур.

## <a name="example"></a>Пример

В следующем коде показано, как использовать **`break`** инструкцию в **`for`** цикле.

```cpp
#include <iostream>
using namespace std;

int main()
{
    // An example of a standard for loop
    for (int i = 1; i < 10; i++)
    {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
    }

    // An example of a range-based for loop
int nums []{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

    for (int i : nums) {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
    }
}
```

```Output
In each case:
1
2
3
```

В следующем коде показано, как использовать **`break`** в **`while`** цикле и в **`do`** цикле.

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;

    while (i < 10) {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
        i++;
    }

    i = 0;
    do {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
        i++;
    } while (i < 10);
}
```

```Output
In each case:
0123
```

В следующем коде показано, как использовать **`break`** в операторе switch. Необходимо использовать **`break`** в каждом случае, если нужно обменять каждый вариант отдельно. Если не использовать **`break`** , выполнение кода будет проходить до следующего варианта.

```cpp
#include <iostream>
using namespace std;

enum Suit{ Diamonds, Hearts, Clubs, Spades };

int main() {

    Suit hand;
    . . .
    // Assume that some enum value is set for hand
    // In this example, each case is handled separately
    switch (hand)
    {
    case Diamonds:
        cout << "got Diamonds \n";
        break;
    case Hearts:
        cout << "got Hearts \n";
        break;
    case Clubs:
        cout << "got Clubs \n";
        break;
    case Spades:
        cout << "got Spades \n";
        break;
    default:
          cout << "didn't get card \n";
    }
    // In this example, Diamonds and Hearts are handled one way, and
    // Clubs, Spades, and the default value are handled another way
    switch (hand)
    {
    case Diamonds:
    case Hearts:
        cout << "got a red card \n";
        break;
    case Clubs:
    case Spades:
    default:
        cout << "didn't get a red card \n";
    }
}
```

## <a name="see-also"></a>См. также статью

[Операторы перехода](../cpp/jump-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор continue](../cpp/continue-statement-cpp.md)
