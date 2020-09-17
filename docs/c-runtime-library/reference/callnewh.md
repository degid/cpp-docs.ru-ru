---
title: _callnewh
ms.date: 4/2/2020
api_name:
- _callnewh
- _o__callnewh
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
- _callnewh
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: 3990d4b15c25cfd6c753c2b1d44c112971ff59af
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918804"
---
# <a name="_callnewh"></a>_callnewh

Вызывает *новый обработчик*, установленный на данный момент.

## <a name="syntax"></a>Синтаксис

```cpp
int _callnewh(
   size_t size
   )
```

### <a name="parameters"></a>Параметры

*size*<br/>
Объем памяти, который [оператор new](../../cpp/new-operator-cpp.md) пытается выделить.

## <a name="return-value"></a>Возвращаемое значение

|Применение|Описание|
|-----------|-----------------|
|0|Ошибка: новый обработчик либо не установлен, либо не активен.|
|1|Успешное завершение: новый обработчик установлен и активен. Выделение памяти можно повторить.|

## <a name="exceptions"></a>Исключения

Эта функция вызывает [bad_alloc](../../standard-library/bad-alloc-class.md), если *новый обработчик* обнаружить не удается.

## <a name="remarks"></a>Примечания

*Новый обработчик* вызывается, если [оператору new](../../cpp/new-operator-cpp.md) не удается успешно выделить память. После этого новый обработчик может инициировать соответствующее действие, например освобождение памяти для успешного выполнения последующих распределений.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|_callnewh|internal.h|

## <a name="see-also"></a>См. также раздел

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
