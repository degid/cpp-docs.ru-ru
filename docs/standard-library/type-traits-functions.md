---
title: Функции &lt;type_traits&gt;
ms.date: 11/04/2016
ms.assetid: dce4492f-f3e4-4d5e-bdb4-5875321254ec
helpviewer_keywords:
- std::is_assignable
- std::is_copy_assignable
- std::is_copy_constructible
- std::is_default_constructible
- std::is_move_assignable
- std::is_move_constructible
- std::is_nothrow_move_assignable
- std::is_trivially_copy_assignable
- std::is_trivially_move_assignable
- std::is_trivially_move_constructible
ms.openlocfilehash: 11defadff0b1785f6e4c5aba6356f7b68a78b9fc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841783"
---
# <a name="lttype_traitsgt-functions"></a>Функции &lt;type_traits&gt;

[is_assignable](#is_assignable)\
[is_copy_assignable](#is_copy_assignable)\
[is_copy_constructible](#is_copy_constructible)\
[is_default_constructible](#is_default_constructible)\
[is_move_assignable](#is_move_assignable)\
[is_move_constructible](#is_move_constructible)\
[is_nothrow_move_assignable](#is_nothrow_move_assignable)\
[is_nothrow_swappable](#is_nothrow_swappable)\
[is_nothrow_swappable_with](#is_nothrow_swappable_with)\
[is_swappable](#is_swappable)\
[is_swappable_with](#is_swappable_with)\
[is_trivially_copy_assignable](#is_trivially_copy_assignable)\
[is_trivially_move_assignable](#is_trivially_move_assignable)\
[is_trivially_move_constructible](#is_trivially_move_constructible)

## <a name="is_assignable"></a><a name="is_assignable"></a> is_assignable

Проверяет, может ли значение *из* типа быть присвоено типу *.*

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Параметры

*Кому*\
Тип объекта, который получает назначение.

*От*\
Тип объекта, который предоставляет значение.

### <a name="remarks"></a>Примечания

Невычисленное выражение `declval<To>() = declval<From>()` должно иметь правильный формат. И *от* , и *до* должны быть полными типами, **`void`** или массивами с неизвестной границей.

## <a name="is_copy_assignable"></a><a name="is_copy_assignable"></a> is_copy_assignable

Проверяет, может ли тип быть скопирован при присвоении значения.

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом с оператором присваивания копии, в противном случае — значение false. Эквивалентно is_assignable \<Ty&, const Ty&> .

## <a name="is_copy_constructible"></a><a name="is_copy_constructible"></a> is_copy_constructible

Проверяет, есть ли у типа конструктор копии.

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом с конструктором копии, в противном случае — значение false.

### <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

struct Copyable
{
    int val;
};

struct NotCopyable
{
   NotCopyable(const NotCopyable&) = delete;
   int val;

};

int main()
{
    std::cout << "is_copy_constructible<Copyable> == " << std::boolalpha
        << std::is_copy_constructible<Copyable>::value << std::endl;
    std::cout << "is_copy_constructible<NotCopyable> == " << std::boolalpha
        << std::is_copy_constructible<NotCopyable>::value << std::endl;

    return (0);
}
```

```Output
is_copy_constructible<Copyable> == true
is_copy_constructible<NotCopyable > == false
```

## <a name="is_default_constructible"></a><a name="is_default_constructible"></a> is_default_constructible

Проверяет, есть ли у типа конструктор по умолчанию.

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>Параметры

*T*\
Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является типом класса с конструктором по умолчанию, в противном случае — значение false. Это эквивалентно предикату `is_constructible<T>`. Тип *T* должен быть полным типом, **`void`** или массивом с неизвестной границей.

### <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

struct Simple
{
    Simple() : val(0) {}
    int val;
};

struct Simple2
{
    Simple2(int v) : val(v) {}
    int val;
};

int main()
{
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha
        << std::is_default_constructible<Simple>::value << std::endl;
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha
        << std::is_default_constructible<Simple2>::value << std::endl;

    return (0);
}
```

```Output
is_default_constructible<Simple> == true
is_default_constructible<Simple2> == false
```

## <a name="is_move_assignable"></a><a name="is_move_assignable"></a> is_move_assignable

Проверяет, является ли тип присваиваемым при перемещении.

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Параметры

*T*\
Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Тип является тип присваиваемым при перемещении, если ссылку rvalue на тип можно присвоить ссылке на тип. Предикат типа эквивалентен `is_assignable<T&, T&&>`. Перемещаемые при присваивании типы включают ссылочные скалярные типы и типы классов, в которых есть созданные компилятором или определяемые пользователем операторы присваивания.

## <a name="is_move_constructible"></a><a name="is_move_constructible"></a> is_move_constructible

Проверяет, имеет ли тип конструктор перемещения.

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Параметры

*T*\
Вычисляемый тип.

### <a name="remarks"></a>Примечания

Предикат типа, который возвращает значение true, если тип *T* может быть создан с помощью операции перемещения. Этот предикат эквивалентен `is_constructible<T, T&&>`.

## <a name="is_nothrow_move_assignable"></a><a name="is_nothrow_move_assignable"></a> is_nothrow_move_assignable

Проверяет, имеет ли тип **`nothrow`** оператор присваивания перемещения.

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* имеет оператор присваивания перемещения, в противном случае — значение false.

## <a name="is_nothrow_swappable"></a><a name="is_nothrow_swappable"></a> is_nothrow_swappable

```cpp
template <class T> struct is_nothrow_swappable;
```

## <a name="is_nothrow_swappable_with"></a><a name="is_nothrow_swappable_with"></a> is_nothrow_swappable_with

```cpp
template <class T, class U> struct is_nothrow_swappable_with;
```

## <a name="is_swappable"></a><a name="is_swappable"></a> is_swappable

```cpp
template <class T> struct is_swappable;
```

## <a name="is_swappable_with"></a><a name="is_swappable_with"></a> is_swappable_with

```cpp
template <class T, class U> struct is_swappable_with;
```

## <a name="is_trivially_copy_assignable"></a><a name="is_trivially_copy_assignable"></a> is_trivially_copy_assignable

Проверяет, есть ли у типа тривиальный оператор присваивания копии.

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Параметры

*T*\
Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является классом, имеющим тривиальный оператор присваивания копии, в противном случае — значение false.

Конструктор присваивания для класса *t* является тривиальным, если он неявно предоставляется, *у класса* *t* нет виртуальных функций, а классы всех нестатических элементов данных типа класса имеют тривиальные операторы присваивания, а классы всех нестатических элементов данных массива типов имеют тривиальные операторы присваивания.

## <a name="is_trivially_move_assignable"></a><a name="is_trivially_move_assignable"></a> is_trivially_move_assignable

Проверяет, есть ли у типа тривиальный оператор присваивания перемещением.

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом, имеющим тривиальный оператор присваивания перемещения, в противном случае — значение false.

Оператор присваивания перемещения для класса *Ty* является тривиальным, если:

он неявно предоставляется;

у класса *Ty* нет виртуальных функций

класс *Ty* не имеет виртуальных базовых классов

классы всех нестатических элементов данных типа класса имеют тривиальные операторы присваивания перемещением;

классы всех нестатических элементов данных массива типов класса имеют тривиальные операторы присваивания перемещением.

## <a name="is_trivially_move_constructible"></a><a name="is_trivially_move_constructible"></a> is_trivially_move_constructible

Проверяет, есть ли у типа тривиальный конструктор перемещения.

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом с тривиальным конструктором перемещения, в противном случае — значение false.

Конструктор перемещения для класса *Ty* является тривиальным, если:

он неявно объявлен;

его типы параметров эквивалентны типам неявного объявления;

у класса *Ty* нет виртуальных функций

класс *Ty* не имеет виртуальных базовых классов

класс не содержит изменчивых нестатических элементов данных;

все прямые базовые классы класса *Ty* имеют тривиальные конструкторы перемещения

классы всех нестатических элементов данных типа класса имеют тривиальные конструкторы перемещения;

классы всех нестатических элементов данных массива типов класса имеют тривиальные конструкторы перемещения.

## <a name="see-also"></a>См. также раздел

[<type_traits>](../standard-library/type-traits.md)
