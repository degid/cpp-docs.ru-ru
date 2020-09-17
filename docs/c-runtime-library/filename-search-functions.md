---
title: Функции поиска имени файла
ms.date: 11/04/2016
api_location:
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
helpviewer_keywords:
- file names [C++], searching for
- _find function
- wfind function
- find function
- _wfind function
ms.assetid: 2bc2f8ef-44e4-4271-b3e8-666d36fde828
ms.openlocfilehash: fb5cc0e18d150d4171e33038e27810989c0f503b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226246"
---
# <a name="filename-search-functions"></a>Функции поиска имени файла

Эти функции осуществляют и завершают поиск для указанных имен файлов:

- [_findnext, _wfindnext](../c-runtime-library/reference/findnext-functions.md)

- [_findfirst, _wfindfirst](../c-runtime-library/reference/findfirst-functions.md)

- [_findclose](../c-runtime-library/reference/findclose.md)

## <a name="remarks"></a>Примечания

Функция `_findfirst` предоставляет сведения о первом экземпляре имени файла, соответствующем файлу, указанному в аргументе `filespec` . В `filespec` можно использовать любые комбинации подстановочных знаков, которые поддерживаются операционной системой.

Функции возвращают сведения о файле в структуре `_finddata_t`, которая определена в IO.h. Различные функции в данном семействе используют множество вариантов структуры `_finddata_t` . Базовая структура `_finddata_t` содержит следующие элементы:

`unsigned attrib`<br/>
Атрибут файла.

`time_t time_create`<br/>
Время создания файла (–1L для файловых систем FAT). Это время хранится в формате UTC. Для преобразования в местное время используйте функцию [localtime_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md).

`time_t time_access`<br/>
Время последнего доступа к файлу (–1L для файловых систем FAT). Это время хранится в формате UTC. Для преобразования в местное время используйте функцию `localtime_s`.

`time_t time_write`<br/>
Время последней записи в файл. Это время хранится в формате UTC. Для преобразования в местное время используйте функцию `localtime_s`.

`_fsize_t size`<br/>
Длина файла в байтах.

`char name` [`_MAX_PATH`] Имя соответствующего файла или каталога без пути с конечным нуль-символом.

В файловых системах, которые не поддерживают время создания и последнего обращения к файлу (например, в системе FAT), поля `time_create` и `time_access` всегда содержат значение –1L.

`_MAX_PATH` определен в Stdlib.h как 260 байт.

Задание целевых атрибутов (например `_A_RDONLY`) для ограничения операции поиска невозможно. Эти атрибуты возвращаются в поле `attrib` структуры `_finddata_t` и могут иметь следующие значения (определенные в IO.h). Пользователи не должны считать эти значения единственно возможными для поля `attrib` .

`_A_ARCH`<br/>
Архив. Устанавливается при изменении файла и очищается командой **BACKUP** . Значение: 0x20.

`_A_HIDDEN`<br/>
Скрытый файл. Обычно не виден команде DIR, если не используется параметр **/AH** . Возвращает сведения об обычных файлах и файлах, имеющих этот атрибут. Значение: 0x02.

`_A_NORMAL`<br/>
Нормальный. У файла не установлены никакие другие атрибуты, чтение и запись возможны без ограничений. Значение: 0x00.

`_A_RDONLY`<br/>
Только для чтения. Файл невозможно открыть для записи; также невозможно создать файл с этим именем. Значение: 0x01.

`_A_SUBDIR`<br/>
Подкаталог. Значение: 0x10.

`_A_SYSTEM`<br/>
Системный файл. Обычно не виден команде **DIR** , если не используется параметр **/A** или **/A:S** . Значение: 0x04.

Функция`_findnext` находит следующее имя, если таковое имеется, которое соответствует аргументу `filespec` , указанному в предыдущем вызове функции `_findfirst`. Аргумент `fileinfo` должен указывать на структуру, инициализированную предыдущим вызовом функции `_findfirst`. Если обнаружено соответствие, содержимое структуры `fileinfo` изменяется, как описано выше. В противном случае оно остается неизменным. Функция`_findclose` закрывает указанный дескриптор поиска и освобождает все связанные ресурсы для функций `_findfirst` и `_findnext`. Дескриптор, возвращенный ранее функцией `_findfirst` или `_findnext` , необходимо сначала передать в функцию `_findclose`, чтобы можно было выполнять операции изменения (например, удаление) в каталогах, которые образуют переданные им пути.

Функции `_find` допускают вложение. Например, если вызов функции `_findfirst` или `_findnext` нашел файл, являющийся подкаталогом, новый поиск можно начать другим вызовом функции `_findfirst` или `_findnext`.

`_wfindfirst` и `_wfindnext` — это версии функций `_findfirst` и `_findnext`для расширенных символов. Аргумент структуры версий для расширенных символов имеет тип данных `_wfinddata_t`, который определен в файлах IO.h и Wchar.h. Поля этого типа данных совпадают с полями `_finddata_t` типа данных, за исключением того, что в `_wfinddata_t` поле имени используется тип, **`wchar_t`** а не тип **`char`** . В остальном поведение функций `_wfindfirst` и `_wfindnext` не отличается от поведения функций `_findfirst` и `_findnext`.

Функции`_findfirst` и `_findnext` используют 64-разрядный тип времени. Если необходимо использовать прежний 32-разрядный тип времени, можно определить `_USE_32BIT_TIME_T`. Версии этих функций, в именах которых имеется суффикс `32` , используют 32-разрядный тип времени; версии с суффиксом `64` используют 64-разрядный тип времени.

Функции `_findfirst32i64`, `_findnext32i64`, `_wfindfirst32i64`и `_wfindnext32i64` также ведут себя идентично версиям этих функций с 32-разрядным типом времени, за исключением того, что они используют и возвращают 64-разрядные значения длины файлов. Функции `_findfirst64i32`, `_findnext64i32`, `_wfindfirst64i32` и `_wfindnext64i32` используют 64-разрядный тип времени, но 32-разрядные значения длины файлов. Эти функции используют соответствующие варианты типа `_finddata_t` , в которых поля имеют разные типы для времени и размера файла.

`_finddata_t` фактически представляет собой макрос, который преобразуется в `_finddata64i32_t` (или `_finddata32_t` , если определена константа `_USE_32BIT_TIME_T` ). В следующей таблице приведены сводные сведения об этих вариантах `_finddata_t`:

|Структура|Тип времени|Тип размера файла|
|---------------|---------------|--------------------|
|`_finddata_t`, `_wfinddata_t`|`__time64_t`|`_fsize_t`|
|`_finddata32_t`, `_wfinddata32_t`|`__time32_t`|`_fsize_t`|
|`__finddata64_t`, `__wfinddata64_t`|`__time64_t`|**`__int64`**|
|`_finddata32i64_t`, `_wfinddata32i64_t`|`__time32_t`|**`__int64`**|
|`_finddata64i32_t`, `_wfinddata64i32_t`|`__time64_t`|`_fsize_t`|

`_fsize_t`значение **`typedef`** для **`unsigned long`** (32 бит).

## <a name="example"></a>Пример

```c
// crt_find.c
// This program uses the 32-bit _find functions to print
// a list of all files (and their attributes) with a .C extension
// in the current directory.

#include <stdio.h>
#include <stdlib.h>
#include <io.h>
#include <time.h>

int main( void )
{
   struct _finddata_t c_file;
   intptr_t hFile;

   // Find first .c file in current directory
   if( (hFile = _findfirst( "*.c", &c_file )) == -1L )
      printf( "No *.c files in current directory!\n" );
   else
   {
      printf( "Listing of .c files\n\n" );
      printf( "RDO HID SYS ARC  FILE         DATE %25c SIZE\n", ' ' );
      printf( "--- --- --- ---  ----         ---- %25c ----\n", ' ' );
      do {
         char buffer[30];
         printf( ( c_file.attrib & _A_RDONLY ) ? " Y  " : " N  " );
         printf( ( c_file.attrib & _A_HIDDEN ) ? " Y  " : " N  " );
         printf( ( c_file.attrib & _A_SYSTEM ) ? " Y  " : " N  " );
         printf( ( c_file.attrib & _A_ARCH )   ? " Y  " : " N  " );
         ctime_s( buffer, _countof(buffer), &c_file.time_write );
         printf( " %-12s %.24s  %9ld\n",
            c_file.name, buffer, c_file.size );
      } while( _findnext( hFile, &c_file ) == 0 );
      _findclose( hFile );
   }
}
```

```Output
Listing of .c files

RDO HID SYS ARC  FILE         DATE                           SIZE
--- --- --- ---  ----         ----                           ----
N   N   N   Y   blah.c       Wed Feb 13 09:21:42 2002       1715
N   N   N   Y   test.c       Wed Feb 06 14:30:44 2002        312
```

## <a name="see-also"></a>См. также раздел

[Системные вызовы](../c-runtime-library/system-calls.md)
