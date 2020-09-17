---
title: div, ldiv, lldiv
ms.date: 04/05/2018
api_name:
- div
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
- api-ms-win-crt-utility-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- div
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
ms.openlocfilehash: 24432ec1514f6cd2d569fd5752a8ed7118059d6a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234228"
---
# <a name="div-ldiv-lldiv"></a>div, ldiv, lldiv

Вычисляет частное и остаток от деления двух целочисленных значений.

## <a name="syntax"></a>Синтаксис

```C
div_t div(
   int numer,
   int denom
);
ldiv_t ldiv(
   long numer,
   long denom
);
lldiv_t lldiv(
   long long numer,
   long long denom
);
```

```cpp
ldiv_t div(
   long numer,
   long denom
); /* C++ only */
lldiv_t div(
   long long numer,
   long long denom
); /* C++ only */
```

### <a name="parameters"></a>Параметры

*число ключей*<br/>
Числитель.

*деном*<br/>
Знаменатель.

## <a name="return-value"></a>Возвращаемое значение

элемент **div** , вызываемый с помощью аргументов типа **`int`** , возвращает структуру типа **div_t**, которая состоит из частного и остатка. Возвращаемое значение с аргументами типа **`long`** **ldiv_t**, а возвращаемое значение с аргументами типа **`long long`** — **lldiv_t**. **div_t**, **ldiv_t**и **lldiv_t** определяются в \<stdlib.h> .

## <a name="remarks"></a>Примечания

Функция **div** делит *число ключей* на *Деном* , тем самым вычисляя частное и остаток. Структура [div_t](../../c-runtime-library/standard-types.md) содержит частное, **quot**и остаток, **REM**. Знак частного является таким же, как и у математического частного. Его абсолютное значение представляет собой наибольшее целое число, которое меньше абсолютного значения математического частного. Если знаменатель равен 0, выполнение программы прекратится и появится сообщение об ошибке.

Перегрузки **div** , принимающие аргументы типа **`long`** или **`long long`** , доступны только для кода C++. Возвращаемые типы [ldiv_t](../../c-runtime-library/standard-types.md) и [lldiv_t](../../c-runtime-library/standard-types.md) содержат элементы **quot** и **REM**, которые имеют те же значения, что и элементы **div_t**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**div**, **ldiv**, **lldiv**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_div.c
// arguments: 876 13

// This example takes two integers as command-line
// arguments and displays the results of the integer
// division. This program accepts two arguments on the
// command line following the program name, then calls
// div to divide the first argument by the second.
// Finally, it prints the structure members quot and rem.
//

#include <stdlib.h>
#include <stdio.h>
#include <math.h>

int main( int argc, char *argv[] )
{
   int x,y;
   div_t div_result;

   x = atoi( argv[1] );
   y = atoi( argv[2] );

   printf( "x is %d, y is %d\n", x, y );
   div_result = div( x, y );
   printf( "The quotient is %d, and the remainder is %d\n",
           div_result.quot, div_result.rem );
}
```

```Output
x is 876, y is 13
The quotient is 67, and the remainder is 5
```

## <a name="see-also"></a>См. также раздел

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
