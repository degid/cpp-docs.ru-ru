---
title: setvbuf
ms.date: 4/2/2020
api_name:
- setvbuf
- _o_setvbuf
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
- setvbuf
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
ms.openlocfilehash: 907d02e94c79acf09dfa99a8b42e9f448d32dcfa
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915755"
---
# <a name="setvbuf"></a>setvbuf

Управляет потоковой буферизацией и размером буфера.

## <a name="syntax"></a>Синтаксис

```C
int setvbuf(
   FILE *stream,
   char *buffer,
   int mode,
   size_t size
);
```

### <a name="parameters"></a>Параметры

*вышестоящий*<br/>
Указатель на структуру **FILE**.

*двойной*<br/>
Выделенный пользователем буфер.

*mode*<br/>
Режим буферизации.

*size*<br/>
Размер буфера в байтах. Допустимый диапазон: 2 <= *size* <= INT_MAX (2147483647). На внутреннем уровне значение, заданное для параметра *size* , округляется вниз до ближайшего числа, кратного 2.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха.

Если *Stream* имеет **значение NULL**или если *режим* или *Размер* не находятся в допустимом изменении, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает –1 и задает для **errno** значение **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **setvbuf** позволяет программе управлять как буферизацией, так и размером буфера для *потока*. *поток* должен ссылаться на открытый файл, который не проходил операцию ввода-вывода с момента открытия. Массив, на который указывает *buffer* , используется в качестве буфера, если он не равен **null**, в этом случае **setvbuf** использует автоматически выделяемый буфер *размера*/2 \* 2 байта.

Режим должен быть **_IOFBF**, **_IOLBF**или **_IONBF**. Если параметр *mode* имеет значение **_IOFBF** или **_IOLBF**, то в качестве размера буфера используется *size* . Если параметр *mode* имеет значение **_IONBF**, поток не буферизован, а *Размер* и *буфер* не учитываются. Значения для *mode* и их значений:

|значение *режима*|Значение|
|-|-|
| **_IOFBF** | Полная буферизация; то есть *буфер* используется в качестве буфера, а *Размер* используется в качестве размера буфера. Если значение *buffer* равно **null**, используется автоматически выделяемый *Размер* буфера (в байтах). |
| **_IOLBF** | В некоторых системах таким образом осуществляется линейная буферизация. Однако для Win32 поведение аналогично **_IOFBF** -полной буферизации. |
| **_IONBF** | Буфер не используется, независимо от размера *буфера* или *размеров*. |

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**setvbuf**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_setvbuf.c
// This program opens two streams: stream1
// and stream2. It then uses setvbuf to give stream1 a
// user-defined buffer of 1024 bytes and stream2 no buffer.
//

#include <stdio.h>

int main( void )
{
   char buf[1024];
   FILE *stream1, *stream2;

   if( fopen_s( &stream1, "data1", "a" ) == 0 &&
       fopen_s( &stream2, "data2", "w" ) == 0 )
   {
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )
         printf( "Incorrect type or size of buffer for stream1\n" );
      else
         printf( "'stream1' now has a buffer of 1024 bytes\n" );
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )
         printf( "Incorrect type or size of buffer for stream2\n" );
      else
         printf( "'stream2' now has no buffer\n" );
      _fcloseall();
   }
}
```

```Output
'stream1' now has a buffer of 1024 bytes
'stream2' now has no buffer
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setbuf](setbuf.md)<br/>
