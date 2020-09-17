---
title: _get_osfhandle
ms.date: 4/2/2020
api_name:
- _get_osfhandle
- _o__get_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_osfhandle
- _get_osfhandle
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: 085bf20a12d9b77be0977521bde2ab75d9b2636a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918283"
---
# <a name="_get_osfhandle"></a>_get_osfhandle

Получает дескриптор файла операционной системы, связанный с указанным дескриптором файла.

## <a name="syntax"></a>Синтаксис

```C
intptr_t _get_osfhandle(
   int fd
);
```

### <a name="parameters"></a>Параметры

*демо*<br/>
Дескриптор существующего файла.

## <a name="return-value"></a>Возвращаемое значение

Возвращает описатель файла операционной системы, если *демон демона* является допустимым. В противном случае вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, возвращается **INVALID_HANDLE_VALUE** (-1). Он **также устанавливает значение** по **значение EBADF**, указывающее на недопустимый маркер файла. Чтобы избежать предупреждения, когда результат используется как файловый обработчик Win32, приведите его к типу **Handle** .

> [!NOTE]
> Если **stdin**, **stdout**и **stderr** не связаны с потоком (например, в приложении Windows без окна консоли), значения дескрипторов файлов для этих потоков возвращаются из [_fileno](fileno.md) как особое значение-2. Аналогично, если в качестве параметра дескриптора файла используется 0, 1 или 2, а не результат вызова **_fileno**, **_get_osfhandle** также возвращает особое значение-2, если дескриптор файла не связан с потоком, и **не устанавливает значение**переводится. Однако это недопустимое значение для этого файла, и последующие вызовы, которые пытаются его использовать, скорее всего, завершатся ошибкой.

Дополнительные сведения о **значение EBADF** и других кодах ошибок см. в разделе [_doserrno, код ошибки, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Чтобы закрыть файл, дескриптор файла операционной системы которого получается **_get_osfhandle**, вызовите [_close](close.md) для дескриптора *фильтра*файлов. Никогда не вызывайте функцию **CloseHandle** на возвращаемом значении этой функции. Дескриптор файла базовой операционной системы принадлежит дескриптору файла *демона* и закрывается при вызове [_close](close.md) в процессе *демона*. Если дескриптор файла принадлежит `FILE *` потоку, то вызов [фклосе](fclose-fcloseall.md) для этого `FILE *` потока закрывает дескриптор файла и базовый дескриптор файла операционной системы. В этом случае не вызывайте [_close](close.md) для дескриптора файла.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[\_open_osfhandle](open-osfhandle.md)
