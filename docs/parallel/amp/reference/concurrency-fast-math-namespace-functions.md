---
title: Функции пространства имен Concurrency::fast_math
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::fast_math::acos
- amp_math/Concurrency::fast_math::asin
- amp_math/Concurrency::fast_math::asinf
- amp_math/Concurrency::fast_math::atan2
- amp_math/Concurrency::fast_math::atan2f
- amp_math/Concurrency::fast_math::ceil
- amp_math/Concurrency::fast_math::ceilf
- amp_math/Concurrency::fast_math::cosf
- amp_math/Concurrency::fast_math::cosh
- amp_math/Concurrency::fast_math::exp
- amp_math/Concurrency::fast_math::exp2
- amp_math/Concurrency::fast_math::expf
- amp_math/Concurrency::fast_math::fabs
- amp_math/Concurrency::fast_math::floor
- amp_math/Concurrency::fast_math::floorf
- amp_math/Concurrency::fast_math::fmaxf
- amp_math/Concurrency::fast_math::fmin
- amp_math/Concurrency::fast_math::fmod
- amp_math/Concurrency::fast_math::fmodf
- amp_math/Concurrency::fast_math::frexpf
- amp_math/Concurrency::fast_math::isfinite
- amp_math/Concurrency::fast_math::isnan
- amp_math/Concurrency::fast_math::ldexp
- amp_math/Concurrency::fast_math::log
- amp_math/Concurrency::fast_math::log10
- amp_math/Concurrency::fast_math::log2
- amp_math/Concurrency::fast_math::log2f
- amp_math/Concurrency::fast_math::modf
- amp_math/Concurrency::fast_math::modff
- amp_math/Concurrency::fast_math::powf
- amp_math/Concurrency::fast_math::round
- amp_math/Concurrency::fast_math::rsqrt
- amp_math/Concurrency::fast_math::rsqrtf
- amp_math/Concurrency::fast_math::signbitf
- amp_math/Concurrency::fast_math::sin
- amp_math/Concurrency::fast_math::sincosf
- amp_math/Concurrency::fast_math::sinf
- amp_math/Concurrency::fast_math::sinhf
- amp_math/Concurrency::fast_math::sqrt
- amp_math/Concurrency::fast_math::tan
- amp_math/Concurrency::fast_math::tanf
- amp_math/Concurrency::fast_math::tanhf
- amp_math/Concurrency::fast_math::trunc
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
ms.openlocfilehash: ff919016449723ad67e029a249ec222ccf1fe6a4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831064"
---
# <a name="concurrencyfast_math-namespace-functions"></a>Функции пространства имен Concurrency::fast_math

:::row:::
   :::column span="":::
      [`acos`](#acos)\
      [`acosf`](#acosf)\
      [`asin`](#asin)\
      [`asinf`](#asinf)\
      [`atan`](#atan)\
      [`atan2`](#atan2)\
      [`atan2f`](#atan2f)\
      [`atanf`](#atanf)\
      [`ceil`](#ceil)\
      [`ceilf`](#ceilf)\
      [`cos`](#cos)\
      [`cosf`](#cosf)\
      [`cosh`](#cosh)\
      [`coshf`](#coshf)\
      [`exp`](#exp)\
      [`exp2`](#exp2)\
      [`exp2f`](#exp2f)
   :::column-end:::
   :::column span="":::
      [`expf`](#expf)\
      [`fabs`](#fabs)\
      [`fabsf`](#fabsf)\
      [`floor`](#floor)\
      [`floorf`](#floorf)\
      [`fmax`](#fmax)\
      [`fmaxf`](#fmaxf)\
      [`fmin`](#fmin)\
      [`fminf`](#fminf)\
      [`fmod`](#fmod)\
      [`fmodf`](#fmodf)\
      [`frexp`](#frexp)\
      [`frexpf`](#frexpf)\
      [`isfinite`](#isfinite)\
      [`isinf`](#isinf)\
      [`isnan`](#isnan)
   :::column-end:::
   :::column span="":::
      [`ldexp`](#ldexp)\
      [`ldexpf`](#ldexpf)\
      [`log`](#log)\
      [`log10`](#log10)\
      [`log10f`](#log10f)\
      [`log2`](#log2)\
      [`log2f`](#log2f)\
      [`logf`](#logf)\
      [`modf`](#modf)\
      [`modff`](#modff)\
      [`pow`](#pow)\
      [`powf`](#powf)\
      [`round`](#round)\
      [`roundf`](#roundf)\
      [`rsqrt`](#rsqrt)\
      [`rsqrtf`](#rsqrtf)
   :::column-end:::
   :::column span="":::
      [`signbit`](#signbit)\
      [`signbitf`](#signbitf)\
      [`sin`](#sin)\
      [`sincos`](#sincos)\
      [`sincosf`](#sincosf)\
      [`sinf`](#sinf)\
      [`sinh`](#sinh)\
      [`sinhf`](#sinhf)\
      [`sqrt`](#sqrt)\
      [`sqrtf`](#sqrtf)\
      [`tan`](#tan)\
      [`tanf`](#tanf)\
      [`tanh`](#tanh)\
      [`tanhf`](#tanhf)\
      [`trunc`](#trunc)\
      [`truncf`](#truncf)
   :::column-end:::
:::row-end:::

## <a name="acos"></a><a name="acos"></a> ACOS

Вычисляет арккосинус аргумента

```cpp
inline float acos(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арккосинус аргумента

## <a name="acosf"></a><a name="acosf"></a> acosf

Вычисляет арккосинус аргумента

```cpp
inline float acosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арккосинус аргумента

## <a name="asin"></a><a name="asin"></a> ASIN

Вычисляет арксинус аргумента

```cpp
inline float asin(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арксинус аргумента

## <a name="asinf"></a><a name="asinf"></a> асинф

Вычисляет арксинус аргумента

```cpp
inline float asinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арксинус аргумента

## <a name="atan"></a><a name="atan"></a> Atan

Вычисляет арктангенс аргумента.

```cpp
inline float atan(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арктангенс аргумента

## <a name="atan2"></a><a name="atan2"></a> atan2

Вычисляет арктангенс _Y/_X

```cpp
inline float atan2(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Y*<br/>
Значение с плавающей запятой

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арктангенс _Y/_X

## <a name="atan2f"></a><a name="atan2f"></a> atan2f

Вычисляет арктангенс _Y/_X

```cpp
inline float atan2f(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Y*<br/>
Значение с плавающей запятой

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арктангенс _Y/_X

## <a name="atanf"></a><a name="atanf"></a> атанф

Вычисляет арктангенс аргумента.

```cpp
inline float atanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арктангенс аргумента

## <a name="ceil"></a><a name="ceil"></a> ceil

Вычисляет Ceiling аргумента

```cpp
inline float ceil(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает Ceiling аргумента

## <a name="ceilf"></a><a name="ceilf"></a> ceilf

Вычисляет Ceiling аргумента

```cpp
inline float ceilf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает Ceiling аргумента

## <a name="cosf"></a><a name="cosf"></a> cosf

Вычисляет косинус аргумента.

```cpp
inline float cosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение косинуса аргумента

## <a name="coshf"></a><a name="coshf"></a> кошф

Вычисляет гиперболический косинус значения аргумента

```cpp
inline float coshf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического косинуса аргумента

## <a name="cos"></a><a name="cos"></a> COS

Вычисляет косинус аргумента.

```cpp
inline float cos(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение косинуса аргумента

## <a name="cosh"></a><a name="cosh"></a> cosh

Вычисляет гиперболический косинус значения аргумента

```cpp
inline float cosh(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического косинуса аргумента

## <a name="exp"></a><a name="exp"></a> расширением

Вычисляет экспоненту аргумента по основанию e

```cpp
inline float exp(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает экспоненту по базовому e аргумента

## <a name="exp2"></a><a name="exp2"></a> EXP2

Вычисляет экспоненту аргумента по основанию 2

```cpp
inline float exp2(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает 2 в степени, равной аргументу.

## <a name="exp2f"></a><a name="exp2f"></a> exp2f

Вычисляет экспоненту аргумента по основанию 2

```cpp
inline float exp2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает 2 в степени, равной аргументу.

## <a name="expf"></a><a name="expf"></a> експф

Вычисляет экспоненту аргумента по основанию e

```cpp
inline float expf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает экспоненту по базовому e аргумента

## <a name="fabs"></a><a name="fabs"></a> Fabs

Возвращает абсолютное значение аргумента

```cpp
inline float fabs(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает абсолютное значение аргумента

## <a name="fabsf"></a><a name="fabsf"></a> fabsf

Возвращает абсолютное значение аргумента

```cpp
inline float fabsf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает абсолютное значение аргумента

## <a name="floor"></a><a name="floor"></a> фабрич

Вычисляет этаж аргумента

```cpp
inline float floor(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает этаж аргумента

## <a name="floorf"></a><a name="floorf"></a> флурф

Вычисляет этаж аргумента

```cpp
inline float floorf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает этаж аргумента

## <a name="fmax"></a><a name="fmax"></a> Fmax

Определение максимального числового значения аргументов

```cpp
inline float max(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возврат максимального числового значения аргументов

## <a name="fmaxf"></a><a name="fmaxf"></a> fmaxf

Определение максимального числового значения аргументов

```cpp
inline float fmaxf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возврат максимального числового значения аргументов

## <a name="fmin"></a><a name="fmin"></a> фмин

Определение минимального числового значения аргументов

```cpp
inline float min(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возврат минимального числового значения аргументов

## <a name="fminf"></a><a name="fminf"></a> фминф

Определение минимального числового значения аргументов

```cpp
inline float fminf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возврат минимального числового значения аргументов

## <a name="fmod"></a><a name="fmod"></a> FMOD

Вычисляет остаток числа с плавающей запятой _X/_Y

```cpp
inline float fmod(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает остаток от _X и _Y с плавающей запятой

## <a name="fmodf"></a><a name="fmodf"></a> фмодф

Вычисляет остаток от деления числа _X/_Y с плавающей запятой.

```cpp
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает остаток от _X и _Y с плавающей запятой

## <a name="frexp"></a><a name="frexp"></a> frexp

Возвращает мантисса и показатель степени _X

```cpp
inline float frexp(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Exp*<br/>
Возвращает целочисленную степень числа _X в значении с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает мантисса _X

## <a name="frexpf"></a><a name="frexpf"></a> фрекспф

Возвращает мантисса и показатель степени _X

```cpp
inline float frexpf(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Exp*<br/>
Возвращает целочисленную степень числа _X в значении с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает мантисса _X

## <a name="isfinite"></a><a name="isfinite"></a> isFinite

Определяет, имеет ли аргумент конечное значение

```cpp
inline int isfinite(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение только в том случае, если аргумент имеет конечное значение

## <a name="isinf"></a><a name="isinf"></a> исинф

Определяет, является ли аргумент бесконечной

```cpp
inline int isinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Функция возвращает ненулевое значение только в том случае, если аргумент имеет бесконечное значение

## <a name="isnan"></a><a name="isnan"></a> IsNaN

Определяет, является ли аргумент нечисловым

```cpp
inline int isnan(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение только в том случае, если аргумент имеет значение NaN.

## <a name="ldexp"></a><a name="ldexp"></a> ldexp

Вычисляет вещественное число из мантиссаа и экспоненты

```cpp
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой, ментисса

*_Exp*<br/>
Целочисленная экспонента

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X \* 2 ^ _Exp

## <a name="ldexpf"></a><a name="ldexpf"></a> лдекспф

Вычисляет вещественное число из мантиссаа и экспоненты

```cpp
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой, ментисса

*_Exp*<br/>
Целочисленная экспонента

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X \* 2 ^ _Exp

## <a name="log"></a><a name="log"></a> Журналь

Вычисляет логарифм аргумента по основанию e.

```cpp
inline float log(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает логарифм по базовому e аргумента

## <a name="log10"></a><a name="log10"></a> LOG10

Вычисляет десятичный логарифм аргумента

```cpp
inline float log10(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает десятичный логарифм аргумента

## <a name="log10f"></a><a name="log10f"></a> log10f

Вычисляет десятичный логарифм аргумента

```cpp
inline float log10f(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает десятичный логарифм аргумента

## <a name="log2"></a><a name="log2"></a> log2

Вычисляет логарифм аргумента по основанию 2

```cpp
inline float log2(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает логарифм по основанию 2 аргумента

## <a name="log2f"></a><a name="log2f"></a> log2f

Вычисляет логарифм аргумента по основанию 2

```cpp
inline float log2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает десятичный логарифм аргумента

## <a name="logf"></a><a name="logf"></a> логф

Вычисляет логарифм аргумента по основанию e.

```cpp
inline float logf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает логарифм по базовому e аргумента

## <a name="modf"></a><a name="modf"></a> modf

Разделяет _X на дробные и целые части.

```cpp
inline float modf(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Ip*<br/>
Получает целочисленную часть значения

### <a name="return-value"></a>Возвращаемое значение

Возвращает знак дробной части _X

## <a name="modff"></a><a name="modff"></a> modff

Разделяет _X на дробные и целые части.

```cpp
inline float modff(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Ip*<br/>
Получает целочисленную часть значения

### <a name="return-value"></a>Возвращаемое значение

Возвращает знак дробной части _X

## <a name="pow"></a><a name="pow"></a> Pow

Вычисляет _X, возведенное в степень _Y

```cpp
inline float pow(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой, основание

*_Y*<br/>
Значение с плавающей запятой, экспонента

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение _X, возведенное в степень _Y

## <a name="powf"></a><a name="powf"></a> powf

Вычисляет _X, возведенное в степень _Y

```cpp
inline float powf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой, основание

*_Y*<br/>
Значение с плавающей запятой, экспонента

### <a name="return-value"></a>Возвращаемое значение

## <a name="round"></a><a name="round"></a> округло

Округляет _X до ближайшего целого числа

```cpp
inline float round(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ближайшее целое число _X

## <a name="roundf"></a><a name="roundf"></a> раундф

Округляет _X до ближайшего целого числа

```cpp
inline float roundf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ближайшее целое число _X

## <a name="rsqrt"></a><a name="rsqrt"></a> рскрт

Возвращает обратную величину квадратного корня аргумента

```cpp
inline float rsqrt(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную величину квадратного корня аргумента

## <a name="rsqrtf"></a><a name="rsqrtf"></a> рскртф

Возвращает обратную величину квадратного корня аргумента

```cpp
inline float rsqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную величину квадратного корня аргумента

## <a name="signbit"></a><a name="signbit"></a> сигнбит

Определяет, является ли знак _X отрицательным

```cpp
inline int signbit(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Функция возвращает ненулевое значение только в том случае, если знак _X является отрицательным

## <a name="signbitf"></a><a name="signbitf"></a> сигнбитф

Определяет, является ли знак _X отрицательным

```cpp
inline int signbitf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Функция возвращает ненулевое значение только в том случае, если знак _X является отрицательным

## <a name="sin"></a><a name="sin"></a> Sin

Вычисляет значение синуса для аргумента

```cpp
inline float sin(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение синуса аргумента

## <a name="sinf"></a><a name="sinf"></a> sinf

Вычисляет значение синуса для аргумента

```cpp
inline float sinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение синуса аргумента

## <a name="sincos"></a><a name="sincos"></a> синкос

Вычисляет синус и косинус значения _X

```cpp
inline void sincos(
    float _X,
    float* _S,
    float* _C) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_S*<br/>
Возвращает значение синуса _X

*_C*<br/>
Возвращает значение косинуса _X

## <a name="sincosf"></a><a name="sincosf"></a> синкосф

Вычисляет синус и косинус значения _X

```cpp
inline void sincosf(
    float _X,
    float* _S,
    float* _C) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_S*<br/>
Возвращает значение синуса _X

*_C*<br/>
Возвращает значение косинуса _X

## <a name="sinh"></a><a name="sinh"></a> sinh

Вычисляет гиперболический синус значения аргумента

```cpp
inline float sinh(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического синуса аргумента

## <a name="sinhf"></a><a name="sinhf"></a> sinhf

Вычисляет гиперболический синус значения аргумента

```cpp
inline float sinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического синуса аргумента

## <a name="sqrt"></a><a name="sqrt"></a> МНИМ

Вычисляет корень скуре аргумента

```cpp
inline float sqrt(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает корень скуре аргумента

## <a name="sqrtf"></a><a name="sqrtf"></a> скртф

Вычисляет корень скуре аргумента

```cpp
inline float sqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает корень скуре аргумента

## <a name="tan"></a><a name="tan"></a> тангенс

Вычисляет значение тангенса аргумента

```cpp
inline float tan(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение тангенса аргумента

## <a name="tanf"></a><a name="tanf"></a> TANF

Вычисляет значение тангенса аргумента

```cpp
inline float tanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение тангенса аргумента

## <a name="tanh"></a><a name="tanh"></a> tanh

Вычисляет значение гиперболического тангенса аргумента

```cpp
inline float tanh(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического тангенса аргумента

## <a name="tanhf"></a><a name="tanhf"></a> tanhf

Вычисляет значение гиперболического тангенса аргумента

```cpp
inline float tanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического тангенса аргумента

## <a name="trunc"></a><a name="trunc"></a> TRUNC

Усекает аргумент до целочисленного компонента

```cpp
inline float trunc(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает целочисленный компонент аргумента

## <a name="truncf"></a><a name="truncf"></a> трункф

Усекает аргумент до целочисленного компонента

```cpp
inline float truncf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает целочисленный компонент аргумента

## <a name="requirements"></a>Требования

**Заголовок:** **пространство имен** amp_math.h: Concurrency:: fast_math

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency::fast_math](concurrency-fast-math-namespace.md)
