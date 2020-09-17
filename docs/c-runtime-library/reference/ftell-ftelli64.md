---
title: ftell, _ftelli64
ms.date: 4/2/2020
api_name:
- _ftelli64
- ftell
- _o__ftelli64
- _o_ftell
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
- _ftelli64
- ftell
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
ms.openlocfilehash: 273ad4990f78355029770e19e7cdcf36d7ba39bf
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910077"
---
# <a name="ftell-_ftelli64"></a>ftell, _ftelli64

Получает текущее положение указателя файла.

## <a name="syntax"></a>Синтаксис

```C
long ftell(
   FILE *stream
);
__int64 _ftelli64(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*вышестоящий*<br/>
Структура целевого **файла** .

## <a name="return-value"></a>Возвращаемое значение

**ftell** и **_ftelli64** возвращают текущее расположение файла. Значение, возвращаемое **ftell** и **_ftelli64** , может не отражать физическое смещение байтов для потоков, открытых в текстовом режиме, так как текстовый режим вызывает перевод перевода строки с возвратом каретки. Используйте **ftell** с [fseek](fseek-fseeki64.md) или **_ftelli64** с [_fseeki64](fseek-fseeki64.md) , чтобы правильно вернуться к расположениям файлов. При возникновении ошибки **ftell** и **_ftelli64** вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают-1L и применяют **к одной** из двух констант, определенных в начале. Высоты. Константа **значение EBADF** означает, что аргумент *потока* не является допустимым значением указателя файла или не ссылается на открытый файл. **Еинвал** означает, что функции был передан недопустимый аргумент *потока* . На устройствах, которые не могут выполнять поиск (например, терминалы и принтеры) или если *поток* не ссылается на открытый файл, возвращаемое значение не определено.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функции **ftell** и **_ftelli64** извлекают текущую позиции указателя файла (при наличии), связанного с *потоком*. Позиция представляется как смещение относительно начала потока.

Обратите внимание, что когда файл открыт для добавления данных, текущее положение в файле определяется последней операцией ввода-вывода, а не тем, где должна быть произведена следующая запись. Например, если файл открыт для добавления и последней операцией было чтение, положением в файле является место, где должна начинаться следующая операция чтения, а не следующая операция записи. (Когда файл открывается для добавления, расположение файла перемещается в конец файла перед любой операцией записи.) Если для файла, открытого для добавления, еще не выполнялась операция ввода-вывода, то позицией файла является начало файла.

В текстовом режиме при вводе CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для операций чтения и записи, **fopen** и все связанные подпрограммы проверяют CTRL + Z в конце файла и удаляют его, если это возможно. Это делается потому, что использование сочетания **ftell** и [fseek](fseek-fseeki64.md) или **_ftelli64** и [_fseeki64](fseek-fseeki64.md)для перемещения внутри файла, который заканчивается на Ctrl + Z, может вызвать неправильное поведение **ftell** или **_ftelli64** в конце файла.

Во время выполнения функция блокирует вызывающий поток, поэтому она потокобезопасна. Сведения о версии без блокировки см. в разделе **_ftell_nolock**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|Необязательные заголовки|
|--------------|---------------------|----------------------|
|**ftell**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_ftell.c
// This program opens a file named CRT_FTELL.C
// for reading and tries to read 100 characters. It
// then uses ftell to determine the position of the
// file pointer and displays this position.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long position;
   char list[100];
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )
   {
      // Move the pointer by reading data:
      fread( list, sizeof( char ), 100, stream );
      // Get position after read:
      position = ftell( stream );
      printf( "Position after trying to read 100 bytes: %ld\n",
              position );
      fclose( stream );
   }
}
```

```Output
Position after trying to read 100 bytes: 100
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
