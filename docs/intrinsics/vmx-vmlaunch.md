---
title: __vmx_vmlaunch
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmlaunch
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
ms.openlocfilehash: 8d78e5181fdd43e10431e12d0cf540c8c9c2e719
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219545"
---
# <a name="__vmx_vmlaunch"></a>__vmx_vmlaunch

**Блок, относящийся только к системам Microsoft**

Помещает вызывающее приложение в VMX состояние операции, не являющейся корневой (ввод ВИРТУАЛЬНОЙ машины), используя текущую структуру управления виртуальными машинами (VMCS).

## <a name="syntax"></a>Синтаксис

```C
unsigned char __vmx_vmlaunch(void);
```

## <a name="return-value"></a>Возвращаемое значение

|Значение|Смысл|
|-----------|-------------|
|0|Операция успешно выполнена.|
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|
|2|Сбой операции без сведений о состоянии.|

## <a name="remarks"></a>Примечания

Приложение может выполнить операцию типа "виртуальная машина — ввод" с помощью функции [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) или [__vmx_vmresume](../intrinsics/vmx-vmresume.md) . Функция [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) может использоваться только с VMCS, состояние запуска которого — `Clear`, а функция [__vmx_vmresume](../intrinsics/vmx-vmresume.md) может использоваться только с VMCS, состояние запуска которого —. `Launched` Следовательно, используйте функцию [__vmx_vmclear](../intrinsics/vmx-vmclear.md) , чтобы установить состояние запуска VMCS в `Clear`, а затем используйте функцию [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) для первой операции ВМ-Enter и функцию [__vmx_vmresume](../intrinsics/vmx-vmresume.md) для последующей виртуальной машины — Enter. Operations.

Функция `__vmx_vmlaunch` эквивалентна инструкции компьютера `VMLAUNCH` . Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе "Техническая спецификация виртуализации Intel для архитектуры IA-32 Intel" номер документа C97063-002 на сайте корпорации [Intel](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__vmx_vmlaunch`|X64|

**Заголовочный файл** \<> Intrin.h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
