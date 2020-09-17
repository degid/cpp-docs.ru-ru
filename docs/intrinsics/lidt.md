---
title: __lidt
ms.date: 09/02/2019
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 87a49643e7cd11ae57dc01130f250895cf012065
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562497"
---
# <a name="__lidt"></a>__lidt

**Блок, относящийся только к системам Microsoft**

Загружает регистр таблицы дескрипторов прерываний (ИДТР) со значением в указанном расположении в памяти.

## <a name="syntax"></a>Синтаксис

```C
void __lidt(void * Source);
```

### <a name="parameters"></a>Параметры

*Источника*\
окне Указатель на значение, которое должно быть скопировано в ИДТР.

## <a name="requirements"></a>Требования

|Intrinsic|Architecture|
|---------------|------------------|
|`__lidt`|x86, x64|

**Файл заголовка** \<intrin.h>

## <a name="remarks"></a>Примечания

`__lidt`Функция эквивалентна `LIDT` инструкции компьютера и доступна только в режиме ядра. Дополнительные сведения см. в документе "Руководство разработчика по архитектуры Intel, том 2. Справочник по набору инструкций" на сайте корпорации [Intel](https://software.intel.com/articles/intel-sdm) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__sidt](../intrinsics/sidt.md)
