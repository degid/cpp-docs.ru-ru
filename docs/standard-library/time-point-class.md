---
title: Класс time_point
ms.date: 03/27/2019
f1_keywords:
- chrono/std::chrono::time_point
- chrono/std::chrono::time_point::time_point
- chrono/std::chrono::time_point::max
- chrono/std::chrono::time_point::min
- chrono/std::chrono::time_point::time_since_epoch
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
helpviewer_keywords:
- std::chrono [C++], time_point
ms.openlocfilehash: e1de674d4a13ba465100923bffe6cba76e61ab4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368031"
---
# <a name="time_point-class"></a>Класс time_point

`time_point` описывает тип, представляющий момент времени. Он содержит объект типа [duration](../standard-library/duration-class.md), в котором хранится время, прошедшее с начала эпохи, представленной аргументом шаблона `Clock`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Clock,
    class Duration = typename Clock::duration>
class time_point;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`time_point::clock`|Синоним параметра шаблона `Clock`.|
|`time_point::duration`|Синоним параметра шаблона `Duration`.|
|`time_point::period`|Синоним имени вложенного типа `duration::period`.|
|`time_point::rep`|Синоним имени вложенного типа `duration::rep`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[time_point](#time_point)|Формирует объект `time_point`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Макс](#max)|Указывает верхний предел для значения типа `time_point::ref`.|
|[Мин](#min)|Указывает нижний предел для значения типа `time_point::ref`.|
|[time_since_epoch](#time_since_epoch)|Возвращает сохраненное значение `duration`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[time_point::operator](#op_add_eq)|Добавляет указанное значение к хранимой длительности.|
|[time_point::operator-=](#operator-_eq)|Вычитает заданное значение из хранимой длительности.|

## <a name="requirements"></a>Требования

**Заголовок:** \<хроно>

**Пространство имен:** std::chrono

## <a name="time_pointmax"></a><a name="max"></a>time_point::max

Статический метод, который возвращает верхнюю границу значений типа `time_point::ref`.

```cpp
static constexpr time_point max();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `time_point(duration::max())`.

## <a name="time_pointmin"></a><a name="min"></a>time_point:мин

Статический метод, который возвращает нижнюю границу для значений типа `time_point::ref`.

```cpp
static constexpr time_point min();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `time_point(duration::min())`.

## <a name="time_pointoperator"></a><a name="op_add_eq"></a>time_point::operator

Добавляет указанное значение к хранимому значению [duration](../standard-library/duration-class.md).

```cpp
time_point& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Параметры

*Dur*\
Объект `duration` .

### <a name="return-value"></a>Возвращаемое значение

Объект `time_point` после добавления.

## <a name="time_pointoperator-"></a><a name="operator-_eq"></a>time_point:оператор-я

Вычитает заданное значение из хранимого значения [duration](../standard-library/duration-class.md).

```cpp
time_point& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Параметры

*Dur*\
Объект `duration` .

### <a name="return-value"></a>Возвращаемое значение

Объект `time_point` после вычитания.

## <a name="time_pointtime_point-constructor"></a><a name="time_point"></a>time_point::time_point Конструктор

Формирует объект `time_point`.

```cpp
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>
constexpr time_point(const time_point<clock, Duration2>& Tp);
```

### <a name="parameters"></a>Параметры

*Dur*\
Объект [duration](../standard-library/duration-class.md).

*Tp*\
Объект `time_point` .

### <a name="remarks"></a>Примечания

Первый конструктор создает объект, хранимое значение `duration` которого равно [duration::zero](../standard-library/duration-class.md#zero).

Второй конструктор строит объект, значение хранящейся продолжительности которого равно *Dur.* Если `is_convertible<Duration2, duration>` это не так, второй конструктор не участвует в разрешении перегрузок. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

Третий конструктор инициализирует свое значение `duration`, используя `Tp.time_since_epoch()`.

## <a name="time_pointtime_since_epoch"></a><a name="time_since_epoch"></a>time_point:::time_since_epoch

Извлекает хранимое значение [duration](../standard-library/duration-class.md).

```cpp
constexpr duration time_since_epoch() const;
```

## <a name="see-also"></a>См. также раздел

[Справка по файлам заголовка](../standard-library/cpp-standard-library-header-files.md)\
[\<хроно>](../standard-library/chrono.md)
