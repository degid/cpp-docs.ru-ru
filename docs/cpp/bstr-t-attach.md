---
title: _bstr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
ms.openlocfilehash: 718efb9e3dac0d776678fe9efd912a602e041659
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749699"
---
# <a name="_bstr_tattach"></a>_bstr_t::Attach

**Microsoft Специфический**

Связывает упаковщик `_bstr_t` со строкой `BSTR`.

## <a name="syntax"></a>Синтаксис

```cpp
void Attach(
   BSTR s
);
```

#### <a name="parameters"></a>Параметры

*s*<br/>
Ресурс `BSTR` для связывания с переменной `_bstr_t` или назначения ей.

## <a name="remarks"></a>Примечания

Если переменная `_bstr_t` была ранее присоединена к другому ресурсу `BSTR`, `_bstr_t` очистит ресурсы `BSTR`, если другие переменные `_bstr_t` не используют `BSTR`.

## <a name="example"></a>Пример

Смотрите [_bstr_t::Назначить](../cpp/bstr-t-assign.md) для примера с помощью **attach**.

**END Microsoft Специфический**

## <a name="see-also"></a>См. также раздел

[_bstr_t класс](../cpp/bstr-t-class.md)
