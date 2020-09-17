---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: 73de3c2d19063f0738b8b0a3c510ea520f58de0b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745060"
---
# <a name="_com_ptr_trelease"></a>_com_ptr_t::Release

**Microsoft Специфический**

Вызывает **Release** функцию участника `IUnknown` выпуска на инкапсулированном указателе интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
void Release( );
```

## <a name="remarks"></a>Примечания

Вызовы `IUnknown::Release` на инкапсулированный указатель `E_POINTER` интерфейса, поднимая ошибку, если этот указатель интерфейса NULL.

**END Microsoft Специфический**

## <a name="see-also"></a>См. также раздел

[класс _com_ptr_t](../cpp/com-ptr-t-class.md)
