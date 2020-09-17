---
title: _chmod, _wchmod
ms.date: 4/2/2020
api_name:
- _chmod
- _wchmod
- _o__chmod
- _o__wchmod
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
- _chmod
- _wchmod
- wchmod
helpviewer_keywords:
- _chmod function
- wchmod function
- file permissions [C++]
- chmod function
- files [C++], changing permissions
- _wchmod function
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
ms.openlocfilehash: b1bc89ce51fff44a847111d68cac8e8b3f58a635
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917004"
---
# <a name="_chmod-_wchmod"></a>_chmod, _wchmod

Изменяет параметры разрешений файла.

## <a name="syntax"></a>Синтаксис

```C
int _chmod( const char *filename, int pmode );
int _wchmod( const wchar_t *filename, int pmode );
```

### <a name="parameters"></a>Параметры

*файлов*<br/>
Имя существующего файла.

*пмоде*<br/>
Настройка разрешений для файла.

## <a name="return-value"></a>Возвращаемое значение

Эти функции возвращают 0, если параметр разрешений успешно изменен. Возвращаемое значение, равное-1, означает сбой. Если не удалось найти указанный файл, для параметра « **еноент**» задается **значение «Ошибка** ». Если параметр является недопустимым **, то** для параметра « **еинвал**» задается значение «ошибка».

## <a name="remarks"></a>Примечания

Функция **_chmod** изменяет параметр разрешений для файла, указанного параметром *filename*. Параметр разрешений управляет чтением и записью в файл. Целочисленное выражение *пмоде* содержит одну или обе следующие константы манифеста, определенные в файле SYS\Stat.h.

| *пмоде* | Значение |
|-|-|
| **\_\_иреад** | Разрешено только чтение. |
| **\_\_иврите** | Разрешена запись. (Если действует, разрешает чтение и запись.) |
| **\_Иреад\_** **&#124; \_s иврите\_** | Разрешены чтение и запись. |

Если заданы обе константы, они соединяются с оператором побитового**\|** или (). Если разрешение на запись не предоставлено, файл остается доступным только для чтения. Обратите внимание на то, что все файлы всегда доступны для чтения; предоставить разрешение только на запись нельзя. Таким же режимом **_S_IWRITE** и **_S_IREAD** \| **_S_IWRITE** эквивалентны.

**_wchmod** — это версия **_chmod**для расширенных символов; Аргумент *filename* для **_wchmod** является строкой расширенных символов. в противном случае **_wchmod** и **_chmod** ведут себя одинаково.

Эта функция проверяет свои параметры. Если *пмоде* не является сочетанием одной из констант манифеста или включает другой набор констант, функция просто игнорирует их. Если параметр *filename* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **,** параметру **еинвал** присваивается значение, а функция возвращает-1.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchmod**|**_chmod**|**_chmod**|**_wchmod**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_chmod**|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|
|**_wchmod**|\<io.h> или \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_chmod.c
// This program uses _chmod to
// change the mode of a file to read-only.
// It then attempts to modify the file.
//

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

// Change the mode and report error or success
void set_mode_and_report(char * filename, int mask)
{
   // Check for failure
   if( _chmod( filename, mask ) == -1 )
   {
      // Determine cause of failure and report.
      switch (errno)
      {
         case EINVAL:
            fprintf( stderr, "Invalid parameter to chmod.\n");
            break;
         case ENOENT:
            fprintf( stderr, "File %s not found\n", filename );
            break;
         default:
            // Should never be reached
            fprintf( stderr, "Unexpected error in chmod.\n" );
       }
   }
   else
   {
      if (mask == _S_IREAD)
        printf( "Mode set to read-only\n" );
      else if (mask & _S_IWRITE)
        printf( "Mode set to read/write\n" );
   }
   fflush(stderr);
}

int main( void )
{

   // Create or append to a file.
   system( "echo /* End of file */ >> crt_chmod.c_input" );

   // Set file mode to read-only:
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );

   system( "echo /* End of file */ >> crt_chmod.c_input " );

   // Change back to read/write:
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );

   system( "echo /* End of file */ >> crt_chmod.c_input " );
}
```

```Output

A line of text.
```

```Output

      A line of text.Mode set to read-only
Access is denied.
Mode set to read/write
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[Функции _stat, _wstat](stat-functions.md)<br/>
