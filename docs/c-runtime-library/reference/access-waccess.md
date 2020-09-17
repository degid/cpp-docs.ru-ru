---
title: _access, _waccess
ms.date: 4/2/2020
api_name:
- _access
- _waccess
- _o__access
- _o__waccess
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
- _waccess
- _access
- taccess
- waccess
- _taccess
helpviewer_keywords:
- access function
- _taccess function
- waccess function
- _access function
- _waccess function
- taccess function
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
ms.openlocfilehash: fdada7f02115f44aa6a7e3c5e9bdfdf5e65f8b2f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846593"
---
# <a name="_access-_waccess"></a>_access, _waccess

Определяет, доступен ли файл только для чтения или нет. Существуют более безопасные версии этих функций; см. раздел [_access_s, _waccess_s](access-s-waccess-s.md).

## <a name="syntax"></a>Синтаксис

```C
int _access(
   const char *path,
   int mode
);
int _waccess(
   const wchar_t *path,
   int mode
);
```

### <a name="parameters"></a>Параметры

*путь*<br/>
Путь к файлу или каталогу.

*mode*<br/>
Атрибут чтения и записи.

## <a name="return-value"></a>Возвращаемое значение

Если файл имеет заданный режим, все функции возвращают значение 0. Функция возвращает значение-1, если именованный файл не существует или не имеет заданного режима. в этом случае `errno` задается, как показано в следующей таблице.

| Значение | Описание |
|--|--|
| `EACCES` | Доступ запрещен: настройка разрешений файла не допускает указанный доступ. |
| `ENOENT` | Имя файла или путь не найдены. |
| `EINVAL` | Недопустимый параметр. |

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

При использовании с файлами Функция **_access** определяет, существует ли указанный файл или каталог, и содержит атрибуты, заданные в параметре *mode*. При использовании с каталогами **_access** определяет, существует ли указанный каталог. в операционных системах Windows 2000 и более поздних версий все каталоги имеют доступ на чтение и запись.

|значение *режима*|Проверяет файл на|
|------------------|---------------------|
|00|Существование|
|02|Только на запись|
|04|Только для чтения|
|06|Чтение и запись|

Эта функция проверяет только то, является ли файл или каталог доступным только для чтения; параметры безопасности файловой системы не проверяются. Для этого требуется токен доступа. Дополнительные сведения о безопасности файловой системы см. в разделе [Токены доступа](/windows/win32/SecAuthZ/access-tokens). Для использования этой функции предназначен класс ATL, см. раздел [Класс CAccessToken](../../atl/reference/caccesstoken-class.md).

**_waccess** — это версия **_access**для расширенных символов; Аргумент *пути* к **_waccess** является строкой расширенных символов. в противном случае **_waccess** и **_access** ведут себя одинаково.

Эта функция проверяет свои параметры. Если параметр *path* имеет значение null или *режим* не указывает допустимый режим, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция устанавливает параметр `errno` в значение `EINVAL` и возвращает –1.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess`|**_access**|**_access**|**_waccess**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательные заголовки|
|-------------|---------------------|----------------------|
|**_access**|\<io.h>|\<errno.h>|
|**_waccess**|\<wchar.h> или \<io.h>|\<errno.h>|

## <a name="example"></a>Пример

В следующем примере используется **_access** для проверки файла с именем crt_ACCESS. C, чтобы определить, существует ли он и разрешена ли запись.

```C
// crt_access.c
// compile with: /W1
// This example uses _access to check the file named
// crt_ACCESS.C to see if it exists and if writing is allowed.

#include  <io.h>
#include  <stdio.h>
#include  <stdlib.h>

int main( void )
{
    // Check for existence.
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )
    {
        printf_s( "File crt_ACCESS.C exists.\n" );

        // Check for write permission.
        // Assume file is read-only.
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );
    }
}
```

```Output
File crt_ACCESS.C exists.
File crt_ACCESS.C does not have write permission.
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[Функции _stat, _wstat](stat-functions.md)
