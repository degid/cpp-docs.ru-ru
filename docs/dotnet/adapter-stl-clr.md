---
title: adapter (STL/CLR)
ms.date: 06/15/2018
ms.topic: reference
f1_keywords:
- <cliext/adapter>
- cliext::collection_adapter
- cliext::collection_adapter::base
- cliext::collection_adapter::begin
- cliext::collection_adapter::collection_adapter
- cliext::collection_adapter::difference_type
- cliext::collection_adapter::end
- cliext::collection_adapter::iterator
- cliext::collection_adapter::key_type
- cliext::collection_adapter::mapped_type
- cliext::collection_adapter::operator=
- cliext::collection_adapter::reference
- cliext::collection_adapter::size
- cliext::collection_adapter::size_type
- cliext::collection_adapter::swap
- cliext::collection_adapter::value_type
- cliext::make_collection
- cliext::range_adapter
- cliext::operator=
- cliext::range_adapter::operator=
- cliext::range_adapter::range_adapter
helpviewer_keywords:
- <adapter> header [STL/CLR]
- adapter [STL/CLR]
- <cliext/adapter> header [STL/CLR]
- collection_adapter class [STL/CLR]
- base member [STL/CLR]
- begin member [STL/CLR]
- collection_adapter member [STL/CLR]
- difference_type member [STL/CLR]
- end member [STL/CLR]
- iterator member [STL/CLR]
- key_type member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- value_type member [STL/CLR]
- make_collection function [STL/CLR]
- range_adapter class [STL/CLR]
- operator= member [STL/CLR]
- range_adapter member [STL/CLR]
ms.assetid: 71ce7e51-42b6-4f70-9595-303791a97677
ms.openlocfilehash: 7730b5a8dbb8c92d85b4c8c5732657d28bf5b229
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216444"
---
# <a name="adapter-stlclr"></a>adapter (STL/CLR)

В заголовке STL/CLR `<cliext/adapter>` указаны два класса шаблонов ( `collection_adapter` и `range_adapter` ) и функция шаблона `make_collection` .

## <a name="syntax"></a>Синтаксис

```cpp
#include <cliext/adapter>
```

## <a name="requirements"></a>Требования

**Заголовок:**\<cliext/adapter>

**Пространство имен:** cliext

## <a name="declarations"></a>Объявления

|Class|Описание:|
|-----------|-----------------|
|[collection_adapter (STL/CLR)](#collection_adapter)|Создает оболочку для коллекции базовых классов (BCL) в виде диапазона.|
|[range_adapter (STL/CLR)](#range_adapter)|Заключает диапазон в оболочку в качестве коллекции BCL.|

|Компонент|Описание|
|--------------|-----------------|
|[make_collection (STL/CLR)](#make_collection)|Создает адаптер диапазона с помощью пары итератора.|

## <a name="members"></a>Элементы

## <a name="collection_adapter-stlclr"></a><a name="collection_adapter"></a>collection_adapter (STL/CLR)

Создает оболочку для коллекции .NET для использования в качестве контейнера STL/CLR. `collection_adapter`— Это класс шаблона, описывающий простой объект контейнера STL/CLR. Он создает оболочку для интерфейса библиотеки базовых классов (BCL) и возвращает пару итераторов, которая используется для управления управляемой последовательностью.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Coll>
    ref class collection_adapter;

template<>
    ref class collection_adapter<
        System::Collections::ICollection>;
template<>
    ref class collection_adapter<
        System::Collections::IEnumerable>;
template<>
    ref class collection_adapter<
        System::Collections::IList>;
template<>
    ref class collection_adapter<
        System::Collections::IDictionary>;
template<typename Value>
    ref class collection_adapter<
        System::Collections::Generic::ICollection<Value>>;
template<typename Value>
    ref class collection_adapter<
        System::Collections::Generic::IEnumerable<Value>>;
template<typename Value>
    ref class collection_adapter<
        System::Collections::Generic::IList<Value>>;
template<typename Key,
    typename Value>
    ref class collection_adapter<
        System::Collections::Generic::IDictionary<Key, Value>>;
```

#### <a name="parameters"></a>Параметры

*Coll*<br/>
Тип упакованной коллекции.

### <a name="specializations"></a>Специализации

|Специализация|Описание|
|--------------------|-----------------|
|IEnumerable|Последовательности через элементы.|
|ICollection|Поддерживает группу элементов.|
|IList|Поддерживает упорядоченную группу элементов.|
|IDictionary|Поддерживать набор пар {ключ, значение}.|
|IEnumerable\<Value>|Последовательности через типизированные элементы.|
|ICollection\<Value>|Поддерживает группу типизированных элементов.|
|IList\<Value>|Поддерживает упорядоченную группу типизированных элементов.|
|IDictionary\<Value> |Поддерживает набор типизированных пар {ключ — значение}.|

### <a name="members"></a>Элементы

|Определение типа|Описание|
|---------------------|-----------------|
|[collection_adapter::difference_type (STL/CLR)](#difference_type)|Тип расстояния со знаком между двумя элементами.|
|[collection_adapter::iterator (STL/CLR)](#iterator)|Тип итератора для управляемой последовательности.|
|[collection_adapter::key_type (STL/CLR)](#key_type)|Тип ключа словаря.|
|[collection_adapter::mapped_type (STL/CLR)](#mapped_type)|Тип значения словаря.|
|[collection_adapter::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|
|[collection_adapter::size_type (STL/CLR)](#size_type)|Тип расстояния со знаком между двумя элементами.|
|[collection_adapter::value_type (STL/CLR)](#value_type)|Тип элемента.|

|Функция-член|Описание|
|---------------------|-----------------|
|[collection_adapter::base (STL/CLR)](#base)|Обозначает инкапсулированный интерфейс BCL.|
|[collection_adapter::begin (STL/CLR)](#begin)|Задает начало управляемой последовательности.|
|[collection_adapter::collection_adapter (STL/CLR)](#collection_adapter_collection_adapter)|Конструирует объект адаптера.|
|[collection_adapter::end (STL/CLR)](#end)|Задает конец управляемой последовательности.|
|[collection_adapter::size (STL/CLR)](#size)|Подсчитывает количество элементов.|
|[collection_adapter::swap (STL/CLR)](#swap)|Меняет местами содержимое двух контейнеров.|

|Оператор|Описание|
|--------------|-----------------|
|[collection_adapter::operator= (STL/CLR)](#op_eq)|Заменяет сохраненный обработчик BCL.|

### <a name="remarks"></a>Примечания

Этот класс шаблона используется для управления контейнером BCL в качестве контейнера STL/CLR. Объект `collection_adapter` хранит обработчик для интерфейса BCL, который, в свою очередь, управляет последовательностью элементов. `collection_adapter`Объект `X` возвращает пару итераторов ввода `X.begin()` и `X.end()` используется для посещения элементов по порядку. Некоторые специализации также позволяют писать, `X.size()` чтобы определить длину управляемой последовательности.

## <a name="collection_adapterbase-stlclr"></a><a name="base"></a>collection_adapter:: Base (STL/CLR)

Обозначает инкапсулированный интерфейс BCL.

### <a name="syntax"></a>Синтаксис

```cpp
Coll^ base();
```

### <a name="remarks"></a>Примечания

Функция – член возвращает сохраненный обработчик интерфейса BCL.

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_base.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
    {
    cliext::deque<wchar_t> d6x(6, L'x');
    Mycoll c1(%d6x);

    // display initial contents "x x x x x x "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("base() same = {0}", c1.base() == %c1);
    return (0);
    }
```

```Output
x x x x x x
base() same = True
```

## <a name="collection_adapterbegin-stlclr"></a><a name="begin"></a>collection_adapter:: Begin (STL/CLR)

Задает начало управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator begin();
```

### <a name="remarks"></a>Примечания

Функция – член возвращает итератор ввода, который обозначает первый элемент управляемой последовательности или сразу за концом пустой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_begin.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Mycoll::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);
    return (0);
}
```

```Output
a b c
*begin() = a
*++begin() = b
```

## <a name="collection_adaptercollection_adapter-stlclr"></a><a name="collection_adapter_collection_adapter"></a>collection_adapter:: collection_adapter (STL/CLR)

Конструирует объект адаптера.

### <a name="syntax"></a>Синтаксис

```cpp
collection_adapter();
collection_adapter(collection_adapter<Coll>% right);
collection_adapter(collection_adapter<Coll>^ right);
collection_adapter(Coll^ collection);
```

#### <a name="parameters"></a>Параметры

*набор*<br/>
Описатель BCL для переноса.

*Правильно*<br/>
Копируемый объект.

### <a name="remarks"></a>Примечания

Конструктор:

`collection_adapter();`

Инициализирует хранимый маркер с **`nullptr`** .

Конструктор:

`collection_adapter(collection_adapter<Coll>% right);`

Инициализирует хранимый маркер `right.` [collection_adapter:: Base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md) `()` .

Конструктор:

`collection_adapter(collection_adapter<Coll>^ right);`

Инициализирует хранимый маркер `right->` [collection_adapter:: Base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md) `()` .

Конструктор:

`collection_adapter(Coll^ collection);`

Инициализирует хранимый маркер с `collection` .

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_construct.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d6x(6, L'x');

    // construct an empty container
    Mycoll c1;
    System::Console::WriteLine("base() null = {0}", c1.base() == nullptr);

    // construct with a handle
    Mycoll c2(%d6x);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Mycoll c3(c2);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying a container handle
    Mycoll c4(%c3);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
}
```

```Output
base() null = True
x x x x x x
x x x x x x
x x x x x x
```

## <a name="collection_adapterdifference_type-stlclr"></a><a name="difference_type"></a>collection_adapter::d ifference_type (STL/CLR)

Типы расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Примечания

Тип описывает число подписанных элементов.

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_difference_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mycoll::difference_type diff = 0;
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
}
```

```Output
a b c
end()-begin() = 3
```

## <a name="collection_adapterend-stlclr"></a><a name="end"></a>collection_adapter:: end (STL/CLR)

Задает конец управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator end();
```

### <a name="remarks"></a>Примечания

Функция – член возвращает итератор ввода, указывающий сразу за пределы управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_end.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="collection_adapteriterator-stlclr"></a><a name="iterator"></a>collection_adapter:: iterator (STL/CLR)

Тип итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает объект неопределенного типа `T1` , который может выступать в качестве итератора ввода для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_iterator.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="collection_adapterkey_type-stlclr"></a><a name="key_type"></a>collection_adapter:: key_type (STL/CLR)

Тип ключа словаря.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона `Key` в специализации для `IDictionary` или `IDictionary<Value>` ; в противном случае он не определен.

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_key_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef cliext::collection_adapter<
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;
int main()
{
    Mymap d1;
    d1.insert(Mymap::make_value(L'a', 1));
    d1.insert(Mymap::make_value(L'b', 2));
    d1.insert(Mymap::make_value(L'c', 3));
    Mycoll c1(%d1);

    // display contents "[a 1] [b 2] [c 3] "
    for each (Mypair elem in c1)
    {
        Mycoll::key_type key = elem.Key;
        Mycoll::mapped_type value = elem.Value;
        System::Console::Write("[{0} {1}] ", key, value);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="collection_adaptermapped_type-stlclr"></a><a name="mapped_type"></a>collection_adapter:: mapped_type (STL/CLR)

Тип значения словаря.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Value mapped_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона `Value` в специализации для `IDictionary` или `IDictionary<Value>` ; в противном случае он не определен.

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_mapped_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef cliext::collection_adapter<
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;
int main()
{
    Mymap d1;
    d1.insert(Mymap::make_value(L'a', 1));
    d1.insert(Mymap::make_value(L'b', 2));
    d1.insert(Mymap::make_value(L'c', 3));
    Mycoll c1(%d1);

    // display contents "[a 1] [b 2] [c 3] "
    for each (Mypair elem in c1)
    {
        Mycoll::key_type key = elem.Key;
        Mycoll::mapped_type value = elem.Value;
        System::Console::Write("[{0} {1}] ", key, value);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="collection_adapteroperator-stlclr"></a><a name="op_eq"></a>collection_adapter::operator= (STL/CLR)

Заменяет сохраненный обработчик BCL.

### <a name="syntax"></a>Синтаксис

```cpp
collection_adapter<Coll>% operator=(collection_adapter<Coll>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Адаптер для копирования.

### <a name="remarks"></a>Примечания

Оператор члена копирует *прямо* в объект, а затем возвращает **`*this`** . Он используется для замены сохраненного обработчика BCL копией сохраненного обработчика BCL в *правой части*.

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_operator_as.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mycoll c2;
    c2 = c1;
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
a b c
```

## <a name="collection_adapterreference-stlclr"></a><a name="reference"></a>collection_adapter:: Reference (STL/CLR)

Тип ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Примечания

Тип описывает ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_reference.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
    {
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
    {   // get a reference to an element
        Mycoll::reference ref = *it;
        System::Console::Write("{0} ", ref);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="collection_adaptersize-stlclr"></a><a name="size"></a>collection_adapter:: size (STL/CLR)

Подсчитывает количество элементов.

### <a name="syntax"></a>Синтаксис

```cpp
size_type size();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает длину управляемой последовательности. Он не определен в специализации для `IEnumerable` или `IEnumerable<Value>` .

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_size.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d6x(6, L'x');
    Mycoll c1(%d6x);

    // display initial contents "x x x x x x "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
}
```

```Output
x x x x x x
size() = 6
```

## <a name="collection_adaptersize_type-stlclr"></a><a name="size_type"></a>collection_adapter:: size_type (STL/CLR)

Тип расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Примечания

Тип описывает неотрицательное число элементов.

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_size_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d6x(6, L'x');
    Mycoll c1(%d6x);

    // display initial contents "x x x x x x"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    Mycoll::size_type size = c1.size();
    System::Console::WriteLine("size() = {0}", size);
    return (0);
}
```

```Output
x x x x x x
size() = 6
```

## <a name="collection_adapterswap-stlclr"></a><a name="swap"></a>collection_adapter:: Swap (STL/CLR)

Меняет местами содержимое двух контейнеров.

### <a name="syntax"></a>Синтаксис

```cpp
void swap(collection_adapter<Coll>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Контейнер для обмена содержимым.

### <a name="remarks"></a>Примечания

Функция – член меняет местами сохраненные дескрипторы BCL между **`*this`** и *right*.

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_swap.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    cliext::deque<wchar_t> d2(5, L'x');
    Mycoll c2(%d2);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
x x x x x
x x x x x
a b c
```

## <a name="collection_adaptervalue_type-stlclr"></a><a name="value_type"></a>collection_adapter:: value_type (STL/CLR)

Тип элемента.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для *значения*параметра шаблона, если он есть в специализации. в противном случае он является синонимом для `System::Object^` .

### <a name="example"></a>Пример

```cpp
// cliext_collection_adapter_value_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display contents "a b c" using value_type
    for (Mycoll::iterator it = c1.begin();
        it != c1.end(); ++it)
    {   // store element in value_type object
        Mycoll::value_type val = *it;

        System::Console::Write("{0} ", val);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="make_collection-stlclr"></a><a name="make_collection"></a>make_collection (STL/CLR)

Сделать `range_adapter` из пары итератора.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Iter>
    range_adapter<Iter> make_collection(Iter first, Iter last);
```

#### <a name="parameters"></a>Параметры

*Iter*<br/>
Тип заключенных в оболочку итераторов.

*first*<br/>
Первый итератор для переноса.

*last*<br/>
Второй итератор для переноса.

### <a name="remarks"></a>Примечания

Функция шаблона возвращает `gcnew range_adapter<Iter>(first, last)`. Он используется для создания `range_adapter<Iter>` объекта из пары итераторов.

### <a name="example"></a>Пример

```cpp
// cliext_make_collection.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::deque<wchar_t> Mycont;
typedef cliext::range_adapter<Mycont::iterator> Myrange;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in d1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Collections::ICollection^ p1 =
        cliext::make_collection(d1.begin(), d1.end());
    System::Console::WriteLine("Count = {0}", p1->Count);
    System::Console::WriteLine("IsSynchronized = {0}",
        p1->IsSynchronized);
    System::Console::WriteLine("SyncRoot not nullptr = {0}",
        p1->SyncRoot != nullptr);

    // copy the sequence
    cli::array<System::Object^>^ a1 = gcnew cli::array<System::Object^>(5);

    a1[0] = L'|';
    p1->CopyTo(a1, 1);
    a1[4] = L'|';
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
}
```

```Output
a b c
Count = 3
IsSynchronized = False
SyncRoot not nullptr = True
| a b c |
```

## <a name="range_adapter-stlclr"></a><a name="range_adapter"></a>range_adapter (STL/CLR)

Класс шаблона, который служит оболочкой для пары итераторов, используемых для реализации нескольких интерфейсов библиотеки базовых классов (BCL). Используйте range_adapter для управления диапазоном STL/CLR, как если бы он был коллекцией BCL.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Iter>
    ref class range_adapter
        :   public
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<Value>,
        System::Collections::Generic::ICollection<Value>
    { ..... };
```

#### <a name="parameters"></a>Параметры

*Iter*<br/>
Тип, связанный с заключенными в оболочку итераторами.

### <a name="members"></a>Элементы

|Функция-член|Описание|
|---------------------|-----------------|
|[range_adapter::range_adapter (STL/CLR)](#range_adapter_range_adapter)|Конструирует объект адаптера.|

|Оператор|Описание|
|--------------|-----------------|
|[range_adapter::operator= (STL/CLR)](#range_adapter_op_eq)|Заменяет сохраненную пару итераторов.|

### <a name="interfaces"></a>Интерфейсы

|Интерфейс|Описание|
|---------------|-----------------|
|<xref:System.Collections.IEnumerable>|Выполняет перебор элементов в коллекции.|
|<xref:System.Collections.ICollection>|Поддерживает группу элементов.|
|<xref:System.Collections.Generic.IEnumerable%601>|Выполняет перебор типизированных элементов в коллекции.|
|<xref:System.Collections.Generic.ICollection%601>|Поддерживает группу типизированных элементов.|

### <a name="remarks"></a>Примечания

Range_adapter хранит пару итераторов, которые, в свою очередь, разделяют последовательность элементов. Объект реализует четыре интерфейса BCL, которые позволяют выполнять итерацию по элементам по порядку. Этот класс шаблона используется для управления диапазонами STL/CLR практически подобно контейнерам BCL.

## <a name="range_adapteroperator-stlclr"></a><a name="range_adapter_op_eq"></a>range_adapter::operator= (STL/CLR)

Заменяет сохраненную пару итераторов.

### <a name="syntax"></a>Синтаксис

```cpp
range_adapter<Iter>% operator=(range_adapter<Iter>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Адаптер для копирования.

### <a name="remarks"></a>Примечания

Оператор члена копирует *прямо* в объект, а затем возвращает **`*this`** . Его можно использовать для замены хранимой пары итератора копией сохраненной пары итератора в *правой части*.

### <a name="example"></a>Пример

```cpp
// cliext_range_adapter_operator_as.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::deque<wchar_t> Mycont;
typedef cliext::range_adapter<Mycont::iterator> Myrange;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Myrange c1(d1.begin(), d1.end());

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Myrange c2;
    c2 = c1;
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
a b c
```

## <a name="range_adapterrange_adapter-stlclr"></a><a name="range_adapter_range_adapter"></a>range_adapter:: range_adapter (STL/CLR)

Конструирует объект адаптера.

### <a name="syntax"></a>Синтаксис

```cpp
range_adapter();
range_adapter(range_adapter<Iter>% right);
range_adapter(range_adapter<Iter>^ right);
range_adapter(Iter first, Iter last);
```

#### <a name="parameters"></a>Параметры

*first*<br/>
Первый итератор для переноса.

*last*<br/>
Второй итератор для переноса.

*Правильно*<br/>
Копируемый объект.

### <a name="remarks"></a>Примечания

Конструктор:

`range_adapter();`

Инициализирует хранимую пару итераторов с созданными по умолчанию итераторами.

Конструктор:

`range_adapter(range_adapter<Iter>% right);`

Инициализирует хранимую пару итераторов путем копирования пары, сохраненной в *правой части*.

Конструктор:

`range_adapter(range_adapter<Iter>^ right);`

Инициализирует хранимую пару итераторов путем копирования пары, хранящейся в `*right` .

Конструктор:

`range_adapter(Iter^ first, last);`

Инициализирует хранимую пару итератора *первой* и *последней*.

### <a name="example"></a>Пример

```cpp
// cliext_range_adapter_construct.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::deque<wchar_t> Mycont;
typedef cliext::range_adapter<Mycont::iterator> Myrange;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');

    // construct an empty adapter
    Myrange c1;

    // construct with an iterator pair
    Myrange c2(d1.begin(), d1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another adapter
    Myrange c3(c2);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying an adapter handle
    Myrange c4(%c3);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
}
```

```Output
a b c
a b c
a b c
```
