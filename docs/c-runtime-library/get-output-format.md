---
title: _get_output_format
ms.date: 11/04/2016
api_name:
- _get_output_format
api_location:
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_output_format
- _get_output_format
helpviewer_keywords:
- output formatting
- get_output_format function
- _get_output_format function
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
ms.openlocfilehash: 682ab9796942e52ed036193887158ea22b738189
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349341"
---
# <a name="_get_output_format"></a>_get_output_format

Получает текущее значение флага формата вывода.

> [!IMPORTANT]
> Эта функция является устаревшей. Начиная с Visual Studio 2015 она недоступна в CRT.

## <a name="syntax"></a>Синтаксис

```
unsigned int _get_output_format();
```

## <a name="return-value"></a>Возвращаемое значение

Текущее значение флага формата вывода.

## <a name="remarks"></a>Примечания

Флаг формата вывода задает особенности форматированного ввода-вывода. В настоящее время флаг имеет два возможных значения: 0 и `_TWO_DIGIT_EXPONENT`. Если установлено значение `_TWO_DIGIT_EXPONENT` , числа с плавающей запятой выводятся только с двумя цифрами в показателе степени, если только значение показателя не требует третьей цифры. Если флаг равен нулю, то числа с плавающей запятой выводятся с тремя цифрами в показателе степени; при необходимости значение дополняется до трех цифр нулями.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`_get_output_format`|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../c-runtime-library/compatibility.md) во введении.

## <a name="see-also"></a>См. также раздел

[Синетаксис спецификации формата: функции printf и wprintf](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_set_output_format](../c-runtime-library/set-output-format.md)
