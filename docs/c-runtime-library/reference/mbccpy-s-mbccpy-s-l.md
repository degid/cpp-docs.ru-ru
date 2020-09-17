---
title: _mbccpy_s, _mbccpy_s_l
ms.date: 4/2/2020
api_name:
- _mbccpy_s
- _mbccpy_s_l
- _o__mbccpy_s
- _o__mbccpy_s_l
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
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
ms.openlocfilehash: 85db4e478b070823bb14028018d918e0f3cabbd7
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920324"
---
# <a name="_mbccpy_s-_mbccpy_s_l"></a>_mbccpy_s, _mbccpy_s_l

Копирует один многобайтовый символ из одной строки в другую. Это версии функций [_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _mbccpy_s(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src
);
errno_t _mbccpy_s_l(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src,
   locale_t locale
);
template <size_t size>
errno_t _mbccpy_s(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src
); // C++ only
template <size_t size>
errno_t _mbccpy_s_l(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src,
   locale_t locale
); // C++ only
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Место назначения копирования.

*буффсизеинбитес*<br/>
Размер буфера назначения.

*пкопиед*<br/>
Заполняется числом скопированных байтов (1 или 2 в случае успешного выполнения). Если вы не следите за числом, передайте **значение NULL** .

*src*<br/>
Многобайтовый символ для копирования.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи. Если *src* или *dest* имеет **значение NULL**или если в *dest*будет скопировано более **буффсизеинбитес** байтов, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функции возвращают **еинвал** **, а для возврата — значение** **еинвал**.

## <a name="remarks"></a>Примечания

Функция **_mbccpy_s** копирует один многобайтовый символ из *src* в *dest*. Если *src* не указывает на старший байт многобайтового символа, как определено неявным вызовом [_ismbblead](ismbblead-ismbblead-l.md), то копируется один байт, на который указывает *src* . Если *src* указывает на старший байт, но следующий байт имеет значение 0 и, таким является, недопустимый, то 0 копируется в *dest* **, параметру «T0** » присваивается значение **еилсек**, а функция возвращает **еилсек**.

**_mbccpy_s** не добавляет символ завершения null; Однако, если *src* указывает на пустой символ, то это значение NULL копируется в *dest* (это просто обычная Однобайтовая копия).

Значение в *пкопиед* заполняется числом скопированных байтов. В случае успешного выполнения операции возможны значения 1 и 2. Если передается **значение NULL** , этот параметр игнорируется.

|*src*|скопировано в *dest*|*пкопиед*|Возвращаемое значение|
|-----------|----------------------|---------------|------------------|
|не старший байт|не старший байт|1|0|
|0|0|1|0|
|старший байт, за которым следует не 0|старший байт, за которым следует не 0|2|0|
|старший байт, за которым следует 0|0|1|**EILSEQ**|

Обратите внимание, что вторая строка представляет собой особый случай первой. Также обратите внимание, что в таблице предполагается, что *буффсизеинбитес* >= *пкопиед*.

**_mbccpy_s** использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта. **_mbccpy_s_l** идентична **_mbccpy_s** за исключением того, что **_mbccpy_s_l** использует языковой стандарт, переданный для поведения, зависящего от языкового стандарта.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|Сопоставляется макросу или встраиваемой функции.|**_mbccpy_s**|Сопоставляется макросу или встраиваемой функции.|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbccpy_s**|\<mbstring.h>|
|**_mbccpy_s_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Locale](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
