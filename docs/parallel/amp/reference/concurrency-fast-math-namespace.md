---
title: Пространство имен Concurrency::fast_math
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::fast_math
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
ms.openlocfilehash: 6ed8dcfa2faff49e8811769b76aad9df15b2fe7b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226754"
---
# <a name="concurrencyfast_math-namespace"></a>Пространство имен Concurrency::fast_math

Функции в `fast_math` пространстве имен имеют меньшую точность, поддерживают только одну точность ( **`float`** ) и вызывают встроенные компоненты DirectX. Существует две версии каждой функции, например `cos` и `cosf` . Обе версии принимают и возвращают **`float`** , но каждый вызывает одну и ту же встроенную функцию DirectX.

## <a name="syntax"></a>Синтаксис

```cpp
namespace fast_math;
```

## <a name="members"></a>Участники

### <a name="functions"></a>Функции

|Имя|Описание|
|----------|-----------------|
|[COS](concurrency-fast-math-namespace-functions.md#cos)|Вычисляет арккосинус аргумента|
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Вычисляет арккосинус аргумента|
|[ASIN](concurrency-fast-math-namespace-functions.md#asin)|Вычисляет арксинус аргумента|
|[asinf](concurrency-fast-math-namespace-functions.md#asinf)|Вычисляет арксинус аргумента|
|[Atan](concurrency-fast-math-namespace-functions.md#atan)|Вычисляет арктангенс аргумента.|
|[atan2](concurrency-fast-math-namespace-functions.md#atan2)|Вычисляет арктангенс _Y/_X|
|[atan2f](concurrency-fast-math-namespace-functions.md#atan2f)|Вычисляет арктангенс _Y/_X|
|[atanf](concurrency-fast-math-namespace-functions.md#atanf)|Вычисляет арктангенс аргумента.|
|[ceil](concurrency-fast-math-namespace-functions.md#ceil)|Вычисляет Ceiling аргумента|
|[ceilf](concurrency-fast-math-namespace-functions.md#ceilf)|Вычисляет Ceiling аргумента|
|[COS](concurrency-fast-math-namespace-functions.md#cos)|Вычисляет косинус аргумента.|
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Вычисляет косинус аргумента.|
|[cosh](concurrency-fast-math-namespace-functions.md#cosh)|Вычисляет гиперболический косинус значения аргумента|
|[coshf](concurrency-fast-math-namespace-functions.md#coshf)|Вычисляет гиперболический косинус значения аргумента|
|[exp](concurrency-fast-math-namespace-functions.md#exp)|Вычисляет экспоненту аргумента по основанию e|
|[EXP2](concurrency-fast-math-namespace-functions.md#exp2)|Вычисляет экспоненту аргумента по основанию 2|
|[exp2f](concurrency-fast-math-namespace-functions.md#exp2f)|Вычисляет экспоненту аргумента по основанию 2|
|[expf](concurrency-fast-math-namespace-functions.md#expf)|Вычисляет экспоненту аргумента по основанию e|
|[fabs](concurrency-fast-math-namespace-functions.md#fabs)|Возвращает абсолютное значение аргумента|
|[fabsf](concurrency-fast-math-namespace-functions.md#fabsf)|Возвращает абсолютное значение аргумента|
|[фабрич](concurrency-fast-math-namespace-functions.md#floor)|Вычисляет этаж аргумента|
|[floorf](concurrency-fast-math-namespace-functions.md#floorf)|Вычисляет этаж аргумента|
|[fmax](concurrency-fast-math-namespace-functions.md#fmax)|Определение максимального числового значения аргументов|
|[fmaxf](concurrency-fast-math-namespace-functions.md#fmaxf)|Определение максимального числового значения аргументов|
|[fmin](concurrency-fast-math-namespace-functions.md#fmin)|Определение минимального числового значения аргументов|
|[fminf](concurrency-fast-math-namespace-functions.md#fminf)|Определение минимального числового значения аргументов|
|[fmod](concurrency-fast-math-namespace-functions.md#fmod)|Вычисляет остаток числа с плавающей запятой _X/_Y|
|[fmodf](concurrency-fast-math-namespace-functions.md#fmodf)|Вычисляет остаток числа с плавающей запятой _X/_Y|
|[frexp](concurrency-fast-math-namespace-functions.md#frexp)|Возвращает мантисса и показатель степени _X|
|[фрекспф](concurrency-fast-math-namespace-functions.md#frexpf)|Возвращает мантисса и показатель степени _X|
|[isFinite](concurrency-fast-math-namespace-functions.md#isfinite)|Определяет, имеет ли аргумент конечное значение|
|[isinf](concurrency-fast-math-namespace-functions.md#isinf)|Определяет, является ли аргумент бесконечной|
|[IsNaN](concurrency-fast-math-namespace-functions.md#isnan)|Определяет, является ли аргумент нечисловым|
|[ldexp](concurrency-fast-math-namespace-functions.md#ldexp)|Вычисляет вещественное число из мантиссаа и экспоненты|
|[лдекспф](concurrency-fast-math-namespace-functions.md#ldexpf)|Вычисляет вещественное число из мантиссаа и экспоненты|
|[Журналь](concurrency-fast-math-namespace-functions.md#log)|Вычисляет логарифм аргумента по основанию e.|
|[LOG10](concurrency-fast-math-namespace-functions.md#log10)|Вычисляет десятичный логарифм аргумента|
|[log10f](concurrency-fast-math-namespace-functions.md#log10f)|Вычисляет десятичный логарифм аргумента|
|[log2](concurrency-fast-math-namespace-functions.md#log2)|Вычисляет логарифм аргумента по основанию 2|
|[log2f](concurrency-fast-math-namespace-functions.md#log2f)|Вычисляет логарифм аргумента по основанию 2|
|[logf](concurrency-fast-math-namespace-functions.md#logf)|Вычисляет логарифм аргумента по основанию e.|
|[modf](concurrency-fast-math-namespace-functions.md#modf)|Разделяет _X на дробные и целые части.|
|[modff](concurrency-fast-math-namespace-functions.md#modff)|Разделяет _X на дробные и целые части.|
|[Pow](concurrency-fast-math-namespace-functions.md#pow)|Вычисляет _X, возведенное в степень _Y|
|[powf](concurrency-fast-math-namespace-functions.md#powf)|Вычисляет _X, возведенное в степень _Y|
|[округло](concurrency-fast-math-namespace-functions.md#round)|Округляет _X до ближайшего целого числа|
|[roundf](concurrency-fast-math-namespace-functions.md#roundf)|Округляет _X до ближайшего целого числа|
|[рскрт](concurrency-fast-math-namespace-functions.md#rsqrt)|Возвращает обратную величину квадратного корня аргумента|
|[рскртф](concurrency-fast-math-namespace-functions.md#rsqrtf)|Возвращает обратную величину квадратного корня аргумента|
|[signbit](concurrency-fast-math-namespace-functions.md#signbit)|Возвращает знак аргумента|
|[сигнбитф](concurrency-fast-math-namespace-functions.md#signbitf)|Возвращает знак аргумента|
|[Sin](concurrency-fast-math-namespace-functions.md#sin)|Вычисляет значение синуса для аргумента|
|[синкос](concurrency-fast-math-namespace-functions.md#sincos)|Вычисляет синус и косинус значения _X|
|[синкосф](concurrency-fast-math-namespace-functions.md#sincosf)|Вычисляет синус и косинус значения _X|
|[sinf](concurrency-fast-math-namespace-functions.md#sinf)|Вычисляет значение синуса для аргумента|
|[sinh](concurrency-fast-math-namespace-functions.md#sinh)|Вычисляет гиперболический синус значения аргумента|
|[sinhf](concurrency-fast-math-namespace-functions.md#sinhf)|Вычисляет гиперболический синус значения аргумента|
|[МНИМ](concurrency-fast-math-namespace-functions.md#sqrt)|Вычисляет квадратный корень аргумента|
|[sqrtf](concurrency-fast-math-namespace-functions.md#sqrtf)|Вычисляет квадратный корень аргумента|
|[тангенс](concurrency-fast-math-namespace-functions.md#tan)|Вычисляет значение тангенса аргумента|
|[tanf](concurrency-fast-math-namespace-functions.md#tanf)|Вычисляет значение тангенса аргумента|
|[tanh](concurrency-fast-math-namespace-functions.md#tanh)|Вычисляет значение гиперболического тангенса аргумента|
|[tanhf](concurrency-fast-math-namespace-functions.md#tanhf)|Вычисляет значение гиперболического тангенса аргумента|
|[TRUNC](concurrency-fast-math-namespace-functions.md#trunc)|Усекает аргумент до целочисленного компонента|
|[truncf](concurrency-fast-math-namespace-functions.md#truncf)|Усекает аргумент до целочисленного компонента|

## <a name="requirements"></a>Требования

**Заголовок:** amp_math.h

**Пространство имен:** Concurrency:: fast_math

## <a name="see-also"></a>См. также статью

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
