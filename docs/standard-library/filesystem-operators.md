---
title: Операторы &lt;filesystem&gt;
ms.date: 11/04/2016
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::operator==
- FILESYSTEM/std::experimental::filesystem::operator!=
- FILESYSTEM/std::experimental::filesystem::operator<
- FILESYSTEM/std::experimental::filesystem::operator<=
- FILESYSTEM/std::experimental::filesystem::operator>
- FILESYSTEM/std::experimental::filesystem::operator>=
- FILESYSTEM/std::experimental::filesystem::operator/
- FILESYSTEM/std::experimental::filesystem::operator<<
- FILESYSTEM/std::experimental::filesystem::operator>>
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
ms.openlocfilehash: 819c91e707e50a190aa58eda62f8e07f3451b033
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240730"
---
# <a name="ltfilesystemgt-operators"></a>Операторы &lt;filesystem&gt;

Операторы выполняют лексическое сравнение двух путей как строк. Используйте `equivalent` функцию, чтобы определить, ссылаются ли два пути (например, относительный путь и абсолютный путь) на один и тот же файл или каталог на диске.

Дополнительные сведения см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="operator"></a> operator==

```cpp
bool operator==(const path& left, const path& right) noexcept;
```

Функция возвращает left.native() == right.native().

## <a name="operator"></a> operator!=

```cpp
bool operator!=(const path& left, const path& right) noexcept;
```

Функция возвращает !(left == right).

## <a name="operator"></a> operator<

```cpp
bool operator<(const path& left, const path& right) noexcept;
```

Функция возвращает left.native() < right.native().

## <a name="operator"></a> operator<=

```cpp
bool operator<=(const path& left, const path& right) noexcept;
```

Функция возвращает !(right \< left).

## <a name="operator"></a> operator>

```cpp
bool operator>(const path& left, const path& right) noexcept;
```

Функция возвращает right \< left.

## <a name="operator"></a> operator>=

```cpp
bool operator>=(const path& left, const path& right) noexcept;
```

Функция возвращает !(left < right).

## <a name="operator"></a> operator/

```cpp
path operator/(const path& left, const path& right);
```

Функция выполняет:

```cpp
basic_string<Elem, Traits> str;
path ans = left;
return (ans /= right);
```

## <a name="operator"></a> operator<<

```cpp
template <class Elem, class Traits>
basic_ostream<Elem, Traits>& operator<<(basic_ostream<Elem, Traits>& os, const path& pval);
```

Функция возвращает << pval.string\<Elem, Traits>().

## <a name="operator"></a> operator>>

```cpp
template <class Elem, class Traits>
basic_istream<Elem, Traits>& operator<<(basic_istream<Elem, Traits>& is, const path& pval);
```

Функция выполняет:

```cpp
basic_string<Elem, Traits> str;
is>> str;
pval = str;
return (is);
```
