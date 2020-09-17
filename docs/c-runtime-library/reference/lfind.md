---
title: _lfind
ms.date: 4/2/2020
api_name:
- _lfind
- _o__lfind
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
- _lfind
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
ms.openlocfilehash: 4721ba96e145b3c2fde4ce0bb73157bbbcab4dff
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916456"
---
# <a name="_lfind"></a>_lfind

Выполняет линейный поиск указанного ключа. Существует более безопасная версия этой функции; см. раздел [_lfind_s](lfind-s.md).

## <a name="syntax"></a>Синтаксис

```C
void *_lfind(
   const void *key,
   const void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Искомый объект.

*base*<br/>
Указатель на начало данных, где будет производиться поиск.

*number*<br/>
Число элементов массива.

*width*<br/>
Ширина элементов массива.

*равенств*<br/>
Указатель на подпрограмму сравнения. Первый параметр — это указатель на ключ для поиска. Второй параметр — это указатель на элемент массива, который будет сравниваться с ключом.

## <a name="return-value"></a>Возвращаемое значение

Если ключ найден, **_lfind** возвращает указатель на элемент массива в *базовом* массиве, который соответствует *ключу*. Если ключ не найден, **_lfind** возвращает **значение NULL**.

## <a name="remarks"></a>Примечания

Функция **_lfind** выполняет линейный поиск *ключа* значения в массиве *числовых* элементов, каждый из которых имеет *ширину* в байтах. В отличие от **bsearch**, **_lfind** не требует сортировки массива. *Базовый* аргумент — это указатель на базовую часть массива, в котором выполняется поиск. Аргумент *Compare* — это указатель на предоставляемую пользователем подпрограммы, которая сравнивает два элемента массива и возвращает значение, указывающее их связь. **_lfind** вызывает подпрограммы *сравнения* один или несколько раз во время поиска, передавая указатели на два элемента массива при каждом вызове. Подпрограммы *сравнения* должны сравнивать элементы, а затем возвращать ненулевое значение (т. е. элементы различаются) или 0 (это означает, что элементы идентичны).

Эта функция проверяет свои параметры. Если *параметр Compare*, *ключ* или *число* имеет **значение NULL**или *Если Base* имеет **значение NULL** , а *Number* имеет ненулевое значение или если *Width* меньше нуля, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** устанавливается значение, а функция возвращает **значение NULL**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_lfind**|\<search.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_lfind.c
// This program uses _lfind to search a string array
// for an occurrence of "hello".

#include <search.h>
#include <string.h>
#include <stdio.h>

int compare(const void *arg1, const void *arg2 )
{
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );
}

int main( )
{
   char *arr[] = {"Hi", "Hello", "Bye"};
   int n = sizeof(arr) / sizeof(char*);
   char **result;
   char *key = "hello";

   result = (char **)_lfind( &key, arr,
                      &n, sizeof(char *), compare );

   if( result )
      printf( "%s found\n", *result );
   else
      printf( "hello not found!\n" );
}
```

```Output
Hello found
```

## <a name="see-also"></a>См. также раздел

[Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
[qsort](qsort.md)<br/>
