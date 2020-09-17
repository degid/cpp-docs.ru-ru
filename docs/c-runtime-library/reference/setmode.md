---
title: _setmode
ms.date: 4/2/2020
api_name:
- _setmode
- _o__setmode
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
- _setmode
helpviewer_keywords:
- Unicode [C++], console output
- files [C++], modes
- _setmode function
- file translation [C++], setting mode
- files [C++], translation
- setmode function
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
ms.openlocfilehash: 1995d54e972f99543773fff374e56c0dd7cf4988
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915807"
---
# <a name="_setmode"></a>_setmode

Задает режим преобразования файлов.

## <a name="syntax"></a>Синтаксис

```C
int _setmode (
   int fd,
   int mode
);
```

### <a name="parameters"></a>Параметры

*демо*<br/>
Дескриптор файла.

*mode*<br/>
Новый режим преобразования.

## <a name="return-value"></a>Возвращаемое значение

При успешном выполнении возвращает предыдущий режим преобразования.

Если функции переданы недопустимые параметры, вызывается обработчик недопустимого параметра, как описано в разделе [Parameter Validation](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает значение-1 **и задает для** параметра « **значение EBADF**», что указывает на недопустимый дескриптор файла, или **еинвал**, который указывает на недопустимый аргумент *mode* .

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **_setmode** *задает для режима преобразования файла, заданного* параметром \ " *демон*\". Передача **_O_TEXT** как *mode* устанавливает режим текста (т. е. переведенный). Сочетания символов возврата каретки и перевода строки (CR-LF) преобразуются в один символ перевода строки во входных данных. Символы перевода строки преобразуются в комбинацию CR-LF в выводе. Передача **_O_BINARY** задает двоичный (непреобразованный) режим, в котором эти переводы подавляются.

Можно также передать **_O_U16TEXT**, **_O_U8TEXT**или **_O_WTEXT** , чтобы включить режим Юникода, как показано во втором примере далее в этом документе.

> [!CAUTION]
> Режим Юникода предназначен для расширенных функций печати (например, `wprintf`) и не поддерживается для узких функций печати. Использование небольшой функции печати в потоке режима Юникод вызывает утверждение.

**_setmode** обычно используется для изменения режима преобразования **stdin** и **stdout**по умолчанию, но его можно использовать в любом файле. При применении **_setmode** к дескриптору файла для потока вызовите метод **_setmode** , прежде чем выполнять операции ввода или вывода в потоке.

> [!CAUTION]
> При записи данных в файловый поток явно очистите код с помощью [fflush](fflush.md) , прежде чем использовать **_setmode** для изменения режима. Если не выполнить сброс кода, может возникнуть непредвиденное поведение. Если данные не записывались в поток, выполнять сброс кода не нужно.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательные заголовки|
|-------------|---------------------|----------------------|
|**_setmode**|\<io.h>|\<fcntl.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_setmode.c
// This program uses _setmode to change
// stdin from text mode to binary mode.

#include <stdio.h>
#include <fcntl.h>
#include <io.h>

int main( void )
{
   int result;

   // Set "stdin" to have binary mode:
   result = _setmode( _fileno( stdin ), _O_BINARY );
   if( result == -1 )
      perror( "Cannot set mode" );
   else
      printf( "'stdin' successfully changed to binary mode\n" );
}
```

```Output
'stdin' successfully changed to binary mode
```

## <a name="example"></a>Пример

```C
// crt_setmodeunicode.c
// This program uses _setmode to change
// stdout to Unicode. Cyrillic and Ideographic
// characters will appear on the console (if
// your console font supports those character sets).

#include <fcntl.h>
#include <io.h>
#include <stdio.h>

int main(void) {
    _setmode(_fileno(stdout), _O_U16TEXT);
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");
    return 0;
}
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_set_fmode](set-fmode.md)<br/>
