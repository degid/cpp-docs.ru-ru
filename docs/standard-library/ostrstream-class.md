---
title: Класс ostrstream
ms.date: 11/04/2016
f1_keywords:
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
helpviewer_keywords:
- std::ostrstream [C++], freeze
- std::ostrstream [C++], pcount
- std::ostrstream [C++], rdbuf
- std::ostrstream [C++], str
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
ms.openlocfilehash: f17d8006aea6c5467f8de270318386bb12df264a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222229"
---
# <a name="ostrstream-class"></a>Класс ostrstream

Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class ostrstream : public ostream
```

## <a name="remarks"></a>Примечания

Объект сохраняет объект класса `strstreambuf`.

> [!NOTE]
> Этот класс устарел. Вместо него рекомендуется использовать [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) или [wostringstream](../standard-library/sstream-typedefs.md#wostringstream).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[ostrstream](#ostrstream)|Создает объект типа `ostrstream`.|

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

## <a name="ostrstreamfreeze"></a><a name="freeze"></a>ostrstream:: Freeze

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

Пример, в котором используется, см. в разделе [strstream:: Freeze](../standard-library/strstreambuf-class.md#freeze) `freeze` .

## <a name="ostrstreamostrstream"></a><a name="ostrstream"></a>ostrstream:: ostrstream

Создает объект типа `ostrstream`.

```cpp
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Параметры

*ptr*\
Буфер.

*count*\
Размер буфера в байтах.

*_Mode*\
Режим ввода-вывода буфера. См. раздел [ios_base::openmode](../standard-library/ios-base-class.md#openmode) для получения дополнительной информации.

### <a name="remarks"></a>Примечания

Оба конструктора инициализируют базовый класс путем вызова [ostream](../standard-library/ostream-typedefs.md#ostream)(**SB**), где `sb` — это хранимый объект класса [strstreambuf](../standard-library/strstreambuf-class.md). Первый конструктор также инициализируется `sb` путем вызова `strstreambuf` . Второй конструктор инициализирует базовый класс одним из двух способов:

- Если `_Mode`  &  **ios_base:: App**= = 0, то `ptr` параметр должен обозначать первый элемент массива `count` элементов, а конструктор вызывает `strstreambuf` ( `ptr` , `count` , `ptr` ).

- В противном случае `ptr` должен обозначать первый элемент массива элементов count, содержащий строку C, первый элемент которой обозначен `ptr` , а конструктор вызывает `strstreambuf` ( `ptr` , `count` , `ptr`  +  `strlen` ( `ptr` )).

## <a name="ostrstreampcount"></a><a name="pcount"></a>ostrstream: число:p

Возвращает число элементов, записанных в управляемую последовательность.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов, записанных в управляемую последовательность.

### <a name="remarks"></a>Примечания

Функция – член возвращает [rdbuf](#rdbuf)  ->  [pcount](../standard-library/strstreambuf-class.md#pcount).

### <a name="example"></a>Пример

См. раздел [strstream::pcount](../standard-library/strstreambuf-class.md#pcount) с примером использования `pcount`.

## <a name="ostrstreamrdbuf"></a><a name="rdbuf"></a>ostrstream:: rdbuf

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

## <a name="ostrstreamstr"></a><a name="str"></a>ostrstream:: str

Вызывает [freeze](../standard-library/strstreambuf-class.md#freeze), затем возвращает указатель на начало управляемой последовательности.

```cpp
char *str();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало управляемой последовательности.

### <a name="remarks"></a>Примечания

Функция – член возвращает [rdbuf](#rdbuf)  ->  [str](../standard-library/strstreambuf-class.md#str).

### <a name="example"></a>Пример

Пример, в котором используется, см. в разделе [strstream:: str](../standard-library/strstreambuf-class.md#str) `str` .

## <a name="see-also"></a>См. также раздел

[ostream](../standard-library/ostream-typedefs.md#ostream)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
