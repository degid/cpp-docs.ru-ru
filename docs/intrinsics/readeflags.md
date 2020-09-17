---
title: __readeflags
ms.date: 09/02/2019
f1_keywords:
- __readeflags
helpviewer_keywords:
- __readeflags intrinsic
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
ms.openlocfilehash: 6afdc0f20a3ae72865a80ba2eb7f896f79f63171
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857909"
---
# <a name="__readeflags"></a>__readeflags

**Блок, относящийся только к системам Майкрософт**

Считывает Регистр состояния программы и управления (ЕФЛАГС).

## <a name="syntax"></a>Синтаксис

```C
unsigned     int __readeflags(void); /* x86 */
unsigned __int64 __readeflags(void); /* x64 */
```

## <a name="return-value"></a>Возвращаемое значение

Значение регистра ЕФЛАГС. Возвращаемое значение — 32 бит на 32-разрядной платформе и 64 бит на 64-разрядной платформе.

## <a name="remarks"></a>Заметки

Эти подпрограммы доступны только в виде встроенных функций.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__readeflags`|x86, x64|

**Файл заголовка** \<Intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__writeeflags](../intrinsics/writeeflags.md)
