---
title: Класс is_literal_type
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_literal_type
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
ms.openlocfilehash: d5b750755f2499c89e91e497ed03244a11484871
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212258"
---
# <a name="is_literal_type-class"></a>Класс is_literal_type

Проверяет, может ли тип использоваться в качестве **`constexpr`** переменной или быть создан, использован или возвращен из **`constexpr`** функций.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Параметры

*T*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является *типом литерала*, в противном случае — значение false. Литеральный тип является либо **`void`** скалярным типом, ссылочным типом, массивом типа литерала, либо типом класса литерала. Тип класса литерала — это тип класса, который имеет тривиальный деструктор, является либо агрегатным типом, либо имеет по крайней мере один конструктор без перемещения, не являющийся копией **`constexpr`** , а все его базовые классы и нестатические элементы данных являются типами литералов, не являющимися переменными. Хотя тип литерала всегда является литералом, понятие типа литерала включает все, что компилятор может вычислить как **`constexpr`** во время компиляции.

## <a name="requirements"></a>Требования

**Заголовок:**\<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[<type_traits>](../standard-library/type-traits.md)
