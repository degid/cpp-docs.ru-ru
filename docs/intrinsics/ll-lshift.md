---
title: __ll_lshift
ms.date: 09/02/2019
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
ms.openlocfilehash: 988284b81c9f04ee5d7f09f8a2f173a689f9fb55
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230523"
---
# <a name="__ll_lshift"></a>__ll_lshift

**Блок, относящийся только к системам Microsoft**

Сдвигает переданное 64-разрядное значение влево на указанное число битов.

## <a name="syntax"></a>Синтаксис

```C
unsigned __int64 __ll_lshift(
   unsigned __int64 Mask,
   int nBit
);
```

### <a name="parameters"></a>Параметры

*Виде*\
окне 64-разрядное целочисленное значение, которое необходимо сдвинуть влево.

*нбит*\
окне Число битов для сдвига.

## <a name="return-value"></a>Возвращаемое значение

Маска, смещенная влево по `nBit` битам.

## <a name="requirements"></a>Требования

|Intrinsic|Architecture|
|---------------|------------------|
|`__ll_lshift`|x86, x64|

**Файл заголовка** \<intrin.h>

## <a name="remarks"></a>Примечания

Если вы компилируете программу для 64-разрядной архитектуры и `nBit` превышает 63, число битов для сдвига — остаток от деления по `nBit` модулю 64. Если вы компилируете программу для 32-разрядной архитектуры и `nBit` превышает 31, число битов для сдвига является `nBit` остатком по модулю 32.

`ll`В имени указывает, что это операция над **`long long`** ( **`__int64`** ).

## <a name="example"></a>Пример

```cpp
// ll_lshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_lshift)

int main()
{
   unsigned __int64 Mask = 0x100;
   int nBit = 8;
   Mask = __ll_lshift(Mask, nBit);
   cout << hex << Mask << endl;
}
```

## <a name="output"></a>Выходные данные

```Output
10000
```

> [!NOTE]
> Нет неподписанной версии операции сдвига влево. Это вызвано тем, что `__ll_lshift` уже использует входной параметр без знака. В отличие от сдвига вправо, не существует зависимости от знака сдвига влево, так как наименьший значащий бит в результате всегда имеет нулевое значение, независимо от знака сдвига значения.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__ll_rshift](../intrinsics/ll-rshift.md)\
[__ull_rshift](../intrinsics/ull-rshift.md)\
[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)
