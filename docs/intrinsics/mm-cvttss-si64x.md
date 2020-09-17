---
title: _mm_cvttss_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_cvttss_si64x
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
ms.openlocfilehash: 6d920a5c59cacb23c7fb155c7ac8e813a9b0e8d0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217991"
---
# <a name="_mm_cvttss_si64x"></a>_mm_cvttss_si64x

**Блок, относящийся только к системам Microsoft**

Выдает расширенную версию x64 инструкции CONVERT с плавающей запятой одиночной точности до 64-разрядного целого числа ( `cvttss2si` ).

## <a name="syntax"></a>Синтаксис

```C
__int64 _mm_cvttss_si64x(
   __m128 value
);
```

### <a name="parameters"></a>Параметры

*значений*\
окне **`__m128`** Структура, содержащая значения с плавающей точкой одиночной точности.

## <a name="return-value"></a>Возвращаемое значение

Результат преобразования первого значения с плавающей запятой в 64-разрядное целое число.

## <a name="requirements"></a>Требования

|Intrinsic|Architecture|
|---------------|------------------|
|`_mm_cvttss_si64x`|X64|

**Файл заголовка** \<intrin.h>

## <a name="remarks"></a>Примечания

Внутренняя функция отличается от того `_mm_cvtss_si64x` , что неточные преобразования усекаются в сторону нуля. Поскольку **`__m128`** структура представляет регистр XMM, созданная инструкция перемещает данные из регистра XMM в системную память.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```cpp
// _mm_cvttss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvttss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] = { 101.5, 200.75,
                                          300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvttss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__m128](../cpp/m128.md)\
[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)
