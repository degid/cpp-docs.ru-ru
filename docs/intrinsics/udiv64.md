---
title: _udiv64
ms.date: 09/02/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: ddb46f33b0fccc1cedc2a704265b096ba715b506
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858000"
---
# <a name="_udiv64"></a>_udiv64

`_udiv64` функция делит 64-разрядное целое число без знака на 32-разрядное целое число без знака. Возвращаемое значение содержит частное, а внутренний возвращает остаток через параметр указателя. `_udiv64` зависит **от корпорации Майкрософт**.

## <a name="syntax"></a>Синтаксис

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>Параметры

*делимое*\
окне 64-битовое целое число без знака для деления.

*делитель*\
окне 32-битовое целое число без знака для деления на.

*остаток*\
заполняет Остаток от 32-разрядного целого числа без знака.

## <a name="return-value"></a>Возвращаемое значение

32 бит частного.

## <a name="remarks"></a>Заметки

`_udiv64` внутренние деления, *делимые* на *делитель*. Он сохраняет остаток в 32-битовом целом число без знака, на который указывает *остаток*, и возвращает биты числа 32.

Встроенная функция `_udiv64` доступна начиная с Visual Studio 2019 RTM.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`_udiv64`|x86, x64|\<использованием immintrin.h >|

## <a name="see-also"></a>См. также:

[_div64](div64.md) \
[Встроенные функции компилятора](compiler-intrinsics.md)
