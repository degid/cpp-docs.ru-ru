---
title: _getcwd, _wgetcwd
description: Функции библиотеки времени выполнения C _getcwd, _wgetcwd получения текущего рабочего каталога.
ms.date: 4/2/2020
api_name:
- _wgetcwd
- _getcwd
- _o__getcwd
- _o__wgetcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getcwd
- wgetcwd
- _wgetcwd
- tgetcwd
- _tgetcwd
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
ms.openlocfilehash: b6fb32a593a969f93a934f251f38cd50960440b0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221891"
---
# <a name="_getcwd-_wgetcwd"></a>_getcwd, _wgetcwd

Возвращает текущий рабочий каталог.

## <a name="syntax"></a>Синтаксис

```C
char *_getcwd(
   char *buffer,
   int maxlen
);
wchar_t *_wgetcwd(
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>Параметры

*двойной*\
Место хранения пути.

*maxlen*\
Максимальная длина пути в символах: **`char`** для **_getcwd** и **`wchar_t`** для **_wgetcwd**.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на *буфер*. Возвращаемое значение **null** указывает на ошибку, а параметру " **No** @" — на " **еномем** *",* что свидетельствует о нехватке памяти для выделения *maxlen* байт (если аргумент равен **null** ) или значение **ERANGE**, указывающее, что путь длиннее *maxlen* символов. Если *maxlen* меньше или равно нулю, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **_getcwd** возвращает полный путь к текущему рабочему каталогу для диска по умолчанию и сохраняет его в *буфере*. Целочисленный аргумент *maxlen* задает максимальную длину пути. Если длина пути (включая завершающий символ null) превышает *maxlen*, возникает ошибка. Аргумент *buffer* может иметь **значение NULL**. буфер как минимум размера *maxlen* (только при необходимости) автоматически выделяется с помощью **malloc**для хранения пути. Этот буфер можно впоследствии освободить, вызвав **Free** и передав ему **_getcwd** возвращаемое значение (указатель на выделенный буфер).

**_getcwd** возвращает строку, представляющую путь к текущему рабочему каталогу. Если текущий рабочий каталог является корнем, строка заканчивается обратной косой чертой ( `\` ). Если текущий рабочий каталог отличается от корневого, строка заканчивается именем каталога, а не обратной косой чертой.

**_wgetcwd** — это версия **_getcwd**для расширенных символов; Аргумент *буфера* и возвращаемое значение **_wgetcwd** являются строками расширенных символов. в противном случае **_wgetcwd** и **_getcwd** ведут себя одинаково.

Если определены **_DEBUG** и **_CRTDBG_MAP_ALLOC** , вызовы **_getcwd** и **_wgetcwd** заменяются вызовами **_getcwd_dbg** и **_wgetcwd_dbg** , что позволяет выполнять отладку выделения памяти. Дополнительные сведения см. в разделе [_getcwd_dbg, _wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getcwd**|\<direct.h>|
|**_wgetcwd**|\<direct.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getcwd.c
// Compile with: cl /W4 crt_getcwd.c
// This program places the name of the current directory in the
// buffer array, then displays the name of the current directory
// on the screen. Passing NULL as the buffer forces getcwd to allocate
// memory for the path, which allows the code to support file paths
// longer than _MAX_PATH, which are supported by NTFS.

#include <direct.h> // _getcwd
#include <stdlib.h> // free, perror
#include <stdio.h>  // printf
#include <string.h> // strlen

int main( void )
{
   char* buffer;

   // Get the current working directory:
   if ( (buffer = _getcwd( NULL, 0 )) == NULL )
      perror( "_getcwd error" );
   else
   {
      printf( "%s \nLength: %zu\n", buffer, strlen(buffer) );
      free(buffer);
   }
}
```

```Output
C:\Code
```

## <a name="see-also"></a>См. также раздел

[Управление каталогом](../../c-runtime-library/directory-control.md)\
[_chdir, _wchdir](chdir-wchdir.md)\
[_mkdir, _wmkdir](mkdir-wmkdir.md)\
[_rmdir, _wrmdir](rmdir-wrmdir.md)
