---
title: необязательный класс
ms.date: 11/04/2016
f1_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
helpviewer_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
ms.openlocfilehash: b1e77325cc485da1caec91316ce5d46cfa6357dc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841939"
---
# <a name="optional-class"></a>необязательный класс

Шаблон класса `optional<T>` описывает объект, который может или не может содержать значение типа `T` , называемое *вложенным значением*.

Если экземпляр `optional<T>` содержит значение, вложенное значение выделяется в пределах хранилища `optional` объекта в области, подходящей по отношению к типу `T` . При `optional<T>` преобразовании в **`bool`** результат принимает **`true`** значение, если объект содержит значения; в противном **`false`** случае —.

Тип вложенного объекта `T` не должен быть [in_place_t](in-place-t-struct.md) или [nullopt_t](nullopt-t-structure.md). `T` должен быть *можно уничтожить*, то есть его деструктор должен освободить все собственные ресурсы и не может вызывать исключения.

`optional`Класс является новым в c++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class optional
{
    using value_type = T;
};

template<class T> optional(T) -> optional<T>;
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
| **Конструкторы и деструктор** | |
|[используемых](#optional) | Создает объект типа `optional`. |
|[~ Необязательный](#optional-destructor) | Уничтожает объект типа `optional` . |
| **Назначение** | |
| [operator=](#op_eq) | Заменяет экземпляр на `optional` копию другого объекта `optional` . |
| [emplace](#op_eq) | Инициализирует содержащееся значение с указанными аргументами. |
| **Позиции** | |
| [swap](#swap) | Меняет местами вложенное значение или пустое состояние на другое `optional` . |
| **Наблюдатели** | |
| [has_value](#has_value) | Возвращает, `optional` содержит ли объект значение. |
| [value](#value) | Возвращает содержащееся значение. |
| [value_or](#value_or) | Возвращает содержащееся значение или альтернативу, если значение отсутствует. |
| [operator->](#op_as) | Ссылается на значение, содержащееся в `optional` объекте. |
| [operator](#op_mem) | Ссылается на значение, содержащееся в `optional` объекте. |
| [operator bool](#op_bool) | Возвращает, `optional` содержит ли объект значение. |
| **Модификаторы** | |
| [reset](#reset) | Сбрасывает объект `optional` , уничтожая любое из содержащихся в нем значений. |

## <a name="has_value"></a><a name="has_value"></a> has_value

```cpp
constexpr bool has_value() const noexcept;
```

## <a name="optional-constructor"></a><a name="optional"></a> Необязательный конструктор

Создает объект типа `optional`.

```cpp
constexpr optional() noexcept;
constexpr optional(nullopt_t nullopt) noexcept;
constexpr optional(const optional& rhs);
constexpr optional(optional&& rhs) noexcept;

template <class... Args>
constexpr explicit optional(in_place_t, Args&&... args);

template <class U, class... Args>
constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);

template <class U = T>
explicit constexpr optional(U&& rhs);

template <class U>
explicit optional(const optional<U>& rhs);

template <class U>
explicit optional(optional<U>&& rhs);
```

### <a name="parameters"></a>Параметры

*RHS*\
Объект `optional` для копирования или перемещения, создающий содержимое, из которого строится значение.

*i_list*\
Список инициализаторов для создания содержащего значения из.

*args*\
Список аргументов для создания содержащего значения из.

### <a name="remarks"></a>Примечания

`constexpr optional() noexcept;`
`constexpr optional(nullopt_t nullopt) noexcept;` Эти конструкторы создают объект `optional` , который не содержит значения.

`constexpr optional(const optional& rhs);` Конструктор копий инициализирует содержащееся значение из содержащегося в аргументе значения. Она определяется как **Удаленная** `is_copy_constructible_v<T>` , если не имеет значения true и является тривиальной, если `is_trivially_copy_constructible_v<T>` имеет значение true.

`constexpr optional(optional&& rhs) noexcept;` Конструктор перемещения инициализирует вложенное значение, перемещая из содержащего его значения аргумента. Он не участвует в разрешении перегрузки `is_move_constructible_v<T>` , если не имеет значение true и является тривиальным, если `is_trivially_move_constructible_v<T>` имеет значение true.

`template <class... Args> constexpr explicit optional(in_place_t, Args&&... args);` Direct инициализирует вложенное значение как при использовании аргументов `std::forward<Args>(args)` . Этот конструктор имеет значение, **`constexpr`** Если `T` используется конструктор **`constexpr`** . Он не участвует в разрешении перегрузки `is_constructible_v<T, Args...>` , если не имеет значение true.

`template <class U, class... Args> constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);` Direct инициализирует вложенное значение как при использовании аргументов `i_list, std::forward<Args>(args)` . Этот конструктор имеет значение, **`constexpr`** Если `T` используется конструктор **`constexpr`** . Он не участвует в разрешении перегрузки `is_constructible_v<T, initializer_list<U>&, Args&&...>` , если не имеет значение true.

`template <class U = T> explicit constexpr optional(U&& rhs);` Direct инициализирует вложенное значение, как при использовании `std::forward<U>(v)` . Этот конструктор имеет значение, **`constexpr`** Если `T` используется конструктор **`constexpr`** . Он не участвует в разрешении перегрузки `is_constructible_v<T, U&&>` , если не имеет значение true, а `is_same_v<remove_cvref_t<U>, in_place_t>` и и имеет `is_same_v<remove_cvref_t<U>, optional>` значение false.

`template <class U> explicit optional(const optional<U>& rhs);` Если *RHS* содержит значение, то прямые инициализируют содержащееся значение из содержащегося в аргументе значения. Он не участвует в разрешении перегрузки, если только `is_constructible_v<T, const U&>` не имеет значение true, а,,,,, `is_constructible_v<T, optional<U>&>` `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_constructible_v<T, const optional<U>&&>` `is_convertible_v<optional<U>&, T>` `is_convertible_v<optional<U>&&, T>` , `is_convertible_v<const optional<U>&, T>` и `is_convertible_v<const optional<U>&&, T>` все равно false.

`template <class U> explicit optional(optional<U>&& rhs);` Если *RHS* содержит значение, то при использовании функции Direct инициализирует содержащееся значение `std::move(*rhs)` . Он не участвует в разрешении перегрузки, если только `is_constructible_v<T, U&&>` не имеет значение true, а,,,,, `is_constructible_v<T, optional<U>&>` `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_constructible_v<T, const optional<U>&&>` `is_convertible_v<optional<U>&, T>` `is_convertible_v<optional<U>&&, T>` , `is_convertible_v<const optional<U>&, T>` и `is_convertible_v<const optional<U>&&, T>` все равно false.

## <a name="optional-destructor"></a><a name="optional-destructor"></a> ~ Необязательный деструктор

Уничтожает любое нетривиальное можно уничтожитьное значение, если оно присутствует, путем вызова его деструктора.

```cpp
~optional();
```

### <a name="remarks"></a>Примечания

Если `T` является тривиальным можно уничтожить, то `optional<T>` он также тривиальным можно уничтожить.

## <a name="operator"></a><a name="op_eq"></a> operator=

Заменяет вложенное значение объекта на `optional` копию или перемещение из другого `optional` содержащего значения.

```cpp
optional& operator=(nullopt_t) noexcept;
optional& operator=(const optional& rhs);
optional& operator=(optional&&) noexcept( /* see below */ );

template <class U = T>
    optional& operator=(U&&);

template <class U>
optional& operator=(const optional<U>&);

template <class U>
    optional& operator=(optional<U>&&);

template <class... Args>
T& emplace(Args&&...);

template <class U, class... Args>
T& emplace(initializer_list<U>, Args&&...);
```

## <a name="operator-"></a><a name="op_as"></a> operator->

Разыменование вложенного значения `optional` объекта.

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

## <a name="operator"></a><a name="op_mem"></a> operator

Разыменование вложенного значения `optional` объекта.

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

## <a name="operator-bool"></a><a name="op_bool"></a> operator bool

Сообщает, `optional` содержит ли объект содержащееся значение.

```cpp
constexpr explicit operator bool() const noexcept;
```

## <a name="reset"></a><a name="reset"></a> reset

Фактически вызывает деструктор вложенного объекта, если он есть, и задает для него неинициализированное состояние.

```cpp
void reset() noexcept;
```

## <a name="swap"></a><a name="swap"></a> swap

```cpp
template<class T>
void swap(optional<T>&, optional<T>&) noexcept;
```

## <a name="value"></a>Значение <a name="value"></a>

```cpp
constexpr const T& value() const&;
constexpr T& value() &;
constexpr T&& value() &&;
constexpr const T&& value() const&&;
```

## <a name="value_or"></a><a name="value_or"></a> value_or

```cpp
template <class U>
    constexpr T value_or(U&&) const&;
template <class U>
    constexpr T value_or(U&&) &&;
```

## <a name="see-also"></a>См. также раздел

[\<optional>](optional.md)
