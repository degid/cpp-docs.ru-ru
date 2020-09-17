---
title: _locking
ms.date: 4/2/2020
api_name:
- _locking
- _o__locking
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
- _locking
helpviewer_keywords:
- locking function
- bytes [C++], locking file
- files [C++], locking bytes
- files [C++], locking
- _locking function
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
ms.openlocfilehash: c1c211ffaa63a0e4711374b01b0530ed8db20dfb
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911538"
---
# <a name="_locking"></a>_locking

Блокирует или разблокирует байт файла.

## <a name="syntax"></a>Синтаксис

```C
int _locking(
   int fd,
   int mode,
   long nbytes
);
```

### <a name="parameters"></a>Параметры

*демо*<br/>
Дескриптор файла.

*mode*<br/>
Выполняемое действие блокировки.

*nbytes*<br/>
Число байтов для блокировки.

## <a name="return-value"></a>Возвращаемое значение

При успешном выполнении **_locking** возвращает 0. Возвращаемое значение, равное-1, указывает на сбой, в этом случае для параметра «вывод [» задано](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) одно из следующих значений.

|Значение errno|Условие|
|-|-|
| **еакцес** | Нарушение блокировки (файл уже заблокирован или разблокирован). |
| **EBADF** | Недопустимый дескриптор файла. |
| **EDEADLOCK** | Нарушение блокировки. Возвращается, если задан флаг **_LK_LOCK** или **_LK_RLCK** и файл не может быть заблокирован после 10 попыток. |
| **еинвал** | **_Locking**передан недопустимый аргумент. |

Если сбой происходит из-за недопустимого параметра, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>Примечания

Функция **_locking** блокирует или разблокирует *nbytes* байт файла, заданного параметром \ " *демон*\". Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Все блокировки или разблокировки начинаются с текущего положения указателя файла и распространяются на следующие *nbytes* байт. Возможна блокировка байтов за концом файла.

Параметр *mode* должен быть одной из следующих констант манифеста, определенных в файле Locking.h.

|значение *режима*|Действие|
|-|-|
| **_LK_LOCK** | Блокирует указанные байты. Если заблокировать байты не удается, программа попытается повторить блокировку через 1 секунду. Если после 10 попыток байты все равно не удается заблокировать, константа возвращает ошибку. |
| **_LK_NBLCK** | Блокирует указанные байты. Если после 10 попыток байты все равно не удается заблокировать, константа возвращает ошибку. |
| **_LK_NBRLCK** | То же, что и **_LK_NBLCK**. |
| **_LK_RLCK** | То же, что и **_LK_LOCK**. |
| **_LK_UNLCK** | Разблокирует указанные байты, которые предварительно должны быть заблокированы. |

Можно заблокировать несколько разделов файла, которые не перекрываются. Разблокируемый раздел файла должен быть предварительно заблокирован. **_locking** не выполняет слияние смежных областей; Если два заблокированных региона являются смежными, каждый регион должен быть разблокирован отдельно. Разделы следует блокировать только на короткое время. Их необходимо разблокировать перед закрытием файла или выходом из программы.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_locking**|\<io.h> и \<sys/locking.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_locking.c
/* This program opens a file with sharing. It locks
* some bytes before reading them, then unlocks them. Note that the
* program works correctly only if the file exists.
*/

#include <sys/types.h>
#include <sys/stat.h>
#include <sys/locking.h>
#include <share.h>
#include <fcntl.h>
#include <stdio.h>
#include <stdlib.h>
#include <io.h>

int main( void )
{
   int  fh, numread;
   char buffer[40];

   /* Quit if can't open file or system doesn't
    * support sharing.
    */
   errno_t err = _sopen_s( &fh, "crt_locking.txt", _O_RDONLY, _SH_DENYNO,
                          _S_IREAD | _S_IWRITE );
   printf( "%d %d\n", err, fh );
   if( err != 0 )
      exit( 1 );

   /* Lock some bytes and read them. Then unlock. */
   if( _locking( fh, LK_NBLCK, 30L ) != -1 )
   {
      long lseek_ret;
      printf( "No one can change these bytes while I'm reading them\n" );
      numread = _read( fh, buffer, 30 );
      buffer[30] = '\0';
      printf( "%d bytes read: %.30s\n", numread, buffer );
      lseek_ret = _lseek( fh, 0L, SEEK_SET );
      _locking( fh, LK_UNLCK, 30L );
      printf( "Now I'm done. Do what you will with them\n" );
   }
   else
      perror( "Locking failed\n" );

   _close( fh );
}
```

### <a name="input-crt_lockingtxt"></a>Входные данные: crt_locking.txt

```Input
The first thirty bytes of this file will be locked.
```

## <a name="sample-output"></a>Пример выходных данных

```Output
No one can change these bytes while I'm reading them
30 bytes read: The first thirty bytes of this
Now I'm done. Do what you will with them
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
