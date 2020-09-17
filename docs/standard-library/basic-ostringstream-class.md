---
title: Класс basic_ostringstream
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_ostringstream
- sstream/std::basic_ostringstream::allocator_type
- sstream/std::basic_ostringstream::rdbuf
- sstream/std::basic_ostringstream::str
helpviewer_keywords:
- std::basic_ostringstream [C++]
- std::basic_ostringstream [C++], allocator_type
- std::basic_ostringstream [C++], rdbuf
- std::basic_ostringstream [C++], str
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
ms.openlocfilehash: 9e10474d3e4fb2a37e8ab52f77495758c37e8a5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376782"
---
# <a name="basic_ostringstream-class"></a>Класс basic_ostringstream

Описывает объект, который управляет вставкой элементов и закодированными объектами в `Alloc` буфер потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem,** **Tr,**>.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_ostringstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Параметры

*Alloc*\
Класс распределителя.

*Elem*\
Тип основного элемента строки.

*Tr*\
Признаки символа, соответствующие основному элементу строки.

## <a name="remarks"></a>Примечания

Класс описывает объект, который управляет вставкой элементов и закодированных объектов в буфер потока, с элементами типа, `Elem`чьи черты характера определяются классом, `Tr`и элементы которого выделяются распределителем класса. `Alloc` Этот объект сохраняет объект класса basic_stringbuf< **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|Создает объект типа `basic_ostringstream`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Тип является синонимом параметра *шаблона Alloc.*|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[rdbuf](#rdbuf)|Возвращает адрес сохраненного буфера `pointer` потока типа `Tr` `Alloc` [в basic_stringbuf,](../standard-library/basic-stringbuf-class.md)< `Elem`>.|
|[Ул](#str)|Задает или получает текст в буфере строк без изменения позиции записи.|

## <a name="requirements"></a>Требования

**Заголовок:** \<sstream>

**Пространство имен:** std

## <a name="basic_ostringstreamallocator_type"></a><a name="allocator_type"></a>basic_ostringstream::allocator_type

Тип является синонимом параметра *шаблона Alloc.*

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_ostringstreambasic_ostringstream"></a><a name="basic_ostringstream"></a>basic_ostringstream::basic_ostringstream

Создает объект типа basic_ostringstream.

```cpp
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Параметры

*_mode*\
Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*str*\
Объект типа `basic_string`.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует базовый класс, позвонив [basic_ostream](../standard-library/basic-ostream-class.md) **(sb),** `sb` где `Alloc` находится хранимый объект класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem,** **Tr,**>. Он также инициализирует **sb** путем вызова basic_stringbuf< **Elem**, **Tr**, `Alloc`>( `_Mode` &#124; `ios_base::out`).

Второй конструктор инициализирует базовый класс путем вызова basic_ostream( **sb**). Он `sb` также инициализирует, позвонив basic_stringbuf< `ios_base::out` **Elem**, **Tr**, `Alloc`> (' *Str*, `_Mode` &#124; ).

## <a name="basic_ostringstreamrdbuf"></a><a name="rdbuf"></a>basic_ostringstream:rdbuf

Возвращает адрес сохраненного буфера `pointer` потока типа [для](../standard-library/basic-stringbuf-class.md)< basic_stringbuf `Alloc` **Elem,** **Tr,**>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес буфера хранимых `pointer` потоков, типа basic_stringbuf `Alloc`< **Elem,** **Tr,**>.

### <a name="remarks"></a>Примечания

Функция участника возвращает адрес сохраненного буфера `pointer` потока типа basic_stringbuf< `Alloc` **Elem,** **Tr,**>.

### <a name="example"></a>Пример

Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="basic_ostringstreamstr"></a><a name="str"></a>basic_ostringstream::str

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
