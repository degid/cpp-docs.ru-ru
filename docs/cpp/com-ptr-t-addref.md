---
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 4dcf643357c9b368d4b2ea3bc51e6567acf45a44
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745102"
---
# <a name="_com_ptr_taddref"></a>_com_ptr_t::AddRef

**Microsoft Специфический**

Вызывает `AddRef` функцию `IUnknown` члена на инкапсулированном указателе интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
void AddRef( );
```

## <a name="remarks"></a>Примечания

Вызовы `IUnknown::AddRef` на инкапсулированный указатель `E_POINTER` интерфейса, поднимая ошибку, если указатель NULL.

**END Microsoft Специфический**

## <a name="see-also"></a>См. также раздел

[класс _com_ptr_t](../cpp/com-ptr-t-class.md)
