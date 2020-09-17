---
title: Класс strstreambuf
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstreambuf::freeze
- strstream/std::strstreambuf::overflow
- strstream/std::strstreambuf::pbackfail
- strstream/std::strstreambuf::pcount
- strstream/std::strstreambuf::seekoff
- strstream/std::strstreambuf::seekpos
- strstream/std::strstreambuf::str
- strstream/std::strstreambuf::underflow
helpviewer_keywords:
- std::strstreambuf [C++], freeze
- std::strstreambuf [C++], overflow
- std::strstreambuf [C++], pbackfail
- std::strstreambuf [C++], pcount
- std::strstreambuf [C++], seekoff
- std::strstreambuf [C++], seekpos
- std::strstreambuf [C++], str
- std::strstreambuf [C++], underflow
ms.assetid: b040b8ea-0669-4eba-8908-6a9cc159c54b
ms.openlocfilehash: e6b4df60f4d28839419d02fd3ed6d7cbf73d327f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87202198"
---
# <a name="strstreambuf-class"></a>Класс strstreambuf

Описывает буфер потока, который управляет передачей элементов в последовательность элементов, хранящихся в объекте массива, и из нее **`char`** .

## <a name="syntax"></a>Синтаксис

```cpp
class strstreambuf : public streambuf
```

## <a name="remarks"></a>Примечания

В зависимости от способа создания объекта он выделяется, расширяется и освобождается при необходимости для обеспечения соответствия изменениям в последовательности.

Объект класса `strstreambuf` хранит несколько битов сведений о режиме в качестве своего режима `strstreambuf`. Эти биты определяют следующие сведения об управляемой последовательности:

- она выделена, и ее со временем нужно освободить;

- ее можно изменять;

- она расширяется за счет перераспределения хранилища;

- она заморожена, поэтому ее необходимо разморозить до уничтожения или освобождения (если он выделен) объекта элементом, отличным от объекта.

Замороженную управляемую последовательность невозможно изменить или расширить независимо от состояния этих отдельных битов режима.

Объект также хранит указатели на две функции, которые управляют выделением `strstreambuf`. Если это пустые указатели, объект использует собственный метод выделения и освобождения памяти для управляемой последовательности.

> [!NOTE]
> Этот класс устарел. Вместо этого следует использовать [stringbuf](../standard-library/sstream-typedefs.md#stringbuf) или [wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[strstreambuf](#strstreambuf)|Создает объект типа `strstreambuf`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[фиксировать](#freeze)|Делает буфер потока недоступным для операций с буфером потока.|
|[полн](#overflow)|Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.|
|[pbackfail](#pbackfail)|Защищенная виртуальная функция-член, которая пытается поместить элемент обратно во входной поток, а затем делает его текущим (на него указывает следующий указатель).|
|[pcount](#pcount)|Возвращает число элементов, записанных в управляемую последовательность.|
|[seekoff](#seekoff)|Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.|
|[seekpos](#seekpos)|Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.|
|[str](#str)|Вызывает [freeze](#freeze), затем возвращает указатель на начало управляемой последовательности.|
|[потери значимости](#underflow)|Защищенная виртуальная функция для извлечения текущего элемента из входного потока.|

## <a name="requirements"></a>Требования

**Заголовок:**\<strstream>

**Пространство имен:** std

## <a name="strstreambuffreeze"></a><a name="freeze"></a>strstreambuf:: Freeze

Делает буфер потока недоступным для операций с буфером потока.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Параметры

*_Freezeit*\
Значение типа **`bool`** , указывающее, нужно ли заморозить поток.

### <a name="remarks"></a>Примечания

Если *_Freezeit* имеет значение true, функция изменяет сохраненный `strstreambuf` режим, чтобы заморозить управляемую последовательность. В противном случае управляемая последовательность зафиксирована не будет.

[str](#str) подразумевает `freeze`.

> [!NOTE]
> Замороженные буферы не будут освобождены во время уничтожения `strstreambuf`. Необходимо отменить фиксацию буфера до освобождения, чтобы избежать утечки памяти.

### <a name="example"></a>Пример

```cpp
// strstreambuf_freeze.cpp
// compile with: /EHsc

#include <iostream>
#include <strstream>

using namespace std;

void report(strstream &x)
{
    if (!x.good())
        cout << "stream bad" << endl;
    else
        cout << "stream good" << endl;
}

int main()
{
    strstream x;

    x << "test1";
    cout << "before freeze: ";
    report(x);

    // Calling str freezes stream.
    cout.write(x.rdbuf()->str(), 5) << endl;
    cout << "after freeze: ";
    report(x);

    // Stream is bad now, wrote on frozen stream
    x << "test1.5";
    cout << "after write to frozen stream: ";
    report(x);

    // Unfreeze stream, but it is still bad
    x.rdbuf()->freeze(false);
    cout << "after unfreezing stream: ";
    report(x);

    // Clear stream
    x.clear();
    cout << "after clearing stream: ";
    report(x);

    x << "test3";
    cout.write(x.rdbuf()->str(), 10) << endl;

    // Clean up.  Failure to unfreeze stream will cause a
    // memory leak.
    x.rdbuf()->freeze(false);
}
```

```Output
before freeze: stream good
test1
after freeze: stream good
after write to frozen stream: stream bad
after unfreezing stream: stream bad
after clearing stream: stream good
test1test3
```

## <a name="strstreambufoverflow"></a><a name="overflow"></a>strstreambuf:: overflow

Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.

```cpp
virtual int overflow(int _Meta = EOF);
```

### <a name="parameters"></a>Параметры

*_Meta*\
Символ для вставки в буфер или `EOF`.

### <a name="return-value"></a>Возвращаемое значение

Если функции не удалось выполниться успешно, возвращается значение `EOF`. В противном случае, если * \_ meta*  ==  `EOF` возвращает другое значение, отличное от `EOF` . В противном случае он возвращает * \_ meta*.

### <a name="remarks"></a>Примечания

Если * \_ meta* ! = `EOF` , Защищенная виртуальная функция с членом пытается вставить элемент `(char)_Meta` в выходной буфер. Это можно сделать разными способами.

- Если позиция записи доступна, можно сохранить элемент в позиции записи и увеличить следующий указатель для выходного буфера.

- Если сохраненный режим strstreambuf указывает, что управляемая последовательность доступна для изменения и расширения и не зафиксирована, функция может сделать позицию записи доступной, выделив новую позицию для выходного буфера. Расширение выходного буфера таким способом также расширяет любой связанный входной буфер.

## <a name="strstreambufpbackfail"></a><a name="pbackfail"></a>strstreambuf: сбой:p

Защищенная виртуальная функция-член, которая пытается поместить элемент обратно во входной поток, а затем делает его текущим (на него указывает следующий указатель).

```cpp
virtual int pbackfail(int _Meta = EOF);
```

### <a name="parameters"></a>Параметры

*_Meta*\
Символ для вставки в буфер или `EOF`.

### <a name="return-value"></a>Возвращаемое значение

Если функции не удалось выполниться успешно, возвращается значение `EOF`. В противном случае, если * \_ meta*  ==  `EOF` возвращает другое значение, отличное от `EOF` . В противном случае он возвращает * \_ meta*.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член пытается поместить элемент обратно во входной буфер, а затем делает его текущим (на него указывает следующий указатель).

Если объект * \_ meta*  ==  `EOF` , элемент для обратной передачи фактически является уже находящегося в потоке до текущего элемента. В противном случае этот элемент заменяется на `ch = (char)_Meta` . Функция может передать элемент обратно различными способами.

- Если доступна позиция возврата, а элемент, хранящийся в ней, сравнивается со значением `ch` , он может уменьшить следующий указатель для входного буфера.

- Если позиция возврата позиции доступно, и в режиме strstreambuf указано, что управляемая последовательность является изменяемой, функция может сохранить `ch` в позиции позиция возврата и уменьшить следующий указатель для входного буфера.

## <a name="strstreambufpcount"></a><a name="pcount"></a>strstreambuf: число:p

Возвращает число элементов, записанных в управляемую последовательность.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов, записанных в управляемую последовательность.

### <a name="remarks"></a>Примечания

В частности, если [pptr](../standard-library/basic-streambuf-class.md#pptr) является пустым указателем, функция возвращает нуль. В противном случае возвращается `pptr`  -  [PBase](../standard-library/basic-streambuf-class.md#pbase).

### <a name="example"></a>Пример

```cpp
// strstreambuf_pcount.cpp
// compile with: /EHsc
#include <iostream>
#include <strstream>
using namespace std;

int main( )
{
   strstream x;
   x << "test1";
   cout << x.rdbuf( )->pcount( ) << endl;
   x << "test2";
   cout << x.rdbuf( )->pcount( ) << endl;
}
```

## <a name="strstreambufseekoff"></a><a name="seekoff"></a>strstreambuf:: seekoff

Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.

```cpp
virtual streampos seekoff(streamoff _Off,
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

Если функция успешно изменила одну или обе позиции потока, то она возвращает итоговую позицию потока. В противном случае она завершается неудачно и возвращает недопустимую позицию потока.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член пытается изменить текущие положения для управляемых потоков. Для объекта класса strstreambuf позиция потока состоит исключительно из смещения потока. Нулевое смещение обозначает первый элемент управляемой последовательности.

Новая позиция определяется следующим образом.

- Если `_Way == ios_base::beg` значение равно, то Новая единица является началом потока плюс *_Off*.

- Если `_Way == ios_base::cur` , Новая единица является текущей позицией в потоке плюс *_Off*.

- Если `_Way == ios_base::end` значение равно, то новая точка является концом потока плюс *_Off*.

Если `_Which & ios_base::in` имеет ненулевое значение и существует входной буфер, функция изменяет следующую для считывания во входном буфере. Если `_Which & ios_base::out` не равно нулю, `_Way != ios_base::cur` и существует выходной буфер, функция также задает следующую запись для записи в соответствии со следующей позицией для чтения.

В противном случае, если `_Which & ios_base::out` имеет ненулевое значение и выходной буфер существует, функция меняет следующую позицию для записи в выходном буфере. В противном случае операция размещения завершается сбоем. Для успешного выполнения операции размещения итоговая позиция потока должна находиться в управляемой последовательности.

## <a name="strstreambufseekpos"></a><a name="seekpos"></a>strstreambuf:: seekpos

Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.

```cpp
virtual streampos seekpos(streampos _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*_Sp*\
Позиция для поиска.

*_Which*\
Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно изменила одну или обе позиции потока, то она возвращает итоговую позицию потока. В противном случае она завершается неудачно и возвращает недопустимую позицию потока. Чтобы определить, является ли позиция в потоке недопустимой, сравните возвращаемое значение с `pos_type(off_type(-1))`.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член пытается изменить текущие положения для управляемых потоков. Для объекта класса strstreambuf позиция потока состоит исключительно из смещения потока. Нулевое смещение обозначает первый элемент управляемой последовательности. Новая позицией определяется *_Sp*.

Если `_Which` & **ios_base::in** имеет ненулевое значение и существует входной буфер, функция изменяет следующую позицию для чтения во входном буфере. Если `_Which` & `ios_base::out` имеет ненулевое значение и существует выходной буфер, функция также задает следующую позицию для записи, соответствующую следующей позиции для чтения. В противном случае, если `_Which` & `ios_base::out` имеет ненулевое значение и выходной буфер существует, функция меняет следующую позицию для записи в выходном буфере. В противном случае операция размещения завершается сбоем. Для успешного выполнения операции размещения итоговая позиция потока должна находиться в управляемой последовательности.

## <a name="strstreambufstr"></a><a name="str"></a>strstreambuf:: str

Вызывает [freeze](#freeze), затем возвращает указатель на начало управляемой последовательности.

```cpp
char *str();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало управляемой последовательности.

### <a name="remarks"></a>Примечания

Завершающий элемент null не существует, если явно его не вставить.

### <a name="example"></a>Пример

Пример использования **str** см. в разделе [strstreambuf::freeze](#freeze).

## <a name="strstreambufstrstreambuf"></a><a name="strstreambuf"></a>strstreambuf:: strstreambuf

Создает объект типа `strstreambuf`.

```cpp
explicit strstreambuf(streamsize count = 0);

strstreambuf(void (* alloc_func)(size_t),
    void (* free_func)(void*));

strstreambuf(char* getptr,
    streamsize count,
    char* putptr = 0);

strstreambuf(signed char* getptr,
    streamsize count,
    signed char* putptr = 0);

strstreambuf(unsigned char* getptr,
    streamsize count,
    unsigned char* putptr = 0);

strstreambuf(const char* getptr,
    streamsize count);

strstreambuf(const signed char* getptr,
    streamsize count);

strstreambuf(const unsigned char* getptr,
    streamsize count);
```

### <a name="parameters"></a>Параметры

*alloc_func*\
Функция, используемая для выделения памяти буфера.

*count*\
Определяет длину буфера, на который указывает *жетптр*. Если *жетптр* не является аргументом (первой формой конструктора), рекомендуемый размер выделения буферов.

*_Freefunc*\
Функция, используемая для освобождения памяти буфера.

*жетптр*\
Буфер, используемый для ввода.

*путптр*\
Буфер, используемый для вывода.

### <a name="remarks"></a>Примечания

Первый конструктор сохраняет пустой указатель во всех указателях, управляющих входным и выходным буферами, а также распределением strstreambuf. Он задает сохраненный режим strstreambuf, чтобы сделать управляемую последовательность доступной для изменения и расширения. Он *также принимает значение* в качестве предполагаемого первоначального размера выделения.

Второй конструктор ведет себя так же, как первый, за исключением того, что он хранит *alloc_func* как указатель на функцию для вызова, чтобы выделить память и *free_func* в качестве указателя на функцию для вызова для освобождения хранилища.

Три конструктора:

```cpp
strstreambuf(char *getptr,
    streamsize count,
    char *putptr = 0);

strstreambuf(signed char *getptr,
    streamsize count,
    signed char *putptr = 0);

strstreambuf(unsigned char *getptr,
    streamsize count,
    unsigned char *putptr = 0);
```

также работает аналогично первому, за исключением того, что *жетптр* обозначает объект массива, используемый для хранения управляемой последовательности. (Следовательно, он не должен быть пустым указателем.) Число элементов *N* в массиве определяется следующим образом:

- Если значение (*count* > 0), то *число* *N* будет равно.

- Если (*Count* = = 0), то *N* имеет значение `strlen((const char *) getptr )` .

- Если (*count* < 0), то *N* **INT_MAX**.

Если *путптр* является пустым указателем, функция устанавливает только входной буфер, выполняя:

```cpp
setg(getptr,
    getptr,
    getptr + N);
```

В противном случае она устанавливает и входной, и выходной буферы, выполняя следующее.

```cpp
setg(getptr,
    getptr,
    putptr);

setp(putptr,
    getptr + N);
```

В этом случае *путптр* должно быть в интервале [ *жетптр*, *жетптр*  +  *N*].

Наконец, три конструктора:

```cpp
strstreambuf(const char *getptr,
    streamsize count);

strstreambuf(const signed char *getptr,
    streamsize count);

strstreambuf(const unsigned char *getptr,
    streamsize count);
```

все ведут себя так же как:

```cpp
streambuf((char *)getptr, count);
```

за исключением того, что хранимый режим делает управляемую последовательность недоступной для изменения или расширения.

## <a name="strstreambufunderflow"></a><a name="underflow"></a>strstreambuf:: потеря значимости

Защищенная виртуальная функция для извлечения текущего элемента из входного потока.

```cpp
virtual int underflow();
```

### <a name="return-value"></a>Возвращаемое значение

Если функции не удалось выполниться успешно, возвращается значение `EOF`. В противном случае она возвращает текущий элемент во входном потоке, преобразованный, как описано выше.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция члена пытается извлечь текущий элемент `ch` из входного буфера, затем переместить текущее расположение потока и вернуть элемент в качестве `(int)(unsigned char)ch` . Это можно сделать только одним способом: Если доступная позиции чтения доступна, она принимает в `ch` качестве элемента, хранящегося в позиции чтения, и перемещает следующий указатель для входного буфера.

## <a name="see-also"></a>См. также раздел

[streambuf](../standard-library/streambuf-typedefs.md#streambuf)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
