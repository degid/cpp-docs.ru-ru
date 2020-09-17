---
title: isgreater, isgreaterequal, isless, islessequal, islessgreater, isunordered
ms.date: 01/31/2019
f1_keywords:
- isgreater
- math/isgreater
- isgreaterequal
- math/isgreaterequal
- isless
- math/isless
- islessequal
- math/islessequal
- islessgreater
- math/islessgreater
- isunordered
- math/isunordered
helpviewer_keywords:
- isgreater function
- isgreaterequal function
- isless function
- islessequal function
- islessgreater function
- isunordered function
ms.openlocfilehash: 907b26f4e1824d7ef5c7c1a36b4e4d8ccb74c978
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220721"
---
# <a name="isgreater-isgreaterequal-isless-islessequal-islessgreater-isunordered"></a>isgreater, isgreaterequal, isless, islessequal, islessgreater, isunordered

Определяет упорядочение между двумя значениями с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
int isgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isgreaterequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isless(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isunordered(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */
```

```C++
template <class FloatingType1, class FloatingType2>
inline bool isgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isgreaterequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isless(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isunordered(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>Параметры

*x*, *y*<br/>
Сравниваемые значения с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Во всех сравнениях бесконечные знаки одного и того же знака сравниваются как равные. Отрицательная бесконечность меньше любого конечного значения или положительной бесконечности. Положительная бесконечность больше любого конечного значения или отрицательной бесконечности. Нули равны, независимо от знака. Значений NaN не меньше, равно или больше любого значения, включая другое значение NaN.

Если ни один из аргументов не является NaN, то **упорядочение макросов,** **исгреатерекуал**, не равно и **ислессекуал** , возвращает ненулевое **значение, если**указанная связь упорядочения между *x* и *y* имеет значение true. Эти макросы возвращают 0, если один или оба аргумента являются значений NaN или если связь упорядочения имеет значение false. Формы функций ведут себя одинаково, но возвращают **`true`** или **`false`** .

Макрос **ислессгреатер** возвращает ненулевое значение, если *x* и *y* не являются значений NaN, а *x* меньше или больше, чем *y*. Он возвращает 0, если один или оба аргумента являются значений NaN, или если значения равны. Форма функции функционирует таким же образом, но возвращает **`true`** или **`false`** .

Макрос **исунордеред** возвращает ненулевое значение, если *x*, *y*или оба являются значений NaN. В противном случае возвращается значение 0. Форма функции функционирует таким же образом, но возвращает **`true`** или **`false`** .

## <a name="remarks"></a>Примечания

Эти операции сравнения реализуются как макросы при компиляции как C, а также как встроенные функции шаблона при компиляции в виде C++.

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|--------------|---------------------------|-------------------------------|
| **замечательно**, **исгреатерекуал**, **без**<br/>**ислессекуал**, **ислессгреатер**, **исунордеред** | \<math.h> | \<math.h> или \<cmath> |

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
