---
title: wcsrtombs_s
ms.date: 4/2/2020
api_name:
- wcsrtombs_s
- _o_wcsrtombs_s
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
- wcsrtombs_s
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
ms.openlocfilehash: c804d232dbcce67b8d467eaa37ccf2b15282881a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910597"
---
# <a name="wcsrtombs_s"></a>wcsrtombs_s

Преобразует строку расширенных символов в соответствующее представление многобайтовой строки. Версия функции [wcsrtombs](wcsrtombs.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
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
Максимальное число байтов, сохраняемых в буфере *мбстр* , или [_TRUNCATE](../../c-runtime-library/truncate.md).

*мбстате*<br/>
Указатель на **mbstate_t** объект состояния преобразования.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

|Условие ошибки|Возвращаемое значение **и** перевернутое|
|---------------------|------------------------------|
|*мбстр* имеет **значение NULL** , а *сизеинбитес* > 0|**еинвал**|
|*вкстр* имеет **значение NULL**|**еинвал**|
|Буфер назначения слишком мал для хранения преобразованной строки (если *Счетчик* не **_TRUNCATE**; см. примечания ниже)|**ERANGE**|

Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает код ошибки **и устанавливает значение** переводится, как указано в таблице.

## <a name="remarks"></a>Примечания

Функция **wcsrtombs_s** преобразует строку расширенных символов, на которую указывает *вкстр* , в многобайтовые символы, хранящиеся в буфере, на который указывает *мбстр*, используя состояние преобразования, содержащееся в *мбстате*. Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.

- Встретился расширенный нуль-символ.

- Встретился расширенный символ, который не может быть преобразован.

- Число байтов, хранящихся в буфере *мбстр* , равно *Count*.

Строка назначения всегда завершается нуль-символом (даже в случае ошибки).

Если параметр *Count* является специальным значением [_TRUNCATE](../../c-runtime-library/truncate.md), то **wcsrtombs_s** преобразуется в большую часть строки, как помещается в буфер назначения, в то время как при этом остается место для нулевого терминатора.

Если **wcsrtombs_s** успешно преобразует исходную строку, она помещает размер в байтах преобразованной строки, включая знак завершения null, в *&#42;претурнвалуе* (предоставленный *претурнвалуе* не равен **null**). Это происходит, даже если аргумент *мбстр* имеет **значение NULL** и предоставляет способ определения требуемого размера буфера. Обратите внимание, что если *мбстр* имеет **значение NULL**, *Count* игнорируется.

Если **wcsrtombs_s** обнаруживает широкий символ, который он не может преобразовать в многобайтовый символ, он помещает-1 в * \*претурнвалуе*, устанавливает в качестве буфера назначения пустую строку **, устанавливает значение** очистки в **еилсек**и возвращает **еилсек**.

Если последовательности, на которые указывает *вкстр* и *мбстр* , перекрываются, поведение **wcsrtombs_s** не определено. **wcsrtombs_s** зависит от категории LC_TYPE текущего языкового стандарта.

> [!IMPORTANT]
> Убедитесь, что *вкстр* и *мбстр* не перекрываются, и что этот *Счетчик* правильно отражает количество расширенных символов для преобразования.

Функция **wcsrtombs_s** отличается от [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) ее перезапуском. Состояние преобразования хранится в *мбстате* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, приложение будет использовать **вксрлен** вместо **wcslen**, если вместо **wcstombs_s**использовался последующий вызов **wcsrtombs_s** .

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="exceptions"></a>Исключения

Функция **wcsrtombs_s** является потокобезопасной, если ни одна из функций в текущем потоке не вызывает **setlocale** во время выполнения этой функции и *мбстате* имеет значение null.

## <a name="example"></a>Пример

```cpp
// crt_wcsrtombs_s.cpp
//
// This code example converts a wide
// character string into a multibyte
// character string.
//

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

int main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    errno_t         err;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);
    if (err == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfully converted.\n" );
    }
}
```

```Output
The string was successfully converted.
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcsrtombs_s**|\<wchar.h>|

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
