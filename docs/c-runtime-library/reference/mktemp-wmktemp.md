---
title: _mktemp, _wmktemp
ms.date: 4/2/2020
api_name:
- _wmktemp
- _mktemp
- _o__mktemp
- _o__wmktemp
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
helpviewer_keywords:
- _wmktemp function
- _mktemp function
- files [C++], temporary
- tmktemp function
- _tmktemp function
- wmktemp function
- mktemp function
- temporary files [C++]
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
ms.openlocfilehash: 536a63841c6e29fa003eb8b99c896f6d1cf5519f
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919098"
---
# <a name="_mktemp-_wmktemp"></a>_mktemp, _wmktemp

Создает уникальное имя файла. Существуют более безопасные версии этих функций; см. раздел [_mktemp_s, _wmktemp_s](mktemp-s-wmktemp-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *_mktemp(
   char *nameTemplate
);
wchar_t *_wmktemp(
   wchar_t *nameTemplate
);
template <size_t size>
char *_mktemp(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
wchar_t *_wmktemp(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>Параметры

*наметемплате*<br/>
Шаблон имени файла.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на измененный Наметемплате. Функция возвращает **значение NULL** , если *наметемплате* имеет неправильный формат или не может быть создано более уникальных имен из данного наметемплате.

## <a name="remarks"></a>Примечания

Функция **_mktemp** создает уникальное имя файла, изменяя аргумент *наметемплате* . **_mktemp** автоматически обрабатывает строковые аргументы многобайтовых символов соответствующим образом, распознает последовательности многобайтовых символов в соответствии с многобайтовой кодовой страницей, используемой в настоящее время системой выполнения. **_wmktemp** — это версия **_mktemp**для расширенных символов; аргумент и возвращаемое значение **_wmktemp** являются строками расширенных символов. поведение **_wmktemp** и **_mktemp** идентично в других случаях, за исключением того, что **_wmktemp** не обрабатывает строки многобайтовых символов.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

Аргумент *наметемплате* имеет форму с *основанием*XXXXXX, где *base* — это часть нового имени файла, которую вы указали, и каждый X является заполнителем для символа, предоставленного **_mktemp**. Каждый символ заполнителя в *наметемплате* должен быть прописной буквой X. **_mktemp** сохраняет *основу* и заменяет первый замыкающий символ буквой x. **_mktemp** заменяет следующий символ X на значение из пяти цифр; Это значение представляет собой уникальный номер, идентифицирующий вызывающий процесс или в многопоточных программах, вызывающий поток.

Каждый успешный вызов **_mktemp** изменяет *наметемплате*. В каждом последующем вызове из того же процесса или потока с одним и тем же аргументом *наметемплате* **_mktemp** проверяет имена файлов, которые соответствуют именам, возвращаемым **_mktemp** в предыдущих вызовах. Если для данного имени файл не существует, **_mktemp** возвращает это имя. Если файлы существуют для всех ранее возвращенных имен, **_mktemp** создает новое имя, заменяя букву, которая использовалась в ранее возвращенном имени, на следующую доступную строчную букву в порядке от "a" до "z". Например, если *base* имеет значение:

> **FN**

и 5-значным значением, предоставленным **_mktemp** , является 12345, первым возвращенным именем является:

> **fna12345**

Если это имя используется для создания файла FNA12345, а этот файл по-прежнему существует, то следующее имя, возвращаемое при вызове из того же процесса или потока с той же *базой* для *наметемплате* , имеет следующий результат:

> **fnb12345**

Если файл FNA12345 не существует, то опять возвращается следующее имя:

> **fna12345**

**_mktemp** можно создать не более 26 уникальных имен файлов для любой заданной комбинации *базовых* и *наметемплате* значений. Таким образом, FNZ12345 — это Последнее уникальное имя файла, которое **_mktemp** может быть создано для значений *base* и *наметемплате* , используемых в этом примере.

В случае сбоя задается значение « **No No** ». Если *наметемплате* имеет недопустимый формат (например, меньше, чем 6 X **), то** для свойства "значение после" задается **еинвал**. Если **_mktemp** не может создать уникальное имя, так как все 26 возможных имен файлов уже существуют, **_mktemp** устанавливает наметемплате в пустую строку и возвращает **иксист**.

В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mktemp**|\<io.h>|
|**_wmktemp**|\<io.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_mktemp.c
// compile with: /W3
/* The program uses _mktemp to create
* unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>
#include <errno.h>

char *template = "fnXXXXXX";
char *result;
char names[27][9];

int main( void )
{
   int i;
   FILE *fp;

   for( i = 0; i < 27; i++ )
   {
      strcpy_s( names[i], sizeof( names[i] ), template );
      /* Attempt to find a unique filename: */
      result = _mktemp( names[i] );  // C4996
      // Note: _mktemp is deprecated; consider using _mktemp_s instead
      if( result == NULL )
      {
         printf( "Problem creating the template\n" );
         if (errno == EINVAL)
         {
             printf( "Bad parameter\n");
         }
         else if (errno == EEXIST)
         {
             printf( "Out of unique filenames\n");
         }
      }
      else
      {
         fopen_s( &fp, result, "w" );
         if( fp != NULL )
            printf( "Unique filename is %s\n", result );
         else
            printf( "Cannot open %s\n", result );
         fclose( fp );
      }
   }
}
```

```Output
Unique filename is fna03912
Unique filename is fnb03912
Unique filename is fnc03912
Unique filename is fnd03912
Unique filename is fne03912
Unique filename is fnf03912
Unique filename is fng03912
Unique filename is fnh03912
Unique filename is fni03912
Unique filename is fnj03912
Unique filename is fnk03912
Unique filename is fnl03912
Unique filename is fnm03912
Unique filename is fnn03912
Unique filename is fno03912
Unique filename is fnp03912
Unique filename is fnq03912
Unique filename is fnr03912
Unique filename is fns03912
Unique filename is fnt03912
Unique filename is fnu03912
Unique filename is fnv03912
Unique filename is fnw03912
Unique filename is fnx03912
Unique filename is fny03912
Unique filename is fnz03912
Problem creating the template.
Out of unique filenames.
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile](tmpfile.md)<br/>
