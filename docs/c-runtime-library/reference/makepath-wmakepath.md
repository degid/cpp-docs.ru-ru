---
title: _makepath, _wmakepath
ms.date: 4/2/2020
api_name:
- _makepath
- _wmakepath
- _o__makepath
- _o__wmakepath
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
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
ms.openlocfilehash: 19a20de40bb02e49f618e8e617c9659788dc3e25
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914397"
---
# <a name="_makepath-_wmakepath"></a>_makepath, _wmakepath

Создают путь из компонентов. Существуют более безопасные версии этих функций; см. раздел [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="syntax"></a>Синтаксис

```C
void _makepath(
   char *path,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
void _wmakepath(
   wchar_t *path,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
```

### <a name="parameters"></a>Параметры

*path*<br/>
Буфер полного пути.

*диск*<br/>
Содержит букву (A, B и т. д.), соответствующую требуемому диску, с необязательным двоеточием после нее. **_makepath** автоматически вставляет двоеточие в составной путь, если он отсутствует. Если параметр *Drive* имеет **значение NULL** или указывает на пустую строку, буква диска не отображается в строке составного *пути* .

*dir*<br/>
Содержит путь каталогов, не включая обозначение диска или фактическое имя файла. Замыкающая косая черта является необязательной, и в одном аргументе *dir* может использоваться\\либо косая черта (/), либо обратная косая черта (), либо и то, и другое. Если конечная косая черта (/ или \\) не указана, она вставляется автоматически. Если параметр *dir* имеет **значение NULL** или указывает на пустую строку, путь к каталогу не вставляется в строку составного *пути* .

*fname*<br/>
Содержит базовое имя файла без расширений. Если параметр *fname* имеет **значение NULL** или указывает на пустую строку, имя файла не вставляется в строку составного *пути* .

*WLAN*<br/>
Содержит фактическое расширение имени файла с предшествующей точкой (.) или без нее. **_makepath** вставляет период автоматически, если он не появился в *ext*. Если *ext* имеет **значение NULL** или указывает на пустую строку, расширение не вставляется в строку составного *пути* .

## <a name="remarks"></a>Примечания

Функция **_makepath** создает строку составного пути из отдельных компонентов, сохраняя результат в *path*. *Путь* может содержать букву диска, путь к каталогу, имя файла и расширение имени файла. **_wmakepath** — это версия **_makepath**для расширенных символов; аргументы для **_wmakepath** являются строками расширенных символов. в противном случае **_wmakepath** и **_makepath** ведут себя одинаково.

**Примечание о безопасности.** Следует использовать строку, оканчивающуюся нуль-символом. Чтобы избежать переполнения буфера, строка, завершающаяся нулем, не должна превышать размер буфера *пути* . **_makepath** не гарантирует, что длина строки составного пути не превысит **_MAX_PATH**. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

Аргумент *path* должен указывать на пустой буфер, достаточно большой для хранения полного пути. Составной *путь* должен быть не больше, чем **_MAX_PATHная** константа, определенная в STDLIB.h.

Если параметр path имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Кроме того, для параметра « **еинвал**» задано значение **«нет»** . Значения **null** допускаются для всех остальных параметров.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_makepath**|\<stdlib.h>|
|**_wmakepath**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_makepath.c
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];

   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996
   // Note: _makepath is deprecated; consider using _makepath_s instead
   printf( "Path created with _makepath: %s\n\n", path_buffer );
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996
   // Note: _splitpath is deprecated; consider using _splitpath_s instead
   printf( "Path extracted with _splitpath:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath: c:\sample\crt\makepath.c

Path extracted with _splitpath:
   Drive: c:
   Dir: \sample\crt\
   Filename: makepath
   Ext: .c
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)<br/>
