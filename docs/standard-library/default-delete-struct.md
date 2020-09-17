---
title: Структура default_delete
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: 8baa9f5d294cf083fd55414cd529e438f328d1a1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845085"
---
# <a name="default_delete-struct"></a>Структура default_delete

Стандартный объект функции, который выполняет операцию деления ( `operator/` ) в своих аргументах.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
    struct default_delete
```

## <a name="requirements"></a>Требования

**Заголовок:**\<memory>

**Пространство имен:** std

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[default_delete](#default_delete)|Конструктор для объектов типа `default_delete`.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator()](#op_paren)|Ссылочный оператор для доступа `default_delete` .|

## <a name="default_delete"></a><a name="default_delete"></a> default_delete

Конструктор для объектов типа `default_delete`.

```cpp
constexpr default_delete() noexcept = default;
template <class U>
    default_delete(const default_delete<U>&) noexcept;
```

## <a name="operator"></a><a name="op_paren"></a> operator()

Ссылочный оператор для доступа `default_delete` .

```cpp
void operator()(T*) const;
```

## <a name="see-also"></a>См. также раздел

[\<memory>](../standard-library/memory.md)
