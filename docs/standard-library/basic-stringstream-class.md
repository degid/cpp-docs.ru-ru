---
title: Класс basic_stringstream
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_stringstream
- sstream/std::basic_stringstream::allocator_type
- sstream/std::basic_stringstream::rdbuf
- sstream/std::basic_stringstream::str
helpviewer_keywords:
- std::basic_stringstream [C++]
- std::basic_stringstream [C++], allocator_type
- std::basic_stringstream [C++], rdbuf
- std::basic_stringstream [C++], str
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
ms.openlocfilehash: f08689b1080837f042abfb3c4c52bb0ad558a448
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364872"
---
# <a name="basic_stringstream-class"></a>Класс basic_stringstream

Описывает объект, который управляет вставкой и извлечением элементов и закодированных `Alloc` объектов с помощью буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem,** **Tr,**>.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Параметры

*Alloc*\
Класс распределителя.

*Elem*\
Тип основного элемента строки.

*Tr*\
Признаки символа, соответствующие основному элементу строки.

## <a name="remarks"></a>Примечания

Шаблон класса описывает объект, который управляет вставкой и извлечением элементов и закодированных `Alloc` объектов с `Elem`помощью буфера потока класса `Tr` [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem,** **Tr**,>, с элементами типа, чьи черты характера определяются классом, и элементы которых выделяются распределителем класса. `Alloc` Этот объект сохраняет объект класса basic_stringbuf< **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_stringstream](#basic_stringstream)|Создает объект типа `basic_stringstream`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Этот тип является синонимом для параметра шаблона `Alloc`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[rdbuf](#rdbuf)|Возвращает адрес сохраненного буфера `pointer` потока типа `Tr` `Alloc` [в basic_stringbuf,](../standard-library/basic-stringbuf-class.md)< `Elem`>.|
|[Ул](#str)|Задает или получает текст в буфере строк без изменения позиции записи.|

## <a name="requirements"></a>Требования

**Заголовок:** \<sstream>

**Пространство имен:** std

## <a name="basic_stringstreamallocator_type"></a><a name="allocator_type"></a>basic_stringstream::allocator_type

Этот тип является синонимом для параметра шаблона `Alloc`.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstreambasic_stringstream"></a><a name="basic_stringstream"></a>basic_stringstream::basic_stringstream

Создает объект типа `basic_stringstream`.

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*_mode*\
Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*str*\
Объект типа `basic_string`.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует базовый класс, позвонив [basic_iostream](../standard-library/basic-iostream-class.md) **(sb),** `sb` где `Alloc` хранится объект класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem,** **Tr,**>. Он также `sb` инициализирует, позвонив basic_stringbuf< **Elem**, **Tr**, `Alloc`>(). `_Mode`

Второй конструктор инициализирует базовый класс путем вызова basic_iostream( **sb**). Он `sb` также инициализирует, позвонив basic_stringbuf< **Elem**, **Tr**, `Alloc`> (Str , *Str* `_Mode`).

## <a name="basic_stringstreamrdbuf"></a><a name="rdbuf"></a>basic_stringstream::rdbuf

Возвращает адрес буфера сохраненного потока типа **pointer** в [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес сохраненного буфера потока `pointer` типа basic_stringbuf< **Elem,** **Tr,** `Alloc`>.

### <a name="example"></a>Пример

Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="basic_stringstreamstr"></a><a name="str"></a>basic_stringstream::str

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

Возвращает объект класса [basic_string](../standard-library/basic-string-class.md)< **Elem** `Alloc` , **Tr**,>, чья контролируемая последовательность является копией последовательности, контролируемой ** \*этим.**

### <a name="remarks"></a>Примечания

Функция первого члена возвращает [rdbuf](#rdbuf) -> [str.](../standard-library/basic-stringbuf-class.md#str) Функция второго `rdbuf`  -> члена `_Newstr`вызывает **str**().

### <a name="example"></a>Пример

Смотрите [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) для примера, который использует `str`.

## <a name="see-also"></a>См. также раздел

[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[программирование йострима](../standard-library/iostream-programming.md)\
[iostreams Конвенций](../standard-library/iostreams-conventions.md)
