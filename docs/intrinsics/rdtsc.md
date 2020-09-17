---
title: __rdtsc
ms.date: 09/02/2019
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 837b68ca6ac63587cd43a7e8828777221c677e3c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217146"
---
# <a name="__rdtsc"></a>__rdtsc

**Блок, относящийся только к системам Microsoft**

`rdtsc` Формирует инструкцию, которая возвращает метку времени процессора. В метке времени процессора записывается число циклов часов с момента последнего сброса.

## <a name="syntax"></a>Синтаксис

```C
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>Возвращаемое значение

64-битовое целое число без знака, представляющее число тактов.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__rdtsc`|x86, x64|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

Эта подпрограммы доступна только в качестве встроенной функции.

Интерпретация значения TSC в последующих поколениях оборудования отличается от интерпретации в более ранних версиях x64. Дополнительные сведения см. в руководстве по оборудованию.

## <a name="example"></a>Пример

```cpp
// rdtsc.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__rdtsc)

int main()
{
    unsigned __int64 i;
    i = __rdtsc();
    printf_s("%I64d ticks\n", i);
}
```

```Output
3363423610155519 ticks
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
