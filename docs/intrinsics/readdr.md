---
title: __readdr
ms.date: 09/02/2019
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: fbaf9e761f9f1450ccd12dc378ab6e498aa0df08
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857883"
---
# <a name="__readdr"></a>__readdr

**Блок, относящийся только к системам Майкрософт**

Считывает значение указанного регистра отладки.

## <a name="syntax"></a>Синтаксис

```C
unsigned         __readdr(unsigned int DebugRegister); /* x86 */
unsigned __int64 __readdr(unsigned int DebugRegister); /* x64 */
```

### <a name="parameters"></a>Параметры

*Дебугрегистер*\
окне Константа от 0 до 7, определяющая регистр отладки.

## <a name="return-value"></a>Возвращаемое значение

Значение указанного регистра отладки.

## <a name="remarks"></a>Заметки

Эти встроенные функции доступны только в режиме ядра, а подпрограммы доступны только в виде встроенных функций.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__readdr`|x86, x64|

**Файл заголовка** \<Intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
