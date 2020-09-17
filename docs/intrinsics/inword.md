---
title: __inword
ms.date: 09/02/2019
f1_keywords:
- __inword_cpp
- __inword
helpviewer_keywords:
- in instruction
- __inword intrinsic
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
ms.openlocfilehash: 7daaf1abd5089716061f118e30e9534e5c5c18ee
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440975"
---
# <a name="__inword"></a>__inword

**Блок, относящийся только к системам Microsoft**

Считывает данные из указанного порта с помощью инструкции `in`.

## <a name="syntax"></a>Синтаксис

```C
unsigned short __inword(
   unsigned short Port
);
```

### <a name="parameters"></a>Параметры

\ *порта*
окне Порт, из которого производится чтение.

## <a name="return-value"></a>Возвращаемое значение

Слово прочитанных данных.

## <a name="requirements"></a>Требования

|Intrinsic|Architecture|
|---------------|------------------|
|`__inword`|x86, x64|

**Файл заголовка** \<Intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
