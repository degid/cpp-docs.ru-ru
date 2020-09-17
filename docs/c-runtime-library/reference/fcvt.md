---
title: _fcvt
ms.date: 4/2/2020
api_name:
- _fcvt
- _o__fcvt
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
- _fcvt
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
ms.openlocfilehash: 2ca8a7fcd58e91ffa8982f30117b09af587d96cf
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920186"
---
# <a name="_fcvt"></a>_fcvt

Преобразует число с плавающей запятой в строку. Существует более безопасная версия этой функции, см. раздел [_fcvt_s](fcvt-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *_fcvt(
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
Число разрядов после десятичной запятой.

*уменьшение*<br/>
Указатель на сохраненную позицию десятичной запятой.

*писать*<br/>
Указатель на сохраненный индикатор знака.

## <a name="return-value"></a>Возвращаемое значение

**_fcvt** возвращает указатель на строку цифр, **null** при ошибке.

## <a name="remarks"></a>Примечания

Функция **_fcvt** преобразует число с плавающей запятой в строку символов, завершающуюся нулем. Параметр *value* — это преобразуемое число с плавающей запятой. **_fcvt** сохраняет цифры *значения* в виде строки и добавляет нуль-символ ("\ 0"). Параметр *Count* задает количество цифр, сохраняемых после десятичной запятой. Лишние цифры округляются в *число* разрядов. Если *число меньше числа разрядов* точности, строка дополняется нулями.

Общее число цифр, возвращенных **_fcvt** не будет превышать **_CVTBUFSIZE**.

В строке сохраняются только цифры. Позицию десятичной запятой и знака *значения* можно получить из *Dec* и знака после вызова. Параметр *Dec* указывает на целочисленное значение; Это целое значение задает позицию десятичной запятой относительно начала строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. *Знак* параметра указывает на целое число, обозначающее знак *значения*. Целое число устанавливается в 0, если *значение* положительное и имеет ненулевое число, если *значение* отрицательное.

Разница между **_ecvt** и **_fcvt** заключается в интерпретации параметра *Count* . **_ecvt** интерпретирует *число* как общее количество цифр в выходной строке, а **_fcvt** *интерпретирует как количество* цифр после десятичной запятой.

**_ecvt** и **_fcvt** используют один статически выделенный буфер для преобразования. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова.

Эта функция проверяет свои параметры. Если *Dec* или *Sign* имеет **значение NULL**или *Count* равно 0, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** устанавливается значение, а возвращается **значение NULL** .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fcvt.c
// compile with: /W3
// This program converts the constant
// 3.1415926535 to a string and sets the pointer
// buffer to point to that string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int  decimal, sign;
   char *buffer;
   double source = 3.1415926535;

   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996
   // Note: _fcvt is deprecated; consider using _fcvt_s instead
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",
            source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0
```

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_gcvt](gcvt.md)<br/>
