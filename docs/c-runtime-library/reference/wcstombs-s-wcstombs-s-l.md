---
title: wcstombs_s, _wcstombs_s_l
ms.date: 4/2/2020
api_name:
- _wcstombs_s_l
- wcstombs_s
- _o__wcstombs_s_l
- _o_wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
ms.openlocfilehash: 7254df673694bf4d91679f1a41837c10f61d28e2
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910607"
---
# <a name="wcstombs_s-_wcstombs_s_l"></a>wcstombs_s, _wcstombs_s_l

Преобразует последовательность расширенных символов в соответствующую последовательность многобайтовых символов. Версии функций [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t wcstombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count
);

errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);

template <size_t size>
errno_t wcstombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only

template <size_t size>
errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Параметры

*претурнвалуе*<br/>
Размер в байтах преобразованной строки, включая знак завершения null.

*мбстр*<br/>
Адрес буфера для итоговой преобразованной строки многобайтовых символов.

*сизеинбитес*<br/>
Размер в байтах буфера *мбстр* .

*вкстр*<br/>
Указывает на строку расширенных символов, которую необходимо преобразовать.

*count*<br/>
Максимальное число байтов для хранения в буфере *мбстр* , не включая завершающий символ null или [_TRUNCATE](../../c-runtime-library/truncate.md).

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

|Условие ошибки|Возвращаемое значение **и** перевернутое|
|---------------------|------------------------------|
|*мбстр* имеет **значение NULL** , а *сизеинбитес* > 0|**еинвал**|
|*вкстр* имеет **значение NULL**|**еинвал**|
|Буфер назначения слишком мал для хранения преобразованной строки (если *Счетчик* не **_TRUNCATE**; см. примечания ниже)|**ERANGE**|

Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает код ошибки **и устанавливает значение** переводится, как указано в таблице.

## <a name="remarks"></a>Примечания

Функция **wcstombs_s** преобразует строку расширенных символов, на которую указывает *вкстр* , в многобайтовые символы, хранящиеся в буфере, на который указывает *мбстр*. Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.

- Встретился расширенный нуль-символ.

- Встретился расширенный символ, который не может быть преобразован.

- Число байтов, хранящихся в буфере *мбстр* , равно *Count*.

Строка назначения всегда завершается нуль-символом (даже в случае ошибки).

Если параметр *Count* является специальным значением [_TRUNCATE](../../c-runtime-library/truncate.md), то **wcstombs_s** преобразуется в большую часть строки, как помещается в буфер назначения, в то время как при этом остается место для нулевого терминатора. Если строка усекается, возвращаемое значение — **стрункате**, а преобразование считается успешным.

Если **wcstombs_s** успешно преобразует исходную строку, она помещает размер в байтах преобразованной строки, включая знак завершения null, в *&#42;претурнвалуе* (предоставленный *претурнвалуе* не равен **null**). Это происходит, даже если аргумент *мбстр* имеет **значение NULL** и предоставляет способ определения требуемого размера буфера. Обратите внимание, что если *мбстр* имеет **значение NULL**, *Count* игнорируется.

Если **wcstombs_s** обнаруживает широкий символ, который он не может преобразовать в многобайтовый символ, он помещает 0 в *&#42;претурнвалуе*, устанавливает для буфера назначения пустую строку **, устанавливает значение** очистки в **еилсек**и возвращает **еилсек**.

Если последовательности, на которые указывает *вкстр* и *мбстр* , перекрываются, поведение **wcstombs_s** не определено.

> [!IMPORTANT]
> Убедитесь, что *вкстр* и *мбстр* не перекрываются, и что этот *Счетчик* правильно отражает количество расширенных символов для преобразования.

**wcstombs_s** использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; **_wcstombs_s_l** идентичен **wcstombs** , за исключением того, что он использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcstombs_s**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Эта программа иллюстрирует поведение функции **wcstombs_s** .

```C
// crt_wcstombs_s.c
// This example converts a wide character
// string to a multibyte character string.
#include <stdio.h>
#include <stdlib.h>
#include <assert.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t   i;
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t*pWCBuffer = L"Hello, world.";

    printf( "Convert wide-character string:\n" );

    // Conversion
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,
               pWCBuffer, (size_t)BUFFER_SIZE );

    // Output
    printf("   Characters converted: %u\n", i);
    printf("    Multibyte character: %s\n\n",
     pMBBuffer );

    // Free multibyte character buffer
    if (pMBBuffer)
    {
    free(pMBBuffer);
    }
}
```

```Output
Convert wide-character string:
   Characters converted: 14
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
