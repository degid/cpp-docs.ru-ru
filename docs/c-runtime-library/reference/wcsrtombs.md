---
title: wcsrtombs
ms.date: 4/2/2020
api_name:
- wcsrtombs
- _o_wcsrtombs
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
- wcsrtombs
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
ms.openlocfilehash: cad31f28c5542a96eae9f144344882b71806052a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910617"
---
# <a name="wcsrtombs"></a>wcsrtombs

Преобразует строку расширенных символов в соответствующее представление многобайтовой строки. Существует более безопасная версия этой функции; см. раздел [wcsrtombs_s](wcsrtombs-s.md).

## <a name="syntax"></a>Синтаксис

```C
size_t wcsrtombs(
   char *mbstr,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcsrtombs(
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Параметры

*мбстр*<br/>
Расположение адреса итоговой преобразованной строки многобайтовых символов.

*вкстр*<br/>
Косвенно указывает на расположение преобразуемой строки расширенных символов.

*count*<br/>
Количество символов для преобразования.

*мбстате*<br/>
Указатель на **mbstate_t** объект состояния преобразования.

## <a name="return-value"></a>Возвращаемое значение

Возвращает число успешно преобразованных байтов, не включая завершающий байт NULL (если имеется); в противном случае — значение -1, если произошла ошибка.

## <a name="remarks"></a>Примечания

Функция **вксртомбс** преобразует строку расширенных символов, начиная с указанного состояния преобразования, содержащегося в *мбстате*, из значений, косвенно указываемых в *вкстр*, в адрес *мбстр*. Преобразование продолжится для каждого символа до тех пор, пока не будет обнаружен несоответствующий символ или если следующий символ превысит предел, содержащийся в параметре *Count*. Если **вксртомбс** обнаруживает символ NULL с расширенными символами (L ' \ 0 ') как до, так и при *подсчете* , он преобразует его в 8-разрядный 0 и останавливается.

Таким словами, Строка многобайтовых символов в *мбстр* завершается нулем, только если **вксртомбс** во время преобразования встречает символ расширенного символа null. Если последовательности, на которые указывает *вкстр* и *мбстр* , перекрываются, поведение **вксртомбс** не определено. на **вксртомбс** влияет Категория LC_TYPE текущего языкового стандарта.

Функция **вксртомбс** отличается от [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) ее перезапуском. Состояние преобразования хранится в *мбстате* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, приложение будет использовать **вксрлен** , а не **wcsnlen**, если последующий вызов **вксртомбс** использовался вместо **wcstombs**.

Если аргумент *мбстр* имеет **значение NULL**, **вксртомбс** возвращает требуемый размер строки назначения в байтах. Если *мбстате* имеет значение null, используется внутреннее **mbstate_t** состояние преобразования. Если для последовательности символов *WCHAR* не задано соответствующее представление многобайтового символа, возвращается значение-1, а **для свойства переводится** значение **еилсек**.

В C++ эта функция имеет шаблонную перегрузку, которая вызывает более новые и безопасные аналоги этой функции. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="exceptions"></a>Исключения

Функция **вксртомбс** является потокобезопасной, если ни одна из функций в текущем потоке не вызывает **setlocale** во время выполнения этой функции, а *мбстате* не равен null.

## <a name="example"></a>Пример

```cpp
// crt_wcsrtombs.cpp
// compile with: /W3
// This code example converts a wide
// character string into a multibyte
// character string.

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
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    countConverted = wcsrtombs(mbString, &wcsIndirectString,
                               MB_BUFFER_SIZE, &mbstate); // C4996
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s
    if (errno == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfuly converted.\n" );
    }
}
```

```Output
The string was successfuly converted.
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcsrtombs**|\<wchar.h>|

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
