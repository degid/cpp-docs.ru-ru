---
title: Класс basic_istringstream
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
ms.openlocfilehash: fd2ab79466c01343cbdadbcb649e3b05eee3c2a0
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561782"
---
# <a name="basic_istringstream-class"></a>Класс basic_istringstream

Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **elem**, **tr** `Alloc`>.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Параметры

*Alloc*\
Класс распределителя.

*Elem*\
Тип основного элемента строки.

*ТС*\
Признаки символа, соответствующие основному элементу строки.

## <a name="remarks"></a>Примечания

Шаблон класса описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **elem**, **tr** `Alloc`>, с элементами типа *elem*, признаки символов которых определяются классом *tr*, а элементы выделяются распределителем *выделения*класса. Этот объект сохраняет объект класса basic_stringbuf< **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_istringstream](#basic_istringstream)|Создает объект типа `basic_istringstream`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Этот тип является синонимом для параметра шаблона `Alloc`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[rdbuf](#rdbuf)|Возвращает адрес буфера сохраненного потока типа `pointer` для [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem` , `Tr` `Alloc`>.|
|[str](#str)|Задает или получает текст в буфере строк без изменения позиции записи.|
|[swap](#swap)|Меняет местами значения в этом объекте `basic_istringstream` и значения предоставленного объекта.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator=](#op_eq)|Назначает значения этому объекту `basic_istringstream` из параметра объекта.|

## <a name="requirements"></a>Требования

**Заголовок:**\<sstream>

**Пространство имен:** std

## <a name="basic_istringstreamallocator_type"></a><a name="allocator_type"></a> basic_istringstream::allocator_type

Этот тип является синонимом для параметра шаблона `Alloc`.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstreambasic_istringstream"></a><a name="basic_istringstream"></a> basic_istringstream::basic_istringstream

Создает объект типа `basic_istringstream`.

```cpp
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```

### <a name="parameters"></a>Параметры

*_Mode*\
Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*str*\
Объект типа `basic_string`.

*right*\
Ссылка rvalue на объект `basic_istringstream`.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует базовый класс путем вызова [basic_istream](../standard-library/basic-istream-class.md)( `sb` ), где `sb` — это сохраненный объект класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem` , `Tr` `Alloc`>. Он также инициализирует `sb` путем вызова `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`).

Второй конструктор инициализирует базовый класс путем вызова `basic_istream(sb)`. Он также инициализирует `sb` путем вызова `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `str`, `_Mode` &#124; `ios_base::in`).

Третий конструктор инициализирует объект с содержимым *right*, который рассматривается как ссылка rvalue.

## <a name="basic_istringstreamoperator"></a><a name="op_eq"></a> basic_istringstream::operator=

Назначает значения этому объекту `basic_istringstream` из параметра объекта.

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>Параметры

*right*\
Ссылка rvalue на объект `basic_istringstream`.

### <a name="remarks"></a>Примечания

Оператор Member заменяет содержимое объекта содержимым *right*, которое рассматривается как присваивание перемещения ссылки rvalue.

## <a name="basic_istringstreamrdbuf"></a><a name="rdbuf"></a> basic_istringstream::rdbuf

Возвращает адрес буфера сохраненного потока типа `pointer` для [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **elem**, **tr** `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес буфера сохраненного потока типа `pointer` для basic_stringbuf< **elem**, **tr**, `Alloc`>.

### <a name="example"></a>Пример

Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="basic_istringstreamstr"></a><a name="str"></a> basic_istringstream::str

Задает или получает текст в буфере строк без изменения позиции записи.

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Параметры

*_Newstr*\
Новая строка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект класса [basic_string](../standard-library/basic-string-class.md) <  **elem**, **tr** `Alloc`>, управляемой последовательностью которого является копия последовательности, управляемой ** \* этим**объектом.

### <a name="remarks"></a>Примечания

Первая функция – член возвращает [rdbuf](#rdbuf)  ->  [str](../standard-library/basic-stringbuf-class.md#str). Вторая функция-член вызывает `rdbuf`  ->  **str**( `_Newstr` ).

### <a name="example"></a>Пример

Пример, в котором используется, см. в разделе [basic_stringbuf:: str](../standard-library/basic-stringbuf-class.md#str) `str` .

## <a name="basic_istringstreamswap"></a><a name="swap"></a> basic_istringstream::swap

Меняет местами значения двух объектов `basic_istringstream`.

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>Параметры

*right*\
Ссылка lvalue на объект `basic_istringstream`.

### <a name="remarks"></a>Примечания

Функция элемента меняет местами значения этого объекта и значения *right*.

## <a name="see-also"></a>См. также

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
