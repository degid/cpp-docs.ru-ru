---
title: Функции &lt;random&gt;
ms.date: 09/04/2019
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 3d94f607fc6b7bdf22d7f573f590b451dbaa718d
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425247"
---
# <a name="ltrandomgt-functions"></a>Функции &lt;random&gt;

## <a name="generate_canonical"></a>generate_canonical

Возвращает значение с плавающей запятой из случайной последовательности.

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Параметры

*Реалтипе*\
Тип с плавающей запятой. Возможные типы см. в разделе [\<random>](../standard-library/random.md).

\ *BITS*
Количество используемых битов случайности.

\ *генератора*
Класс генератора случайных чисел.

*Общие*\
Ссылка на экземпляр генератора случайных чисел типа " *генератор*".

### <a name="remarks"></a>Примечания

Функция шаблона вызывает `operator()` операции *Gen* многократно и упаковывает возвращаемые значения в значение с плавающей запятой `x` типа *реалтипе* , пока оно не собрало указанное число битов мантисса в `x`. Указанное число является меньшим из *битов* (значение которого должно быть ненулевым) и полным числом битов мантисса в *реалтипе*. Первый вызов предоставляет младшие разряды. Функция возвращает `x`.
