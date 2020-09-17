---
title: _InterlockedAddLargeStatistic
ms.date: 09/02/2019
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
ms.openlocfilehash: de8c5b7dfd2462dddcb98324ebacc44c8148d85e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222087"
---
# <a name="_interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic

**Блок, относящийся только к системам Microsoft**

Выполняет сложение с блокировкой, в котором первый операнд является 64-битным значением.

## <a name="syntax"></a>Синтаксис

```C
long _InterlockedAddLargeStatistic(
   __int64 volatile * Addend,
   long Value
);
```

### <a name="parameters"></a>Параметры

*Слагаемое*\
[вход, выход] Указатель на первый операнд операции добавления. Значение, на которое указывает, заменяется результатом сложения.

*Значений*\
окне Второй операнд; значение, добавляемое к первому операнду.

## <a name="return-value"></a>Возвращаемое значение

Значение второго операнда.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_InterlockedAddLargeStatistic`|x86|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

`_InterlockedAddLargeStatistic` Встроенная функция не является атомарной, поскольку реализуется как две отдельные инструкции блокировки. Атомарный 64-разрядный Read, происходящий в другом потоке во время выполнения встроенного параметра, может привести к считыванию несогласованного значения.

`_InterlockedAddLargeStatistic`ведет себя как барьер для чтения и записи. Дополнительные сведения см. в разделе [_ReadWriteBarrier](../intrinsics/readwritebarrier.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[Конфликты с 32-разрядным (x86) компилятором](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
