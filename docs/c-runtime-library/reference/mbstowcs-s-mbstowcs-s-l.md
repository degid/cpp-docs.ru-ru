---
title: mbstowcs_s, _mbstowcs_s_l
ms.date: 4/2/2020
api_name:
- _mbstowcs_s_l
- mbstowcs_s
- _o__mbstowcs_s_l
- _o_mbstowcs_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbstowcs_s_l
- mbstowcs_s
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
ms.openlocfilehash: 4a6e86e1122a7392862fa34a59042c32560fd69d
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915457"
---
# <a name="mbstowcs_s-_mbstowcs_s_l"></a>mbstowcs_s, _mbstowcs_s_l

Преобразует последовательность многобайтовых символов в соответствующую последовательность расширенных символов. Это версии функции [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count
);
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Параметры

*претурнвалуе*<br/>
Количество символов для преобразования.

*вкстр*<br/>
Адрес буфера для результирующей преобразованной строки расширенных символов.

*сизеинвордс*<br/>
Размер буфера *вкстр* в словах.

*мбстр*<br/>
Адрес последовательности многобайтовых символов, заканчивающейся нуль-символом.

*count*<br/>
Максимальное количество расширенных символов для хранения в буфере *вкстр* , не включая завершающее значение null или [_TRUNCATE](../../c-runtime-library/truncate.md).

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

|Условие ошибки|Возвращаемое значение **и** перевернутое|
|---------------------|------------------------------|
|*вкстр* имеет **значение NULL** , а *сизеинвордс* > 0|**еинвал**|
|*мбстр* имеет **значение NULL**|**еинвал**|
|Буфер назначения слишком мал для хранения преобразованной строки (если *Счетчик* не **_TRUNCATE**; см. примечания ниже)|**ERANGE**|
|*вкстр* не имеет **значение NULL** и *сизеинвордс* = = 0|**еинвал**|

Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает код ошибки **и устанавливает значение** переводится, как указано в таблице.

## <a name="remarks"></a>Примечания

Функция **mbstowcs_s** преобразует строку многобайтовых символов, на которую указывает *мбстр* , в широкие символы, хранящиеся в буфере, на который указывает *вкстр*. Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.

- Встретился многобайтовый символ null.

- Встретился недопустимый многобайтовый символ.

- Количество расширенных символов, хранящихся в буфере *вкстр* , равно *Count*.

Строка назначения всегда завершается нуль-символом (даже в случае ошибки).

Если параметр *Count* является специальным значением [_TRUNCATE](../../c-runtime-library/truncate.md), то **mbstowcs_s** преобразуется в большую часть строки, как помещается в буфер назначения, в то время как при этом остается место для нулевого терминатора.

Если **mbstowcs_s** успешно преобразует исходную строку, она помещает размер в расширенных символах преобразованной строки, включая знак завершения null, в *&#42;претурнвалуе* (предоставленный *претурнвалуе* не равен **null**). Это происходит, даже если аргумент *вкстр* имеет **значение NULL** и предоставляет способ определения требуемого размера буфера. Обратите внимание, что если *вкстр* имеет **значение NULL**, *Count* игнорируется, а *сизеинвордс* должен быть равен 0.

Если **mbstowcs_s** встречает недопустимый многобайтовый символ, он помещает 0 в *&#42;претурнвалуе*, устанавливает в качестве буфера назначения пустую строку **, устанавливает значение** очистки в **еилсек**и возвращает **еилсек**.

Если последовательности, на которые указывает *мбстр* и *вкстр* , перекрываются, поведение **mbstowcs_s** не определено.

> [!IMPORTANT]
> Убедитесь, что *вкстр* и *мбстр* не перекрываются, и что *Счетчик* правильно отражает число преобразуемых многобайтовых символов.

**mbstowcs_s** использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; **_mbstowcs_s_l** является идентичным, за исключением того, что использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**mbstowcs_s**|\<stdlib.h>|
|**_mbstowcs_s_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
