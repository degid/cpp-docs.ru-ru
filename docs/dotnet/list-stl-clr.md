---
title: list (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::list
- cliext::list::assign
- cliext::list::back
- cliext::list::back_item
- cliext::list::begin
- cliext::list::clear
- cliext::list::const_iterator
- cliext::list::const_reference
- cliext::list::const_reverse_iterator
- cliext::list::difference_type
- cliext::list::empty
- cliext::list::end
- cliext::list::erase
- cliext::list::front
- cliext::list::front_item
- cliext::list::generic_container
- cliext::list::generic_iterator
- cliext::list::generic_reverse_iterator
- cliext::list::generic_value
- cliext::list::insert
- cliext::list::iterator
- cliext::list::list
- cliext::list::merge
- cliext::list::operator=
- cliext::list::pop_back
- cliext::list::pop_front
- cliext::list::push_back
- cliext::list::push_front
- cliext::list::rbegin
- cliext::list::reference
- cliext::list::remove
- cliext::list::remove_if
- cliext::list::rend
- cliext::list::resize
- cliext::list::reverse
- cliext::list::reverse_iterator
- cliext::list::size
- cliext::list::size_type
- cliext::list::sort
- cliext::list::splice
- cliext::list::swap
- cliext::list::to_array
- cliext::list::unique
- cliext::list::value_type
- cliext::operator!=(list)
- cliext::operator<(list)
- cliext::operator<=(list)
- cliext::operator==(list)
- cliext::operator>(list)
- cliext::operator>=(list)
helpviewer_keywords:
- <cliext/list> header [STL/CLR]
- list class [STL/CLR]
- <list> header [STL/CLR]
- assign member [STL/CLR]
- assign member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- erase member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- list member [STL/CLR]
- merge member [STL/CLR]
- operator= member [STL/CLR]
- pop_back member [STL/CLR]
- pop_front member [STL/CLR]
- push_back member [STL/CLR]
- push_front member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- remove member [STL/CLR]
- remove_if member [STL/CLR]
- rend member [STL/CLR]
- resize member [STL/CLR]
- reverse member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- sort member [STL/CLR]
- splice member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- unique member [STL/CLR]
- value_type member [STL/CLR]
- operator!=(list) member [STL/CLR]
- operator<(list) member [STL/CLR]
- operator<=(list) member [STL/CLR]
- operator==(list) member [STL/CLR]
- operator>(list) member [STL/CLR]
- operator>=(list) member [STL/CLR]
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
ms.openlocfilehash: 1c05aff71b16c3edf1348466df325caacb027554
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225635"
---
# <a name="list-stlclr"></a>list (STL/CLR)

Класс шаблона описывает объект, управляющий последовательностью элементов различной длины с двунаправленным доступом. Контейнер используется `list` для управления последовательностью элементов в виде двунаправленного связанного списка узлов, каждый из которых хранит один элемент.

В описании ниже `GValue` то же самое, что и *значение* , если только второй не является ссылочным типом, в этом случае — `Value^` .

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    ref class list
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        Microsoft::VisualC::StlClr::IList<GValue>
    { ..... };
```

### <a name="parameters"></a>Параметры

*Value*<br/>
Тип элемента в управляемой последовательности.

## <a name="requirements"></a>Требования

**Заголовок:**\<cliext/list>

**Пространство имен:** cliext

## <a name="declarations"></a>Объявления

|Определение типа|Описание:|
|---------------------|-----------------|
|[list::const_iterator (STL/CLR)](#const_iterator)|Тип постоянного итератора для управляемой последовательности.|
|[list::const_reference (STL/CLR)](#const_reference)|Тип постоянной ссылки на элемент.|
|[list::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Тип постоянного обратного итератора для управляемой последовательности.|
|[list::difference_type (STL/CLR)](#difference_type)|Тип расстояния со знаком между двумя элементами.|
|[list::generic_container (STL/CLR)](#generic_container)|Тип универсального интерфейса для контейнера.|
|[list::generic_iterator (STL/CLR)](#generic_iterator)|Тип итератора для универсального интерфейса для контейнера.|
|[list::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Тип реверсивного итератора для универсального интерфейса контейнера.|
|[list::generic_value (STL/CLR)](#generic_value)|Тип элемента для универсального интерфейса контейнера.|
|[list::iterator (STL/CLR)](#iterator)|Тип итератора для управляемой последовательности.|
|[list::reference (STL/CLR)](#reference)|Тип ссылки на элемент.|
|[list::reverse_iterator (STL/CLR)](#reverse_iterator)|Тип обратного итератора для управляемой последовательности.|
|[list::size_type (STL/CLR)](#size_type)|Тип расстояния со знаком между двумя элементами.|
|[list::value_type (STL/CLR)](#value_type)|Тип элемента.|

|Функция-член|Описание:|
|---------------------|-----------------|
|[list::assign (STL/CLR)](#assign)|Заменяет все элементы.|
|[list::back (STL/CLR)](#back)|Обращается к последнему элементу.|
|[list::begin (STL/CLR)](#begin)|Задает начало управляемой последовательности.|
|[list::clear (STL/CLR)](#clear)|Удаляет все элементы.|
|[list::empty (STL/CLR)](#empty)|Проверяет отсутствие элементов.|
|[list::end (STL/CLR)](#end)|Задает конец управляемой последовательности.|
|[list::erase (STL/CLR)](#erase)|Удаляет элементы в указанных позициях.|
|[list::front (STL/CLR)](#front)|Обращается к первому элементу.|
|[list::insert (STL/CLR)](#insert)|Добавляет элементы в указанную позиции.|
|[list::list (STL/CLR)](#list)|Создает объект контейнера.|
|[list::merge (STL/CLR)](#merge)|Объединяет две упорядоченные управляемые последовательности.|
|[list::pop_back (STL/CLR)](#pop_back)|Удаляет последний элемент.|
|[list::pop_front (STL/CLR)](#pop_front)|Удаляет первый элемент.|
|[list::push_back (STL/CLR)](#push_back)|Добавляет новый последний элемент.|
|[list::push_front (STL/CLR)](#push_front)|Добавляет новый первый элемент.|
|[list::rbegin (STL/CLR)](#rbegin)|Задает начало обратной управляемой последовательности.|
|[list::remove (STL/CLR)](#remove)|Удаляет элемент с указанным значением.|
|[list::remove_if (STL/CLR)](#remove_if)|Удаляет элементы, которые прошли указанный тест.|
|[list::rend (STL/CLR)](#rend)|Задает конец обратной управляемой последовательности.|
|[list::resize (STL/CLR)](#resize)|Изменяет количество элементов.|
|[list::reverse (STL/CLR)](#reverse)|Изменяет направление управляемой последовательности на противоположную.|
|[list::size (STL/CLR)](#size)|Подсчитывает количество элементов.|
|[list::sort (STL/CLR)](#sort)|Упорядочивает управляемую последовательность.|
|[list::splice (STL/CLR)](#splice)|Восстанавливает ссылки между узлами.|
|[list::swap (STL/CLR)](#swap)|Меняет местами содержимое двух контейнеров.|
|[list::to_array (STL/CLR)](#to_array)|Копирует управляемую последовательность в новый массив.|
|[list::unique (STL/CLR)](#unique)|Удаляет смежные элементы, которые прошли заданный тест.|

|Свойство|Описание:|
|--------------|-----------------|
|[list::back_item (STL/CLR)](#back_item)|Обращается к последнему элементу.|
|[list::front_item (STL/CLR)](#front_item)|Обращается к первому элементу.|

|Оператор|Описание:|
|--------------|-----------------|
|[list::operator= (STL/CLR)](#op_as)|Заменяет управляемую последовательность.|
|[operator!= (list) (STL/CLR)](#op_neq)|Определяет `list` , не равен ли объект другому `list` объекту.|
|[operator< (List) (STL/CLR)](#op_lt)|Определяет `list` , меньше ли объект, чем другой `list` объект.|
|[operator<= (List) (STL/CLR)](#op_lteq)|Определяет, `list` является ли объект меньшим или равным другому `list` объекту.|
|[operator = = (List) (STL/CLR)](#op_eq)|Определяет `list` , равен ли объект другому `list` объекту.|
|[operator> (List) (STL/CLR)](#op_gt)|Определяет `list` , больше ли объект, чем другой `list` объект.|
|[operator>= (List) (STL/CLR)](#op_gteq)|Определяет `list` , больше или равен ли объект другому `list` объекту.|

## <a name="interfaces"></a>Интерфейсы

|Интерфейс|Описание|
|---------------|-----------------|
|<xref:System.ICloneable>|Дублировать объект.|
|<xref:System.Collections.IEnumerable>|Последовательное упорядочение элементов.|
|<xref:System.Collections.ICollection>|Поддержка группы элементов.|
|<xref:System.Collections.Generic.IEnumerable%601>|Последовательность через типизированные элементы.|
|<xref:System.Collections.Generic.ICollection%601>|Поддержание группы типизированных элементов.|
|IList\<Value>|Поддержание универсального контейнера.|

## <a name="remarks"></a>Примечания

Объект выделяет и освобождает хранилище для последовательности, которую он контролирует как отдельные узлы в списке двунаправленных ссылок. Он переупорядочивает элементы, изменяя связи между узлами, не копируя содержимое одного узла в другой. Это означает, что можно свободно вставлять и удалять элементы без нарушения работы остальных элементов. Таким же, список является хорошим кандидатом для базового контейнера для очереди класса шаблона [(STL/CLR)](../dotnet/queue-stl-clr.md) или [стека классов шаблонов (STL/CLR)](../dotnet/stack-stl-clr.md).

`list`Объект поддерживает двунаправленные итераторы. Это означает, что можно пошагово перейти к смежным элементам с помощью итератора, который обозначает элемент в управляемой последовательности. Специальный головной узел соответствует итератору, возвращенному [List:: end (STL/CLR)](../dotnet/list-end-stl-clr.md) `()` . Можно уменьшить этот итератор, чтобы достичь последнего элемента в управляемой последовательности, если он есть. Можно увеличить итератор списка, чтобы достигнуть головного узла, а затем сравнить его со значением `end()` . Но нельзя разыменование итератора, возвращаемого методом `end()` .

Обратите внимание, что нельзя ссылаться на элемент списка напрямую, учитывая его числовое значение, для которого требуется итератор произвольного доступа. Поэтому список *не* может использоваться в качестве базового контейнера для класса шаблона [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).

Итератор списка сохраняет маркер в связанном с ним узле списка, который, в свою очередь, хранит маркер связанного с ним контейнера. Итераторы можно использовать только со связанными объектами контейнера. Итератор списка остается действительным до тех пор, пока связанный с ним узел списка связан с некоторым списком. Более того, допустимый итератор — дереференкабле — вы можете использовать его для доступа к значению элемента, которое он определяет, или изменять его значение, если оно не равно `end()` .

При стирании или удалении элемента вызывается деструктор для его сохраненного значения. При уничтожении контейнера удаляются все элементы. Таким образом, контейнер, тип элемента которого является ссылочным классом, гарантирует, что контейнер не будет находиться ни в одной из элементов. Однако обратите внимание, что контейнер дескрипторов не *уничтожает свои* элементы.

## <a name="members"></a>Элементы

## <a name="listassign-stlclr"></a><a name="assign"></a>List:: Assign (STL/CLR)

Заменяет все элементы.

### <a name="syntax"></a>Синтаксис

```cpp
void assign(size_type count, value_type val);
template<typename InIt>
    void assign(InIt first, InIt last);
void assign(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>Параметры

*count*<br/>
Число элементов для вставки.

*first*<br/>
Начало диапазона для вставки.

*last*<br/>
Конец диапазона для вставки.

*Правильно*<br/>
Перечисление для вставки.

*Val*<br/>
Значение вставляемого элемента.

### <a name="remarks"></a>Примечания

Первая функция-член заменяет управляемую последовательность повторением элементов *Count* в значении *Val*. Он используется для заполнения контейнера всеми элементами, имеющими одинаковое значение.

Если `InIt` является целочисленным типом, вторая функция-член ведет себя так же, как `assign((size_type)first, (value_type)last)` . В противном случае управляемая последовательность заменяется последовательностью [ `first` , `last` ). Он используется для того, чтобы управляемая последовательность скопировала еще одну последовательность.

Третья функция – член заменяет управляемую последовательность на последовательность, обозначенную *правым*перечислителем. Он используется для того, чтобы управляемая последовательность была копией последовательности, описанной перечислителем.

### <a name="example"></a>Пример

```cpp
// cliext_list_assign.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // assign a repetition of values
    cliext::list<wchar_t> c2;
    c2.assign(6, L'x');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign an iterator range
    cliext::list<wchar_t>::iterator it = c1.end();
    c2.assign(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign an enumeration
    c2.assign(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
x x x x x x
a b
a b c
```

## <a name="listback-stlclr"></a><a name="back"></a>List:: Back (STL/CLR)

Обращается к последнему элементу.

### <a name="syntax"></a>Синтаксис

```cpp
reference back();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на последний элемент управляемой последовательности, который не должен быть пустым. Он используется для доступа к последнему элементу, если известно, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_list_back.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("back() = {0}", c1.back());

    // alter last item and reinspect
    c1.back() = L'x';
    for each (wchar_t elem in c1)
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

## <a name="listback_item-stlclr"></a><a name="back_item"></a>List:: back_item (STL/CLR)

Обращается к последнему элементу.

### <a name="syntax"></a>Синтаксис

```cpp
property value_type back_item;
```

### <a name="remarks"></a>Примечания

Свойство обращается к последнему элементу управляемой последовательности, который не должен быть пустым. Он используется для чтения или записи последнего элемента, если известно, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_list_back_item.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("back_item = {0}", c1.back_item);

    // alter last item and reinspect
    c1.back_item = L'x';
    for each (wchar_t elem in c1)
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

## <a name="listbegin-stlclr"></a><a name="begin"></a>List:: Begin (STL/CLR)

Задает начало управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator begin();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает итератор произвольного доступа, который обозначает первый элемент управляемой последовательности или сразу за концом пустой последовательности. Используется для получения итератора, который задает начало управляемой последовательности с параметром `current`, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_list_begin.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    cliext::list<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);

    // alter first two items and reinspect
    *--it = L'x';
    *++it = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*begin() = a
*++begin() = b
x y c
```

## <a name="listclear-stlclr"></a><a name="clear"></a>List:: Clear (STL/CLR)

Удаляет все элементы.

### <a name="syntax"></a>Синтаксис

```cpp
void clear();
```

### <a name="remarks"></a>Примечания

Функция-член фактически вызывает [List:: Erase (STL/CLR)](../dotnet/list-erase-stl-clr.md) `(` [List:: Begin (STL/CLR)](../dotnet/list-begin-stl-clr.md) `(),` [List:: end (STL/CLR)](../dotnet/list-end-stl-clr.md) `())` . Он используется, чтобы гарантировать, что управляемая последовательность пуста.

### <a name="example"></a>Пример

```cpp
// cliext_list_clear.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    // add elements and clear again
    c1.push_back(L'a');
    c1.push_back(L'b');

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 0
a b
size() = 0
```

## <a name="listconst_iterator-stlclr"></a><a name="const_iterator"></a>List:: const_iterator (STL/CLR)

Тип постоянного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает объект неопределенного типа `T2` , который может служить в качестве постоянного итератора произвольного доступа для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_list_const_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    cliext::list<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="listconst_reference-stlclr"></a><a name="const_reference"></a>List:: const_reference (STL/CLR)

Тип постоянной ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Примечания

Тип описывает константную ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_list_const_reference.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    cliext::list<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        cliext::list<wchar_t>::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="listconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>List:: const_reverse_iterator (STL/CLR)

Тип константного реверсивного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает объект неопределенного типа `T4` , который может служить в качестве постоянного реверсивного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_list_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" reversed
    cliext::list<wchar_t>::const_reverse_iterator crit = c1.rbegin();
    cliext::list<wchar_t>::const_reverse_iterator crend = c1.rend();
    for (; crit != crend; ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="listdifference_type-stlclr"></a><a name="difference_type"></a>список::d ifference_type (STL/CLR)

Типы расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Примечания

Тип описывает число подписанных элементов.

### <a name="example"></a>Пример

```cpp
// cliext_list_difference_type.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    cliext::list<wchar_t>::difference_type diff = 0;
    for (cliext::list<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it) ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (cliext::list<wchar_t>::iterator it = c1.end();
        it != c1.begin(); --it) --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="listempty-stlclr"></a><a name="empty"></a>List:: Empty (STL/CLR)

Проверяет отсутствие элементов.

### <a name="syntax"></a>Синтаксис

```cpp
bool empty();
```

### <a name="remarks"></a>Примечания

Эта функция-член возвращает значение true для пустой управляемой последовательности. Он эквивалентен [List:: size (STL/CLR)](../dotnet/list-size-stl-clr.md) `() == 0` . Он используется для проверки, является ли список пустым.

### <a name="example"></a>Пример

```cpp
// cliext_list_empty.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.clear();
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

## <a name="listend-stlclr"></a><a name="end"></a>List:: end (STL/CLR)

Задает конец управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
iterator end();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает итератор произвольного доступа, указывающий сразу за пределы управляемой последовательности. Он используется для получения итератора, который обозначает конец управляемой последовательности. его состояние не изменяется при изменении длины управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_list_end.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    cliext::list<wchar_t>::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);

    // alter first two items and reinspect
    *--it = L'x';
    *++it = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
a x y
```

## <a name="listerase-stlclr"></a><a name="erase"></a>List:: Erase (STL/CLR)

Удаляет элементы в указанных позициях.

### <a name="syntax"></a>Синтаксис

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
```

#### <a name="parameters"></a>Параметры

*first*<br/>
Начало диапазона для стирания.

*last*<br/>
Конец диапазона для стирания.

*where*<br/>
Элемент для стирания.

### <a name="remarks"></a>Примечания

Первая функция члена удаляет элемент управляемой последовательности, на которую указывает, *где*. Он используется для удаления одного элемента.

Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [`first`, `last`). Он используется для удаления непрерывных или более смежных элементов.

Обе функции-члены возвращают итератор, который обозначает первый элемент, оставшийся после удаления элементов, или [List:: end (STL/CLR)](../dotnet/list-end-stl-clr.md) , `()` Если такого элемента не существует.

При удалении элементов число копий элементов линейно в числе элементов между концом очистки и ближайшим концом последовательности. (При удалении одного или нескольких элементов в любом конце последовательности не происходит копирования элементов.)

### <a name="example"></a>Пример

```cpp
// cliext_list_erase.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

    // add elements and display " b c d e"
    c1.push_back(L'd');
    c1.push_back(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase all but end
    cliext::list<wchar_t>::iterator it = c1.end();
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",
        *c1.erase(c1.begin(), --it));
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
erase(begin()) = b
b c d e
erase(begin(), end()-1) = e
size() = 1
```

## <a name="listfront-stlclr"></a><a name="front"></a>List:: Front (STL/CLR)

Обращается к первому элементу.

### <a name="syntax"></a>Синтаксис

```cpp
reference front();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на первый элемент управляемой последовательности, который не должен быть пустым. Он используется для чтения или записи первого элемента, если известно, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_list_front.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first item
    System::Console::WriteLine("front() = {0}", c1.front());

    // alter first item and reinspect
    c1.front() = L'x';
    for each (wchar_t elem in c1)
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

## <a name="listfront_item-stlclr"></a><a name="front_item"></a>List:: front_item (STL/CLR)

Обращается к первому элементу.

### <a name="syntax"></a>Синтаксис

```cpp
property value_type front_item;
```

### <a name="remarks"></a>Примечания

Свойство обращается к первому элементу управляемой последовательности, который не должен быть пустым. Он используется для чтения или записи первого элемента, если известно, что он существует.

### <a name="example"></a>Пример

```cpp
// cliext_list_front_item.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first item
    System::Console::WriteLine("front_item = {0}", c1.front_item);

    // alter first item and reinspect
    c1.front_item = L'x';
    for each (wchar_t elem in c1)
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

## <a name="listgeneric_container-stlclr"></a><a name="generic_container"></a>List:: generic_container (STL/CLR)

Тип универсального интерфейса для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::
    IList<generic_value>
    generic_container;
```

### <a name="remarks"></a>Примечания

Тип описывает универсальный интерфейс для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_list_generic_container.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(gc1->end(), L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.push_back(L'e');

    System::Collections::IEnumerator^ enum1 =
        gc1->GetEnumerator();
    while (enum1->MoveNext())
        System::Console::Write("{0} ", enum1->Current);
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

## <a name="listgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>List:: generic_iterator (STL/CLR)

Тип итератора для использования с универсальным интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает универсальный итератор, который можно использовать с универсальным интерфейсом для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_list_generic_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::list<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a a c
```

## <a name="listgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>List:: generic_reverse_iterator (STL/CLR)

Тип реверсивного итератора для использования с универсальным интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseBidirectionalIterator<generic_value> generic_reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает универсальный обратный итератор, который можно использовать с универсальным интерфейсом для этого класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_list_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::list<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();
    cliext::list<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a c c
```

## <a name="listgeneric_value-stlclr"></a><a name="generic_value"></a>List:: generic_value (STL/CLR)

Тип элемента для использования с универсальным интерфейсом для контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Примечания

Тип описывает объект типа `GValue` , описывающий сохраненное значение элемента для использования с универсальным интерфейсом для данного класса контейнера шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_list_generic_value.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::list<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a a c
```

## <a name="listinsert-stlclr"></a><a name="insert"></a>List:: Insert (STL/CLR)

Добавляет элементы в указанную позиции.

### <a name="syntax"></a>Синтаксис

```cpp
iterator insert(iterator where, value_type val);
void insert(iterator where, size_type count, value_type val);
template<typename InIt>
    void insert(iterator where, InIt first, InIt last);
void insert(iterator where,
    System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>Параметры

*count*<br/>
Число элементов для вставки.

*first*<br/>
Начало диапазона для вставки.

*last*<br/>
Конец диапазона для вставки.

*Правильно*<br/>
Перечисление для вставки.

*Val*<br/>
Значение вставляемого элемента.

*where*<br/>
Место вставки перед контейнером.

### <a name="remarks"></a>Примечания

Каждая из функций-членов вставляет, перед элементом, *на который указывает, в* управляемой последовательности последовательность, указанная оставшимися операндами.

Первая функция члена вставляет элемент со значением *Val* и возвращает итератор, указывающий на вновь вставленный элемент. Он используется для вставки одного элемента перед местом, назначенным итератором.

Вторая функция-член вставляет повторение элементов *Count* в значении *Val*. Он используется для вставки нуль или более непрерывных элементов, которые являются копиями одного и того же значения.

Если `InIt` имеет целочисленный тип, первая функция-член ведет себя так же, как `insert(where, (size_type)first, (value_type)last)`. В противном случае она вставляет последовательность [ `first` , `last` ). Он используется для вставки нуль или более непрерывных элементов, скопированных из другой последовательности.

Четвертая функция с членом вставляет последовательность, обозначенную *справа*. Он используется для вставки последовательности, описанной перечислителем.

При вставке одного элемента количество копий элементов линейно в числе элементов между точкой вставки и ближайшим концом последовательности. (При вставке одного или нескольких элементов в любом конце последовательности не происходит копирования элементов.) Если `InIt` является итератором ввода, третья функция-член фактически выполняет одиночную вставку для каждого элемента последовательности. В противном случае при вставке `N` элементов число копий элементов линейное, `N` а также число элементов между точкой вставки и ближайшим концом последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_list_insert.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value using iterator
    cliext::list<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",
        *c1.insert(++it, L'x'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a repetition of values
    cliext::list<wchar_t> c2;
    c2.insert(c2.begin(), 2, L'y');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an iterator range
    it = c1.end();
    c2.insert(c2.end(), c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an enumeration
    c2.insert(c2.begin(),   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value using index
    it = c2.begin();
    ++it, ++it, ++it;
    c2.insert(it, L'z');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
a b c
insert(begin()+1, L'x') = x
a x b c
y y
y y a x b
a x b c y y a x b
```

## <a name="listiterator-stlclr"></a><a name="iterator"></a>List:: iterator (STL/CLR)

Тип итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает объект неопределенного типа `T1` , который может служить итератором произвольного доступа для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_list_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    cliext::list<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();

    // alter first element and redisplay
    it = c1.begin();
    *it = L'x';
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
x b c
```

## <a name="listlist-stlclr"></a><a name="list"></a>List:: List (STL/CLR)

Создает объект контейнера.

### <a name="syntax"></a>Синтаксис

```cpp
list();
list(list<Value>% right);
list(list<Value>^ right);
explicit list(size_type count);
list(size_type count, value_type val);
template<typename InIt>
    list(InIt first, InIt last);
list(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>Параметры

*count*<br/>
Число элементов для вставки.

*first*<br/>
Начало диапазона для вставки.

*last*<br/>
Конец диапазона для вставки.

*Правильно*<br/>
Объект или диапазон для вставки.

*Val*<br/>
Значение вставляемого элемента.

### <a name="remarks"></a>Примечания

Конструктор:

`list();`

инициализирует управляемую последовательность без элементов. Он используется для указания пустой начальной управляемой последовательности.

Конструктор:

`list(list<Value>% right);`

инициализирует управляемую последовательность с помощью последовательности [ `right.begin()` , `right.end()` ). Он используется для указания начальной управляемой последовательности, которая является копией последовательности, управляемой объектом списка *right*.

Конструктор:

`list(list<Value>^ right);`

инициализирует управляемую последовательность с помощью последовательности [ `right->begin()` , `right->end()` ). Он используется для указания начальной управляемой последовательности, которая является копией последовательности, управляемой объектом списка, маркер которого является *верным*.

Конструктор:

`explicit list(size_type count);`

инициализирует управляемую последовательность с элементами *Count* каждый со значением `value_type()` . Он используется для заполнения контейнера всеми элементами, имеющими значение по умолчанию.

Конструктор:

`list(size_type count, value_type val);`

инициализирует управляемую последовательность с элементами *Count* , каждый из которых имеет значение *Val*. Он используется для заполнения контейнера всеми элементами, имеющими одинаковое значение.

Конструктор:

`template<typename InIt>`

`list(InIt first, InIt last);`

инициализирует управляемую последовательность с помощью последовательности [ `first` , `last` ). Он используется для того, чтобы управляемая последовательность была копией другой последовательности.

Конструктор:

`list(System::Collections::Generic::IEnumerable<Value>^ right);`

инициализирует управляемую последовательность с помощью последовательности, обозначенной *правым*перечислителем. Он используется для того, чтобы управляемая последовательность стала копией другой последовательности, описываемой перечислителем.

### <a name="example"></a>Пример

```cpp
// cliext_list_construct.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
// construct an empty container
    cliext::list<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    // construct with a repetition of default values
    cliext::list<wchar_t> c2(3);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

    // construct with a repetition of values
    cliext::list<wchar_t> c3(6, L'x');
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    cliext::list<wchar_t>::iterator it = c3.end();
    cliext::list<wchar_t> c4(c3.begin(), --it);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    cliext::list<wchar_t> c7(c3);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying a container handle
    cliext::list<wchar_t> c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
size() = 0
0 0 0
x x x x x x
x x x x x
x x x x x x
x x x x x x
x x x x x x
```

## <a name="listmerge-stlclr"></a><a name="merge"></a>List:: Merge (STL/CLR)

Объединяет две упорядоченные управляемые последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
void merge(list<Value>% right);
template<typename Pred2>
    void merge(list<Value>% right, Pred2 pred);
```

#### <a name="parameters"></a>Параметры

*Возможен*<br/>
Компаратор для пар элементов.

*Правильно*<br/>
Контейнер, в котором выполняется слияние.

### <a name="remarks"></a>Примечания

Первая функция – член удаляет все элементы из последовательности, управляемой *вправо* , и вставляет их в управляемую последовательность. Обе последовательности должны быть предварительно упорядочены по `operator<` элементам--элементы не должны уменьшаться в значении по мере выполнения любой последовательности. Результирующая последовательность также упорядочивается по `operator<` . Эта функция-член используется для слияния двух последовательностей, увеличивающихся в последовательности, которые также увеличивают значение.

Вторая функция члена ведет себя так же, как первая, за исключением того, что последовательности упорядочиваются по `pred`  --  `pred(X, Y)` элементам `X` , которые следуют за элементом `Y` последовательности. Он используется для слияния двух последовательностей, упорядоченных с помощью указанной функции предиката или делегата.

Обе функции выполняют стабильное слияние — никакие пары элементов в одной из исходных управляемых последовательностей не меняются в результирующей управляемой последовательности. Кроме того, если пара элементов `X` и `Y` в результирующей управляемой последовательности имеет эквивалентное упорядочение-- `!(X < Y) && !(X < Y)` --, элемент из исходной управляемой последовательности появляется перед элементом из последовательности, управляемой *вправо*.

### <a name="example"></a>Пример

```cpp
// cliext_list_merge.cpp
// compile with: /clr
#include <cliext/list>

typedef cliext::list<wchar_t> Mylist;
int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'c');
    c1.push_back(L'e');

    // display initial contents " a c e"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    cliext::list<wchar_t> c2;
    c2.push_back(L'b');
    c2.push_back(L'd');
    c2.push_back(L'f');

    // display initial contents " b d f"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // merge and display
    cliext::list<wchar_t> c3(c1);
    c3.merge(c2);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("c2.size() = {0}", c2.size());

    // sort descending, merge descending, and redisplay
    c1.sort(cliext::greater<wchar_t>());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    c3.sort(cliext::greater<wchar_t>());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    c3.merge(c1, cliext::greater<wchar_t>());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("c1.size() = {0}", c1.size());
    return (0);
    }
```

```Output
a c e
b d f
a b c d e f
c2.size() = 0
e c a
f e d c b a
f e e d c c b a a
c1.size() = 0
```

## <a name="listoperator-stlclr"></a><a name="op_as"></a>List::operator= (STL/CLR)

Заменяет управляемую последовательность.

### <a name="syntax"></a>Синтаксис

```
list<Value>% operator=(list<Value>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Контейнер для копирования.

### <a name="remarks"></a>Примечания

Оператор члена копирует *прямо* в объект, а затем возвращает **`*this`** . Он используется для замены управляемой последовательности копией управляемой последовательности в *правой части*.

### <a name="example"></a>Пример

```cpp
// cliext_list_operator_as.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
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

## <a name="listpop_back-stlclr"></a><a name="pop_back"></a>список::p op_back (STL/CLR)

Удаляет последний элемент.

### <a name="syntax"></a>Синтаксис

```cpp
void pop_back();
```

### <a name="remarks"></a>Примечания

Функция-член удаляет последний элемент управляемой последовательности, который не должен быть пустым. Он используется для сокращения списка по одному элементу.

### <a name="example"></a>Пример

```cpp
// cliext_list_pop_back.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // pop an element and redisplay
    c1.pop_back();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b
```

## <a name="listpop_front-stlclr"></a><a name="pop_front"></a>список::p op_front (STL/CLR)

Удаляет первый элемент.

### <a name="syntax"></a>Синтаксис

```cpp
void pop_front();
```

### <a name="remarks"></a>Примечания

Функция-член удаляет первый элемент управляемой последовательности, который не должен быть пустым. Он используется для сокращения списка по одному элементу на передний план.

### <a name="example"></a>Пример

```cpp
// cliext_list_pop_front.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // pop an element and redisplay
    c1.pop_front();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
b c
```

## <a name="listpush_back-stlclr"></a><a name="push_back"></a>список::p ush_back (STL/CLR)

Добавляет новый последний элемент.

### <a name="syntax"></a>Синтаксис

```cpp
void push_back(value_type val);
```

### <a name="remarks"></a>Примечания

Функция члена вставляет элемент со значением `val` в конце управляемой последовательности. Его можно использовать для добавления в список другого элемента.

### <a name="example"></a>Пример

```cpp
// cliext_list_push_back.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="listpush_front-stlclr"></a><a name="push_front"></a>список::p ush_front (STL/CLR)

Добавляет новый первый элемент.

### <a name="syntax"></a>Синтаксис

```cpp
void push_front(value_type val);
```

### <a name="remarks"></a>Примечания

Функция члена вставляет элемент со значением `val` в начале управляемой последовательности. Он используется для добавления другого элемента в список.

### <a name="example"></a>Пример

```cpp
// cliext_list_push_front.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_front(L'a');
    c1.push_front(L'b');
    c1.push_front(L'c');

    // display contents " c b a"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="listrbegin-stlclr"></a><a name="rbegin"></a>List:: rbegin (STL/CLR)

Задает начало обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает обратный итератор, обозначающий последний элемент управляемой последовательности или сразу за началом пустой последовательности. Таким образом, он задает для обратной последовательности параметр `beginning`. Используется для получения итератора, который задает начало управляемой последовательности с параметром `current`, отображаемой в обратном порядке, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_list_rbegin.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);

    // alter first two items and reinspect
    *--rit = L'x';
    *++rit = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
a y x
```

## <a name="listreference-stlclr"></a><a name="reference"></a>List:: Reference (STL/CLR)

Тип ссылки на элемент.

### <a name="syntax"></a>Синтаксис

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Примечания

Тип описывает ссылку на элемент.

### <a name="example"></a>Пример

```cpp
// cliext_list_reference.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    cliext::list<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::list<wchar_t>::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();

    // modify contents " a b c"
    for (it = c1.begin(); it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::list<wchar_t>::reference ref = *it;

        ref += (wchar_t)(L'A' - L'a');
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
A B C
```

## <a name="listremove-stlclr"></a><a name="remove"></a>List:: Remove (STL/CLR)

Удаляет элемент с указанным значением.

### <a name="syntax"></a>Синтаксис

```cpp
void remove(value_type val);
```

#### <a name="parameters"></a>Параметры

*Val*<br/>
Значение удаляемого элемента.

### <a name="remarks"></a>Примечания

Функция-член удаляет элемент в управляемой последовательности, для которой `((System::Object^)val)->Equals((System::Object^)x)` имеет значение true (если есть). Он используется для стирания произвольного элемента с указанным значением.

### <a name="example"></a>Пример

```cpp
// cliext_list_remove.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // fail to remove and redisplay
    c1.remove(L'A');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // remove and redisplay
    c1.remove(L'b');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a c
```

## <a name="listremove_if-stlclr"></a><a name="remove_if"></a>List:: remove_if (STL/CLR)

Удаляет элементы, которые прошли указанный тест.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Pred1>
    void remove_if(Pred1 pred);
```

#### <a name="parameters"></a>Параметры

*Возможен*<br/>
Проверка элементов для удаления.

### <a name="remarks"></a>Примечания

Функция-член удаляет из управляемой последовательности (стирает) каждый элемент, `X` для которого `pred(X)` значение равно true. Он используется для удаления всех элементов, которые соответствуют условию, указанному в качестве функции или делегата.

### <a name="example"></a>Пример

```cpp
// cliext_list_remove_if.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'b');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b b b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // fail to remove and redisplay
    c1.remove_if(cliext::binder2nd<cliext::equal_to<wchar_t> >(
        cliext::equal_to<wchar_t>(), L'd'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // remove and redisplay
    c1.remove_if(cliext::binder2nd<cliext::not_equal_to<wchar_t> >(
        cliext::not_equal_to<wchar_t>(), L'b'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b b b c
a b b b c
b b b
```

## <a name="listrend-stlclr"></a><a name="rend"></a>List:: rend (STL/CLR)

Задает конец обратной управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает обратный итератор, указывающий сразу за начало управляемой последовательности. Таким образом, он задает для обратной последовательности параметр `end`. Используется для получения итератора, который задает конец управляемой последовательности с параметром `current`, отображаемой в обратном порядке, однако в случае изменения длины управляемой последовательности его состояние может измениться.

### <a name="example"></a>Пример

```cpp
// cliext_list_rend.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    cliext::list<wchar_t>::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);

    // alter first two items and reinspect
    *--rit = L'x';
    *++rit = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
y x c
```

## <a name="listresize-stlclr"></a><a name="resize"></a>List:: изменение размера (STL/CLR)

Изменяет количество элементов.

### <a name="syntax"></a>Синтаксис

```cpp
void resize(size_type new_size);
void resize(size_type new_size, value_type val);
```

#### <a name="parameters"></a>Параметры

*new_size*<br/>
Новый размер управляемой последовательности.

*Val*<br/>
Значение элемента заполнения.

### <a name="remarks"></a>Примечания

Функции-члены гарантируют, что [List:: size (STL/CLR)](../dotnet/list-size-stl-clr.md) `()` исходя этого возвращает *new_size*. Если необходимо, чтобы управляемая последовательность была длиннее, первая функция члена добавляет элементы со значением `value_type()` , а вторая функция – добавляет элементы со значением *Val*. Чтобы сделать управляемую последовательность короче, обе функции-члены фактически удаляют время последнего элемента [List:: size (STL/CLR)](../dotnet/list-size-stl-clr.md) `() -` `new_size` . Он используется для обеспечения *new_size*размера управляемой последовательности путем усечения или заполнения текущей управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_list_resize.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
// construct an empty container and pad with default values
    cliext::list<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());
    c1.resize(4);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

    // resize to empty
    c1.resize(0);
    System::Console::WriteLine("size() = {0}", c1.size());

    // resize and pad
    c1.resize(5, L'x');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
0 0 0 0
size() = 0
x x x x x
```

## <a name="listreverse-stlclr"></a><a name="reverse"></a>List:: Reverse (STL/CLR)

Изменяет направление управляемой последовательности на противоположную.

### <a name="syntax"></a>Синтаксис

```cpp
void reverse();
```

### <a name="remarks"></a>Примечания

Функция члена изменяет порядок всех элементов в управляемой последовательности на обратный. Он используется для отражения списка элементов.

### <a name="example"></a>Пример

```cpp
// cliext_list_reverse.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // reverse and redisplay
    c1.reverse();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
c b a
```

## <a name="listreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>List:: reverse_iterator (STL/CLR)

Тип обратного итератора для управляемой последовательности.

### <a name="syntax"></a>Синтаксис

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Примечания

Тип описывает объект неопределенного типа `T3` , который может служить в качестве реверсивного итератора для управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_list_reverse_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" reversed
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();

    // alter first element and redisplay
    rit = c1.rbegin();
    *rit = L'x';
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
x b a
```

## <a name="listsize-stlclr"></a><a name="size"></a>List:: size (STL/CLR)

Подсчитывает количество элементов.

### <a name="syntax"></a>Синтаксис

```cpp
size_type size();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает длину управляемой последовательности. Он используется для определения количества элементов, находящихся в настоящий момент в управляемой последовательности. Если вас интересует только то, имеет ли последовательность ненулевой размер, см. раздел [List:: Empty (STL/CLR)](../dotnet/list-empty-stl-clr.md) `()` .

### <a name="example"></a>Пример

```cpp
// cliext_list_size.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.push_back(L'a');
    c1.push_back(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 3 starting with 3
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="listsize_type-stlclr"></a><a name="size_type"></a>List:: size_type (STL/CLR)

Тип расстояния со знаком между двумя элементами.

### <a name="syntax"></a>Синтаксис

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Примечания

Тип описывает неотрицательное число элементов.

### <a name="example"></a>Пример

```cpp
// cliext_list_size_type.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    cliext::list<wchar_t>::size_type diff = 0;
    for (cliext::list<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="listsort-stlclr"></a><a name="sort"></a>List:: Sort (STL/CLR)

Упорядочивает управляемую последовательность.

### <a name="syntax"></a>Синтаксис

```cpp
void sort();
template<typename Pred2>
    void sort(Pred2 pred);
```

#### <a name="parameters"></a>Параметры

*Возможен*<br/>
Компаратор для пар элементов.

### <a name="remarks"></a>Примечания

Первая функция-член переупорядочивает элементы в управляемой последовательности таким образом, чтобы они упорядочивались по `operator<` элементам, не уменьшая значение по мере прохождения последовательности. Эта функция – член используется для сортировки последовательности в порядке возрастания.

Вторая функция-член ведет себя так же, как первая, за исключением того, что последовательность упорядочивается по `pred`  --  `pred(X, Y)` значению false для любого элемента `X` , следующего за элементом `Y` в результирующей последовательности. Он используется для сортировки последовательности в порядке, указанном с помощью функции предиката или делегата.

Обе функции выполняют стабильную сортировку — ни одна пара элементов в исходной управляемой последовательности не изменяется в результирующей управляемой последовательности.

### <a name="example"></a>Пример

```cpp
// cliext_list_sort.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // sort descending and redisplay
    c1.sort(cliext::greater<wchar_t>());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // sort ascending and redisplay
    c1.sort();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
c b a
a b c
```

## <a name="listsplice-stlclr"></a><a name="splice"></a>List:: splice (STL/CLR)

Ресшивка ссылок между узлами.

### <a name="syntax"></a>Синтаксис

```cpp
void splice(iterator where, list<Value>% right);
void splice(iterator where, list<Value>% right,
    iterator first);
void splice(iterator where, list<Value>% right,
    iterator first, iterator last);
```

#### <a name="parameters"></a>Параметры

*first*<br/>
Начало диапазона для объединения.

*last*<br/>
Конец диапазона для объединения.

*Правильно*<br/>
Контейнер, из которого следует присоединиться.

*where*<br/>
Место, где в контейнере следует присоединиться ранее.

### <a name="remarks"></a>Примечания

Первая функция – член вставляет последовательность, управляемую *вправо* перед элементом в управляемой последовательности, на которую указывает, *где*. Он также удаляет все элементы из *правой части*. ( `%right` не должно быть равно **`this`** .) Он используется для объединения всего одного списка в другой.

Вторая функция члена удаляет элемент, на который *указывает, в последовательности,* управляемой *вправо* , и вставляет его перед элементом в управляемой последовательности, на которую указывает, *где*. (Если `where` `==` `first` `||` `where` `== ++first`, изменения не происходят.) Он используется для объединения одного элемента одного списка в другой.

Третья функция-член вставляет поддиапазон, обозначенный [ `first` , `last` ), из последовательности, управляемой *непосредственно* перед элементом в управляемой последовательности, на которую *where*указывает. Он также удаляет исходный поддиапазон из последовательности, управляемой *вправо*. (Если `right == this` , диапазон [ `first` , `last` ) не должен включать элемент, на который указывает, с помощью *WHERE*.) Он используется для объединения вложенной последовательности из одного списка в другой.

### <a name="example"></a>Пример

```cpp
// cliext_list_splice.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // splice to a new list
    cliext::list<wchar_t> c2;
    c2.splice(c2.begin(), c1);
    System::Console::WriteLine("c1.size() = {0}", c1.size());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // return one element
    c1.splice(c1.end(), c2, c2.begin());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // return remaining elements
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("c2.size() = {0}", c2.size());
    return (0);
    }
```

```Output
a b c
c1.size() = 0
a b c
a
b c
b c a
c2.size() = 0
```

## <a name="listswap-stlclr"></a><a name="swap"></a>List:: Swap (STL/CLR)

Меняет местами содержимое двух контейнеров.

### <a name="syntax"></a>Синтаксис

```cpp
void swap(list<Value>% right);
```

#### <a name="parameters"></a>Параметры

*Правильно*<br/>
Контейнер для обмена содержимым.

### <a name="remarks"></a>Примечания

Функция – член меняет местами управляемые последовательности между **`*this`** и *вправо*. Это происходит в постоянном времени и не создает исключений. Он используется в качестве быстрого способа обмена содержимым двух контейнеров.

### <a name="example"></a>Пример

```cpp
// cliext_list_swap.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    cliext::list<wchar_t> c2(5, L'x');
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

## <a name="listto_array-stlclr"></a><a name="to_array"></a>List:: to_array (STL/CLR)

Копирует управляемую последовательность в новый массив.

### <a name="syntax"></a>Синтаксис

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>Примечания

Функция члена возвращает массив, содержащий управляемую последовательность. Он используется для получения копии управляемой последовательности в виде массива.

### <a name="example"></a>Пример

```cpp
// cliext_list_to_array.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.push_back(L'd');
    for each (wchar_t elem in c1)
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

## <a name="listunique-stlclr"></a><a name="unique"></a>List:: Unique (STL/CLR)

Удаляет смежные элементы, которые прошли заданный тест.

### <a name="syntax"></a>Синтаксис

```cpp
void unique();
template<typename Pred2>
    void unique(Pred2 pred);
```

#### <a name="parameters"></a>Параметры

*Возможен*<br/>
Компаратор для пар элементов.

### <a name="remarks"></a>Примечания

Первая функция-член удаляет из управляемой последовательности (стирает) каждый элемент, который сравнивается с предшествующим элементом, если элемент `X` находится перед элементом, `Y` а `X == Y` функция-член удаляется `Y` . Он используется для удаления всех вложенных последовательностей соседних элементов, которые равны, кроме одной копии. Обратите внимание, что если управляемая последовательность упорядочена, например, путем вызова [List:: Sort (STL/CLR)](../dotnet/list-sort-stl-clr.md) `()` , функция-член оставляет только элементы с уникальными значениями. (Поэтому они так и называются.)

Вторая функция члена ведет себя так же, как первая, за исключением того, что она удаляет каждый элемент `Y` после элемента, `X` для которого `pred(X, Y)` . Он используется для удаления всех вложенных последовательностей смежных элементов, которые соответствуют указанной функции предиката или делегата. Обратите внимание, что если управляемая последовательность упорядочена, например, с помощью вызова `sort(pred)` , функция-член оставляет только те элементы, которые не имеют эквивалентного упорядочения с другими элементами.

### <a name="example"></a>Пример

```cpp
// cliext_list_unique.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display contents after unique
    cliext::list<wchar_t> c2(c1);
    c2.unique();
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display contents after unique(not_equal_to)
    c2 = c1;
    c2.unique(cliext::not_equal_to<wchar_t>());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a a b c
a b c
a a
```

## <a name="listvalue_type-stlclr"></a><a name="value_type"></a>List:: value_type (STL/CLR)

Тип элемента.

### <a name="syntax"></a>Синтаксис

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для *значения*параметра шаблона.

### <a name="example"></a>Пример

```cpp
// cliext_list_value_type.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" using value_type
    for (cliext::list<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        {   // store element in value_type object
        cliext::list<wchar_t>::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operator-list-stlclr"></a><a name="op_neq"></a>operator!= (List) (STL/CLR)

Сравнение списка "не равно".

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator!=(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `!(left == right)` . Он используется для проверки того, не упорядочен ли *Left* *так, как если* бы оба списка сравнивались по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_list_operator_ne.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
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

## <a name="operatorlt-list-stlclr"></a><a name="op_lt"></a>Оператор &lt; (List) (STL/CLR)

Сравнение списка "меньше".

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator<(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает значение true, если для наименьшей позицией, `i` для которой `!(right[i] < left[i])` также задано значение true `left[i] < right[i]` . В противном случае он возвращает значение, `left->size() < right->size()` чтобы проверить, упорядочивается ли функция *Left* до *правого* , когда два списка сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_list_operator_lt.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
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

## <a name="operatorlt-list-stlclr"></a><a name="op_lteq"></a>operator &lt; = (List) (STL/CLR)

Сравнение списка "меньше или равно".

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator<=(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `!(right < left)` . Он используется для проверки, не упорядочен ли *Left* после *right* , когда два списка сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_list_operator_le.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
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

## <a name="operator-list-stlclr"></a><a name="op_eq"></a>operator = = (List) (STL/CLR)

Сравнение списка равно.

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator==(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает значение true, только если последовательности, управляемые *левым* и *правым* , имеют одинаковую длину и для каждой `i` должности `left[i] ==` `right[i]` . Он используется для проверки того, упорядочивается ли *Left* *так, как если бы* два списка сравнивались по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_list_operator_eq.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
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

## <a name="operatorgt-list-stlclr"></a><a name="op_gt"></a>Оператор &gt; (List) (STL/CLR)

Список "больше сравнения".

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator>(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `right` `<` `left` . Он используется для проверки, упорядочен ли *Left* после *right* , когда два списка сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_list_operator_gt.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
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

## <a name="operatorgt-list-stlclr"></a><a name="op_gteq"></a>operator &gt; = (List) (STL/CLR)

Сравнение списка "больше или равно".

### <a name="syntax"></a>Синтаксис

```cpp
template<typename Value>
    bool operator>=(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>Параметры

*слева*<br/>
Левый контейнер для сравнения.

*Правильно*<br/>
Правый контейнер для сравнения.

### <a name="remarks"></a>Примечания

Функция оператора возвращает `!(left` `<` `right)` . Он используется для проверки, не упорядочен ли *Left* до *право* , когда два списка сравниваются по элементу.

### <a name="example"></a>Пример

```cpp
// cliext_list_operator_ge.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
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
