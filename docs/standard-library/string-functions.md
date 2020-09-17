---
title: Функции &lt;string&gt;
ms.date: 11/04/2016
f1_keywords:
- string/std::getline
- string/std::stod
- string/std::stof
- string/std::stoi
- string/std::stol
- string/std::stold
- string/std::stoll
- string/std::stoul
- string/std::stoull
- string/std::swap
- string/std::to_string
- string/std::to_wstring
ms.assetid: 1a4ffd11-dce5-4cc6-a043-b95de034c7c4
helpviewer_keywords:
- std::getline [C++]
- std::stod [C++]
- std::stof [C++]
- std::stoi [C++]
- std::stol [C++]
- std::stold [C++]
- std::stoll [C++]
- std::stoul [C++]
- std::stoull [C++]
- std::swap [C++]
- std::to_string [C++]
- std::to_wstring [C++]
ms.openlocfilehash: 350a66481c7061322f08a768ec1628598f4af68e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843187"
---
# <a name="ltstringgt-functions"></a>Функции &lt;string&gt;

[getline](#getline)\
[стод](#stod)\
[стоф](#stof)\
[стои](#stoi)\
[стол](#stol)\
[столд](#stold)\
[столл](#stoll)\
[стаул](#stoul)\
[стаулл](#stoull)\
[swap](#swap)\
[to_string](#to_string)\
[to_wstring](#to_wstring)

## <a name="getline"></a><a name="getline"></a> getline

Извлекает строки из входного потока, последовательно по одной строке.

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delimiter);

template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delimiter);

// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str);

template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& in_stream,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>Параметры

*in_stream*\
Входной поток, из которого извлекается строка.

*str*\
Строка, в которую считываются символы из входного потока.

*разделитель*\
Разделитель строк.

### <a name="return-value"></a>Возвращаемое значение

*In_stream*входного потока.

### <a name="remarks"></a>Примечания

Пара сигнатур функций, помеченных как `(1)` извлеченные символы из *in_stream* до тех пор, пока не будет найден *Разделитель* , сохраняя их в *str*.

Пара сигнатур функций, помеченных как, используют новую строку в `(2)` качестве разделителя по умолчанию и ведут себя как `getline(in_stream, str, in_stream. widen('\n'))` .

Вторая функция каждой пары аналогична первой и поддерживает [ссылки rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md).

Извлечение останавливается при возникновении одного из следующих условий.

- В конце файла, в этом случае флаг внутреннего состояния *in_stream* имеет значение `ios_base::eofbit` .

- После извлечения из функции элемента, который сравнивается с *разделителем*. Элемент не перемещается назад или добавляется в управляемую последовательность.

- После извлечения функцией `str.` [max_size](../standard-library/basic-string-class.md#max_size) элементов. Флаг внутреннего состояния *in_stream* имеет значение `ios_base::failbit` .

- Другие ошибки, отличные от перечисленных выше. Флаг внутреннего состояния *in_stream* имеет значение `ios_base::badbit` .

Сведения о внутренних флагах состояния см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

Если функция не извлекает ни одного элемента, флаг внутреннего состояния *in_stream* имеет значение `ios_base::failbit` . В любом случае `getline` возвращает *in_stream*.

При возникновении исключения *in_stream* и *str* остаются в допустимом состоянии.

### <a name="example"></a>Пример

Следующий код демонстрирует `getline()` в двух режимах: в первом с разделителем — символом новой строки (по умолчанию), во втором с разделителем — пробелом. Символ конца файла (CTRL-Z на клавиатуре) используется для управления завершением циклов while. Это значение задает для флага внутреннего состояния `cin` значение `eofbit` , которое необходимо очистить с помощью [basic_ios:: Clear ()](../standard-library/basic-ios-class.md#clear) , прежде чем второй цикл while будет работать правильно.

```cpp
// compile with: /EHsc /W4
#include <string>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    string str;
    vector<string> v1;
    cout << "Enter a sentence, press ENTER between sentences. (Ctrl-Z to stop): " << endl;
    // Loop until end-of-file (Ctrl-Z) is input, store each sentence in a vector.
    // Default delimiter is the newline character.
    while (getline(cin, str)) {
        v1.push_back(str);
    }

    cout << "The following input was stored with newline delimiter:" << endl;
    for (const auto& p : v1) {
        cout << p << endl;
    }

    cin.clear();

    vector<string> v2;
    // Now try it with a whitespace delimiter
    while (getline(cin, str, ' ')) {
        v2.push_back(str);
    }

    cout << "The following input was stored with whitespace as delimiter:" << endl;
    for (const auto& p : v2) {
        cout << p << endl;
    }
}
```

## <a name="stod"></a><a name="stod"></a> стод

Преобразует последовательность символов в **`double`** .

```cpp
double stod(
    const string& str,
    size_t* idx = 0);

double stod(
    const wstring& str,
    size_t* idx = 0
;
```

### <a name="parameters"></a>Параметры

*str*\
Последовательность символов для преобразования.

*IDX*\
Значение индекса первого непреобразованного символа.

### <a name="return-value"></a>Возвращаемое значение

**`double`** Значение.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* в значение типа, **`double`** как при вызове метода `strtod( str.c_str(), _Eptr)` , где `_Eptr` является объектом, внутренним по отношению к функции. Если `str.c_str() == *_Eptr` значение равно, то создается объект типа `invalid_argument` . Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает значение.

## <a name="stof"></a><a name="stof"></a> стоф

Преобразует последовательность символов в число с плавающей запятой.

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Параметры

*str*\
Последовательность символов для преобразования.

*IDX*\
Значение индекса первого непреобразованного символа.

### <a name="return-value"></a>Возвращаемое значение

**`float`** Значение.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* в значение типа, **`float`** как при вызове метода `strtof( str.c_str(), _Eptr)` , где `_Eptr` является объектом, внутренним по отношению к функции. Если `str.c_str() == *_Eptr` значение равно, то создается объект типа `invalid_argument` . Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает значение.

## <a name="stoi"></a><a name="stoi"></a> стои

Преобразует последовательность символов в целое число.

```cpp
int stoi(
    const string& str,
    size_t* idx = 0,
    int base = 10);

int stoi(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="return-value"></a>Возвращаемое значение

Целочисленное значение.

### <a name="parameters"></a>Параметры

*str*\
Последовательность символов для преобразования.

*IDX*\
Значение индекса первого непреобразованного символа.

*из*\
Используемое числовое основание.

### <a name="remarks"></a>Примечания

Функция `stoi` преобразует последовательность символов в *str* в значение типа **`int`** и возвращает значение. Например, если передать последовательность символов "10", `stoi` возвращает целочисленное значение 10.

`stoi` ведет себя аналогично функции `strtol` для однобайтовых символов, когда она вызывается способом `strtol( str.c_str(), _Eptr, idx)` , где `_Eptr` является объектом, внутренним по отношению к функции, или `wcstol` для расширенных символов, когда он вызывается подобным образом `wcstol(Str.c_str(), _Eptr, idx)` . Дополнительные сведения см. в разделе [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

Если `str.c_str() == *_Eptr` значение равно, `stoi` вызывается объект типа `invalid_argument` . Если такой вызов будет установлен `errno` или если возвращаемое значение не может быть представлено как объект типа **`int`** , то создается объект типа `out_of_range` . В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr - str.c_str()` в `*idx` .

## <a name="stol"></a><a name="stol"></a> стол

Преобразует последовательность символов в **`long`** .

```cpp
long stol(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long stol(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Параметры

*str*\
Последовательность символов для преобразования.

*IDX*\
Значение индекса первого непреобразованного символа.

*из*\
Используемое числовое основание.

### <a name="return-value"></a>Возвращаемое значение

Длинное целое значение.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* в значение типа, **`long`** как при вызове метода `strtol( str.c_str(), _Eptr, idx)` , где `_Eptr` является объектом, внутренним по отношению к функции. Если `str.c_str() == *_Eptr` значение равно, то создается объект типа `invalid_argument` . Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает значение.

## <a name="stold"></a><a name="stold"></a> столд

Преобразует последовательность символов в **`long double`** .

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Параметры

*str*\
Последовательность символов для преобразования.

*IDX*\
Значение индекса первого непреобразованного символа.

### <a name="return-value"></a>Возвращаемое значение

**`long double`** Значение.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* в значение типа, **`long double`** как при вызове метода `strtold( str.c_str(), _Eptr)` , где `_Eptr` является объектом, внутренним по отношению к функции. Если `str.c_str() == *_Eptr` значение равно, то создается объект типа `invalid_argument` . Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает значение.

## <a name="stoll"></a><a name="stoll"></a> столл

Преобразует последовательность символов в **`long long`** .

```cpp
long long stoll(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long long stoll(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Параметры

*str*\
Последовательность символов для преобразования.

*IDX*\
Значение индекса первого непреобразованного символа.

*из*\
Используемое числовое основание.

### <a name="return-value"></a>Возвращаемое значение

**`long long`** Значение.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* в значение типа, **`long long`** как при вызове метода `strtoll( str.c_str(), _Eptr, idx)` , где `_Eptr` является объектом, внутренним по отношению к функции. Если `str.c_str() == *_Eptr` значение равно, то создается объект типа `invalid_argument` . Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает значение.

## <a name="stoul"></a><a name="stoul"></a> стаул

Преобразует последовательность символов в длинное целое без знака.

```cpp
unsigned long stoul(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long stoul(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Параметры

*str*\
Последовательность символов для преобразования.

*IDX*\
Значение индекса первого непреобразованного символа.

*из*\
Используемое числовое основание.

### <a name="return-value"></a>Возвращаемое значение

Длинное целое значение без знака.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* в значение типа, **`unsigned long`** как при вызове метода `strtoul( str.c_str(), _Eptr, idx)` , где `_Eptr` является объектом, внутренним по отношению к функции. Если `str.c_str() == *_Eptr` значение равно, то создается объект типа `invalid_argument` . Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает значение.

## <a name="stoull"></a><a name="stoull"></a> стаулл

Преобразует последовательность символов в **`unsigned long long`** .

```cpp
unsigned long long stoull(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long long stoull(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Параметры

*str*\
Последовательность символов для преобразования.

*IDX*\
Значение индекса первого непреобразованного символа.

*из*\
Используемое числовое основание.

### <a name="return-value"></a>Возвращаемое значение

**`unsigned long long`** Значение.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* в значение типа, **`unsigned long long`** как при вызове метода `strtoull( str.c_str(), _Eptr, idx)` , где `_Eptr` является объектом, внутренним по отношению к функции. Если `str.c_str() == *_Eptr` значение равно, то создается объект типа `invalid_argument` . Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает значение.

## <a name="swap"></a><a name="swap"></a> swap

Меняет местами массивы символов двух строк.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Одна строка, элементы которой должны быть заменены элементами другой строки.

*right*\
Другая строка, элементы которой будут заменены на элементы первой строки.

### <a name="remarks"></a>Примечания

Функция шаблона выполняет специализированную функцию члена *Left*. [Переключение](../standard-library/basic-string-class.md#swap)(*right*) для строк, что гарантирует постоянную сложность.

### <a name="example"></a>Пример

```cpp
// string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   swap ( s1 , s2 );
   cout << "\nAfter swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.

After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="to_string"></a><a name="to_string"></a> to_string

Преобразует значение в `string`.

```cpp
string to_string(int value);
string to_string(unsigned int value);
string to_string(long value);
string to_string(unsigned long value);
string to_string(long long value);
string to_string(unsigned long long value);
string to_string(float value);
string to_string(double value);
string to_string(long double value);
```

### <a name="parameters"></a>Параметры

*value*\
Преобразуемое значение.

### <a name="return-value"></a>Возвращаемое значение

Объект `string`, представляющий значение.

### <a name="remarks"></a>Примечания

Функция преобразует *значение* в последовательность элементов, хранящихся в объекте массива, `Buf` который является внутренним по отношению к функции, как при вызове метода `sprintf(Buf, Fmt, value)` , где `Fmt`

- `"%d"` Если *значение* имеет тип **`int`**

- `"%u"` Если *значение* имеет тип **`unsigned int`**

- `"%ld"` Если *значение* имеет тип **`long`**

- `"%lu"` Если *значение* имеет тип **`unsigned long`**

- `"%lld"` Если *значение* имеет тип **`long long`**

- `"%llu"` Если *значение* имеет тип **`unsigned long long`**

- `"%f"` Если *значение* имеет тип **`float`** или **`double`**

- `"%Lf"` Если *значение* имеет тип **`long double`**

Функция возвращает `string(Buf)`.

## <a name="to_wstring"></a><a name="to_wstring"></a> to_wstring

Преобразует значение в расширенную строку.

```cpp
wstring to_wstring(int value);
wstring to_wstring(unsigned int value);
wstring to_wstring(long value);
wstring to_wstring(unsigned long value);
wstring to_wstring(long long value);
wstring to_wstring(unsigned long long value);
wstring to_wstring(float value);
wstring to_wstring(double value);
wstring to_wstring(long double value);
```

### <a name="parameters"></a>Параметры

*value*\
Преобразуемое значение.

### <a name="return-value"></a>Возвращаемое значение

Расширенная строка, представляющая значение.

### <a name="remarks"></a>Примечания

Функция преобразует *значение* в последовательность элементов, хранящихся в объекте массива, `Buf` который является внутренним по отношению к функции, как при вызове метода `swprintf(Buf, Len, Fmt, value)` , где `Fmt`

- `L"%d"` Если *значение* имеет тип **`int`**

- `L"%u"` Если *значение* имеет тип **`unsigned int`**

- `L"%ld"` Если *значение* имеет тип **`long`**

- `L"%lu"` Если *значение* имеет тип **`unsigned long`**

- `L"%lld"` Если *значение* имеет тип **`long long`**

- `L"%llu"` Если *значение* имеет тип **`unsigned long long`**

- `L"%f"` Если *значение* имеет тип **`float`** или **`double`**

- `L"%Lf"` Если *значение* имеет тип **`long double`**

Функция возвращает `wstring(Buf)`.

## <a name="see-also"></a>См. также раздел

[\<string>](../standard-library/string.md)
