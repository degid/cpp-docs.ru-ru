---
title: Класс reference_wrapper
ms.date: 11/04/2016
f1_keywords:
- functional/std::reference_wrapper
- type_traits/std::reference_wrapper
- xrefwrap/std::reference_wrapper
- type_traits/std::reference_wrapper::get
- type_traits/std::reference_wrapper::operator()
- functional/std::reference_wrapper::result_type
- functional/std::reference_wrapper::type
- functional/std::reference_wrapper::get
- functional/std::reference_wrapper::operator()
helpviewer_keywords:
- std::reference_wrapper [C++]
- std::reference_wrapper [C++]
- std::reference_wrapper [C++], result_type
- std::reference_wrapper [C++], type
- std::reference_wrapper [C++], get
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
ms.openlocfilehash: 623e1480bdec85120e504c8dc71b28d017c8872a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845072"
---
# <a name="reference_wrapper-class"></a>Класс reference_wrapper

Создает оболочку для ссылки.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
class reference_wrapper
{
    typedef Ty type;

    reference_wrapper(Ty&) noexcept;
    operator Ty&() const noexcept;
    Ty& get() const noexcept;

    template <class... Types>
    auto operator()(Types&&... args) const ->
        decltype(std::invoke(get(), std::forward<Types>(args)...));
};
```

## <a name="remarks"></a>Примечания

`reference_wrapper<Ty>` — это конструируемый и назначаемый копированием класс-оболочка вокруг ссылки на объект или функцию типа `Ty`. Он содержит указатель на объект этого типа. `reference_wrapper` может использоваться для хранения ссылок в стандартных контейнерах и для передачи объектов по ссылке на `std::bind`.

Тип `Ty` должен иметь тип "Объект" или "Функция". В противном случае статическое утверждение во время компиляции завершится ошибкой.

Вспомогательные функции [std::ref](functional-functions.md#ref) и [std::cref](functional-functions.md#cref) можно использовать для создания объектов `reference_wrapper`.

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[reference_wrapper](#reference_wrapper)|Создает документ `reference_wrapper`.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[result_type](#result_type)|Слабый тип результата ссылки в оболочке.|
|[type](#type)|Тип ссылки в оболочке.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[get](#get)|Получает ссылку в оболочке.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[Оператор Ty&amp;](#op_ty_amp)|Получает указатель на ссылку в оболочке.|
|[operator()](#op_call)|Вызывает ссылку в оболочке.|

## <a name="get"></a><a name="get"></a> get

Получает ссылку в оболочке.

```cpp
Ty& get() const noexcept;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку в оболочке.

### <a name="example"></a>Пример

```cpp
// std__functional__reference_wrapper_get.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int main() {
    int i = 1;
    std::reference_wrapper<int> rwi(i);

    std::cout << "i = " << i << std::endl;
    std::cout << "rwi = " << rwi << std::endl;
    rwi.get() = -1;
    std::cout << "i = " << i << std::endl;

    return (0);
}
```

```Output
i = 1
rwi = 1
i = -1
```

## <a name="operator-tyamp"></a><a name="op_ty_amp"></a> Оператор Ty&amp;

Получение ссылки в оболочке.

```cpp
operator Ty&() const noexcept;
```

### <a name="remarks"></a>Примечания

Оператор-член возвращает `*ptr`.

### <a name="example"></a>Пример

```cpp
// std__functional__reference_wrapper_operator_cast.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int main() {
    int i = 1;
    std::reference_wrapper<int> rwi(i);

    std::cout << "i = " << i << std::endl;
    std::cout << "(int)rwi = " << (int)rwi << std::endl;

    return (0);
}
```

```Output
i = 1
(int)rwi = 1
```

## <a name="operator"></a><a name="op_call"></a> operator()

Вызывает ссылку в оболочке.

```cpp
template <class... Types>
auto operator()(Types&&... args);
```

### <a name="parameters"></a>Параметры

*Типов*\
Типы списка аргументов.

*args*\
Список аргументов.

### <a name="remarks"></a>Примечания

Элемент шаблона `operator()` возвращает `std::invoke(get(), std::forward<Types>(args)...)`.

### <a name="example"></a>Пример

```cpp
// std__functional__reference_wrapper_operator_call.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    std::reference_wrapper<int (int)> rwi(neg);

    std::cout << "rwi(3) = " << rwi(3) << std::endl;

    return (0);
}
```

```Output
rwi(3) = -3
```

## <a name="reference_wrapper"></a><a name="reference_wrapper"></a> reference_wrapper

Создает документ `reference_wrapper`.

```cpp
reference_wrapper(Ty& val) noexcept;
```

### <a name="parameters"></a>Параметры

*Ty*\
Тип для упаковки.

*val*\
Значение для упаковки.

### <a name="remarks"></a>Примечания

Конструктор устанавливает сохраненное значение `ptr` в `&val`.

### <a name="example"></a>Пример

```cpp
// std__functional__reference_wrapper_reference_wrapper.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    int i = 1;
    std::reference_wrapper<int> rwi(i);

    std::cout << "i = " << i << std::endl;
    std::cout << "rwi = " << rwi << std::endl;
    rwi.get() = -1;
    std::cout << "i = " << i << std::endl;

    return (0);
}
```

```Output
i = 1
rwi = 1
i = -1
```

## <a name="result_type"></a><a name="result_type"></a> result_type

Слабый тип результата ссылки в оболочке.

```cpp
typedef R result_type;
```

### <a name="remarks"></a>Примечания

Определение типа `result_type` является синонимом слабого типа результата функции в оболочке. Это определение типа имеет смысл только для типов функций.

### <a name="example"></a>Пример

```cpp
// std__functional__reference_wrapper_result_type.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    typedef std::reference_wrapper<int (int)> Mywrapper;
    Mywrapper rwi(neg);
    Mywrapper::result_type val = rwi(3);

    std::cout << "val = " << val << std::endl;

    return (0);
}
```

```Output
val = -3
```

## <a name="type"></a>Тип <a name="type"></a>

Тип ссылки в оболочке.

```cpp
typedef Ty type;
```

### <a name="remarks"></a>Примечания

Определение типа является синонимом параметра шаблона `Ty`.

### <a name="example"></a>Пример

```cpp
// std__functional__reference_wrapper_type.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    int i = 1;
    typedef std::reference_wrapper<int> Mywrapper;
    Mywrapper rwi(i);
    Mywrapper::type val = rwi.get();

    std::cout << "i = " << i << std::endl;
    std::cout << "rwi = " << val << std::endl;

    return (0);
}
```

```Output
i = 1
rwi = 1
```
