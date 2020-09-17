---
title: _read
ms.date: 4/2/2020
api_name:
- _read
- _o__read
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
- _read
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
ms.openlocfilehash: 2f43fc54a0092afc6ab5855c160a7879747faef7
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919515"
---
# <a name="_read"></a>_read

Считывает данные из файла.

## <a name="syntax"></a>Синтаксис

```C
int _read(
   int const fd,
   void * const buffer,
   unsigned const buffer_size
);
```

### <a name="parameters"></a>Параметры

*демо*<br/>
Дескриптор файла, ссылающийся на открытый файл.

*двойной*<br/>
Место хранения данных.

*buffer_size*<br/>
Максимальное число байтов для чтения.

## <a name="return-value"></a>Возвращаемое значение

**_read** возвращает число считанных байтов, которое может быть меньше *BUFFER_SIZE* , если в файле осталось меньше *BUFFER_SIZE* байт или если файл был открыт в текстовом режиме. В текстовом режиме каждая пара `\r\n` символов возврата каретки и перевода строки заменяется одним символом `\n`перевода строки. В возвращаемом значении учитывается только один символ перевода строки. Эта замена не влияет на указатель файла.

Если функция пытается прочитать конечную часть файла, она возвращает 0. Если *демон* не является допустимым, файл не открыт для чтения или файл заблокирован, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция **возвращает значение-1 и устанавливает** для **значение EBADF**.

Если параметр *buffer* имеет **значение NULL**или *BUFFER_SIZE* > **INT_MAX**, вызывается обработчик недопустимых параметров. Если выполнение может быть продолжено, функция возвращает значение-1 **, а** параметру возврата — **еинвал**.

Дополнительные сведения об этом и других кодах возврата см. в статье [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **_read** считывает максимум *BUFFER_SIZE* байт в *буфер* из файла, связанного с *демоном*. Операция чтения начинается с текущего положения указателя файла, связанного с данным файлом. После операции чтения указатель файла указывает на следующий непрочитанный символ.

Если файл был открыт в текстовом режиме, чтение завершается, когда **_read** встречает символ CTRL + Z, который рассматривается как индикатор конца файла. Чтобы очистить индикатор конца файла, следует использовать [_lseek](lseek-lseeki64.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_read**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_read.c
/* This program opens a file named crt_read.txt
* and tries to read 60,000 bytes from
* that file using _read. It then displays the
* actual number of bytes read.
*/

#include <fcntl.h>      /* Needed only for _O_RDWR definition */
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <share.h>

char buffer[60000];

int main( void )
{
   int fh, bytesread;
   unsigned int nbytes = 60000;

   /* Open file for input: */
   if ( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ))
   {
      perror( "open failed on input file" );
      exit( 1 );
   }

   /* Read in input: */
   if (( bytesread = _read( fh, buffer, nbytes )) <= 0 )
      perror( "Problem reading file" );
   else
      printf( "Read %u bytes from file\n", bytesread );

   _close( fh );
}
```

### <a name="input-crt_readtxt"></a>Входные данные: crt_read.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Вывод

```Output
Read 19 bytes from file
```

## <a name="see-also"></a>См. также

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fread](fread.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_write](write.md)<br/>
