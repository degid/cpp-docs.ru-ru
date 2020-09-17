---
title: '&lt;sstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <sstream>
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
ms.openlocfilehash: 31a445fcc7deb5e5bade5437058cb36e28dacd40
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844331"
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;

Определяет несколько шаблонов классов, поддерживающих операции iostream для последовательностей, хранящихся в выделенном объекте массива. Такие последовательности легко преобразуются в объекты и из объектов шаблона класса [basic_string](../standard-library/basic-string-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
namespace std {
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringbuf;
typedef basic_stringbuf<char>
stringbuf;
typedef basic_stringbuf<wchar_t> wstringbuf;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_istringstream;
typedef basic_istringstream<char>
istringstream;
typedef basic_istringstream<wchar_t> wistringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_ostringstream;
typedef basic_ostringstream<char>
ostringstream;
typedef basic_ostringstream<wchar_t> wostringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringstream;
typedef basic_stringstream<char>
stringstream;
typedef basic_stringstream<wchar_t> wstringstream;
// TEMPLATE FUNCTIONS
template <class CharType, class Traits, class Allocator>
void swap(
    basic_stringbuf<CharType, Traits, Allocator>& left,
    basic_stringbuf<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_istringstream<CharType, Traits, Allocator>& left,
    basic_istringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_ostringstream<CharType, Traits, Allocator>& left,
    basic_ostringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap (
    basic_stringstream<CharType, Traits, Allocator>& left,
    basic_stringstream<CharType, Traits, Allocator>& right);

}  // namespace std
```

### <a name="parameters"></a>Параметры

*left*\
Ссылка на объект `sstream`.

*right*\
Ссылка на объект `sstream`.

## <a name="remarks"></a>Примечания

Объекты типа `char *` могут использовать функции [\<strstream>](../standard-library/strstream.md) для потоковой передачи. Однако вместо \<strstream> рекомендуется использовать \<sstream>.

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|Создает тип, `basic_istringstream` специализированный для **`char`** параметра шаблона.|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|Создает тип, `basic_ostringstream` специализированный для **`char`** параметра шаблона.|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|Создает тип, `basic_stringbuf` специализированный для **`char`** параметра шаблона.|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|Создает тип, `basic_stringstream` специализированный для **`char`** параметра шаблона.|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|Создает тип, `basic_istringstream` специализированный для **`wchar_t`** параметра шаблона.|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|Создает тип, `basic_ostringstream` специализированный для **`wchar_t`** параметра шаблона.|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|Создает тип, `basic_stringbuf` специализированный для **`wchar_t`** параметра шаблона.|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|Создает тип, `basic_stringstream` специализированный для **`wchar_t`** параметра шаблона.|

### <a name="manipulators"></a>Манипуляторы

|Имя|Описание|
|-|-|
|[swap](../standard-library/sstream-functions.md#sstream_swap)|Меняет местами значения двух объектов `sstream`.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|Описывает буфер потока, который управляет передачей элементов типа `Elem`, признаки символов которого определяются с помощью класса `Tr`, в последовательность элементов, сохраненную в объекте массива, и из нее.|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **elem**, **tr** `Alloc`>, с элементами типа `Elem` , признаки символов которых определяются классом `Tr` и элементы, выделенные распределителем класса `Alloc` .|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **elem**, **tr** `Alloc`>, с элементами типа `Elem` , признаки символов которых определяются классом `Tr` и элементы, выделенные распределителем класса `Alloc` .|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|Описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **elem**, **tr** `Alloc`>, с элементами типа `Elem` , признаки символов которых определяются классом `Tr` , и элементы, выделенные распределителем класса `Alloc` .|

## <a name="requirements"></a>Требования

- **Заголовок:**\<sstream>

- **Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
