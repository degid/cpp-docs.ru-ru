---
title: strerror, _strerror, _wcserror, __wcserror
description: Описывает функции библиотеки времени выполнения Microsoft C (CRT) strerror, _strerror, _wcserror и __wcserror.
ms.date: 4/2/2020
api_name:
- strerror
- _strerror
- _wcserror
- __wcserror
- _o___wcserror
- _o__strerror
- _o__wcserror
- _o_strerror
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
ms.openlocfilehash: 30885974b9c9fbf0fdca0e52808fb8bd1dfbaffe
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920034"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror, _strerror, _wcserror, __wcserror

Возвращает строку сообщения системной ошибки (**strerror**, **_wcserror**) или формат пользовательской строки сообщения об ошибке (**_strerror**, **__wcserror**). Существуют более безопасные версии этих функций; см. раздел [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md).

## <a name="syntax"></a>Синтаксис

```C
char * strerror(
   int errnum );

char * _strerror(
   const char *strErrMsg );

wchar_t * _wcserror(
   int errnum );

wchar_t * __wcserror(
   const wchar_t *strErrMsg );
```

### <a name="parameters"></a>Параметры

*errnum*\
Номер ошибки.

*стреррмсг*\
Пользовательское сообщение.

## <a name="return-value"></a>Возвращаемое значение

Все эти функции возвращают указатель на строку сообщения об ошибке в локальном буфере хранилища потока, принадлежащем среде выполнения. Последующие вызовы в том же потоке могут перезаписать эту строку.

## <a name="remarks"></a>Примечания

Функция **strerror** сопоставляет *errnum* со строкой сообщения об ошибке и возвращает указатель на строку. Функции **strerror** и **_strerror** на самом деле не напечатали сообщение. Для печати вызовите выходную функцию, например [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile", 2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

Если *стреррмсг* передается как **null**, **_strerror** возвращает указатель на строку. Он содержит системное сообщение об ошибке для последнего вызова библиотеки, вызвавшего ошибку. Строка сообщения об ошибке оканчивается символом новой строки ('\n'). Если значение *стреррмсг* не **равно NULL**, строка содержит, по порядку: строку *стреррмсг* , двоеточие, пробел, системное сообщение об ошибке и символ новой строки. Строковое сообщение может содержать не более 94 символов и содержать либо узкие (**_strerror**), либо широкие (**__wcserror**) символы.

Фактический номер ошибки для **_strerror** хранится в [переменной.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) Чтобы получить точные результаты, вызовите **_strerror** сразу после того, как подпрограммы библиотеки возвращают ошибку. В противном случае последующие вызовы подпрограмм библиотек могут перезаписать значение **errno** перезаписи.

**_wcserror** и **__wcserror** — это версии **strerror** и **_strerror**для расширенных символов соответственно.

**_strerror**, **_wcserror**и **__Wcserror** являются специфичными для Майкрософт, а не частью стандартной библиотеки C. Мы не рекомендуем использовать их в том месте, где нужен переносимый код. Для стандартной совместимости C используйте вместо него **strerror** .

Для получения строк ошибок рекомендуется использовать **strerror** или **_wcserror** вместо устаревших макросов [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) и [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) , а также устаревшие внутренние функции **__sys_errlist** и **__sys_nerr**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления универсальных текстовых подпрограмм

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**, **__wcserror**|\<string.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [perror](perror-wperror.md).

## <a name="see-also"></a>См. также раздел

[Управление строками](../../c-runtime-library/string-manipulation-crt.md)\
[клеарерр](clearerr.md)\
[ferror](ferror.md)\
[perror, _wperror](perror-wperror.md)
