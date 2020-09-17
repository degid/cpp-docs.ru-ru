---
title: _mbsbtype, _mbsbtype_l
ms.date: 4/2/2020
api_name:
- _mbsbtype_l
- _mbsbtype
- _o__mbsbtype
- _o__mbsbtype_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
ms.openlocfilehash: c1431a2d0886ffd3d16b43abf82b7342c166273a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909472"
---
# <a name="_mbsbtype-_mbsbtype_l"></a>_mbsbtype, _mbsbtype_l

Возвращает тип байта в строке.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _mbsbtype(
   const unsigned char *mbstr,
   size_t count
);
int _mbsbtype_l(
   const unsigned char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*мбстр*<br/>
Адрес последовательности многобайтовых символов.

*count*<br/>
Смещение в байтах относительно заголовка строки.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbsbtype** и **_mbsbtype_l** возвращают целочисленное значение, указывающее результат теста по указанному байту. Константы манифеста, представленные в приведенной ниже таблице, определены в файле Mbctype.h.

|Возвращаемое значение|Тип байта|
|------------------|---------------|
|**_MBC_SINGLE** (0)|Однобайтовый символ. Например, в кодовой странице 932 **_mbsbtype** возвращает 0, если указанный байт находится в диапазоне от 0X20 до 0X7e или 0XA1-0xDF.|
|**_MBC_LEAD** (1)|Старший байт многобайтового символа. Например, в кодовой странице 932 **_mbsbtype** возвращает значение 1, если указанный байт находится в пределах диапазона 0X81-0X9F или 0XE0-0xFC.|
|**_MBC_TRAIL** (2)|Младший байт многобайтового символа. Например, в кодовой странице 932 **_mbsbtype** возвращает 2, если указанный байт находится в диапазоне 0X40-0x7E или 0X80-0xFC.|
|**_MBC_ILLEGAL** (-1)|Строка **со значением NULL** , недопустимый символ или значение null, обнаруженное до байта *со значением смещения в* *мбстр*.|

## <a name="remarks"></a>Примечания

Функция **_mbsbtype** определяет тип байта в строке многобайтовых символов. Функция проверяет только байт со *значением* смещения в *мбстр*, игнорируя недопустимые символы перед указанным байтом.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версия этой функции без суффикса **_l** использует текущий языковой стандарт для этого поведения, зависящего от языкового стандарта. Версия с суффиксом **_l** идентична, за исключением того, что она использует переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если входная строка имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **,** параметру **еинвал** присваивается значение, а функция возвращает **_MBC_ILLEGAL**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbsbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* Для констант манифеста используются в качестве возвращаемых значений.

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
