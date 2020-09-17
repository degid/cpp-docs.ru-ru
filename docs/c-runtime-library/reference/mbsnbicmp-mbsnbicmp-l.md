---
title: _mbsnbicmp, _mbsnbicmp_l
ms.date: 4/2/2020
api_name:
- _mbsnbicmp_l
- _mbsnbicmp
- _o__mbsnbicmp
- _o__mbsnbicmp_l
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
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _mbsnbicmp_l
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
ms.openlocfilehash: e84e6b367c428dc26a1864db80f6828f7ec9c176
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911832"
---
# <a name="_mbsnbicmp-_mbsnbicmp_l"></a>_mbsnbicmp, _mbsnbicmp_l

Сравнивает **n** байт двух строк многобайтовых символов и игнорирует регистр.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _mbsnbicmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>Параметры

*строка1*, *строка2*<br/>
Строки с завершающим нулем для сравнения.

*count*<br/>
Число сравниваемых байтов.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение показывает связь между подстроками.

|Возвращаемое значение|Описание|
|------------------|-----------------|
|< 0|Строка *строка1* меньше, чем *строка2* подстроки.|
|0|Строка *строка1* совпадает с подстрокой *строка_замены* .|
|> 0|Строка *строка1* больше, чем *строка2* подстроки.|

При возникновении ошибки **_mbsnbicmp** возвращает **_NLSCMPERROR**, которая определена в String.h и Mbstring.h.

## <a name="remarks"></a>Примечания

Функция **_mbsnbicmp** выполняет порядковое сравнение по сравнению с первым *числом* байтов *строка1* и *строка2*. Сравнение выполняется путем преобразования каждого символа в нижний регистр; [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) — это зависящая от регистра версия **_mbsnbicmp**. Сравнение завершается, если достигнут завершающий нуль-символ в любой строке до сравнения символов *счетчика* . Если строки равны, когда завершающий нуль-символ достигается в любой строке до сравнения символов *счетчика* , более короткая строка меньше.

**_mbsnbicmp** похож на [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md), за исключением того, что он сравнивает строки вплоть до *количества* байтов, а не символов.

Две строки, содержащие символы, которые расположены между Z и a в таблице ASCII ("[", "\\", "]", "^", "_" и "\`"), сравниваются по-разному в зависимости от их регистра. Например, две строки "ABCD" и "ABCD ^" сравнивают один из них, если сравнение является строчным ("ABCDE" > "abcd ^"), а другой способ ("ABCDE" < "ABCD ^"), если он является прописным.

**_mbsnbicmp** распознает последовательности многобайтовых символов в соответствии с используемой в данный момент [многобайтовой кодовой страницей](../../c-runtime-library/code-pages.md) . На нее не влияет текущий параметр языкового стандарта.

Если *строка1* или *строка2* являются пустым указателем, **_mbsnbicmp** вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает **_NLSCMPERROR** **и устанавливает для** **еинвал**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsnbicmp**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md).

## <a name="see-also"></a>См. также раздел

[Управление строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
