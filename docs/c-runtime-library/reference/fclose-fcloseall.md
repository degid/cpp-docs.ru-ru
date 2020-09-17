---
title: fclose, _fcloseall
ms.date: 4/2/2020
api_name:
- fclose
- _fcloseall
- _o__fcloseall
- _o_fclose
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
- fclose
- _fcloseall
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
ms.openlocfilehash: 3f8567f7bb01c519938f5a4e28bbb33bce09dffe
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920230"
---
# <a name="fclose-_fcloseall"></a>fclose, _fcloseall

Закрывает поток (**фклосе**) или закрывает все открытые потоки (**_fcloseall**).

## <a name="syntax"></a>Синтаксис

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>Параметры

*вышестоящий*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**фклосе** возвращает 0, если поток успешно закрыт. **_fcloseall** возвращает общее число закрытых потоков. Обе функции возвращают **EOF** , чтобы указать ошибку.

## <a name="remarks"></a>Примечания

Функция **фклосе** закрывает *поток*. Если *Stream* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **fclose** , фклосе **устанавливает значение** переводится в **еинвал** и возвращает **EOF**. Рекомендуется всегда проверять указатель *потока* перед вызовом этой функции.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Функция **_fcloseall** закрывает все открытые потоки, за исключением **stdin**, **stdout**, **stderr** (и, в MS-DOS, **_stdaux** и **_stdprn**). Он также закрывает и удаляет временные файлы, созданные **tmpfile**. При использовании обеих функций все буферы, связанные с потоком, перед закрытием сбрасываются. При закрытии потока выделенные системой буферы освобождаются. Буферы, назначенные пользователем с помощью **setbuf** и **setvbuf** , не освобождаются автоматически.

**Примечание.** При использовании этих функций для закрытия потока вместе с ним закрываются также базовый дескриптор файла и обработчик (или сокет) файла операционной системы. Таким образом, если файл был первоначально открыт как дескриптор файла или дескриптор файла и закрывается с помощью **фклосе**, не вызывайте **_close** , чтобы закрыть дескриптор файла. не вызывайте функцию Win32 в **CloseHandle** для закрытия маркера файла.

**фклосе** и **_fcloseall** включают код для защиты от помех от других потоков. Сведения о неблокирующей версии **фклосе**см. в разделе **_fclose_nolock**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fclose**|\<stdio.h>|
|**_fcloseall**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [fopen](fopen-wfopen.md).

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
