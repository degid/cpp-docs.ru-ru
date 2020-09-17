---
title: or_eq
ms.date: 11/04/2016
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- std::or_eq
- or_eq
- std.or_eq
helpviewer_keywords:
- or_eq function
ms.assetid: 1eb92464-ed58-40d8-a30e-f0a6aa2f4318
ms.openlocfilehash: 3c651cb75fa7628918bc8b5ebbcd4b31f9b583df
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170167"
---
# <a name="or_eq"></a>or_eq

Альтернатива оператору &#124;=.

## <a name="syntax"></a>Синтаксис

```C

#define or_eq |=
```

## <a name="remarks"></a>Примечания

Макрос создает оператор &#124;=.

## <a name="example"></a>Пример

```cpp
// iso646_oreq.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 3, b = 2, result;

   result= a |= b;
   cout << result << endl;

   result= a or_eq b;
   cout << result << endl;
}
```

```Output
3
3
```

## <a name="requirements"></a>Требования

**Заголовок:** \<iso646.h >
