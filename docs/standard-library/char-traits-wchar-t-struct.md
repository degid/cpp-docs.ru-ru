---
title: Структура char_traits&lt;wchar_t&gt;
ms.date: 11/04/2016
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
ms.openlocfilehash: 3b2504dbb124ccca7f9b27619585abb2b5795f92
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219174"
---
# <a name="char_traitsltwchar_tgt-struct"></a>Структура char_traits&lt;wchar_t&gt;

Класс, являющийся специализацией структуры шаблона, **char_traits \<CharType> ** элементу типа **`wchar_t`** .

## <a name="syntax"></a>Синтаксис

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>Примечания

Специализация позволяет структуре использовать преимущества библиотечных функций, которые управляют объектами этого типа **`wchar_t`** .

## <a name="requirements"></a>Требования

**Заголовок:**\<string>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[Структура char_traits](../standard-library/char-traits-struct.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
