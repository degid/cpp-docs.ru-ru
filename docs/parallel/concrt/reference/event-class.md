---
title: Класс event
ms.date: 11/04/2016
f1_keywords:
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
ms.openlocfilehash: 3f2ec71083f7a7905bad5cda014baba914e31e79
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215807"
---
# <a name="event-class"></a>Класс event

Сбрасываемое вручную событие, которое явно учитывает среду выполнения с параллелизмом.

## <a name="syntax"></a>Синтаксис

```cpp
class event;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Деструктор события ~](#dtor)|Уничтожает событие.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[reset](#reset)|Сбрасывает событие в несигнальное состояние.|
|[set](#set)|Сигнализирует о событии.|
|[ожидания](#wait)|Ожидает сигнала события.|
|[wait_for_multiple](#wait_for_multiple)|Ожидает получения сигнала для нескольких событий.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[timeout_infinite](#timeout_infinite)|Значение, указывающее, что время ожидания никогда не должно истечь.|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`event`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h

**Пространство имен:** concurrency

## <a name="event"></a>Событие<a name="ctor"></a>

Конструирует новое событие.

```cpp
_CRTIMP event();
```

### <a name="remarks"></a>Примечания

## <a name="event"></a><a name="dtor"></a>событие ~

Уничтожает событие.

```cpp
~event();
```

### <a name="remarks"></a>Примечания

Ожидается, что потоки, ожидающие события, не будут выполняться при выполнении деструктора. Разрешение уничтожения события при наличии ожидающих его результатов потоков приводит к неопределенному поведению.

## <a name="reset"></a><a name="reset"></a>перезапуск

Сбрасывает событие в несигнальное состояние.

```cpp
void reset();
```

## <a name="set"></a><a name="set"></a>параметр

Сигнализирует о событии.

```cpp
void set();
```

### <a name="remarks"></a>Примечания

Подача сигнала о событии может привести к тому, что произвольное число контекстов будет ожидать, когда событие станет готово к запуску.

## <a name="timeout_infinite"></a><a name="timeout_infinite"></a>timeout_infinite

Значение, указывающее, что время ожидания никогда не должно истечь.

```cpp
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```

## <a name="wait"></a><a name="wait"></a>ожидания

Ожидает сигнала события.

```cpp
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*_Timeout*<br/>
Указывает число миллисекунд до истечения времени ожидания. Значение `COOPERATIVE_TIMEOUT_INFINITE` указывает на отсутствие времени ожидания.

### <a name="return-value"></a>Возвращаемое значение

Если ожидание было удовлетворено, `0` возвращается значение; в противном случае — значение, `COOPERATIVE_WAIT_TIMEOUT` указывающее, что время ожидания истекло без оповещения о событии.

> [!IMPORTANT]
> В приложении универсальная платформа Windows (UWP) не вызывайте `wait` поток ASTA, так как этот вызов может блокировать текущий поток и может привести к тому, что приложение перестанет отвечать на запросы.

## <a name="wait_for_multiple"></a><a name="wait_for_multiple"></a>wait_for_multiple

Ожидает получения сигнала для нескольких событий.

```cpp
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*_PPEvents*<br/>
Массив событий для ожидания. Число событий в массиве указывается `count` параметром.

*count*<br/>
Число событий в массиве, переданном в `_PPEvents` параметре.

*_FWaitAll*<br/>
Если задано значение **`true`** , параметр указывает, что все события в массиве, передаваемые в `_PPEvents` параметре, должны быть сигнальными для удовлетворения ожидания. Если задано значение **`false`** , оно указывает, что любое событие в массиве, передаваемое `_PPEvents` параметром, будет соответствовать ожиданиям.

*_Timeout*<br/>
Указывает число миллисекунд до истечения времени ожидания. Значение `COOPERATIVE_TIMEOUT_INFINITE` указывает на отсутствие времени ожидания.

### <a name="return-value"></a>Возвращаемое значение

Если ожидание было удовлетворено, индекс в массиве, указанный в `_PPEvents` параметре, который удовлетворяет условию ожидания; в противном случае — значение, `COOPERATIVE_WAIT_TIMEOUT` указывающее, что время ожидания истекло без соблюдения условия.

### <a name="remarks"></a>Примечания

Если параметру `_FWaitAll` присвоено значение, **`true`** указывающее, что все события должны быть сигнальными для удовлетворения ожидания, индекс, возвращаемый функцией, не несет никакого специального значения, Кроме того факта, что он не является значением `COOPERATIVE_WAIT_TIMEOUT` .

> [!IMPORTANT]
> В приложении универсальная платформа Windows (UWP) не вызывайте `wait_for_multiple` поток ASTA, так как этот вызов может блокировать текущий поток и может привести к тому, что приложение перестанет отвечать на запросы.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)
