---
title: __svm_invlpga
ms.date: 09/02/2019
f1_keywords:
- __svm_invlpga
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
ms.openlocfilehash: e0f8ef02efdb64f70bb65f6f017449fcc03beca1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219885"
---
# <a name="__svm_invlpga"></a>__svm_invlpga

**Блок, относящийся только к системам Microsoft**

Делает недействительным запись сопоставления адресов в буфере переноса компьютера. Параметры укажите виртуальный адрес и идентификатор пространства адресов страницы, которые необходимо сделать недействительными.

## <a name="syntax"></a>Синтаксис

```C
void __svm_invlpga(void *Vaddr, int as_id);
```

### <a name="parameters"></a>Параметры

*ваддр*\
окне Виртуальный адрес страницы, которую необходимо сделать недействительной.

*as_id*\
окне Идентификатор адресного пространства (асид) страницы, которую необходимо сделать недействительной.

## <a name="remarks"></a>Примечания

Функция `__svm_invlpga` эквивалентна инструкции компьютера `INVLPGA` . Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе "Ручная задача программиста архитектуры AMD64", том 2: Системное программирование, «номер документа 24593, версия 3,11, на сайте [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__svm_invlpga`|x86, x64|

**Заголовочный файл** \<> Intrin.h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
