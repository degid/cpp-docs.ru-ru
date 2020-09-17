---
title: _spawnve, _wspawnve
ms.date: 4/2/2020
api_name:
- _spawnve
- _wspawnve
- _o__spawnve
- _o__wspawnve
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
- wspawnve
- _spawnve
- _wspawnve
helpviewer_keywords:
- _spawnve function
- spawnve function
- wspawnve function
- processes, creating
- _wspawnve function
- processes, executing new
- process creation
ms.assetid: 26d1713d-b551-4f21-a07b-e9891a2ae6cf
ms.openlocfilehash: dc6a6195987c1d5b323a86671de09dc28df84665
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836121"
---
# <a name="_spawnve-_wspawnve"></a>_spawnve, _wspawnve

Создает и выполняет новый процесс.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _spawnve(
   int mode,
   const char *cmdname,
   const char *const *argv,
   const char *const *envp
);
intptr_t _wspawnve(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Параметры

*mode*<br/>
Режим выполнения для вызывающего процесса.

*кмднаме*<br/>
Путь к выполняемому файлу.

*argv*<br/>
Массив указателей на аргументы. Аргумент *argv*[0] обычно является указателем на путь в реальном режиме или с именем программы в защищенном режиме, а *argv*[1] через *argv*[**n**] — это указатели на символьные строки, формирующие новый список аргументов. Аргумент *argv*[**n** + 1] должен быть **пустым** указателем, чтобы пометить конец списка аргументов.

*envp*<br/>
Массив указателей на параметры среды.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение из синхронного **_spawnve** или **_wspawnve** (**_P_WAIT** , заданное для *режима*) — это состояние выхода нового процесса. Возвращаемое значение из асинхронного **_spawnve** или **_wspawnve** (**_P_NOWAIT** или **_P_NOWAITO** , заданное для *режима*) — это обработчик процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Можно задать для состояния выхода ненулевое значение, если порожденный процесс явно вызывает процедуру **выхода** с ненулевым аргументом. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение, равное-1, указывает на ошибку (новый процесс не запущен). В этом случае для **параметра «значение возврата»** задается одно из следующих значений.

| Значение | Описание |
|-|-|
| **E2BIG** | Длина списка аргументов превышает 1024 байта. |
| **еинвал** | Недопустимый аргумент *mode* . |
| **еноент** | Файл или путь не найден. |
| **ENOEXEC** | Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла. |
| **еномем** | Недостаточно памяти для выполнения нового процесса. |

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая из этих функций создает и выполняет новый процесс, передавая ему массив указателей на аргументы командной строки и массив указателей на параметры среды.

Эти функции проверяют свои параметры. Если либо *кмднаме* , либо *argv* является пустым указателем, или если *argv* указывает на указатель null или *argv*[0] является пустой строкой, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции **устанавливают** значение **еинвал**и возвращают-1. Нет порожденных новых процессов.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_spawnve**|\<stdio.h> или \<process.h>|
|**_wspawnve**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [_spawn, _wspawn Functions](../../c-runtime-library/spawn-wspawn-functions.md).

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn, функции _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[рвал](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, функции _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
