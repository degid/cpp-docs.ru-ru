---
title: _spawnlpe, _wspawnlpe
ms.date: 11/04/2016
api_name:
- _spawnlpe
- _wspawnlpe
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wspawnlpe
- _spawnlpe
- wspawnlpe
helpviewer_keywords:
- _wspawnlpe function
- wspawnlpe function
- processes, creating
- spawnlpe function
- _spawnlpe function
- processes, executing new
- process creation
ms.assetid: e171ebfa-70e7-4c44-8331-2a291fc17bd6
ms.openlocfilehash: 8e5e20827ef67d83b008a055505ec95abbde7d49
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844175"
---
# <a name="_spawnlpe-_wspawnlpe"></a>_spawnlpe, _wspawnlpe

Создает и выполняет новый процесс.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
intptr_t _spawnlpe(
   int mode,
   const char *cmdname,
   const char *arg0,
   const char *arg1,
   ... const char *argn,
   NULL,
   const char *const *envp
);
intptr_t _wspawnlpe(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *arg0,
   const wchar_t *arg1,
   ... const wchar_t *argn,
   NULL,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Параметры

*mode*<br/>
Режим выполнения для вызывающего процесса.

*кмднаме*<br/>
Путь к выполняемому файлу.

*arg0*, *arg1*,... *argN*<br/>
Список указателей на аргументы. Аргумент *arg0* обычно является указателем на *кмднаме*. Аргументы *arg1* – *argN* — это указатели на символьные строки, которые формируют новый список аргументов. В *следующих случаях*для обозначения конца списка аргументов должен быть **пустой** указатель.

*envp*<br/>
Массив указателей на параметры среды.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение из синхронного **_spawnlpe** или **_wspawnlpe** (**_P_WAIT** , заданное для *режима*) — это состояние выхода нового процесса. Возвращаемое значение из асинхронного **_spawnlpe** или **_wspawnlpe** (**_P_NOWAIT** или **_P_NOWAITO** , заданное для *режима*) — это обработчик процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Можно задать для состояния выхода ненулевое значение, если порожденный процесс специально использует ненулевый аргумент для вызова подпрограммы **выхода** . Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение, равное-1, указывает на ошибку (новый процесс не запущен). В этом случае для **параметра «значение возврата»** задается одно из следующих значений.

| Значение | Описание |
|-|-|
| **E2BIG** | Длина списка аргументов превышает 1024 байта. |
| **еинвал** | Недопустимый аргумент *mode* . |
| **еноент** | Файл или путь не найден. |
| **ENOEXEC** | Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла. |
| **еномем** | Недостаточно памяти для выполнения нового процесса. |

Дополнительные сведения об этих и других кодах возврата см. в разделе переввод [, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая из этих функций создает и выполняет новый процесс и передает каждый аргумент командной строки как отдельный параметр, а также передает массив указателей на параметры среды. Эти функции используют переменную среды **path** для поиска файла, который нужно выполнить.

Эти функции проверяют свои параметры. Если *кмднаме* или *arg0* является пустой строкой или пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции **устанавливают** значение **еинвал**и возвращают-1. Нет порожденных новых процессов.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_spawnlpe**|\<process.h>|
|**_wspawnlpe**|\<stdio.h> или \<wchar.h>|

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
