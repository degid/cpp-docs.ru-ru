---
title: __sidt
ms.date: 09/02/2019
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: d6b685da0e02373307a3149c5b7b28213f37ad40
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222322"
---
# <a name="__sidt"></a>__sidt

**Блок, относящийся только к системам Microsoft**

Сохраняет значение регистра таблицы дескрипторов прерываний (ИДТР) в указанном расположении в памяти.

## <a name="syntax"></a>Синтаксис

```C
void __sidt(void * Destination);
```

### <a name="parameters"></a>Параметры

*Местоназначение*\
окне Указатель на место в памяти, где хранится ИДТР.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__sidt`|x86, x64|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

Функция `__sidt` эквивалентна инструкции компьютера `SIDT` . Дополнительные сведения см. в документе "Руководство разработчика по архитектуры Intel, том 2: Справочник по набору инструкций "на сайте корпорации [Intel](https://software.intel.com/articles/intel-sdm) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__lidt](../intrinsics/lidt.md)
