---
title: ___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max
ms.date: 4/2/2020
api_name:
- ___mb_cur_max_l_func
- __p___mb_cur_max
- ___mb_cur_max_func
- __mb_cur_max
- _o____mb_cur_max_func
api_location:
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
- __mb_cur_max
helpviewer_keywords:
- __mb_cur_max
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
ms.openlocfilehash: 8287e2e7cab8880d35fef170287713adcc103c7e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912956"
---
# <a name="___mb_cur_max_func-___mb_cur_max_l_func-__p___mb_cur_max-__mb_cur_max"></a>___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max

Внутренняя функция CRT. Получает максимальное число байт в многобайтовом символе для текущего или указанного языкового стандарта.

## <a name="syntax"></a>Синтаксис

```cpp
int ___mb_cur_max_func(void);
int ___mb_cur_max_l_func(_locale_t locale);
int * __p___mb_cur_max(void);
#define __mb_cur_max (___mb_cur_max_func())
```

#### <a name="parameters"></a>Параметры

locale — структура языкового стандарта, из которой предполагается получать результаты. Если значение этого параметра — NULL, используется языковой стандарт текущего потока.

## <a name="return-value"></a>Возвращаемое значение

Максимальное число байт в многобайтовом символе для текущего языкового стандарта потока или указанного языкового стандарта.

## <a name="remarks"></a>Примечания

Это внутренняя функция, которую CRT использует для получения текущего значения макроса [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md) из локального хранилища потока. Рекомендуется использовать макрос `MB_CUR_MAX` для обеспечения переносимости кода.

Макрос `__mb_cur_max` — это удобный способ вызова функции `___mb_cur_max_func()`. Функция `__p___mb_cur_max` определяется для совместимости с Visual C++ 5.0 и более ранних версий.

Внутренние функции CRT связаны с конкретной реализацией и подлежат изменению в каждом выпуске. Мы не рекомендуем использовать их в коде.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<ctype.h>, \<stdlib.h>|

## <a name="see-also"></a>См. также раздел

[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)
