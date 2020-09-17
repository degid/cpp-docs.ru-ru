---
title: _cexit, _c_exit
ms.date: 4/2/2020
api_name:
- _c_exit
- _cexit
- _o__cexit
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
- _cexit
- c_exit
- _c_exit
- cexit
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
ms.openlocfilehash: 78675ef91c2ab68e18f6111b4908886017ae1f79
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917146"
---
# <a name="_cexit-_c_exit"></a>_cexit, _c_exit

Выполняет операции очистки и возвращает значение, не прерывая процесс.

## <a name="syntax"></a>Синтаксис

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>Примечания

Функция **_cexit** вызывает, в порядке "последним поatexit, первым обслужен" (LIFO) функции, зарегистрированные с помощью **atexit** и **_onexit**. Затем **_cexit** сбрасывает все буферы ввода-вывода и закрывает все открытые потоки перед возвратом. **_c_exit** совпадает с **_exit** , но возвращается в вызывающий процесс без обработки **atexit** или **_onexit** или очистки буферов потока. Поведение функций **Exit**, **_exit**, **_cexit**и **_c_exit** показано в следующей таблице.

|Функция|Поведение|
|--------------|--------------|
|**exit**|Выполняет полные процедуры завершения библиотеки C, завершает процесс и завершается с предоставленным кодом состояния.|
|**_exit**|Выполняет быстрые процедуры завершения библиотеки C, завершает процесс и завершается с предоставленным кодом состояния.|
|**_cexit**|Выполняет полные процедуры завершения библиотеки C и возвращает управление вызывающему объекту, но не завершает процесс.|
|**_c_exit**|Выполняет быстрые процедуры завершения библиотеки C и возвращает управление вызывающему объекту, но не завершает процесс.|

При вызове функций **_cexit** или **_c_exit** деструкторы для всех временных или автоматических объектов, которые существуют во время вызова, не вызываются. Автоматический объект — это объект, который определяется в функции, если он не объявлен статическим. Временный объект — это объект, созданный компилятором. Чтобы уничтожить автоматический объект перед вызовом **_cexit** или **_c_exit**, явно вызовите деструктор для объекта следующим образом:

```cpp
myObject.myClass::~myClass( );
```

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[рвал](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, функции _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
