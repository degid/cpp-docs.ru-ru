---
title: _ecvt
ms.date: 4/2/2020
api_name:
- _ecvt
- _o__ecvt
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ecvt
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
ms.openlocfilehash: 227010fde5dc5ec82fc13c724c8d5a2f43788a8f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234202"
---
# <a name="_ecvt"></a>_ecvt

Преобразует **`double`** число в строку. Существует более безопасная версия этой функции, см. раздел [_ecvt_s](ecvt-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *_ecvt(
   double value,
   int count,
   int *dec,
   int *sign
);
```

### <a name="parameters"></a>Параметры

*value*<br/>
Число, которое требуется преобразовать.

*count*<br/>
Сохраненное число разрядов.

*уменьшение*<br/>
Сохраненная позиция десятичной запятой.

*sign*<br/>
Знак преобразованного числа.

## <a name="return-value"></a>Возвращаемое значение

**_ecvt** возвращает указатель на строку цифр; **Значение NULL** , если произошла ошибка.

## <a name="remarks"></a>Примечания

Функция **_ecvt** преобразует число с плавающей запятой в символьную строку. Параметр *value* — это преобразуемое число с плавающей запятой. Эта функция сохраняет *количество* разрядов *значения* в виде строки и добавляет нуль-символ ("\ 0"). Если число цифр в *значении* превышает *Count*, то цифра с низким порядком округляется. Если число знаков меньше *числа* , строка дополняется нулями.

Общее число цифр, возвращенных **_ecvt** не будет превышать **_CVTBUFSIZE**.

В строке сохраняются только цифры. Позицию десятичной запятой и знака *значения* можно получить из *Dec* и *знака* после вызова. Параметр *Dec* указывает на целочисленное значение, задающего позицию десятичной запятой относительно начала строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. Параметр *Sign* указывает на целое число, которое указывает знак преобразованного числа. Если целочисленное значение равно 0, число является положительным. В противном случае число будет отрицательным.

Разница между **_ecvt** и **_fcvt** заключается в интерпретации параметра *Count* . **_ecvt** интерпретирует *число* как общее количество цифр в выходной строке, а **_fcvt** *интерпретирует как количество* цифр после десятичной запятой.

**_ecvt** и **_fcvt** используют один статически выделенный буфер для преобразования. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова.

Эта функция проверяет свои параметры. Если *Dec* или *Sign* имеет **значение NULL**или *Count* равно 0, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** устанавливается значение, а возвращается **значение NULL** .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_ecvt**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_ecvt.c
// compile with: /W3
// This program uses _ecvt to convert a
// floating-point number to a character string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int     decimal,   sign;
   char    *buffer;
   int     precision = 10;
   double  source = 3.1415926535;

   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996
   // Note: _ecvt is deprecated; consider using _ecvt_s instead
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",
           source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0
```

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
