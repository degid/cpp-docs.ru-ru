---
title: Класс strstream
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
helpviewer_keywords:
- std::strstream [C++], freeze
- std::strstream [C++], pcount
- std::strstream [C++], rdbuf
- std::strstream [C++], str
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
ms.openlocfilehash: 796bf1b3ac41a4b5a6ab5bc16239d50616f554df
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224621"
---
# <a name="strstream-class"></a>Класс strstream

Описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>Примечания

Объект сохраняет объект класса `strstreambuf`.

> [!NOTE]
> Этот класс устарел. Вместо него рекомендуется использовать [stringstream](../standard-library/sstream-typedefs.md#stringstream) или [wstringstream](../standard-library/sstream-typedefs.md#wstringstream).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание:|
|-|-|
|[strstream](#strstream)|Создает объект типа `strstream`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[фиксировать](#freeze)|Делает буфер потока недоступным для операций с буфером потока.|
|[pcount](#pcount)|Возвращает число элементов, записанных в управляемую последовательность.|
|[rdbuf](#rdbuf)|Возвращает указатель на объект `strstreambuf`, связанный с потоком.|
|[str](#str)|Вызывает [freeze](../standard-library/strstreambuf-class.md#freeze), затем возвращает указатель на начало управляемой последовательности.|

## <a name="requirements"></a>Требования

**Заголовок:**\<strstream>

**Пространство имен:** std

## <a name="strstreamfreeze"></a><a name="freeze"></a>strstream:: Freeze

Делает буфер потока недоступным для операций с буфером потока.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Параметры

*_Freezeit*\
Значение типа **`bool`** , указывающее, нужно ли заморозить поток.

### <a name="remarks"></a>Примечания

Функция-член вызывает [rdbuf](#rdbuf)  ->  [Freeze](../standard-library/strstreambuf-class.md#freeze)(_ *фризеит*).

### <a name="example"></a>Пример

Пример, в котором используется, см. в разделе [strstreambuf:: Freeze](../standard-library/strstreambuf-class.md#freeze) `freeze` .

## <a name="strstreampcount"></a><a name="pcount"></a>strstream: число:p

Возвращает число элементов, записанных в управляемую последовательность.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов, записанных в управляемую последовательность.

### <a name="remarks"></a>Примечания

Функция – член возвращает [rdbuf](#rdbuf)  ->  [pcount](../standard-library/strstreambuf-class.md#pcount).

### <a name="example"></a>Пример

См. пример использования метода pcount в разделе [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).

## <a name="strstreamrdbuf"></a><a name="rdbuf"></a>strstream:: rdbuf

Возвращает указатель на объект strstreambuf, связанный с потоком.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект strstreambuf, связанный с потоком.

### <a name="remarks"></a>Примечания

Функция члена возвращает адрес буфера сохраненного потока типа `pointer` в [strstreambuf](../standard-library/strstreambuf-class.md).

### <a name="example"></a>Пример

См. пример использования `rdbuf` в разделе [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).

## <a name="strstreamstr"></a><a name="str"></a>strstream:: str

Вызывает [freeze](../standard-library/strstreambuf-class.md#freeze), затем возвращает указатель на начало управляемой последовательности.

```cpp
char *str();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало управляемой последовательности.

### <a name="remarks"></a>Примечания

Функция – член возвращает [rdbuf](#rdbuf)  ->  [str](../standard-library/strstreambuf-class.md#str).

### <a name="example"></a>Пример

Пример, в котором используется, см. в разделе [strstreambuf:: str](../standard-library/strstreambuf-class.md#str) `str` .

## <a name="strstreamstrstream"></a><a name="strstream"></a>strstream:: strstream

Создает объект типа `strstream`.

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*count*\
Размер буфера.

*_Mode*\
Режим ввода-вывода буфера. См. раздел [ios_base::openmode](../standard-library/ios-base-class.md#openmode) для получения дополнительной информации.

*ptr*\
Буфер.

### <a name="remarks"></a>Примечания

Оба конструктора инициализируют базовый класс путем вызова [streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **SB**), где `sb` — это хранимый объект класса [strstreambuf](../standard-library/strstreambuf-class.md). Первый конструктор также инициализируется `sb` путем вызова [strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf). Второй конструктор инициализирует базовый класс одним из двух способов:

- Если `_Mode`  &  **ios_base:: App**= = 0, то *ptr* должен обозначать первый элемент массива `count` элементов, а конструктор вызывает `strstreambuf` ( `ptr` , `count` , `ptr` ).

- В противном случае *ptr* должен обозначать первый элемент массива элементов count, содержащий строку C, первый элемент которой обозначен указателем *ptr*, а конструктор вызывает `strstreambuf` ( `ptr` , `count` , `ptr`  +  `strlen` ( `ptr` )).

## <a name="see-also"></a>См. также статью

[iostream](../standard-library/istream-typedefs.md#iostream)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
