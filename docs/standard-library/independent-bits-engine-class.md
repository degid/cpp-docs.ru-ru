---
title: Класс independent_bits_engine
ms.date: 11/04/2016
f1_keywords:
- random/std::independent_bits_engine
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
ms.openlocfilehash: f9c1c97795e6d4eeff64ba8be8f22602f4f3fbd6
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845774"
---
# <a name="independent_bits_engine-class"></a>Класс independent_bits_engine

Создает случайную последовательность чисел с указанным числом разрядов, перемешивая разряды из значений, возвращенных базовым механизмом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Engine, size_t W, class UIntType>
class independent_bits_engine;
```

### <a name="parameters"></a>Параметры

*Ядре*\
Тип базового механизма.

*Белая*\
**Размер слова**. Размер каждого полученного числа в битах. **Предварительное условие**: `0 < W ≤ numeric_limits<UIntType>::digits`

*уинттипе*\
Беззнаковый целочисленный тип результата. Возможные типы см. в разделе [\<random>](../standard-library/random.md) .

## <a name="members"></a>Элементы

`independent_bits_engine::independent_bits_engine`\
`independent_bits_engine::base`\
`independent_bits_engine::base_type`\
`independent_bits_engine::discard`\
`independent_bits_engine::operator()`\
`independent_bits_engine::seed`

Дополнительные сведения о членах подсистемы см [\<random>](../standard-library/random.md) . в разделе.

## <a name="remarks"></a>Примечания

Этот шаблон класса описывает *адаптер подсистемы* , создающий значения путем повторного упаковки битов из значений, возвращенных базовым механизмом, в результате чего используются значения *W*bit.

## <a name="requirements"></a>Требования

**Заголовок:**\<random>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[\<random>](../standard-library/random.md)
