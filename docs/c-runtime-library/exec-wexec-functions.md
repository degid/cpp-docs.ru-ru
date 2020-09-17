---
title: Функции _exec, _wexec
ms.date: 11/04/2016
api_location:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _texecve
- texecl
- _texeclpe
- texecve
- texecv
- texeclp
- texecle
- exec
- texeclpe
- _texecvp
- _texecl
- _texecle
- wexec
- _exec
- _texeclp
- _texecvpe
- texecvpe
- _texecv
- _wexec
helpviewer_keywords:
- _texecle function
- _texecv function
- texeclpe function
- texecle function
- _texecl function
- texecv function
- _texeclp function
- _texecve function
- texecl function
- texecve function
- exec function
- texeclp function
- texecvp function
- texecvpe function
- processes, executing new
- _texecvp function
- _texeclpe function
- _wexec functions
- wexec functions
- _exec function
- _texecvpe function
ms.assetid: a261df93-206a-4fdc-b8ac-66aa7db83bc6
ms.openlocfilehash: ecfcf88b09a4383fc050e9737a0ffe7203f9a050
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839729"
---
# <a name="_exec-_wexec-functions"></a>Функции _exec, _wexec

Каждая функция в этом семействе загружает и выполняет новый процесс.

:::row:::
   :::column span="":::
      [_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)\
      [_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)\
      [_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)
   :::column-end:::
   :::column span="":::
      [_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)\
      [_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)\
      [_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)
   :::column-end:::
   :::column span="":::
      [_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)\
      [_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)
   :::column-end:::
:::row-end:::

Буква в конце имени функции определяет вариацию.

|Суффикс функции _exec|Описание|
|----------------------------|-----------------|
|`e`|`envp`, массив указателей на параметры среды, передается в новый процесс.|
|`l`|Аргументы командной строки передаются по отдельности в функцию `_exec`. Обычно используется, когда число параметров нового процесса известно заранее.|
|`p`|Переменная среды `PATH` используется для поиска файла для выполнения.|
|`v`|`argv`, массив указателей на аргументы командной строки, передается в `_exec`. Обычно используется, когда число параметров нового процесса непостоянно.|

## <a name="remarks"></a>Примечания

Каждая функция `_exec` загружает и выполняет новый процесс. Все функции `_exec` используют одну и ту же функцию операционной системы ([CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw)). Функции `_exec` автоматически обрабатывают аргументы строки многобайтовых символов соответствующим образом, распознавая последовательности многобайтовых символов согласно многобайтовой кодовой странице, используемой в данный момент. Функции `_wexec` — это версии функций `_exec` с расширенными символами. Поведение функций `_wexec` идентично их аналогам из семейства `_exec` за исключением того, что они не обрабатывают строки многобайтовых символов.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_texecl`|`_execl`|`_execl`|`_wexecl`|
|`_texecle`|`_execle`|`_execle`|`_wexecle`|
|`_texeclp`|`_execlp`|`_execlp`|`_wexeclp`|
|`_texeclpe`|`_execlpe`|`_execlpe`|`_wexeclpe`|
|`_texecv`|`_execv`|`_execv`|`_wexecv`|
|`_texecve`|`_execve`|`_execve`|`_wexecve`|
|`_texecvp`|`_execvp`|`_execvp`|`_wexecvp`|
|`_texecvpe`|`_execvpe`|`_execvpe`|`_wexecvpe`|

Параметр `cmdname` указывает файл, который будет выполняться как новый процесс. Он может указывать полный путь (от корневого каталога), частичный путь (от текущего рабочего каталога) или имя файла. Если `cmdname` не указывает расширение файла или не заканчивается точкой (.), функция `_exec` выполняет поиск названного файла. Если поиск не дает результатов, функция пытается найти то же основное имя с расширением COM, а затем с расширениями EXE, BAT и CMD. Если параметр `cmdname` включает расширение файла, для поиска используется только это расширение. Если `cmdname` заканчивается точкой, функция `_exec` выполняет поиск `cmdname` без расширения файла. `_execlp`, `_execlpe`, `_execvp` и `_execvpe` выполняют поиск `cmdname` (используя те же процедуры) в каталогах, указанных переменной среды `PATH`. Если `cmdname` содержит описатель диска или любые косые черты (то есть является относительным путем), функция `_exec` выполняет поиск только указанного файла, а не пути.

Параметры передаются в новый процесс путем предоставления одного или нескольких указателей на строки символов как параметров в вызове `_exec`. Эти строки символов формируют список параметров для нового процесса. Общая длина наследуемых параметров среды и строк, формирующих список параметров для нового процесса, не должна превышать 32 КБ. Символ null, завершающий строку ('\0'), для каждой строки не учитывается, однако учитываются символы пробелов (вставляемые автоматически для разделения параметров).

> [!NOTE]
> Пробелы, встроенные в строки, могут вызывать непредвиденное поведение. Например, если передать в функцию `_exec` строку `"hi there"`, это приведет к тому, что новый процесс получит два аргумента: `"hi"` и `"there"`. Если предполагалось, что новый процесс должен открыть файл с именем hi there, произойдет сбой процесса. Этого можно избежать, заключив строку в кавычки: `"\"hi there\""`.

> [!IMPORTANT]
> Не передавайте данные, вводимые пользователем, в функцию `_exec`, не выбрав это содержимое явно. `_exec` вызывает функцию [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw), поэтому имейте в виду, что неполные пути могут привести к потенциальным уязвимостям безопасности.

Эти функции `_exec` проверяют свои параметры. Если ожидаемые параметры являются пустыми указателями или строками либо они пропущены, функции `_exec` вызывают обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают -1. Новые процессы не выполняются.

Указатели аргументов могут передаваться как отдельные параметры (в `_execl`, `_execle`, `_execlp` и `_execlpe`) или как массивы указателей (в `_execv`, `_execve`, `_execvp` и `_execvpe`). По крайней мере один параметр, `arg0`, должен быть передан в новый процесс; этот параметр — `argv`[0] нового процесса. Обычно этот параметр является копией `cmdname` (другое значение не создает ошибку).

Вызовы функций `_execl`, `_execle`, `_execlp` и `_execlpe` обычно используются, когда число параметров известно заранее. Параметр `arg0`, как правило, является указателем на `cmdname`. Параметры с `arg1` по `argn` указывают на строку символов, формирующую новый список параметров. За параметром `argn` должен следовать пустой указатель, отмечающий конец списка параметров.

Функции `_execv`, `_execve`, `_execvp` и `_execvpe` можно вызывать, когда число параметров в новом процессе не определено. Указатели на параметры передаются как массив, `argv`. Параметр `argv`[0] обычно является указателем на `cmdname`. Параметры с `argv`[1] по `argv`[`n`] указывают на строки символов, формирующие новый список параметров. Параметр `argv`[`n` +1] должен быть указателем на **NULL**, отмечающим конец списка параметров.

Файлы, открытые во время вызова функции `_exec`, остаются открытыми в новом процессе. В вызовах `_execl`, `_execlp`, `_execv` и `_execvp` новый процесс наследует среду вызывающего процесса. Вызовы функций `_execle`, `_execlpe`, `_execve` и `_execvpe` изменяют среду для нового процесса, передавая список параметров среды с помощью параметра `envp`. `envp` — это массив указателей символов, каждый элемент которого (за исключением последнего) указывает на строку, завершающуюся символом null, определенную в переменной среды. Такие строки обычно имеют вид `NAME`=`value`, где `NAME` — это имя переменной среды, а `value` — строковое значение, задаваемое для данной переменной. (Обратите внимание, что `value` не заключено в двойные кавычки.) Последний элемент `envp` массива должен иметь **значение NULL**. Если же значение самого параметра `envp` — **NULL**, новый процесс наследует параметры среды вызывающего процесса.

Программа, выполняемая с одной из функций `_exec`, всегда загружается в память, как если бы для поля максимального объема выделяемой памяти в заголовке EXE-файла было задано значение по умолчанию 0xFFFFH.

Вызовы `_exec` не сохраняют режимы преобразования открытых файлов. Если новый процесс должен использовать файлы, наследуемые из вызывающего процесса, используйте подпрограмму [_setmode](../c-runtime-library/reference/setmode.md), чтобы задать нужный режим преобразования для этих файлов. Перед вызовом функции `fflush` необходимо явно сбросить (используя ключевое слово `_flushall` или `_exec`) или закрыть все потоки. Сигнальные параметры не сохраняются в новых процессах, создаваемых вызовом подпрограмм `_exec`. Сигнальные параметры сбрасываются до значений по умолчанию в новом процессе.

## <a name="example"></a>Пример

```c
// crt_args.c
// Illustrates the following variables used for accessing
// command-line arguments and environment variables:
// argc  argv  envp
// This program will be executed by crt_exec which follows.

#include <stdio.h>

int main( int argc,  // Number of strings in array argv
char *argv[],       // Array of command-line argument strings
char **envp )       // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    printf( "\nCommand-line arguments:\n" );
    for( count = 0; count < argc; count++ )
        printf( "  argv[%d]   %s\n", count, argv[count] );

    // Display each environment variable.
    printf( "\nEnvironment variables:\n" );
    while( *envp != NULL )
        printf( "  %s\n", *(envp++) );

    return;
}
```

Запустите следующую программу, чтобы выполнить Crt_args.exe:

```c
// crt_exec.c
// Illustrates the different versions of exec, including
//      _execl          _execle          _execlp          _execlpe
//      _execv          _execve          _execvp          _execvpe
//
// Although CRT_EXEC.C can exec any program, you can verify how
// different versions handle arguments and environment by
// compiling and specifying the sample program CRT_ARGS.C. See
// "_spawn, _wspawn Functions" for examples of the similar spawn
// functions.

#include <stdio.h>
#include <conio.h>
#include <process.h>

char *my_env[] =     // Environment for exec?e
{
   "THIS=environment will be",
   "PASSED=to new process by",
   "the EXEC=functions",
   NULL
};

int main( int ac, char* av[] )
{
   char *args[4];
   int ch;
   if( ac != 3 ){
      fprintf( stderr, "Usage: %s <program> <number (1-8)>\n", av[0] );
      return;
   }

   // Arguments for _execv?
   args[0] = av[1];
   args[1] = "exec??";
   args[2] = "two";
   args[3] = NULL;

   switch( atoi( av[2] ) )
   {
   case 1:
      _execl( av[1], av[1], "_execl", "two", NULL );
      break;
   case 2:
      _execle( av[1], av[1], "_execle", "two", NULL, my_env );
      break;
   case 3:
      _execlp( av[1], av[1], "_execlp", "two", NULL );
      break;
   case 4:
      _execlpe( av[1], av[1], "_execlpe", "two", NULL, my_env );
      break;
   case 5:
      _execv( av[1], args );
      break;
   case 6:
      _execve( av[1], args, my_env );
      break;
   case 7:
      _execvp( av[1], args );
      break;
   case 8:
      _execvpe( av[1], args, my_env );
      break;
   default:
      break;
   }

   // This point is reached only if exec fails.
   printf( "\nProcess was not execed." );
   exit( 0 );
}
```

## <a name="requirements"></a>Требования

**Заголовок:** process.h

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../c-runtime-library/process-and-environment-control.md)<br/>
[рвал](../c-runtime-library/reference/abort.md)<br/>
[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)<br/>
[_spawn, функции _wspawn](../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)
