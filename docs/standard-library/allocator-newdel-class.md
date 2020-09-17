---
title: Класс allocator_newdel
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- stdext::allocators::allocator_newdel
helpviewer_keywords:
- stdext::allocators [C++], allocator_newdel
- stdext::allocator_newdel
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
ms.openlocfilehash: 30e0f7902a8af435b46aaedf0b38661b7a6604a8
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562601"
---
# <a name="allocator_newdel-class"></a>Класс allocator_newdel

Реализует распределитель, использующий **оператор DELETE** для освобождения блока памяти и **оператора New** для выделения блока памяти.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class allocator_newdel;
```

### <a name="parameters"></a>Параметры

*Type*\
Тип элементов, распределяемых распределителем.

## <a name="remarks"></a>Примечания

Макрос [ALLOCATOR_DECL](allocators-functions.md#allocator_decl) передает этот класс в качестве параметра *Name* в следующей инструкции: `ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`

## <a name="requirements"></a>Требования

**Заголовок:**\<allocators>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также

[\<allocators>](allocators-header.md)
