---
title: Неустранимая ошибка C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 2217b865109cc48151e4e96b2d38b88764c0c64f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203655"
---
# <a name="fatal-error-c1189"></a>Неустранимая ошибка C1189

> **ошибка\#:** *переданное пользователем сообщение об ошибке*

## <a name="remarks"></a>Примечания

C1189 создается директивой `#error`. Разработчик, который кодирует директиву, указывает текст сообщения об ошибке. Дополнительные сведения см. в разделе [директива #error (C++C/)](../../preprocessor/hash-error-directive-c-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C1189. В этом примере разработчик выдает пользовательское сообщение об ошибке, поскольку идентификатор `_WIN32` не определен:

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>См. также раздел

[Директива #define (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
