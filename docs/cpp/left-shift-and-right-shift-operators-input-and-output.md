---
title: Операторы сдвига влево и вправо ( &gt; &gt; и &lt; &lt; )
ms.date: 08/13/2018
f1_keywords:
- <<
- '>>'
helpviewer_keywords:
- << operator [C++], with specific objects
- left shift operators [C++]
- right shift operators [C++]
- bitwise-shift operators [C++]
- '>> operator'
- shift operators [C++]
- operators [C++], shift
ms.assetid: 25fa0cbb-5fdd-4657-8745-b35f7d8f1606
ms.openlocfilehash: 4cdb353c950313396b331dc7ba01b3ea392ed0f8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186962"
---
# <a name="left-shift-and-right-shift-operators-gtgt-and-ltlt"></a>Операторы сдвига влево и вправо ( &gt; &gt; и &lt; &lt; )

Операторы побитового сдвига являются оператором сдвига вправо ( **&gt;&gt;** ), который перемещает биты *сдвига* вправо и оператор сдвига влево ( **&lt;&lt;** ), который перемещает биты *SHIFT-Expression* влево. <sup>1</sup>

## <a name="syntax"></a>Синтаксис

> *SHIFT-выражение* `<<` *аддитивное выражение*\
> *shift-expression* `>>` *additive-expression*

## <a name="remarks"></a>Примечания

> [!IMPORTANT]
> Следующие описания и примеры допустимы в Windows для архитектур x86 и x64. Реализация операторов сдвига влево и сдвига вправо в Windows для устройств ARM существенно различается. Дополнительные сведения см. в разделе "операторы сдвига" в записи блога [Hello ARM](https://devblogs.microsoft.com/cppblog/hello-arm-exploring-undefined-unspecified-and-implementation-defined-behavior-in-c/) .

## <a name="left-shifts"></a>Сдвиги влево

Оператор сдвига влево приводит к тому, что биты в *выражении сдвига* сдвигаются влево на число позиций, заданное *аддитивным выражением*. Позиции битов, освобожденные при операции сдвига, заполняются нулями. Сдвиг влево является логическим сдвигом (биты, сдвигаемые с конца отбрасываются, включая бит знака). Дополнительные сведения о типах побитовых сдвигов см. в разделе [побитовые сдвиги](https://en.wikipedia.org/wiki/Bitwise_shift).

В следующем примере показаны операции сдвига влево с использованием чисел без знака. В этом примере показано, что происходит с битами при представлении значения как bitset. Дополнительные сведения см. в разделе [класс битовом массиве](../standard-library/bitset-class.md).

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned short short1 = 4;
    bitset<16> bitset1{short1};   // the bitset representation of 4
    cout << bitset1 << endl;  // 0b00000000'00000100

    unsigned short short2 = short1 << 1;     // 4 left-shifted by 1 = 8
    bitset<16> bitset2{short2};
    cout << bitset2 << endl;  // 0b00000000'00001000

    unsigned short short3 = short1 << 2;     // 4 left-shifted by 2 = 16
    bitset<16> bitset3{short3};
    cout << bitset3 << endl;  // 0b00000000'00010000
}
```

Если выполняется сдвиг влево числа со знаком и при этом затрагивается бит знака, результат не определен. В следующем примере показано, что происходит при сдвиге 1-й бита на разряд знака.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short short1 = 16384;
    bitset<16> bitset1(short1);
    cout << bitset1 << endl;  // 0b01000000'00000000

    short short3 = short1 << 1;
    bitset<16> bitset3(short3);  // 16384 left-shifted by 1 = -32768
    cout << bitset3 << endl;  // 0b10000000'00000000

    short short4 = short1 << 14;
    bitset<16> bitset4(short4);  // 4 left-shifted by 14 = 0
    cout << bitset4 << endl;  // 0b00000000'00000000
}
```

## <a name="right-shifts"></a>Сдвиги вправо

Оператор сдвига вправо вызывает сдвиг битового шаблона в *выражении сдвига* вправо на число позиций, заданное *аддитивным выражением*. Для чисел без знака позиции битов, освобожденные при операции сдвига, заполняются нулями. Для чисел со знаком бит знака используется для заполнения освобожденных позиций битов. Другими словами, если число является положительным, используется 0, если число является отрицательным, используется 1.

> [!IMPORTANT]
> Результат сдвига вправо отрицательного числа со знаком зависит от реализации. Несмотря на то, что компилятор Microsoft C++ использует бит знака для заполнения освобожденных битовых позиций, нет никакой гарантии, что это также делается для других реализаций.

В следующем примере показаны операции сдвига вправо с использованием чисел без знака.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned short short11 = 1024;
    bitset<16> bitset11{short11};
    cout << bitset11 << endl;     // 0b00000100'00000000

    unsigned short short12 = short11 >> 1;  // 512
    bitset<16> bitset12{short12};
    cout << bitset12 << endl;     // 0b00000010'00000000

    unsigned short short13 = short11 >> 10;  // 1
    bitset<16> bitset13{short13};
    cout << bitset13 << endl;     // 0b00000000'00000001

    unsigned short short14 = short11 >> 11;  // 0
    bitset<16> bitset14{short14};
    cout << bitset14 << endl;     // 0b00000000'00000000
}
```

В следующем примере показаны операции сдвига вправо с использованием положительных чисел со знаком.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short short1 = 1024;
    bitset<16> bitset1(short1);
    cout << bitset1 << endl;     // 0b00000100'00000000

    short short2 = short1 >> 1;  // 512
    bitset<16> bitset2(short2);
    cout << bitset2 << endl;     // 0b00000010'00000000

    short short3 = short1 >> 11;  // 0
    bitset<16> bitset3(short3);
    cout << bitset3 << endl;     // 0b00000000'00000000
}
```

В следующем примере показаны операции сдвига вправо с использованием отрицательных целых чисел со знаком.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short neg1 = -16;
    bitset<16> bn1(neg1);
    cout << bn1 << endl;  // 0b11111111'11110000

    short neg2 = neg1 >> 1; // -8
    bitset<16> bn2(neg2);
    cout << bn2 << endl;  // 0b11111111'11111000

    short neg3 = neg1 >> 2; // -4
    bitset<16> bn3(neg3);
    cout << bn3 << endl;  // 0b11111111'11111100

    short neg4 = neg1 >> 4; // -1
    bitset<16> bn4(neg4);
    cout << bn4 << endl;  // 0b11111111'11111111

    short neg5 = neg1 >> 5; // -1
    bitset<16> bn5(neg5);
    cout << bn5 << endl;  // 0b11111111'11111111
}
```

## <a name="shifts-and-promotions"></a>Сдвиги и перемещения

Выражения с обеих сторон оператора сдвига должны быть целочисленными типами. Целочисленные акции выполняются в соответствии с правилами, описанными в разделе [стандартные преобразования](standard-conversions.md). Тип результата совпадает с типом повышенного *выражения сдвига*.

В следующем примере переменная типа **`char`** повышается до **`int`** .

```cpp
#include <iostream>
#include <typeinfo>

using namespace std;

int main() {
    char char1 = 'a';

    auto promoted1 = char1 << 1;   // 194
    cout << typeid(promoted1).name() << endl;  // int

    auto promoted2 = char1 << 10;  // 99328
    cout << typeid(promoted2).name() << endl;  // int
}
```

## <a name="additional-details"></a>Дополнительные сведения

Результат операции сдвига не определен, если *аддитивное выражение* является отрицательным или если *аддитивное выражение* больше или равно количеству битов в *выражении сдвига*(повышенной). Если *аддитивное выражение* имеет значение 0, то операция сдвига не выполняется.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned int int1 = 4;
    bitset<32> b1{int1};
    cout << b1 << endl;    // 0b00000000'00000000'00000000'00000100

    unsigned int int2 = int1 << -3;  // C4293: '<<' : shift count negative or too big, undefined behavior
    unsigned int int3 = int1 >> -3;  // C4293: '>>' : shift count negative or too big, undefined behavior
    unsigned int int4 = int1 << 32;  // C4293: '<<' : shift count negative or too big, undefined behavior
    unsigned int int5 = int1 >> 32;  // C4293: '>>' : shift count negative or too big, undefined behavior
    unsigned int int6 = int1 << 0;
    bitset<32> b6{int6};
    cout << b6 << endl;    // 0b00000000'00000000'00000000'00000100 (no change)
}
```

## <a name="footnotes"></a>Примечания

<sup>1</sup> ниже приведено описание операторов сдвига в спецификации C++ 11 ISO (ИНЦИТС/ISO/IEC 14882-2011 [2012]), разделы 5.8.2 и 5.8.3.

Значение `E1 << E2` представляет собой `E1` со сдвигом влево на `E2` позиций битов; освобожденные биты заполняются нулями. Если `E1` имеет тип без знака, то результатом будет значение **E1 × 2**<sup>**E2**</sup>, но по меньшей мере остаток от деления превышает максимальное значение, которое может быть представлено в типе результата. В противном случае, если `E1` имеет тип со знаком и неотрицательное значение, а **E1 × 2**<sup>**E2**</sup> может быть представлено в соответствующем неподписанном типе результата, то это значение, преобразованное в тип результата, является результирующим значением; в противном случае поведение не определено.

Значение `E1 >> E2` представляет собой `E1` со сдвигом вправо на `E2` позиций битов. Если `E1` имеет тип без знака или если `E1` имеет тип со знаком и неотрицательное значение, значение результата является неотъемлемой частью частного числа **E1/2**<sup>**E2**</sup>. Если `E1` имеет тип со знаком и отрицательное значение, значение результата определяется реализацией.

## <a name="see-also"></a>См. также раздел

[Выражения с бинарными операторами](../cpp/expressions-with-binary-operators.md)<br/>
[Операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
