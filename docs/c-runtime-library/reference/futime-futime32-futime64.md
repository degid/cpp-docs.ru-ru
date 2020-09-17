---
title: _futime, _futime32, _futime64
ms.date: 4/2/2020
api_name:
- _futime64
- _futime32
- _futime
- _o__futime32
- _o__futime64
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- futime
- _futime
- futime64
- _futime64
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
ms.openlocfilehash: 615e436abf9d763e73d26db61d9063d5e586232b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909915"
---
# <a name="_futime-_futime32-_futime64"></a>_futime, _futime32, _futime64

Задает время изменения открытого файла.

## <a name="syntax"></a>Синтаксис

```C
int _futime(
   int fd,
   struct _utimbuf *filetime
);
int _futime32(
   int fd,
   struct __utimbuf32 *filetime
);
int _futime64(
   int fd,
   struct __utimbuf64 *filetime
);
```

### <a name="parameters"></a>Параметры

*демо*<br/>
Дескриптор открытого файла.

*значения*<br/>
Указатель на структуру, содержащую новую дату изменения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха. Если возникает ошибка, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает значение-1 **, а** параметру переводится в **значение EBADF**, что указывает на недопустимый дескриптор файла или **еинвал**, что указывает на недопустимый параметр.

## <a name="remarks"></a>Примечания

**_Futime** подпрограммы задает дату изменения и время доступа к открытому файлу, связанному с *демоном*. **_futime** идентичен [_utime](utime-utime32-utime64-wutime-wutime32-wutime64.md), за исключением того, что его аргумент является дескриптором открытого файла, а не именем файла или путем к файлу. Структура **_utimbuf** содержит поля для новой даты изменения и времени доступа. Оба поля должны содержать допустимые значения. **_utimbuf32** и **_utimbuf64** идентичны **_utimbuf** за исключением использования 32-разрядных и 64-разрядных типов времени соответственно. **_futime** и **_utimbuf** используют 64-разрядный тип времени и **_futime** идентичны в поведении **_futime64**. Если необходимо принудительно выполнить старое поведение, определите **_USE_32BIT_TIME_T**. Это приведет к тому, что **_futime** будут идентичными в поведении **_futime32** и приводит к тому, что в структуре **_utimbuf** будет использоваться 32-разрядный тип времени, что делает его эквивалентным **__utimbuf32**.

**_futime64**, которая использует структуру **__utimbuf64** , может считывать и изменять даты файлов до 23:59:59, 31 декабря 3000, UTC; в то время как вызов **_futime32** завершается ошибкой, если дата файла позже 23:59:59 января 2038, в формате UTC. Полночь 1-го января 1970 года — нижняя граница диапазона дат для этих функций.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**_futime**|\<sys/utime.h>|\<errno.h>|
|**_futime32**|\<sys/utime.h>|\<errno.h>|
|**_futime64**|\<sys/utime.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_futime.c
// This program uses _futime to set the
// file-modification time to the current time.

#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <io.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <sys/utime.h>
#include <share.h>

int main( void )
{
   int hFile;

   // Show file time before and after.
   system( "dir crt_futime.c_input" );

   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );

   if( _futime( hFile, NULL ) == -1 )
      perror( "_futime failed\n" );
   else
      printf( "File time modified\n" );

   _close (hFile);

   system( "dir crt_futime.c_input" );
}
```

### <a name="input-crt_futimec_input"></a>Входные данные: crt_futime.c_input

```Input
Arbitrary file contents.
```

### <a name="sample-output"></a>Пример выходных данных

```Output
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:40 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:41 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
File time modified
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
