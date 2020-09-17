---
title: '&lt;битовые &gt; функции'
description: Функции для доступа к отдельным битам и последовательностям бит и их обработки.
ms.date: 08/28/2020
f1_keywords:
- bit/std::bit_cast
- bit/std::has_single_bit
- bit/std::bit_ceil
- bit/std::bit_floor
- bit/std::bit_width
- bit/std::rotl
- bit/std::rotr
- bit/std::countl_zero
- bit/std::countl_one
- bit/std::countr_zero
- bit/std::countr_one
- bit/std::popcount
helpviewer_keywords:
- std::bit [C++], bit_cast
- std::bit [C++], has_single_bit
- std::bit [C++], bit_ceil
- std::bit [C++], bit_floor
- std::bit [C++], bit_width
- std::bit [C++], rotl
- std::bit [C++], rotr
- std::bit [C++], countl_zero
- std::bit [C++], countl_one
- std::bit [C++], countr_zero
- std::bit [C++], countr_one
- std::bit [C++], popcount
ms.openlocfilehash: a2408df9aa13c6e714f615561871397be17fc4a3
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039820"
---
# <a name="ltbitgt-functions"></a>&lt;битовые &gt; функции

\<bit>Заголовок содержит следующие функции-шаблоны, не являющиеся членами:

| **Функции, не являющиеся членами** | **Описание** |
|--------|---------|
|[bit_cast](#bit_cast) | Воспримет представление объекта из одного типа в другой. |
|[bit_ceil](#bit_ceil) | Найти наименьшую степень числа двух значений или больше. |
|[bit_floor](#bit_floor) | Найдите максимальную степень числа 2, не превышающую значение. |
|[bit_width](#bit_width) | Найти наименьшее количество битов, необходимых для представления значения. |
|[countl_zero](#countl_zero) | Подсчитайте число последовательных битов, равных нулю, начиная с самого большого бита. |
|[countl_one](#countl_one) | Подсчитайте число последовательных битов, для которых задано значение 1, начиная с самого большого бита. |
|[countr_zero](#countr_zero) | Подсчитайте число последовательных битов, равных нулю, начиная с наименее значащих бит. |
|[countr_one](#countl_one) | Подсчитайте число последовательных битов, для которых задано значение 1, начиная с наименее значащих бит. |
|[has_single_bit](#has_single_bit) | Проверьте, имеет ли значение один бит, равный одному. Это то же самое, что и проверка того, является ли значение степенью двух. |
|[попкаунт](#popcount) | Подсчитайте число битов, для которых задано значение 1. |
|[ротл](#rotl) | Вычисление результата побитового сдвига влево. |
|[ротр](#rotr) | Вычисление результата побитового сдвига вправо. |

## <a name="bit_cast"></a>`bit_cast`

Скопируйте битовый шаблон из объекта типа `From` в новый объект типа `To` .

```cpp
template <class To, class From>
[[nodiscard]] constexpr To bit_cast(const From& from) noexcept;
```

### <a name="parameters"></a>Параметры

*Кому*\
Тип выхода.

*От*\
Тип, в который нужно преобразовать значение.

*От*\
Преобразуемое значение.

### <a name="return-value"></a>Возвращаемое значение

Объект типа `To`.

Каждый бит в результате соответствует соответствующему биту в `from` , если в не есть биты заполнения в `To` , в этом случае эти биты в результате не будут указаны.

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <iostream>

int main()
{
    float f = std::numeric_limits<float>::infinity();
    int i = std::bit_cast<int>(f);
    std::cout << "float f = " << std::hex << f
              << "\nstd::bit_cat<int>(f) = " << std::hex << i << '\n';
    return 0;
}
```

```Output
float f = inf
std::bit_cat<int>(f) = 7f800000
```

### <a name="remarks"></a>Комментарии

Код низкого уровня часто должен интерпретировать объект одного типа как другой тип. Переинтерпретируемый объект имеет то же битовое представление, что и исходный, но имеет другой тип.

Вместо использования `reinterpret_cast` , или `memcpy()` , `bit_cast()` является лучшим способом выполнения этих преобразований. Это лучше, поскольку:
- `bit_cast()` равно `constexpr`
- `bit_cast()` требует, чтобы типы были просто скопированы и иметь одинаковый размер. Это позволяет избежать потенциальных проблем, с которыми можно столкнуться при использовании `reinterpret_cast` и, `memcpy` поскольку они могут использоваться для непреднамеренного и некорректного преобразования нетривиальных копий типов. Кроме того, можно `memcpy()` использовать для непреднамеренного копирования типов, которые имеют неодинаковый размер. Например, Double (8 байт) в целое число без знака (4 байта) или наоборот.

Эта перегрузка принимает участие в разрешении перегрузки только в том случае, если:
-  `sizeof(To) == sizeof(From)`
- `To` и `From` являются [is_trivially_copyableми](is-trivially-copyable-class.md).

Этот шаблон функции имеет значение, `constexpr` только если `To` , и `From` типы их подобъектов:
- не является типом объединения или указателя
- не является указателем на тип элемента
- без временных квалификаторов
- не иметь нестатических элементов данных, являющихся ссылочным типом

## <a name="bit_ceil"></a>`bit_ceil`

Найти наименьшую степень числа двух значений или больше. Например, `3` возвращает `4` .

```cpp
template<class T>
[[nodiscard]] constexpr T bit_ceil(T value);
```

### <a name="parameters"></a>Параметры

*value*\
Целочисленное значение без знака для проверки.

### <a name="return-value"></a>Возвращаемое значение

 Наименьшая степень числа двух больше или равна `value` .

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (auto i = 0u; i < 6u; ++i) // bit_ceil() takes an unsigned integer type
    {
        auto nextClosestPowerOf2 = std::bit_ceil(i);
        std::cout << "\nbit_ceil(0b" << std::bitset<4>(i) << ") = "
                  << "0b" << std::bitset<4>(nextClosestPowerOf2);
    }
    return 0;
}
```

```Output
bit_ceil(0b0000) = 0b0001
bit_ceil(0b0001) = 0b0001
bit_ceil(0b0010) = 0b0010
bit_ceil(0b0011) = 0b0100
bit_ceil(0b0100) = 0b0100
bit_ceil(0b0101) = 0b1000
```

### <a name="remarks"></a>Комментарии

Эта функция шаблона участвует в разрешении перегрузки только в `T` том случае, если является целочисленным типом без знака. Например: `unsigned int` , `unsigned long` , `unsigned short` , `unsigned char` и т. д.

## <a name="bit_floor"></a>`bit_floor`

Найдите максимальную степень числа 2, не превышающую значение. Например, `5` возвращает `4` .

```cpp
template< class T >
[[nodiscard]] constexpr T bit_floor(T value) noexcept;
```

### <a name="parameters"></a>Параметры

*value*\
Целочисленное значение без знака для проверки.

### <a name="return-value"></a>Возвращаемое значение

Самая большая степень числа двух, которая не больше, чем `value` .
Если значение `value` равно нулю, возвращает ноль.

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (auto i = 0u; i < 6u; ++i) // bit_floor() takes an unsigned integer type
    {
        auto previousPowerOf2 = std::bit_floor(i);
        std::cout << "\nbit_floor(0b" << std::bitset<4>(i) << ") = 0b"
                  << std::bitset<4>(previousPowerOf2);
    }
    return 0;
}
```

```Output
bit_floor(0b0000) = 0b0000
bit_floor(0b0001) = 0b0001
bit_floor(0b0010) = 0b0010
bit_floor(0b0011) = 0b0010
bit_floor(0b0100) = 0b0100
bit_floor(0b0101) = 0b0100
```

### <a name="remarks"></a>Комментарии

Эта функция шаблона участвует в разрешении перегрузки только в `T` том случае, если является целочисленным типом без знака. Например: `unsigned int` , `unsigned long` , `unsigned short` , `unsigned char` и т. д.

## <a name="bit_width"></a>`bit_width`

Найти наименьшее количество битов, необходимых для представления значения.

Например, если задано значение 5 (0b101), функция возвращает 3, так как для выражения значения 5 требуется 3 двоичных бита.

```cpp
template<class T>
[[nodiscard]] constexpr T bit_width(T value) noexcept;
```

### <a name="parameters"></a>Параметры

*value*\
Целочисленное значение без знака для проверки.

### <a name="return-value"></a>Возвращаемое значение

Число битов, которые необходимо представить `value` .
Если значение `value` равно нулю, возвращает ноль.

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <iostream>

int main()
{
    for (unsigned i=0u; i <= 8u; ++i)
    {
        std::cout << "\nbit_width(" << i << ") = "
                  << std::bit_width(i);
    }
    return 0;
}
```

```Output
bit_width(0) = 0
bit_width(1) = 1
bit_width(2) = 2
bit_width(3) = 2
bit_width(4) = 3
bit_width(5) = 3
bit_width(6) = 3
bit_width(7) = 3
bit_width(8) = 4
```

### <a name="remarks"></a>Комментарии

Эта функция шаблона участвует в разрешении перегрузки только в `T` том случае, если является целочисленным типом без знака. Например: `unsigned int` , `unsigned long` , `unsigned short` , `unsigned char` и т. д.

## <a name="countl_zero"></a>`countl_zero`

Подсчитайте число последовательных битов, равных нулю, начиная с самого большого бита.

```cpp
template<class T>
[[nodiscard]] constexpr int countl_zero(T value) noexcept;
```

### <a name="parameters"></a>Параметры

*value*\
Целочисленное значение без знака для проверки.

### <a name="return-value"></a>Возвращаемое значение

Число последовательных нулевых битов, начиная с самого большого бита. \
Если `value` равно нулю, число битов в типе `value` .

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (unsigned char result = 0, i = 0; i < 9; i++)
    {
        std::cout << "\ncountl_zero(0b" << std::bitset<8>(result) << ") = " << std::countl_zero(result);
        result = result == 0 ? 1 : result * 2;
    }
    return 0;
}
```

```Output
countl_zero(0b00000000) = 8
countl_zero(0b00000001) = 7
countl_zero(0b00000010) = 6
countl_zero(0b00000100) = 5
countl_zero(0b00001000) = 4
countl_zero(0b00010000) = 3
countl_zero(0b00100000) = 2
countl_zero(0b01000000) = 1
countl_zero(0b10000000) = 0
```

### <a name="remarks"></a>Комментарии

Эта функция шаблона участвует в разрешении перегрузки только в `T` том случае, если является целочисленным типом без знака. Например: `unsigned int` , `unsigned long` , `unsigned short` , `unsigned char` и т. д.

## <a name="countl_one"></a>`countl_one`

Подсчитайте число последовательных битов, для которых задано значение 1, начиная с самого большого бита.

```cpp
template<class T>
[[nodiscard]] constexpr int countl_one(T value) noexcept;
```

### <a name="parameters"></a>Параметры

*value*\
Целочисленное значение без знака для проверки.

### <a name="return-value"></a>Возвращаемое значение

Число последовательных битов, для которых задано значение 1, начиная с наиболее значимого бита.

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char value = 0;
    for (unsigned char bit = 128; bit > 0; bit /= 2)
    {
        value |= bit;
        std::cout << "\ncountl_one(0b" << std::bitset<8>(value) << ") = "
                  << std::countl_one(value);
    }
    return 0;
}
```

```Output
countl_one(0b10000000) = 1
countl_one(0b11000000) = 2
countl_one(0b11100000) = 3
countl_one(0b11110000) = 4
countl_one(0b11111000) = 5
countl_one(0b11111100) = 6
countl_one(0b11111110) = 7
countl_one(0b11111111) = 8
```

### <a name="remarks"></a>Комментарии

Эта функция шаблона участвует в разрешении перегрузки только в `T` том случае, если является целочисленным типом без знака. Например: `unsigned int` , `unsigned long` , `unsigned short` , `unsigned char` и т. д.

## <a name="countr_zero"></a>`countr_zero`

Подсчитайте число последовательных битов, равных нулю, начиная с наименее значащих бит.

```cpp
template<class T>
[[nodiscard]] constexpr int countr_zero(T value) noexcept;
```

### <a name="parameters"></a>Параметры

*value*\
Целочисленное значение без знака для проверки.

### <a name="return-value"></a>Возвращаемое значение

Число последовательных нулей, начиная с наименее значащих бит. \
Если `value` равно нулю, число битов в типе `value` .

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (unsigned char result = 0, i = 0; i < 9; i++)
    {
        std::cout << "\ncountr_zero(0b" << std::bitset<8>(result) << ") = "
                  << std::countr_zero(result);
        result = result == 0 ? 1 : result * 2;
    }
    return 0;
}
```

```Output
countr_zero(0b00000000) = 8
countr_zero(0b00000001) = 0
countr_zero(0b00000010) = 1
countr_zero(0b00000100) = 2
countr_zero(0b00001000) = 3
countr_zero(0b00010000) = 4
countr_zero(0b00100000) = 5
countr_zero(0b01000000) = 6
countr_zero(0b10000000) = 7
```

### <a name="remarks"></a>Комментарии

Эта функция шаблона участвует в разрешении перегрузки только в `T` том случае, если является целочисленным типом без знака. Например: `unsigned int` , `unsigned long` , `unsigned short` , `unsigned char` и т. д.

## <a name="countr_one"></a>`countr_one`

Подсчитайте число последовательных битов, для которых задано значение 1, начиная с наименее значащих бит.

```cpp
template<class T>
[[nodiscard]] constexpr int countr_one(T value) noexcept;
```

### <a name="parameters"></a>Параметры

*value*\
Целочисленное значение без знака для проверки.

### <a name="return-value"></a>Возвращаемое значение

Число последовательных битов, для которых задано значение 1, начиная с наименее значимого бита.

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char value = 0;
    for (int bit = 1; bit <= 128; bit *= 2)
    {
        value |= bit;
        std::cout << "\ncountr_one(0b" << std::bitset<8>(value) << ") = "
                  << std::countr_one(value);
    }
    return 0;
}
```

```Output
countr_one(0b00000001) = 1
countr_one(0b00000011) = 2
countr_one(0b00000111) = 3
countr_one(0b00001111) = 4
countr_one(0b00011111) = 5
countr_one(0b00111111) = 6
countr_one(0b01111111) = 7
countr_one(0b11111111) = 8
```

### <a name="remarks"></a>Комментарии

Эта функция шаблона участвует в разрешении перегрузки только в `T` том случае, если является целочисленным типом без знака. Например: `unsigned int` , `unsigned long` , `unsigned short` , `unsigned char` и т. д.

## <a name="has_single_bit"></a>`has_single_bit`

Проверьте, имеет ли значение только один битовый набор. Это то же самое, что и проверка того, является ли значение степенью двух.
 
```cpp
template <class T>
[[nodiscard]] constexpr bool has_single_bit(T value) noexcept;
```

### <a name="parameters"></a>Параметры

*value*\
Целочисленное значение без знака для проверки.

### <a name="return-value"></a>Возвращаемое значение

`true``value`значение, если имеет только один бит, что также означает `value` степень числа двух. В противном случае — значение `false`.

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <bitset>
#include <iostream>
#include <iomanip>

int main()
{
    for (auto i = 0u; i < 10u; ++i)
    {
        std::cout << "has_single_bit(0b" << std::bitset<4>(i) << ") = "
                  << std::boolalpha << std::has_single_bit(i) << '\n';
    }
    return 0;
}
```

```Output
has_single_bit(0b0000) = false
has_single_bit(0b0001) = true
has_single_bit(0b0010) = true
has_single_bit(0b0011) = false
has_single_bit(0b0100) = true
has_single_bit(0b0101) = false
has_single_bit(0b0110) = false
has_single_bit(0b0111) = false
has_single_bit(0b1000) = true
has_single_bit(0b1001) = false
```

### <a name="remarks"></a>Комментарии

Эта функция шаблона участвует в разрешении перегрузки только в `T` том случае, если является целочисленным типом без знака. Например: `unsigned int` , `unsigned long` , `unsigned short` , `unsigned char` и т. д.

## <a name="popcount"></a>`popcount`

Подсчитайте число битов, равных одному, в целочисленном значении без знака.
 
```cpp
template<class T>
[[nodiscard]] constexpr int popcount(T value) noexcept;
```

### <a name="parameters"></a>Параметры

*value*\
Целочисленное значение без знака для проверки.

### <a name="return-value"></a>Возвращаемое значение

Число битов, заданных в параметре, равное единице `value` .

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
   for (unsigned char value = 0; value < 16; value++)
    {
        std::cout << "\npopcount(0b" << std::bitset<4>(value) << ") = "
                  << std::popcount(value);
    }
    return 0;
}
```

```Output
popcount(0b0000) = 0
popcount(0b0001) = 1
popcount(0b0010) = 1
popcount(0b0011) = 2
popcount(0b0100) = 1
popcount(0b0101) = 2
popcount(0b0110) = 2
popcount(0b0111) = 3
popcount(0b1000) = 1
popcount(0b1001) = 2
popcount(0b1010) = 2
popcount(0b1011) = 3
popcount(0b1100) = 2
popcount(0b1101) = 3
popcount(0b1110) = 3
popcount(0b1111) = 4
```

### <a name="remarks"></a>Комментарии

Эта функция шаблона участвует в разрешении перегрузки только в `T` том случае, если является целочисленным типом без знака. Например: `unsigned int` , `unsigned long` , `unsigned short` , `unsigned char` и т. д.

## <a name="rotl"></a>`rotl`

Поворачивает биты целочисленного значения без знака влево на указанное число раз. Биты, которые «попадают» из самого левого бита, поворачиваются в самый правый бит.
 
```cpp
template<class T>
[[nodiscard]] constexpr T rotl(T value, int s) noexcept;
```

### <a name="parameters"></a>Параметры

*value*\
Целочисленное значение без знака для поворота.

*#d0*\
Количество выполняемых левых поворотов.

### <a name="return-value"></a>Возвращаемое значение

Результат поворота `value` слева, `s` раз.
Если значение `s` равно нулю, функция возвращает `value` .
Если `s` является отрицательным, то имеет значение `rotr(value, -s)` . Биты, которые попадают в крайний правый бит, поворачиваются в крайний левый бит.

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char bits = 1;
    for (int i = 0; i < 8; ++i)
    {
        std::cout << "rotl(0b" << std::bitset<8>(bits) << ", 1) = ";
        bits = std::rotl(bits, 1);
        std::cout << "0b" << std::bitset<8>(bits) << '\n';
    }
    std::cout << "rotl(0b" << std::bitset<8>(bits) << ",-1) = ";
    bits = std::rotl(bits, -1);
    std::cout << "0b" << std::bitset<8>(bits);
    return 0;
}
```

```Output
rotl(0b00000001, 1) = 0b00000010
rotl(0b00000010, 1) = 0b00000100
rotl(0b00000100, 1) = 0b00001000
rotl(0b00001000, 1) = 0b00010000
rotl(0b00010000, 1) = 0b00100000
rotl(0b00100000, 1) = 0b01000000
rotl(0b01000000, 1) = 0b10000000
rotl(0b10000000, 1) = 0b00000001
rotl(0b00000001,-1) = 0b10000000
```

### <a name="remarks"></a>Комментарии

Эта функция шаблона участвует в разрешении перегрузки только в `T` том случае, если является целочисленным типом без знака. Например: `unsigned int` , `unsigned long` , `unsigned short` , `unsigned char` и т. д.

## <a name="rotr"></a>`rotr`

Поворачивает биты `value` справа заданное число раз. Биты, которые "попадают" из крайнего правого бита, поворачиваются обратно в самый левый бит.
 
```cpp
template<class T>
[[nodiscard]] constexpr T rotr(T value, int s) noexcept;
```

### <a name="parameters"></a>Параметры

*value*\
Целочисленное значение без знака для поворота.

*#d0*\
Количество выполняемых вправо поворотов.

### <a name="return-value"></a>Возвращаемое значение

Результат поворота `value` вправо, `s` раз.
Если значение `s` равно нулю, функция возвращает `value` .
Если `s` является отрицательным, то имеет значение `rotl(value, -s)` . Биты, которые попадают из самого левого бита, поворачиваются обратно в самый правый бит.

### <a name="example"></a>Пример

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char bits = 128;
    for (int i = 0; i < 8; ++i)
    {
        std::cout << "rotr(0b" << std::bitset<8>(bits) << ", 1) = ";
        bits = std::rotr(bits, 1);
        std::cout << "0b" << std::bitset<8>(bits) << '\n';
    }
    std::cout << "rotr(0b" << std::bitset<8>(bits) << ",-1) = ";
    bits = std::rotr(bits, -1);
    std::cout << "0b" << std::bitset<8>(bits);
    return 0;
}
```

```Output
rotr(0b10000000, 1) = 0b01000000
rotr(0b01000000, 1) = 0b00100000
rotr(0b00100000, 1) = 0b00010000
rotr(0b00010000, 1) = 0b00001000
rotr(0b00001000, 1) = 0b00000100
rotr(0b00000100, 1) = 0b00000010
rotr(0b00000010, 1) = 0b00000001
rotr(0b00000001, 1) = 0b10000000
rotr(0b10000000,-1) = 0b00000001
```

### <a name="remarks"></a>Комментарии

Эта функция шаблона участвует в разрешении перегрузки только в `T` том случае, если является целочисленным типом без знака. Например: `unsigned int` , `unsigned long` , `unsigned short` , `unsigned char` и т. д.

## <a name="requirements"></a>Требования

**Заголовок:**\<bit>

**Пространство имен:** std

[/std: требуется более поздняя версия c + +](../build/reference/std-specify-language-standard-version.md) .

## <a name="see-also"></a>См. также раздел

[\<bit>](bit.md)