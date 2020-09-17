---
title: Type — универсальные математические символы
description: Описание макросов в <tgmath.h>, упрощающих написание кода на языке C, который вызывает правую математическую функцию на основе типа аргумента.
ms.date: 9/3/2020
helpviewer_keywords:
- CRT tgmath.h
ms.openlocfilehash: 8994edcaa05247a16d90b47bca8ec26fca27cda7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89557779"
---
# <a name="type-generic-math"></a>Type — универсальные математические символы

Для ISO C Standard 11 (C11) и более поздних версий \<tgmath.h> заголовок, помимо включения \<math.h> и \<complex.h> , предоставляет макросы, которые вызывают соответствующую математическую функцию на основе типов параметров.

Математические функции библиотеки времени выполнения C бывают реальными и сложными вариантами. Каждый вариант состоит из трех разновидностей, в зависимости от типа аргумента: `float` , `double` и `long double` . Поскольку C не поддерживает перегрузку, например C++, у каждого варианта есть другое имя. Например, чтобы получить абсолютное значение вещественного значения с плавающей запятой, необходимо вызвать метод `fabsf` , или, `fabs` `fabsl` в зависимости от того, передается `float` `double` значение, или, `long double` соответственно. Чтобы получить комплексное абсолютное значение, необходимо вызвать один из методов, или, в зависимости от того, передается `cabsf` `cabs` `cabsl` ли `float` , `double` и `long double` сложное значение соответственно. Если аргументы не соответствуют ни одному из перечисленных выше типов, функция выбирается так, как будто аргументы являются двойными.

\<tgmath.h> содержит макросы, упрощающие выбор правой математической функции для вызова. Макросы проверяют тип, который они передают, а затем вызывают правую функцию. Например, `sqrt` макрос привязывается `sqrt(9.9f)` к `sqrtf()` , в то время как он привязывается `sqrt(9.9)` к `sqrt()` . Если хотя бы один аргумент макроса для универсального параметра является сложным, то макрос привязывается к сложной функции. в противном случае он вызывает реальную функцию.

Универсальные макросы типа в \<tgmath.h> позволяют писать более переносимый код, так как не требуется управлять приведением или выбирать различные имена функций в зависимости от типа аргумента.

Эти макросы находятся в собственном заголовке, поэтому программы, написанные с помощью `<math.h>` заголовка, не будут прерываться. Так что `double x = sin(42);` ведет себя всегда, когда вы включаете \<math.h> . Несмотря на это, ожидается, что большинство существующих программ на C не будут затронуты при \<tgmath.h> включении заголовка вместо \<math.h> или \<complex.h> .

В следующей таблице перечислены макросы, доступные в \<tgmath.h> и которые они расширяют. `modf` не включается в эту таблицу, так как не имеет соответствующего универсального типа макроса, так как не ясно, как обеспечить безопасность без усложнения разрешения типов.

|Макрос  |Real</br>`float`  | Real</br>`double` | Real</br>`long double` | Complex</br>`float` | Complex</br>`double` | Complex</br>`long double` |
|---------|---------|---------|---------|---------|---------|---------|
`acos` | [acosf](reference/mbsnbicmp-mbsnbicmp-l.md) | [ACOS](reference/mbsnbicmp-mbsnbicmp-l.md) | [acosl](reference/mbsnbicmp-mbsnbicmp-l.md) | [cacosf](reference/cacos-cacosf-cacosl.md) | [cacos](reference/cacos-cacosf-cacosl.md) | [cacosl](reference/cacos-cacosf-cacosl.md) |
`acosh` | [acoshf](reference/acosh-acoshf-acoshl.md) | [acosh](reference/acosh-acoshf-acoshl.md) | [acoshl](reference/acosh-acoshf-acoshl.md) | [cacoshf](reference/cacosh-cacoshf-cacoshl.md) | [cacosh](reference/cacosh-cacoshf-cacoshl.md) | [cacoshl](reference/cacosh-cacoshf-cacoshl.md) |
`asin` | [asinf](reference/asin-asinf-asinl.md) | [ASIN](reference/asin-asinf-asinl.md) | [asinl](reference/asin-asinf-asinl.md) | [casinf](reference/casin-casinf-casinl.md) | [casin](reference/casin-casinf-casinl.md) | [casinl](reference/casin-casinf-casinl.md) |
`asinh` | [asinhf](reference/asin-asinf-asinl.md) | [asinh](reference/asin-asinf-asinl.md) | [asinhl](reference/asin-asinf-asinl.md) | [casinhf](reference/casinh-casinhf-casinhl.md) | [casinh](reference/casinh-casinhf-casinhl.md) | [casinhl](reference/casinh-casinhf-casinhl.md) |
`atan` | [atanf](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [Atan](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atanl](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [catanf](reference/catan-catanf-catanl.md) | [catan](reference/catan-catanf-catanl.md) | [catanl](reference/catan-catanf-catanl.md) |
`atanh` | [atanhf](reference/atanh-atanhf-atanhl.md) | [atanh](reference/atanh-atanhf-atanhl.md) | [atanhl](reference/atanh-atanhf-atanhl.md) | [catanhf](reference/catanh-catanhf-catanhl.md) | [catanh](reference/catanh-catanhf-catanhl.md) | [catanhl](reference/catanh-catanhf-catanhl.md) |
`cos` | [cosf](reference/cos-cosf-cosl.md) | [COS](reference/cos-cosf-cosl.md) | [cosl](reference/cos-cosf-cosl.md) | [ccosf](reference/ccos-ccosf-ccosl.md) | [ccos](reference/ccos-ccosf-ccosl.md) | [ccosl](reference/ccos-ccosf-ccosl.md) |
`cosh` | [coshf](reference/cosh-coshf-coshl.md) | [cosh](reference/cosh-coshf-coshl.md) | [coshl](reference/cosh-coshf-coshl.md) | [ccoshf](reference/ccosh-ccoshf-ccoshl.md) | [ccosh](reference/ccosh-ccoshf-ccoshl.md) | [ccoshl](reference/ccosh-ccoshf-ccoshl.md) |
`exp` | [expf](reference/exp-expf.md) | [exp](reference/exp-expf.md) | [expl](reference/exp-expf.md) | [cexpf](reference/cexp-cexpf-cexpl.md) | [cexp](reference/cexp-cexpf-cexpl.md) | [cexpl](reference/cexp-cexpf-cexpl.md) |
`fabs` | [fabsf](reference/fabs-fabsf-fabsl.md) | [fabs](reference/fabs-fabsf-fabsl.md) | [фабсл](reference/fabs-fabsf-fabsl.md) | [cabsf](reference/cabs-cabsf-cabsl.md) | [Cabs](reference/cabs-cabsf-cabsl.md) | [cabsl](reference/cabs-cabsf-cabsl.md) |
`log` | [logf](reference/log-logf-log10-log10f.md) | [Журналь](reference/log-logf-log10-log10f.md) | [logl](reference/log-logf-log10-log10f.md) | [clogf](reference/clog-clogf-clogl.md) | [clog](reference/clog-clogf-clogl.md) | [clogl](reference/clog-clogf-clogl.md) |
`pow` | [powf](reference/pow-powf-powl.md) | [Pow](reference/pow-powf-powl.md) | [повл](reference/pow-powf-powl.md) | [cpowf](reference/cpow-cpowf-cpowl.md) | [cpow](reference/cpow-cpowf-cpowl.md) | [cpowl](reference/cpow-cpowf-cpowl.md) |
`sin` | [sinf](reference/sin-sinf-sinl.md) | [Sin](reference/sin-sinf-sinl.md) | [sinl](reference/sin-sinf-sinl.md) | [csinf](reference/csin-csinf-csinl.md) | [csin](reference/csin-csinf-csinl.md) | [csinl](reference/csin-csinf-csinl.md) |
`sinh` | [sinhf](reference/sinh-sinhf-sinhl.md) | [sinh](reference/sinh-sinhf-sinhl.md) | [sinhl](reference/sinh-sinhf-sinhl.md) | [csinhf](reference/csinh-csinhf-csinhl.md) | [csinh](reference/csinh-csinhf-csinhl.md) | [csinhl](reference/csinh-csinhf-csinhl.md) |
`sqrt` | [sqrtf](reference/sqrt-sqrtf-sqrtl.md) | [МНИМ](reference/sqrt-sqrtf-sqrtl.md) | [sqrtl](reference/sqrt-sqrtf-sqrtl.md) | [csqrtf](reference/csqrt-csqrtf-csqrtl.md) | [csqrt](reference/csqrt-csqrtf-csqrtl.md) | [csqrtl](reference/csqrt-csqrtf-csqrtl.md) |
`tan` | [tanf](reference/tan-tanf-tanl.md) | [тангенс](reference/tan-tanf-tanl.md) | [tanl](reference/tan-tanf-tanl.md) | [ctanf](reference/ctan-ctanf-ctanl.md) | [ctan](reference/ctan-ctanf-ctanl.md) | [ctanl](reference/ctan-ctanf-ctanl.md) |
`tanh` | [tanhf](reference/tanh-tanhf-tanhl.md) | [tanh](reference/tanh-tanhf-tanhl.md) | [tanhl](reference/tanh-tanhf-tanhl.md) | [ctanhf](reference/ctanh-ctanhf-ctanhl.md) | [ctanh](reference/ctanh-ctanhf-ctanhl.md) | [ctanhl](reference/ctanh-ctanhf-ctanhl.md) |
`atan2` | [atan2f](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atan2](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [atan2l](reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | - | - | - |
`cbrt` | [cbrtf](reference/cbrt-cbrtf-cbrtl.md) | [cbrt](reference/cbrt-cbrtf-cbrtl.md) | [cbrtl](reference/cbrt-cbrtf-cbrtl.md) | - | - | - |
`ceil` | [ceilf](reference/ceil-ceilf-ceill.md) | [ceil](reference/ceil-ceilf-ceill.md) | [ceill](reference/ceil-ceilf-ceill.md) | - | - | - |
`copysign` | [copysignf](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | [кописигн](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | [copysignl](reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md) | - | - | - |
`erf` | [erff](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erf](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erfl](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | - | - | - |
`erfc` | [erfcf](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erfc](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | [erfcl](reference/erf-erff-erfl-erfc-erfcf-erfcl.md) | - | - | - |
`exp2` | [exp2f](reference/exp2-exp2f-exp2l.md) | [EXP2](reference/exp2-exp2f-exp2l.md) | [exp2l](reference/exp2-exp2f-exp2l.md) | - | - | - |
`expm1` | [expm1f](reference/expm1-expm1f-expm1l.md) | [expm1](reference/expm1-expm1f-expm1l.md) | [expm1l](reference/expm1-expm1f-expm1l.md) | - | - | - |
`fdim` | [fdimf](reference/fdim-fdimf-fdiml.md) | [fdim](reference/fdim-fdimf-fdiml.md) | [fdiml](reference/fdim-fdimf-fdiml.md) | - | - | - |
`floor` | [floorf](reference/floor-floorf-floorl.md) | [фабрич](reference/floor-floorf-floorl.md) | [floorl](reference/floor-floorf-floorl.md) | - | - | - |
`fma` | [fmaf](reference/fma-fmaf-fmal.md) | [fma](reference/fma-fmaf-fmal.md) | [fmal](reference/fma-fmaf-fmal.md) | - | - | - |
`fmax` | [fmaxf](reference/fmax-fmaxf-fmaxl.md) | [fmax](reference/fmax-fmaxf-fmaxl.md) | [fmaxl](reference/fmax-fmaxf-fmaxl.md) | - | - | - |
`fmin` | [fminf](reference/fmin-fminf-fminl.md) | [fmin](reference/fmin-fminf-fminl.md) | [fminl](reference/fmin-fminf-fminl.md) | - | - | - |
`fmod` | [fmodf](reference/fmod-fmodf.md) | [fmod](reference/fmod-fmodf.md) | [fmodl](reference/fmod-fmodf.md) | - | - | - |
`frexp` | [фрекспф](reference/frexp.md) | [frexp](reference/frexp.md) | [фрекспл](reference/frexp.md) | - | - | - |
`hypot` | [хипотф](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | [hypot](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | [hypotl](reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md) | - | - | - |
`ilogb` | [ilogbf](reference/ilogb-ilogbf-ilogbl2.md) | [ilogb](reference/ilogb-ilogbf-ilogbl2.md) | [ilogbl](reference/ilogb-ilogbf-ilogbl2.md) | - | - | - |
`ldexp` | [лдекспф](reference/ldexp.md) | [ldexp](reference/ldexp.md) | [лдекспл](reference/ldexp.md) | - | - | - |
`lgamma` | [lgammaf](reference/lgamma-lgammaf-lgammal.md) | [lgamma](reference/lgamma-lgammaf-lgammal.md) | [lgammal](reference/lgamma-lgammaf-lgammal.md) | - | - | - |
`llrint` | [llrintf](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [llrint](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [llrintl](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | - | - | - |
`llround` | [llroundf](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [llround](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [llroundl](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | - | - | - |
`log10` | [log10f](reference/log-logf-log10-log10f.md) | [LOG10](reference/log-logf-log10-log10f.md) | [log10l](reference/log-logf-log10-log10f.md) | - | - | - |
`log1p` | [log1pf](reference/log1p-log1pf-log1pl2.md) | [log1p](reference/log1p-log1pf-log1pl2.md) | [log1pl](reference/log1p-log1pf-log1pl2.md) | - | - | - |
`log2` | [log2f](reference/log2-log2f-log2l.md) | [log2](reference/log2-log2f-log2l.md) | [log2l](reference/log2-log2f-log2l.md) | - | - | - |
`logb` | [logbf](reference/logb-logbf-logbl-logb-logbf.md) | [logb](reference/logb-logbf-logbl-logb-logbf.md) | [logbl](reference/logb-logbf-logbl-logb-logbf.md) | - | - | - |
`lrint` | [lrintf](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [lrint](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | [lrintl](reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md) | - | - | - |
`lround` | [lroundf](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [lround](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | [lroundl](reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md) | - | - | - |
`nearbyint` | [nearbyintf](reference/nearbyint-nearbyintf-nearbyintl1.md) | [nearbyint](reference/nearbyint-nearbyintf-nearbyintl1.md) | [nearbyintl](reference/nearbyint-nearbyintf-nearbyintl1.md) | - | - | - |
`nextafter` | [некстафтерф](reference/nextafter-functions.md) | [nextafter](reference/nextafter-functions.md) | [nextafterl](reference/nextafter-functions.md) | - | - | - |
`nexttoward` | [nexttowardf](reference/nextafter-functions.md) | [nexttoward](reference/nextafter-functions.md) | [nexttowardl](reference/nextafter-functions.md) | - | - | - |
`remainder` | [remainderf](reference/remainder-remainderf-remainderl.md) | [дальнейшем](reference/remainder-remainderf-remainderl.md) | [remainderl](reference/remainder-remainderf-remainderl.md) | - | - | - |
`remquo` | [remquof](reference/remquo-remquof-remquol.md) | [remquo](reference/remquo-remquof-remquol.md) | [remquol](reference/remquo-remquof-remquol.md) | - | - | - |
`rint` | [rintf](reference/rint-rintf-rintl.md) | [rint](reference/rint-rintf-rintl.md) | [rintl](reference/rint-rintf-rintl.md) | - | - | - |
`round` | [roundf](reference/round-roundf-roundl.md) | [округло](reference/round-roundf-roundl.md) | [roundl](reference/round-roundf-roundl.md) | - | - | - |
`scalbln` | [scalblnf](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbln](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalblnl](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | - | - | - |
`scalbn` | [scalbnf](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbn](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | [scalbnl](reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md) | - | - | - |
`tgamma` | [tgammaf](reference/tgamma-tgammaf-tgammal.md) | [tgamma](reference/tgamma-tgammaf-tgammal.md) | [tgammal](reference/tgamma-tgammaf-tgammal.md) | - | - | - |
`trunc` | [truncf](reference/trunc-truncf-truncl.md) | [TRUNC](reference/trunc-truncf-truncl.md) | [truncl](reference/trunc-truncf-truncl.md) | - | - | - |
`carg` | - | - | - | [cargf](reference/carg-cargf-cargl.md) | [carg](reference/carg-cargf-cargl.md) | [cargl](reference/carg-cargf-cargl.md) |
`conj` | - | - | - | [conjf](reference/conj-conjf-conjl.md) | [конж](reference/conj-conjf-conjl.md) | [conjl](reference/conj-conjf-conjl.md) |
`creal` | - | - | - | [crealf](reference/creal-crealf-creall.md) | [creal](reference/creal-crealf-creall.md) | [creall](reference/creal-crealf-creall.md) |
`cimag` | - | - | - | [cimagf](reference/cimag-cimagf-cimagl.md) | [cimag](reference/cimag-cimagf-cimagl.md) | [cimagl](reference/cimag-cimagf-cimagl.md) |
`cproj` | - | - | - | [cprojf](reference/cproj-cprojf-cprojl.md) | [cproj](reference/cproj-cprojf-cprojl.md) | [cprojl](reference/cproj-cprojf-cprojl.md) |

## <a name="requirements"></a>Требования

[std: требуется c++ 11](../build/reference/std-specify-language-standard-version.md) или более поздней версии.

Windows SDK версии 10.0.20201.0 или более поздней.

## <a name="see-also"></a>Дополнительно

[Справочник по библиотеке времени выполнения C](c-run-time-library-reference.md)
