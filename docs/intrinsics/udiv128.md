---
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: 5e8cc9ca3dbf19a04d07edb1d73df84f2e29a5c3
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857987"
---
# <a name="_udiv128"></a>_udiv128

`_udiv128` функция делит 128-разрядное целое число без знака на 64-разрядное целое число без знака. Возвращаемое значение содержит частное, а внутренний возвращает остаток через параметр указателя. `_udiv128` зависит **от корпорации Майкрософт**.

## <a name="syntax"></a>Синтаксис

```C
unsigned __int64 _udiv128(
   unsigned __int64 highDividend,
   unsigned __int64 lowDividend,
   unsigned __int64 divisor,
   unsigned __int64 *remainder
);
```

### <a name="parameters"></a>Параметры

*хигхдивиденд* \
окне Старшие 64 бит делимого.

*ловдивиденд* \
окне Младший 64 бит делимого.

*делитель* \
окне 64-разрядное целое число для деления на.

*остаток* \
заполняет 64-разрядный целочисленный бит остатка.

## <a name="return-value"></a>Возвращаемое значение

64 бит частного.

## <a name="remarks"></a>Заметки

Передайте верхние 64 бит 128-разрядного делимого на *хигхдивиденд*, а младшие биты 64 — в *ловдивиденд*. Внутренняя функция делит это значение на *делитель*. Он сохраняет остаток в 64-битовом целом число без знака, на который указывает *остаток*, и возвращает биты числа 64.

Встроенная функция `_udiv128` доступна начиная с Visual Studio 2019 RTM.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`_udiv128`|x64|\<использованием immintrin.h >|

## <a name="see-also"></a>См. также:

[_div128](div128.md) \
[Встроенные функции компилятора](compiler-intrinsics.md)
