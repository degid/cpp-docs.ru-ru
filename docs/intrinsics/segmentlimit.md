---
title: __segmentlimit
ms.date: 09/02/2019
f1_keywords:
- __segmentlimit
helpviewer_keywords:
- __segmentlimit intrinsic
- lsl instruction
ms.assetid: d0bc3630-90cb-4185-8667-686fd41e23d4
ms.openlocfilehash: 9239d8de8ce2065d09ee7975301a2cb41832ba89
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217996"
---
# <a name="__segmentlimit"></a>__segmentlimit

**Блок, относящийся только к системам Microsoft**

Создает инструкцию `lsl` (ограничение загрузки сегментов).

## <a name="syntax"></a>Синтаксис

```C
unsigned long __segmentlimit(
   unsigned long a
);
```

### <a name="parameters"></a>Параметры

*конкретного*\
окне Константа, указывающая селектор сегмента.

## <a name="return-value"></a>Возвращаемое значение

Ограничение сегмента для селектора сегмента, заданноепараметром, если селектор является допустимым и видимым на текущем уровне разрешений.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__segmentlimit`|x86, x64|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

Если ограничение сегмента не может быть получено, эта инструкция завершается ошибкой. При сбое эта инструкция очищает флаг ЗФ, и возвращаемое значение не определено.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```cpp
#include <stdio.h>

#ifdef _M_IX86
typedef unsigned int READETYPE;
#else
typedef unsigned __int64 READETYPE;
#endif

#define EFLAGS_ZF      0x00000040
#define KGDT_R3_DATA    0x0020
#define RPL_MASK        0x3

extern "C"
{
unsigned long __segmentlimit (unsigned long);
READETYPE __readeflags();
}

#pragma intrinsic(__readeflags)
#pragma intrinsic(__segmentlimit)

int main(void)
{
   const unsigned long initsl = 0xbaadbabe;
   READETYPE eflags = 0;
   unsigned long sl = initsl;

   printf("Before: segment limit =0x%x eflags =0x%x\n", sl, eflags);
   sl = __segmentlimit(KGDT_R3_DATA + RPL_MASK);

   eflags = __readeflags();

   printf("After: segment limit =0x%x eflags =0x%x eflags.zf = %s\n", sl, eflags, (eflags & EFLAGS_ZF) ? "set" : "clear");

   // If ZF is set, the call to lsl succeeded; if ZF is clear, the call failed.
   printf("%s\n", eflags & EFLAGS_ZF ? "Success!": "Fail!");

   // You can verify the value of sl to make sure that the instruction wrote to it
   printf("sl was %s\n", (sl == initsl) ? "unchanged" : "changed");

   return 0;
}
```

```Output
Before: segment limit =0xbaadbabe eflags =0x0
After: segment limit =0xffffffff eflags =0x256 eflags.zf = set
Success!
sl was changed
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
