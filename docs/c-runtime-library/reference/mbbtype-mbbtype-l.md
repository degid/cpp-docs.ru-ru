---
title: _mbbtype, _mbbtype_l
ms.date: 4/2/2020
api_name:
- _mbbtype
- _mbbtype_l
- _o__mbbtype
- _o__mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
ms.openlocfilehash: dca59f2d31cc5ad843a48e9825ef6a617d46ae4a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919589"
---
# <a name="_mbbtype-_mbbtype_l"></a>_mbbtype, _mbbtype_l

Возвращает тип байта, основываясь на предыдущем байте.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _mbbtype(
   unsigned char c,
   int type
);
int _mbbtype_l(
   unsigned char c,
   int type,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*ц*<br/>
Проверяемый символ.

*type*<br/>
Тип байта для проверки.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbbtype** Возвращает тип Byte в строке. Это решение является контекстно-зависимым, как указано в значении *типа*, которое предоставляет условие теста элемента управления. *Type* — это тип предыдущего байта в строке. Константы манифеста, представленные в приведенной ниже таблице, определены в файле Mbctype.h.

|Значение *типа*|**_mbbtype** тесты для|Возвращаемое значение|*ц*|
|---------------------|--------------------------|------------------|---------|
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|**_MBC_SINGLE** (0)|Один байт (0x20-0x7E, 0xA1-0xDF)|
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|**_MBC_LEAD** (1)|Старший байт многобайтового символа (0x81-0x9F, 0xE0-0xFC)|
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|**_MBC_ILLEGAL**<br /><br /> (-1)|Недопустимый символ (любое значение, кроме 0x20-0x7E, 0xA1-0xDF, 0x81-0x9F, 0xE0-0xFC|
|1|Допустимый младший байт|**_MBC_TRAIL** (2)|Конечный байт многобайтового символа (0x40-0x7E, 0x80-0xFC)|
|1|Допустимый младший байт|**_MBC_ILLEGAL**<br /><br /> (-1)|Недопустимый символ (любое значение, кроме 0x20-0x7E, 0xA1-0xDF, 0x81-0x9F, 0xE0-0xFC|

## <a name="remarks"></a>Примечания

Функция **_mbbtype** определяет тип байта в многобайтовой кодировке. Если значение *типа* является любым значением, кроме 1, **_mbbtype** проверяет допустимый однобайтовый или старший байт многобайтового символа. Если значение *типа* равно 1, **_mbbtype** проверяет допустимый младший байт многобайтового символа.

На выходное значение влияет параметр категории **LC_CTYPE** языкового стандарта. Дополнительные сведения см. [в разделе setlocale, _wsetlocale](setlocale-wsetlocale.md) . **_Mbbtypeная** версия этой функции использует текущий языковой стандарт для этого поведения, зависящего от языкового стандарта; версия **_mbbtype_l** идентична, за исключением того, что она использует переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В более ранних версиях **_mbbtype** был назван **чкктипе**. Для нового кода используйте вместо этого **_mbbtype** .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* Для определения констант манифеста, которые используются в качестве возвращаемых значений.

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
