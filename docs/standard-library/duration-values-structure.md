---
title: Структура duration_values
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
ms.openlocfilehash: e2c03b4540ea5f89843562d1310b71635b3bc259
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368744"
---
# <a name="duration_values-structure"></a>Структура duration_values

Предоставляет конкретные значения для параметра-шаблона [длительности](../standard-library/duration-class.md)`Rep`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Rep>
struct duration_values;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Макс](#max)|Статический. Указывает верхний предел для значения типа `Rep`.|
|[Мин](#min)|Статический. Указывает нижний предел для значения типа `Rep`.|
|[Нуля](#zero)|Статический. Возвращает `Rep(0)`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<хроно>

**Пространство имен:** std::chrono

## <a name="duration_valuesmax"></a><a name="max"></a>duration_values::max

Статический метод, который возвращает верхнюю границу значений типа `Ref`.

```cpp
static constexpr Rep max();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `numeric_limits<Rep>::max()`.

### <a name="remarks"></a>Примечания

Если `Rep` является пользовательским типом, возвращаемое значение должно быть больше [duration_values::zero](#zero).

## <a name="duration_valuesmin"></a><a name="min"></a>duration_values::мин

Статический метод, который возвращает нижнюю границу для значений типа `Ref`.

```cpp
static constexpr Rep min();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `numeric_limits<Rep>::lowest()`.

### <a name="remarks"></a>Примечания

Если `Rep` является пользовательским типом, возвращаемое значение должно быть меньше или равно [duration_values::zero](#zero).

## <a name="duration_valueszero"></a><a name="zero"></a>duration_values::нулевой

Возвращает `Rep(0)`.

```cpp
static constexpr Rep zero();
```

### <a name="remarks"></a>Примечания

Если `Rep` является пользовательским типом, возвращаемое значение должно представлять аддитивную бесконечность.

## <a name="see-also"></a>См. также раздел

[Справка по файлам заголовка](../standard-library/cpp-standard-library-header-files.md)\
[\<хроно>](../standard-library/chrono.md)
