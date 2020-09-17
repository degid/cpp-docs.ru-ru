---
title: __debugbreak
ms.date: 09/02/2019
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: e4cf2c85818a878417c560ddb5a80f8690e60a93
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217920"
---
# <a name="__debugbreak"></a>__debugbreak

**Блок, относящийся только к системам Microsoft**

Вызывает точку останова в коде, где пользователю будет предложено запустить отладчик.

## <a name="syntax"></a>Синтаксис

```C
void __debugbreak();
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`__debugbreak`|x86, x64, ARM, ARM64|\<> Intrin.h|

## <a name="remarks"></a>Примечания

Внутренняя функция компилятора`__debugbreak`, аналогичная [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak), является переносимым способом Win32, который вызывает точку останова.

> [!NOTE]
> При компиляции с **параметром/CLR**функция, содержащая `__debugbreak` , будет скомпилирована в MSIL. При использовании `asm int 3` функция компилируется в машинный код. Дополнительные сведения см. в разделе [__asm](../assembler/inline/asm.md).

Например:

```C
main() {
   __debugbreak();
}
```

аналогично

```C
main() {
   __asm {
      int 3
   }
}
```

на компьютере с архитектурой x86.

В ARM64 `__debugbreak` встроенная функция компилируется в инструкцию `brk #0xF000`.

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[Ключевые слова](../cpp/keywords-cpp.md)
