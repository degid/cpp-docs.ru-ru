---
title: _fcvt_s
ms.date: 4/2/2020
api_name:
- _fcvt_s
- _o__fcvt_s
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
- fcvt_s
- _fcvt_s
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
ms.openlocfilehash: 557a1d359c389f0eb7477aab4bf9cbb51558703a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920207"
---
# <a name="_fcvt_s"></a>_fcvt_s

Преобразует число с плавающей запятой в строку. Это версия функции [_fcvt](fcvt.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _fcvt_s(
   char* buffer,
   size_t sizeInBytes,
   double value,
   int count,
   int *dec,
   int *sign
);
template <size_t size>
errno_t _fcvt_s(
   char (&buffer)[size],
   double value,
   int count,
   int *dec,
   int *sign
); // C++ only
```

### <a name="parameters"></a>Параметры

*двойной*<br/>
Предоставленный буфер, в который помещается результат преобразования.

*сизеинбитес*<br/>
Размер буфера в байтах.

*value*<br/>
Число, которое требуется преобразовать.

*count*<br/>
Число разрядов после десятичной запятой.

*уменьшение*<br/>
Указатель на сохраненную позицию десятичной запятой.

*писать*<br/>
Указатель на сохраненный индикатор знака.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Список этих ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

В случае недопустимого параметра, как указано в приведенной ниже таблице, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция **устанавливает** **Еинвал** и возвращает **еинвал**.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*двойной*|*сизеинбитес*|значение|count|dec|подписывание|Возвращает|Значение в *буфере*|
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|
|**ЗАКАНЧИВАЮЩ**|any|any|any|any|any|**еинвал**|Не изменено.|
|Not **null** (указывает на допустимый объем памяти)|<=0|any|any|any|any|**еинвал**|Не изменено.|
|any|any|any|any|**ЗАКАНЧИВАЮЩ**|any|**еинвал**|Не изменено.|
|any|any|any|any|any|**ЗАКАНЧИВАЮЩ**|**еинвал**|Не изменено.|

## <a name="security-issues"></a>Проблемы с безопасностью

**_fcvt_s** может вызвать нарушение прав доступа, если *буфер* не указывает на допустимый объем памяти и не равен **null**.

## <a name="remarks"></a>Примечания

Функция **_fcvt_s** преобразует число с плавающей запятой в строку символов, завершающуюся нулем. Параметр *value* — это преобразуемое число с плавающей запятой. **_fcvt_s** сохраняет цифры *значения* в виде строки и добавляет нуль-символ ("\ 0"). Параметр *Count* задает количество цифр, сохраняемых после десятичной запятой. Лишние цифры округляются в *число* разрядов. Если *число меньше числа разрядов* точности, строка дополняется нулями.

В строке сохраняются только цифры. Позицию десятичной запятой и знака *значения* можно получить из *Dec* и *знака* после вызова. Параметр *Dec* указывает на целочисленное значение; Это целое значение задает позицию десятичной запятой относительно начала строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. *Знак* параметра указывает на целое число, обозначающее знак *значения*. Целое число устанавливается в 0, если *значение* положительное и имеет ненулевое число, если *значение* отрицательное.

Буфер **_CVTBUFSIZE** длины достаточно для любого значения с плавающей запятой.

Разница между **_ecvt_s** и **_fcvt_s** заключается в интерпретации параметра *Count* . **_ecvt_s** интерпретирует *количество* как общее количество цифр в выходной строке, а **_fcvt_s** *интерпретирует как количество* цифр после десятичной запятой.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Отладочная версия этой функции сначала заполняет буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**_fcvt_s**|\<stdlib.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

**Библиотеки:** все версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// fcvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main()
{
    char * buf = 0;
    int decimal;
    int sign;
    int err;

    buf = (char*) malloc(_CVTBUFSIZE);
    err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);

    if (err != 0)
    {
        printf("_fcvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 120000
```

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt_s](ecvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
[_fcvt](fcvt.md)<br/>
