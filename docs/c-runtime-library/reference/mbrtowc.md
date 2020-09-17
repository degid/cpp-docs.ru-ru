---
title: mbrtowc
ms.date: 4/2/2020
api_name:
- mbrtowc
- _o_mbrtowc
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
- mbrtowc
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
ms.openlocfilehash: 55d866e6f0e372c148de36bf259954bed11a953c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229432"
---
# <a name="mbrtowc"></a>mbrtowc

Преобразуют многобайтовый символ в текущем языковом стандарте в эквивалентный расширенный символ с возможностью перезапуска в середине многобайтового символа.

## <a name="syntax"></a>Синтаксис

```C
size_t mbrtowc(
   wchar_t *wchar,
   const char *mbchar,
   size_t count,
   mbstate_t *mbstate
);
```

### <a name="parameters"></a>Параметры

*WCHAR*<br/>
Адрес расширенного символа для получения преобразованной строки расширенных символов (тип **`wchar_t`** ). Это значение может быть пустым указателем, если не требуется возвращать расширенный символ.

*мбчар*<br/>
Адрес последовательности байтов (многобайтовый символ).

*count*<br/>
Число проверяемых байтов.

*мбстате*<br/>
Указатель на объект состояния преобразования. Если это значение является пустым указателем, функция использует статичный внутренний объект состояния преобразования. Так как внутренний объект **mbstate_t** не является потокобезопасным, рекомендуется всегда передавать собственный аргумент *мбстате* .

## <a name="return-value"></a>Возвращаемое значение

Принимает одно из следующих значений:

0 следующее *число* или меньше байтов заполнит многобайтовый символ, представляющий расширенный символ null, который хранится в параметре *WCHAR*, если *WCHAR* не является пустым указателем.

1 для *подсчета*, включая следующее или меньшее *число* байтов, заполнит допустимый многобайтовый символ. Возвращаемое значение равно количеству байтов, составляющих многобайтовый символ. Эквивалент расширенного символа хранится в *WCHAR*, если *WCHAR* не является пустым указателем.

(size_t) (-1) Произошла ошибка кодирования. Следующее *число* или меньшее количество байт не влияет на полный и допустимый многобайтовый символ. В этом случае для параметра "ЕИЛСЕК" задано значение **", а** состояние сдвига преобразования в *мбстате* не указано.

(size_t) (-2) Следующее *число* байтов вносит в неполный, но потенциально допустимый многобайтовый символ, и все байты *счетчика* были обработаны. Значение *WCHAR*не хранится, но *мбстате* обновляется для перезапуска функции.

## <a name="remarks"></a>Примечания

Если *мбчар* является пустым указателем, функция эквивалентна вызову:

`mbrtowc(NULL, "", 1, &mbstate)`

В этом случае значения аргументов *WCHAR* и *Count* игнорируются.

Если *мбчар* не является пустым указателем, функция проверяет число байтов из *мбчар* , чтобы определить необходимое *число байтов,* необходимых для завершения следующего многобайтового символа. Если следующий символ допустим, соответствующий многобайтовый символ хранится в *WCHAR* , если он не является пустым указателем. Если символ соответствует расширенному значению NULL, полученное состояние *мбстате* является начальным состоянием преобразования.

Функция **мбртовк** отличается от [mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md) ее перезапуском. Состояние преобразования хранится в *мбстате* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, приложение должно использовать **вксрлен** вместо **wcslen** , если последующий вызов **вксртомбс** используется вместо **wcstombs**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="example"></a>Пример

Преобразует многобайтовый символ в эквивалентный расширенный символ.

```cpp
// crt_mbrtowc.cpp

#include <stdio.h>
#include <mbctype.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

#define BUF_SIZE 100

int Sample(char* szIn, wchar_t* wcOut, int nMax)
{
    mbstate_t   state = {0}; // Initial state
    size_t      nConvResult,
                nmbLen = 0,
                nwcLen = 0;
    wchar_t*    wcCur = wcOut;
    wchar_t*    wcEnd = wcCur + nMax;
    const char* mbCur = szIn;
    const char* mbEnd = mbCur + strlen(mbCur) + 1;
    char*       szLocal;

    // Sets all locale to French_Canada.1252
    szLocal = setlocale(LC_ALL, "French_Canada.1252");
    if (!szLocal)
    {
        printf("The fuction setlocale(LC_ALL, \"French_Canada.1252\") failed!\n");
        return 1;
    }

    printf("Locale set to: \"%s\"\n", szLocal);

    // Sets the code page associated current locale's code page
    // from a previous call to setlocale.
    if (_setmbcp(_MB_CP_SBCS) == -1)
    {
        printf("The fuction _setmbcp(_MB_CP_SBCS) failed!");
        return 1;
    }

    while ((mbCur < mbEnd) && (wcCur < wcEnd))
    {
        //
        nConvResult = mbrtowc(wcCur, mbCur, 1, &state);
        switch (nConvResult)
        {
            case 0:
            {  // done
                printf("Conversion succeeded!\nMultibyte String: ");
                printf(szIn);
                printf("\nWC String: ");
                wprintf(wcOut);
                printf("\n");
                mbCur = mbEnd;
                break;
            }

            case -1:
            {  // encoding error
                printf("The call to mbrtowc has detected an encoding error.\n");
                mbCur = mbEnd;
                break;
            }

            case -2:
            {  // incomplete character
                if   (!mbsinit(&state))
                {
                    printf("Currently in middle of mb conversion, state = %x\n", state);
                    // state will contain data regarding lead byte of mb character
                }

                ++nmbLen;
                ++mbCur;
                break;
            }

            default:
            {
                if   (nConvResult > 2) // The multibyte should never be larger than 2
                {
                    printf("Error: The size of the converted multibyte is %d.\n", nConvResult);
                }

                ++nmbLen;
                ++nwcLen;
                ++wcCur;
                ++mbCur;
            break;
            }
        }
    }

   return 0;
}

int main(int argc, char* argv[])
{
    char    mbBuf[BUF_SIZE] = "AaBbCc\x9A\x8B\xE0\xEF\xF0xXyYzZ";
    wchar_t wcBuf[BUF_SIZE] = {L''};

    return Sample(mbBuf, wcBuf, BUF_SIZE);
}
```

### <a name="sample-output"></a>Пример выходных данных

```Output
Locale set to: "French_Canada.1252"
Conversion succeeded!
Multibyte String: AaBbCcÜïα∩≡xXyYzZ
WC String: AaBbCcÜïα∩≡xXyYzZ
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**mbrtowc**|\<wchar.h>|

## <a name="see-also"></a>См. также статью

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
