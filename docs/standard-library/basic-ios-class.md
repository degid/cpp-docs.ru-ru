---
title: Класс basic_ios
ms.date: 11/04/2016
f1_keywords:
- ios/std::basic_ios
- ios/std::basic_ios::char_type
- ios/std::basic_ios::int_type
- ios/std::basic_ios::off_type
- ios/std::basic_ios::pos_type
- ios/std::basic_ios::traits_type
- ios/std::basic_ios::bad
- ios/std::basic_ios::clear
- ios/std::basic_ios::copyfmt
- ios/std::basic_ios::eof
- ios/std::basic_ios::exceptions
- ios/std::basic_ios::fail
- ios/std::basic_ios::fill
- ios/std::basic_ios::good
- ios/std::basic_ios::imbue
- ios/std::basic_ios::init
- ios/std::basic_ios::move
- ios/std::basic_ios::narrow
- ios/std::basic_ios::rdbuf
- ios/std::basic_ios::rdstate
- ios/std::basic_ios::set_rdbuf
- ios/std::basic_ios::setstate
- ios/std::basic_ios::swap
- ios/std::basic_ios::tie
- ios/std::basic_ios::widen
- ios/std::basic_ios::explicit operator bool
helpviewer_keywords:
- std::basic_ios [C++]
- std::basic_ios [C++], char_type
- std::basic_ios [C++], int_type
- std::basic_ios [C++], off_type
- std::basic_ios [C++], pos_type
- std::basic_ios [C++], traits_type
- std::basic_ios [C++], bad
- std::basic_ios [C++], clear
- std::basic_ios [C++], copyfmt
- std::basic_ios [C++], eof
- std::basic_ios [C++], exceptions
- std::basic_ios [C++], fail
- std::basic_ios [C++], fill
- std::basic_ios [C++], good
- std::basic_ios [C++], imbue
- std::basic_ios [C++], init
- std::basic_ios [C++], move
- std::basic_ios [C++], narrow
- std::basic_ios [C++], rdbuf
- std::basic_ios [C++], rdstate
- std::basic_ios [C++], set_rdbuf
- std::basic_ios [C++], setstate
- std::basic_ios [C++], swap
- std::basic_ios [C++], tie
- std::basic_ios [C++], widen
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
ms.openlocfilehash: b730933879df04d2455b5eae6fc5abf16bbf4484
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219278"
---
# <a name="basic_ios-class"></a>Класс basic_ios

Шаблон класса описывает хранилище и функции-члены, общие для входных потоков (класса Template [basic_istream](../standard-library/basic-istream-class.md)) и потоков вывода (шаблона класса [basic_ostream](../standard-library/basic-ostream-class.md)), которые зависят от параметров шаблона. (Класс [ios_base](../standard-library/ios-base-class.md) описывает общие и независящие от параметров шаблона параметры.) Объект класса ** \<class Elem, class Traits> basic_ios** помогает управлять потоком с элементами типа `Elem` , признаки символов которых определяются классом `Traits` .

## <a name="syntax"></a>Синтаксис

```cpp

template <class Elem, class Traits>
class basic_ios : public ios_base
```

### <a name="parameters"></a>Параметры

*Elem*\
Тип.

*Traits*\
Переменная типа `char_traits`.

## <a name="remarks"></a>Примечания

Объект класса **basic_ios \<class Elem, class Traits> ** хранит:

- Указатель привязки к объекту типа [basic_istream](../standard-library/basic-istream-class.md) **\<Elem, Traits>** .

- Указатель буфера потока на объект типа [basic_streambuf](../standard-library/basic-streambuf-class.md) **\<Elem, Traits >** .

- [Сведения о форматировании](../standard-library/ios-base-class.md).

- [Сведения о состоянии потока](../standard-library/ios-base-class.md) в базовом объекте типа [ios_base](../standard-library/ios-base-class.md).

- Символ заполнения в объекте типа `char_type`.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_ios](#basic_ios)|Создает класс `basic_ios`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Синоним параметра шаблона `Elem`.|
|[int_type](#int_type)|Синоним для `Traits::int_type`.|
|[off_type](#off_type)|Синоним для `Traits::off_type`.|
|[pos_type](#pos_type)|Синоним для `Traits::pos_type`.|
|[traits_type](#traits_type)|Синоним параметра шаблона `Traits`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Неправильное значение](#bad)|Сообщает о потере целостности буфера потока.|
|[clear](#clear)|Очищает все флаги ошибок.|
|[copyfmt](#copyfmt)|Копирует флаги из одного потока в другой.|
|[конца](#eof)|Указывает, достигнут ли конец потока.|
|[exceptions](#exceptions)|Указывает, какие исключения будут создаваться потоком.|
|[Cчетчик](#fail)|Сообщает об ошибке при извлечении допустимого поля из потока.|
|[заполнения](#fill)|Задает или возвращает символ, который будет использоваться, если ширина текста не совпадает с шириной потока.|
|[рекомендуется](#good)|Указывает, что поток находится в хорошем состоянии.|
|[imbue](#imbue)|Изменяет языковой стандарт.|
|[init](#init)|Вызывается конструкторами `basic_ios`.|
|[move](#move)|Перемещает все значения, кроме указателя на буфер потока, из параметра в текущий объект.|
|[narrow](#narrow)|Находит эквивалентный char для данного `char_type`.|
|[rdbuf](#rdbuf)|Направляет поток в указанный буфер.|
|[rdstate](#rdstate)|Считывает состояние битов для флагов.|
|[set_rdbuf](#set_rdbuf)|Назначает буфер потока буфером чтения для этого объекта потока.|
|[setstate](#setstate)|Устанавливает дополнительные флаги.|
|[swap](#swap)|Меняет местами значения в этом объекте `basic_ios` и значения другого объекта `basic_ios`. Указатели на буферы потока не меняются местами.|
|[tie](#tie)|Гарантирует, что один поток обрабатывается до другого потока.|
|[widen](#widen)|Находит эквивалент `char_type` для указанного char.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[explicit operator bool](#op_bool)|Позволяет использовать объект в `basic_ios` качестве **`bool`** . Автоматическое преобразование типов отключено для предотвращения распространенных непредвиденных побочных эффектов.|
|[operator void *](#op_void_star)|Указывает, находится ли поток по-прежнему в хорошем состоянии.|
|[operator!](#op_not)|Указывает, не находится ли поток в плохом состоянии.|

## <a name="requirements"></a>Требования

**Заголовок:**\<ios>

**Пространство имен:** std

## <a name="basic_iosbad"></a><a name="bad"></a>basic_ios:: Bad

Сообщает о потере целостности буфера потока.

```cpp
bool bad() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`**`rdstate & badbit`значение, если значение не равно нулю; в противном случае **`false`** .

Дополнительные сведения по `badbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Пример

```cpp
// basic_ios_bad.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
    using namespace std;
    bool b = cout.bad( );
    cout << boolalpha;
    cout << b << endl;

    b = cout.good( );
    cout << b << endl;
}
```

## <a name="basic_iosbasic_ios"></a><a name="basic_ios"></a>basic_ios:: basic_ios

Конструирует класс basic_ios.

```cpp
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```

### <a name="parameters"></a>Параметры

*средствами*\
Стандартный буфер для хранения элементов ввода или вывода.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует свой объект-член путем вызова [init](#init)(_ *Sb*). Второй (защищенный) конструктор оставляет свои объекты-члены не инициализированными. После последующего вызова метод `init` должен инициализировать объект, прежде чем его можно будет безопасно уничтожить.

## <a name="basic_ioschar_type"></a><a name="char_type"></a>basic_ios:: char_type

Синоним параметра шаблона `Elem`.

```cpp
typedef Elem char_type;
```

## <a name="basic_iosclear"></a><a name="clear"></a>basic_ios:: Clear

Очищает все флаги ошибок.

```cpp
void clear(iostate state = goodbit, bool reraise = false);
void clear(io_state state);
```

### <a name="parameters"></a>Параметры

*с*\
Используемых Флаги, которые необходимо задать после очистки всех флагов. По умолчанию — `goodbit`.

*reraise*\
Используемых Указывает, следует ли повторно создавать исключение. По умолчанию принимает значение **`false`** (исключение не будет повторно вызываться).

### <a name="remarks"></a>Примечания

Флаги: `goodbit` , `failbit` , `eofbit` и `badbit` . Проверяет наличие этих флагов с помощью [good](#good), [bad](#bad), [eof](#eof) и [fail](#fail)

Функция-член заменяет сохраненную информацию о состоянии потока на следующее:

`state` &#124; `(`[rdbuf](#rdbuf) != 0 **goodbit** : **badbit**)

Если `state` **&** [исключения](#exceptions) являются ненулевыми, то он создает объект с [ошибкой](../standard-library/ios-base-class.md#failure)класса.

### <a name="example"></a>Пример

Примеры использования см. в разделе [rdstate](#rdstate) и @ [line](../standard-library/string-functions.md#getline) `clear` .

## <a name="basic_ioscopyfmt"></a><a name="copyfmt"></a>basic_ios:: copyfmt

Копирует флаги из одного потока в другой.

```cpp
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```

### <a name="parameters"></a>Параметры

*right*\
Поток, флаги которого требуется скопировать.

### <a name="return-value"></a>Возвращаемое значение

**`this`** Объект для потока, в который копируются флаги.

### <a name="remarks"></a>Примечания

Функция – член сообщает о ** \_ событии стирания**события обратного вызова. Затем он копируется *непосредственно* в ** \* этот** символ заполнения, указатель на привязку и сведения о форматировании. Перед изменением маски исключения он сообщает о событии обратного вызова `copyfmt_event` . Если после завершения копирования **state & **[exceptions](#exceptions) не равно нулю, функция эффективно вызывает [clear](#clear) с аргументом [rdstate](#rdstate). Он возвращает ** \*this**.

### <a name="example"></a>Пример

```cpp
// basic_ios_copyfmt.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
    using namespace std;
    ofstream x( "test.txt" );
    int i = 10;

    x << showpos;
    cout << i << endl;
    cout.copyfmt( x );
    cout << i << endl;
}
```

## <a name="basic_ioseof"></a><a name="eof"></a>basic_ios:: EOF

Указывает, достигнут ли конец потока.

```cpp
bool eof() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если конец потока достигнут, **`false`** в противном случае.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение **`true`** , если [rdstate](#rdstate) `& eofbit` не равно нулю. Дополнительные сведения по `eofbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Пример

```cpp
// basic_ios_eof.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

int main( int argc, char* argv[] )
{
    fstream   fs;
    int n = 1;
    fs.open( "basic_ios_eof.txt" );   // an empty file
    cout << boolalpha
    cout << fs.eof() << endl;
    fs >> n;   // Read the char in the file
    cout << fs.eof() << endl;
}
```

## <a name="basic_iosexceptions"></a><a name="exceptions"></a>basic_ios:: исключения

Указывает, какие исключения будут создаваться потоком.

```cpp
iostate exceptions() const;
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```

### <a name="parameters"></a>Параметры

*невексцепт*\
Флаги, которые должны вызывать исключение.

### <a name="return-value"></a>Возвращаемое значение

Флаги, указанные в настоящий момент для создания исключения для потока.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает сохраненную маску исключения. Вторая функция-член сохраняет *_Except* в маске исключения и возвращает предыдущее хранившееся там значение. Обратите внимание, что сохранение новой маски исключения может вызвать исключение так же, как вызов [clear](#clear)( [rdstate](#rdstate) ).

### <a name="example"></a>Пример

```cpp
// basic_ios_exceptions.cpp
// compile with: /EHsc /GR
#include <iostream>

int main( )
{
    using namespace std;

    cout << cout.exceptions( ) << endl;
    cout.exceptions( ios::eofbit );
    cout << cout.exceptions( ) << endl;
    try
    {
        cout.clear( ios::eofbit );   // Force eofbit on
    }
    catch ( exception &e )
    {
        cout.clear( );
        cout << "Caught the exception." << endl;
        cout << "Exception class: " << typeid(e).name()  << endl;
        cout << "Exception description: " << e.what() << endl;
    }
}
```

```Output
0
1
Caught the exception.
Exception class: class std::ios_base::failure
Exception description: ios_base::eofbit set
```

## <a name="basic_iosfail"></a><a name="fail"></a>basic_ios:: Fail

Сообщает об ошибке при извлечении допустимого поля из потока.

```cpp
bool fail() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если [rdstate](#rdstate) `& (badbit|failbit)` не равно нулю, в противном случае **`false`** .

Дополнительные сведения по `failbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Пример

```cpp
// basic_ios_fail.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
    using namespace std;
    bool b = cout.fail( );
    cout << boolalpha;
    cout << b << endl;
}
```

## <a name="basic_iosfill"></a><a name="fill"></a>basic_ios:: Fill

Задает или возвращает символ, который будет использоваться, если ширина текста не совпадает с шириной потока.

```cpp
char_type fill() const;
char_type fill(char_type Char);
```

### <a name="parameters"></a>Параметры

*Типа*\
Символ, который нужно использовать в качестве символа заливки.

### <a name="return-value"></a>Возвращаемое значение

Текущий символ заливки.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает сохраненный символ заливки. Вторая функция *члена сохраняет знак* в символе заполнения и возвращает свое предыдущее сохраненное значение.

### <a name="example"></a>Пример

```cpp
// basic_ios_fill.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>

int main( )
{
    using namespace std;

    cout << setw( 5 ) << 'a' << endl;
    cout.fill( 'x' );
    cout << setw( 5 ) << 'a' << endl;
    cout << cout.fill( ) << endl;
}
```

```Output
a
xxxxa
x
```

## <a name="basic_iosgood"></a><a name="good"></a>basic_ios:: хорошее

Указывает, что поток находится в хорошем состоянии.

```cpp
bool good() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`**, если [rdstate](#rdstate) `== goodbit` (флаги состояния не заданы), в противном случае — **`false`** .

Дополнительные сведения по `goodbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Пример

Пример использования `good` разделе [basic_ios::bad](#bad).

## <a name="basic_iosimbue"></a><a name="imbue"></a>basic_ios:: imbue

Изменяет языковой стандарт.

```cpp
locale imbue(const locale& Loc);
```

### <a name="parameters"></a>Параметры

*Loc*\
Строка языкового стандарта.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий языковой стандарт.

### <a name="remarks"></a>Примечания

Если [rdbuf](#rdbuf) не является пустым указателем, функция-член вызывает

`rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#pubimbue)(_ *Loc*)

В любом случае возвращается [ios_base::imbue](../standard-library/ios-base-class.md#imbue)(_ *Loc*).

### <a name="example"></a>Пример

```cpp
// basic_ios_imbue.cpp
// compile with: /EHsc
#include <iostream>
#include <locale>

int main( )
{
    using namespace std;

    cout.imbue( locale( "french_france" ) );
    double x = 1234567.123456;
    cout << x << endl;
}
```

## <a name="basic_iosinit"></a><a name="init"></a>basic_ios:: init

Вызывается конструкторами basic_ios.

```cpp
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```

### <a name="parameters"></a>Параметры

*_Sb*\
Стандартный буфер для хранения элементов ввода или вывода.

*_Isstd*\
Указывает, является ли этот поток стандартным.

### <a name="remarks"></a>Примечания

Функция-член сохраняет значения во всех объектах-членах, так что:

- [rdbuf](#rdbuf) возвращает *_Sb*;

- [tie](#tie) возвращает пустой указатель;

- [rdstate](#rdstate) возвращает значение [goodbit](../standard-library/ios-base-class.md#iostate) , если *_Sb* не равно нулю; в противном случае возвращается [badbit](../standard-library/ios-base-class.md#iostate).

- [исключения](#exceptions) возвращают `goodbit` .

- [flags](../standard-library/ios-base-class.md#flags) возвращает [skipws](../standard-library/ios-base-class.md#fmtflags) &#124; [dec](../standard-library/ios-base-class.md#fmtflags);

- [width](../standard-library/ios-base-class.md#width) возвращает 0;

- [precision](../standard-library/ios-base-class.md#precision) возвращает 6;

- [fill](#fill) возвращает символ пробела;

- [getloc](../standard-library/ios-base-class.md#getloc) возвращает `locale::classic`;

- [iword](../standard-library/ios-base-class.md#iword) возвращает ноль, и [pword](../standard-library/ios-base-class.md#pword) возвращает пустой указатель для всех значений аргумента.

## <a name="basic_iosint_type"></a><a name="int_type"></a>basic_ios:: int_type

Синоним для `traits_type::int_type`.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_iosmove"></a><a name="move"></a>basic_ios:: Move

Перемещает все значения, кроме указателя на буфер потока, из параметра в текущий объект.

```cpp
void move(basic_ios&& right);
```

### <a name="parameters"></a>Параметры

*right*\
Объект `ios_base`, из которого будут перемещаться значения.

### <a name="remarks"></a>Примечания

Защищенная функция-член перемещает все значения, хранящиеся *справа* **`*this`** , за исключением хранимой функции `stream buffer pointer` , которая не изменяется в *правой части* и устанавливает для нее указатель null в **`*this`** . Сохраненный `tie pointer` указатель имеет значение NULL в *правильном*указателе.

## <a name="basic_iosnarrow"></a><a name="narrow"></a>basic_ios:: Narrow

Находит эквивалентный char для данного `char_type`.

```cpp
char narrow(char_type Char, char Default = '\0') const;
```

### <a name="parameters"></a>Параметры

*Типа*\
**`char`** Преобразуемый объект.

*Параметры*\
Объект **`char`** , который должен возвращаться, если эквивалент не найден.

### <a name="return-value"></a>Возвращаемое значение

Эквивалент **`char`** заданного `char_type` .

### <a name="remarks"></a>Примечания

Функция-член возвращает [use_facet](../standard-library/basic-filebuf-class.md#open) \<ctype\<E> > ( [getloc](../standard-library/ios-base-class.md#getloc)()). `narrow` ( `Char`, `Default`).

### <a name="example"></a>Пример

```cpp
// basic_ios_narrow.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <wchar.h>

int main( )
{
    using namespace std;
    wchar_t *x = L"test";
    char y[10];
    cout << x[0] << endl;
    wcout << x << endl;
    y[0] = wcout.narrow( x[0] );
    cout << y[0] << endl;
}
```

## <a name="basic_iosoff_type"></a><a name="off_type"></a>basic_ios:: off_type

Синоним для `traits_type::off_type`.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_iosoperator-void-"></a><a name="op_void_star"></a>basic_ios::operator void *

Указывает, находится ли поток по-прежнему в хорошем состоянии.

```cpp
operator void *() const;
```

### <a name="return-value"></a>Возвращаемое значение

Оператор возвращает пустой указатель только в том случае, если [fail](#fail).

### <a name="example"></a>Пример

```cpp
// basic_ios_opgood.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << (bool)(&cout != 0) << endl;   // Stream is still good
}
```

```Output
1
```

## <a name="basic_iosoperator"></a><a name="op_not"></a>basic_ios::operator!

Указывает, не находится ли поток в плохом состоянии.

```cpp
bool operator!() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает [fail](#fail).

### <a name="example"></a>Пример

```cpp
// basic_ios_opbad.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << !cout << endl;   // Stream is not bad
}
```

```Output
0
```

## <a name="basic_iosoperator-bool"></a><a name="op_bool"></a>basic_ios::operator bool

Позволяет использовать объект в `basic_ios` качестве **`bool`** . Автоматическое преобразование типов отключено для предотвращения распространенных непредвиденных побочных эффектов.

```cpp
explicit operator bool() const;
```

### <a name="remarks"></a>Примечания

Оператор возвращает значение, которое можно преобразовать в, **`false`** только если `fail()` . Тип возвращаемого значения может быть преобразован только в **`bool`** , `void *` а не в или на другой известный скалярный тип.

## <a name="basic_iospos_type"></a><a name="pos_type"></a>basic_ios::p os_type

Синоним для `traits_type::pos_type`.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_iosrdbuf"></a><a name="rdbuf"></a>basic_ios:: rdbuf

Направляет поток в указанный буфер.

```cpp
basic_streambuf<Elem, Traits> *rdbuf() const;
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```

### <a name="parameters"></a>Параметры

*_Sb*\
Поток.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает сохраненный указатель буфера потока.

Вторая функция члена сохраняет *_Sb* в указателе буфера сохраненного потока и возвращает ранее сохраненное значение.

### <a name="example"></a>Пример

```cpp
// basic_ios_rdbuf.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <fstream>

int main( )
{
    using namespace std;
    ofstream file( "rdbuf.txt" );
    streambuf *x = cout.rdbuf( file.rdbuf( ) );
    cout << "test" << endl;   // Goes to file
    cout.rdbuf(x);
    cout << "test2" << endl;
}
```

```Output
test2
```

## <a name="basic_iosrdstate"></a><a name="rdstate"></a>basic_ios:: rdstate

Считывает состояние битов для флагов.

```cpp
iostate rdstate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сведения о состоянии сохраненного потока.

### <a name="example"></a>Пример

```cpp
// basic_ios_rdstate.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>
using namespace std;

void TestFlags( ios& x )
{
    cout << ( x.rdstate( ) & ios::badbit ) << endl;
    cout << ( x.rdstate( ) & ios::failbit ) << endl;
    cout << ( x.rdstate( ) & ios::eofbit ) << endl;
    cout << endl;
}

int main( )
{
    fstream x( "c:\test.txt", ios::out );
    x.clear( );
    TestFlags( x );
    x.clear( ios::badbit | ios::failbit | ios::eofbit );
    TestFlags( x );
}
```

```Output
0
0
0

4
2
1
```

## <a name="basic_iossetstate"></a><a name="setstate"></a>basic_ios:: setState

Устанавливает дополнительные флаги.

```cpp
void setstate(iostate _State);
```

### <a name="parameters"></a>Параметры

*_State*\
Дополнительные флаги для установки.

### <a name="remarks"></a>Примечания

Эта функция-член эффективно вызывает [clear](#clear)(_ *State* &#124; [rdstate](#rdstate)).

### <a name="example"></a>Пример

```cpp
// basic_ios_setstate.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
using namespace std;

int main( )
{
    bool b = cout.bad( );
    cout << b << endl;   // Good
    cout.clear( ios::badbit );
    b = cout.bad( );
    // cout.clear( );
    cout << b << endl;   // Is bad, good
    b = cout.fail( );
    cout << b << endl;   // Not failed
    cout.setstate( ios::failbit );
    b = cout.fail( );
    cout.clear( );
    cout << b << endl;   // Is failed, good
    return 0;
}
```

```Output
0
1
```

## <a name="basic_iosset_rdbuf"></a><a name="set_rdbuf"></a>basic_ios:: set_rdbuf

Назначает буфер потока буфером чтения для этого объекта потока.

```cpp
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)
```

### <a name="parameters"></a>Параметры

*strBuf*\
Буфер потока, который должен стать буфером чтения.

### <a name="remarks"></a>Примечания

Защищенная функция члена сохраняет *strBuf* в `stream buffer pointer` . Он не вызывает `clear` .

## <a name="basic_iostie"></a><a name="tie"></a>basic_ios:: привязать

Гарантирует, что один поток обрабатывается до другого потока.

```cpp
basic_ostream<Elem, Traits> *tie() const;
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```

### <a name="parameters"></a>Параметры

*str*\
Поток.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает сохраненный указатель tie. Вторая функция члена сохраняет *str* в указателе привязки и возвращает свое предыдущее сохраненное значение.

### <a name="remarks"></a>Примечания

`tie` вызывает синхронизацию двух потоков, так что операции в одном потоке операций происходят после завершения операций в другом потоке.

### <a name="example"></a>Пример

В этом примере путем связывания cin с cout гарантируется, что строка "Enter a number:" будет появляться на консоли перед самим номером, извлекаемым из cin. Это исключает возможность того, что строка "Enter a number:" будет оставаться в буфере при считывании номера, и таким образом мы гарантируем, что пользователь фактически получает некоторый запрос, на который нужно отреагировать. По умолчанию cin и cout связаны.

```cpp
#include <ios>
#include <iostream>

int main( )
{
    using namespace std;
    int i;
    cin.tie( &cout );
    cout << "Enter a number:";
    cin >> i;
}
```

## <a name="basic_iostraits_type"></a><a name="traits_type"></a>basic_ios:: traits_type

Синоним параметра шаблона `Traits`.

```cpp
typedef Traits traits_type;
```

## <a name="basic_ioswiden"></a><a name="widen"></a>basic_ios:: Widening

Находит эквивалент `char_type` заданного **`char`** .

```cpp
char_type widen(char Char) const;
```

### <a name="parameters"></a>Параметры

*Типа*\
Символ для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Находит эквивалент `char_type` заданного **`char`** .

### <a name="remarks"></a>Примечания

Функция-член возвращает [use_facet](../standard-library/basic-filebuf-class.md#open) <  **CType** \< **E**> > ( [getloc](../standard-library/ios-base-class.md#getloc)). `widen`( `Char`).

### <a name="example"></a>Пример

```cpp
// basic_ios_widen.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <wchar.h>

int main( )
{
    using namespace std;
    char *z = "Hello";
    wchar_t y[2] = {0,0};
    cout << z[0] << endl;
    y[0] = wcout.widen( z[0] );
    wcout << &y[0] << endl;
}
```

## <a name="basic_iosswap"></a><a name="swap"></a>basic_ios:: swap

Меняет местами значения в этом объекте `basic_ios` и значения другого объекта `basic_ios`. Однако указатели на буферы потока не меняются местами.

```cpp
void swap(basic_ios&& right);
```

### <a name="parameters"></a>Параметры

*right*\
Объект `basic_ios`, используемый для обмена значений.

### <a name="remarks"></a>Примечания

Защищенная функция элемента обменивается со всеми значениями, которые хранятся *справа* , **`*this`** за исключением хранимой функции `stream buffer pointer` .

## <a name="see-also"></a>См. также раздел

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
