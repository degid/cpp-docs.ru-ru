---
title: _set_output_format
ms.date: 11/04/2016
api_name:
- _set_output_format
api_location:
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_output_format
- _set_output_format
helpviewer_keywords:
- _TWO_DIGIT_EXPONENT constant
- output formatting
- TWO_DIGIT_EXPONENT constant
- _set_output_format function
- set_output_format function
ms.assetid: 1cb48df8-44b4-4400-bd27-287831d6b3ff
ms.openlocfilehash: c855df4c29a53fd898b920f6446afe4e568ba5bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360918"
---
# <a name="_set_output_format"></a>_set_output_format

Настраивает форматы вывода, которые используются форматированными функциями ввода-вывода.

> [!IMPORTANT]
> Эта функция является устаревшей. Начиная с Visual Studio 2015 она недоступна в CRT.

## <a name="syntax"></a>Синтаксис

```
unsigned int _set_output_format(
   unsigned int format
);
```

#### <a name="parameters"></a>Параметры

*Формат*<br/>
[in] Значение, представляющее используемый формат.

## <a name="return-value"></a>Возвращаемое значение

Предыдущий формат вывода.

## <a name="remarks"></a>Примечания

`_set_output_format` используется для настройки вывода форматированных функций ввода-вывода, таких как [printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md). В настоящее время единственное соглашение о форматировании, которое эта функция может изменить, — число цифр показателя степени в числах с плавающей запятой.

По умолчанию такие функции, как `printf_s`, `wprintf_s`и связанные функции в стандартной библиотеке C Visual C++, выводят три цифры в показателе степени, даже если значение показателя не требует третьей цифры. Нули используются для заполнения значения тремя цифрами. `_set_output_format` позволяет изменить это поведение, чтобы только две цифры выводились в показателе степени, если только значение показателя не требует третьей цифры.

Чтобы включить показатели степени с двумя цифрами, вызовите эту функцию с параметром `_TWO_DIGIT_EXPONENT`, как показано в примере. Чтобы отключить показатели степени с двумя цифрами, вызовите эту функцию с аргументом 0.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`_set_output_format`|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../c-runtime-library/compatibility.md) во введении.

## <a name="example"></a>Пример

```C
// crt_set_output_format.c
#include <stdio.h>

void printvalues(double x, double y)
{
   printf_s("%11.4e %11.4e\n", x, y);
   printf_s("%11.4E %11.4E\n", x, y);
   printf_s("%11.4g %11.4g\n", x, y);
   printf_s("%11.4G %11.4G\n", x, y);
}

int main()
{
   double x = 1.211E-5;
   double y = 2.3056E-112;
   unsigned int old_exponent_format;

   // Use the default format
   printvalues(x, y);

   // Enable two-digit exponent format
   old_exponent_format = _set_output_format(_TWO_DIGIT_EXPONENT);

   printvalues(x, y);

   // Disable two-digit exponent format
   _set_output_format( old_exponent_format );

   printvalues(x, y);
}
```

```Output
1.2110e-005 2.3056e-112
1.2110E-005 2.3056E-112
1.211e-005  2.306e-112
1.211E-005  2.306E-112
1.2110e-05 2.3056e-112
1.2110E-05 2.3056E-112
  1.211e-05  2.306e-112
  1.211E-05  2.306E-112
1.2110e-005 2.3056e-112
1.2110E-005 2.3056E-112
1.211e-005  2.306e-112
1.211E-005  2.306E-112
```

## <a name="see-also"></a>См. также раздел

[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_get_output_format](../c-runtime-library/get-output-format.md)
