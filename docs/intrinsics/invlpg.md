---
title: __invlpg
ms.date: 09/02/2019
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: ba8bd81498f805992336b0dc4163fe18fa157a2c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221895"
---
# <a name="__invlpg"></a>__invlpg

**Блок, относящийся только к системам Microsoft**

Создает инструкцию `invlpg` x86, которая делает недействительным буфер TLB преобразования для страницы, связанной с памятью, на которую указывает *адрес*.

## <a name="syntax"></a>Синтаксис

```C
void __invlpg(
   void* Address
);
```

### <a name="parameters"></a>Параметры

*Address*\
окне 64-разрядный адрес.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__invlpg`|x86, x64|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

Внутренняя функция `__invlpg` создает привилегированную инструкцию и доступна только в режиме ядра с уровнем привилегий (CPL), равным 0.

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
