---
title: __writeeflags
ms.date: 09/02/2019
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: 6b9b6976369ed810789e5749a2e30029cad4c2d7
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858052"
---
# <a name="__writeeflags"></a>__writeeflags

**Блок, относящийся только к системам Майкрософт**

Записывает указанное значение в Регистр состояния программы и контроль (ЕФЛАГС).

## <a name="syntax"></a>Синтаксис

```C
void __writeeflags(unsigned Value); /* x86 */
void __writeeflags(unsigned __int64 Value); /* x64 */
```

### <a name="parameters"></a>Параметры

*Значение*\
окне Значение, записываемое в ЕФЛАГС регистр. Параметр `Value` имеет длину 32 бит/с для 32-разрядной платформы и 64 разрядов для 64-разрядной платформы.

## <a name="remarks"></a>Заметки

Эти подпрограммы доступны только в виде встроенных функций.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__writeeflags`|x86, x64|

**Файл заголовка** \<Intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
