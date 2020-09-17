---
title: Класс ios_base
ms.date: 11/04/2016
f1_keywords:
- xiosbase/std::ios_base
- ios/std::ios_base::event_callback
- xiosbase/std::ios_base::fmtflags
- xiosbase/std::ios_base::iostate
- xiosbase/std::ios_base::openmode
- xiosbase/std::ios_base::seekdir
- xiosbase/std::ios_base::event
- xiosbase/std::ios_base::adjustfield
- xiosbase/std::ios_base::app
- xiosbase/std::ios_base::ate
- xiosbase/std::ios_base::badbit
- xiosbase/std::ios_base::basefield
- xiosbase/std::ios_base::beg
- xiosbase/std::ios_base::binary
- xiosbase/std::ios_base::boolalpha
- xiosbase/std::ios_base::cur
- xiosbase/std::ios_base::dec
- xiosbase/std::ios_base::end
- xiosbase/std::ios_base::eofbit
- xiosbase/std::ios_base::failbit
- xiosbase/std::ios_base::fixed
- xiosbase/std::ios_base::floatfield
- xiosbase/std::ios_base::goodbit
- xiosbase/std::ios_base::hex
- xiosbase/std::ios_base::in
- xiosbase/std::ios_base::internal
- xiosbase/std::ios_base::left
- xiosbase/std::ios_base::oct
- xiosbase/std::ios_base::out
- xiosbase/std::ios_base::right
- xiosbase/std::ios_base::scientific
- xiosbase/std::ios_base::showbase
- xiosbase/std::ios_base::showpoint
- xiosbase/std::ios_base::showpos
- xiosbase/std::ios_base::skipws
- xiosbase/std::ios_base::trunc
- xiosbase/std::ios_base::unitbuf
- xiosbase/std::ios_base::uppercase
- xiosbase/std::ios_base::failure
- xiosbase/std::ios_base::flags
- xiosbase/std::ios_base::getloc
- xiosbase/std::ios_base::imbue
- xiosbase/std::ios_base::Init
- xiosbase/std::ios_base::iword
- xiosbase/std::ios_base::precision
- xiosbase/std::ios_base::pword
- ios/std::ios_base::register_callback
- xiosbase/std::ios_base::setf
- xiosbase/std::ios_base::sync_with_stdio
- xiosbase/std::ios_base::unsetf
- xiosbase/std::ios_base::width
- xiosbase/std::ios_base::xalloc
helpviewer_keywords:
- std::ios_base [C++]
- std::ios_base [C++], event_callback
- std::ios_base [C++], fmtflags
- std::ios_base [C++], iostate
- std::ios_base [C++], openmode
- std::ios_base [C++], seekdir
- std::ios_base [C++], event
- std::ios_base [C++], adjustfield
- std::ios_base [C++], app
- std::ios_base [C++], ate
- std::ios_base [C++], badbit
- std::ios_base [C++], basefield
- std::ios_base [C++], beg
- std::ios_base [C++], binary
- std::ios_base [C++], boolalpha
- std::ios_base [C++], cur
- std::ios_base [C++], dec
- std::ios_base [C++], end
- std::ios_base [C++], eofbit
- std::ios_base [C++], failbit
- std::ios_base [C++], fixed
- std::ios_base [C++], floatfield
- std::ios_base [C++], goodbit
- std::ios_base [C++], hex
- std::ios_base [C++], in
- std::ios_base [C++], internal
- std::ios_base [C++], left
- std::ios_base [C++], oct
- std::ios_base [C++], out
- std::ios_base [C++], right
- std::ios_base [C++], scientific
- std::ios_base [C++], showbase
- std::ios_base [C++], showpoint
- std::ios_base [C++], showpos
- std::ios_base [C++], skipws
- std::ios_base [C++], trunc
- std::ios_base [C++], unitbuf
- std::ios_base [C++], uppercase
- std::ios_base [C++], failure
- std::ios_base [C++], flags
- std::ios_base [C++], getloc
- std::ios_base [C++], imbue
- std::ios_base [C++], Init
- std::ios_base [C++], iword
- std::ios_base [C++], precision
- std::ios_base [C++], pword
- std::ios_base [C++], register_callback
- std::ios_base [C++], setf
- std::ios_base [C++], sync_with_stdio
- std::ios_base [C++], unsetf
- std::ios_base [C++], width
- std::ios_base [C++], xalloc
ms.assetid: 0f9e0abc-f70f-49bc-aa1f-003859f56cfe
ms.openlocfilehash: da7c8eee2653a34035f39fe272378ae63165bfc2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845501"
---
# <a name="ios_base-class"></a>Класс ios_base

Этот класс описывает хранилище и функции-члены общие для обоих потоков (ввода и вывода), не зависящих от параметров шаблона. (Шаблон класса [basic_ios](../standard-library/basic-ios-class.md) описывает общие параметры и зависит от параметров шаблона.)

Объект класса ios_base хранит сведения о форматировании, состоящие из следующих элементов:

- Флаги формата в объекте типа [`fmtflags`](#fmtflags) .

- Маска исключения в объекте типа [`iostate`](#iostate) .

- Ширина поля в объекте типа **`int`** .

- Точность представления в объекте типа **`int`** .

- Объект языкового стандарта в объекте типа `locale` .

- Два расширяемых массива с элементами типа **`long`** и **`void`** указателя.

Объект класса ios_base также хранит сведения о состоянии потока в объекте типа [`iostate`](#iostate) и стеке обратного вызова.

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[ios_base](#ios_base)|Создает объект `ios_base`.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[event_callback](#event_callback)|Описывает функцию, передаваемую в [register_call](#register_callback).|
|[`fmtflags`](#fmtflags)|Константы для определения внешнего вида выходных данных.|
|[`iostate`](#iostate)|Определяет константы, описывающие состояние потока.|
|[openmode](#openmode)|Описывает процесс взаимодействия с потоком.|
|[seekdir](#seekdir)|Задает начальную точку для операций смещения.|

### <a name="enums"></a>Перечисления

|Имя|Описание|
|-|-|
|[event](#event)|Задает типы событий.|

### <a name="constants"></a>Константы

|Имя|Описание|
|-|-|
|[adjustfield](#fmtflags)|Битовая маска, определенная как `internal` &#124; `left` &#124; `right`.|
|[app](#openmode)|Задает поиск до конца потока перед каждой вставкой.|
|[ate](#openmode)|Задает поиск до конца потока при первом создании его управляющего объекта.|
|[badbit](#iostate)|Регистрирует потерю целостности буфера потока.|
|[basefield](#fmtflags)|Битовая маска, определенная как `dec` &#124; `hex` &#124; `oct`.|
|[beg](#seekdir)|Задает поиск относительно начала последовательности.|
|[binary](#openmode)|Указывает, что файл должен быть считан как двоичный, а не текстовый поток.|
|[boolalpha](#fmtflags)|Задает вставку или извлечение объектов типа **`bool`** в виде имен (например **`true`** , и **`false`** ), а не числовых значений.|
|[выравнивани](#seekdir)|Задает поиск относительно текущей позиции в последовательности.|
|[уменьшение](#fmtflags)|Задает вставку или извлечение целочисленных значений в десятичном формате.|
|[конце](#seekdir)|Задает поиск относительно конца последовательности.|
|[eofbit](#iostate)|Регистрирует конец файла при извлечении из потока.|
|[failbit](#iostate)|Регистрирует сбой при извлечении допустимого поля из потока.|
|[fixed](#fmtflags)|Задает вставку значений с плавающей запятой в формате с фиксированной запятой (без поля экспоненты).|
|[floatfield](#fmtflags)|Битовая маска, определенная как `fixed` &#124; `scientific`|
|[goodbit](#iostate)|Очищает все биты состояния.|
|[hex](#fmtflags)|Задает вставку или извлечение целочисленных значений в шестнадцатеричном формате.|
|[in](#openmode)|Задает извлечение из потока.|
|[internal](#fmtflags)|Выполняет заполнение по ширине поля, вставляя символы заполнения в точке внутри созданного числового поля.|
|[слева](#fmtflags)|Задает выравнивание по левому краю.|
|[октября](#fmtflags)|Задает вставку или извлечение целочисленных значений в восьмеричном формате.|
|[out](#openmode)|Задает вставку в поток.|
|[Правильно](#fmtflags)|Задает выравнивание по правому краю.|
|[экспоненциаль](#fmtflags)|Задает вставку значений с плавающей запятой в экспоненциальном формате (с полем экспоненты).|
|[showbase](#fmtflags)|Задает вставку префикса, отображающего базу созданного целочисленного поля.|
|[showpoint](#fmtflags)|Задает безусловную вставку десятичной запятой в созданное поле с плавающей запятой.|
|[showpos](#fmtflags)|Задает вставку знака плюс в созданное неотрицательное числовое поле.|
|[skipws](#fmtflags)|Задает пропуск начальных пробелов перед определенными извлечениями.|
|[TRUNC](#openmode)|Задает удаление содержимого существующего файла при создании его управляющего объекта.|
|[unitbuf](#fmtflags)|Обеспечивает запись выходных данных на диск после каждой вставки.|
|[верхний регистр](#fmtflags)|Задает вставку эквивалентных прописных букв для букв нижнего регистра в определенных вставках.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[состояние](#failure)|Класс Member выступает в качестве базового класса для всех исключений, создаваемых функцией члена [clear](../standard-library/basic-ios-class.md#clear) в шаблоне класса [basic_ios](../standard-library/basic-ios-class.md).|
|[flags](#flags)|Задает или возвращает текущие параметры флага.|
|[getloc](#getloc)|Возвращает сохраненный объект языкового стандарта.|
|[imbue](#imbue)|Изменяет языковой стандарт.|
|[Init](#init)|Создает стандартные `iostream` объекты при создании.|
|[iword](#iword)|Присваивает значение, сохраняемое в виде `iword`.|
|[precision](#precision)|Задает количество цифр для отображения числа с плавающей запятой.|
|[pword](#pword)|Присваивает значение, сохраняемое в виде `pword`.|
|[register_callback](#register_callback)|Задает функцию обратного вызова.|
|[setf](#setf)|Задает указанные флаги.|
|[sync_with_stdio](#sync_with_stdio)|Гарантирует, что `iostream` и операции с библиотекой времени выполнения C выполняются в том порядке, в котором они отображаются в исходном коде.|
|[unsetf](#unsetf)|Отключает указанные флаги.|
|[width](#width)|Задает длину потока вывода.|
|[xalloc](#xalloc)|Указывает, что переменная должна быть частью потока.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator=](#op_eq)|Оператор присваивания для объектов `ios_base`.|

## <a name="requirements"></a>Требования

**Заголовок:**\<ios>

**Пространство имен:** std

## <a name="event"></a>Событие<a name="event"></a>

Задает типы событий.

```cpp
enum event {
    erase_event,
    imbue_event,
    copyfmt_event};
```

### <a name="remarks"></a>Примечания

Тип — перечисляемый тип, описывающий объект, который может хранить событие обратного вызова, использованное в качестве аргумента для функции, зарегистрированной в [register_callback](#register_callback). Различные значения события:

- `copyfmt_event`для обнаружения обратного вызова, который выполняется около конца вызова [copyfmt](../standard-library/basic-ios-class.md#copyfmt), непосредственно перед копированием [маски исключения](../standard-library/ios-base-class.md) .

- `erase_event`, чтобы найти обратный вызов, который выполняется в начале вызова [copyfmt](../standard-library/basic-ios-class.md#copyfmt), или в начале вызова деструктора для ** \*this**.

- `imbue_event`для обнаружения обратного вызова, который выполняется в конце вызова [imbue](#imbue), непосредственно перед возвратом функции.

### <a name="example"></a>Пример

Для примера см. [register_callback](#register_callback).

## <a name="event_callback"></a><a name="event_callback"></a> event_callback

Описывает функцию, передаваемую в [register_call](#register_callback).

```cpp
typedef void (__cdecl *event_callback)(
    event _E,
    ios_base& _Base,
    int _I);
```

### <a name="parameters"></a>Параметры

*_E*\
[Событие](#event).

*_Base*\
Поток, в котором был вызов события.

*_I*\
Определенное пользователем число.

### <a name="remarks"></a>Примечания

Тип описывает указатель на функцию, которая может быть зарегистрирована с помощью [register_callback](#register_callback). Функции этого типа не должны вызывать исключение.

### <a name="example"></a>Пример

См. [register_call](#register_callback) для примера с использованием `event_callback`.

## <a name="failure"></a><a name="failure"></a> состояние

Класс `failure` определяет базовый класс для типов всех объектов, вызываемых как исключения, с помощью функций в библиотеке `iostreams`, для отчетов об ошибках, обнаруженных во время операций буфера потока.

```cpp
namespace std {
    class failure : public system_error {
    public:
        explicit failure(
            const string& _Message,
            const error_code& _Code = io_errc::stream);

        explicit failure(
            const char* str,
            const error_code& _Code = io_errc::stream);
    };
}
```

### <a name="remarks"></a>Примечания

Значение, возвращаемое `what()`, — это копия `_Message`, возможно, дополненная тестом на основе `_Code`. Если значение `_Code` не указано, значение по умолчанию — `make_error_code(io_errc::stream)`.

### <a name="example"></a>Пример

```cpp
// ios_base_failure.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.exceptions(ios::failbit);
    try
    {
        file.open( "rm.txt", ios_base::in );
        // Opens nonexistent file for reading
    }
    catch( ios_base::failure f )
    {
        cout << "Caught an exception: " << f.what() << endl;
    }
}
```

```Output
Caught an exception: ios_base::failbit set
```

## <a name="flags"></a><a name="flags"></a> Метки

Задает или возвращает текущие параметры флага.

```cpp
fmtflags flags() const;
fmtflags flags(fmtflags fmtfl);
```

### <a name="parameters"></a>Параметры

*фмтфл*\
Новое значение `fmtflags`.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее или текущее значение `fmtflags`.

### <a name="remarks"></a>Примечания

Список флагов см. в разделе [ios_base::fmtflags](#fmtflags).

Первая функция-член возвращает сохраненные флажки формата. Вторая функция – член сохраняет *фмтфл* в флагах формата и возвращает свое предыдущее сохраненное значение.

### <a name="example"></a>Пример

```cpp
// ios_base_flags.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    cout << cout.flags( ) << endl;
    cout.flags( ios::dec | ios::boolalpha );
    cout << cout.flags( );
}
```

```Output
513
16896
```

## <a name="fmtflags"></a><a name="fmtflags"></a> fmtflags

Константы для определения внешнего вида выходных данных.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type fmtflags;
   static const fmtflags boolalpha;
   static const fmtflags dec;
   static const fmtflags fixed;
   static const fmtflags hex;
   static const fmtflags internal;
   static const fmtflags left;
   static const fmtflags oct;
   static const fmtflags right;
   static const fmtflags scientific;
   static const fmtflags showbase;
   static const fmtflags showpoint;
   static const fmtflags showpos;
   static const fmtflags skipws;
   static const fmtflags unitbuf;
   static const fmtflags uppercase;
   static const fmtflags adjustfield;
   static const fmtflags basefield;
   static const fmtflags floatfield;
   // ...
};
```

### <a name="remarks"></a>Примечания

Поддерживает манипуляторы в [ios](../standard-library/ios.md).

Тип — это тип битовой маски, описывающий объект, который может хранить флаги формата. Ниже перечислены значения различных флагов (элементы).

- `dec`, чтобы вставить или извлечь целочисленные значения в десятичном формате.

- `hex`, чтобы вставить или извлечь целочисленные значения в шестнадцатеричном формате.

- `oct`, чтобы вставить или извлечь целочисленные значения в восьмеричном формате.

- `showbase`, чтобы вставить префикс, отображающий базу созданного целочисленного поля.

- `internal`, чтобы выполнить заполнение по ширине поля, вставляя символы заполнения в точке внутри созданного числового поля. (Сведения о задании ширины поля см. в разделе [`setw`](../standard-library/iomanip-functions.md#setw) ).

- `left`, чтобы выполнить заполнение по ширине поля, вставляя символы заполнения в конец созданного числового поля (выравнивание по левому краю).

- `right`, чтобы выполнить заполнение по ширине поля, вставляя символы заполнения в начало созданного числового поля (выравнивание по правому краю).

- `boolalpha`, чтобы вставить или извлечь объекты типа **`bool`** как имена (например **`true`** , и **`false`** ), а не как числовые значения.

- `fixed`, чтобы вставить значения с плавающей запятой в формате с фиксированной запятой (без поля экспоненты).

- `scientific`, чтобы вставить значения с плавающей запятой в экспоненциальном формате (с полем экспоненты).

- `showpoint`, чтобы выполнить безусловную вставку десятичной запятой в созданное поле с плавающей запятой.

- `showpos`, чтобы вставить знак плюс в созданное неотрицательное числовое поле.

- `skipws`, чтобы пропустить начальные пробелы перед определенными извлечениями.

- `unitbuf`, чтобы записывать выходные данные на диск после каждой вставки.

- `uppercase`, чтобы вставить эквивалентные прописные буквы для букв нижнего регистра в определенных вставках.

Кроме того, ниже приведено несколько полезных значений:

- `adjustfield`, битовая маска, определенная как `internal` &#124; `left` &#124; `right`

- `basefield`, определенная как `dec` &#124; `hex` &#124; `oct`

- `floatfield`, определенная как `fixed` &#124; `scientific`

Примеры функций, изменяющих эти флаги формата, см. в разделе [\<iomanip>](../standard-library/iomanip.md) .

## <a name="getloc"></a><a name="getloc"></a> getloc

Возвращает сохраненный объект языкового стандарта.

```cpp
locale getloc() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект языкового стандарта.

### <a name="example"></a>Пример

```cpp
// ios_base_getlock.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << cout.getloc( ).name( ).c_str( ) << endl;
}
```

```Output
C
```

## <a name="imbue"></a><a name="imbue"></a> imbue

Изменяет языковой стандарт.

```cpp
locale imbue(const locale& _Loc);
```

### <a name="parameters"></a>Параметры

*_Loc*\
Новое значение языкового стандарта.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий языковой стандарт.

### <a name="remarks"></a>Примечания

Функция члена сохраняет *_Loc* в объекте языкового стандарта, а затем сообщает о событии обратного вызова и `imbue_event` . Она возвращает предыдущее сохраненное значение.

### <a name="example"></a>Пример

Пример см. в разделе [basic_ios::imbue](../standard-library/basic-ios-class.md#imbue).

## <a name="init"></a><a name="init"></a> Ini

Создает стандартные `iostream` объекты при создании.

```cpp
class Init { };
```

### <a name="remarks"></a>Примечания

Вложенный класс описывает объект, построение которого гарантирует, что стандартные `iostream` объекты должным образом созданы, даже перед выполнением конструктора для произвольного статического объекта.

## <a name="ios_base"></a><a name="ios_base"></a> ios_base

Создает объекты ios_base.

```cpp
ios_base();
```

### <a name="remarks"></a>Примечания

(Защищенный) конструктор ничего не делает. Последующий вызов `basic_ios::` [init](../standard-library/basic-ios-class.md#init) должен инициализировать объект, прежде чем его можно будет безопасно уничтожить. Таким образом, единственное безопасного использования класса ios_base является базовым классом для [basic_ios](../standard-library/basic-ios-class.md)шаблона класса.

## <a name="iostate"></a><a name="iostate"></a> iostate

Тип констант, описывающих состояние потока.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type iostate;
   static const iostate badbit;
   static const iostate eofbit;
   static const iostate failbit;
   static const iostate goodbit;
   // ...
};
```

### <a name="remarks"></a>Примечания

Тип — это тип битовой маски, описывающий объект, который может хранить данные о состоянии потока. Ниже перечислены значения различных флагов (элементы).

- `badbit` регистрирует потерю целостности буфера потока.

- `eofbit` регистрирует конец файла при извлечении из потока.

- `failbit` регистрирует ошибку извлечения корректного поля из потока.

Кроме того, полезное значение — `goodbit` , где ни один из ранее упомянутых битов не задан ( `goodbit` гарантированно равен нулю).

## <a name="iword"></a><a name="iword"></a> иворд

Присваивает значение, сохраняемое в виде `iword`.

```cpp
long& iword(int idx);
```

### <a name="parameters"></a>Параметры

*IDX*\
Индекс значения для сохранения как `iword`.

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на элемент *idx* расширяемого массива с элементами типа **`long`** . Все элементы эффективно присутствуют и изначально хранят нулевое значение. Возвращенная ссылка является недопустимой после следующего вызова для `iword` объекта, после того как объект изменен вызовом `basic_ios::` [copyfmt](../standard-library/basic-ios-class.md#copyfmt)или после уничтожения объекта.

Если значение *idx* отрицательное или если для элемента недоступно уникальное хранилище, функция вызывает [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)` и возвращает ссылку, которая может быть неуникальной.

Чтобы получить уникальный индекс для использования во всех объектах типа `ios_base` , вызовите [`xalloc`](#xalloc) .

### <a name="example"></a>Пример

[`xalloc`](#xalloc)Пример использования см. в разделе `iword` .

## <a name="openmode"></a><a name="openmode"></a> OpenMode

Описывает процесс взаимодействия с потоком.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type iostate;
   static const iostate badbit;
   static const iostate eofbit;
   static const iostate failbit;
   static const iostate goodbit;
   // ...
};
```

### <a name="remarks"></a>Примечания

Тип — это `bitmask type` , описывающий объект, который может хранить режим открытия для нескольких `iostream` объектов. Ниже перечислены значения различных флагов (элементы).

- `app`, чтобы перейти к концу потока перед каждой вставкой.

- `ate`, чтобы найти конец потока при первом создании его управляющего объекта.

- `binary`, чтобы считать файл в двоичном потоке, а не в виде текстового потока.

- `in`, чтобы допускать извлечение из потока.

- `out`, чтобы позволить вставку в поток.

- `trunc`, чтобы удалить содержимое существующего файла при создании его управляющего объекта.

### <a name="example"></a>Пример

```cpp
// ios_base_openmode.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.open( "rm.txt", ios_base::out | ios_base::trunc );

    file << "testing";
}
```

## <a name="operator"></a><a name="op_eq"></a> operator=

Оператор присваивания для объектов ios_base.

```cpp
ios_base& operator=(const ios_base& right);
```

### <a name="parameters"></a>Параметры

*right*\
Объект типа `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Объект, которому выполняется присваивание.

### <a name="remarks"></a>Примечания

Оператор копирует сохраненные сведения о форматировании, создавая новую копию для любых расширяемых массивов. Затем он возвращает ** \*this**. Обратите внимание, что стек обратных вызовов не копируется.

Этот оператор используется только классами, производными от `ios_base`.

## <a name="precision"></a><a name="precision"></a> обеспечивают

Задает количество цифр для отображения числа с плавающей запятой.

```cpp
streamsize precision() const;
streamsize precision(streamsize _Prec);
```

### <a name="parameters"></a>Параметры

*_Prec*\
Количество значащих цифр при отображении, или количество цифр после десятичной запятой в фиксированной нотации.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает сохраненное [количество цифр для отображения](../standard-library/ios-base-class.md). Вторая функция – член сохраняет *_Prec* в точности экрана и возвращает свое предыдущее сохраненное значение.

### <a name="remarks"></a>Примечания

Числа с плавающей запятой отображаются в фиксированной нотации с помощью [fixed](../standard-library/ios-functions.md#fixed).

### <a name="example"></a>Пример

```cpp
// ios_base_precision.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    float i = 31.31234F;

    cout.precision( 3 );
    cout << i << endl;          // display three significant digits
    cout << fixed << i << endl; // display three digits after decimal
                                // point
}
```

```Output
31.3
31.312
```

## <a name="pword"></a><a name="pword"></a> пворд

Присваивает значение, сохраняемое в виде `pword`.

```cpp
void *& pword(int index);
```

### <a name="parameters"></a>Параметры

*номер*\
Индекс значения для сохранения как `pword`.

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на *индекс* элемента расширяемого массива с элементами типа **`void`** Pointer. Все элементы эффективно присутствуют и изначально хранят нулевой указатель. Возвращенная ссылка является недопустимой после следующего вызова для `pword` объекта, после того как объект изменен вызовом `basic_ios::` [copyfmt](../standard-library/basic-ios-class.md#copyfmt)или после уничтожения объекта.

Если *индекс* является отрицательным или для элемента недоступно уникальное хранилище, функция вызывает [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)` и возвращает ссылку, которая может быть неуникальной.

Чтобы получить уникальный индекс для использования во всех объектах типа `ios_base` , вызовите [`xalloc`](#xalloc) .

### <a name="example"></a>Пример

См. [`xalloc`](#xalloc) с примером использования `pword`.

## <a name="register_callback"></a><a name="register_callback"></a> register_callback

Задает функцию обратного вызова.

```cpp
void register_callback(
    event_callback pfn, int idx);
```

### <a name="parameters"></a>Параметры

*PFN*\
Указатель на функцию обратного вызова.

*IDX*\
Определенное пользователем число.

### <a name="remarks"></a>Примечания

Функция-член помещает пару в `{pfn, idx}` сохраненный [стек обратного вызова](../standard-library/ios-base-class.md)стека обратного вызова. Когда сообщается о событии обратного вызова **EV** , функции вызываются в обратном порядке в реестре по выражению `(*pfn)(ev, *this, idx)` .

### <a name="example"></a>Пример

```cpp
// ios_base_register_callback.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

void callback1( ios_base::event e, ios_base& stream, int arg )
{
    cout << "in callback1" << endl;
    switch ( e )
    {
    case ios_base::erase_event:
        cout << "an erase event" << endl;
        break;
    case ios_base::imbue_event:
        cout << "an imbue event" << endl;
        break;
    case ios_base::copyfmt_event:
        cout << "an copyfmt event" << endl;
        break;
    };
}

void callback2( ios_base::event e, ios_base& stream, int arg )
{
    cout << "in callback2" << endl;
    switch ( e )
    {
    case ios_base::erase_event:
        cout << "an erase event" << endl;
        break;
    case ios_base::imbue_event:
        cout << "an imbue event" << endl;
        break;
    case ios_base::copyfmt_event:
        cout << "an copyfmt event" << endl;
        break;
    };
}

int main( )
{
    // Make sure the imbue will not throw an exception
    // assert( setlocale( LC_ALL, "german" )!=NULL );

    cout.register_callback( callback1, 0 );
    cin.register_callback( callback2, 0 );

    try
    {
        // If no exception because the locale's not found,
        // generate an imbue_event on callback1
        cout.imbue(locale("german"));
    }
    catch(...)
    {
        cout << "exception" << endl;
    }

    // This will
    // (1) erase_event on callback1
    // (2) copyfmt_event on callback2
    cout.copyfmt(cin);

    // We get two erase events from callback2 at the end because
    // both cin and cout have callback2 registered when cin and cout
    // are destroyed at the end of program.
}
```

```Output
in callback1
an imbue event
in callback1
an erase event
in callback2
an copyfmt event
in callback2
an erase event
in callback2
an erase event
```

## <a name="seekdir"></a><a name="seekdir"></a> seekdir

Задает начальную точку для операций смещения.

```cpp
namespace std {
    class ios_base {
    public:
        typedef implementation-defined-enumerated-type seekdir;
        static const seekdir beg;
        static const seekdir cur;
        static const seekdir end;
        // ...
    };
}
```

### <a name="remarks"></a>Примечания

Тип является перечислимым типом, описывающим объект, который может хранить режим поиска, используемый в качестве аргумента для функций-членов нескольких `iostream` классов. Ниже перечислены значения различных флагов.

- `beg`, чтобы найти (изменить текущее положение чтения или записи) относительно начала последовательности (массива, потока или файла).

- `cur`, чтобы выполнить поиск относительно текущей позицией в последовательности.

- `end`, чтобы выполнить поиск относительно конца последовательности.

### <a name="example"></a>Пример

```cpp
// ios_base_seekdir.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.open( "rm.txt", ios_base::out | ios_base::trunc );

    file << "testing";
    file.seekp( 0, ios_base::beg );
    file << "a";
    file.seekp( 0, ios_base::end );
    file << "a";
}
```

## <a name="setf"></a><a name="setf"></a> setf

Задает указанные флаги.

```cpp
fmtflags setf(
    fmtflags _Mask
);
fmtflags setf(
    fmtflags _Mask,
    fmtflags _Unset
);
```

### <a name="parameters"></a>Параметры

*_Mask*\
Флажки, которые нужно включить.

*_Unset*\
Флаги, которые необходимо отключить.

### <a name="return-value"></a>Возвращаемое значение

Предыдущие флаги формата

### <a name="remarks"></a>Примечания

Первая функция-член фактически вызывает [Флаги](#flags) `(_Mask | _Flags)` (устанавливает выбранные биты), а затем возвращает предыдущие флаги формата. Вторая функция-член фактически вызывает `flags(_Mask & fmtfl, flags & ~_Mask)` (заменяя выбранные биты в маске), а затем возвращает предыдущие флаги формата.

### <a name="example"></a>Пример

```cpp
// ios_base_setf.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    int i = 10;
    cout << i << endl;

    cout.unsetf( ios_base::dec );
    cout.setf( ios_base::hex );
    cout << i << endl;

    cout.setf( ios_base::dec );
    cout << i << endl;
    cout.setf( ios_base::hex, ios_base::dec );
    cout << i << endl;
}
```

## <a name="sync_with_stdio"></a><a name="sync_with_stdio"></a> sync_with_stdio

Гарантирует, что `iostream` и операции с библиотекой времени выполнения C выполняются в том порядке, в котором они отображаются в исходном коде.

```cpp
static bool sync_with_stdio(
   bool _Sync = true
);
```

### <a name="parameters"></a>Параметры

*_Sync*\
Синхронизированы ли все потоки с `stdio` .

### <a name="return-value"></a>Возвращаемое значение

Предыдущий параметр для этой функции.

### <a name="remarks"></a>Примечания

Статическая функция-член сохраняет `stdio` флаг синхронизации, который изначально имеет значение **`true`** . Когда **`true`** этот флаг обеспечивает правильную синхронизацию операций в одном файле между [`iostreams`](../standard-library/iostreams-conventions.md) функциями и теми, которые определены в стандартной библиотеке C++. В противном случае синхронизация может быть гарантирована или не гарантируется, но производительность может быть улучшена. Функция сохраняет *_Sync* в `stdio` флаге синхронизации и возвращает предыдущее сохраненное значение. Его можно вызвать надежно только перед выполнением любых операций со стандартными потоками.

## <a name="unsetf"></a><a name="unsetf"></a> unsetf

Отключает указанные флаги.

```cpp
void unsetf(
   fmtflags _Mask
);
```

### <a name="parameters"></a>Параметры

*_Mask*\
Флаги для сброса в off.

### <a name="remarks"></a>Примечания

Функция-член фактически вызывает [Флаги](#flags)( `~` *_Mask* **& флаги**) (снимите флажки для выбранных битов).

### <a name="example"></a>Пример

Пример использования см. в разделе [ios_base:: setf](#setf) `unsetf` .

## <a name="width"></a><a name="width"></a> Ширина

Задает длину потока вывода.

```cpp
streamsize width( ) const;
streamsize width(
   streamsize _Wide
);
```

### <a name="parameters"></a>Параметры

*_Wide*\
Нужный размер выходного потока.

### <a name="return-value"></a>Возвращаемое значение

Текущее значение ширины.

### <a name="remarks"></a>Примечания

Первая функция – член возвращает ширину сохраненного поля. Вторая функция – член сохраняет *_Wide* в ширине поля и возвращает свое предыдущее сохраненное значение.

### <a name="example"></a>Пример

```cpp
// ios_base_width.cpp
// compile with: /EHsc
#include <iostream>

int main( ) {
    using namespace std;

    cout.width( 20 );
    cout << cout.width( ) << endl;
    cout << cout.width( ) << endl;
}
```

```Output
20
0
```

## <a name="xalloc"></a><a name="xalloc"></a> xalloc

Указывает, что переменная является частью потока.

```cpp
static int xalloc( );
```

### <a name="return-value"></a>Возвращаемое значение

Статическая функция-член возвращает сохраненное статическое значение, которое увеличивается при каждом вызове.

### <a name="remarks"></a>Примечания

Возвращаемое значение можно использовать как аргумент уникального индекса при вызове функций-членов [`iword`](#iword) или [`pword`](#pword) .

### <a name="example"></a>Пример

```cpp
// ios_base_xalloc.cpp
// compile with: /EHsc
// Lets you store user-defined information.
// iword, jword, xalloc
#include <iostream>

int main( )
{
    using namespace std;

    static const int i = ios_base::xalloc();
    static const int j = ios_base::xalloc();
    cout.iword( i ) = 11;
    cin.iword( i ) = 13;
    cin.pword( j ) = "testing";
    cout << cout.iword( i ) << endl;
    cout << cin.iword( i ) << endl;
    cout << ( char * )cin.pword( j ) << endl;
}
```

```Output
11
13
testing
```

## <a name="see-also"></a>См. также раздел

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
