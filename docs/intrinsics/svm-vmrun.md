---
title: __svm_vmrun
ms.date: 09/02/2019
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: f23df894cc8ad1c270c4c0acbc97cab727e47d93
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219819"
---
# <a name="__svm_vmrun"></a>__svm_vmrun

**Блок, относящийся только к системам Microsoft**

Запускает выполнение гостевого кода виртуальной машины, соответствующего указанному блоку управления виртуальной машиной (ВМКБ).

## <a name="syntax"></a>Синтаксис

```C
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>Параметры

*вмкбфисикаладдресс*\
окне Физический адрес ВМКБ.

## <a name="remarks"></a>Примечания

`__svm_vmrun` Функция использует минимальный объем информации в вмкб, чтобы начать выполнять гостевой код виртуальной машины. Используйте функцию [__svm_vmsave](../intrinsics/svm-vmsave.md) или [__svm_vmload](../intrinsics/svm-vmload.md) , если требуются дополнительные сведения для обработки сложного прерывания или переключения на другой гость.

Функция `__svm_vmrun` эквивалентна инструкции компьютера `VMRUN` . Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе "Ручная задача программиста архитектуры AMD64", том 2: Системное программирование, «номер документа 24593, редакция 3,11 или более поздней версии, на сайте [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__svm_vmrun`|x86, x64|

**Заголовочный файл** \<> Intrin.h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
