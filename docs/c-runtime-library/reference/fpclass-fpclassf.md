---
title: _fpclass, _fpclassf
ms.date: 4/2/2020
api_name:
- _fpclass
- _fpclassf
- _o__fpclass
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
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
ms.openlocfilehash: a6591d9348739d27831785a05f4a602aacdd4d0c
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914850"
---
# <a name="_fpclass-_fpclassf"></a>_fpclass, _fpclassf

Возвращает значение, указывающее классификацию числа с плавающей запятой для аргумента.

## <a name="syntax"></a>Синтаксис

```C
int _fpclass(
   double x
);

int _fpclassf(
   float x
); /* x64 only */
```

### <a name="parameters"></a>Параметры

*x*<br/>
Проверяемое значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **_fpclass** и **_fpclassf** возвращают целочисленное значение, которое указывает на классификацию с плавающей запятой аргумента *x*. Классификация может иметь одно из следующих значений, определенных в \<float.h>.

|Применение|Описание|
|-----------|-----------------|
|**_FPCLASS_SNAN**|Сигнальное значение NaN|
|**_FPCLASS_QNAN**|Несигнальное значение NaN|
|**_FPCLASS_NINF**|Отрицательная бесконечность (-INF)|
|**_FPCLASS_NN**|Отрицательное ненулевое нормализованное значение|
|**_FPCLASS_ND**|Отрицательное денормализованное значение|
|**_FPCLASS_NZ**|Отрицательный ноль (-0)|
|**_FPCLASS_PZ**|Положительный 0 (+ 0)|
|**_FPCLASS_PD**|Положительное денормализованное значение|
|**_FPCLASS_PN**|Положительное ненулевое нормализованное значение|
|**_FPCLASS_PINF**|Положительная бесконечность (+INF)|

## <a name="remarks"></a>Примечания

Функции **_fpclass** и **_fpclassf** являются специфичными для Microsoft. Они похожи на [fpclassify](fpclassify.md), но возвращают подробные сведения об аргументе. Функция **_fpclassf** доступна только при компиляции для платформы x64.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fpclass**, **_fpclassf**|\<float.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[fpclassify](fpclassify.md)<br/>
