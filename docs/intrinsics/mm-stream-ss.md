---
title: _mm_stream_ss
ms.date: 09/02/2019
f1_keywords:
- _mm_stream_ss
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
ms.openlocfilehash: ef1a2045a20070b667d416175826e5377fe30ef6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215989"
---
# <a name="_mm_stream_ss"></a>_mm_stream_ss

**Блок, относящийся только к системам Microsoft**

Записывает 32-битные данные в расположение в памяти, не замусоривать кэши.

## <a name="syntax"></a>Синтаксис

```C
void _mm_stream_ss(
   float * Destination,
   __m128 Source
);
```

### <a name="parameters"></a>Параметры

*Местоназначение*\
заполняет Указатель на расположение, в которое записываются исходные данные.

*Источника*\
окне 128-разрядное число, содержащее значение, которое **`float`** должно быть записано в последние 32 бит.

## <a name="return-value"></a>Возвращаемое значение

Нет.

## <a name="requirements"></a>Требования

|Intrinsic|Architecture|
|---------------|------------------|
|`_mm_stream_ss`|SSE4a|

**Файл заголовка** \<intrin.h>

## <a name="remarks"></a>Примечания

Внутренняя функция создает `movntss` инструкцию. Чтобы определить поддержку оборудования для этой инструкции, вызовите `__cpuid` встроенную функцию с параметром `InfoType=0x80000001` и установите бит 6 из `CPUInfo[2] (ECX)` . Этот бит равен 1, если инструкция поддерживается, и 0 в противном случае.

Если запустить код, использующий `_mm_stream_ss` встроенное на оборудовании, которое не поддерживает эту `movntss` инструкцию, результаты будут непредсказуемыми.

## <a name="example"></a>Пример

```cpp
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
    __m128 vals;
    float f[4];

    f[0] = -1.;
    f[1] = -2.;
    f[2] = -3.;
    f[3] = -4.;
    vals.m128_f32[0] = 0.;
    vals.m128_f32[1] = 1.;
    vals.m128_f32[2] = 2.;
    vals.m128_f32[3] = 3.;
    _mm_stream_ss(&f[3], vals);
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;
}
```

```Output
f[0] = -1, f[1] = -2
f[2] = -3, f[3] = 3
```

**Завершение блока, относящегося только к системам Майкрософт**

Для частей авторские права на 2007 по расширенным микроустройствам, Inc. Все права защищены. Воспроизводить с разрешением от расширенных микроустройств, Inc.

## <a name="see-also"></a>См. также раздел

[_mm_stream_sd](../intrinsics/mm-stream-sd.md)\
[_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)\
[_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)\
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)\
[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)
