---
title: "_vcprintf, _vcprintf_l, _vcwprintf, _vcwprintf_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _vcwprintf
- _vcprintf_l
- _vcwprintf_l
- _vcprintf
apilocation:
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
apitype: DLLExport
f1_keywords:
- _vcwprintf_l
- _vtcprintf
- vcwprintf
- _vcwprintf
- vcprintf_l
- _vcprintf_l
- _vcprintf
- vcprintf
- vcwprintf_l
dev_langs:
- C++
helpviewer_keywords:
- vcwprintf function
- _vcwprintf_l function
- _vcprintf function
- _vcprintf_l function
- vtcprintf_l function
- vcprintf function
- vcprintf_l function
- _vtcprintf function
- _vcwprintf function
- _vtcprintf_l function
- vcwprintf_l function
- vtcprintf function
- formatted text [C++]
ms.assetid: 4ef8d237-6200-4b66-8731-8c57e5624bb1
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: a9fc87a32f3c223a509d45e013aae5a480f4b77c
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="vcprintf-vcprintfl-vcwprintf-vcwprintfl"></a>_vcprintf, _vcprintf_l, _vcwprintf, _vcwprintf_l
Записывают форматированные выходные данные в консоль с помощью указателя на список аргументов. Существуют более безопасные версии этих функций; см. раздел [_vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l](../../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md).  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _vcprintf(  
   const char* format,  
   va_list argptr  
);  
int _vcprintf_l(  
   const char* format,  
   locale_t locale,  
   va_list argptr  
);  
int _vcwprintf(  
   const wchar_t* format,  
   va_list argptr  
);  
int _vcwprintf_l(  
   const wchar_t* format,  
   locale_t locale,  
   va_list argptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `format`  
 Спецификация формата.  
  
 `argptr`  
 Указатель на список аргументов.  
  
 `locale`  
 Используемый языковой стандарт.  
  
 Дополнительные сведения см. в разделе [Спецификации формата](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Число записанных символов или отрицательное значение в случае ошибки вывода. Если параметр `format` является пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, для `errno` задается значение `EINVAL` и возвращается значение -1.  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций принимает указатель на список аргументов, а затем форматирует и записывает указанные данные в консоль. `_vcwprintf` — версия `_vcprintf` с расширенными символами. Она принимает строку расширенных символов в качестве аргумента.  
  
 Версии этих функций с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  
  
> [!IMPORTANT]
>  Убедитесь, что `format` не является строкой, определяемой пользователем. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vtcprintf`|`_vcprintf`|`_vcprintf`|`_vcwprintf`|  
|`_vtcprintf_l`|`_vcprintf_l`|`_vcprintf_l`|`_vcwprintf_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|-------------|---------------------|----------------------|  
|`_vcprintf`, `_vcprintf_l`|\<conio.h> и \<stdarg.h>|\<varargs.h>*|  
|`_vcwprintf`, `_vcwprintf_l`|\<conio.h> или \<wchar.h> и \<stdarg.h>|\<varargs.h>*|  
  
 \* Требуется для совместимости с UNIX V.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_vcprintf.cpp  
// compile with: /c  
#include <conio.h>  
#include <stdarg.h>  
  
// An error formatting function used to print to the console.  
int eprintf(const char* format, ...)  
{  
  va_list args;  
  va_start(args, format);  
  int result = _vcprintf(format, args);  
  va_end(args);  
  return result;  
}  
  
int main()  
{  
   eprintf("  (%d:%d): Error %s%d : %s\n", 10, 23, "C", 2111,  
           "<some error text>");  
   eprintf("  (Related to symbol '%s' defined on line %d).\n",  
           "<symbol>", 5 );  
}  
```  
  
```Output  
(10,23): Error C2111 : <some error text>  
  (Related to symbol '<symbol>' defined on line 5).  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)   
 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)