---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: 60ad1c1bd95eb35f2a4f2800f79d0326c68a1176
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745846"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**Microsoft Специфический**

Присваивает строку данному объекту `_variant_t`.

## <a name="syntax"></a>Синтаксис

```cpp
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>Параметры

*Psrc*<br/>
Указатель на строку знаков.

## <a name="remarks"></a>Примечания

Преобразует символьную строку ANSI в строку `BSTR` Юникода и присваивает ее данному объекту `_variant_t`.

**END Microsoft Специфический**

## <a name="see-also"></a>См. также раздел

[класс _variant_t](../cpp/variant-t-class.md)
