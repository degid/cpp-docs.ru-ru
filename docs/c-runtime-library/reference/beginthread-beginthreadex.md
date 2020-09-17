---
title: _beginthread, _beginthreadex
ms.date: 4/2/2020
api_name:
- _beginthread
- _beginthreadex
- _o__beginthread
- _o__beginthreadex
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
- beginthread
- _beginthread
- beginthreadex
- _beginthreadex
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
ms.openlocfilehash: 29458f2d752f1fe59778b752480e268f8243f15e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234280"
---
# <a name="_beginthread-_beginthreadex"></a>_beginthread, _beginthreadex

Создает поток.

## <a name="syntax"></a>Синтаксис

```cpp
uintptr_t _beginthread( // NATIVE CODE
   void( __cdecl *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthread( // MANAGED CODE
   void( __clrcall *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthreadex( // NATIVE CODE
   void *security,
   unsigned stack_size,
   unsigned ( __stdcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
uintptr_t _beginthreadex( // MANAGED CODE
   void *security,
   unsigned stack_size,
   unsigned ( __clrcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
```

### <a name="parameters"></a>Параметры

*start_address*<br/>
Начальный адрес процедуры, который начинает выполнение нового потока. Для **_beginthread**соглашением о вызовах является либо [__cdecl](../../cpp/cdecl.md) (для машинного кода), либо [__clrcall](../../cpp/clrcall.md) (для управляемого кода). для **_beginthreadex**это либо [__stdcall](../../cpp/stdcall.md) (для машинного кода), либо [__clrcall](../../cpp/clrcall.md) (для управляемого кода).

*stack_size*<br/>
Размер стека нового потока или 0.

*arglist*<br/>
Список аргументов, передаваемый в новый поток, или **значение NULL**.

*Безопасность*<br/>
Указатель на структуру [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) определяет, может ли возвращаемый дескриптор быть унаследован дочерними процессами. Если *Безопасность* имеет **значение NULL**, маркер не может быть унаследован. Для приложений Windows 95 значение должно быть **равно NULL** .

*инитфлаг*<br/>
Флаги, управляющие начальным состоянием нового потока. Задайте для *инитфлаг* значение 0 для немедленного запуска или **CREATE_SUSPENDED** , чтобы создать поток в приостановленном состоянии. Используйте [ресумесреад](/windows/win32/api/processthreadsapi/nf-processthreadsapi-resumethread) для выполнения потока. Задайте для параметра *инитфлаг* **STACK_SIZE_PARAM_IS_A_RESERVATION** флаг, чтобы использовать *stack_size* в качестве начального резервного размера стека в байтах; Если этот флаг не указан, *stack_size* задает размер фиксации.

*срдаддр*<br/>
Указывает на 32-разрядную переменную, которая получает идентификатор потока. Если он **равен null**, он не используется.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха каждая из этих функций возвращает маркер вновь созданного потока. Однако если вновь созданный поток завершается слишком быстро, **_beginthread** может не возвращать допустимый обработчик. (См. обсуждение в разделе "Примечания".) При возникновении ошибки **_beginthread** возвращает значение-1L, **а для** свойства "переводится" **, если слишком** много потоков, для **еинвал** , если аргумент является недопустимым или размер стека неверен, либо на **еакцес** в случае нехватки ресурсов (например, памяти). При возникновении ошибки **_beginthreadex** возвращает 0, а задаются значения "T0 **" и "** **_doserrno** ".

Если *start_address* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции **устанавливают** значение **еинвал** и возвращают-1.

Дополнительные сведения об этих и других кодах возврата см. в разделе переввод [, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Дополнительные сведения о **uintptr_t**см. в разделе [стандартные типы](../../c-runtime-library/standard-types.md).

## <a name="remarks"></a>Примечания

Функция **_beginthread** создает поток, который начинает выполнение процедуры в *start_address*. Подпрограмма на *start_address* должна использовать **`__cdecl`** (для машинного кода) или **__clrcall** (для управляемого кода) соглашение о вызовах и не должно иметь возвращаемого значения. При возврате потока из этой процедуры он завершается автоматически. Дополнительные сведения о потоках см. в разделе [Поддержка многопоточности для устаревшего кода (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

**_beginthreadex** похож на API-интерфейс Win32 [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) более тесно, чем **_beginthread** . **_beginthreadex** отличается от **_beginthread** следующими способами.

- **_beginthreadex** имеет три дополнительных параметра: *инитфлаг*, *Security*и **среададдр**. Новый поток может быть создан в приостановленном состоянии с заданной безопасностью и доступен с помощью *срдаддр*, который является идентификатором потока.

- Подпрограмма на *start_address* , которая передается в **_beginthreadex** , должна использовать **`__stdcall`** (для машинного кода) или **__clrcall** (для управляемого кода) соглашение о вызовах и должно возвращать код выхода потока.

- **_beginthreadex** возвращает значение 0 в случае сбоя, а не-1L.

- Поток, созданный с помощью **_beginthreadex** , завершается вызовом [_endthreadex](endthread-endthreadex.md).

Функция **_beginthreadex** предоставляет более полный контроль над созданием потока, чем **_beginthread** . Функция **_endthreadex** также более гибка. Например, с помощью **_beginthreadex**можно использовать сведения о безопасности, установить начальное состояние потока (выполняется или приостановлено) и получить идентификатор потока только что созданного потока. Вы также можете использовать обработчик, возвращаемый **_beginthreadex** , с API-интерфейсами синхронизации, которые невозможно выполнить с помощью **_beginthread**.

Безопаснее использовать **_beginthreadex** , чем **_beginthread**. Если поток, созданный **_beginthread** быстро завершает работу, маркер, возвращаемый вызывающему **_beginthread** , может быть недопустимым или указывать на другой поток. Однако маркер, возвращаемый **_beginthreadex** , должен быть закрыт вызывающим объектом **_beginthreadex**, поэтому он гарантированно должен быть допустимым, если **_beginthreadex** не возвращал ошибку.

Чтобы завершить поток, можно явно вызвать [_endthread](endthread-endthreadex.md) или **_endthreadex** . Однако **_endthread** или **_endthreadex** вызывается автоматически, когда поток возвращается из подпрограммы, передаваемой в качестве параметра. Завершение потока с вызовом **_endthread** или **_endthreadex** помогает обеспечить правильное восстановление ресурсов, выделенных для потока.

**_endthread** автоматически закрывает обработчик потока, а **_endthreadex** — нет. Поэтому при использовании **_beginthread** и **_endthread**не следует явно закрывать обработчик потока, вызывая API-интерфейс Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) . Это поведение отличается от функции API Win32 [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) .

> [!NOTE]
> Для исполняемого файла, связанного с LIBCMT. lib, не следует вызывать API Win32 **ExitThread** , чтобы не предотвратить освобождение выделенных ресурсов системой времени выполнения. **_endthread** и **_endthreadex** освободить выделенные ресурсы потока, а затем вызвать **ExitThread**.

Операционная система обрабатывает выделение стека при вызове **_beginthread** или **_beginthreadex** ; не нужно передавать адрес стека потока ни одной из этих функций. Кроме того, аргумент *stack_size* может быть равен 0, в этом случае операционная система использует то же значение, что и стек, указанный для основного потока.

*arglist* — это параметр, передаваемый только что созданному потоку. Как правило, это адрес элемента данных, например строки символов. *arglist* может иметь **значение NULL** , если это не требуется, но **_beginthread** и **_beginthreadex** должны иметь какое-либо значение для передачи в новый поток. Все потоки завершаются, если любой поток вызывает [Abort](abort.md), **Exit**, **_exit**или **ExitProcess**.

Языковой стандарт для нового потока инициализируется с использованием сведений о глобальном текущем языковом стандарте для каждого процесса. Если языковой стандарт для каждого потока включен с помощью вызова [_configthreadlocale](configthreadlocale.md) (глобально или только для новых потоков), поток может изменить свой языковой стандарт независимо от других потоков, вызвав **setlocale** или **_wsetlocale**. Потоки, у которых нет установленного флага локали для каждого потока, могут влиять на сведения о языковых стандартах во всех других потоках, которые также не имеют установленного флага локали для каждого потока, а также всех вновь создаваемых потоков. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Для кода **/clr** **_beginthread** и **_beginthreadex** имеют две перегрузки. Один принимает собственный указатель функции соглашения о вызовах, а другой принимает указатель на функцию **__clrcall** . Первый перегруженный метод не является безопасным для домена приложения и никогда таковым не будет. При написании кода **/CLR** необходимо убедиться, что новый поток входит в правильный домен приложения, прежде чем он будет получать доступ к управляемым ресурсам. Это можно сделать, например, с помощью [функции call_in_appdomain](../../dotnet/call-in-appdomain-function.md). Вторая перегрузка — это Доменная безопасность приложения; вновь созданный поток всегда будет находиться в домене приложения вызывающего объекта **_beginthread** или **_beginthreadex**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_beginthread**|\<process.h>|
|**_beginthreadex**|\<process.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только многопоточные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md) .

Чтобы использовать **_beginthread** или **_beginthreadex**, приложение должно создать связь с одной из многопоточных библиотек времени выполнения C.

## <a name="example"></a>Пример

В следующем примере используются **_beginthread** и **_endthread**.

```C
// crt_BEGTHRD.C
// compile with: /MT /D "_X86_" /c
// processor: x86
#include <windows.h>
#include <process.h>    /* _beginthread, _endthread */
#include <stddef.h>
#include <stdlib.h>
#include <conio.h>

void Bounce( void * );
void CheckKey( void * );

// GetRandom returns a random integer between min and max.
#define GetRandom( min, max ) ((rand() % (int)(((max) + 1) - (min))) + (min))
// GetGlyph returns a printable ASCII character value
#define GetGlyph( val ) ((char)((val + 32) % 93 + 33))

BOOL repeat = TRUE;                 // Global repeat flag
HANDLE hStdOut;                     // Handle for console window
CONSOLE_SCREEN_BUFFER_INFO csbi;    // Console information structure

int main()
{
    int param = 0;
    int * pparam = &param;

    // Get display screen's text row and column information.
    hStdOut = GetStdHandle( STD_OUTPUT_HANDLE );
    GetConsoleScreenBufferInfo( hStdOut, &csbi );

    // Launch CheckKey thread to check for terminating keystroke.
    _beginthread( CheckKey, 0, NULL );

    // Loop until CheckKey terminates program or 1000 threads created.
    while( repeat && param < 1000 )
    {
        // launch another character thread.
        _beginthread( Bounce, 0, (void *) pparam );

        // increment the thread parameter
        param++;

        // Wait one second between loops.
        Sleep( 1000L );
    }
}

// CheckKey - Thread to wait for a keystroke, then clear repeat flag.
void CheckKey( void * ignored )
{
    _getch();
    repeat = 0;    // _endthread implied
}

// Bounce - Thread to create and control a colored letter that moves
// around on the screen.
//
// Params: parg - the value to create the character from
void Bounce( void * parg )
{
    char       blankcell = 0x20;
    CHAR_INFO  ci;
    COORD      oldcoord, cellsize, origin;
    DWORD      result;
    SMALL_RECT region;

    cellsize.X = cellsize.Y = 1;
    origin.X = origin.Y = 0;

    // Generate location, letter and color attribute from thread argument.
    srand( _threadid );
    oldcoord.X = region.Left = region.Right =
        GetRandom(csbi.srWindow.Left, csbi.srWindow.Right - 1);
    oldcoord.Y = region.Top = region.Bottom =
        GetRandom(csbi.srWindow.Top, csbi.srWindow.Bottom - 1);
    ci.Char.AsciiChar = GetGlyph(*((int *)parg));
    ci.Attributes = GetRandom(1, 15);

    while (repeat)
    {
        // Pause between loops.
        Sleep( 100L );

        // Blank out our old position on the screen, and draw new letter.
        WriteConsoleOutputCharacterA(hStdOut, &blankcell, 1, oldcoord, &result);
        WriteConsoleOutputA(hStdOut, &ci, cellsize, origin, &region);

        // Increment the coordinate for next placement of the block.
        oldcoord.X = region.Left;
        oldcoord.Y = region.Top;
        region.Left = region.Right += GetRandom(-1, 1);
        region.Top = region.Bottom += GetRandom(-1, 1);

        // Correct placement (and beep) if about to go off the screen.
        if (region.Left < csbi.srWindow.Left)
            region.Left = region.Right = csbi.srWindow.Left + 1;
        else if (region.Right >= csbi.srWindow.Right)
            region.Left = region.Right = csbi.srWindow.Right - 2;
        else if (region.Top < csbi.srWindow.Top)
            region.Top = region.Bottom = csbi.srWindow.Top + 1;
        else if (region.Bottom >= csbi.srWindow.Bottom)
            region.Top = region.Bottom = csbi.srWindow.Bottom - 2;

        // If not at a screen border, continue, otherwise beep.
        else
            continue;
        Beep((ci.Char.AsciiChar - 'A') * 100, 175);
    }
    // _endthread given to terminate
    _endthread();
}
```

Чтобы закрыть приложение-пример, нажмите любую клавишу.

## <a name="example"></a>Пример

В следующем образце кода показано, как можно использовать обработчик потока, возвращаемый **_beginthreadex** с помощью [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject)API синхронизации. Основной поток ожидает завершения другого потока, прежде чем продолжить. Когда второй поток вызывает **_endthreadex**, он приводит к тому, что его объект потока переходит в сигнальное состояние. Это позволяет продолжить выполнение основного потока. Это невозможно сделать с помощью **_beginthread** и **_endthread**, поскольку **_endthread** вызывает **CloseHandle**, который уничтожает объект потока, прежде чем его можно будет установить в сигнальное состояние.

```cpp
// crt_begthrdex.cpp
// compile with: /MT
#include <windows.h>
#include <stdio.h>
#include <process.h>

unsigned Counter;
unsigned __stdcall SecondThreadFunc( void* pArguments )
{
    printf( "In second thread...\n" );

    while ( Counter < 1000000 )
        Counter++;

    _endthreadex( 0 );
    return 0;
}

int main()
{
    HANDLE hThread;
    unsigned threadID;

    printf( "Creating second thread...\n" );

    // Create the second thread.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc, NULL, 0, &threadID );

    // Wait until second thread terminates. If you comment out the line
    // below, Counter will not be correct because the thread has not
    // terminated, and Counter most likely has not been incremented to
    // 1000000 yet.
    WaitForSingleObject( hThread, INFINITE );
    printf( "Counter should be 1000000; it is-> %d\n", Counter );
    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
Creating second thread...
In second thread...
Counter should be 1000000; it is-> 1000000
```

## <a name="see-also"></a>См. также статью

- [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)
- [_endthread, _endthreadex](endthread-endthreadex.md)
- [abort](abort.md)
- [exit, _Exit, _exit](exit-exit-exit.md)
- [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)
