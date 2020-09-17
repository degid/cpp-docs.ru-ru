---
title: Класс basic_ostream
ms.date: 03/27/2019
f1_keywords:
- ostream/std::basic_ostream
- ostream/std::basic_ostream::flush
- ostream/std::basic_ostream::put
- ostream/std::basic_ostream::seekp
- ostream/std::basic_ostream::sentry
- ostream/std::basic_ostream::swap
- ostream/std::basic_ostream::tellp
- ostream/std::basic_ostream::write
helpviewer_keywords:
- std::basic_ostream [C++]
- std::basic_ostream [C++], flush
- std::basic_ostream [C++], put
- std::basic_ostream [C++], seekp
- std::basic_ostream [C++], sentry
- std::basic_ostream [C++], swap
- std::basic_ostream [C++], tellp
- std::basic_ostream [C++], write
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
ms.openlocfilehash: 972c21feec805e4c1032f0ebad1e3ac0d7daa7dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219239"
---
# <a name="basic_ostream-class"></a>Класс basic_ostream

Этот шаблон класса описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока с элементами типа `Elem` , также известными как [char_type](../standard-library/basic-ios-class.md#char_type), признаки символов которых определяются классом `Tr` , также известным как [traits_type](../standard-library/basic-ios-class.md#traits_type).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>Параметры

*Elem*\
Объект `char_type`.

*ТС*\
`traits_type` символа.

## <a name="remarks"></a>Примечания

Большинство функций-членов, которые перегружают [operator<<](#basic_ostream_operator_lt_lt),  — это форматированные выходные функции. Они следуют этому шаблону:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{try
{<convert and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
width(0);
// Except for operator<<(Elem)
setstate(state);

return (*this);
```

Две другие функции-члены — это неформатированные выходные функции. Они следуют этому шаблону:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (!ok)
    state |= badbit;
else
{try
{<obtain and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
setstate(state);

return (*this);
```

Обе группы функций вызывают [SetState](../standard-library/basic-ios-class.md#setstate)(**badbit**), если при вставке элементов возникает ошибка.

Объект класса basic_istream \< **Elem**, **Tr**> хранит только виртуальный открытый базовый объект класса [basic_ios](../standard-library/basic-ios-class.md) **\<Elem**, **Tr>** .

## <a name="example"></a>Пример

Дополнительные сведения о выходных потоках см. в примере для [класса basic_ofstream](../standard-library/basic-ofstream-class.md).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_ostream](#basic_ostream)|Формирует объект `basic_ostream`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[flush](#flush)|Очищает буфер.|
|[PUT](#put)|Помещает символ в поток.|
|[seekp](#seekp)|Сбрасывает позицию в потоке вывода.|
|[sentry](#sentry)|Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции.|
|[swap](#swap)|Меняет местами значения в этом объекте `basic_ostream` и значения предоставленного объекта `basic_ostream`.|
|[tellp](#tellp)|Сообщает позицию в потоке вывода.|
|[будет](#write)|Помещает символы в поток.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator=](#op_eq)|Присваивает значение указанного параметра объекта `basic_ostream` этому объекту.|
|[operator<<](#basic_ostream_operator_lt_lt)|Записывает данные в поток.|

## <a name="requirements"></a>Требования

**Заголовок:**\<ostream>

**Пространство имен:** std

## <a name="basic_ostreambasic_ostream"></a><a name="basic_ostream"></a>basic_ostream:: basic_ostream

Формирует объект `basic_ostream`.

```cpp
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```

### <a name="parameters"></a>Параметры

*strBuf*\
Объект типа [basic_streambuf](../standard-library/basic-streambuf-class.md).

*_Isstd*\
**`true`** значение, если это стандартный поток; в противном случае — **`false`** .

*right*\
Ссылка rvalue на объект типа `basic_ostream`.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует базовый класс путем вызова [init](../standard-library/basic-ios-class.md#init)( `strbuf` ). Второй конструктор инициализирует базовый класс путем вызова [basic_ios:: Move](../standard-library/basic-ios-class.md#move) `(right)` .

### <a name="example"></a>Пример

Дополнительные сведения о выходных потоках см. в примере для [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream).

## <a name="basic_ostreamflush"></a><a name="flush"></a>basic_ostream:: Flush

Очищает буфер.

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Примечания

Если [rdbuf](../standard-library/basic-ios-class.md#rdbuf) не является пустым указателем, функция вызывает **rdbuf->**[pubsync](../standard-library/basic-streambuf-class.md#pubsync). Если возвращается значение –1, функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**). Он возвращает ** \*this**.

### <a name="example"></a>Пример

```cpp
// basic_ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "test";
   cout.flush();
}
```

```Output
test
```

## <a name="basic_ostreamoperatorltlt"></a><a name="basic_ostream_operator_lt_lt"></a>basic_ostream::operator&lt;&lt;

Записывает данные в поток.

```cpp
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& (* Pfn)(basic_ostream<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(
    ios_base& (* Pfn)(ios_base&));

basic_ostream<Elem, Tr>& operator<<(
    basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
basic_ostream<Elem, Tr>& operator<<(bool val);
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int __w64  val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long __w64  val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

### <a name="parameters"></a>Параметры

*PFN*\
Указатель функции.

*strBuf*\
Указатель на объект `stream_buf`.

*val*\
Элемент, записываемый в поток.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Примечания

Заголовок \<ostream> также определяет несколько глобальных операторов вставки. Дополнительные сведения см. в разделе [operator<<](../standard-library/ostream-operators.md#op_lt_lt).

Первая функция-член гарантирует, что выражение формы `ostr << endl` вызывает [endl](../standard-library/ostream-functions.md#endl)**(OSTR)**, а затем возвращает ** \*this**. Вторая и третья функции обеспечивают аналогичное поведение других манипуляторов, таких как [hex](../standard-library/ios-functions.md#hex). Все остальные функции являются форматированными выходными функциями.

Функция

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

Извлекает элементы из *strBuf*, если *strBuf* не является пустым указателем, и вставляет их. Извлечение останавливается в конце файла или если оно создает исключение (которое создается повторно). Оно также останавливается без извлечения соответствующего элемента, если вставка завершается неудачно. Если функция не вставляет элементы или если вставка создает исключение, эта функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). В любом случае функция возвращает ** \*this**.

Функция

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

Преобразует `_Val` в логическое поле и вставляет его путем вызова [use_facet](../standard-library/basic-filebuf-class.md#open) **<num_put \<Elem, OutIt> ** `(` [getloc](../standard-library/ios-base-class.md#getloc)). [put](#put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#rdbuf)), **\*this**, `getloc`, **val**). Здесь `OutIt` определяется как [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md) **\<Elem, Tr>** . Функция возвращает ** \*this**.

Функции

```cpp
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

Каждый из них преобразует *Val* в числовое поле и вставляет его путем вызова **use_facet \<Elem, OutIt><num_put**( `getloc` ). **помещает**(**OutIt**( `rdbuf` ), ** \*this**, `getloc` , **Val**). Здесь **OutIt** определяется как **ostreambuf_iterator \<Elem, Tr> **. Функция возвращает ** \*this**.

Функции

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

Каждый из них преобразует *Val* в числовое поле и вставляет его путем вызова **use_facet \<Elem, OutIt><num_put**( `getloc` )**.** WHERE (**OutIt**( `rdbuf` ), ** \*this**, `getloc` , **Val**). Здесь **OutIt** определяется как **ostreambuf_iterator \<Elem, Tr> **. Функция возвращает ** \*this**.

### <a name="example"></a>Пример

```cpp
// basic_ostream_op_write.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_ostream<char, char_traits<char> >& somefunc(basic_ostream<char, char_traits<char> > &i)
{
    if (i == cout)
    {
        i << "i is cout" << endl;
    }
    return i;
}

class CTxtStreambuf : public basic_streambuf< char, char_traits< char > >
{
public:
    CTxtStreambuf(char *_pszText)
    {
        pszText = _pszText;
        setg(pszText, pszText, pszText + strlen(pszText));
    };
    char *pszText;
};

int main()
{
    cout << somefunc;
    cout << 21 << endl;

    hex2(cout);
    cout << 21 << endl;

    CTxtStreambuf f("text in streambuf");
    cout << &f << endl;
}
```

## <a name="basic_ostreamoperator"></a><a name="op_eq"></a>basic_ostream::operator=

Присваивает значения указанного параметра объекта `basic_ostream` этому объекту.

```cpp
basic_ostream& operator=(basic_ostream&& right);
```

### <a name="parameters"></a>Параметры

*right*\
Ссылка `rvalue` на объект `basic_ostream`.

### <a name="remarks"></a>Примечания

Оператор-член вызывает swap `(right)`.

## <a name="basic_ostreamput"></a><a name="put"></a>basic_ostream::p UT

Помещает символ в поток.

```cpp
basic_ostream<Elem, Tr>& put(char_type _Ch);
```

### <a name="parameters"></a>Параметры

*_Ch*\
Символ.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Примечания

Неформатированная выходная функция вставляет элемент *_Ch*. Он возвращает ** \*this**.

### <a name="example"></a>Пример

```cpp
// basic_ostream_put.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout.put( 'v' );
   cout << endl;
   wcout.put( L'l' );
}
```

```Output
v
l
```

## <a name="basic_ostreamseekp"></a><a name="seekp"></a>basic_ostream:: seekp

Сбрасывает позицию в выходном потоке.

```cpp
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```

### <a name="parameters"></a>Параметры

*_Pos*\
Позиция в потоке.

*_Off*\
Смещение относительно *_Way*.

*_Way*\
Одно из перечислений [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir).

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Примечания

Если значение [Fail](../standard-library/basic-ios-class.md#fail) равно **`false`** , первая функция-член вызывает **newpos =** [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)(*_Pos*) для некоторых `pos_type` временных объектов `newpos` . Если `fail` имеет значение false, вторая функция вызывает **newpos = rdbuf->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(*_Off, _Way*). В любом случае, если ( `off_type` )**newpos = =** ( `off_type` ) (-1) (операция позиционирования завершается ошибкой), функция вызывает **ISTR.** [SetState](../standard-library/basic-ios-class.md#setstate)(**failbit**). Обе функции возвращают ** \*this**.

### <a name="example"></a>Пример

```cpp
// basic_ostream_seekp.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main()
{
    using namespace std;
    ofstream x("basic_ostream_seekp.txt");
    streamoff i = x.tellp();
    cout << i << endl;
    x << "testing";
    i = x.tellp();
    cout << i << endl;
    x.seekp(2);   // Put char in third char position in file
    x << " ";

    x.seekp(2, ios::end);   // Put char two after end of file
    x << "z";
}
```

```Output
0
7
```

## <a name="basic_ostreamsentry"></a><a name="sentry"></a>basic_ostream:: Sentry

Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции.

класс Sentry {public: явный Sentry (basic_ostream \<Elem, Tr>& _Ostr); operator bool () const; ~ Sentry ();};

### <a name="remarks"></a>Примечания

Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции. Если **OSTR.** [хорошая](../standard-library/basic-ios-class.md#good) — **`true`** и **OSTR.** значение [привязки](../standard-library/basic-ios-class.md#tie) не является пустым указателем, конструктор вызывает **OSTR. Call->** [flush](#flush). Затем конструктор сохраняет значение, возвращаемое `ostr.good` в `status` . Последующий вызов метода для `operator bool` доставки этого сохраненного значения.

Если `uncaught_exception` функция Returns **`false`** и [flags](../standard-library/ios-base-class.md#flags) **&** [unitbuf](../standard-library/ios-functions.md#unitbuf) не равны нулю, деструктор вызывает [flush](#flush).

## <a name="basic_ostreamswap"></a><a name="swap"></a>basic_ostream:: swap

Меняет местами значения в этом объекте `basic_ostream` и значения предоставленного объекта `basic_ostream`.

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>Параметры

*right*\
Ссылка на объект `basic_ostream`.

### <a name="remarks"></a>Примечания

Функция – член вызывает метод [basic_ios:: Swap](../standard-library/basic-ios-class.md#swap) `(right)` для обмена содержимым этого объекта с содержимым *right*.

## <a name="basic_ostreamtellp"></a><a name="tellp"></a>basic_ostream:: теллп

Сообщает позицию в выходном потоке.

```cpp
pos_type tellp();
```

### <a name="return-value"></a>Возвращаемое значение

Позиция в выходном потоке.

### <a name="remarks"></a>Примечания

В [fail](../standard-library/basic-ios-class.md#fail) случае сбоя **`false`** функция-член возвращает [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur` , **in**). В противном случае она возвращает `pos_type`(–1).

### <a name="example"></a>Пример

Пример использования `tellp` см. в разделе [seekp](#seekp).

## <a name="basic_ostreamwrite"></a><a name="write"></a>basic_ostream:: Write

Помещает символы в поток.

```cpp
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```

### <a name="parameters"></a>Параметры

*count*\
Количество символов для помещения в поток.

*str*\
Символы для помещения в поток.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Примечания

[Неформатированная выходная функция](../standard-library/basic-ostream-class.md) вставляет последовательность элементов *Count* , начиная с *str*.

### <a name="example"></a>Пример

Пример использования `write` см. в разделе [streamsize](../standard-library/ios-typedefs.md#streamsize).

## <a name="see-also"></a>См. также раздел

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
