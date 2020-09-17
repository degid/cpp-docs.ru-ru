---
title: exp2, exp2f, exp2l
description: Ссылка API для EXP2 (), exp2f () и exp2l (), в которой выдается вычисление 2 для указанного значения.
ms.date: 9/1/2020
api_name:
- exp2
- exp2f
- exp2l
- _o_exp2
- _o_exp2f
- _o_exp2l
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
ms.openlocfilehash: 518525a38ef575583fde3b7732561f2fa553dd18
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556623"
---
# <a name="exp2-exp2f-exp2l"></a>exp2, exp2f, exp2l

Вычисление 2 вызывает указанное значение.

## <a name="syntax"></a>Синтаксис

```C
double exp2(
   double x
);

float exp2(
   float x
);  // C++ only

long double exp2(
   long double x
); // C++ only

float exp2f(
   float x
);

long double exp2l(
   long double x
);
#define exp2(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Значение экспоненты.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха Возвращает экспоненту по основанию 2 *x*, то есть 2<sup>x</sup>. В противном случае возвращается одно из следующих значений:

|Проблема|Возвращает|
|-----------|------------|
|*x* = ± 0|1|
|*x* =-бесконечность|+0|
|*x* = + бесконечность|+INFINITY|
|*x* = NaN|NaN|
|Ошибка переполнения диапазона|+HUGE_VAL, +HUGE_VALF или +HUGE_VALL|
|Ошибка недостаточного заполнения диапазона|Правильный результат, после округления|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **EXP2** , которые принимают и возвращают **`float`** **`long double`** типы и. В программе на языке C, если вы не используете \<tgmath.h> макрос для вызова этой функции, **EXP2** всегда принимает и возвращает **`double`** , если только макрос в <tgmath.h не используется>.

При использовании \<tgmath.h> `exp2()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**EXP2**, **expf2**, **expl2**|\<math.h>|\<cmath>|
|макрос **EXP2** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
