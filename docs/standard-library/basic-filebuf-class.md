---
title: Класс basic_filebuf
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_filebuf
- fstream/std::basic_filebuf::char_type
- fstream/std::basic_filebuf::int_type
- fstream/std::basic_filebuf::off_type
- fstream/std::basic_filebuf::pos_type
- fstream/std::basic_filebuf::traits_type
- fstream/std::basic_filebuf::close
- fstream/std::basic_filebuf::is_open
- fstream/std::basic_filebuf::open
- fstream/std::basic_filebuf::overflow
- fstream/std::basic_filebuf::pbackfail
- fstream/std::basic_filebuf::seekoff
- fstream/std::basic_filebuf::seekpos
- fstream/std::basic_filebuf::setbuf
- fstream/std::basic_filebuf::Swap
- fstream/std::basic_filebuf::sync
- fstream/std::basic_filebuf::uflow
- fstream/std::basic_filebuf::underflow
helpviewer_keywords:
- std::basic_filebuf [C++]
- std::basic_filebuf [C++], char_type
- std::basic_filebuf [C++], int_type
- std::basic_filebuf [C++], off_type
- std::basic_filebuf [C++], pos_type
- std::basic_filebuf [C++], traits_type
- std::basic_filebuf [C++], close
- std::basic_filebuf [C++], is_open
- std::basic_filebuf [C++], open
- std::basic_filebuf [C++], overflow
- std::basic_filebuf [C++], pbackfail
- std::basic_filebuf [C++], seekoff
- std::basic_filebuf [C++], seekpos
- std::basic_filebuf [C++], setbuf
- std::basic_filebuf [C++], Swap
- std::basic_filebuf [C++], sync
- std::basic_filebuf [C++], uflow
- std::basic_filebuf [C++], underflow
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
ms.openlocfilehash: 7dc244cde3d77ad99add1c35716779a55eac9263
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219317"
---
# <a name="basic_filebuf-class"></a>Класс basic_filebuf

Описывает буфер потока, управляющий передачей элементов типа *Char_T*, признаки символов которых определяются классом *tr*, в последовательность элементов, хранящуюся во внешнем файле, и из нее.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_filebuf : public basic_streambuf<Char_T, Tr>
```

### <a name="parameters"></a>Параметры

*Char_T*\
Базовый элемент буфера файла.

*ТС*\
Признаки базового элемента буферного файла (обычно `char_traits<Char_T>` ).

## <a name="remarks"></a>Примечания

Шаблон класса описывает буфер потока, который управляет передачей элементов типа *Char_T*, признаки символов которых определяются классом *tr*, в последовательность элементов, хранящуюся во внешнем файле, и из нее.

> [!NOTE]
> Объекты типа `basic_filebuf` создаются с внутренним буфером типа __char \* __ независимо от `char_type` заданного параметром типа *Char_T*. Это означает, что строка в Юникоде (содержащая **`wchar_t`** символы) будет преобразована в строку ANSI (содержащая **`char`** символы) перед записью во внутренний буфер. Чтобы сохранить строки Юникода в буфере, создайте новый буфер типа **`wchar_t`** и задайте его с помощью [`basic_streambuf::pubsetbuf`](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` метода. Ниже приведен пример, демонстрирующий такие действия.

Объект класса `basic_filebuf<Char_T, Tr>` хранит указатель на файл, который обозначает `FILE` объект, управляющий потоком, связанным с открытым файлом. Он также содержит указатели на два аспекта преобразования файла для использования защищенными функциями-членами [overflow](#overflow) и [underflow](#underflow). Дополнительные сведения см. на веб-сайте [`basic_filebuf::open`](#open).

## <a name="example"></a>Пример

Следующий пример демонстрирует способ использования объекта типа `basic_filebuf<wchar_t>` для хранения символов Юникода в своем внутреннем буфере, с помощью метода `pubsetbuf()`.

```cpp
// unicode_basic_filebuf.cpp
// compile with: /EHsc

#include <iostream>
#include <string>
#include <fstream>
#include <iomanip>
#include <memory.h>
#include <string.h>

#define IBUFSIZE 16

using namespace std;

void hexdump(const string& filename);

int main()
{
    wchar_t* wszHello = L"Hello World";
    wchar_t wBuffer[128];

    basic_filebuf<wchar_t> wOutFile;

    // Open a file, wcHello.txt, then write to it, then dump the
    // file's contents in hex
    wOutFile.open("wcHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wcHello.txt\n";
        return -1;
    }
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";
    hexdump(string("wcHello.txt"));

    // Open a file, wwHello.txt, then set the internal buffer of
    // the basic_filebuf object to be of type wchar_t, then write
    // to the file and dump the file's contents in hex
    wOutFile.open("wwHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wwHello.txt\n";
        return -1;
    }
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";
    hexdump(string("wwHello.txt"));

    return 0;
}

// dump contents of filename to stdout in hex
void hexdump(const string& filename)
{
    fstream ifile(filename.c_str(),
        ios_base::in | ios_base::binary);
    char *ibuff = new char[IBUFSIZE];
    char *obuff = new char[(IBUFSIZE*2)+1];
    int i;

    if(!ifile.is_open())
    {
        cout << "Cannot Open " << filename.c_str()
             << " for reading\n";
        return;
    }
    if(!ibuff || !obuff)
    {
        cout << "Cannot Allocate buffers\n";
        ifile.close();
        return;
    }

    while(!ifile.eof())
    {
        memset(obuff,0,(IBUFSIZE*2)+1);
        memset(ibuff,0,IBUFSIZE);
        ifile.read(ibuff,IBUFSIZE);

        // corner case where file is exactly a multiple of
        // 16 bytes in length
        if(ibuff[0] == 0 && ifile.eof())
            break;

        for(i = 0; i < IBUFSIZE; i++)
        {
            if(ibuff[i] >= ' ')
                obuff[i] = ibuff[i];
            else
                obuff[i] = '.';

            cout << setfill('0') << setw(2) << hex
                 << (int)ibuff[i] << ' ';
        }
        cout << "  " << obuff << endl;
    }
    ifile.close();
}
```

```Output
Hex Dump of wcHello.txt - note that output is ANSI chars:
48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....

Hex Dump of wwHello.txt - note that output is wchar_t chars:
48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o. .W.o.
72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_filebuf](#basic_filebuf)|Создает объект типа `basic_filebuf`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Связывает имя типа с параметром шаблона `Char_T`.|
|[int_type](#int_type)|Делает этот тип в области `basic_filebuf` эквивалентным типу с таким же именем в области `Tr`.|
|[off_type](#off_type)|Делает этот тип в области `basic_filebuf` эквивалентным типу с таким же именем в области `Tr`.|
|[pos_type](#pos_type)|Делает этот тип в области `basic_filebuf` эквивалентным типу с таким же именем в области `Tr`.|
|[traits_type](#traits_type)|Связывает имя типа с параметром шаблона `Tr`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[выхода](#close)|Закрывает файл.|
|[is_open](#is_open)|Указывает, открыт ли файл.|
|[open](#open)|Открывает файл.|
|[полн](#overflow)|Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.|
|[pbackfail](#pbackfail)|Защищенная виртуальная функция-член пытается поместить элемент обратно во входной поток, затем делает его текущим (на него указывает следующий указатель).|
|[seekoff](#seekoff)|Защищенная виртуальная функция-член пытается изменить текущие положения управляемых потоков.|
|[seekpos](#seekpos)|Защищенная виртуальная функция-член пытается изменить текущие положения управляемых потоков.|
|[setbuf](#setbuf)|Защищенная виртуальная функция-член выполняет операции, относящиеся непосредственно к каждому производному буферу потока.|
|[swap](#swap)|Меняет местами содержимое этого `basic_filebuf` и содержимое указанного параметра `basic_filebuf`.|
|[nosync](#sync)|Защищенная виртуальная функция пытается синхронизировать управляемые потоки с любыми связанными внешними потоками.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|Защищенная виртуальная функция для извлечения текущего элемента из входного потока.|
|[потери значимости](#underflow)|Защищенная виртуальная функция для извлечения текущего элемента из входного потока.|

## <a name="requirements"></a>Требования

**Заголовок:**\<fstream>

**Пространство имен:** std

## <a name="basic_filebufbasic_filebuf"></a><a name="basic_filebuf"></a>basic_filebuf:: basic_filebuf

Создает объект типа `basic_filebuf`.

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>Примечания

Первый конструктор сохраняет пустой указатель во всех указателях, управляющих входным и выходным буферами. Он также сохраняет пустой указатель в указателе файла.

Второй конструктор инициализирует объект с содержимым *right*, который рассматривается как ссылка rvalue.

## <a name="basic_filebufchar_type"></a><a name="char_type"></a>basic_filebuf:: char_type

Связывает имя типа с параметром шаблона `Char_T`.

```cpp
typedef Char_T char_type;
```

## <a name="basic_filebufclose"></a><a name="close"></a>basic_filebuf:: Close

Закрывает файл.

```cpp
basic_filebuf<Char_T, Tr> *close();
```

### <a name="return-value"></a>Возвращаемое значение

Функция-член возвращает указатель null, если указатель файла является указателем null.

### <a name="remarks"></a>Примечания

`close` вызывает `fclose(fp)`. Если эта функция возвращает ненулевое значение, то возвращается пустой указатель. В противном случае возвращается **`this`** значение, указывающее, что файл был успешно закрыт.

Для широкого потока, если с момента открытия потока или с момента последнего вызова в функцию возникли какие-либо операции вставки `streampos` [`overflow`](#overflow) . Он также вставляет любую последовательность, необходимую для восстановления исходного состояния преобразования, с помощью аспекта преобразования файлов `fac` для вызова `fac.unshift` по мере необходимости. Каждый созданный элемент `byte` типа **`char`** записывается в связанный поток, обозначенный указателем файла, как если бы они были `fp` успешными вызовами формы `fputc(byte, fp)` . При `fac.unshift` сбое вызова или любой записи функция не будет выполнена.

### <a name="example"></a>Пример

В следующем примере предполагается, что в текущем каталоге два файла: *basic_filebuf_close.txt* (содержимое — "тестирование") и *iotest.txt* (содержимое — "сссс").

```cpp
// basic_filebuf_close.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main() {
   using namespace std;
   ifstream file;
   basic_ifstream <wchar_t> wfile;
   char c;
   // Open and close with a basic_filebuf
   file.rdbuf()->open( "basic_filebuf_close.txt", ios::in );
   file >> c;
   cout << c << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "iotest.txt" );
   file >> c;
   cout << c << endl;
   file.close( );

   // open a file with a wide character name
   wfile.open( L"iotest.txt" );

   // Open and close a nonexistent with a basic_filebuf
   file.rdbuf()->open( "ziotest.txt", ios::in );
   cout << file.fail() << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "ziotest.txt" );
   cout << file.fail() << endl;
   file.close( );
}
```

```Output
t
s
0
1
```

## <a name="basic_filebufint_type"></a><a name="int_type"></a>basic_filebuf:: int_type

Делает этот тип в `basic_filebuf` области эквивалентным типу с тем же именем в `Tr` области.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_filebufis_open"></a><a name="is_open"></a>basic_filebuf:: is_open

Указывает, открыт ли файл.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если указатель файла не равен null.

### <a name="example"></a>Пример

```cpp
// basic_filebuf_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   cout << boolalpha << file.rdbuf( )->is_open( ) << endl;

   file.open( "basic_filebuf_is_open.cpp" );
   cout << file.rdbuf( )->is_open( ) << endl;
}
```

```Output
false
true
```

## <a name="basic_filebufoff_type"></a><a name="off_type"></a>basic_filebuf:: off_type

Делает этот тип в `basic_filebuf` области эквивалентным типу с тем же именем в `Tr` области.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_filebufopen"></a><a name="open"></a>basic_filebuf:: Open

Открывает файл.

```cpp
basic_filebuf<Char_T, Tr> *open(
    const char* filename,
    ios_base::openmode mode,
    int protection = (int)ios_base::_Openprot);

basic_filebuf<Char_T, Tr> *open(
    const char* filename,
    ios_base::openmode mode);

basic_filebuf<Char_T, Tr> *open(
    const wchar_t* filename,
    ios_base::openmode mode,
    int protection = (int)ios_base::_Openprot);

basic_filebuf<Char_T, Tr> *open(
    const wchar_t* filename,
    ios_base::openmode mode);
```

### <a name="parameters"></a>Параметры

*файлов*\
Имя файла, который необходимо открыть.

*режима*\
Одно из перечислений в [`ios_base::openmode`](../standard-library/ios-base-class.md#openmode) .

*уровень*\
Защита открытия файлов по умолчанию, эквивалентная параметру *шфлаг* в [_fsopen _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="return-value"></a>Возвращаемое значение

Если буфер уже открыт или если указатель файла является пустым указателем, функция возвращает пустой указатель. В противном случае возвращается значение **`this`** .

### <a name="remarks"></a>Примечания

Эта функция использует `FILE *` для возврата, `basic_filebuf` как будто вы вызывали [`fopen/wfopen`](../c-runtime-library/reference/fopen-wfopen.md) `(filename, strmode)` . `strmode`определяется из `mode & ~(` [`ate`](../standard-library/ios-base-class.md#openmode) `|` [`binary`](../standard-library/ios-base-class.md#openmode) `)` :

- `ios_base::in`преобразуется `"r"` (открывает существующий файл для чтения).
- [ios_base:: out](../standard-library/ios-base-class.md#fmtflags) или `ios_base::out | ios_base::trunc` преобразуется `"w"` (усечение существующего файла или создание для записи).
- `ios_base::out | app`принимает `"a"` (открывает существующий файл для добавления всех операций записи).
- `ios_base::in | ios_base::out`преобразуется `"r+"` (открывает существующий файл для чтения и записи).
- `ios_base::in | ios_base::out | ios_base::trunc`преобразуется `"w+"` (усекает существующий файл или создает для чтения и записи).
- `ios_base::in | ios_base::out | ios_base::app`принимает `"a+"` (открывает существующий файл для чтения и для добавления всех операций записи).

Если `mode & ios_base::binary` имеет ненулевое значение, функция добавляет `b` к, `strmode` чтобы открыть двоичный поток вместо текстового потока.
Если `mode & ios_base::ate` имеет ненулевое значение и файл был успешно открыт, текущее расположение в потоке размещается в конце файла. Если это не удается, файл закрывается.

Если приведенные выше операции завершились успешно, аспект преобразования файла определяется следующим образом: `use_facet<codecvt<Char_T, char, traits_type::` [`state_type`](../standard-library/char-traits-struct.md#state_type) `> >(` [`getloc`](../standard-library/basic-streambuf-class.md#getloc) `)` , для использования в целях [неточного](#underflow) и [переполнения](#overflow).

Если файл не может быть успешно открыт, возвращается значение null.

### <a name="example"></a>Пример

См [`basic_filebuf::close`](#close) . пример, в котором используется `open` .

## <a name="basic_filebufoperator"></a><a name="op_eq"></a>basic_filebuf::operator=

Назначьте содержимое этого объекта буфера потока. Это назначение перемещения, включающее rvalue, который не оставляет копию позади.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>Параметры

*right*\
Ссылка rvalue на объект [basic_filebuf](../standard-library/basic-filebuf-class.md).

### <a name="return-value"></a>Возвращаемое значение

Возвращает __* this__.

### <a name="remarks"></a>Примечания

Оператор Member заменяет содержимое объекта с помощью содержимого *right*, которое рассматривается как ссылка rvalue. Дополнительные сведения см. в разделе [декларатор ссылок rvalue:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="basic_filebufoverflow"></a><a name="overflow"></a>basic_filebuf:: overflow

Вызывается при вставке нового символа в полный буфер.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Параметры

*_Meta*\
Символ, вставляемый в буфер или `traits_type::eof` .

### <a name="return-value"></a>Возвращаемое значение

Если функция не может быть выполнена, возвращается значение `traits_type::eof` . В противном случае возвращается значение `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)` .

### <a name="remarks"></a>Примечания

Если `_Meta != traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) значение равно, Защищенная виртуальная функция – член пытается вставить элемент `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)` в выходной буфер. Это можно сделать разными способами.

- Если позиция записи доступна, можно сохранить элемент в позиции записи и увеличить следующий указатель для выходного буфера.

- Можно сделать позицию записи доступной, выделяя новое или дополнительное хранилище для выходного буфера.

- Он может преобразовать все ожидающие выходные данные в выходной буфер, за которым следует `ch` , с помощью аспекта преобразования файлов `fac` для вызова `fac.out` по мере необходимости. Каждый созданный элемент `ch` типа *char* записывается в связанный поток, обозначенный указателем файла, как если бы они были `fp` успешными вызовами формы `fputc(ch, fp)` . В случае сбоя любого преобразования или записи эта функция завершается неудачно.

## <a name="basic_filebufpbackfail"></a><a name="pbackfail"></a>basic_filebuf: неудачная:p

Пытается поместить элемент обратно во входной поток, затем делает его текущим (на него указывает следующий указатель).

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Параметры

*_Meta*\
Символ для вставки в буфер или `traits_type::eof`.

### <a name="return-value"></a>Возвращаемое значение

Если функция не может быть выполнена, возвращается значение `traits_type::eof` . В противном случае возвращается значение `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)` .

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член помещает элемент обратно во входной буфер, а затем делает его текущим (на него указывает следующий указатель). Если `_Meta == traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) значение равно, то элемент, который необходимо вернуть обратно, фактически является уже в потоке до текущего элемента. В противном случае этот элемент заменяется на `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)` . Функция может передать элемент обратно различными способами.

- Если `putback` расположение доступно, а элемент, в котором хранится, сравнивается со значением `ch` , он может уменьшить следующий указатель для входного буфера.

- Если функция может сделать `putback` позицию доступной, она может сделать это, установить следующий указатель, указывающий на эту позицию, и сохранить `ch` его в этой позиции.

- Если функция может вернуть элемент во входной поток, это может сделать это, например, путем вызова `ungetc` для элемента типа **`char`** .

## <a name="basic_filebufpos_type"></a><a name="pos_type"></a>basic_filebuf::p os_type

Делает этот тип в `basic_filebuf` области эквивалентным типу с тем же именем в `Tr` области.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_filebufseekoff"></a><a name="seekoff"></a>basic_filebuf:: seekoff

Пытается изменить текущие положения для управляемых потоков.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*_Off*\
Искомое положение относительно *_Way*.

*_Way*\
Начальная точка для операций смещения. Возможные значения см. в разделе [seekdir](../standard-library/ios-base-class.md#seekdir).

*_Which*\
Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Возвращает новую позицию или недопустимую позицию потока.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция – член пытается изменить текущие позиции для управляемых потоков. Для объекта класса [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>` позиция потока может быть представлена объектом типа `fpos_t` , который хранит смещение и все сведения о состоянии, необходимые для синтаксического анализа большого потока. Нулевое смещение относится к первому элементу потока. (Объект типа [`pos_type`](../standard-library/basic-streambuf-class.md#pos_type) хранит по крайней мере `fpos_t` объект.)

Для файла, открытого для чтения и записи, входной и выходной потоки располагаются вместе. Для переключения между вставкой и извлечением необходимо вызвать либо [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos) . Вызовы `pubseekoff` (и, следовательно, `seekoff` ) имеют различные ограничения для [текстовых потоков](../c-runtime-library/text-and-binary-streams.md), [двоичных потоков](../c-runtime-library/text-and-binary-streams.md)и [широких потоков](../c-runtime-library/byte-and-wide-streams.md).

Если указатель файла `fp` является пустым указателем, функция завершается ошибкой. В противном случае он пытается изменить расположение потока путем вызова `fseek(fp, _Off, _Way)` . Если эта функция завершилась с ошибкой и результирующая положение `fposn` может быть определено вызовом `fgetpos(fp, &fposn)` функции, функция будет выполнена. Если функция завершается с ошибкой, она возвращает значение типа, `pos_type` содержащее `fposn` . В противном случае она возвращает недопустимую позицию потока.

## <a name="basic_filebufseekpos"></a><a name="seekpos"></a>basic_filebuf:: seekpos

Пытается изменить текущие положения для управляемых потоков.

```cpp
virtual pos_type seekpos(
    pos_type _Sp,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*_Sp*\
Позиция для поиска.

*_Which*\
Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Если указатель файла `fp` является пустым указателем, функция завершается ошибкой. В противном случае он пытается изменить позицию потока путем вызова метода `fsetpos(fp, &fposn)` , где `fposn` — это `fpos_t` объект, хранящийся в `pos` . Если эта функция выполняется успешно, функция возвращает `pos`. В противном случае она возвращает недопустимую позицию потока. Чтобы определить, является ли позиция в потоке недопустимой, сравните возвращаемое значение с `pos_type(off_type(-1))`.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция – член пытается изменить текущие позиции для управляемых потоков. Для объекта класса [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>` позиция потока может быть представлена объектом типа `fpos_t` , который хранит смещение и все сведения о состоянии, необходимые для синтаксического анализа большого потока. Нулевое смещение относится к первому элементу потока. (Объект типа `pos_type` хранит по крайней мере объект `fpos_t`.)

Для файла, открытого для чтения и записи, входной и выходной потоки располагаются вместе. Для переключения между вставкой и извлечением необходимо вызвать либо [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos) . Вызовы `pubseekoff` (и в `seekoff` ) имеют различные ограничения для текстовых потоков, двоичных потоков и широких потоков.

Что касается широкого потока, если после открытия такого потока или с момента последнего вызова `streampos` были произведены какие-либо вставки, то эта функция вызывает [переполнение](#overflow). Он также вставляет любую последовательность, необходимую для восстановления исходного состояния преобразования, с помощью аспекта преобразования файлов `fac` для вызова `fac.unshift` по мере необходимости. Каждый созданный элемент `byte` типа **`char`** записывается в связанный поток, обозначенный указателем файла, как если бы они были `fp` успешными вызовами формы `fputc(byte, fp)` . При `fac.unshift` сбое вызова или любой записи функция не будет выполнена.

## <a name="basic_filebufsetbuf"></a><a name="setbuf"></a>basic_filebuf:: setbuf

Выполняет операции, относящиеся непосредственно к каждому производному буферу потока.

```cpp
virtual basic_streambuf<Char_T, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Параметры

*_Buffer*\
Указатель на буфер.

*count*\
Размер буфера.

### <a name="return-value"></a>Возвращаемое значение

Эта защищенная функция-член возвращает нуль, если указатель файла `fp` является пустым указателем.

### <a name="remarks"></a>Примечания

`setbuf`вызывает метод `setvbuf( fp, (char*) _Buffer, _IOFBF, count * sizeof( Char_T))` для предложения массива `count` элементов, начиная с *_Buffer* в виде буфера для потока. Если эта функция возвращает ненулевое значение, то возвращается пустой указатель. В противном случае возвращается **`this`** значение для успешного сигнала.

## <a name="basic_filebufswap"></a><a name="swap"></a>basic_filebuf:: swap

Меняет местами содержимое этого объекта `basic_filebuf` с содержимым указанного объекта `basic_filebuf`.

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>Параметры

*right*\
Ссылка lvalue на другую `basic_filebuf` .

## <a name="basic_filebufsync"></a><a name="sync"></a>basic_filebuf:: Sync

Пытается синхронизировать управляемые потоки с любыми связанными внешними потоками.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает нуль, если указатель файла `fp` является пустым указателем. В противном случае он возвращает нуль только в том случае, если вызовы обоих типов вызывают [переполнение](#overflow) и `fflush(fp)` выполняются при сбросе всех ожидающих выходных данных в поток.

## <a name="basic_filebuftraits_type"></a><a name="traits_type"></a>basic_filebuf:: traits_type

Связывает имя типа с параметром шаблона `Tr`.

```cpp
typedef Tr traits_type;
```

## <a name="basic_filebufunderflow"></a><a name="underflow"></a>basic_filebuf:: потеря значимости

Извлекает текущий элемент из входного потока.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Возвращаемое значение

Если функция не может быть выполнена, возвращается значение `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) . В противном случае возвращается `ch` , преобразуется, как описано в разделе "Примечания".

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция члена пытается извлечь текущий элемент `ch` из входного потока и вернуть элемент в качестве `traits_type::` [`to_int_type`](../standard-library/char-traits-struct.md#to_int_type) `(ch)` . Это можно сделать разными способами.

- Если доступная для чтения позиции доступна, она принимает в `ch` качестве элемента, хранящегося в позиции чтения, и перемещает следующий указатель для входного буфера.

- Он может считывать один или несколько элементов типа **`char`** , как при последовательных вызовах формы `fgetc(fp)` , так и преобразовывать их в элемент `ch` типа `Char_T` , используя аспект преобразования файла `fac` для вызова `fac.in` по мере необходимости. В случае сбоя какого-либо преобразования или операции чтения эта функция завершается неудачно.

## <a name="see-also"></a>См. также раздел

[\<fstream>](../standard-library/fstream.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
