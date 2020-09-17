---
title: __ll_rshift
ms.date: 09/02/2019
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
ms.openlocfilehash: 6ae750f1a8825096ee30adb01768d5603ab23a01
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219668"
---
# <a name="__ll_rshift"></a>__ll_rshift

**Блок, относящийся только к системам Microsoft**

Сдвигает 64-разрядное значение, заданное первым параметром вправо, на число битов, заданное вторым параметром.

## <a name="syntax"></a>Синтаксис

```C
__int64 __ll_rshift(
   __int64 Mask,
   int nBit
);
```

### <a name="parameters"></a>Параметры

*Виде*\
окне 64-разрядное целочисленное значение, которое нужно сдвинуть вправо.

*нбит*\
окне Число битов для сдвига, остаток от деления 64 на x64 и остаток от деления 32 на x86.

## <a name="return-value"></a>Возвращаемое значение

Маска, смещенная по `nBit` битам.

## <a name="requirements"></a>Требования

|Intrinsic|Architecture|
|---------------|------------------|
|`__ll_rshift`|x86, x64|

**Файл заголовка** \<intrin.h>

## <a name="remarks"></a>Примечания

Если второй параметр больше 64 в x64 (32 на x86), то это число берется по модулю 64 (32 на x86), чтобы определить число битов для сдвига. `ll`Префикс указывает, что это операция над **`long long`** , еще одно имя для **`__int64`** , 64-разрядного целочисленного типа со знаком.

## <a name="example"></a>Пример

```cpp
// ll_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_rshift)

int main()
{
   __int64 Mask = - 0x100;
   int nBit = 4;
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
   Mask = __ll_rshift(Mask, nBit);
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
}
```

## <a name="output"></a>Выходные данные

```Output
ffffffffffffff00
- 100
fffffffffffffff0
- 10
```

> [!NOTE]
> Если `_ull_rshift` использовался параметр, то в случае отрицательного значения не было бы получено значение конца старшего смещенного сдвига, чтобы получить требуемый результат.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ull_rshift](../intrinsics/ull-rshift.md)
