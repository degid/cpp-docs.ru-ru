---
title: Win32ThreadTraits Класс
ms.date: 11/04/2016
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
ms.openlocfilehash: 64f02293508894a70f36c29d5032c9ba8f250c38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325801"
---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits Класс

Этот класс обеспечивает функцию создания потока Windows. Используйте этот класс, если поток не будет использовать функции CRT.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class Win32ThreadTraits
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Win32ThreadTraits::CreateThread](#createthread)|(Статик) Вызовите эту функцию, чтобы создать поток, который не должен использовать функции CRT.|

## <a name="remarks"></a>Примечания

Черты потока — это классы, которые обеспечивают функцию создания определенного типа потока. Функция создания имеет ту же подпись и семантику, что и функция [Windows CreateThread.](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread)

Черты нити используются следующими классами:

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

Если поток будет использовать функции CRT, вместо этого используйте [CRTThreadTraits.](../../atl/reference/crtthreadtraits-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="win32threadtraitscreatethread"></a><a name="createthread"></a>Win32ThreadTraits::CreateThread

Вызовите эту функцию, чтобы создать поток, который не должен использовать функции CRT.

```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```

### <a name="parameters"></a>Параметры

*лза*<br/>
Атрибуты безопасности для нового потока.

*dwStackSize*<br/>
Размер стека для нового потока.

*pfnThreadProc*<br/>
Процедура потока нового потока.

*pvParam*<br/>
Параметр, который будет передан процедуре потока.

*dwCreationFlags*<br/>
Флаги создания (0 или CREATE_SUSPENDED).

*pdwThreadId*<br/>
(ваут) Адрес переменной DWORD, которая, по успеху, получает идентификатор потока вновь созданного потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку в недавно созданный поток или NULL при сбое. Позвоните [GetLastError,](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) чтобы получить расширенную информацию об ошибках.

### <a name="remarks"></a>Примечания

Дополнительную информацию о параметрах этой функции можно просмотреть [CreateThread.](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread)

Эта функция `CreateThread` вызывает для создания потока.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
