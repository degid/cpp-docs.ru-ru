---
title: ':::no-loc(strtol):::, :::no-loc(wcstol):::, :::no-loc(_strtol_l):::, :::no-loc(_wcstol_l):::'
ms.date: 4/2/2020
api_name:
- ':::no-loc(strtol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_wcstol_l):::'
- '_o_:::no-loc(_strtol_l):::'
- '_o_:::no-loc(_wcstol_l):::'
- '_o_:::no-loc(strtol):::'
- '_o_:::no-loc(wcstol):::'
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
- ':::no-loc(_wcstol_l):::'
- ':::no-loc(strtol):::'
- ':::no-loc(_tcstol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_tcstol_l):::'
helpviewer_keywords:
- ':::no-loc(wcstol)::: function'
- :::no-loc(wcstol):::_l function
- ':::no-loc(_tcstol)::: function'
- string conversion, to integers
- tcstol function
- :::no-loc(strtol):::_l function
- ':::no-loc(_wcstol_l)::: function'
- ':::no-loc(_strtol_l)::: function'
- ':::no-loc(strtol)::: function'
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
no-loc:
- ':::no-loc(strtol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_wcstol_l):::'
- ':::no-loc(LONG_MAX):::'
- ':::no-loc(LONG_MIN):::'
- ':::no-loc(errno):::'
- ':::no-loc(ERANGE):::'
- ':::no-loc(EINVAL):::'
- ':::no-loc(LC_NUMERIC):::'
- ':::no-loc(_tcstol):::'
- ':::no-loc(_tcstol_l):::'
- ':::no-loc(localeconv):::'
- ':::no-loc(setlocale):::'
- ':::no-loc(_wsetlocale):::'
- ':::no-loc(strtod):::'
- ':::no-loc(_strtod_l):::'
- ':::no-loc(wcstod):::'
- ':::no-loc(_wcstod_l):::'
- ':::no-loc(strtoll):::'
- ':::no-loc(_strtoll_l):::'
- ':::no-loc(wcstoll):::'
- ':::no-loc(_wcstoll_l):::'
- ':::no-loc(strtoul):::'
- ':::no-loc(_strtoul_l):::'
- ':::no-loc(wcstoul):::'
- ':::no-loc(_wcstoul_l):::'
- ':::no-loc(atof):::'
- ':::no-loc(_atof_l):::'
- ':::no-loc(_wtof):::'
- ':::no-loc(_wtof_l):::'
ms.openlocfilehash: a5265b434f14f299532d6f5ebb65c83d75ea63ca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232408"
---
# <a name="no-locstrtol-no-locwcstol-no-loc_strtol_l-no-loc_wcstol_l"></a>:::no-loc(strtol):::, :::no-loc(wcstol):::, :::no-loc(_strtol_l):::, :::no-loc(_wcstol_l):::

Преобразование строк в **`long`** целочисленное значение.

## <a name="syntax"></a>Синтаксис

```C
long :::no-loc(strtol):::(
   const char *string,
   char **end_ptr,
   int base
);
long :::no-loc(wcstol):::(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base
);
long :::no-loc(_strtol_l):::(
   const char *string,
   char **end_ptr,
   int base,
   _locale_t locale
);
long :::no-loc(_wcstol_l):::(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*Строка*\
Строка, завершающаяся символом NULL, для преобразования.

*end_ptr*\
Выходной параметр, заданный для указания символа после последнего интерпретируемого символа. Игнорируется, если **значение равно NULL**.

*из*\
Используемое числовое основание.

*языкового стандарта*\
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**:::no-loc(strtol):::**, **:::no-loc(wcstol):::** , **:::no-loc(_strtol_l):::** и **:::no-loc(_wcstol_l):::** возвращают значение, представленное в виде *строки*. Они возвращают 0, если преобразование невозможно. Если представление вызовет переполнение, они возвращают **:::no-loc(LONG_MAX):::** или **:::no-loc(LONG_MIN):::** .

**:::no-loc(errno):::** имеет значение, **:::no-loc(ERANGE):::** Если происходит переполнение или потеря значимости. Он имеет значение, **:::no-loc(EINVAL):::** Если *строка* имеет **значение NULL**. Или, если значение *base* не равно нулю и меньше 2 или больше 36. Дополнительные сведения о **:::no-loc(ERANGE):::** , **:::no-loc(EINVAL):::** и других кодах возврата см. в разделе [_dos :::no-loc(errno)::: , :::no-loc(errno)::: , _sys_errlist и _sys_nerr](../../c-runtime-library/:::no-loc(errno):::-dos:::no-loc(errno):::-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**:::no-loc(strtol):::** Функции, **:::no-loc(wcstol):::** , **:::no-loc(_strtol_l):::** и **:::no-loc(_wcstol_l):::** преобразуют *строку* в **`long`** . Они прекращают чтение *строки* с первого символа, который не распознается как часть числа. Это может быть завершающий символ null или первый буквенно-цифровой символ, который больше или равен *base*.

**:::no-loc(wcstol):::** и **:::no-loc(_wcstol_l):::** — это версии и для расширенных символов **:::no-loc(strtol):::** **:::no-loc(_strtol_l):::** . Их *строковый* аргумент является строкой расширенных символов. Эти функции ведут себя одинаково в **:::no-loc(strtol):::** и **:::no-loc(_strtol_l):::** иным образом. Параметр категории языкового стандарта **:::no-loc(LC_NUMERIC):::** определяет распознавание символа системы счисления (маркер дробной части или десятичной запятой) в *строке*. Функции **:::no-loc(strtol):::** и **:::no-loc(wcstol):::** используют текущий языковой стандарт. **:::no-loc(_strtol_l):::** и **:::no-loc(_wcstol_l):::** использовать переданный языковой стандарт. Дополнительные сведения см. в разделе [ :::no-loc(setlocale)::: ] и [языковой стандарт](../../c-runtime-library/locale.md).

Если *end_ptr* имеет **значение NULL**, он игнорируется. В противном случае указатель на символ, который остановил просмотр, хранится в расположении, на которое указывает *end_ptr*. Преобразование невозможно, если не найдены допустимые цифры или указан недопустимый базовый. Затем значение *строки* сохраняется в расположении, на которое указывает *end_ptr*.

**:::no-loc(strtol):::***строка* должна указывать на строку следующего вида:

> [*пробел*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*буквенно-цифровые символы*]

Квадратные скобки ( `[ ]` ) окружают необязательные элементы. Фигурные скобки и вертикальная черта ( `{ | }` ) заключить альтернативные варианты для одного элемента. *пробелы* могут состоять из пробелов и символов табуляции, которые игнорируются. *буквенно-цифровые* буквы являются десятичными цифрами или буквами от a до z (или от a до z). Первый символ, который не соответствует этой форме, останавливает проверку. Если значение *base* — от 2 до 36, то оно используется в качестве основания для числа. Если значение *base* равно 0, начальные символы строки, на которую указывает *строка* , используются для определения базового объекта. Если первый символ равен 0, а второй символ — не "x" или "X", строка интерпретируется как восьмеричное целое число. Если первый символ — 0, а второй символ равен x или X, строка интерпретируется как шестнадцатеричное целое число. Если первый символ — от 1 до 9, строка интерпретируется как десятичное целое число. Буквам от "a" до "z" (или от "A" до "Z") присваиваются значения от 10 до 35. Сканирование допускает только те буквы, значения которых меньше *базового*. Первый символ за пределами диапазона основания останавливает сканирование. Например, предположим, что *строка* начинается с «01». Если значение *base* равно 0, то средство проверки предполагает, что это восьмеричное целое число. Символ "8" или "9" останавливает сканирование.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**:::no-loc(_tcstol):::**|**:::no-loc(strtol):::**|**:::no-loc(strtol):::**|**:::no-loc(wcstol):::**|
|**:::no-loc(_tcstol_l):::**|**:::no-loc(_strtol_l):::**|**:::no-loc(_strtol_l):::**|**:::no-loc(_wcstol_l):::**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**:::no-loc(strtol):::**|\<stdlib.h>|
|**:::no-loc(wcstol):::**|\<stdlib.h> или \<wchar.h>|
|**:::no-loc(_strtol_l):::**|\<stdlib.h>|
|**:::no-loc(_wcstol_l):::**|\<stdlib.h> или \<wchar.h>|

**:::no-loc(_strtol_l):::** Функции и **:::no-loc(_wcstol_l):::** являются специфичными для Microsoft, а не частью стандартной библиотеки C. Дополнительные сведения о совместимости см. в статье [Compatibility](../compatibility.md).

## <a name="example"></a>Пример

См. пример для [:::no-loc(strtod):::](:::no-loc(strtod):::-:::no-loc(strtod):::-l-:::no-loc(wcstod):::-:::no-loc(wcstod):::-l.md) .

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../data-conversion.md)\
[Языкового стандарта](../locale.md)\
[:::no-loc(localeconv):::](:::no-loc(localeconv):::.md)\
[:::no-loc(setlocale):::, :::no-loc(_wsetlocale):::](:::no-loc(setlocale):::-w:::no-loc(setlocale):::.md)\
[Функции типа "строка — числовое значение"](../string-to-numeric-value-functions.md)\
[:::no-loc(strtod):::, :::no-loc(_strtod_l):::, :::no-loc(wcstod):::, :::no-loc(_wcstod_l):::](:::no-loc(strtod):::-:::no-loc(strtod):::-l-:::no-loc(wcstod):::-:::no-loc(wcstod):::-l.md)\
[:::no-loc(strtoll):::, :::no-loc(_strtoll_l):::, :::no-loc(wcstoll):::, :::no-loc(_wcstoll_l):::](:::no-loc(strtoll):::-:::no-loc(strtoll):::-l-:::no-loc(wcstoll):::-:::no-loc(wcstoll):::-l.md)\
[:::no-loc(strtoul):::, :::no-loc(_strtoul_l):::, :::no-loc(wcstoul):::, :::no-loc(_wcstoul_l):::](:::no-loc(strtoul):::-:::no-loc(strtoul):::-l-:::no-loc(wcstoul):::-:::no-loc(wcstoul):::-l.md)\
[:::no-loc(atof):::, :::no-loc(_atof_l):::, :::no-loc(_wtof):::, :::no-loc(_wtof_l):::](:::no-loc(atof):::-:::no-loc(atof):::-l-wtof-wtof-l.md)
