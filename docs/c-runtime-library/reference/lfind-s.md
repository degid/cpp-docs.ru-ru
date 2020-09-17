---
title: _lfind_s
ms.date: 4/2/2020
api_name:
- _lfind_s
- _o__lfind_s
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
- api-ms-win-crt-utility-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- lfind_s
- _lfind_s
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
ms.openlocfilehash: 589a413c9f1fb49fbfe8cd1b5eacb9d452716523
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916506"
---
# <a name="_lfind_s"></a>_lfind_s

Выполняет линейный поиск указанного ключа. Версия функции [_lfind](lfind.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
void *_lfind_s(
   const void *key,
   const void *base,
   unsigned int *num,
   size_t size,
   int (__cdecl *compare)(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Искомый объект.

*base*<br/>
Указатель на начало данных, где будет производиться поиск.

*number*<br/>
Число элементов массива.

*size*<br/>
Размер элементов массива в байтах.

*равенств*<br/>
Указатель на подпрограмму сравнения. Первый параметр — это указатель *контекста* . Второй параметр — это указатель на ключ для поиска. Третий параметр — это указатель на элемент массива, который будет сравниваться с ключом.

*context*<br/>
Указатель на объект, доступ к которому может получить функция сравнения.

## <a name="return-value"></a>Возвращаемое значение

Если ключ найден, **_lfind_s** возвращает указатель на элемент массива в *базовом* массиве, который соответствует *ключу*. Если ключ не найден, **_lfind_s** возвращает **значение NULL**.

Если функции передаются недопустимые параметры, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** устанавливается значение, а функция возвращает **значение NULL**.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|ключ|base;|compare|num|размер;|errno|
|---------|----------|-------------|---------|----------|-----------|
|**ЗАКАНЧИВАЮЩ**|any|any|any|any|**еинвал**|
|any|**ЗАКАНЧИВАЮЩ**|any|!= 0|any|**еинвал**|
|any|any|any|any|нуль|**еинвал**|
|any|any|**ЗАКАНЧИВАЮЩ**|любой|any|**еинвал**|

## <a name="remarks"></a>Примечания

Функция **_lfind_s** выполняет линейный поиск *ключа* значения в массиве *числовых* элементов, каждый из которых имеет *ширину* в байтах. В отличие от **bsearch_s**, **_lfind_s** не требует сортировки массива. *Базовый* аргумент — это указатель на базовую часть массива, в котором выполняется поиск. Аргумент *Compare* — это указатель на предоставляемую пользователем подпрограммы, которая сравнивает два элемента массива и возвращает значение, указывающее их связь. **_lfind_s** вызывает подпрограммы *сравнения* один или несколько раз во время поиска, передавая указатель *контекста* и указатели на два элемента массива при каждом вызове. Подпрограммы *сравнения* должны сравнивать элементы и возвращать ненулевое значение (т. е. элементы отличаются) или 0 (это означает, что элементы идентичны).

**_lfind_s** похож на **_lfind** , за исключением добавления указателя *контекста* к аргументам функции сравнения и списка параметров функции. Указатель *контекста* может быть полезен, если искомая структура данных является частью объекта, а функция *сравнения* должна обращаться к членам объекта. Функция *Compare* может привести указатель void к соответствующему типу объекта и получить доступ к членам этого объекта. Добавление параметра *контекста* делает **_lfind_s** более безопасным, поскольку можно использовать дополнительный контекст, чтобы избежать ошибок повторного входа, связанных с использованием статических переменных, чтобы сделать данные доступными для функции *сравнения* .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_lfind_s**|\<search.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```cpp
// crt_lfind_s.cpp
// This program uses _lfind_s to search a string array,
// passing a locale as the context.
// compile with: /EHsc
#include <stdlib.h>
#include <stdio.h>
#include <search.h>
#include <process.h>
#include <locale.h>
#include <locale>
#include <windows.h>
using namespace std;

// The sort order is dependent on the code page.  Use 'chcp' at the
// command line to change the codepage.  When executing this application,
// the command prompt codepage must match the codepage used here:

#define CODEPAGE_850

#ifdef CODEPAGE_850
// Codepage 850 is the OEM codepage used by the command line,
// so \x00e1 is the German Sharp S

char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };

#define GERMAN_LOCALE "German_Germany.850"

#endif

#ifdef CODEPAGE_1252
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df
   // for the German Sharp S
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };

#define GERMAN_LOCALE "German_Germany.1252"

#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making it vulnerable to thread conflicts
// (if this were a multithreaded program).

int compare( void *pvlocale, const void *str1, const void *str2)
{
    char *s1 = *(char**)str1;
    char *s2 = *(char**)str2;

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(
       s1, s1+strlen(s1),
       s2, s2+strlen(s2) );
}

void find_it( char *key, char *array[], unsigned int num, locale &loc )
{
   char **result = (char **)_lfind_s( &key, array,
                      &num, sizeof(char *), compare, &loc );
   if( result )
      printf( "%s found\n", *result );
   else
      printf( "%s not found\n", key );
}

int main( )
{
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );
}
```

```Output
weit found
```

## <a name="see-also"></a>См. также раздел

[Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort_s](qsort-s.md)<br/>
[_lfind](lfind.md)<br/>
