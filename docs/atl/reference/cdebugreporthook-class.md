---
title: Класс CDebugReportHook
ms.date: 11/04/2016
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
ms.openlocfilehash: 8380556bbe007326156bf0ec0eefc23052e8e056
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747723"
---
# <a name="cdebugreporthook-class"></a>Класс CDebugReportHook

Используйте этот класс для отправки отчетов об отладке в именованные трубы.

## <a name="syntax"></a>Синтаксис

```
class CDebugReportHook
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|Вызовы [SetPipeName,](#setpipename) [SetTimeout](#settimeout)и [SetHook](#sethook).|
|[CDebugReportHook:::CDebugReportHook](#dtor)|Вызовы [CDebugReportHook::RemoveHook](#removehook).|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(Статик) Пользовательская функция отчетности, подключенная к процессу отладки времени выполнения C.|
|[CDebugReportHook::RemoveHook](#removehook)|Вызов иметод, чтобы остановить отправку отчетов об отладке в названную трубу и восстановить предыдущий крюк отчета.|
|[CDebugReportHook::SetHook](#sethook)|Вызовите этот метод, чтобы начать отправку отчетов об отладке в названную трубу.|
|[CDebugReportHook::SetPipeName](#setpipename)|Вызовите этот метод, чтобы установить машину и название трубы, на которую будут отправлены отчеты об отладке.|
|[CDebugReportHook::SetTimeout](#settimeout)|Вызовите этот метод, чтобы установить время в миллисекундах, что этот класс будет ждать, пока названная труба станет доступной.|

## <a name="remarks"></a>Примечания

Создайте экземпляр этого класса в отладочных сборках ваших служб или приложений для отправки отчетов об отладке в названную трубу. Отчеты об ошибке генерируются путем вызова [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) или использования обертки для этой функции, такой как макросы [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) и [ATLASSERT.](debugging-and-error-reporting-macros.md#atlassert)

Использование этого класса позволяет интерактивно отладить компоненты, работающие в неинтерактивных [оконных станциях.](/windows/win32/winstation/window-stations)

Обратите внимание, что отчеты об отладке отправляются с использованием базового контекста безопасности потока. Олицетворение временно отключено, так что отладка отчетов могут быть просмотрены в ситуациях, когда олицетворение пользователей с низкими привилегиями происходит, например, в веб-приложениях.

## <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="cdebugreporthookcdebugreporthook"></a><a name="cdebugreporthook"></a>CDebugReportHook::CDebugReportHook

Вызовы [SetPipeName,](#setpipename) [SetTimeout](#settimeout)и [SetHook](#sethook).

```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```

### <a name="parameters"></a>Параметры

*szMachineName*<br/>
Название машины, на которую должен быть отправлен выход отладки. По умолчанию к локальной машине.

*szPipeName*<br/>
Название указанной трубы, на которую должен быть отправлен выход отладки.

*dwTimeout*<br/>
Время в миллисекундах, что этот класс будет ждать названной трубы, чтобы стать доступным.

## <a name="cdebugreporthookcdebugreporthook"></a><a name="dtor"></a>CDebugReportHook:::CDebugReportHook

Вызовы [CDebugReportHook::RemoveHook](#removehook).

```
~CDebugReportHook() throw();
```

## <a name="cdebugreporthookcdebugreporthookproc"></a><a name="cdebugreporthookproc"></a>CDebugReportHook::CDebugReportHookProc

Пользовательская функция отчетности, подключенная к процессу отладки времени выполнения C.

```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```

### <a name="parameters"></a>Параметры

*отчетType*<br/>
Тип отчета (_CRT_WARN, _CRT_ERROR или _CRT_ASSERT).

*message*<br/>
Строка сообщения.

*возвратСтоимость*<br/>
Значение, которое должно быть возвращено [_CrtDbgReport.](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)

### <a name="return-value"></a>Возвращаемое значение

Возвращает FALSE, если крючок обрабатывает сообщение, о котором идет речь, так что никаких дополнительных отчетов не требуется. Возвращает TRUE, если `_CrtDbgReport` следует сообщить сообщение в обычном порядке.

### <a name="remarks"></a>Примечания

Функция отчетности пытается открыть названную трубу и связаться с процессом на другом конце. Если труба занята, функция отчетности будет ждать, пока труба не станет свободной или истекло тайм-аут. Тайм-аут может быть установлен конструктором или вызовом [на CDebugReportHook::SetTimeout](#settimeout).

Код в этой функции выполняется в базовом контексте безопасности потока вызова, т.е. олицетворение отключено на время действия этой функции.

## <a name="cdebugreporthookremovehook"></a><a name="removehook"></a>CDebugReportHook::RemoveHook

Вызов иметод, чтобы остановить отправку отчетов об отладке в названную трубу и восстановить предыдущий крюк отчета.

```cpp
void RemoveHook() throw();
```

### <a name="remarks"></a>Примечания

Вызовы [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) для восстановления предыдущего крючка отчета.

## <a name="cdebugreporthooksethook"></a><a name="sethook"></a>CDebugReportHook::SetHook

Вызовите этот метод, чтобы начать отправку отчетов об отладке в названную трубу.

```cpp
void SetHook() throw();
```

### <a name="remarks"></a>Примечания

Вызовы [_CrtSetReportHook2,](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) чтобы отладить отчеты направляется через [CDebugReportHookProc](#cdebugreporthookproc) к названной трубе. Этот класс отслеживает предыдущий крюк отчета, чтобы он мог быть восстановлен при вызове [RemoveHook.](#removehook)

## <a name="cdebugreporthooksetpipename"></a><a name="setpipename"></a>CDebugReportHook::SetPipeName

Вызовите этот метод, чтобы установить машину и название трубы, на которую будут отправлены отчеты об отладке.

```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```

### <a name="parameters"></a>Параметры

*szMachineName*<br/>
Название машины, на которую должен быть отправлен выход отладки.

*szPipeName*<br/>
Название указанной трубы, на которую должен быть отправлен выход отладки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="cdebugreporthooksettimeout"></a><a name="settimeout"></a>CDebugReportHook::SetTimeout

Вызовите этот метод, чтобы установить время в миллисекундах, что этот класс будет ждать, пока названная труба станет доступной.

```cpp
void SetTimeout(DWORD dwTimeout);
```

### <a name="parameters"></a>Параметры

*dwTimeout*<br/>
Время в миллисекундах, что этот класс будет ждать названной трубы, чтобы стать доступным.

## <a name="see-also"></a>См. также раздел

[Классы](../../atl/reference/atl-classes.md)
