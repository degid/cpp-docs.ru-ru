---
title: "fopen_s, _wfopen_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfopen_s
- fopen_s
apilocation:
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
apitype: DLLExport
f1_keywords:
- fopen_s
- _tfopen_s
- _wfopen_s
dev_langs:
- C++
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
caps.latest.revision: 41
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 168d1cd797f9f7d6080f2da7aefeb8859c7f2232
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="fopens-wfopens"></a>fopen_s, _wfopen_s
Открывает файл. Это версии функций [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t fopen_s(   
   FILE** pFile,  
   const char *filename,  
   const char *mode   
);  
errno_t _wfopen_s(  
   FILE** pFile,  
   const wchar_t *filename,  
   const wchar_t *mode   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `pFile`  
 Указатель на файловый указатель, который получит указатель на открытый файл.  
  
 [in] `filename`  
 Имя файла.  
  
 [in] `mode`  
 Тип разрешенного доступа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль в случае успеха или код ошибки в случае неудачи. Дополнительные сведения об этих кодах ошибки см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`pFile`|`filename`|`mode`|Возвращаемое значение|Содержимое `pFile`|  
|-------------|----------------|------------|------------------|------------------------|  
|`NULL`|any|любые|`EINVAL`|без изменений|  
|any|`NULL`|любые|`EINVAL`|без изменений|  
|any|any|NULL|`EINVAL`|без изменений|  
  
## <a name="remarks"></a>Примечания  
 Файлы, открытые с помощью `fopen_s` и `_wfopen_s`, не поддерживают совместный доступ. Если требуется совместный доступ к файлу, используйте функции [_fsopen, _wfsopen](../../c-runtime-library/reference/fsopen-wfsopen.md) с соответствующей константой режима совместного доступа — например, `_SH_DENYNO` для совместного чтения или записи.  
  
 Функция `fopen_s` открывает файл, заданный параметром `filename`. `_wfopen_s` — это двухбайтовая версия `fopen_s`; аргументы для `_wfopen_s` представляют собой двухбайтовые строки. Поведение `_wfopen_s` и `fopen_s` идентично в противном случае.  
  
 Функция `fopen_s` принимает пути, допустимые в файловой системе во время выполнения; UNC-пути и пути, в которых фигурируют сопоставленные сетевых диски, принимаются функцией `fopen_s`, если система, которая выполняет код, имеет доступ к общему или сетевому диску в момент выполнения. При построении путей для `fopen_s` убедитесь, что драйверы, пути или сетевые общие папки будут доступны в среде выполнения. В пути в качестве разделителей каталогов можно использовать прямую (/) или обратную (\\) косую черту.  
  
 Эти функции проверяют свои параметры. Если параметр `pFile`, `filename` или `mode` представляет собой указатель NULL, эти функции создают исключение недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
 Всегда проверяйте возвращаемое значение, чтобы узнать, успешно ли выполнила свою работу функция, прежде чем выполнять какие-либо дальнейшие операции с файлом. При возникновении ошибки возвращается ее код и задается глобальная переменная `errno`. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="unicode-support"></a>Поддержка Юникода  
 `fopen_s` поддерживает файловые потоки Юникода. Чтобы открыть новый или существующий файл Юникода, передайте флаг `ccs`, задающий нужную кодировку, в `fopen_s`:  
  
 `fopen_s(&fp, "newfile.txt", "rw, ccs=`*кодировки*`");`  
  
 Допустимые значения *кодирование* , `UNICODE`, `UTF-8`, и `UTF-16LE`. Если существует не указано значение для *кодирование*, `fopen_s` использует кодировку ANSI.  
  
 Если файл уже существует и открыт для чтения или добавления, метка порядка байтов (BOM), если она присутствует в файле, определяет кодировку. Кодировка, заданная меткой BOM, имеет приоритет над кодировкой, заданной флагом `ccs`. Заданная флагом `ccs` кодировка используется, только если метка BOM отсутствует или речь идет о новом файле.  
  
> [!NOTE]
>  Обнаружение метки BOM применяется только к файлам, которые будут открываться в режиме Юникода (т. е. путем передачи флага `ccs`).  
  
 В следующей таблице приведены режимы, которые используются для различных флагов `ccs`, передаваемых `fopen_s`, и для меток порядка байтов в файле.  
  
### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>Кодирования, используемые на основе CCS-флага и метки BOM  
  
|Флаг`ccs` |Нет метки BOM (или новый файл)|BOM: UTF-8|BOM: UTF-16|  
|----------------|----------------------------|-----------------|------------------|  
|`UNICODE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
|`UTF-8`|`UTF-8`|`UTF-8`|`UTF-16LE`|  
|`UTF-16LE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
  
 В файлы, открываемые для записи в режиме Юникода, метка BOM записывается автоматически.  
  
 Если `mode` — «, ccs =*кодирование*», `fopen_s` сначала пытается открыть файл с доступом на чтение и запись. Если эта операция завершается успешно, функция считывает метку BOM, чтобы определить кодировку для файла; если операция завершается сбоем, функция использует для файла кодировку по умолчанию. В любом случае `fopen_s` затем снова открывает файл с доступом только на запись. (Это актуально только для режима `a`, но не `a+`.)  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfopen_s`|`fopen_s`|`fopen_s`|`_wfopen_s`|  
  
 Символьная строка `mode` указывает тип доступа, который запрошен для файла, следующим образом.  
  
 `"r"`  
 Открывает для чтения. Если файл не существует или его невозможно найти, вызов `fopen_s` завершается ошибкой.  
  
 `"w"`  
 Открывает пустой файл для записи. Если файл существует, его содержимое удаляется.  
  
 `"a"`  
 Открывает файл для записи в конец файла (добавления) без удаления маркера конца файла перед записью в файл новых данных. Создает файл, если он не существует.  
  
 `"r+"`  
 Открывает для чтения и записи. (Файл должен существовать.)  
  
 `"w+"`  
 Открывает пустой файл для чтения и записи. Если файл существует, его содержимое удаляется.  
  
 `"a+"`  
 Открывается для чтения и добавления. Операция добавления включает в себя удаление маркера конца файла перед записью новых данных в файл. По завершении записи маркер конца файла восстанавливается. Создает файл, если он не существует.  
  
 Если файл открывается с использованием типа доступа `"a"` или `"a+"`, все операции записи выполняются в конце файла. Файловый указатель может быть перемещен с помощью `fseek` или `rewind`, но он всегда возвращается в конец файла перед выполнением какой-либо операции записи, поэтому существующие данные не могут быть перезаписаны.  
  
 Режим `"a"` не удаляет маркер конца файла перед добавлением в файл. После добавления команда MS-DOS TYPE отображает данные только до первоначального маркера конца файла, но не данные, добавленные в файл. Перед добавлением в файл режим `"a+"` удаляет маркер конца файла. После добавления команда TYPE MS-DOS отображает все данные в файле. Режим `"a+"` необходим для добавления данных в потоковый файл, завершаемый маркером конца файла CTRL+Z.  
  
 Когда `"r+"`, `"w+",` или `"a+"` задан тип доступа, чтение и запись разрешены. (Считается, что файл открыт для "обновления"). Однако при переходе от чтения к записи операция ввода должна получить маркер конца файла. Если маркер конца файла отсутствует, необходимо воспользоваться промежуточным вызовом функции позиционирования в файле. Функции позиционирования в файле — это `fsetpos`, `fseek` и `rewind`. При переходе от записи к чтению необходимо воспользоваться промежуточным вызовом либо функции `fflush`, либо функции позиционирования в файле.  
  
 В дополнение к указанным выше значениям, в параметр `mode` можно добавить следующие символы, чтобы задать режим преобразования для символов новой строки:  
  
 `t`  
 Откройте файл в текстовом (переведенном) режиме. В этом режиме CTRL+Z интерпретируется как символ конца файла на входе. В файлах, открытых для чтения/записи с использованием режима `"a+"`, `fopen_s` проверяет наличие символа CTRL+Z в конце файла и удаляет его, если это возможно. Это делается потому, что использование функций `fseek` и `ftell` для перемещения в пределах файла, который заканчивается символом CTRL+Z, может вызвать неправильное поведение `fseek` вблизи конца файла.  
  
 Также в текстовом режиме сочетания символов возврата перевода каретки преобразуются в один символ перевода строки на входе и символы перевода строки преобразуются на выходе в сочетания перевода строки возврата каретки. Если функция ввода-вывода потока Юникода работает в текстовом режиме (по умолчанию) исходный или конечный поток рассматривается как последовательность многобайтовых символов. Поэтому входные функции потока Юникода преобразуют многобайтовые символы в расширенные (как если бы для этого вызывалась функция `mbtowc` ). По той же причине выходные функции потока Юникода преобразуют расширенные символы в многобайтовые (как если бы для этого вызывалась функция `wctomb` ).  
  
 `b`  
 При открытии в двоичном (непреобразованном) режиме преобразования, включающие символы возврата каретки и перевода строки, подавляются.  
  
 Если символ `t` или `b` в параметре `mode`не указан, режим преобразования по умолчанию определяется глобальной переменной [_fmode](../../c-runtime-library/fmode.md). Если символ `t` или `b` указан как префикс аргумента, функция завершается с ошибкой и возвращает `NULL`.  
  
 Дополнительные сведения об использовании текстового и двоичного режимов в Юникоде и многобайтовом потоковом вводе-выводе см. в разделах [Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md) и [Ввод-вывод в поток в кодировке Юникод в текстовом и двоичном режиме](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
 `c`  
 Включите флажок фиксации для связанного объекта `filename` , чтобы содержимое файлового буфера записывалось непосредственно на диск при вызове `fflush` или `_flushall` .  
  
 `n`  
 Сбросьте флажок фиксации для связанного объекта `filename` , задайте для него значение "без фиксации". Это значение по умолчанию. Оно также переопределяет глобальный флаг фиксации при соединении программы с COMMODE.OBJ. Значение по умолчанию глобального флага фиксации — "без фиксации" (no-commit), если только программа не связана явно с файлом COMMODE.OBJ (см. статью [Link Options](../../c-runtime-library/link-options.md)).  
  
 `N`  
 Указывает, что файл не наследуется дочерними процессами.  
  
 `S`  
 Указывает, что кэширование оптимизировано для последовательного доступа с диска, но не ограничивается им.  
  
 `R`  
 Указывает, что кэширование оптимизировано для случайного доступа с диска, но не ограничивается им.  
  
 `T`  
 Определяет файл как временный. По возможности он не сбрасывается на диск.  
  
 `D`  
 Определяет файл как временный. Он удаляется, если закрывается последний указатель файла.  
  
 `ccs=ENCODING`  
 Задает набор кодированных символов, которые требуется использовать для этого файла (UTF-8, UTF-16LE и UNICODE). Если требуется использовать кодировку ANSI, не указывайте никакое значение.  
  
 Допустимые символы для строки `mode`, используемой в функциях `fopen_s` и `_fdopen`, соответствуют аргументам `oflag`, которые используются в функциях [_open](../../c-runtime-library/reference/open-wopen.md) и [_sopen](../../c-runtime-library/reference/sopen-wsopen.md), следующим образом.  
  
|Символы в строке режима|Эквивалентное значение `oflag` для `_open`/`_sopen`|  
|-------------------------------|----------------------------------------------------|  
|`a`|`_O_WRONLY &#124; _O_APPEND` (обычно `_O_WRONLY &#124; _O_CREAT &#124; _O_APPEND`)|  
|`a+`|`_O_RDWR &#124; _O_APPEND` (обычно `_O_RDWR &#124; _O_APPEND &#124; _O_CREAT`)|  
|`r`|`_O_RDONLY`|  
|`r+`|`_O_RDWR`|  
|`w`|`_O_WRONLY` (обычно `_O_WRONLY &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`w+`|`_O_RDWR` (обычно `_O_RDWR &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`b`|`_O_BINARY`|  
|`t`|`_O_TEXT`|  
|`c`|Нет|  
|`n`|Нет|  
|`S`|`_O_SEQUENTIAL`|  
|`R`|`_O_RANDOM`|  
|`T`|`_O_SHORTLIVED`|  
|`D`|`_O_TEMPORARY`|  
|`ccs=UNICODE`|`_O_WTEXT`|  
|`ccs=UTF-8`|`_O_UTF8`|  
|`ccs=UTF-16LE`|`_O_UTF16`|  
  
 Если вы используете режим `rb`, не собираетесь портировать код, планируете считывать большое количество файлов или не заботитесь о быстродействии сети, можно рассмотреть вариант с использованием размещенных в памяти файлов Win32.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`fopen_s`|\<stdio.h>|  
|`_wfopen_s`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
 Параметры `c`, `n` и `t` `mode` представляют собой расширения Майкрософт для `fopen_s` и `_fdopen`, и их не следует использовать, если требуется обеспечить переносимость ANSI.  
  
## <a name="example"></a>Пример  
  
```C  
// crt_fopen_s.c  
// This program opens two files. It uses  
// fclose to close the first file and  
// _fcloseall to close all remaining files.  
  
#include <stdio.h>  
  
FILE *stream, *stream2;  
  
int main( void )  
{  
   errno_t err;  
  
   // Open for read (will fail if file "crt_fopen_s.c" does not exist)  
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );  
   if( err == 0 )  
   {  
      printf( "The file 'crt_fopen_s.c' was opened\n" );  
   }  
   else  
   {  
      printf( "The file 'crt_fopen_s.c' was not opened\n" );  
   }  
  
   // Open for write   
   err = fopen_s( &stream2, "data2", "w+" );  
   if( err == 0 )  
   {  
      printf( "The file 'data2' was opened\n" );  
   }  
   else  
   {  
      printf( "The file 'data2' was not opened\n" );  
   }  
  
   // Close stream if it is not NULL   
   if( stream )  
   {  
      err = fclose( stream );  
      if ( err == 0 )  
      {  
         printf( "The file 'crt_fopen_s.c' was closed\n" );  
      }  
      else  
      {  
         printf( "The file 'crt_fopen_s.c' was not closed\n" );  
      }  
   }  
  
   // All other files are closed:  
   int numclosed = _fcloseall( );  
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );  
}  
```  
  
```Output  
The file 'crt_fopen_s.c' was opened  
The file 'data2' was opened  
Number of files closed by _fcloseall: 1  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)