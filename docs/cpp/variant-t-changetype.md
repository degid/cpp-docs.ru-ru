---
title: _variant_t::ChangeType
ms.date: 11/04/2016
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
ms.openlocfilehash: c2283158856a6781ab2e12c51f4e2ad0e4f1d531
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750732"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**Microsoft Специфический**

Изменяет тип `_variant_t` объекта на `VARTYPE`указанный .

## <a name="syntax"></a>Синтаксис

```cpp
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>Параметры

*вартип*<br/>
Для `VARTYPE` этого `_variant_t` объекта.

*Psrc*<br/>
Указатель на объект `_variant_t`, который необходимо преобразовать. Если это значение NULL, конверсия выполняется на месте.

## <a name="remarks"></a>Примечания

Эта функция члена `_variant_t` преобразует объект `VARTYPE`в указанный . Если *pSrc* null, преобразование выполняется `_variant_t` на месте, в противном случае этот объект скопирован из *pSrc,* а затем преобразуется.

**END Microsoft Специфический**

## <a name="see-also"></a>См. также раздел

[класс _variant_t](../cpp/variant-t-class.md)
