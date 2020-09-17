---
title: _strdup, _wcsdup, _mbsdup
ms.date: 4/2/2020
api_name:
- _strdup
- _mbsdup
- _wcsdup
- _o__strdup
- _o__wcsdup
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcsdup
- mbsdup
- _mbsdup
- _strdup
- _ftcsdup
- _wcsdup
helpviewer_keywords:
- wcsdup function
- ftcsdup function
- _ftcsdup function
- mbsdup function
- strdup function
- _strdup function
- _wcsdup function
- copying strings
- duplicating strings
- strings [C++], copying
- _mbsdup function
- strings [C++], duplicating
- tcsdup function
- _tcsdup function
ms.assetid: 8604f8bb-95e9-45d3-93ef-20397ebf247a
ms.openlocfilehash: 42b4a890c1c7f350b83bb92a548d716ee6d9ebfc
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914475"
---
# <a name="_strdup-_wcsdup-_mbsdup"></a>_strdup, _wcsdup, _mbsdup

Повторяющиеся строки.

> [!IMPORTANT]
> **_mbsdup** нельзя использовать в приложениях, которые выполняются в среда выполнения Windows. Дополнительные сведения см. [в разделе функции CRT, которые не поддерживаются в универсальная платформа Windows приложениях](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *_strdup(
   const char *strSource
);
wchar_t *_wcsdup(
   const wchar_t *strSource
);
unsigned char *_mbsdup(
   const unsigned char *strSource
);
```

### <a name="parameters"></a>Параметры

*стрсаурце*<br/>
Исходная строка, завершающаяся символом NULL.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на место хранения копируемой строки или **значение NULL** , если не удается выделить хранилище.

## <a name="remarks"></a>Примечания

Функция **_strdup** вызывает функцию [malloc](malloc.md) , чтобы выделить место для хранения копии *Стрсаурце* , а затем копирует *стрсаурце* в выделенное пространство.

**_wcsdup** и **_mbsdup** — это версии **_strdup**для расширенных символов и многобайтовых символов. Аргументы и возвращаемое значение **_wcsdup** являются строками расширенных символов; **_mbsdup** являются строками многобайтовых символов. В остальном эти три функции ведут себя идентично.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup**|**_strdup**|**_mbsdup**|**_wcsdup**|

Поскольку **_strdup** вызывает функцию **malloc** для выделения места для хранения копии *стрсаурце*, рекомендуется всегда освобождать эту память, вызывая [бесплатную](free.md) подпрограммы для указателя, возвращаемого вызовом метода **_strdup**.

Если определены **_DEBUG** и **_CRTDBG_MAP_ALLOC** , то **_strdup** и **_wcsdup** заменяются вызовами **_strdup_dbg** и **_wcsdup_dbg** , что позволяет выполнять отладку выделения памяти. Дополнительные сведения см. в разделе [_strdup_dbg, _wcsdup_dbg](strdup-dbg-wcsdup-dbg.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_strdup**|\<string.h>|
|**_wcsdup**|\<string.h> или \<wchar.h>|
|**_mbsdup**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strdup.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char buffer[] = "This is the buffer text";
   char *newstring;
   printf( "Original: %s\n", buffer );
   newstring = _strdup( buffer );
   printf( "Copy:     %s\n", newstring );
   free( newstring );
}
```

```Output
Original: This is the buffer text
Copy:     This is the buffer text
```

## <a name="see-also"></a>См. также раздел

[Управление строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
