---
title: Определения типов &lt;streambuf&gt;
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: f08c08de0d6449714f953f5a65fadd2e0279ed44
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843200"
---
# <a name="ltstreambufgt-typedefs"></a>Определения типов &lt;streambuf&gt;

[streambuf](#streambuf)\
[встреамбуф](#wstreambuf)

## <a name="streambuf"></a><a name="streambuf"></a> streambuf

Специализация `basic_streambuf` , которая использует **`char`** в качестве параметров шаблона.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для шаблона класса [basic_streambuf](../standard-library/basic-streambuf-class.md), специализированного для элементов типа **`char`** с признаками символа по умолчанию.

## <a name="wstreambuf"></a><a name="wstreambuf"></a> встреамбуф

Специализация `basic_streambuf` , которая использует **`wchar_t`** в качестве параметров шаблона.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для шаблона класса [basic_streambuf](../standard-library/basic-streambuf-class.md), специализированного для элементов типа **`wchar_t`** с признаками символа по умолчанию.

## <a name="see-also"></a>См. также раздел

[\<streambuf>](../standard-library/streambuf.md)
