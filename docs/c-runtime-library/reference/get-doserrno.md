---
title: _get_doserrno
ms.date: 4/2/2020
api_name:
- _get_doserrno
- _o__get_doserrno
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
- _get_doserrno
- get_doserrno
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: 7b889bccc0b1f1fd99a9a0526bbfb42a2e520970
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919385"
---
# <a name="_get_doserrno"></a>_get_doserrno

Возвращает значение ошибки, возвращенное операционной системой перед его переводом **в значение возврата** .

## <a name="syntax"></a>Синтаксис

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Указатель на целое число, которое должно быть заполнено текущим значением глобального макроса **_doserrno** .

## <a name="return-value"></a>Возвращаемое значение

Если **_get_doserrno** завершается, возвращается ноль; в случае сбоя возвращается код ошибки. Если параметр *pValue* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция **устанавливает** **Еинвал** и возвращает **еинвал**.

## <a name="remarks"></a>Примечания

Во время инициализации CRT для **_doserrno** глобальный макрос устанавливается значение 0, перед началом выполнения процесса. Ему присваивается значение ошибки операционной системы, возвращаемое вызовом любой функции уровня системы. Вызов возвращает ошибку операционной системы и никогда не сбрасывается до нуля во время выполнения. При написании кода для проверки значения ошибки, возвращаемого функцией, всегда снимайте **_doserrno** с помощью [_set_doserrno](set-doserrno.md) перед вызовом функции. Поскольку другой вызов функции может перезаписать **_doserrno**, проверьте значение с помощью **_get_doserrno** сразу после вызова функции.

Для переносимых кодов ошибок рекомендуется [_get_errno](get-errno.md) вместо **_get_doserrno** .

Возможные значения **_doserrno** определяются в>е « \<переводятся».h.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h>, \<cerrno> (C++)|

**_get_doserrno** является расширением Microsoft. Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
