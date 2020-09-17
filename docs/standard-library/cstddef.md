---
title: '&lt;cstddef&gt;'
description: Описывает <STDDEF.h>, который гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C, объявляются в `std` пространстве имен.
ms.date: 9/4/2020
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 186de0e893c413a25d31d4f1431c280d749e9541
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040032"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

Включает заголовок стандартной библиотеки C \<stddef.h> и добавляет связанные имена в `std` пространство имен. Включение этого заголовка гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C, объявляются в `std` пространстве имен.

> [!NOTE]
> \<cstddef> включает тип **Byte** и не включает тип **`wchar_t`** .

## <a name="syntax"></a>Синтаксис

```cpp
#include <cstddef>
```

## <a name="namespace-and-macros"></a>Пространство имен и макросы

```cpp
namespace std {
    using ptrdiff_t = see definition;
    using size_t = see definition;
    using max_align_t = see definition;
    using nullptr_t = decltype(nullptr);
}

#define NULL  // an implementation-defined null pointer constant
#define offsetof(type, member-designator)
```

### <a name="parameters"></a>Параметры

*ptrdiff_t*\
Определенный реализацией тип целого числа со знаком, который может содержать разность двух индексов в объекте массива.

*size_t*\
Определяемый реализацией целочисленный тип без знака, достаточно большой для хранения размера в байтах любого объекта.

*max_align_t*\
Тип POD, требование выравнивания которого по крайней мере такой же, как и у каждого скалярного типа, а требования выравнивания поддерживаются в каждом контексте.

*nullptr_t*\
Синоним для типа **`nullptr`** выражения. Хотя **`nullptr`** адрес не может быть получен, можно получить адрес другого *nullptr_t* объекта, который является левосторонним значением.

## <a name="byte-class"></a>Класс Byte

```cpp
enum class byte : unsigned char {};

template <class IntType>
    constexpr byte& operator<<=(byte& b, IntType shift) noexcept;
    constexpr byte operator<<(byte b, IntType shift) noexcept;
    constexpr byte& operator>>=(byte& b, IntType shift) noexcept;
    constexpr byte operator>>(byte b, IntType shift) noexcept;

constexpr byte& operator|=(byte& left, byte right) noexcept;
constexpr byte operator|(byte left, byte right) noexcept;
constexpr byte& operator&=(byte& left, byte right) noexcept;
constexpr byte operator&(byte left, byte right) noexcept;
constexpr byte& operator^=(byte& left, byte right) noexcept;
constexpr byte operator^(byte left, byte right) noexcept;
constexpr byte operator~(byte b) noexcept;

template <class IntType>
    IntType to_integer(byte b) noexcept;
```

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
