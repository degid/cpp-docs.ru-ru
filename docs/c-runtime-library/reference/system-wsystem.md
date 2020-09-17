---
title: system, _wsystem
ms.date: 4/2/2020
api_name:
- system
- _wsystem
- _o__wsystem
- _o_system
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
- _tsystem
- _wsystem
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
ms.openlocfilehash: 15e4637d709fdf4600ecb4c66c7d4a75c4fa07eb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844981"
---
# <a name="system-_wsystem"></a>system, _wsystem

Выполняет команду.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int system(
   const char *command
);
int _wsystem(
   const wchar_t *command
);
```

### <a name="parameters"></a>Параметры

*command*<br/>
Команда для выполнения.

## <a name="return-value"></a>Возвращаемое значение

Если *Команда* имеет **значение NULL** и обнаружен интерпретатор команд, возвращает ненулевое значение. Если интерпретатор команд не найден, возвращает 0 **и устанавливает для** **еноент**значение. Если *команда* не имеет **значение NULL**, **система** возвращает значение, возвращаемое интерпретатором команд. Она возвращает значение 0, только если интерпретатор команд возвращает значение 0. Возвращаемое значение, равное-1, указывает на ошибку **, а параметру «вывод** » задано одно из следующих значений:

| Значение | Описание |
|-|-|
| **E2BIG** | Список аргументов (который зависит от системы) слишком велик. |
| **еноент** | Интерпретатор команд не найден. |
| **ENOEXEC** | Файл интерпретатора команд не может быть выполнен из-за недопустимого формата. |
| **еномем** | Недостаточно доступной памяти для выполнения команды; или доступная память повреждена; или существует недопустимый блок, что указывает на неправильное выделение памяти для процесса, который выполняет вызов. |

Дополнительные сведения об этих кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Системная** функция передает *команду* интерпретатору команд, который выполняет строку в качестве команды операционной системы. **система** использует переменные среды **ComSpec** и **path** для поиска файла интерпретатора команд CMD.exe. Если *Команда* имеет **значение NULL**, функция просто проверяет, существует ли интерпретатор команд.

Необходимо явно очистить с помощью [fflush](fflush.md) или [_flushall](flushall.md)или закрыть любой поток перед вызовом **System**.

**_wsystem** — это версия **системы**с расширенными символами; Аргумент *команды* для **_wsystem** является строкой расширенных символов. В остальном эти функции ведут себя одинаково.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsystem**|**система**|**система**|**_wsystem**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**система**|\<process.h> или \<stdlib.h>|
|**_wsystem**|\<process.h>, \<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

В этом примере **система** используется для ввода текстового файла.

```C
// crt_system.c

#include <process.h>

int main( void )
{
   system( "type crt_system.txt" );
}
```

### <a name="input-crt_systemtxt"></a>Входные данные: crt_system.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Вывод

```Output
Line one.
Line two.
```

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, функции _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_spawn, функции _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
