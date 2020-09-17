---
title: _clear87, _clearfp
ms.date: 04/05/2018
api_name:
- _clearfp
- _clear87
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- clearfp
- _clearfp
- _clear87
- clear87
helpviewer_keywords:
- clearing floating point status word
- clearfp function
- _clear87 function
- _clearfp function
- clear87 function
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
ms.openlocfilehash: 4ca49895b881d9e307c1116681bc36f86b167c25
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942955"
---
# <a name="_clear87-_clearfp"></a>_clear87, _clearfp

Получает и очищает слово состояния модуля операций с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
unsigned int _clear87( void );
unsigned int _clearfp( void );
```

## <a name="return-value"></a>Возвращаемое значение

Биты в возвращенном значении указывают состояние числа с плавающей запятой до вызова **_clear87** или **_clearfp**. Полное определение битов, возвращаемых функцией **_clear87**, см. в разделе float.h. Многие математические библиотечные функции изменяют слово состояния 8087/80287 с непредсказуемыми результатами. Возвращаемые значения из **_clear87** и **_status87** становятся более надежными, так как между известными состояниями слова состояния с плавающей запятой выполняется меньше операций с плавающей точкой.

## <a name="remarks"></a>Примечания

Функция **_clear87** очищает флаги исключений в слове состояния с плавающей запятой, устанавливает для бита значение 0 и возвращает слово состояния. Слово состояния — это сочетание слова состояния 8087/80287 и других условий, обнаруженных обработчиком исключений 8087/80287, таких как переполнение стека или потеря точности.

**_clearfp** — это независимая от платформы переносимая версия подпрограммы **_clear87** . Он идентичен **_clear87** на платформах Intel (x86) и поддерживается платформами x64 и ARM. Чтобы обеспечить перенос кода с плавающей запятой на x64 и ARM, используйте **_clearfp**. Если вы предназначена только для платформ x86, можно использовать либо **_clear87** , либо **_clearfp**.

Эти функции являются устаревшими при компиляции с [параметром/CLR (компиляция общеязыковой среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md) , так как среда CLR поддерживает только точность с плавающей запятой по умолчанию.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_clear87**|\<float.h>|
|**_clearfp**|\<float.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_clear87.c
// compile with: /Od

// This program creates various floating-point
// problems, then uses _clear87 to report on these problems.
// Compile this program with Optimizations disabled (/Od).
// Otherwise the optimizer will remove the code associated with
// the unused floating-point values.
//

#include <stdio.h>
#include <float.h>

int main( void )
{
   double a = 1e-40, b;
   float x, y;

   printf( "Status: %.4x - clear\n", _clear87()  );

   // Store into y is inexact and underflows:
   y = a;
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );

   // y is denormal:
   b = y;
   printf( "Status: %.4x - denormal\n", _clear87() );
}
```

```Output
Status: 0000 - clear
Status: 0003 - inexact, underflow
Status: 80000 - denormal
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
