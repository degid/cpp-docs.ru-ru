---
title: классы is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::is_invocable
- type_traits/std::is_invocable_r
- type_traits/std::is_nothrow_invocable
- type_traits/std::is_nothrow_invocable_r
helpviewer_keywords:
- is_invocable class
- is_invocable
- is_invocable_r class
- is_invocable_r
- is_nothrow_invocable class
- is_nothrow_invocable
- is_nothrow_invocable_r class
- is_nothrow_invocable_r
ms.openlocfilehash: 47801eff0ea0c41c7b69dfb7a1aa5190a43f1b75
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233110"
---
# <a name="is_invocable-is_invocable_r-is_nothrow_invocable-is_nothrow_invocable_r-classes"></a>классы is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r

Эти шаблоны определяют, можно ли вызывать тип с указанными типами аргументов. `is_invocable_r`а `is_nothrow_invocable_r` также определить, будет ли результат вызова преобразован в конкретный тип. `is_nothrow_invocable`а `is_nothrow_invocable_r` также определить, может ли вызов не создавать исключения. Добавлено в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Callable, class... Args>
struct is_invocable;

template <class Convertible, class Callable, class... Args>
struct is_invocable_r;

template <class Callable, class... Args>
struct is_nothrow_invocable;

template <class Convertible, class Callable, class... Args>
struct is_nothrow_invocable_r;

// Helper templates
template <class Callable, class... Args>
inline constexpr bool is_invocable_v =
    std::is_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_invocable_r_v =
    std::is_invocable_r<Convertible, Callable, Args...>::value;

template <class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_v =
    std::is_nothrow_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_r_v =
    std::is_nothrow_invocable_r<Convertible, Callable, Args...>::value;
```

### <a name="parameters"></a>Параметры

*Предназначен*\
Вызываемый тип для запроса.

*Args*\
Типы аргументов для запроса.

*Приведен*\
Тип результата *вызываемого* элемента должен быть преобразован в.

## <a name="remarks"></a>Примечания

`is_invocable`Предикат типа содержит значение true, если *вызываемый* вызываемый тип можно вызвать с *Args* помощью аргументов arguments в невычисленном контексте.

`is_invocable_r`Предикат типа содержит значение true, если *вызываемый* вызываемый тип можно вызвать с *Args* помощью аргументов arguments в неоцененном контексте, чтобы получить тип результата, преобразуемый в *преобразуемое*.

`is_nothrow_invocable`Предикат типа содержит значение true, если *вызываемый* вызываемый тип можно вызвать с *Args* помощью аргументов arguments в неоцененном контексте, и такой вызов не вызывает исключение.

`is_nothrow_invocable_r`Предикат типа содержит значение true, если *вызываемый* вызываемый тип можно вызвать с *Args* помощью аргументов arguments в неоцененном контексте, чтобы получить тип результата *Convertible*, преобразуемый в преобразование, и такой вызов не создает исключение.

Каждый из типов, которые могут быть *преобразованы*, *вызываемые*и типы в аргументах *типа пакета параметров* , должны быть полным типом, массивом неизвестной привязки или, возможно, с указанием ОПС **`void`** . В противном случае поведение предиката не определено.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_invocable.cpp
// compile using: cl /EHsc /std:c++17 std__type_traits__is_invocable.cpp
#include <type_traits>

auto test1(int) noexcept -> int (*)()
{
    return nullptr;
}

auto test2(int) -> int (*)()
{
    return nullptr;
}

int main()
{
    static_assert( std::is_invocable<decltype(test1), short>::value );

    static_assert( std::is_invocable_r<int(*)(), decltype(test1), int>::value );
    static_assert( std::is_invocable_r<long(*)(), decltype(test1), int>::value ); // fails

    static_assert( std::is_nothrow_invocable<decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable<decltype(test2), int>::value ); // fails

    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test2), int>::value ); // fails
}
```

## <a name="requirements"></a>Требования

**Заголовок:**\<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также статью

[<type_traits>](../standard-library/type-traits.md)\
[invoke](functional-functions.md#invoke)
