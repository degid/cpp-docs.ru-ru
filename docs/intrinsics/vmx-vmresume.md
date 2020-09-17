---
title: __vmx_vmresume
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmresume
helpviewer_keywords:
- __vmx_vmresume intrinsic
- VMRESUME instruction
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
ms.openlocfilehash: 34d0e6814dd00da07076e644513400bd5be36bd3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219451"
---
# <a name="__vmx_vmresume"></a>__vmx_vmresume

**Блок, относящийся только к системам Microsoft**

Возобновляет некорневую операцию VMX, используя текущую структуру управления виртуальной машины (VMCS).

## <a name="syntax"></a>Синтаксис

```C
unsigned char __vmx_vmresume(
   void);
```

## <a name="return-value"></a>Возвращаемое значение

|Значение|Смысл|
|-----------|-------------|
|0|Операция успешно выполнена.|
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|
|2|Сбой операции без сведений о состоянии.|

## <a name="remarks"></a>Примечания

Приложение может выполнять операцию VM-enter, используя функцию [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) или `__vmx_vmresume` . Функцию `__vmx_vmlaunch` можно использовать только с VMCS, состояние запуска которой — `Clear`, а функцию `__vmx_vmresume` можно использовать только с VMCS, состояние запуска которой — `Launched`. Следовательно, используйте функцию [__vmx_vmclear](../intrinsics/vmx-vmclear.md) для задания состояния запуска VMCS `Clear`, а затем используйте функцию `__vmx_vmlaunch` для первой операции VM-enter и функцию `__vmx_vmresume` для последующих операций VM-enter.

Функция `__vmx_vmresume` эквивалентна инструкции компьютера `VMRESUME` . Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в PDF-документе Intel Virtualization Technical Specification for the IA-32 Intel Architecture (Техническая спецификация виртуализации Intel для архитектуры Intel IA-32); номер документа C97063-002, на сайте [корпорации Intel](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__vmx_vmresume`|X64|

**Заголовочный файл** \<> Intrin.h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
