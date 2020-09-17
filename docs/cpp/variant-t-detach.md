---
title: _variant_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
ms.openlocfilehash: 9737db6b77483fa55e1dad90b9464752cd8537a5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187743"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Блок, относящийся только к системам Microsoft**

Отсоединяет инкапсулированный `VARIANT` объект от этого `_variant_t` объекта.

## <a name="syntax"></a>Синтаксис

```
VARIANT Detach( );
```

## <a name="return-value"></a>Возвращаемое значение

Инкапсулированный `VARIANT`.

## <a name="remarks"></a>Примечания

Извлекает и возвращает инкапсулированный `VARIANT`, а затем удаляет этот объект `_variant_t` без его уничтожения. Эта функция члена удаляет `VARIANT` из инкапсуляции и задает для `VARTYPE` этого `_variant_t` объекта значение VT_EMPTY. Можно освободить возвращенный `VARIANT`, вызвав функцию [вариантклеар](/windows/win32/api/oleauto/nf-oleauto-variantclear) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _variant_t](../cpp/variant-t-class.md)
