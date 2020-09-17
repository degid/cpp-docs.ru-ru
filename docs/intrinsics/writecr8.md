---
title: __writecr8
ms.date: 09/02/2019
f1_keywords:
- _writecr8
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
ms.openlocfilehash: c8df13c15b5cd8a51b77d65ad930a1852809ee30
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219234"
---
# <a name="__writecr8"></a>__writecr8

**Блок, относящийся только к системам Microsoft**

Записывает значение `Data` в регистр CR8.

## <a name="syntax"></a>Синтаксис

```C
void writecr8(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>Параметры

*Data*\
окне Значение, записываемое в CR8 регистр.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__writecr8`|X64|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

`__writecr8` Встроенная функция доступна только в режиме ядра, и подпрограммы доступны только в качестве встроенных.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
