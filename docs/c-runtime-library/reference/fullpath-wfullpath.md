---
title: _fullpath, _wfullpath
ms.date: 4/2/2020
api_name:
- _fullpath
- _wfullpath
- _o__fullpath
- _o__wfullpath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wfullpath
- fullpath
- _wfullpath
- _fullpath
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
ms.openlocfilehash: 8583ea17930721f8d8b80aa5066dbc07372ce243
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231394"
---
# <a name="_fullpath-_wfullpath"></a>_fullpath, _wfullpath

Создает абсолютный или полный путь для указанного относительного пути.

## <a name="syntax"></a>Синтаксис

```C
char *_fullpath(
   char *absPath,
   const char *relPath,
   size_t maxLength
);
wchar_t *_wfullpath(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength
);
```

### <a name="parameters"></a>Параметры

*абспас*<br/>
Указатель на буфер, содержащий абсолютный или полный путь, или **значение NULL**.

*релпас*<br/>
Относительный путь.

*maxLength*<br/>
Максимальная длина абсолютного буфера имени пути (*абспас*). Это длина в байтах для **_fullpath** , но в расширенных символах ( **`wchar_t`** ) для **_wfullpath**.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на буфер, содержащий абсолютный путь (*абспас*). Если возникает ошибка (например, если значение, передаваемое в *релпас* , содержит букву диска, которая не является допустимой или не может быть найдена, или если длина созданного абсолютного пути (*абспас*) больше, чем *MaxLength*), функция возвращает **значение NULL**.

## <a name="remarks"></a>Примечания

Функция **_fullpath** расширяет относительное имя пути в *релпас* до полного или абсолютного пути и сохраняет это имя в *абспас*. Если *абспас* имеет **значение NULL**, то **malloc** используется для выделения буфера достаточной длины для хранения пути. Освобождение этого буфера — обязанность вызывающего объекта. Относительный путь указывает путь в другое расположение из текущего расположения (например, текущей рабочей папки: "."). Абсолютный путь является расширением относительного пути, которое указывает весь путь, требуемый для достижения необходимого расположения из корневой папки файловой системы. В отличие от **_makepath**, **_fullpath** можно использовать для получения абсолютного пути для относительных путей (*релпас*), включающих "./" или ".. /"в своих именах.

Например, чтобы использовать подпрограммы среды выполнения C, приложение должно включать файлы заголовков, которые содержат объявления подпрограмм. Каждый файл заголовка содержит оператор, ссылающийся на расположение файла относительным способом (из рабочей папки приложения):

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#include <stdlib.h>
```

когда абсолютный путь (реальное расположение в файловой системе) файла может иметь вид:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** автоматически обрабатывает строковые аргументы многобайтовых символов соответствующим образом, распознает последовательности многобайтовых символов в соответствии с используемой в данный момент многобайтовой кодовой страницей. **_wfullpath** — это версия **_fullpath**для расширенных символов; строковые аргументы для **_wfullpath** являются строками расширенных символов. поведение **_wfullpath** и **_fullpath** идентично, за исключением того, что **_wfullpath** не обрабатывает строки многобайтовых символов.

Если определены оба **_DEBUG** и **_CRTDBG_MAP_ALLOC** , вызовы **_fullpath** и **_wfullpath** заменяются вызовами **_fullpath_dbg** и **_wfullpath_dbg** , чтобы разрешить отладку выделения памяти. Дополнительные сведения см. в разделе [_fullpath_dbg, _wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md).

Эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md), если *maxlen* меньше или равен 0. Если выполнение может быть продолжено, эта функция **устанавливает** **Еинвал** и возвращает **значение NULL**.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

Если буфер *абспас* имеет **значение NULL**, **_fullpath** вызывает функцию [malloc](malloc.md) для выделения буфера и игнорирует аргумент *MaxLength* . Корректное освобождение этого буфера (с помощью функции [free](free.md)) — обязанность вызывающего объекта. Если аргумент *релпас* указывает диск, текущий каталог этого диска объединяется с путем.

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_fullpath**|\<stdlib.h>|
|**_wfullpath**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fullpath.c
// This program demonstrates how _fullpath
// creates a full path from a partial path.

#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
#include <direct.h>

void PrintFullPath( char * partialPath )
{
   char full[_MAX_PATH];
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )
      printf( "Full path is: %s\n", full );
   else
      printf( "Invalid path\n" );
}

int main( void )
{
   PrintFullPath( "test" );
   PrintFullPath( "\\test" );
   PrintFullPath( "..\\test" );
}
```

```Output
Full path is: C:\Documents and Settings\user\My Documents\test
Full path is: C:\test
Full path is: C:\Documents and Settings\user\test
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
