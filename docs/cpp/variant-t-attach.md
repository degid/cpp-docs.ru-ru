---
title: _variant_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
ms.openlocfilehash: d0822dfc730cbbb64f8364e6fa8fe8bc7207f9f9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750741"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**Microsoft Специфический**

Прикрепляет `VARIANT` объект к **_variant_t** объекту.

## <a name="syntax"></a>Синтаксис

```cpp
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>Параметры

*varSrc*<br/>
Объект, `VARIANT` который должен быть прикреплен к этому **_variant_t** объекту.

## <a name="remarks"></a>Примечания

Принимает право `VARIANT` собственности на инкапсуляции его. Эта функция члена выпускает любые существующие инкапсулированные, `VARIANT`затем копирует поставляемые, `VARIANT`и устанавливает его `VARTYPE` на VT_EMPTY, чтобы убедиться, что его ресурсы могут быть освобождены только **_variant_t** деструктора.

**END Microsoft Специфический**

## <a name="see-also"></a>См. также раздел

[класс _variant_t](../cpp/variant-t-class.md)
