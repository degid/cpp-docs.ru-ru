---
title: Функции vprintf
ms.date: 11/04/2016
api_location:
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- vprintf
helpviewer_keywords:
- vprintf function
- formatted text [C++]
ms.assetid: 02ac7c51-eab1-4bf0-bf4c-77065e3fa744
ms.openlocfilehash: 2455655404bd61c220ebe4e3d018bc81204fa51e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845371"
---
# <a name="vprintf-functions"></a>Функции vprintf

Каждая из функций `vprintf` принимает указатель на список аргументов, а затем форматирует и записывает указанные данные в определенное назначение. Функции различаются тем, как они выполняют проверку параметров, принимают ли двухбайтовые или однобайтовые строки символов, какое используют назначение для вывода и позволяют ли указать в строке формата порядок использования параметров.

[_vcprintf, _vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)\
[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)\
[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)\
[vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)\
[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)\
[_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)\
[vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)\
[_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)\
[_vsnprintf, _vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) 
 [vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)\
[_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)\
[vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)

## <a name="remarks"></a>Примечания

Функции `vprintf` выполняют те же действия, что и перечисленные в следующей таблице аналоги. Но при этом каждая функция `vprintf` принимает указатель на список аргументов, а их аналоги — сам список аргументов.

Эти функции форматируют данные для вывода в назначение, как описано ниже.

|Функция|Функция-аналог|Назначение выходных данных|Проверка параметров|Поддержка позиционных параметров|
|--------------|--------------------------|------------------------|--------------------------|----------------------------------|
|`_vcprintf`|[_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|console|Проверка значений null.|Нет|
|`_vcwprintf`|[_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|console|Проверка значений null.|Нет|
|`vfprintf`|[fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Поток*|Проверка значений null.|Нет|
|**vfprintf_p**|[fprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Поток*|Проверка значений null и допустимого формата.|да|
|`vfprintf_s`|[fprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Поток*|Проверка значений null и допустимого формата.|Нет|
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Поток*|Проверка значений null.|Нет|
|**vfwprintf_p**|[fwprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Поток*|Проверка значений null и допустимого формата.|да|
|`vfwprintf_s`|[fwprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Поток*|Проверка значений null и допустимого формата.|Нет|
|`vprintf`|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Проверка значений null.|Нет|
|**vprintf_p**|[printf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Проверка значений null и допустимого формата.|да|
|`vprintf_s`|[printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Проверка значений null и допустимого формата.|Нет|
|`vwprintf`|[wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Проверка значений null.|Нет|
|**vwprintf_p**|[wprintf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Проверка значений null и допустимого формата.|да|
|`vwprintf_s`|[wprintf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Проверка значений null и допустимого формата.|Нет|
|**vsprintf**|[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|память, на которую указывает *buffer*|Проверка значений null.|Нет|
|**vsprintf_p**|[sprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|память, на которую указывает *buffer*|Проверка значений null и допустимого формата.|да|
|`vsprintf_s`|[sprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|память, на которую указывает *buffer*|Проверка значений null и допустимого формата.|Нет|
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|память, на которую указывает *buffer*|Проверка значений null.|Нет|
|**vswprintf_p**|[swprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|память, на которую указывает *buffer*|Проверка значений null и допустимого формата.|да|
|`vswprintf_s`|[swprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|память, на которую указывает *buffer*|Проверка значений null и допустимого формата.|Нет|
|`_vscprintf`|[_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|память, на которую указывает *buffer*|Проверка значений null.|Нет|
|`_vscwprintf`|[_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|память, на которую указывает *buffer*|Проверка значений null.|Нет|
|`_vsnprintf`|[_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|память, на которую указывает *buffer*|Проверка значений null.|Нет|
|`_vsnwprintf`|[_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|память, на которую указывает *buffer*|Проверка значений null.|Нет|

Аргумент `argptr` имеет тип `va_list`, который определен в VARARGS.H и STDARG.H. Переменная `argptr` должна быть инициализирована через **va_start**, и ее можно инициализировать повторно дополнительными вызовами `va_arg`; в этом случае `argptr` указывает на начало списка аргументов, которые преобразуются и передаются в вывод в соответствии со спецификацией, указанной в аргументе *format*. *format* имеет ту же форму и выполняет ту же роль, что и аргумент *format* функции [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). Ни одна из этих функций не вызывает `va_end`. Более полное описание каждой функции `vprintf` вы найдете в описании соответствующей функции-аналога, указанной в таблице выше.

`_vsnprintf` отличается от **vsprintf** тем, что она записывает в *buffer* не более *count* байтов.

Версии этих функций с инфиксом **w** в имени — это двухбайтовые версии соответствующих функций, не имеющих в имени инфикса **w**. В каждой из этих функций *buffer* и *format* принимают строки двухбайтовых символов. Во всем остальном двухбайтовые версии функций работают полностью так же, как и соответствующие функции для однобайтовой кодировки.

Версии функций с суффиксами **_s** и **_p** являются более защищенными. Эти версии проверяют строки формата и создают исключение, если строка формата имеет неправильный формат (например, если используются недопустимые символы форматирования).

Версии этих функций с суффиксом **_p** позволяют указать порядок подстановки предоставленных аргументов в строку формата. Дополнительные сведения см. в разделе [Позиционные параметры printf_p](../c-runtime-library/printf-p-positional-parameters.md).

Для **vsprintf**, `vswprintf` `_vsnprintf` и `_vsnwprintf` , если копирование происходит между перекрытием строк, поведение не определено.

> [!IMPORTANT]
> Убедитесь, что *format* не является строкой, определяемой пользователем. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns). При использовании безопасных версий этих функций (с суффиксом **_s** или **_p**) со строкой формата, определяемой пользователем, может возникать исключение недопустимого параметра, если определяемая пользователем строка содержит недопустимые символы форматирования.

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)
