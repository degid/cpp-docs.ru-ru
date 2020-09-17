---
title: _mm_insert_si64, _mm_inserti_si64
ms.date: 09/02/2019
f1_keywords:
- _mm_inserti_si64
- _mm_insert_si64
helpviewer_keywords:
- insertq instruction
- _mm_insert_si64 intrinsic
- _mm_inserti_si64 intrinsic
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
ms.openlocfilehash: 08469ad8049df2a07f0e66d650c1ca3118f8b980
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221772"
---
# <a name="_mm_insert_si64-_mm_inserti_si64"></a>_mm_insert_si64, _mm_inserti_si64

**Блок, относящийся только к системам Microsoft**

`insertq` Формирует инструкцию для вставки битов из второго операнда в первый операнд.

## <a name="syntax"></a>Синтаксис

```C
__m128i _mm_insert_si64(
   __m128i Source1,
   __m128i Source2
);
__m128i _mm_inserti_si64(
   __m128i Source1,
   __m128i Source2
   int Length,
   int Index
);
```

### <a name="parameters"></a>Параметры

*Источник1*\
окне 128-битовое поле, содержащее входные данные в младших 64 битах, в которые будет вставлено поле.

*Source2*\
окне 128-битовое поле, в котором находятся данные, вставляемые в младшие биты.  Для `_mm_insert_si64`свойство также содержит дескриптор поля в его старших битах.

*Недопустим*\
окне Целочисленная константа, указывающая длину вставляемого поля.

*Номер*\
окне Целочисленная константа, указывающая индекс наименее значимого бита поля, в который будут вставлены данные.

## <a name="return-value"></a>Возвращаемое значение

128-битовое поле, более 64 низкие биты которого содержат исходные младшие биты в64, с заданным битовым полем, замененным младшими битами *source2*. Верхние 64 разрядов возвращаемого значения не определены.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_mm_insert_si64`|SSE4a|
|`_mm_inserti_si64`|SSE4a|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

Эти встроенные функции создают `insertq` инструкцию для вставки битов из *source2* в *Source1*. Существует две версии: `_mm_inserti_si64`, является немедленной версией и `_mm_insert_si64` является непосредственным вариантом. Каждая версия извлекает битовое поле заданной длины из source2 и вставляет его в Source1.  Извлеченные биты — это наименее значащие биты source2.  Поле source1, в которое будут вставлены эти биты, определяется длиной и индексом наименее значимого бита.  Значения длины и индекса взяты в MOD 64, поэтому обе-1 и 127 интерпретируется как 63. Если сумма (уменьшенная) индекса (с сокращенным) длиной поля превышает 64, результаты будут неопределенными. Нулевое значение для длины поля интерпретируется как 64. Если длина поля и индекс бита равны нулю, биты 63:0 *source2* вставляются в *Source1*. Если длина поля равна нулю, а битовый индекс не равен нулю, результаты не будут определены.

В вызове _mm_insert_si64 длина поля содержится в битах 77:72 source2 и индексе в битах 69:64.

При вызове `_mm_inserti_si64` с аргументами, которые компилятор не может определить как целые константы, компилятор создает код для упаковки этих значений в регистр XMM и для вызова `_mm_insert_si64`.

Чтобы определить аппаратную поддержку для `insertq` инструкции, `__cpuid` вызовите встроенную `InfoType=0x80000001` функцию с параметром и `CPUInfo[2] (ECX)`установите бит 6 из. Этот бит равен 1, если инструкция поддерживается, и 0 в противном случае. Если запустить код, использующий встроенное на оборудовании, которое `insertq` не поддерживает эту инструкцию, результаты будут непредсказуемыми.

## <a name="example"></a>Пример

```cpp
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

union {
    __m128i m;
    unsigned __int64 ui64[2];
} source1, source2, source3, result1, result2, result3;

int
main()
{

    __int64 mask;

    source1.ui64[0] = 0xffffffffffffffffll;
    source2.ui64[0] = 0xfedcba9876543210ll;
    source2.ui64[1] = 0xc10;
    source3.ui64[0] = source2.ui64[0];

    result1.m = _mm_insert_si64 (source1.m, source2.m);
    result2.m = _mm_inserti_si64(source1.m, source3.m, 16, 12);
    mask = 0xffff << 12;
    mask = ~mask;
    result3.ui64[0] = (source1.ui64[0] & mask) |
                      ((source2.ui64[0] & 0xffff) << 12);

    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;
    cout << "result2 = 0x" << result2.ui64[0] << endl;
    cout << "result3 = 0x" << result3.ui64[0] << endl;

}
```

```Output
result1 = 0xfffffffff3210fff
result2 = 0xfffffffff3210fff
result3 = 0xfffffffff3210fff
```

**Завершение блока, относящегося только к системам Майкрософт**

Для частей авторские права на 2007 по расширенным микроустройствам, Inc. Все права защищены. Воспроизводить с разрешением от расширенных микроустройств, Inc.

## <a name="see-also"></a>См. также

[_mm_extract_si64, _mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)\
[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
