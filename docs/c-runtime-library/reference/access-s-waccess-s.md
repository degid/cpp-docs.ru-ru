---
title: _access_s, _waccess_s
ms.date: 4/2/2020
api_name:
- _access_s
- _waccess_s
- _o__access_s
- _o__waccess_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- waccess_s
- access_s
- _waccess_s
- _access_s
helpviewer_keywords:
- access_s function
- taccess_s function
- _taccess_s function
- waccess_s function
- _access_s function
- _waccess_s function
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
ms.openlocfilehash: c3893b3d78a2c142ffc9e10eb6bbf299c5fddb9b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916896"
---
# <a name="_access_s-_waccess_s"></a>_access_s, _waccess_s

Определяет разрешения на чтение и запись файлов. Это — версия функций [_access, _waccess](access-waccess.md) с усовершенствованиями системы безопасности, описанными в разделе [Возможности безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _access_s(
   const char *path,
   int mode
);
errno_t _waccess_s(
   const wchar_t *path,
   int mode
);
```

### <a name="parameters"></a>Параметры

*path*<br/>
Путь к файлу или каталогу.

*mode*<br/>
Настройка разрешений.

## <a name="return-value"></a>Возвращаемое значение

Если файл имеет заданный режим, все функции возвращают значение 0. Если указанный файл не существует или недоступен в заданном режиме, функция возвращает код ошибки. Код ошибки выбирается из набора описанным ниже образом и присваивает `errno` такое же значение.

|Значение errno|Условие|
|-|-|
`EACCES`|Access denied. (Недопустимое значение {значение_утверждения} для утверждения {имя_утверждения}. Доступ запрещен.) Настройка разрешений файла не допускает указанный доступ.
`ENOENT`|Имя файла или путь не найдены.
`EINVAL`|Недопустимый параметр.

Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

При использовании с файлами Функция **_access_s** определяет, существует ли указанный файл, и доступ к нему можно получить, как указано в параметре *mode*. При использовании с каталогами **_access_s** определяет, существует ли указанный каталог. В операционных системах Windows 2000 и более поздних версий все каталоги имеют доступ на чтение и запись.

|значение режима|Проверяет файл на|
|----------------|---------------------|
|00|Существование.|
|02|Разрешение на запись.|
|04|Разрешение на чтение.|
|06|Разрешение на чтение и запись.|

Сами по себе разрешения на чтение или запись файла не обеспечивают возможность открывать файл. Например, если файл заблокирован другим процессом, он может быть недоступен, хотя **_access_s** возвращает 0.

**_waccess_s** — это версия **_access_s**для расширенных символов, где аргумент *пути* к **_waccess_s** является строкой расширенных символов. В противном случае **_waccess_s** и **_access_s** ведут себя одинаково.

Эти функции проверяют свои параметры. Если параметр *path* имеет значение null или *режим* не указывает допустимый режим, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `EINVAL`.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess_s`|**_access_s**|**_access_s**|**_waccess_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_access_s**|\<io.h>|\<errno.h>|
|**_waccess_s**|\<wchar.h> или \<io.h>|\<errno.h>|

## <a name="example"></a>Пример

В этом примере используется **_access_s** для проверки файла с именем crt_access_s. c, чтобы узнать, существует ли он и разрешена ли запись.

```C
// crt_access_s.c

#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
    errno_t err = 0;

    // Check for existence.
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )
    {
        printf_s( "File crt_access_s.c exists.\n" );

        // Check for write permission.
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )
        {
            printf_s( "File crt_access_s.c does have "
                      "write permission.\n" );
        }
        else
        {
            printf_s( "File crt_access_s.c does not have "
                      "write permission.\n" );
        }
    }
    else
    {
        printf_s( "File crt_access_s.c does not exist.\n" );
    }
}
```

```Output
File crt_access_s.c exists.
File crt_access_s.c does not have write permission.
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[Функции _stat, _wstat](stat-functions.md)
