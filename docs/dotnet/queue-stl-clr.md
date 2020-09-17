---
title: queue (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::queue
- cliext::queue::assign
- cliext::queue::back
- cliext::queue::back_item
- cliext::queue::const_reference
- cliext::queue::container_type
- cliext::queue::difference_type
- cliext::queue::empty
- cliext::queue::front
- cliext::queue::front_item
- cliext::queue::generic_container
- cliext::queue::generic_value
- cliext::queue::get_container
- cliext::queue::operator=
- cliext::queue::pop
- cliext::queue::push
- cliext::queue::queue
- cliext::queue::reference
- cliext::queue::size
- cliext::queue::size_type
- cliext::queue::to_array
- cliext::queue::value_type
helpviewer_keywords:
- <queue> header [STL/CLR]
- queue class [STL/CLR]
- <cliext/queue> header [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
- assign member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- push member [STL/CLR]
- queue member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
ms.openlocfilehash: ce4b3ca37fc5e13ace3058cb9ec9e9daad073b47
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87210934"
---
# <a name="queue-stlclr"></a>queue (STL/CLR)

Класс шаблона описывает объект, управляющий последовательностью элементов различной длины, которые имеют первый поочередный доступ. Адаптер контейнера используется `queue` для управления базовым контейнером в качестве очереди.

В описании ниже `GValue` то же самое, что и *значение* , если только второй не является ссылочным типом, в этом случае — `Value^` . Точно так `GContainer` же, как и *контейнер* , если только второй не является ссылочным типом, в этом случае это `Container^` .

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Value,
    typename Container>
    ref class queue
        :   public
        System::ICloneable,
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>
    { ..... };
```

### <a name="parameters"></a>Параметры

*Value*<br/>
Тип элемента в управляемой последовательности.

*Контейнер*<br/>
Тип базового контейнера.

## <a name="requirements"></a>Требования

**Заголовок:**\<cliext/queue>

**Пространство имен:** cliext

## <a name="declarations"></a>Объявления

|Определение типа|Описание|
|---------------------|-----------------|
|[queue::const_reference (STL/CLR)](#const_reference)|Тип постоянной ссылки на элемент.|
|[queue::container_type (STL/CLR)](#container_type)|Тип базового контейнера.|
|[queue::difference_type (STL/CLR)](#difference_type)|Тип расстояния со знаком между двумя элементами.|
|[queue::generic_container (STL/CLR)](#generic_container)|Тип универсального интерфейса для адаптера контейнера.|
|[queue::generic_value (STL/CLR)](#generic_value)|Тип элемента для универсального интерфейса для адаптера контейнера.|
|[queue::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|
|[queue::size_type (STL/CLR)](#size_type)|Тип расстояния со знаком между двумя элементами.|
|[queue::value_type (STL/CLR)](#value_type)|Тип элемента.|

|Функция-член|Описание|
|---------------------|-----------------|
|[queue::assign (STL/CLR)](#assign)|Заменяет все элементы.|
|[queue::back (STL/CLR)](#back)|Обращается к последнему элементу.|
|[queue::empty (STL/CLR)](#empty)|Проверяет отсутствие элементов.|
|[queue::front (STL/CLR)](#front)|Обращается к первому элементу.|
|[queue::get_container (STL/CLR)](#get_container)|Осуществляет доступ к базовому контейнеру.|
|[queue::pop (STL/CLR)](#pop)|Удаляет первый элемент.|
|[queue::push (STL/CLR)](#push)|Добавляет новый последний элемент.|
|[queue::queue (STL/CLR)](#queue)|Создает объект контейнера.|
|[queue::size (STL/CLR)](#size)|Подсчитывает количество элементов.|
|[queue::to_array (STL/CLR)](#to_array)|Копирует управляемую последовательность в новый массив.|

|Свойство|Description|
|--------------|-----------------|
|[queue::back_item (STL/CLR)](#back_item)|Обращается к последнему элементу.|
|[queue::front_item (STL/CLR)](#front_item)|Обращается к первому элементу.|

|Оператор|Описание|
|--------------|-----------------|
|[queue::operator= (STL/CLR)](#op_as)|Заменяет управляемую последовательность.|
|[operator!= (очередь) (STL/CLR)](#op_neq)|Определяет `queue` , не равен ли объект другому `queue` объекту.|
|[operator< (Queue) (STL/CLR)](#op_lt)|Определяет `queue` , меньше ли объект, чем другой `queue` объект.|
|[operator<= (Queue) (STL/CLR)](#op_lteq)|Определяет, `queue` является ли объект меньшим или равным другому `queue` объекту.|
|[оператор = = (очередь) (STL/CLR)](#op_eq)|Определяет `queue` , равен ли объект другому `queue` объекту.|
|[operator> (Queue) (STL/CLR)](#op_gt)|Определяет `queue` , больше ли объект, чем другой `queue` объект.|
|[operator>= (queue) (STL/CLR)](#op_gteq)|Определяет `queue` , больше или равен ли объект другому `queue` объекту.|

## <a name="interfaces"></a>Интерфейсы

|Интерфейс|Описание|
|---------------|-----------------|
|<xref:System.ICloneable>|Дублировать объект.|
|икуеуе\<Value, Container>|Поддерживать универсальный адаптер контейнера.|

## <a name="remarks"></a>Примечания

Объект выделяет и освобождает хранилище для последовательности, которая управляется через базовый контейнер типа `Container` , который хранит `Value` элементы и растет по запросу. Объект предоставляет доступ только для того, чтобы просто отправить первый элемент и извлечь последний элемент, реализовать первую очередь в очереди (также называемую очередью FIFO или просто очередью).

## <a name="members"></a>Элементы

## <a name="queueassign-stlclr"></a><a name="assign"></a>Queue:: Assign (STL/CLR)

Заменяет все элементы.

### <a name="syntax"></a>Синтаксис

```cpp
void assign(queue<Value, Container>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Вставляемый адаптер контейнера.

### <a name="remarks"></a>Примечания

Функция члена присваивает `right.get_container()` базовому контейнеру. Он используется для изменения всего содержимого очереди.

### <a name="example"></a>Пример

```cpp
// cliext_queue_assign.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign a repetition of values
    Myqueue c2;
    c2.assign(c1);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="queueback-stlclr"></a><a name="back"></a>очередь:: назад (STL/CLR)

Обращается к последнему элементу.

### <a name="syntax"></a>Синтаксис

```cpp
reference back();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на последний элемент управляемой последовательности, который не должен быть пустым. Он используется для доступа к последнему элементу, если известно, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_queue_back.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("back() = {0}", c1.back());

// alter last item and reinspect
    c1.back() = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back() = c
a b x
```

## <a name="queueback_item-stlclr"></a><a name="back_item"></a>Queue:: back_item (STL/CLR)

Обращается к последнему элементу.

### <a name="syntax"></a>Синтаксис

```cpp
property value_type back_item;
```

### <a name="remarks"></a>Примечания

Свойство обращается к последнему элементу управляемой последовательности, который не должен быть пустым. Он используется для чтения или записи последнего элемента, если известно, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_queue_back_item.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("back_item = {0}", c1.back_item);

// alter last item and reinspect
    c1.back_item = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back_item = c
a b x
```

## <a name="queueconst_reference-stlclr"></a><a name="const_reference"></a>Queue:: const_reference (STL/CLR)

Тип постоянной ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Примечания

Тип описывает константную ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_queue_const_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for (; !c1.empty(); c1.pop())
        {   // get a const reference to an element
        Myqueue::const_reference cref = c1.front();
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="queuecontainer_type-stlclr"></a><a name="container_type"></a>Queue:: container_type (STL/CLR)

Тип базового контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Container value_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Container`.

### <a name="example"></a>Пример

```cpp
// cliext_queue_container_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c" using container_type
    Myqueue::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="queuedifference_type-stlclr"></a><a name="difference_type"></a>очередь: ifference_type:d (STL/CLR)

Типы расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Примечания

Тип описывает возможное число отрицательных элементов.

### <a name="example"></a>Пример

```cpp
// cliext_queue_difference_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute negative difference
    Myqueue::difference_type diff = c1.size();
    c1.push(L'd');
    c1.push(L'e');
    diff -= c1.size();
    System::Console::WriteLine("pushing 2 = {0}", diff);

// compute positive difference
    diff = c1.size();
    c1.pop();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("popping 3 = {0}", diff);
    return (0);
    }
```

```Output
a b c
pushing 2 = -2
popping 3 = 3
```

## <a name="queueempty-stlclr"></a><a name="empty"></a>очередь:: Empty (STL/CLR)

Проверяет отсутствие элементов.

### <a name="syntax"></a>Синтаксис

```cpp
bool empty();
```

### <a name="remarks"></a>Примечания

Эта функция-член возвращает значение true для пустой управляемой последовательности. Он эквивалентен [очереди:: size (STL/CLR)](../dotnet/queue-size-stl-clr.md) `() == 0` . Он используется для проверки, пуста ли очередь.

### <a name="example"></a>Пример

```cpp
// cliext_queue_empty.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

// clear the container and reinspect
    c1.pop();
    c1.pop();
    c1.pop();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="queuefront-stlclr"></a><a name="front"></a>Queue:: Front (STL/CLR)

Обращается к первому элементу.

### <a name="syntax"></a>Синтаксис

```cpp
reference front();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на первый элемент управляемой последовательности, который не должен быть пустым. Он используется для доступа к первому элементу, если известно, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_queue_front.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first item
    System::Console::WriteLine("front() = {0}", c1.front());

// alter first item and reinspect
    c1.front() = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front() = a
x b c
```

## <a name="queuefront_item-stlclr"></a><a name="front_item"></a>Queue:: front_item (STL/CLR)

Обращается к первому элементу.

### <a name="syntax"></a>Синтаксис

```cpp
property value_type front_item;
```

### <a name="remarks"></a>Примечания

Свойство обращается к первому элементу управляемой последовательности, который не должен быть пустым. Он используется для чтения или записи первого элемента, если известно, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_queue_front_item.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("front_item = {0}", c1.front_item);

// alter last item and reinspect
    c1.front_item = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front_item = a
x b c
```

## <a name="queuegeneric_container-stlclr"></a><a name="generic_container"></a>Queue:: generic_container (STL/CLR)

Тип универсального интерфейса для адаптера контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::IQueue<Value>
    generic_container;
```

### <a name="remarks"></a>Примечания

Тип описывает универсальный интерфейс для этого класса адаптера контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_queue_generic_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myqueue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    gc1->push(L'd');
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify original and display generic
    c1.push(L'e');
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c d
a b c d e
```

## <a name="queuegeneric_value-stlclr"></a><a name="generic_value"></a>Queue:: generic_value (STL/CLR)

Тип элемента для использования с универсальным интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Примечания

Тип описывает объект типа `GValue` , описывающий сохраненное значение элемента для использования с универсальным интерфейсом для данного класса контейнера шаблона. (значение `GValue` `value_type` или, `value_type^` Если `value_type` является ссылочным типом.)

### <a name="example"></a>Пример

```cpp
// cliext_queue_generic_value.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get interface to container
    Myqueue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// display in order using generic_value
    for (; !gc1->empty(); gc1->pop())
        {
        Myqueue::generic_value elem = gc1->front();

        System::Console::Write("{0} ", elem);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c
```

## <a name="queueget_container-stlclr"></a><a name="get_container"></a>Queue:: get_container (STL/CLR)

Осуществляет доступ к базовому контейнеру.

### <a name="syntax"></a>Синтаксис

```cpp
container_type^ get_container();
```

### <a name="remarks"></a>Примечания

Функция члена возвращает базовый контейнер. Его можно использовать для обхода ограничений, накладываемых программой-оболочкой контейнера.

### <a name="example"></a>Пример

```cpp
// cliext_queue_get_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="queueoperator-stlclr"></a><a name="op_as"></a>Queue::operator= (STL/CLR)

Заменяет управляемую последовательность.

### <a name="syntax"></a>Синтаксис

```cpp
queue <Value, Container>% operator=(queue <Value, Container>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Копируемый адаптер контейнера.

### <a name="remarks"></a>Примечания

Оператор члена копирует *прямо* в объект, а затем возвращает **`*this`** . Он используется для замены управляемой последовательности копией управляемой последовательности в *правой части*.

### <a name="example"></a>Пример

```cpp
// cliext_queue_operator_as.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2 = c1;
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="queuepop-stlclr"></a><a name="pop"></a>очередь::p op (STL/CLR)

Удаляет последний элемент.

### <a name="syntax"></a>Синтаксис

```cpp
void pop();
```

### <a name="remarks"></a>Примечания

Функция-член удаляет последний элемент управляемой последовательности, который не должен быть пустым. Он используется для сокращения очереди по одному элементу.

### <a name="example"></a>Пример

```cpp
// cliext_queue_pop.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// pop an element and redisplay
    c1.pop();
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
b c
```

## <a name="queuepush-stlclr"></a><a name="push"></a>очередь::p тельную (STL/CLR)

Добавляет новый последний элемент.

### <a name="syntax"></a>Синтаксис

```cpp
void push(value_type val);
```

### <a name="remarks"></a>Примечания

Функция члена добавляет элемент со значением `val` в конце очереди. Он используется для добавления элемента в очередь.

### <a name="example"></a>Пример

```cpp
// cliext_queue_push.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="queuequeue-stlclr"></a><a name="queue"></a>очередь:: очередь (STL/CLR)

Конструирует объект адаптера контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
queue();
queue(queue<Value, Container>% right);
queue(queue<Value, Container>^ right);
explicit queue(container_type% wrapped);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Копируемый объект.

*текание*<br/>
Упакованный контейнер для использования.

### <a name="remarks"></a>Примечания

Конструктор:

`queue();`

создает пустой упакованный контейнер. Он используется для указания пустой начальной управляемой последовательности.

Конструктор:

`queue(queue<Value, Container>% right);`

создает упакованный контейнер, который является копией `right.get_container()` . Он используется для указания начальной управляемой последовательности, которая является копией последовательности, управляемой объектом очереди *вправо*.

Конструктор:

`queue(queue<Value, Container>^ right);`

создает упакованный контейнер, который является копией `right->get_container()` . Он используется для указания начальной управляемой последовательности, которая является копией последовательности, управляемой объектом Queue `*right` .

Конструктор:

`explicit queue(container_type wrapped);`

использует существующий контейнер, *упакованный* в качестве упакованного контейнера. Он используется для создания очереди из существующего контейнера.

### <a name="example"></a>Пример

```cpp
// cliext_queue_construct.cpp
// compile with: /clr
#include <cliext/queue>
#include <cliext/list>

typedef cliext::queue<wchar_t> Myqueue;
typedef cliext::list<wchar_t> Mylist;
typedef cliext::queue<wchar_t, Mylist> Myqueue_list;
int main()
    {
// construct an empty container
    Myqueue c1;
    System::Console::WriteLine("size() = {0}", c1.size());

// construct from an underlying container
    Mylist v2(5, L'x');
    Myqueue_list c2(v2);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    Myqueue_list c3(c2);
    for each (wchar_t elem in c3.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container through handle
    Myqueue_list c4(%c2);
    for each (wchar_t elem in c4.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
x x x x x
x x x x x
x x x x x
```

## <a name="queuereference-stlclr"></a><a name="reference"></a>очередь:: Reference (STL/CLR)

Тип ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Примечания

Тип описывает ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_queue_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify back of queue and redisplay
    Myqueue::reference ref = c1.back();
    ref = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b x
```

## <a name="queuesize-stlclr"></a><a name="size"></a>очередь:: размер (STL/CLR)

Подсчитывает количество элементов.

### <a name="syntax"></a>Синтаксис

```cpp
size_type size();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает длину управляемой последовательности. Он используется для определения количества элементов, находящихся в настоящий момент в управляемой последовательности. Если вас интересует только то, имеет ли последовательность ненулевой размер, см. раздел [queue:: Empty (STL/CLR)](../dotnet/queue-empty-stl-clr.md) `()` .

### <a name="example"></a>Пример

```cpp
// cliext_queue_size.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

// pop an item and reinspect
    c1.pop();
    System::Console::WriteLine("size() = {0} after popping", c1.size());

// add two elements and reinspect
    c1.push(L'a');
    c1.push(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 3 starting with 3
size() = 2 after popping
size() = 4 after adding 2
```

## <a name="queuesize_type-stlclr"></a><a name="size_type"></a>Queue:: size_type (STL/CLR)

Тип расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Примечания

Тип описывает неотрицательное число элементов.

### <a name="example"></a>Пример

```cpp
// cliext_queue_size_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myqueue::size_type diff = c1.size();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("size difference = {0}", diff);
    return (0);
    }
```

```Output
a b c
size difference = 2
```

## <a name="queueto_array-stlclr"></a><a name="to_array"></a>Queue:: to_array (STL/CLR)

Копирует управляемую последовательность в новый массив.

### <a name="syntax"></a>Синтаксис

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>Примечания

Функция члена возвращает массив, содержащий управляемую последовательность. Он используется для получения копии управляемой последовательности в виде массива.

### <a name="example"></a>Пример

```cpp
// cliext_queue_to_array.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.push(L'd');
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// display the earlier array copy
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c d
a b c
```

## <a name="queuevalue_type-stlclr"></a><a name="value_type"></a>Queue:: value_type (STL/CLR)

Тип элемента.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для *значения*параметра шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_queue_value_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display reversed contents " a b c" using value_type
    for (; !c1.empty(); c1.pop())
        {   // store element in value_type object
        Myqueue::value_type val = c1.front();

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operator-queue-stlclr"></a><a name="op_neq"></a>operator!= (очередь) (STL/CLR)

Сравнение очереди не равно.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value,
    typename Container>
    bool operator!=(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `!(left == right)` . Используйте его, чтобы проверить, не упорядочивается ли *Left* *, если две* очереди сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_queue_operator_ne.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] != [a b c] is {0}",
        c1 != c1);
    System::Console::WriteLine("[a b c] != [a b d] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] != [a b c] is False
[a b c] != [a b d] is True
```

## <a name="operatorlt-queue-stlclr"></a><a name="op_lt"></a>Оператор &lt; (Queue) (STL/CLR)

Queue меньше, чем сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value,
    typename Container>
    bool operator<(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает значение true, если для наименьшей позицией, `i` для которой `!(right[i] < left[i])` также задано значение true `left[i] < right[i]` . В противном случае возвращается `left->` [очередь:: size (STL/CLR)](../dotnet/queue-size-stl-clr.md) `() <` `right->size()` , которая используется для проверки того, является ли *Left* упорядоченным до *право* , когда две очереди сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_queue_operator_lt.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] < [a b c] is {0}",
        c1 < c1);
    System::Console::WriteLine("[a b c] < [a b d] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] < [a b c] is False
[a b c] < [a b d] is True
```

## <a name="operatorlt-queue-stlclr"></a><a name="op_lteq"></a>operator &lt; = (очередь) (STL/CLR)

Сравнение "меньше или равно" в очереди.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value,
    typename Container>
    bool operator<=(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `!(right < left)` . Он используется для проверки, не упорядочен ли *Left* после *right* , когда две очереди сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_queue_operator_le.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] <= [a b c] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] <= [a b c] is True
[a b d] <= [a b c] is False
```

## <a name="operator-queue-stlclr"></a><a name="op_eq"></a>оператор = = (очередь) (STL/CLR)

Сравнение постановки в очередь.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value,
    typename Container>
    bool operator==(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает значение true, только если последовательности, управляемые *левым* и *правым* , имеют одинаковую длину и для каждой `i` должности `left[i] ==` `right[i]` . Он используется для проверки, упорядочивается ли *Left* *так, как если* бы две очереди сравнивались по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_queue_operator_eq.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] == [a b c] is {0}",
        c1 == c1);
    System::Console::WriteLine("[a b c] == [a b d] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] == [a b c] is True
[a b c] == [a b d] is False
```

## <a name="operatorgt-queue-stlclr"></a><a name="op_gt"></a>Оператор &gt; (Queue) (STL/CLR)

Очередь больше, чем сравнение.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value,
    typename Container>
    bool operator>(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `right` `<` `left` . Он используется для проверки, упорядочен ли *Left* после *right* , когда две очереди сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_queue_operator_gt.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] > [a b c] is {0}",
        c1 > c1);
    System::Console::WriteLine("[a b d] > [a b c] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] > [a b c] is False
[a b d] > [a b c] is True
```

## <a name="operatorgt-queue-stlclr"></a><a name="op_gteq"></a>operator &gt; = (очередь) (STL/CLR)

Сравнение в очереди больше или равно.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value,
    typename Container>
    bool operator>=(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `!(left < right)` . Он используется для проверки того, не упорядочен ли *Left* до *право* , когда две очереди сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_queue_operator_ge.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] >= [a b c] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] >= [a b c] is True
[a b c] >= [a b d] is False
```
