---
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: b28f4554610d37b881494748f75499f46cd9e8d9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230237"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

Включает заголовок стандартной библиотеки C \<assert.h> и добавляет связанные имена в `std` пространство имен. Включение этого заголовка гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C, объявляются в `std` пространстве имен.

> [!NOTE]
> \<assert.h>не определяет **`static_assert`** макрос.

## <a name="syntax"></a>Синтаксис

```cpp
#include <cassert>
```

## <a name="macros"></a>Макросы

```cpp
#define assert(E)
```

### <a name="remarks"></a>Примечания

`assert(E)`является константой, только если NDEBUG определен `assert` , где является последним определением или переопределением, или *E* , преобразованное в bool, вычисляется как **`true`** .

## <a name="see-also"></a>См. также раздел

[Макрос assert, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)\
[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
