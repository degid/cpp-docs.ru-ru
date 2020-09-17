---
title: '&lt;regex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <regex>
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
ms.openlocfilehash: 60548e96e0922fdcff00456b03bf9fa15bb7e3b3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841484"
---
# <a name="ltregexgt"></a>&lt;regex&gt;

Определяет шаблон класса для синтаксического анализа [регулярных выражений (C++)](../standard-library/regular-expressions-cpp.md)и несколько шаблонов классов и функций для поиска совпадений с объектом регулярного выражения.

## <a name="syntax"></a>Синтаксис

```cpp
#include <regex>
```

## <a name="remarks"></a>Примечания

Чтобы создать объект регулярного выражения, используйте [класс class basic_regex](../standard-library/basic-regex-class.md) или одну из его специализаций, [Regex](../standard-library/regex-typedefs.md#regex) и [wregex](../standard-library/regex-typedefs.md#wregex)вместе с флагами синтаксиса типа [regex_constants:: syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).

Для поиска совпадений с объектом регулярного выражения используйте функции-шаблоны [regex_match](../standard-library/regex-functions.md#regex_match) и [regex_search](../standard-library/regex-functions.md#regex_search)вместе с флагами соответствия типа [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type). Эти функции возвращают результаты с помощью шаблона класса [Match_results класса](../standard-library/match-results-class.md) и его специализаций, [cmatch](../standard-library/regex-typedefs.md#cmatch), [wcmatch](../standard-library/regex-typedefs.md#wcmatch), [smatch](../standard-library/regex-typedefs.md#smatch)и [wsmatch](../standard-library/regex-typedefs.md#wsmatch), вместе с шаблоном класса [sub_match классом](../standard-library/sub-match-class.md) и его специализациями, [csub_match](../standard-library/regex-typedefs.md#csub_match), [wcsub_match](../standard-library/regex-typedefs.md#wcsub_match), [ssub_match](../standard-library/regex-typedefs.md#ssub_match)и [wssub_match](../standard-library/regex-typedefs.md#wssub_match).

Чтобы заменить текст, совпадающий с объектом регулярного выражения, используйте функцию шаблона [regex_replace](../standard-library/regex-functions.md#regex_replace)вместе с флагами соответствия типа [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).

Чтобы выполнить итерацию нескольких совпадений объекта регулярного выражения, используйте шаблоны классов [Regex_iterator класс](../standard-library/regex-iterator-class.md) и [класс regex_token_iterator](../standard-library/regex-token-iterator-class.md) или одну из их специализаций, [cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator), [sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator), [wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator), [wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator), [cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator), [sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator), [wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)или [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)вместе с флагами соответствия типа [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).

Чтобы изменить сведения о грамматике регулярных выражений, напишите класс, реализующий характеристики регулярного выражения.

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[basic_regex](../standard-library/basic-regex-class.md)|Создание оболочки для регулярного выражения.|
|[match_results](../standard-library/match-results-class.md)|Содержит последовательность подстрок соответствия.|
|[regex_constants](../standard-library/regex-constants-class.md)|Содержит различные константы.|
|[regex_error](../standard-library/regex-error-class.md)|Сообщает о недопустимом регулярном выражении.|
|[regex_iterator](../standard-library/regex-iterator-class.md)|Перебирает результаты сопоставления.|
|[regex_traits](../standard-library/regex-traits-class.md)|Описывает характеристики элементов для сопоставления.|
|[regex_traits\<char>](../standard-library/regex-traits-char-class.md)|Описывает характеристики **`char`** для сопоставления.|
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|Описывает характеристики **`wchar_t`** для сопоставления.|
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|Перебирает подстроки соответствия.|
|[sub_match](../standard-library/sub-match-class.md)|Описывает подстроку соответствия.|

### <a name="type-definitions"></a>Определения типов

|Имя|Описание|
|-|-|
|[cmatch](../standard-library/regex-typedefs.md#cmatch)|Определение типа для **`char`** `match_results` .|
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)|Определение типа для **`char`** `regex_iterator` .|
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)|Определение типа для **`char`** `regex_token_iterator` .|
|[csub_match](../standard-library/regex-typedefs.md#csub_match)|Определение типа для **`char`** `sub_match` .|
|[регулярные](../standard-library/regex-typedefs.md#regex)|Определение типа для **`char`** `basic_regex` .|
|[smatch](../standard-library/regex-typedefs.md#smatch)|Определение типа для `string` `match_results`.|
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)|Определение типа для `string` `regex_iterator`.|
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)|Определение типа для `string` `regex_token_iterator`.|
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match)|Определение типа для `string` `sub_match`.|
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch)|Определение типа для **`wchar_t`** `match_results` .|
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)|Определение типа для **`wchar_t`** `regex_iterator` .|
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)|Определение типа для **`wchar_t`** `regex_token_iterator` .|
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)|Определение типа для **`wchar_t`** `sub_match` .|
|[wregex](../standard-library/regex-typedefs.md#wregex)|Определение типа для **`wchar_t`** `basic_regex` .|
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch)|Определение типа для `wstring` `match_results`.|
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)|Определение типа для `wstring` `regex_iterator`.|
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)|Определение типа для `wstring` `regex_token_iterator`.|
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match)|Определение типа для `wstring` `sub_match`.|

### <a name="functions"></a>Функции

|Компонент|Описание|
|-|-|
|[regex_match](../standard-library/regex-functions.md#regex_match)|Точно соответствует регулярному выражению.|
|[regex_replace](../standard-library/regex-functions.md#regex_replace)|Заменяет соответствующие регулярные выражения.|
|[regex_search](../standard-library/regex-functions.md#regex_search)|Поиск соответствия регулярному выражению.|
|[swap](../standard-library/regex-functions.md#swap)|Меняет местами объекты `basic_regex` и `match_results`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator==](../standard-library/regex-operators.md#op_eq_eq)|Сравнение различных объектов, равенство.|
|[operator!=](../standard-library/regex-operators.md#op_neq)|Сравнение различных объектов, неравенство.|
|[operator<](../standard-library/regex-operators.md#op_lt)|Сравнение различных объектов, меньше.|
|[operator\<=](../standard-library/regex-operators.md#op_gt_eq)|Сравнение различных объектов, меньше или равно.|
|[operator>](../standard-library/regex-operators.md#op_gt)|Сравнение различных объектов, больше.|
|[operator>=](../standard-library/regex-operators.md#op_gt_eq)|Сравнение различных объектов, больше или равно.|
|[operator<<](../standard-library/regex-operators.md#op_lt_lt)|Вставляет `sub_match` в поток.|

## <a name="see-also"></a>См. также раздел

[Регулярные выражения (C++)](../standard-library/regular-expressions-cpp.md)\
[Класс regex_constants](../standard-library/regex-constants-class.md)\
[Класс regex_error](../standard-library/regex-error-class.md)\
[\<regex> функции](../standard-library/regex-functions.md)\
[Класс regex_iterator](../standard-library/regex-iterator-class.md)\
[\<regex> операторы](../standard-library/regex-operators.md)\
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)\
[Класс regex_traits](../standard-library/regex-traits-class.md)\
[\<regex> определения типов](../standard-library/regex-typedefs.md)
