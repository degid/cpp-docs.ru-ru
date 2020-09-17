---
title: _mm_cvtss_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_cvtss_si64x
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
ms.openlocfilehash: bc6e33da5ac7b25727f6e24c3af6e6a926b29847
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230510"
---
# <a name="_mm_cvtss_si64x"></a>_mm_cvtss_si64x

**Блок, относящийся только к системам Microsoft**

Создает расширенную версию 64-разрядной версии преобразования скалярного числа с плавающей запятой с одинарной точностью до 64 `cvtss2si` .

## <a name="syntax"></a>Синтаксис

```C
__int64 _mm_cvtss_si64x(
   __m128 value
);
```

### <a name="parameters"></a>Параметры

*значений*\
окне **`__m128`** Структура, содержащая плавающие значения типа Point.

## <a name="return-value"></a>Возвращаемое значение

64-разрядное целое число, результат преобразования первого значения с плавающей запятой в целое число.

## <a name="requirements"></a>Требования

|Intrinsic|Architecture|
|---------------|------------------|
|`_mm_cvtss_si64x`|X64|

**Файл заголовка** \<intrin.h>

## <a name="remarks"></a>Примечания

Первый элемент значения структуры преобразуется в целое число и возвращается. Биты управления округлением в МКСКСР используются для определения поведения округления. По умолчанию используется режим округления с округлением до ближайшего значения, округление до четного числа, если десятичная часть равна 0,5. Поскольку **`__m128`** структура представляет регистр XMM, встроенная функция принимает значение из регистра XMM и записывает его в системную память.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```cpp
// _mm_cvtss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] =
                           { 101.25, 200.75, 300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvtss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__m128d](../cpp/m128d.md)\
[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)
