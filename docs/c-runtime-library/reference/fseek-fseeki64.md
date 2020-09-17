---
title: fseek, _fseeki64
ms.date: 4/2/2020
api_name:
- _fseeki64
- fseek
- _o__fseeki64
- _o_fseek
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
- fseek
- _fseeki64
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
ms.openlocfilehash: c9bfc9a575504d890d0021937713c720c4557441
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910193"
---
# <a name="fseek-_fseeki64"></a>fseek, _fseeki64

Перемещает файловый указатель в указанное местоположение.

## <a name="syntax"></a>Синтаксис

```C
int fseek(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Параметры

*вышестоящий*<br/>
Указатель на структуру **FILE**.

*offset*<br/>
Количество байт, начиная с *origin*.

*лета*<br/>
Первоначальная позиция.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха **fseek** и **_fseeki64** возвращают 0. В противном случае возвращается ненулевое значение. Для устройств, которые не поддерживают поиск, возвращаемое значение не определено. Если *Stream* является пустым указателем или если *источник* не является одним из допустимых значений, описанных ниже, **fseek** и **_fseeki64** вызывают обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции **устанавливают** значение **еинвал** и возвращают-1.

## <a name="remarks"></a>Примечания

Функции **fseek** и **_fseeki64** перемещают указатель файла (при его наличии), связанный с *потоком* , в новое расположение, *которое принимает байты* из *источника*. Следующая операция в потоке происходит в новом местоположении. В потоке, открытом для обновления, следующая операция может быть либо операцией чтения, либо операцией записи. *Источник* аргумента должен быть одной из следующих констант, определенных в stdio. Высоты

|значение происхождения|Значение|
|-|-|
| **SEEK_CUR** | Текущая позиция файлового указателя. |
| **SEEK_END** | Конец файла. |
| **SEEK_SET** | Начало файла. |

Можно использовать **fseek** и **_fseeki64** , чтобы изменить расположение указателя в любом месте файла. Указатель также может быть размещен за пределами файла. **fseek** и **_fseeki64** удаляют индикатор конца файла и отменяют результат всех предыдущих вызовов [ungetc](ungetc-ungetwc.md) к *потоку*.

Когда файл открыт для добавления данных, текущая позиция в файле определяется последней операцией ввода-вывода, а не тем, где должна произойти следующая запись. Если в открытом для добавления файле еще не было ни одной операции ввода-вывода, этой позицией является начало файла.

Для потоков, открытых в текстовом режиме, **fseek** и **_fseeki64** имеют ограниченный объем использования, так как переводы перевода строки с возвратом каретки могут вызвать **fseek** и **_fseeki64** для получения непредвиденных результатов. Единственные операции **fseek** и **_fseeki64** , которые гарантированно работают с потоками, открытыми в текстовом режиме,:

- поиск со смещением 0 относительно любого из значений origin;

- Поиск с начала файла со значением offset, возвращенным из вызова [ftell](ftell-ftelli64.md) при использовании **fseek** или [_ftelli64](ftell-ftelli64.md) при использовании **_fseeki64**.

Кроме того, в текстовом режиме при вводе CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для операций чтения и записи, [fopen](fopen-wfopen.md) и все связанные подпрограммы проверяют CTRL + Z в конце файла и удаляют его, если это возможно. Это делается потому, что использование сочетания **fseek** и [ftell](ftell-ftelli64.md) или **_fseeki64** и [_ftelli64](ftell-ftelli64.md)для перемещения внутри файла, который заканчивается на Ctrl + Z, может вызвать неправильное поведение **fseek** или **_fseeki64** в конце файла.

Когда CRT открывает файл, который начинается с метки порядка байтов (BOM), указатель файла помещается после метки (т. е. в начале фактического содержимого файла). Если необходимо **fseek** в начало файла, используйте [ftell](ftell-ftelli64.md) , чтобы получить начальное расположение и **fseek** на него, а не в положении 0.

Эта функция блокирует работу других потоков во время выполнения, поэтому она потокобезопасна. Описание неблокирующей версии этой функции см. в разделе [_fseek_nolock, _fseeki64_nolock](fseek-nolock-fseeki64-nolock.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fseek**|\<stdio.h>|
|**_fseeki64**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fseek.c
// This program opens the file FSEEK.OUT and
// moves the pointer to the file's beginning.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[81];
   int  result;

   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )
   {
      printf( "The file fseek.out was not opened\n" );
      return -1;
   }
   fprintf( stream, "The fseek begins here: "
                    "This is the file 'fseek.out'.\n" );
   result = fseek( stream, 23L, SEEK_SET);
   if( result )
      perror( "Fseek failed" );
   else
   {
      printf( "File pointer is set to middle of first line.\n" );
      fgets( line, 80, stream );
      printf( "%s", line );
    }
   fclose( stream );
}
```

```Output
File pointer is set to middle of first line.
This is the file 'fseek.out'.
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
