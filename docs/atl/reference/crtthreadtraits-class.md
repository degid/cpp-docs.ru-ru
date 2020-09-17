---
title: Класс CRTThreadTraits
ms.date: 11/04/2016
f1_keywords:
- CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits::CreateThread
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
ms.openlocfilehash: a7cfddc64e8c1b4e192e718d05812e385fbe08ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331026"
---
# <a name="crtthreadtraits-class"></a>Класс CRTThreadTraits

Этот класс обеспечивает функцию создания для потока CRT. Используйте этот класс, если поток будет использовать функции CRT.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CRTThreadTraits
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRTThreadTraits::CreateThread](#createthread)|(Статик) Вызовите эту функцию, чтобы создать поток, который может использовать функции CRT.|

## <a name="remarks"></a>Примечания

Черты потока — это классы, которые обеспечивают функцию создания определенного типа потока. Функция создания имеет ту же подпись и семантику, что и функция [Windows CreateThread.](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread)

Черты нити используются следующими классами:

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

Если поток не будет использовать функции CRT, вместо этого используйте [Win32ThreadTraits.](../../atl/reference/win32threadtraits-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="crtthreadtraitscreatethread"></a><a name="createthread"></a>CRTThreadTraits::CreateThread

Вызовите эту функцию, чтобы создать поток, который может использовать функции CRT.

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

Эта функция вызывает [_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) для создания потока.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
