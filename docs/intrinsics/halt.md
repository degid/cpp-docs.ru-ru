---
title: __halt
ms.date: 09/02/2019
f1_keywords:
- __halt
- __halt_cpp
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
ms.openlocfilehash: 66f5e05e7673523966ef35ac743fc585930b511c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222153"
---
# <a name="__halt"></a>__halt

**Блок, относящийся только к системам Microsoft**

Прерывает работу микропроцессора до включенного прерывания, немаскированного прерывания (NMI) или сброса.

## <a name="syntax"></a>Синтаксис

```C
void __halt( void );
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__halt`|x86, x64|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

Функция эквивалентна инструкции компьютера и доступна только в режиме ядра. `HLT` `__halt` Дополнительные сведения см. в документе "Руководство разработчика по архитектуры Intel, том 2: Справочник по набору инструкций "на сайте корпорации [Intel](https://software.intel.com/articles/intel-sdm) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
