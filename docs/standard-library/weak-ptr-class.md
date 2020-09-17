---
title: Класс weak_ptr
ms.date: 07/29/2019
f1_keywords:
- memory/std::weak_ptr
- memory/std::weak_ptr::element_type
- memory/std::weak_ptr::expired
- memory/std::weak_ptr::lock
- memory/std::weak_ptr::owner_before
- memory/std::weak_ptr::reset
- memory/std::weak_ptr::swap
- memory/std::weak_ptr::use_count
- memory/std::weak_ptr::operator=
helpviewer_keywords:
- std::weak_ptr [C++]
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
ms.openlocfilehash: 5a4989b9ac29e6a35e50479343d6bcf5a39ae1b0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831740"
---
# <a name="weak_ptr-class"></a>Класс weak_ptr

Создает оболочку слабо связанного указателя.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T> class weak_ptr;
```

### <a name="parameters"></a>Параметры

*T*\
Тип, управляемый слабым указателем.

## <a name="remarks"></a>Примечания

Шаблон класса описывает объект, указывающий на ресурс, который управляется одним или несколькими [shared_ptrными](shared-ptr-class.md) объектами. `weak_ptr`Объекты, указывающие на ресурс, не влияют на счетчик ссылок ресурса. Когда `shared_ptr` удаляется последний объект, который управляет этим ресурсом, ресурс будет освобожден, даже если имеются `weak_ptr` объекты, указывающие на этот ресурс. Такое поведение важно для предотвращения циклов в структурах данных.

Объект `weak_ptr` указывает на ресурс, если он был создан из объекта `shared_ptr`, который владеет этим ресурсом; если он был создан из объекта `weak_ptr`, который указывает на этот ресурс; или если этот ресурс был назначен ему с помощью [operator=](#op_eq). `weak_ptr`Объект не предоставляет прямой доступ к ресурсу, на который он указывает. Код, которому необходимо использовать ресурс, делает с это с помощью объекта `shared_ptr`, который владеет этим ресурсом. Этот объект создается функцией-членом [lock](#lock). `weak_ptr`Срок действия объекта истек, когда ресурс, на который он указывает, был освобожден, так как все `shared_ptr` объекты, владеющие этим ресурсом, были уничтожены. Вызов `lock` в объекте `weak_ptr` с истекшим сроком действия создает пустой объект shared_ptr.

Пустой объект weak_ptr не указывает ни на какие ресурсы и не имеет управляющего блока. Его функция-член `lock` возвращает пустой объект shared_ptr.

Цикл происходит, если два или более ресурсов, управляемых объектами `shared_ptr` содержат ссылающиеся друг на друга объекты `shared_ptr`. Например, цикличный связанный список с тремя элементами содержит головной узел `N0`; этот узел включает объект `shared_ptr`, который владеет следующим узлом, `N1`; этот узел содержит объект `shared_ptr`, который владеет следующим узлом, `N2`; этот узел, в свою очередь, содержит объект `shared_ptr`, который владеет головным узлом `N0`, что создает цикл. В этом случае количество ссылок никогда не становится нулевым, а узлы в цикле никогда не освобождаются. Чтобы исключить цикл, последний узел `N2` должен содержать объект `weak_ptr`, указывающий на `N0`, а не объект `shared_ptr`. Поскольку `weak_ptr` объект не владеет `N0` , он не влияет на `N0` счетчик ссылок, а при уничтожении последней ссылки программы на головной узел узлы в списке также будут уничтожены.

## <a name="members"></a>Элементы

|Имя|Описание|
|-|-|
| **Конструкторы** | |
|[weak_ptr](#weak_ptr)|Создает документ `weak_ptr`.|
| **Деструкторы** | |
|[~weak_ptr](#tilde-weak_ptr)|Создает документ `weak_ptr`.|
| **Определения типов** | |
|[element_type](#element_type)|Тип элемента.|
| **Функции элементов** | |
|[expired](#expired)|Проверяет, истек ли срок действия владения.|
|[lock](#lock)|Получает эксклюзивные права владения ресурсом.|
|[owner_before](#owner_before)|Возвращает **`true`** , если этот `weak_ptr` указатель упорядочен до (или меньше) указанного указателя.|
|[reset](#reset)|Освобождает ресурс, которым владеет.|
|[swap](#swap)|Меняет местами два объекта `weak_ptr`.|
|[use_count](#use_count)|Подсчитывает количество `shared_ptr` объектов.|
| **Операторы** | |
|[operator=](#op_eq)|Заменяет ресурс, которым владеет.|

## <a name="element_type"></a><a name="element_type"></a> element_type

Тип элемента.

```cpp
typedef T element_type; // through C++17
using element_type = remove_extent_t<T>; // C++20
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `T`.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_element_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::weak_ptr<int>::element_type val = *wp0.lock();

    std::cout << "*wp0.lock() == " << val << std::endl;

    return (0);
}
```

```Output
*wp0.lock() == 5
```

## <a name="expired"></a><a name="expired"></a> expired

Проверяет, истек ли срок владения, т. е. объект, на который указывает ссылка, удален.

```cpp
bool expired() const noexcept;
```

### <a name="remarks"></a>Примечания

Функция члена возвращает **`true`** , если **`*this`** истек срок действия, в противном случае — **`false`** .

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_expired.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="lock"></a><a name="lock"></a> lock

Получает объект `shared_ptr` , который предоставляет право владения ресурсом.

```cpp
shared_ptr<T> lock() const noexcept;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает пустой объект [shared_ptr](shared-ptr-class.md) , если **`*this`** истек срок действия. в противном случае возвращается `shared_ptr<T>` объект, которому принадлежит ресурс, **`*this`** указывающий на. Возвращает значение, эквивалентное атомарному выполнению `expired() ? shared_ptr<T>() : shared_ptr<T>(*this)` .

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_lock.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="operator"></a><a name="op_eq"></a> operator=

Заменяет ресурс, которым владеет.

```cpp
weak_ptr& operator=(const weak_ptr& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const weak_ptr<Other>& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const shared_ptr<Other>& ptr) noexcept;
```

### <a name="parameters"></a>Параметры

*Other*\
Тип, управляемый общим или слабым указателем аргумента.

*ptr*\
Слабый указатель или общий указатель для копирования.

### <a name="remarks"></a>Примечания

Все операторы освобождают ресурс, на который сейчас указывает, **`*this`** и присваивают ему владение ресурсом с именем *ptr* **`*this`** . Если оператор завершается с ошибкой, он остается **`*this`** неизменным. Каждый оператор имеет результат, эквивалентный `weak_ptr(ptr).swap(*this)` .

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_operator_as.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::shared_ptr<int> sp1(new int(10));
    wp0 = sp1;
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::weak_ptr<int> wp1;
    wp1 = wp0;
    std::cout << "*wp1.lock() == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*wp0.lock() == 5
*wp0.lock() == 10
*wp1.lock() == 10
```

## <a name="owner_before"></a><a name="owner_before"></a> owner_before

Возвращает **`true`** , если этот `weak_ptr` указатель упорядочен до (или меньше) указанного указателя.

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr) const noexcept;

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr) const noexcept;
```

### <a name="parameters"></a>Параметры

*ptr*\
Ссылка lvalue на `shared_ptr` или `weak_ptr` .

### <a name="remarks"></a>Примечания

Функция-член шаблона возвращает **`true`** значение **`*this`** , если упорядочено до *ptr*.

## <a name="reset"></a><a name="reset"></a> reset

Освобождает принадлежащий ресурс.

```cpp
void reset() noexcept;
```

### <a name="remarks"></a>Примечания

Функция члена освобождает ресурс, на который указывает, **`*this`** и преобразует **`*this`** его в пустой `weak_ptr` объект.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp(new int(5));
    std::weak_ptr<int> wp(sp);
    std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    wp.reset();
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    return (0);
}
```

```Output
*wp.lock() == 5
wp.expired() == false
wp.expired() == true
```

## <a name="swap"></a><a name="swap"></a> swap

Меняет местами два объекта `weak_ptr`.

```cpp
void swap(weak_ptr& wp) noexcept;
```

Также включает специализацию:

```cpp
template<class T>
void swap(weak_ptr<T>& a, weak_ptr<T>& b) noexcept;
```

### <a name="parameters"></a>Параметры

*wp*\
Слабый указатель, который будет заменен.

### <a name="remarks"></a>Примечания

После a `swap` ресурс, на который изначально указывает, указывает на **`*this`** *WP*, а ресурс, на который изначально указывает *WP* , указывает **`*this`** . Функция не изменяет счетчики ссылок для этих двух ресурсов и не создает никаких исключений. Результат специализации шаблона эквивалентен `a.swap(b)` .

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="use_count"></a><a name="use_count"></a> use_count

Подсчитывает количество `shared_ptr` объектов, владеющих общим ресурсом.

```cpp
long use_count() const noexcept;
```

### <a name="remarks"></a>Примечания

Функция – член возвращает количество `shared_ptr` объектов, владеющих ресурсом, на который указывает **`*this`** .

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_use_count.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    return (0);
}
```

```Output
wp.use_count() == 1
wp.use_count() == 2
```

## <a name="weak_ptr"></a><a name="weak_ptr"></a> weak_ptr

Создает документ `weak_ptr`.

```cpp
constexpr weak_ptr() noexcept;

weak_ptr(const weak_ptr& wp) noexcept;

weak_ptr(weak_ptr&& wp) noexcept;

template <class Other>
weak_ptr(const weak_ptr<Other>& wp) noexcept;

template <class Other>
weak_ptr(weak_ptr<Other>&& sp) noexcept;

template <class Other>
weak_ptr(const shared_ptr<Other>& sp) noexcept;
```

### <a name="parameters"></a>Параметры

*Other*\
Тип, которым управляет общий или слабый указатель на аргумент. Эти конструкторы не участвуют в разрешении перегрузки, если только _другие \* _ не совместимы с `element_type*` .

*wp*\
Слабый указатель для копирования.

*sp*\
Общий указатель для копирования.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию конструирует пустой `weak_ptr` объект. Конструкторы, принимающие аргумент, каждый из них создают пустой `weak_ptr` объект, если указатель аргумента пуст. В противном случае они создают `weak_ptr` объект, указывающий на ресурс с именем, указанным в аргументе. Счетчик ссылок общего объекта не изменен.

### <a name="example"></a>Пример

```cpp
// std__memory__weak_ptr_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp0;
    std::cout << "wp0.expired() == " << std::boolalpha
        << wp0.expired() << std::endl;

    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp1(sp1);
    std::cout << "*wp1.lock() == "
        << *wp1.lock() << std::endl;

    std::weak_ptr<int> wp2(wp1);
    std::cout << "*wp2.lock() == "
        << *wp2.lock() << std::endl;

    return (0);
}
```

```Output
wp0.expired() == true
*wp1.lock() == 5
*wp2.lock() == 5
```

## <a name="weak_ptr"></a><a name="tilde-weak_ptr"></a> ~weak_ptr

Удаляет `weak_ptr`.

```cpp
~weak_ptr();
```

### <a name="remarks"></a>Примечания

Деструктор уничтожает это, `weak_ptr` но не влияет на счетчик ссылок объекта, на который его хранятся точки указателя.

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](cpp-standard-library-header-files.md)\
[\<memory>](memory.md)\
[Класс shared_ptr](shared-ptr-class.md)
