---
title: ungetc, ungetwc
ms.date: 4/2/2020
api_name:
- ungetwc
- ungetc
- _o_ungetc
- _o_ungetwc
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
- _ungettc
- ungetwc
- ungetc
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
ms.openlocfilehash: 406ce7d8befd1d9e9e6a065f2549bacf46d2fd6e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915972"
---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc

Помещает символ обратно в поток.

## <a name="syntax"></a>Синтаксис

```C
int ungetc(
   int c,
   FILE *stream
);
wint_t ungetwc(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*ц*<br/>
Символ, который требуется поместить обратно.

*вышестоящий*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха каждая из этих функций Возвращает символьный аргумент *c*. Если *c* не удается вернуть обратно или если ни один символ не был считан, входной поток не изменяется, а **ungetc** возвращает **EOF**; **ungetwc** возвращает **WEOF**. Если *Stream* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, возвращается **EOF** или **WEOF** , а параметру "переводится **" значение** **еинвал**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **ungetc** помещает символ *c* обратно в *Stream* и очищает индикатор конца файла. Поток должен быть открыт для чтения. Последующая операция чтения в *потоке* начинается с *c*. Попытка принудительной отправки **EOF** в поток с помощью **ungetc** игнорируется.

Символы, помещаемые в поток с помощью **ungetc** , могут быть стерты при вызове **fflush**, [fseek](fseek-fseeki64.md), **fsetpos**или [Rewind](rewind.md) перед считыванием символа из потока. Индикатор позиции в файле будет иметь значение, которое было до помещения символов обратно. Внешнее хранилище, соответствующее потоку, не изменяется. При успешном вызове **ungetc** для текстового потока индикатор положения файла не определен до тех пор, пока все символы, отправленные обратно, не будут прочитаны или отменены. При каждом успешном вызове **ungetc** для двоичного потока индикатор положения файла уменьшается; Если его значение было равно 0 перед вызовом, то после вызова значение не определено.

Результаты непредсказуемы, если **ungetc** вызывается дважды без операции чтения или размещения файла между двумя вызовами. После вызова **fscanf**вызов **ungetc** может завершиться ошибкой, если не была выполнена другая операция чтения (например, **getc**). Это обусловлено тем, что **fscanf** вызывает **ungetc**.

**ungetwc** — это версия **ungetc**для расширенных символов. Однако при каждом успешном вызове **ungetwc** для текстового или двоичного потока значение индикатора положения файла не определено до тех пор, пока все символы, отправленные обратно, не будут прочитаны или отменены.

Эти функции являются потокобезопасными и блокируют конфиденциальные данные во время выполнения. Описание неблокирующей версии см. в разделе [_ungetc_nolock, _ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**ungetc**|\<stdio.h>|
|**ungetwc**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальная платформа Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, **stdin**, **stdout**и **stderr**, должны быть перенаправляться до того, как функции времени выполнения C смогут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_ungetc.c
// This program first converts a character
// representation of an unsigned integer to an integer. If
// the program encounters a character that is not a digit,
// the program uses ungetc to replace it in the  stream.
//

#include <stdio.h>
#include <ctype.h>

int main( void )
{
   int ch;
   int result = 0;

   // Read in and convert number:
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )
      result = result * 10 + ch - '0';    // Use digit.
   if( ch != EOF )
      ungetc( ch, stdin );                // Put nondigit back.
   printf( "Number = %d\nNext character in stream = '%c'",
            result, getchar() );
}
```

```Output

      521aNumber = 521
Next character in stream = 'a'
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
