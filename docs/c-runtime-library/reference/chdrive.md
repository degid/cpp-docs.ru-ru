---
title: _chdrive
ms.date: 4/2/2020
api_name:
- _chdrive
- _o__chdrive
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- chdrive
- _chdrive
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
ms.openlocfilehash: a597a67c7d2083cf5860112f6ed55ff248053d17
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917020"
---
# <a name="_chdrive"></a>_chdrive

Изменяет текущий рабочий диск.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _chdrive(
   int drive
);
```

### <a name="parameters"></a>Параметры

*диск*<br/>
Целое число от 1 до 26, указывающее текущий рабочий диск (1 = A, 2 = B и т. д.).

## <a name="return-value"></a>Возвращаемое значение

Ноль (0), если текущий рабочий диск был успешно изменен; в противном случае возвращается −1.

## <a name="remarks"></a>Примечания

Если параметр *Drive* не находится в диапазоне от 1 до 26, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция **_chdrive** возвращает значение-1 **, а** **для свойства** **_doserrno** устанавливается значение **ERROR_INVALID_DRIVE**.

Функция **_chdrive** не является потокобезопасной, так как зависит от не безопасной для потоков функции **SetCurrentDirectory**. Для безопасного использования функции **_chdrive** в многопоточном приложении необходимо обеспечить собственный механизм синхронизации потоков. Дополнительные сведения см. в разделе [сеткуррентдиректори](/windows/win32/api/winbase/nf-winbase-setcurrentdirectory).

Функция **_chdrive** изменяет текущий рабочий диск, а функция **_chdir** — текущий рабочий каталог.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_chdrive**|\<direct.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. примеры использования функции [_getdrive](getdrive.md).

## <a name="see-also"></a>См. также раздел

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
