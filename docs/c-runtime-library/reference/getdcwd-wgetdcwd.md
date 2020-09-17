---
title: _getdcwd, _wgetdcwd
ms.date: 4/2/2020
api_name:
- _getdcwd
- _wgetdcwd
- _o__getdcwd
- _o__wgetdcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
ms.openlocfilehash: c9ae07c5880cb86b0aafb0dc66a7c1ce3edcc9d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218667"
---
# <a name="_getdcwd-_wgetdcwd"></a>_getdcwd, _wgetdcwd

Получает полный путь текущей рабочей папки на указанном диске.

## <a name="syntax"></a>Синтаксис

```C
char *_getdcwd(
   int drive,
   char *buffer,
   int maxlen
);
wchar_t *_wgetdcwd(
   int drive,
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>Параметры

*диск*<br/>
Неотрицательное целое число, которое определяет диск (0 — диск по умолчанию, 1 — A, 2 — B и т. д.).

Если указанный диск недоступен или не удается определить тип диска (например, съемный, стационарный, компакт-диск, электронный диск или сетевой диск), вызывается обработчик недопустимых параметров. Дополнительные сведения см. в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

*двойной*<br/>
Место хранения для пути или **NULL**.

Если указано **значение NULL** , эта функция выделяет буфер по крайней мере *maxlen* размера с помощью функции **malloc**, а возвращаемое значение **_getdcwd** является указателем на выделенный буфер. Буфер можно освободить, вызвав **Free** и передав ему указатель.

*maxlen*<br/>
Ненулевое положительное число, указывающее максимальную длину пути в символах: **`char`** для **_getdcwd** и **`wchar_t`** для **_wgetdcwd**.

Если *maxlen* меньше или равно нулю, вызывается обработчик недопустимых параметров. Дополнительные сведения см. в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

## <a name="return-value"></a>Возвращаемое значение

Указатель на строку, представляющую полный путь к текущему рабочему каталогу на указанном диске, или **значение NULL**, которое указывает на ошибку.

Если для параметра *buffer* задано **значение NULL** и недостаточно памяти для выделения *maxlen* символов, возникает ошибка **, а для** свойства "переводится" значение **еномем**. Если длина пути, в том числе завершающего нуль-символа, превышает *maxlen*, возникает ошибка, а **параметру** "ключ вывода" присваивается значение **ERANGE**. Дополнительные сведения об этих кодах ошибки см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **_getdcwd** возвращает полный путь к текущему рабочему каталогу на указанном диске и сохраняет его в *буфере*. Если текущей рабочей папкой является корневой каталог, строка заканчивается обратной косой чертой (\\). Если текущая рабочая папка находится в каталоге, отличном от корневого, строка заканчивается именем каталога, а не обратной косой чертой.

**_wgetdcwd** является версией **_getdcwd**для расширенных символов, ее параметр *буфера* и возвращаемое значение являются строками расширенных символов. В противном случае **_wgetdcwd** и **_getdcwd** ведут себя одинаково.

Эта функция потокобезопасна, даже если она зависит от функции **GetFullPathName**, которая сама не потокобезопасна. Однако можно нарушить потокобезопасность, если многопоточное приложение вызывает и эту функцию, и функцию [GetFullPathName](/windows/win32/api/fileapi/nf-fileapi-getfullpathnamew).

Версия этой функции с суффиксом **_nolock** ведет себя идентично этой функции, за исключением того, что она не является потокобезопасной и не защищена от помех в других потоках. Для получения дополнительной информации см. [_getdcwd_nolock, _wgetdcwd_nolock](getdcwd-nolock-wgetdcwd-nolock.md).

Если определены **_DEBUG** и **_CRTDBG_MAP_ALLOC** , вызовы **_getdcwd** и **_wgetdcwd** заменяются вызовами **_getdcwd_dbg** и **_wgetdcwd_dbg** , что позволяет отлаживать выделение памяти. Дополнительные сведения см. в разделе[_getdcwd_dbg, _wgetdcwd_dbg](getdcwd-dbg-wgetdcwd-dbg.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd**|**_getdcwd**|**_getdcwd**|**_wgetdcwd**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getdcwd**|\<direct.h>|
|**_wgetdcwd**|\<direct.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [_getdrive](getdrive.md).

## <a name="see-also"></a>См. также раздел

[Управление каталогом](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
