---
title: Определения типов &lt;regex&gt;
ms.date: 11/04/2016
f1_keywords:
- regex/std::cmatch
- regex/std::cregex_iterator
- regex/std::cregex_token_iterator
- regex/std::csub_match
- regex/std::regex
- regex/std::smatch
- regex/std::sregex_iterator
- regex/std::sregex_token_iterator
- regex/std::ssub_match
- regex/std::wcmatch
- regex/std::wcregex_iterator
- regex/std::wcregex_token_iterator
- regex/std::wcsub_match
- regex/std::wregex
- regex/std::wsmatch
- regex/std::wsregex_iterator
- regex/std::wsregex_token_iterator
- regex/std::wssub_match
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
ms.openlocfilehash: 49c2bb3f09b352413fd9f471a5ff887caa7e0238
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839755"
---
# <a name="ltregexgt-typedefs"></a>Определения типов &lt;regex&gt;

[cmatch](#cmatch)\
[cregex_iterator](#cregex_iterator)\
[cregex_token_iterator](#cregex_token_iterator)\
[csub_match](#csub_match)\
[регулярные](#regex)\
[smatch](#smatch)\
[sregex_iterator](#sregex_iterator)\
[sregex_token_iterator](#sregex_token_iterator)\
[ssub_match](#ssub_match)\
[wcmatch](#wcmatch)\
[wcregex_iterator](#wcregex_iterator)\
[wcregex_token_iterator](#wcregex_token_iterator)\
[wcsub_match](#wcsub_match)\
[wregex](#wregex)\
[wsmatch](#wsmatch)\
[wsregex_iterator](#wsregex_iterator)\
[wsregex_token_iterator](#wsregex_token_iterator)\
[wssub_match](#wssub_match)

## <a name="cmatch-typedef"></a><a name="cmatch"></a> Определение типа cmatch

Определение типа для char match_results.

```cpp
typedef match_results<const char*> cmatch;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Match_results класс](../standard-library/match-results-class.md) для итераторов типа `const char*` .

## <a name="cregex_iterator-typedef"></a><a name="cregex_iterator"></a> Определение типа cregex_iterator

Определение типа для char regex_iterator.

```cpp
typedef regex_iterator<const char*> cregex_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Regex_iterator класс](../standard-library/regex-iterator-class.md) для итераторов типа `const char*` .

## <a name="cregex_token_iterator-typedef"></a><a name="cregex_token_iterator"></a> Определение типа cregex_token_iterator

Определение типа для char regex_token_iterator

```cpp
typedef regex_token_iterator<const char*> cregex_token_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Regex_token_iterator класс](../standard-library/regex-token-iterator-class.md) для итераторов типа `const char*` .

## <a name="csub_match-typedef"></a><a name="csub_match"></a> Определение типа csub_match

Определение типа для char sub_match.

```cpp
typedef sub_match<const char*> csub_match;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Sub_match класс](../standard-library/sub-match-class.md) для итераторов типа `const char*` .

## <a name="regex-typedef"></a><a name="regex"></a> Определение типа Regex

Определение типа для char basic_regex.

```cpp
typedef basic_regex<char> regex;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Basic_regex класс](../standard-library/basic-regex-class.md) для элементов типа **`char`** .

> [!NOTE]
> Символы старших разрядов будут иметь непредсказуемые результаты с `regex`. Значения вне диапазона от 0 до 127 могут привести к неопределенному поведению.

## <a name="smatch-typedef"></a><a name="smatch"></a> Определение типа smatch

Определение типа для string match_results.

```cpp
typedef match_results<string::const_iterator> smatch;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Match_results класс](../standard-library/match-results-class.md) для итераторов типа `string::const_iterator` .

## <a name="sregex_iterator-typedef"></a><a name="sregex_iterator"></a> Определение типа sregex_iterator

Определение типа для string regex_iterator.

```cpp
typedef regex_iterator<string::const_iterator> sregex_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Regex_iterator класс](../standard-library/regex-iterator-class.md) для итераторов типа `string::const_iterator` .

## <a name="sregex_token_iterator-typedef"></a><a name="sregex_token_iterator"></a> Определение типа sregex_token_iterator

Определение типа для string regex_token_iterator.

```cpp
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Regex_token_iterator класс](../standard-library/regex-token-iterator-class.md) для итераторов типа `string::const_iterator` .

## <a name="ssub_match-typedef"></a><a name="ssub_match"></a> Определение типа ssub_match

Определение типа для string sub_match.

```cpp
typedef sub_match<string::const_iterator> ssub_match;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Sub_match класс](../standard-library/sub-match-class.md) для итераторов типа `string::const_iterator` .

## <a name="wcmatch-typedef"></a><a name="wcmatch"></a> Определение типа wcmatch

Определение типа для wchar_t match_results.

```cpp
typedef match_results<const wchar_t *> wcmatch;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Match_results класс](../standard-library/match-results-class.md) для итераторов типа `const wchar_t*` .

## <a name="wcregex_iterator-typedef"></a><a name="wcregex_iterator"></a> Определение типа wcregex_iterator

Определение типа для wchar_t regex_iterator.

```cpp
typedef regex_iterator<const wchar_t*> wcregex_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Regex_iterator класс](../standard-library/regex-iterator-class.md) для итераторов типа `const wchar_t*` .

## <a name="wcregex_token_iterator-typedef"></a><a name="wcregex_token_iterator"></a> Определение типа wcregex_token_iterator

Определение типа для wchar_t regex_token_iterator.

```cpp
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Regex_token_iterator класс](../standard-library/regex-token-iterator-class.md) для итераторов типа `const wchar_t*` .

## <a name="wcsub_match-typedef"></a><a name="wcsub_match"></a> Определение типа wcsub_match

Определение типа для wchar_t sub_match.

```cpp
typedef sub_match<const wchar_t*> wcsub_match;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Sub_match класс](../standard-library/sub-match-class.md) для итераторов типа `const wchar_t*` .

## <a name="wregex-typedef"></a><a name="wregex"></a> Определение типа wregex

Определение типа для wchar_t basic_regex.

```cpp
typedef basic_regex<wchar_t> wregex;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Basic_regex класс](../standard-library/basic-regex-class.md) для элементов типа **`wchar_t`** .

## <a name="wsmatch-typedef"></a><a name="wsmatch"></a> Определение типа wsmatch

Определение типа для wstring match_results.

```cpp
typedef match_results<wstring::const_iterator> wsmatch;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Match_results класс](../standard-library/match-results-class.md) для итераторов типа `wstring::const_iterator` .

## <a name="wsregex_iterator-typedef"></a><a name="wsregex_iterator"></a> Определение типа wsregex_iterator

Определение типа для wstring regex_iterator.

```cpp
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Regex_iterator класс](../standard-library/regex-iterator-class.md) для итераторов типа `wstring::const_iterator` .

## <a name="wsregex_token_iterator-typedef"></a><a name="wsregex_token_iterator"></a> Определение типа wsregex_token_iterator

Определение типа для wstring regex_token_iterator.

```cpp
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Regex_token_iterator класс](../standard-library/regex-token-iterator-class.md) для итераторов типа `wstring::const_iterator` .

## <a name="wssub_match-typedef"></a><a name="wssub_match"></a> Определение типа wssub_match

Определение типа для wstring sub_match.

```cpp
typedef sub_match<wstring::const_iterator> wssub_match;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [Sub_match класс](../standard-library/sub-match-class.md) для итераторов типа `wstring::const_iterator` .

## <a name="see-also"></a>См. также раздел

[\<regex>](../standard-library/regex.md)\
[Класс regex_constants](../standard-library/regex-constants-class.md)\
[Класс regex_error](../standard-library/regex-error-class.md)\
[\<regex> функции](../standard-library/regex-functions.md)\
[Класс regex_iterator](../standard-library/regex-iterator-class.md)\
[\<regex> операторы](../standard-library/regex-operators.md)\
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)\
[Класс regex_traits](../standard-library/regex-traits-class.md)
