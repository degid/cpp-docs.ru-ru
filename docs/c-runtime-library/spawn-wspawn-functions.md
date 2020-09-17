---
title: Функции _spawn, _wspawn
ms.date: 11/04/2016
api_location:
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _spawn
- _tspawnlp
- _tspawnlpe
- _tspawnve
- _tspawnvp
- _tspawnvpe
- _tspawnl
- spawn
- _tspawnv
- _tspawnle
- wspawn
helpviewer_keywords:
- _tspawnve function
- _spawn functions
- _tspawnlpe function
- tspawnvpe function
- processes, creating
- tspawnve function
- _tspawnvp function
- spawn functions
- tspawnl function
- tspawnlp function
- _tspawnvpe function
- _tspawnl function
- tspawnvp function
- tspawnv function
- processes, executing new
- _tspawnv function
- tspawnle function
- process creation
- _tspawnlp function
- tspawnlpe function
- _tspawnle function
ms.assetid: bb47c703-5216-4e09-8023-8cf25bbf2cf9
ms.openlocfilehash: 2f6aa420d7e6bb736721c4a68ff6451121da26ab
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840418"
---
# <a name="_spawn-_wspawn-functions"></a>Функции _spawn, _wspawn

Каждая из функций `_spawn` создает и запускает новый процесс:

:::row:::
   :::column span="":::
      [_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)\
      [_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)\
      [_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)\
      [_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)\
   :::column-end:::
   :::column span="":::
      [_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)\
      [_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)\
      [_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)\
      [_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)\
   :::column-end:::
:::row-end:::

Буквы в конце имени функции определяют вариацию.

|Буква|Variant|
|-|-|
| `e`  | `envp`, массив указателей на параметры среды, передается в новый процесс.  |
| `l`  | Аргументы командной строки передаются по отдельности в функцию `_spawn`. Обычно этот суффикс используется, когда число параметров нового процесса известно заранее.  |
| `p`  | Переменная среды `PATH` используется для поиска файла для выполнения.  |
| `v`  | `argv`, массив указателей на аргументы командной строки, передается в функцию `_spawn`. Обычно этот суффикс используется, когда число параметров нового процесса не постоянно.  |

## <a name="remarks"></a>Примечания

Каждая из функций `_spawn` создает и выполняет новый процесс. Такие функции автоматически обрабатывают аргументы в виде многобайтовых строк требуемым образом, распознавая многобайтовые последовательности символов в соответствии с текущей многобайтовой кодовой страницей. Функции `_wspawn` представляют собой версии функций `_spawn` для расширенных символов и не обрабатывают многобайтовые строки. В противном случае функции `_wspawn` ведут себя точно так же, как аналогичные функции `_spawn`.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_tspawnl`|`_spawnl`|`_spawnl`|`_wspawnl`|
|`_tspawnle`|`_spawnle`|`_spawnle`|`_wspawnle`|
|`_tspawnlp`|`_spawnlp`|`_spawnlp`|`_wspawnlp`|
|`_tspawnlpe`|`_spawnlpe`|`_spawnlpe`|`_wspawnlpe`|
|`_tspawnv`|`_spawnv`|`_spawnv`|`_wspawnv`|
|`_tspawnve`|`_spawnve`|`_spawnve`|`_wspawnve`|
|`_tspawnvp`|`_spawnvp`|`_spawnvp`|`_wspawnvp`|
|`_tspawnvpe`|`_spawnvpe`|`_spawnvpe`|`_wspawnvpe`|

Для загрузки и выполнения нового процесса необходимо обеспечить достаточно памяти. Аргумент `mode` определяет действие, предпринимаемое вызывающим процессом перед вызовом функции `_spawn` и во время ее выполнения. В файле Process.h определяются следующие значения аргумента `mode`:

|Значение|Описание|
|-|-|
| `_P_OVERLAY`  | Перекрывает вызывающий процесс новым процессом, уничтожая вызывающий процесс (тот же эффект, что и при вызовах функций `_exec`).  |
| `_P_WAIT`  | Приостанавливает вызывающий поток до тех пор, пока не будет завершено выполнение нового процесса (синхронная функция `_spawn`).  |
| `_P_NOWAIT` или `_P_NOWAITO`  | Продолжает выполнять вызывающий процесс параллельно с новым процессом (асинхронная функция `_spawn`).  |
| `_P_DETACH`  | Продолжает выполнять вызывающий процесс; новый процесс выполняется в фоновом режиме без доступа к консоли или клавиатуре. Вызовы функции `_cwait` для нового процесса завершаются ошибкой (асинхронная функция `_spawn`).  |

Аргумент `cmdname` определяет файл, который выполняется как новый процесс и может указывать полный путь (от корневого каталога), частичный путь (из текущего рабочего каталога) или просто имя файла. Если `cmdname` не имеет расширения имени файла или не заканчивается точкой (.), функция `_spawn` сначала проверяет расширение COM, затем EXE, BAT и, наконец, CMD.

Если параметр `cmdname` имеет расширение имени файла, для поиска используется только это расширение. Если `cmdname` заканчивается точкой, вызванная функция `_spawn` выполняет поиск `cmdname` без расширения имени файла. Функции `_spawnlp`, `_spawnlpe`, `_spawnvp` и `_spawnvpe` выполняют поиск `cmdname` (используя те же процедуры) в каталогах, указанных в переменной среды `PATH`.

Если `cmdname` содержит описатель диска или какие-либо косые черты (т. е. представляет собой относительный путь), функция `_spawn` выполняет поиск только указанного файла, а не пути.

Раньше некоторые из этих функций присваивали параметру `errno` нулевое значение в случае успеха, теперь при успешном результате значение `errno` остается неизменным, как указано в стандарте С. Если нужно эмулировать старое поведение, перед вызовом этих функций присвойте параметру `errno` нулевое значение.

> [!NOTE]
> Чтобы обеспечить правильную инициализацию и прекращение перекрытия, не используйте функцию `setjmp` или `longjmp` для входа в подпрограмму перекрытия или выхода из нее.

## <a name="arguments-for-the-spawned-process"></a>Аргументы для порожденного процесса

Для передачи аргументов в новый процесс задайте один или нескольких указателей на символьные строки как аргументы вызова функции `_spawn`. Эти символьные строки формируют список аргументов для порожденного процесса. Общая длина строк, формирующих список аргументов для нового процесса, не должна превышать 1024 байтов. Символ null, завершающий строку ('\0'), для каждой строки не учитывается, однако учитываются символы пробелов (вставляемые автоматически для разделения аргументов).

> [!NOTE]
> Пробелы, встроенные в строки, могут вызывать непредвиденное поведение. Например, если передать в функцию `_spawn` строку `"hi there"`, это приведет к тому, что новый процесс получит два аргумента: `"hi"` и `"there"`. Если предполагалось, что новый процесс должен открыть файл с именем hi there, произойдет сбой процесса. Этого можно избежать, заключив строку в кавычки: `"\"hi there\""`.

> [!IMPORTANT]
> Не передавайте данные, вводимые пользователем, в функцию `_spawn`, не выбрав это содержимое явно. `_spawn` вызывает функцию [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw), поэтому имейте в виду, что неполные пути могут привести к потенциальным уязвимостям безопасности.

Указатели аргументов можно передавать как отдельные параметры (в функциях `_spawnl`, `_spawnle`, `_spawnlp` и `_spawnlpe`) или как массивы указателей (в функциях `_spawnv`, `_spawnve`, `_spawnvp` и `_spawnvpe`). В порожденный процесс необходимо передавать хотя бы один аргумент, `arg0` или `argv`[0]. По правилам этот аргумент представляет собой имя программы в том виде, в котором оно бы вводилось в командную строку. Другое значение не создает ошибку.

Вызовы функций `_spawnl`, `_spawnle`, `_spawnlp` и `_spawnlpe` обычно используются, если число аргументов известно заранее. Аргумент `arg0` обычно является указателем на параметр `cmdname`. Аргументы `arg1` – `argn` являются указателями на строки символов, которые образуют новый список аргументов. После `argn` должен следовать указатель на **NULL**, отмечающий конец списка аргументов.

Функции `_spawnv`, `_spawnve`, `_spawnvp` и `_spawnvpe` можно вызывать, если число аргументов в новом процессе не определено. Указатели на аргументы передаются как массив `argv`*.* Аргумент `argv`[0] обычно является указателем на путь в реальном режиме или на имя программы в защищенном режиме, а аргументы с `argv`[1] по `argv`[`n`] — это указатели на символьные строки, формирующие новый список аргументов. Аргумент `argv`[`n` +1] должен быть указателем на **NULL**, отмечающим конец списка аргументов.

## <a name="environment-of-the-spawned-process"></a>Среда порожденного процесса

Файлы, открытые во время вызова функции `_spawn`, остаются открытыми в новом процессе. В вызовах `_spawnl`, `_spawnlp`, `_spawnv` и `_spawnvp` новый процесс наследует среду вызывающего процесса. Вызовы функций `_spawnle`, `_spawnlpe`, `_spawnve` и `_spawnvpe` изменяют среду для нового процесса, передавая список параметров среды с помощью аргумента `envp`. Аргумент `envp` — это массив указателей символов, каждый элемент которого (за исключением последнего) указывает на строку, завершающуюся символом NULL, определенную в переменной среды. Такие строки обычно имеют вид `NAME`=`value`, где `NAME` — это имя переменной среды, а `value` — строковое значение, задаваемое для данной переменной. (Обратите внимание, что `value` не заключено в двойные кавычки.) Последний элемент `envp` массива должен иметь **значение NULL**. Если же значение самого параметра `envp` — **NULL**, порожденный процесс наследует параметры среды родительского процесса.

Функции `_spawn` могут передавать все сведения об открытых файлах, включая режим преобразования, в новый процесс. Эти сведения передаются в режиме реального времени через запись `C_FILE_INFO` в среде. Обычно код запуска обрабатывает эту запись, а затем удаляет ее из среды. Если же функция `_spawn` порождает процесс, отличный от C, эта запись сохраняется в среде. При печати среды в строке определения для этой записи отображаются графические символы, так как сведения о среде передаются в формате двоичных данных в режиме реального времени. На обычную работу это не влияет. В защищенном режиме сведения о среде передаются в виде текста и поэтому не содержат графических символов.

Перед вызовом функции `fflush` необходимо явно сбросить (используя ключевое слово `_flushall` или `_spawn`) или закрыть все потоки.

В новых процессах, создаваемых при вызове подпрограмм `_spawn`, сигнальные параметры не сохраняются. Вместо этого порожденный процесс сбрасывает параметры сигнала по умолчанию.

## <a name="redirecting-output"></a>Перенаправление выходных данных

Если при вызове функции `_spawn` из библиотеки DLL или приложения с графическим интерфейсом вы хотите перенаправить выходные данные в канал, можно выбрать один из двух вариантов:

- Воспользуйтесь API Win32, чтобы создать канал, вызовите функцию [AllocConsole](/windows/console/allocconsole), задайте значения обработки в структуре запуска и вызовите функцию [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw).

- Вызовите функцию [_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md), которая создаст канал и вызовет приложение с помощью файла **cmd.exe /c** (или **command.exe /c**).

## <a name="example"></a>Пример

```c
// crt_spawn.c
// This program accepts a number in the range
// 1-8 from the command line. Based on the number it receives,
// it executes one of the eight different procedures that
// spawn the process named child. For some of these procedures,
// the CHILD.EXE file must be in the same directory; for
// others, it only has to be in the same path.
//

#include <stdio.h>
#include <process.h>

char *my_env[] =
{
   "THIS=environment will be",
   "PASSED=to child.exe by the",
   "_SPAWNLE=and",
   "_SPAWNLPE=and",
   "_SPAWNVE=and",
   "_SPAWNVPE=functions",
   NULL
};

int main( int argc, char *argv[] )
{
   char *args[4];

   // Set up parameters to be sent:
   args[0] = "child";
   args[1] = "spawn??";
   args[2] = "two";
   args[3] = NULL;

   if (argc <= 2)
   {
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );
      exit( 1 );
   }

   switch (argv[1][0])   // Based on first letter of argument
   {
   case '1':
      _spawnl( _P_WAIT, argv[2], argv[2], "_spawnl", "two", NULL );
      break;
   case '2':
      _spawnle( _P_WAIT, argv[2], argv[2], "_spawnle", "two",
               NULL, my_env );
      break;
   case '3':
      _spawnlp( _P_WAIT, argv[2], argv[2], "_spawnlp", "two", NULL );
      break;
   case '4':
      _spawnlpe( _P_WAIT, argv[2], argv[2], "_spawnlpe", "two",
                NULL, my_env );
      break;
   case '5':
      _spawnv( _P_OVERLAY, argv[2], args );
      break;
   case '6':
      _spawnve( _P_OVERLAY, argv[2], args, my_env );
      break;
   case '7':
      _spawnvp( _P_OVERLAY, argv[2], args );
      break;
   case '8':
      _spawnvpe( _P_OVERLAY, argv[2], args, my_env );
      break;
   default:
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );
      exit( 1 );
   }
   printf( "from SPAWN!\n" );
}
```

```Output
child process output
from SPAWN!
```

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../c-runtime-library/process-and-environment-control.md)<br/>
[рвал](../c-runtime-library/reference/abort.md)<br/>
[atexit](../c-runtime-library/reference/atexit.md)<br/>
[_exec, функции _wexec](../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_flushall](../c-runtime-library/reference/flushall.md)<br/>
[_getmbcp](../c-runtime-library/reference/getmbcp.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)<br/>
[_setmbcp](../c-runtime-library/reference/setmbcp.md)<br/>
[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)
