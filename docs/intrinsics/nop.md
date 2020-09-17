---
title: __nop
ms.date: 09/02/2019
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 4561bcb84063f3707825c8ca164867d41500e2db
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221675"
---
# <a name="__nop"></a>__nop

**Блок, относящийся только к системам Microsoft**

Создает машинный код, зависящий от платформы, который не выполняет никаких операций.

## <a name="syntax"></a>Синтаксис

```C
void __nop();
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__nop`|x86, ARM, x64, ARM64|

**Заголовочный файл** \<> Intrin.h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="remarks"></a>Примечания

Функция `__nop` эквивалентна инструкции компьютера `NOP` . Дополнительные сведения об архитектуре x86 и x64 см. в документе "Руководство разработчика по архитектуры Intel, том 2: Справочник по набору инструкций "на сайте корпорации [Intel](https://software.intel.com/articles/intel-sdm) .

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__noop](../intrinsics/noop.md)
