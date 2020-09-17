---
title: _endthread, _endthreadex
ms.date: 4/2/2020
api_name:
- _endthread
- _endthreadex
- _o__endthread
- _o__endthreadex
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
- _endthread
- endthreadex
- _endthreadex
- endthread
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
ms.openlocfilehash: a3889adcc90bd62e766102b72aae68577915e55b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915085"
---
# <a name="_endthread-_endthreadex"></a>_endthread, _endthreadex

Завершает поток; **_endthread** завершает поток, созданный **_beginthread** , и **_endthreadex** завершает поток, созданный **_beginthreadex**.

## <a name="syntax"></a>Синтаксис

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>Параметры

*retval*<br/>
Код выхода потока.

## <a name="remarks"></a>Примечания

Чтобы завершить поток, можно явно вызвать **_endthread** или **_endthreadex** . Однако **_endthread** или **_endthreadex** вызывается автоматически, когда поток возвращается из подпрограммы, передаваемой в качестве параметра в **_beginthread** или **_beginthreadex**. Завершение потока с вызовом **ендсреад** или **_endthreadex** помогает обеспечить правильное восстановление ресурсов, выделенных для потока.

> [!NOTE]
> Для исполняемого файла, связанного с Libcmt.lib, не следует вызывать функцию [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) API Win32. Это помешает системе времени выполнения освобождать выделенные ресурсы. **_endthread** и **_endthreadex** освободить выделенные ресурсы потока, а затем вызвать **ExitThread**.

**_endthread** автоматически закрывает обработчик потока. (Это поведение отличается от API Win32 **ExitThread** .) Поэтому при использовании **_beginthread** и **_endthread**не следует явно закрывать обработчик потока, вызывая API-интерфейс Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) .

Как и API-интерфейс Win32 **ExitThread** , **_endthreadex** не закрывает обработчик потока. Поэтому при использовании **_beginthreadex** и **_endthreadex**необходимо закрыть обработчик потока, вызвав API-интерфейс Win32 **CloseHandle** .

> [!NOTE]
> **_endthread** и **_endthreadex** приводят к тому, что деструкторы C++ ожидают вызова в потоке.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только многопоточные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md) .

## <a name="example"></a>Пример

См. пример для [_beginthread](beginthread-beginthreadex.md).

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
