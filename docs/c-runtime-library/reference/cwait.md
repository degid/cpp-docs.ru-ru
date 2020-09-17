---
title: _cwait
ms.date: 4/2/2020
api_name:
- _cwait
- _o__cwait
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
- api-ms-win-crt-process-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _cwait
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
ms.openlocfilehash: 9e2e23acb041004b9e96d1c6558ae195ed522155
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914798"
---
# <a name="_cwait"></a>_cwait

Ожидает завершения другого процесса.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _cwait(
   int *termstat,
   intptr_t procHandle,
   int action
);
```

### <a name="parameters"></a>Параметры

*термстат*<br/>
Указатель на буфер, где будет сохранен код результата указанного процесса, или **значение NULL**.

*прочандле*<br/>
Обработчик ожидания процесса (то есть процесс, который должен завершиться до того, как **_cwait** может вернуть).

*action*<br/>
NULL: игнорируется приложениями операционной системы Windows; для других приложений: код действия для выполнения в *прочандле*.

## <a name="return-value"></a>Возвращаемое значение

После успешного завершения указанного процесса возвращает маркер указанного процесса и задает для *термстат* результирующий код, возвращаемый указанным процессом. В противном случае возвращает-1 **и задает значение** переводится следующим образом.

|Применение|Описание|
|-----------|-----------------|
|**ECHILD**|Указанный процесс не существует, *прочандле* является недопустимым или не удалось вызвать API [жетекситкодепроцесс](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess) или [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) .|
|**еинвал**|Недопустимое *действие* .|

Дополнительные сведения об этих и других кодах возврата см. в разделе переввод [, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **_cwait** ожидает завершения выполнения идентификатора процесса указанного процесса, предоставленного *прочандле*. Значение *прочандле* , передаваемое в **_cwait** , должно быть значением, возвращаемым вызовом функции [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) , создавшей указанный процесс. Если идентификатор процесса завершается до вызова **_cwait** , **_cwait** немедленно возвращает значение. **_cwait** может использоваться любым процессом для ожидания любого другого известного процесса, для которого существует допустимый Handle (*прочандле*).

*термстат* указывает на буфер, где будет храниться код возврата указанного процесса. Значение *термстат* указывает, завершился ли указанный процесс обычным образом путем вызова API [ExitProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitprocess) для Windows. **ExitProcess** вызывается внутри, если указанный процесс вызывает **Exit** или **_exit**, возвращает из **Main**или достигает конца **Main**. Дополнительные сведения о значении, переданном обратно через *термстат*, см. в разделе [жетекситкодепроцесс](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess). Если **_cwait** вызывается с помощью значения **null** для *термстат*, код возврата указанного процесса не сохраняется.

Параметр *Action* игнорируется операционной системой Windows, поскольку в этих средах не реализованы связи типа «родители-потомки».

Если *прочандле* имеет значение-1 или-2 (обрабатывает текущий процесс или поток), дескриптор будет закрыт. Поэтому в этой ситуации не используйте возвращенный дескриптор.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_cwait**|\<process.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_cwait.c
// compile with: /c
// This program launches several processes and waits
// for a specified process to finish.

#define _CRT_RAND_S

#include <windows.h>
#include <process.h>
#include <stdlib.h>
#include <stdio.h>
#include <time.h>

// Macro to get a random integer within a specified range
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))

struct PROCESS
{
   int     nPid;
   char    name[40];
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };

int main( int argc, char *argv[] )
{
   int termstat, c;
   unsigned int number;

   srand( (unsigned)time( NULL ) );    // Seed randomizer

   // If no arguments, this is the calling process
   if ( argc == 1 )
   {
      // Spawn processes in numeric order
      for ( c = 0; c < 4; c++ ) {
         _flushall();
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],
                                    process[c].name, NULL );
      }

      // Wait for randomly specified process, and respond when done
      c = getrandom( 0, 3 );
      printf( "Come here, %s.\n", process[c].name );
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );
      printf( "Thank you, %s.\n", process[c].name );

   }
   // If there are arguments, this must be a spawned process
   else
   {
      // Delay for a period that's determined by process number
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );
      printf( "Hi, Dad. It's %s.\n", argv[1] );
   }
}
```

```Output
Hi, Dad. It's Ann.
Come here, Ann.
Thank you, Ann.
Hi, Dad. It's Beth.
Hi, Dad. It's Carl.
Hi, Dad. It's Dave.
```

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
