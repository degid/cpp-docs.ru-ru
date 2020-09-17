---
title: _set_new_mode
ms.date: 4/2/2020
api_name:
- _set_new_mode
- _o__set_new_mode
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_new_mode
- _set_new_mode
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
ms.openlocfilehash: aa21854f6a8c4b58a510b16e824449a53b91f329
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218537"
---
# <a name="_set_new_mode"></a>_set_new_mode

Задает новый режим обработчика для **malloc**.

## <a name="syntax"></a>Синтаксис

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>Параметры

*невхандлермоде*<br/>
Новый режим обработчика для **malloc**; Допустимые значения: 0 или 1.

## <a name="return-value"></a>Возвращаемое значение

Возвращает предыдущий режим обработчика, установленный для **malloc**. Возвращаемое значение, равное 1, указывает, что при сбое выделения памяти **malloc** выделит ранее новую подпрограммы обработчика; Возвращаемое значение 0 указывает, что это не так. Если аргумент *невхандлермоде* не равен 0 или 1, возвращает значение-1.

## <a name="remarks"></a>Примечания

Функция **_set_new_mode** C++ задает новый режим обработчика для [malloc](malloc.md). Новый режим обработчика указывает, что в случае сбоя **malloc** вызывает новую подпрограммы обработчика, заданную [_set_new_handler](set-new-handler.md). По умолчанию **malloc** не вызывает новую подпрограммы обработчика при сбое выделения памяти. Это поведение по умолчанию можно переопределить таким образом, что, когда **malloc** не сможет выделить память, **malloc** вызывает новую подпрограммы обработчика так же, как **`new`** если бы она не завершилась по той же причине. Дополнительные сведения см. в разделе об операторах [new](../../cpp/new-operator-cpp.md) и [delete](../../cpp/delete-operator-cpp.md)*справочника по языку C++*. Чтобы переопределить значение по умолчанию, вызовите:

```cpp
_set_new_mode(1);
```

ранее в программе или компоновке с помощью использованием NEWMODE. obj (см. раздел [Параметры связи](../../c-runtime-library/link-options.md)).

Эта функция проверяет свои параметры. Если *невхандлермоде* имеет значение, отличное от 0 или 1, функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, <strong>_set_new_mode</strong> возвращает значение-1 **и устанавливает для** возврата значение `EINVAL` .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[свободный](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
