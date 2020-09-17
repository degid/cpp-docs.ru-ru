---
title: Структура system_clock
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::system_clock
- chrono/std::chrono::system_clock::from_time_t
- chrono/std::chrono::system_clock::now
- chrono/std::chrono::system_clock::to_time_t
- chrono/std::chrono::system_clock::is_monotonic Constant
- chrono/std::chrono::system_clock::is_steady Constant
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
ms.openlocfilehash: 4e530887e7c8cf26e8969a839702286913da9b67
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224582"
---
# <a name="system_clock-structure"></a>Структура system_clock

Представляет *тип clock*, использующий данные системных часов в реальном времени.

## <a name="syntax"></a>Синтаксис

```cpp
struct system_clock;
```

## <a name="remarks"></a>Примечания

*Тип clock* используется для получения текущего времени в формате UTC. Этот тип реализует экземпляр класса [duration](../standard-library/duration-class.md) и шаблон класса [time_point](../standard-library/time-point-class.md), а также определяет статическую функцию-член `now()`, которая возвращает время.

Часы считаются *монотонными*, если значение, возвращаемое при первом вызове `now()`, всегда не больше значений, возвращаемых при последующих вызовах `now()`.

Часы считаются *постоянными*, если они *монотонны* и интервал времени между соседними тактами является постоянной величиной.

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`system_clock::duration`|Синоним для `duration<rep, period>`.|
|`system_clock::period`|Синоним для типа, который используется для представления тактового периода при автономном создании экземпляра `duration`.|
|`system_clock::rep`|Синоним для типа, который используется для представления числа тактов часов при автономном создании экземпляра `duration`.|
|`system_clock::time_point`|Синоним для `time_point<Clock, duration>`, где `Clock` является синонимом для самого типа часов или для другого типа часов, настроенного на ту же эпоху и имеющего тот же вложенный тип `duration`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[from_time_t](#from_time_t)|Статический. Возвращает объект `time_point`, наиболее точно соответствующий указанному времени.|
|[сжать](#now)|Статический. Возвращает текущее время.|
|[to_time_t](#to_time_t)|Статический. Возвращает объект `time_t`, наиболее точно соответствующий указанному объекту `time_point`.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[Константа system_clock::is_monotonic](#is_monotonic_constant)|Указывает, являются ли часы монотонными.|
|[Константа system_clock::is_steady](#is_steady_constant)|Указывает, являются ли часы постоянными.|

## <a name="requirements"></a>Требования

**Заголовок:**\<chrono>

**Пространство имен:** std::chrono

## <a name="system_clockfrom_time_t"></a><a name="from_time_t"></a>system_clock:: from_time_t

Статический метод, возвращающий [time_point](../standard-library/time-point-class.md) , который наиболее точно приблизительно соответствует времени, представленному *TM*.

```cpp
static time_point from_time_t(time_t Tm) noexcept;
```

### <a name="parameters"></a>Параметры

*Операций*\
Объект [time_t](../c-runtime-library/standard-types.md).

## <a name="system_clockis_monotonic-constant"></a><a name="is_monotonic_constant"></a>system_clock:: is_monotonic константа

Статическое значение, указывающее, являются ли часы монотонными.

```cpp
static const bool is_monotonic = false;
```

### <a name="return-value"></a>Возвращаемое значение

В этой реализации `system_clock::is_monotonic` всегда возвращает **`false`** .

### <a name="remarks"></a>Примечания

Часы считаются *монотонными*, если значение, возвращаемое при первом вызове `now()`, всегда не больше значений, возвращаемых при последующих вызовах `now()`.

## <a name="system_clockis_steady-constant"></a><a name="is_steady_constant"></a>system_clock:: is_steady константа

Статическое значение, указывающее, являются ли часы *постоянными*.

```cpp
static const bool is_steady = false;
```

### <a name="return-value"></a>Возвращаемое значение

В этой реализации `system_clock::is_steady` всегда возвращает **`false`** .

### <a name="remarks"></a>Примечания

Часы считаются *постоянными*, если они [монотонны](#is_monotonic_constant) и интервал времени между соседними тактами является постоянной величиной.

## <a name="system_clocknow"></a><a name="now"></a>system_clock:: Now

Статический метод, который возвращает текущее время.

```cpp
static time_point now() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [time_point](../standard-library/time-point-class.md), представляющий текущее время.

## <a name="system_clockto_time_t"></a><a name="to_time_t"></a>system_clock:: to_time_t

Статический метод, возвращающий [time_t](../c-runtime-library/standard-types.md) , который наиболее приблизительно представляет время, представленное *временем*.

```cpp
static time_t to_time_t(const time_point& Time) noexcept;
```

### <a name="parameters"></a>Параметры

*Таймаут*\
Объект [time_point](../standard-library/time-point-class.md).

## <a name="see-also"></a>См. также статью

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)\
[Структура steady_clock](../standard-library/steady-clock-struct.md)
