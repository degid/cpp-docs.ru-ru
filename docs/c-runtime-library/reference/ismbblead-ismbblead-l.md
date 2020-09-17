---
title: _ismbblead, _ismbblead_l
description: Содержит описание библиотеки времени выполнения Microsoft C (CRT) _ismbblead и _ismbblead_l функций.
ms.date: 4/2/2020
api_name:
- _ismbblead_l
- _ismbblead
- _o__ismbblead
- _o__ismbblead_l
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
- ismbblead_l
- istlead
- _ismbblead
- _ismbblead_l
- ismbblead
- _istlead
helpviewer_keywords:
- _ismbblead_l function
- ismbblead function
- _ismbblead function
- istlead function
- ismbblead_l function
- _istlead function
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
ms.openlocfilehash: 7680793b71c4535ed75433ac98167e52a39896ba
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918671"
---
# <a name="_ismbblead-_ismbblead_l"></a>_ismbblead, _ismbblead_l

Проверяет символ, чтобы определить, является ли он старшим байтом многобайтового символа.

## <a name="syntax"></a>Синтаксис

```C
int _ismbblead(
   unsigned int c
);
int _ismbblead_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*ц*\
Целое число, которое требуется проверить.

*языкового стандарта*\
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Функция возвращает ненулевое значение, если целое число *c* является первым байтом многобайтового символа.

## <a name="remarks"></a>Примечания

Многобайтовые символы состоят из старшего байта, за которым следует конечный байт. Старшие байты относятся к определенному диапазону данной кодировки. Например, только в кодовой странице 932, это диапазон из 0x81-0x9F и 0xE0-0xFC.

**_ismbblead** использует текущий языковой стандарт для поведения, зависящего от языкового стандарта. **_ismbblead_l** является идентичным, за исключением того, что использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если языковой стандарт — UTF-8, **_ismbblead** и **_ismbblead_l** всегда возвращают значение 0 (false), независимо от того, является ли *c* старшим байтом.

**_ismbblead** и **_ismbblead_l** являются специфичными для Майкрософт, а не частью стандартной библиотеки C. Мы не рекомендуем использовать их в том месте, где нужен переносимый код. Для стандартной совместимости C используйте вместо него **мбрлен** .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления универсальных текстовых подпрограмм

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istlead**|Всегда возвращает значение false|**_ismbblead**|Всегда возвращает значение false|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_ismbblead**|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbblead_l**|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* Для констант манифестов, используемых в условиях проверки.

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация байтов](../../c-runtime-library/byte-classification.md)\
[подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)\
[mbrlen](mbrlen.md)
