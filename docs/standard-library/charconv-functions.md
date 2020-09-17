---
title: '&lt;&gt;функции чарконв'
description: Описывает <charconv> библиотечные функции, которые преобразуют целые или числовые значения с плавающей запятой в символы или из них.
ms.date: 08/20/2020
f1_keywords:
- charconv/std::to_chars
- charconv/std::from_chars
helpviewer_keywords:
- std::charconv [C++], to_chars
- std::charconv [C++], from_chars
ms.openlocfilehash: b8117f2a272f33be2bb5fef6ba8fa53ec794b63b
ms.sourcegitcommit: f1752bf90b4f869633a859ace85439ca19e208b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "88722158"
---
# <a name="ltcharconvgt-functions"></a>&lt;&gt;функции чарконв

\<charconv>Заголовок содержит следующие функции, не являющиеся членами:

| **Функции, не являющиеся членами** | **Описание** |
|-|-|
|[to_chars](#to_chars) | Преобразование целого числа или значения с плавающей запятой в последовательность **`char`** . |
|[from_chars](#from_chars) | Преобразование последовательности **`char`** в целое число или значение с плавающей запятой. |

Эти функции преобразования настроены для повышения производительности, а также поддерживают кратчайшие круговые пути. Самое короткое поведение означает, что при преобразовании числа в тип char записывается достаточно точности, чтобы обеспечить восстановление исходного числа при преобразовании этих символов обратно в число с плавающей запятой.

- При преобразовании символов в число числовое значение не обязательно должно завершаться нулем. Аналогично, при преобразовании числа в символы результат не завершается нулем.
- Функции преобразования не распределяют память. Вы владеете буфером во всех случаях.
- Функции преобразования не вызывают исключение. Возвращается результат, с помощью которого можно определить, выполнено ли преобразование.
- Функции преобразования не учитывают режим выполнения округления в режиме ожидания.
- Функции преобразования не поддерживают языковой стандарт. Они всегда печатают и анализируют десятичные разделители как `'.'` , а не как "," для национальных настроек, использующих запятые.

## `to_chars`

Преобразование целого числа или значения с плавающей запятой в последовательность **`char`** .

Преобразует `value` в символьную строку, заполняя диапазон \[ `first` , `last` ), где \[ `first` , `last` ) должен быть допустимым диапазоном.
Возвращает [структуру to_chars_result](to-chars-result-structure.md). Если преобразование выполнено успешно, как указано `to_char_result.ec` , элемент `ptr` является указателем на один знак после знака. В противном случае `to_char_result.ec` имеет значение, `errc::value_too_large` `to_char_result.ptr` имеет значение `last` , а содержимое диапазона \[ `first` , `last` ) не задано.

Единственный способ, который `to_chars` может завершиться ошибкой, — создать достаточно большой буфер для хранения результата.

```cpp
// integer to chars

to_chars_result to_chars(char* first, char* last, char value, int base = 10);
to_chars_result to_chars(char* first, char* last, signed char value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned char value, int base = 10);
to_chars_result to_chars(char* first, char* last, short value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned short value, int base = 10);
to_chars_result to_chars(char* first, char* last, int value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned int value, int base = 10);
to_chars_result to_chars(char* first, char* last, long value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned long value, int base = 10);
to_chars_result to_chars(char* first, char* last, long long value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned long long value, int base = 10);
to_chars_result to_chars(char* first, char* last, bool value, int base = 10) = delete;

// floating-point to chars

to_chars_result to_chars(char* first, char* last, float value);
to_chars_result to_chars(char* first, char* last, double value);
to_chars_result to_chars(char* first, char* last, long double value);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt, int precision);
```

### <a name="parameters"></a>Параметры

*first*\
Указывает на начало буфера для заполнения.

*last*\
Указывает на один знак после конца буфера для заполнения.

*value*\
Преобразуемое значение. Если `value` параметр имеет отрицательное значение, представление начинается с `-` .

*из*\
Для целочисленных преобразований — основание, используемое при преобразовании `value` в chars. Должно быть в диапазоне от 2 до 36 включительно. Начальных нулей не будет. Цифры в диапазоне 10.35 (включительно) представлены в виде строчных символов a.. гармошкой

*fmt*\
Для преобразований с плавающей запятой — битовая маска, указывающая используемый формат преобразования, например научный, фиксированный или шестнадцатеричный. Дополнительные сведения см. в разделе [chars_format](chars-format-class.md) .

*обеспечивают*\
Для преобразований с плавающей запятой число разрядов точности для преобразованного значения.

### <a name="return-value"></a>Возвращаемое значение

[To_chars_result](to-chars-result-structure.md) , содержащий результат преобразования.

### <a name="remarks"></a>Примечания

Функции, принимающие параметр [chars_format](chars-format-class.md) , определяют спецификатор преобразования, как если бы он использовался следующим образом. спецификатор преобразования имеет значение, если имеет значение, если равно, `printf()` `'f'` `fmt` `chars_format::fixed` `'e'` `fmt` `chars_format::scientific` `'a'` (без начального значения `0x` в результате), если имеет `fmt` значение `chars_format::hex` , а `'g'` Если `fmt` имеет значение `chars_format::general` . Указание кратчайшей фиксированной нотации по-прежнему может привести к длинному выходу, так как это самое короткое возможное представление, когда значение слишком велико или очень мало.

В следующей таблице описывается поведение преобразования с учетом различных сочетаний `fmt` `precision` параметров и. Термин "кратчайший порядок приема-передачи" означает запись минимального необходимого количества цифр, чтобы синтаксический анализ этого представления с помощью соответствующей `from_chars` функции полностью восстановит значение.

| `fmt``precision`сочетание и | Выходные данные |
|--|--|
|  Нет | Какая-либо фиксированная или экспоненциальная нотация короче, предваряется как тиебреакер.</br>Это поведение нельзя имитировать с помощью перегрузок, принимающих `fmt` параметр. |
| `fmt` | Самое короткое поведение в указанном формате, например в кратчайшем экспоненциальном формате. |
| `fmt` и `precision` | Использует заданную точность, следующий `printf()` стиль, без кратчайшего поведения приема-передачи. |

### <a name="example"></a>Пример

```cpp
#include <charconv>
#include <stdio.h>
#include <system_error>

template <typename T> void TestToChars(const T t)
{
    static_assert(std::is_floating_point_v<T>);
    constexpr bool IsFloat = std::is_same_v<T, float>;

    char buf[100]; // 100 is large enough for double and long double values because the longest possible outputs are "-1.23456735e-36" and "-1.2345678901234567e-100".
    constexpr size_t size = IsFloat ? 15 : 24;
    const std::to_chars_result res = std::to_chars(buf, buf + size, t);  // points to buffer area it can use. Must be char, not wchar_t, etc.
    
    if (res.ec == std::errc{}) // no error
    {
        // %.*s provides the exact number of characters to output because the output range, [buf, res.ptr), isn't null-terminated
        printf("success: %.*s\n", static_cast<int>(res.ptr - buf), buf);
    }
    else // probably std::errc::value_too_large
    {
        printf("Error: %d\n", static_cast<int>(res.ec));
    }
}

int main()
{
    TestToChars(123.34);
    return 0;
}
```

## `from_chars`

Преобразование последовательности **`char`** в целое число или значение с плавающей запятой.

```cpp
// char to an integer value

from_chars_result from_chars(const char* first, const char* last, char& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, signed char& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned char& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, short& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned short& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, int& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned int& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, long& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned long& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, long long& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned long long& value, int base = 10);

// char to a floating-point value

from_chars_result from_chars(const char* first, const char* last, float& value, chars_format fmt = chars_format::general);
from_chars_result from_chars(const char* first, const char* last, double& value, chars_format fmt = chars_format::general);
from_chars_result from_chars(const char* first, const char* last, long double& value, chars_format fmt = chars_format::general);
```

### <a name="parameters"></a>Параметры

*first*\
Указывает на начало буфера преобразуемых символов.

*last*\
Указывает на одну точку после конечного элемента буфера символов для преобразования.

*value*\
Если преобразование выполнено успешно, содержит результат преобразования.

*из*\
Для целочисленных преобразований — основание, используемое во время преобразования. Должно быть в диапазоне от 2 до 36 включительно.

*fmt*\
Для преобразований с плавающей запятой — формат преобразуемой последовательности символов. Дополнительные сведения см. в разделе [chars_format](chars-format-class.md) .

### <a name="remarks"></a>Примечания

`from_chars()`Функции анализируют строку \[ `first` , `last` ) для шаблона числа, где \[ `first` , `last` ) должно быть допустимым диапазоном.

При синтаксическом анализе символов пробел не учитывается. В отличие от, например, `strtod()` буфер должен начинаться с допустимого числового представления.

Возвращает [структуру from_chars_result](from-chars-result-structure.md).

Если ни один из символов не соответствует шаблону числа, `value` то не изменяется, `from_chars_result.ptr` указывает на `first` , и `from_chars_result.ec` имеет значение `errc::invalid_argument` .

Если шаблон числа соответствует только некоторым символам, `from_chars_result.ptr` указывает на первый символ, не совпадающий с шаблоном, или значение `last` параметра, если все символы совпадают.

Если проанализированное значение не находится в диапазоне, представленном типом `value` , `value` то параметр не изменяется и `from_chars_result.ec` является `errc::result_out_of_range` .

В противном случае `value` для задается Проанализированное значение, после округления и `from_chars_result.ec` равно `errc{}` .

### <a name="example"></a>Пример

```cpp
#include <charconv>
#include <stdio.h>
#include <string_view>
#include <system_error>

double TestFromChars(const std::string_view sv)
{
    const char* const first = sv.data();
    const char* const last = first + sv.size();
    double dbl;

    const std::from_chars_result res = std::from_chars(first, last, dbl);

    if (res.ec == std::errc{}) // no error
    {
        printf("success: %g\n", dbl);
    }
    else
    {
        printf("Error: %d\n", static_cast<int>(res.ec));
    }

    return dbl;
}

int main()
{
    double dbl = TestFromChars("123.34");
    return 0;
}
```

## <a name="requirements"></a>Требования

**Заголовок:**\<charconv>

**Пространство имен:** std

/std: требуется c++ 17 или более поздней версии.

## <a name="see-also"></a>См. также

[\<charconv>](charconv.md)  
Наиболее [короткая десятичная строка, с которой циклическими обходовми](https://www.exploringbinary.com/the-shortest-decimal-string-that-round-trips-examples/) 
 [описатели формата printf ()](..\c-runtime-library\format-specification-syntax-printf-and-wprintf-functions.md)