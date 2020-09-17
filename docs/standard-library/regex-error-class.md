---
title: Класс regex_error
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
ms.openlocfilehash: f8f3c88c1b203ed7fcea148843fa99590e27b888
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331870"
---
# <a name="regex_error-class"></a>Класс regex_error

Сообщает о неверном объекте basic_regex.

## <a name="syntax"></a>Синтаксис

```cpp
class regex_error
: public std::runtime_error
```

## <a name="remarks"></a>Примечания

Класс описывает объект исключения, создаваемый для уведомления об ошибке в построении или использовании объекта `basic_regex` .

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[regex_error](#regex_error)|Создает объект.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Код](#code)|Возвращает код ошибки.|

## <a name="requirements"></a>Требования

**Заголовок:** \<regex>

**Пространство имен:** std

## <a name="example"></a>Пример

```cpp
// std__regex__regex_error.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex_error paren(std::regex_constants::error_paren);

    try
        {
        std::regex rx("(a");
        }
    catch (const std::regex_error& rerr)
        {
        std::cout << "regex error: "
            << (rerr.code() == paren.code() ? "unbalanced parentheses" : "")
            << std::endl;
        }
    catch (...)
        {
        std::cout << "unknown exception" << std::endl;
        }

    return (0);
    }
```

```Output
regex error: unbalanced parentheses
```

## <a name="regex_errorcode"></a><a name="code"></a>regex_error::Код

Возвращает код ошибки.

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает значение, которое было передано в конструктор объекта.

## <a name="regex_errorregex_error"></a><a name="regex_error"></a>regex_error:regex_error

Создает объект.

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>Параметры

*Ошибка*\
Код ошибки.

### <a name="remarks"></a>Примечания

Конструктор строит объект, который удерживает *ошибку*значения.

## <a name="see-also"></a>См. также раздел

[\<regex>](../standard-library/regex.md)\
[класс regex_constants](../standard-library/regex-constants-class.md)\
[\<функции regex>](../standard-library/regex-functions.md)\
[класс regex_iterator](../standard-library/regex-iterator-class.md)\
[\<операторы regex>](../standard-library/regex-operators.md)\
[класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)\
[класс regex_traits](../standard-library/regex-traits-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)
