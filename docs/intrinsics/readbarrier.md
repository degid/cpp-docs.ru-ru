---
title: _ReadBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadBarrier
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
ms.openlocfilehash: 8bbcecf95daeef6ea2d40877d37e0eb6b7f3a0e8
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217098"
---
# <a name="_readbarrier"></a>_ReadBarrier

**Блок, относящийся только к системам Microsoft**

Ограничивает оптимизации компилятора, которые могут изменить порядок операций доступа к памяти для точки вызова.

> [!CAUTION]
> Встроенные функции компилятора `_ReadBarrier`, `_WriteBarrier` и `_ReadWriteBarrier`, а также макрос `MemoryBarrier` являются нерекомендуемыми, и использовать их не следует. Для обмена данными между потоками используйте такие механизмы, как [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) и [std::\<Atomic T >](../standard-library/atomic.md) , определенные в [ C++ стандартной библиотеке](../standard-library/cpp-standard-library-reference.md). Для доступа к оборудованию используйте параметр компилятора [/volatile: ISO](../build/reference/volatile-volatile-keyword-interpretation.md) вместе с ключевым словом [volatile](../cpp/volatile-cpp.md) .

## <a name="syntax"></a>Синтаксис

```C
void _ReadBarrier(void);
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_ReadBarrier`|x86, x64|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

Встроенная функция `_ReadBarrier` ограничивает оптимизации компилятора, которые могут удалять или изменять порядок операций доступа к памяти для точки вызова.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[Ключевые слова](../cpp/keywords-cpp.md)
