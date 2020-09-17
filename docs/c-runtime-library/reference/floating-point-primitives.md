---
title: Примитивы с плавающей запятой
ms.date: 4/2/2020
api_name:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
- _o__d_int
- _o__dclass
- _o__dlog
- _o__dnorm
- _o__dpcomp
- _o__dpoly
- _o__dscale
- _o__dsign
- _o__dsin
- _o__dtest
- _o__dunscale
- _o__fd_int
- _o__fdclass
- _o__fdexp
- _o__fdlog
- _o__fdpcomp
- _o__fdpoly
- _o__fdscale
- _o__fdsign
- _o__fdsin
- _o__ld_int
- _o__ldclass
- _o__ldexp
- _o__ldlog
- _o__ldpcomp
- _o__ldpoly
- _o__ldscale
- _o__ldsign
- _o__ldsin
- _o__ldtest
- _o__ldunscale
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
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
helpviewer_keywords:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
ms.openlocfilehash: e28c873206d8f050dbde2afc9ebfe3540b6642ff
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218691"
---
# <a name="floating-point-primitives"></a>Примитивы с плавающей запятой

Примитивные функции, предназначенные для Майкрософт, которые используются для реализации некоторых стандартных функций с плавающей запятой в библиотеке времени выполнения C (CRT). Они описаны здесь для полноты, но не рекомендуются для использования. Некоторые из этих функций отмечены как неиспользуемые, поскольку известны проблемы с точностью, обработкой исключений и соответствием поведению IEEE-754. Они существуют в библиотеке только для обеспечения обратной совместимости. Для правильного поведения, переносимости и соблюдения стандартов рекомендуется использовать стандартные функции с плавающей запятой для этих функций.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="_dclass-_ldclass-_fdclass"></a>_dclass, _ldclass _fdclass

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dclass(double x);
short __cdecl _ldclass(long double x);
short __cdecl _fdclass(float x);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции с плавающей точкой.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой реализуют версии языка C макроса CRT [fpclassify](fpclassify.md) для типов с плавающей запятой. Классификация аргумента *x* возвращается в виде одной из этих констант, определенных в Math.h:

|Значение|Описание|
|-----------|-----------------|
| **FP_NAN** | Сигнальное, несигнальное или неопределенное значение NaN |
| **FP_INFINITE** | Положительная или отрицательная бесконечность |
| **FP_NORMAL** | Положительное или отрицательное нормализованное ненулевое значение |
| **FP_SUBNORMAL** | Положительное или отрицательное значение поднормали (денормализованная) |
| **FP_ZERO** | Положительное или отрицательное нулевое значение |

Для получения дополнительных сведений можно использовать функции _fpclass, связанные с Майкрософт [, _fpclassf](fpclass-fpclassf.md) . Используйте макрос или функцию [fpclassify](fpclassify.md) для переносимости.

## <a name="_dsign-_ldsign-_fdsign"></a>_dsign, _ldsign _fdsign

### <a name="syntax"></a>Синтаксис

```C
int __cdecl _dsign(double x);
int __cdecl _ldsign(long double x);
int __cdecl _fdsign(float x);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции с плавающей точкой.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой реализуют макрос или функцию [сигнбит](signbit.md) в CRT. Они возвращают ненулевое значение, если бит знака задан в значащим (мантисса) аргумента *x*, и 0, если бит знака не задан.

## <a name="_dpcomp-_ldpcomp-_fdpcomp"></a>_dpcomp, _ldpcomp _fdpcomp

### <a name="syntax"></a>Синтаксис

```C
int __cdecl _dpcomp(double x, double y);
int __cdecl _ldpcomp(long double x, long double y);
int __cdecl _fdpcomp(float x, float y);
```

### <a name="parameters"></a>Параметры

*x*, *y*<br/>
Аргументы функции с плавающей запятой.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой принимают два аргумента: *x* и *y*и возвращают значение, которое показывает их связь упорядочения, выраженную в виде побитовой или для этих констант, определенных в Math.h:

| Значение | Описание |
|------------|-----------------|
| **_FP_LT** | *x* может считаться менее *y* |
| **_FP_EQ** | *x* может считаться равным *y* |
| **_FP_GT** | *x* может считаться больше *y* |

Эти примитивы реализуют макросы [исгреатерекуал, ислессекуал, ислессгреатер и исунордеред](floating-point-ordering.md) в CRT.

## <a name="_dtest-_ldtest-_fdtest"></a>_dtest, _ldtest _fdtest

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dtest(double* px);
short __cdecl _ldtest(long double* px);
short __cdecl _fdtest(float* px);
```

### <a name="parameters"></a>Параметры

*пиксел*<br/>
Указатель на аргумент с плавающей запятой.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой реализуют версии C++ функции CRT [fpclassify](fpclassify.md) для типов с плавающей запятой. Вычисляется аргумент *x* , и классификация возвращается как одна из этих констант, определенная в Math.h:

|Значение|Описание|
|-----------|-----------------|
| **FP_NAN** | Сигнальное, несигнальное или неопределенное значение NaN |
| **FP_INFINITE** | Положительная или отрицательная бесконечность |
| **FP_NORMAL** | Положительное или отрицательное нормализованное ненулевое значение |
| **FP_SUBNORMAL** | Положительное или отрицательное значение поднормали (денормализованная) |
| **FP_ZERO** | Положительное или отрицательное нулевое значение |

Для получения дополнительных сведений можно использовать функции _fpclass, связанные с Майкрософт [, _fpclassf](fpclass-fpclassf.md) . Используйте функцию [fpclassify](fpclassify.md) для переносимости.

## <a name="_d_int-_ld_int-_fd_int"></a>_d_int, _ld_int _fd_int

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _d_int(double* px, short exp);
short __cdecl _ld_int(long double* px, short exp);
short __cdecl _fd_int(float* px, short exp);
```

### <a name="parameters"></a>Параметры

*пиксел*<br/>
Указатель на аргумент с плавающей запятой.

*exp*<br/>
Экспонента в виде целочисленного типа.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой принимают указатель на значение *px* с плавающей запятой *и значение*экспоненты, а также удаляют дробную часть значения с плавающей запятой ниже заданной экспоненты, если это возможно. Возвращаемое значение является результатом **fpclassify** для входного значения в *px* , если оно равно NaN или бесконечности, и для выходного значения в *пикселях* в противном случае.

## <a name="_dscale-_ldscale-_fdscale"></a>_dscale, _ldscale _fdscale

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dscale(double* px, long exp);
short __cdecl _ldscale(long double* px, long exp);
short __cdecl _fdscale(float* px, long exp);
```

### <a name="parameters"></a>Параметры

*пиксел*<br/>
Указатель на аргумент с плавающей запятой.

*exp*<br/>
Экспонента в виде целочисленного типа.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой принимают указатель на значение *px* с плавающей запятой и значение экспоненты *, а также масштабируют значение в* *px* на 2<sup>*exp*</sup>, если это возможно. Возвращаемое значение является результатом **fpclassify** для входного значения в *px* , если оно равно NaN или бесконечности, и для выходного значения в *пикселях* в противном случае. Для переносимости предпочитают использовать функции [ldexp, лдекспф и лдекспл](ldexp.md) .

## <a name="_dunscale-_ldunscale-_fdunscale"></a>_dunscale, _ldunscale _fdunscale

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dunscale(short* pexp, double* px);
short __cdecl _ldunscale(short* pexp, long double* px);
short __cdecl _fdunscale(short* pexp, float* px);
```

### <a name="parameters"></a>Параметры

*пексп*<br/>
Указатель на экспоненту в виде целочисленного типа.

*пиксел*<br/>
Указатель на аргумент с плавающей запятой.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой разбивают значение с плавающей запятой, на которое указывает *px* , в значащим (мантисса) и экспоненту, если это возможно. Значащим масштабируется таким, что абсолютное значение больше или равно 0,5 и меньше 1,0. Экспонента — это значение *n*, где исходное значение с плавающей запятой равно масштабному значащим времени 2<sup>*n*</sup>. Эта целая экспонента *n* хранится в расположении, на которое указывает *пексп*. Возвращаемое значение является результатом **fpclassify** для входного значения в *px* , если оно равно NaN или бесконечности, и для выходного значения в противном случае. Для переносимости предпочтительнее использовать функции [frexp, фрекспф, фрекспл](frexp.md) .

## <a name="_dexp-_ldexp-_fdexp"></a>_dexp, _ldexp _fdexp

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dexp(double* px, double y, long exp);
short __cdecl _ldexp(long double* px, long double y, long exp);
short __cdecl _fdexp(float* px, float y, long exp);
```

### <a name="parameters"></a>Параметры

*&*<br/>
Аргумент функции с плавающей точкой.

*пиксел*<br/>
Указатель на аргумент с плавающей запятой.

*exp*<br/>
Экспонента в виде целочисленного типа.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой создают значение с плавающей запятой в расположении, которое указывает на число *точек* , равное *y* * 2<sup>*exp*</sup>. Возвращаемое значение является результатом **fpclassify** для входного значения в *y* , если оно равно NaN или бесконечности, и для выходного значения в *пикселях* в противном случае. Для переносимости предпочитают использовать функции [ldexp, лдекспф и лдекспл](ldexp.md) .

## <a name="_dnorm-_fdnorm"></a>_dnorm, _fdnorm

### <a name="syntax"></a>Синтаксис

```C
short __cdecl _dnorm(unsigned short* ps);
short __cdecl _fdnorm(unsigned short* ps);
```

### <a name="parameters"></a>Параметры

*ps*<br/>
Указатель на побитовое представление значения с плавающей запятой, выраженное в виде массива **`unsigned short`** .

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой нормализует дробную часть значения с плавающей запятой неточного типа и настраивают *характеристику*или смещенную степень в соответствии с. Значение передается как побитовое представление типа с плавающей запятой, преобразованного в массив с **`unsigned short`** помощью `_double_val` `_ldouble_val` типа, или `_float_val` Пуннинг Union, объявленного в Math.h. Возвращаемое значение является результатом **fpclassify** для входного значения с плавающей запятой, если оно равно NaN или бесконечности, и для выходного значения в противном случае.

## <a name="_dpoly-_ldpoly-_fdpoly"></a>_dpoly, _ldpoly _fdpoly

### <a name="syntax"></a>Синтаксис

```C
double __cdecl _dpoly(double x, double const* table, int n);
long double __cdecl _ldpoly(long double x, long double const* table, int n);
float __cdecl _fdpoly(float x, _float const* table, int n);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции с плавающей точкой.

*table*<br/>
Указатель на таблицу константных коэффициентов для полинома.

*n*<br/>
Порядок вычисления полинома.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой возвращают вычисление *x* в полиноме порядка *n* , коэффициенты которого представлены соответствующими константными значениями в *таблице*. Например, если *Таблица* \[ 0] = 3,0, *таблица* \[ 1] = 4,0, *Таблица* \[ 2] = 5,0 и *n* = 2, то она представляет собой полином 5.0 x<sup>2</sup> + 4.0 x + 3,0. Если этот полином вычисляется для *x* 2,0, то результатом будет 31,0. Эти функции не используются внутри.

## <a name="_dlog-_dlog-_dlog"></a>_dlog, _dlog _dlog

### <a name="syntax"></a>Синтаксис

```C
double __cdecl _dlog(double x, int base_flag);
long double __cdecl _ldlog(long double x, int base_flag);
float __cdecl _fdlog(float x, int base_flag);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции с плавающей точкой.

*base_flag*<br/>
Флаг, управляющий основанием для использования, 0 для базового *e* и ненулевого для основания 10.

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой возвращают натуральный журнал *x*, LN (*x*) или log<sub>*e*</sub>(*x*), если *base_flag* равен 0. Они возвращают журнал с основанием 10 из *x*или log<sub>10</sub>(*x*), если *base_flag* не равны нулю. Эти функции не используются внутри. Для переносимости предпочтительнее использовать [журналы функций, логф, логл, LOG10, log10f и log10l](log-logf-log10-log10f.md).

## <a name="_dsin-_ldsin-_fdsin"></a>_dsin, _ldsin _fdsin

### <a name="syntax"></a>Синтаксис

```C
double __cdecl _dsin(double x, unsigned int quadrant);
long double __cdecl _ldsin(long double x, unsigned int quadrant);
float __cdecl _fdsin(float x, unsigned int quadrant);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент функции с плавающей точкой.

*квадрат*<br/>
Смещение квадранта, равное 0, 1, 2 или 3, чтобы использовать для создания `sin` `cos` результатов,, `-sin` и `-cos` .

### <a name="remarks"></a>Примечания

Эти примитивы с плавающей запятой возвращают синус смещения *x* по модулю *квадранта* 4. Фактически они возвращают синус, косинус,-синус и-косинус *x* *, если остаток* от деления 4 равен 0, 1, 2 или 3 соответственно. Эти функции не используются внутри. Для переносимости предпочтительнее использовать функции [sin, sinf, sinl](sin-sinf-sinl.md), [COS, cosf и косл](cos-cosf-cosl.md) .

## <a name="requirements"></a>Требования

Заголовок: \<math.h>

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[frexp, frexpf, frexpl](frexp.md)<br/>
[ldexp, лдекспф и лдекспл](ldexp.md)<br/>
[log, logf, logl, log10, log10f, log10l](log-logf-log10-log10f.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
