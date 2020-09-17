---
title: __shiftright128
ms.date: 09/02/2019
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: a18a9958a51f291e4997c23e87ee48f739562416
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220013"
---
# <a name="__shiftright128"></a>__shiftright128

**Блок, относящийся только к системам Microsoft**

Сдвигает 128-разрядную величину, представленную в виде двух 64-разрядныхвеличин `HighPart``LowPart`и , `Shift` вправо на количество разрядов, указанное в  и возвращает младшие 64 разряда результата.

## <a name="syntax"></a>Синтаксис

```C
unsigned __int64 __shiftright128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

### <a name="parameters"></a>Параметры

*ловпарт*\
окне Младший 64 бит 128-разрядного количества для сдвига.

*хигхпарт*\
окне Старшие 64 бит 128-разрядного количества для сдвига.

*Мести*\
окне Число битов для сдвига.

## <a name="return-value"></a>Возвращаемое значение

Младшие 64 разряда результата.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__shiftright128`|X64|

**Заголовочный файл** \<> Intrin.h

## <a name="remarks"></a>Примечания

Это значение `Shift` всегда берется по модулю 64, и, например, при вызове `__shiftright128(0, 1, 64)`, функция будет сдвигать вправо старшую часть `0` разрядов и возвращать младшую часть `0`, а не `1`, как в противном случае можно было ожидать.

## <a name="example"></a>Пример

Пример см. в разделе [__shiftleft128](../intrinsics/shiftleft128.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__shiftleft128](../intrinsics/shiftleft128.md)\
[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
