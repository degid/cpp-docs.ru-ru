---
title: mbrlen
ms.date: 4/2/2020
api_name:
- mbrlen
- _o_mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrlen
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
ms.openlocfilehash: 2e0e0ec9d92744fc904bae5ac7f91db8049de4cd
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842121"
---
# <a name="mbrlen"></a>mbrlen

Определяют число байтов, необходимое для составления многобайтового символа в текущем языковом стандарте, с возможностью перезапуска в середине многобайтового символа.

## <a name="syntax"></a>Синтаксис

```C
size_t mbrlen(
   const char * str,
   size_t count,
   mbstate_t * mbstate
);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Указатель на следующий байт для проверки в строке многобайтовых символов.

*count*<br/>
Максимальное число байтов для проверки.

*мбстате*<br/>
Указатель на текущее состояние сдвига начального байта *str*.

## <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений:

| Значение | Описание |
|--|--|
| 0 | Следующее или меньшее *число* байтов завершает многобайтовый символ, представляющий широкий символ null. |
| от 1 до *подсчета*включительно | Следующее *число* или меньшее количество байт заполнит допустимый многобайтовый символ. Возвращаемое значение равно количеству байтов, составляющих многобайтовый символ. |
| (size_t)(-2) | Следующее *число* байтов вносит в неполный, но потенциально допустимый многобайтовый символ, и все байты *счетчика* были обработаны. |
| (size_t)(-1) | Произошла ошибка кодирования. Следующее *число* или меньшее количество байт не влияет на полный и допустимый многобайтовый символ. В этом случае для параметра "ЕИЛСЕК" задано значение **", а** состояние преобразования в *мбстате* не указано. |

## <a name="remarks"></a>Примечания

Функция **мбрлен** проверяет максимальное число байтов, начиная *с байта* , на который указывает *str* , для определения числа байтов, необходимых для завершения следующего многобайтового символа, включая любые последовательности сдвигов. Он эквивалентен вызову `mbrtowc(NULL, str, count, &mbstate)` , где *мбстате* является либо предоставленным пользователем объектом **mbstate_t** , либо статическим внутренним объектом, предоставленным библиотекой.

Функция **мбрлен** сохраняет и использует состояние сдвига неполного многобайтового символа в параметре *мбстате* . Это дает **мбрлен** возможность перезапуска в середине многобайтового символа, если это необходимо, изучая максимальное *число* байтов. Если *мбстате* является пустым указателем, **мбрлен** использует внутренний статический объект **mbstate_t** для хранения состояния сдвига. Так как внутренний объект **mbstate_t** не является потокобезопасным, рекомендуется всегда выделять и передавать собственный параметр *мбстате* .

Функция **мбрлен** отличается от [_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md) по его перезапуску. Состояние сдвига сохраняется в *мбстате* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, приложение должно использовать **вксрлен** вместо **wcslen** , если последующий вызов **вксртомбс** используется вместо **wcstombs**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|Неприменимо|Неприменимо|**mbrlen**|Неприменимо|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**mbrlen**|\<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

В этом примере показано, как интерпретация многобайтовых символов зависит от текущей кодовой страницы и демонстрирует возможность возобновления работы **мбрлен**.

```C
// crt_mbrlen.c
// Compile by using: cl crt_mbrlen.c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

size_t Example(const char * pStr)
{
    size_t      charLen = 0;
    size_t      charCount = 0;
    mbstate_t   mbState = {0};

    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&
            charLen != (size_t)-1)
    {
        if (charLen != (size_t)-2) // if complete mbcs char,
        {
            charCount++;
        }
    }
    return (charCount);
}

int main( void )
{
    int         cp;
    size_t      charCount = 0;
    const char  *pSample =
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";

    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);

    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale
    _setmbcp(932); // and Japanese multibyte code page
    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);
}
```

```Output

Code page: 0
é╨éτé¬é╚: Shift-jis hiragana.
Character count: 29

Code page: 932
????: Shift-jis hiragana.
Character count: 25
```

## <a name="see-also"></a>См. также раздел

[Управление строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
