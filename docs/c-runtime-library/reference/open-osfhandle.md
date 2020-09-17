---
title: _open_osfhandle
ms.date: 4/2/2020
api_name:
- _open_osfhandle
- _o__open_osfhandle
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
- _open_osfhandle
- open_osfhandle
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
ms.openlocfilehash: d0f86c2588eed506bc9b8408e01bccdb6d1aad9d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844071"
---
# <a name="_open_osfhandle"></a>_open_osfhandle

Связывает дескриптор файла времени выполнения C с существующим дескриптором файла операционной системы.

## <a name="syntax"></a>Синтаксис

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>Параметры

*osfhandle*<br/>
Описатель файла операционной системы.

*flags*<br/>
Разрешенные типы операций.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения функция **_open_osfhandle** возвращает дескриптор файла времени выполнения C. Иначе возвращается значение -1.

## <a name="remarks"></a>Примечания

Функция **_open_osfhandle** выделяет дескриптор файла времени выполнения C. Он связывает этот дескриптор файла с дескриптором файла операционной системы, указанным параметром *осфхандле*. Чтобы компилятор не выдавал предупреждение, приведите аргумент *osfhandle* типа **HANDLE** к типу **intptr_t**. Аргумент *flags* — это целочисленное выражение, сформированное на основе одной или нескольких констант манифеста, определенных в \<fcntl.h> . Можно использовать оператор побитового или ( **&#124;** ) для объединения двух или более констант манифеста для формирования аргумента *flags* .

Эти константы манифеста определены в \<fcntl.h> :

| Константа | Описание |
|--|--|
| **\_O \_ append** | Помещает указатель файла в конец файла перед каждой операцией записи. |
| **\_O \_ рдонли** | Открывает файл только для чтения. |
| **\_O \_ текст** | Открывает файл в текстовом режиме (с преобразованием). |
| **\_O \_ втекст** | Открывает файл в режиме Юникода (с преобразованием UTF-16). |

Вызов **_open_osfhandle** передает право владения дескриптором файла Win32 дескриптору файла. Чтобы закрыть файл, открытый с помощью функции **_open_osfhandle**, вызовите функцию [\_close](close.md). Базовый дескриптор файла ОС также закрывается посредством вызова функции **_close**. Не вызывайте функцию Win32 **CloseHandle** применительно к исходному дескриптору. Если дескриптор файла принадлежит **файлу &#42;** поток, то вызов [фклосе](fclose-fcloseall.md) закрывает как дескриптор файла, так и базовый дескриптор. В этом случае не вызывайте функцию **_close** для дескриптора файла или функцию **CloseHandle** для исходного дескриптора.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[\_get_osfhandle](get-osfhandle.md)
