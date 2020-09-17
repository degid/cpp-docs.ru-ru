---
title: __writedr
ms.date: 09/02/2019
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: 473e7223e9974d0125e772c152ea85ae90b97342
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858065"
---
# <a name="__writedr"></a>__writedr

**Блок, относящийся только к системам Майкрософт**

Записывает указанное значение в указанный регистр отладки.

## <a name="syntax"></a>Синтаксис

```C
void __writedr(unsigned DebugRegister, unsigned DebugValue); /* x86 */
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue); /* x64 */
```

### <a name="parameters"></a>Параметры

*Дебугрегистер*\
окне Число от 0 до 7, идентифицирующее регистр отладки.

*Дебугвалуе*\
окне Значение, записываемое в регистр отладки.

## <a name="remarks"></a>Заметки

Эти встроенные функции доступны только в режиме ядра, а подпрограммы доступны только в виде встроенных функций.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__writedr`|x86, x64|

**Файл заголовка** \<Intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__readdr](../intrinsics/readdr.md)
