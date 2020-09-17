---
title: exit, _Exit, _exit
ms.date: 4/2/2020
api_name:
- _exit
- exit
- _o__exit
- _o_exit
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
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
ms.openlocfilehash: a1c0eeaa6d66e91b913ce7940d37409fc4f6ac29
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909666"
---
# <a name="exit-_exit-_exit"></a>exit, _Exit, _exit

Завершает вызывающий процесс. Функция **Exit** завершает ее после очистки; **_exit** и **_Exit** завершать его немедленно.

> [!NOTE]
> Не используйте этот метод для завершения работы приложения универсальная платформа Windows (UWP), за исключением сценариев тестирования или отладки. В соответствии с [политиками Microsoft Store](/legal/windows/agreements/store-policies)не разрешено закрывать приложения Магазина программным способом или с помощью пользовательского интерфейса. Дополнительные сведения см. в статье [жизненный цикл приложения UWP](/windows/uwp/launch-resume/app-lifecycle). Дополнительные сведения о приложениях Windows 10 см. в разделе [Практические руководства для приложений Windows 10](https://developer.microsoft.com/windows/apps).

## <a name="syntax"></a>Синтаксис

```C
void exit(
   int const status
);
void _Exit(
   int const status
);
void _exit(
   int const status
);
```

### <a name="parameters"></a>Параметры

*status*<br/>
Код состояния завершения.

## <a name="remarks"></a>Примечания

Функции **Exit**, **_Exit** и **_exit** завершают вызывающий процесс. Функция **Exit** вызывает деструкторы для локальных объектов потока, а затем вызывает (в порядке ЛИФО) — функции, зарегистрированные **atexit** и **_onexit**, а затем очищает все буферы файлов до завершения процесса. Функции **_Exit** и **_exit** завершают процесс без удаления локальных объектов потока или обработки **atexit** или функций **_onexit** , а также без очистки буферов потока.

Несмотря на то, что вызовы **Exit**, **_Exit** и **_exit** не возвращают значение, значение в поле *состояние* становится доступным для среды размещения или ожидающего вызывающего процесса, если он существует, после завершения процесса. Как правило, вызывающий объект устанавливает значение *состояния* 0, чтобы указать на нормальную работу, или на какое-либо другое значение, чтобы указать на ошибку. Значение *состояния* доступно для команды Batch операционной системы **ERRORLEVEL** и представляется одной из двух констант: **EXIT_SUCCESS**, представляющей значение 0, или **EXIT_FAILURE**, который представляет значение 1.

Функции **Exit**, **_Exit**, **_exit**, **quick_exit**, **_cexit**и **_c_exit** ведут себя следующим образом.

|Функция|Описание|
|--------------|-----------------|
|**exit**|Выполняет полные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**_Exit**|Выполняет минимальные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**_exit**|Выполняет минимальные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**quick_exit**|Выполняет быстрые процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**_cexit**|Выполняет полные процедуры завершения библиотеки C и возвращает управление вызывающему объекту. Не завершает процесс.|
|**_c_exit**|Выполняет минимальные процедуры завершения библиотеки C и возвращает управление вызывающему объекту. Не завершает процесс.|

При вызове функции **Exit**, **_Exit** или **_exit** деструкторы для всех временных или автоматических объектов, которые существуют во время вызова, не вызываются. Автоматический объект — это не статический локальный объект, определенный в функции. Временный объект — это объект, созданный компилятором, например значение, возвращаемое вызовом функции. Чтобы уничтожить автоматический объект перед вызовом функции **Exit**, **_Exit**или **_exit**, явно вызовите деструктор для объекта, как показано ниже:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

Не используйте **DLL_PROCESS_ATTACH** для вызова **Exit** из **DllMain**. Чтобы выйти из функции **DllMain** , возвратите **значение false** из **DLL_PROCESS_ATTACH**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**выход**, **_Exit** **_exit**|\<process.h> или \<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_exit.c
// This program returns an exit code of 1. The
// error code could be tested in a batch file.

#include <stdlib.h>

int main( void )
{
   exit( 1 );
}
```

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[рвал](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit, _c_exit](cexit-c-exit.md)<br/>
[_exec, функции _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
