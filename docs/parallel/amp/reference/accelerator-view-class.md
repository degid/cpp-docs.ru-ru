---
title: Класс accelerator_view
ms.date: 03/27/2019
f1_keywords:
- accelerator_view
- AMPRT/accelerator_view
- AMPRT/Concurrency::accelerator_view::accelerator_view
- AMPRT/Concurrency::accelerator_view::create_marker
- AMPRT/Concurrency::accelerator_view::flush
- AMPRT/Concurrency::accelerator_view::get_accelerator
- AMPRT/Concurrency::accelerator_view::get_is_auto_selection
- AMPRT/Concurrency::accelerator_view::get_is_debug
- AMPRT/Concurrency::accelerator_view::get_queuing_mode
- AMPRT/Concurrency::accelerator_view::get_version
- AMPRT/Concurrency::accelerator_view::wait
- AMPRT/Concurrency::accelerator_view::accelerator
- AMPRT/Concurrency::accelerator_view::is_auto_selection
- AMPRT/Concurrency::accelerator_view::is_debug
- AMPRT/Concurrency::accelerator_view::queuing_mode
- AMPRT/Concurrency::accelerator_view::version
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
ms.openlocfilehash: 0020acfda7b506bf9f0547b9daedff34d80204f7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87182763"
---
# <a name="accelerator_view-class"></a>Класс accelerator_view

Представляет абстракцию виртуального устройства на C++ AMP ускорителе обработки данных.

## <a name="syntax"></a>Синтаксис

```cpp
class accelerator_view;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор accelerator_view](#ctor)|Инициализирует новый экземпляр класса `accelerator_view`.|
|[Деструктор ~ accelerator_view](#dtor)|Уничтожает `accelerator_view` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[create_marker](#create_marker)|Возвращает будущее, чтобы отследить завершение всех команд, отправленных на данный момент в этот `accelerator_view` объект.|
|[flush](#flush)|Отправляет все ожидающие команды, поставленные в очередь на объект, в `accelerator_view` ускоритель для выполнения.|
|[get_accelerator](#get_accelerator)|Возвращает объект `accelerator` для объекта `accelerator_view`.|
|[get_is_auto_selection](#get_is_auto_selection)|Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующее сочетание клавиш при `accelerator_view` передаче объекта в [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|
|[get_is_debug](#get_is_debug)|Возвращает логическое значение, указывающее, включен ли `accelerator_view` для объекта слой отладки для расширенных отчетов об ошибках.|
|[get_queuing_mode](#get_queuing_mode)|Возвращает режим очереди для `accelerator_view` объекта.|
|[get_version](#get_version)|Возвращает версию `accelerator_view` .|
|[ожидания](#wait)|Ожидает завершения всех команд, отправленных в `accelerator_view` объект.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator!=](#operator_neq)|Сравнивает этот `accelerator_view` объект с другим и возвращает, **`false`** если они одинаковы; в противном случае возвращает **`true`** .|
|[operator=](#operator_eq)|Копирует содержимое указанного `accelerator_view` объекта в этот объект.|
|[operator==](#operator_eq_eq)|Сравнивает этот `accelerator_view` объект с другим и возвращает, **`true`** если они одинаковы; в противном случае возвращает **`false`** .|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Accelerator](#accelerator)|Возвращает объект `accelerator` для объекта `accelerator_view`.|
|[is_auto_selection](#is_auto_selection)|Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующее сочетание клавиш при `accelerator_view` передаче объекта в [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|
|[is_debug](#is_debug)|Возвращает логическое значение, указывающее, включен ли `accelerator_view` для объекта слой отладки для расширенных отчетов об ошибках.|
|[queuing_mode](#queuing_mode)|Возвращает режим очереди для `accelerator_view` объекта.|
|[version](#version)|Возвращает версию ускорителя.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`accelerator_view`

### <a name="remarks"></a>Примечания

`accelerator_view`Объект представляет логическое изолированное представление ускорителя. Одно физическое устройство вычислений может иметь много логических изолированных `accelerator_view` объектов. Каждый ускоритель имеет объект по умолчанию `accelerator_view` . `accelerator_view`Можно создать дополнительные объекты.

Физические устройства могут совместно использоваться несколькими клиентскими потоками. Клиентские потоки могут совместно использовать один и тот же `accelerator_view` объект ускорителя, или каждый клиент может взаимодействовать с устройством вычислений через независимый `accelerator_view` объект для изоляции от других клиентских потоков.

`accelerator_view`Объект может иметь одно из двух [Queuing_mode состояний перечисления](concurrency-namespace-enums-amp.md#queuing_mode) . Если используется режим очереди `immediate` , то команды, такие как `copy` и, `parallel_for_each` отправляются соответствующему устройству ускорителя, как только они возвращаются вызывающему. Если используется режим очереди `deferred` , то такие команды ставятся в очередь в очереди команд, соответствующей `accelerator_view` объекту. Команды на самом деле не отправляются на устройство, пока `flush()` не будет вызван метод.

## <a name="requirements"></a>Требования

**Заголовок:** ампрт.h

**Пространство имен** : Concurrency

## <a name="accelerator"></a><a name="accelerator"></a>Accelerator

Возвращает объект ускорителя для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="accelerator_view"></a><a name="ctor"></a>accelerator_view

Инициализирует новый экземпляр класса accelerator_view путем копирования существующего `accelerator_view` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Копируемый объект `accelerator_view`.

## <a name="create_marker"></a><a name="create_marker"></a>create_marker

Возвращает будущее, чтобы отследить завершение всех команд, отправленных на данный момент в этот `accelerator_view` объект.

### <a name="syntax"></a>Синтаксис

```cpp
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>Возвращаемое значение

Будущее, чтобы отследить завершение всех команд, отправленных на данный момент в этот `accelerator_view` объект.

## <a name="flush"></a>flush

Отправляет все ожидающие команды, поставленные в очередь на объект accelerator_view, в ускоритель для выполнения.

### <a name="syntax"></a>Синтаксис

```cpp
void flush();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает **`void`** .

## <a name="get_accelerator"></a><a name="get_accelerator"></a>get_accelerator

Возвращает объект ускорителя для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
accelerator get_accelerator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект ускорителя для объекта accelerator_view.

## <a name="get_is_auto_selection"></a><a name="get_is_auto_selection"></a>get_is_auto_selection

Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующее сочетание клавиш при передаче accelerator_view в [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).

### <a name="syntax"></a>Синтаксис

```cpp
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если среда выполнения будет автоматически выбирать соответствующее сочетание клавиш, в противном случае — **`false`** .

## <a name="get_is_debug"></a><a name="get_is_debug"></a>get_is_debug

Возвращает логическое значение, указывающее, включен ли для объекта accelerator_view слой отладки для расширенных отчетов об ошибках.

### <a name="syntax"></a>Синтаксис

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, указывающее, включен ли `accelerator_view` для объекта слой отладки для расширенных отчетов об ошибках.

## <a name="get_queuing_mode"></a><a name="get_queuing_mode"></a>get_queuing_mode

Возвращает режим очереди для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Режим очереди для `accelerator_view` объекта.

## <a name="get_version"></a><a name="get_version"></a>get_version

Возвращает версию accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>Возвращаемое значение

Версия объекта `accelerator_view`.

## <a name="is_auto_selection"></a><a name="is_auto_selection"></a>is_auto_selection

Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующее сочетание клавиш при передаче accelerator_view в [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="is_debug"></a><a name="is_debug"></a>is_debug

Получает логическое значение, указывающее, имеет ли объект accelerator_view уровень отладки, позволяющий формировать расширенные отчеты об ошибках.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator"></a><a name="operator_neq"></a>operator!=

Сравнивает этот объект accelerator_view с другим и возвращает, **`false`** если они одинаковы; в противном случае возвращает **`true`** .

### <a name="syntax"></a>Синтаксис

```cpp
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Параметры

*иной*<br/>
`accelerator_view`Объект, сравниваемый с данным объектом.

### <a name="return-value"></a>Возвращаемое значение

**`false`** значение, если два объекта одинаковы; в противном случае — **`true`** .

## <a name="operator"></a><a name="operator_eq"></a>Оператор =

Копирует содержимое указанного объекта accelerator_view в этот объект.

### <a name="syntax"></a>Синтаксис

```cpp
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Объект, из которого производится `accelerator_view` копирование.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на измененный `accelerator_view` объект.

## <a name="operator"></a><a name="operator_eq_eq"></a>Оператор = =

Сравнивает этот объект accelerator_view с другим и возвращает, **`true`** если они одинаковы; в противном случае возвращает **`false`** .

### <a name="syntax"></a>Синтаксис

```cpp
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Параметры

*иной*<br/>
`accelerator_view`Объект, сравниваемый с данным объектом.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если два объекта одинаковы; в противном случае — **`false`** .

## <a name="queuing_mode"></a><a name="queuing_mode"></a>queuing_mode

Возвращает режим очереди для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="version"></a>version

Возвращает версию accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="wait"></a>wait

Ожидает завершения всех команд, отправленных в объект accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
void wait();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает **`void`** .

### <a name="remarks"></a>Примечания

Если [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) имеет значение `immediate` , этот метод возвращает значение немедленно без блокировки.

## <a name="accelerator_view"></a><a name="dtor"></a>~ accelerator_view

Уничтожает объект accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
~accelerator_view();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
