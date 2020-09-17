---
title: Структура from_chars_result
ms.date: 7/23/2020
f1_keywords:
- std::from_chars_result
helpviewer_keywords:
- from_chars_result class
- from_chars_result structure
ms.openlocfilehash: 5a5dcfe6e5b59644e6ebf55d68ce43975e7d3c9d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215768"
---
# <a name="from_chars_result-struct"></a>Структура from_chars_result

## <a name="syntax"></a>Синтаксис

```cpp
struct from_chars_result {
    const char* ptr;
    errc ec;
};
```

|Член|Описание|
|--|--|
|`ptr`| Если `ec` значение равно `errc{}` , преобразование прошло успешно и `ptr` указывает на первый символ, который не является частью распознанного числа. |
|`ec` | Код ошибки преобразования. Конкретные коды ошибок см. в разделе [`errc`](system-error-enums.md#errc) .|

### <a name="remarks"></a>Примечания

Пример. синтаксический анализ `"1729cats"` в виде десятичного целого числа будет выполнен, и `ptr` будет указывать на то, `'c'` что является первой нецифровой цифрой `"1729"` .

Если ни один из символов не соответствует шаблону числа, `from_chars_result.ptr` указывает на `first` , и `from_chars_result.ec` имеет значение `errc::invalid_argument` .

Если шаблон числа соответствует только некоторым символам, `from_chars_result.ptr` указывает на первый символ, не совпадающий с шаблоном, или значение `last` параметра, если все символы совпадают.

Если проанализированное значение не соответствует диапазону выполняемого преобразования, `from_chars_result.ec` то параметр имеет тип `errc::result_out_of_range` .

## <a name="requirements"></a>Требования

**Заголовок:**\<charconv>

**Пространство имен:** std

**Параметр компилятора:** /std: c++ 17 или более поздней версии является обязательным

## <a name="see-also"></a>См. также раздел

[from_chars](charconv-functions.md#from_chars)
