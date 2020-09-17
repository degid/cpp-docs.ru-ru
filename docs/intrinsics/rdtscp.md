---
title: __rdtscp
ms.date: 09/02/2019
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: 4dcabd6ed0f7fb3f422927815cbdc91f2b4b9d43
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221322"
---
# <a name="__rdtscp"></a>__rdtscp

**Блок, относящийся только к системам Microsoft**

Формирует инструкцию, выполняет `TSC_AUX[31:0`запись] в память и возвращает счетчик 64-битной метки времени (`TSC)` результат. `rdtscp`

## <a name="syntax"></a>Синтаксис

```C
unsigned __int64 __rdtscp(
   unsigned int * AUX
);
```

### <a name="parameters"></a>Параметры

*ДОПОЛНИТЕЛЬНЫЙ*\
заполняет Указатель на расположение, которое будет содержать содержимое регистра `TSC_AUX[31:0]`, зависящего от компьютера.

## <a name="return-value"></a>Возвращаемое значение

Число тактов 64-битового целого числа без знака.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__rdtscp`|x86, x64|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

`__rdtscp` Внутренняя функция создаетинструкцию`rdtscp` . Чтобы определить аппаратную поддержку для этой инструкции, вызовите `__cpuid` встроенную функцию с `InfoType=0x80000001` и проверьте `CPUInfo[3] (EDX)`бит 27 из. Этот бит равен 1, если инструкция поддерживается, и 0 в противном случае.  Если запустить код, использующий встроенное на оборудовании, которое `rdtscp` не поддерживает эту инструкцию, результаты будут непредсказуемыми.

Эта инструкция ожидает, пока все предыдущие инструкции не будут выполнены и все предыдущие выявляются глобально видимыми. Однако это не инструкция сериализации. Дополнительные сведения см. в руководствах по Intel и AMD.

Значение в `TSC_AUX[31:0]` зависит от операционной системы.

## <a name="example"></a>Пример

```cpp
#include <intrin.h>
#include <stdio.h>
int main()
{
    unsigned __int64 i;
    unsigned int ui;
    i = __rdtscp(&ui);
    printf_s("%I64d ticks\n", i);
    printf_s("TSC_AUX was %x\n", ui);
}
```

```Output
3363423610155519 ticks
TSC_AUX was 0
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__rdtsc](../intrinsics/rdtsc.md)\
[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
