---
title: Класс SchedulerPolicy
ms.date: 11/04/2016
f1_keywords:
- SchedulerPolicy
- concrt/concurrency::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::GetPolicyValue
- concrt/concurrency::SchedulerPolicy::SetConcurrencyLimits
- concrt/concurrency::SchedulerPolicy::SetPolicyValue
helpviewer_keywords:
- SchedulerPolicy class
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
ms.openlocfilehash: b7b99dae2ffb58123c05a65872e4c71e149ac12c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219577"
---
# <a name="schedulerpolicy-class"></a>Класс SchedulerPolicy

Класс `SchedulerPolicy` содержит набор пар «ключ — значение» по одной для каждого элемента политики, управляющего поведением экземпляра планировщика.

## <a name="syntax"></a>Синтаксис

```cpp
class SchedulerPolicy;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[SchedulerPolicy](#ctor)|Перегружен. Конструирует новую политику планировщика и заполняет ее значениями для [ключей политик](concurrency-namespace-enums.md) , поддерживаемых планировщиками среда выполнения с параллелизмом и диспетчер ресурсов.|
|[Деструктор ~ SchedulerPolicy](#dtor)|Уничтожает политику планировщика.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[жетполицивалуе](#getpolicyvalue)|Возвращает значение ключа политики, предоставляемое в качестве `key` параметра.|
|[сетконкурренцилимитс](#setconcurrencylimits)|Одновременно задает `MinConcurrency` политики и `MaxConcurrency` для `SchedulerPolicy` объекта.|
|[сетполицивалуе](#setpolicyvalue)|Задает значение ключа политики, предоставляемое в качестве `key` параметра, и возвращает старое значение.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator=](#operator_eq)|Назначает политику планировщика из другой политики планировщика.|

## <a name="remarks"></a>Примечания

Дополнительные сведения о политиках, которые можно контролировать с помощью `SchedulerPolicy` класса, см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SchedulerPolicy`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT.h, concrtrm.h

**Пространство имен:** concurrency

## <a name="getpolicyvalue"></a><a name="getpolicyvalue"></a>жетполицивалуе

Возвращает значение ключа политики, предоставляемое в качестве `key` параметра.

```cpp
unsigned int GetPolicyValue(PolicyElementKey key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ политики для получения значения.

### <a name="return-value"></a>Возвращаемое значение

Если ключ, заданный `key` параметром, поддерживается, значение политики для приведения ключа к **`unsigned int`** .

### <a name="remarks"></a>Примечания

Метод вызовет исключение [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) для недопустимого ключа политики.

## <a name="operator"></a><a name="operator_eq"></a>Оператор =

Назначает политику планировщика из другой политики планировщика.

```cpp
SchedulerPolicy& operator= (const SchedulerPolicy& _RhsPolicy);
```

### <a name="parameters"></a>Параметры

*_RhsPolicy*<br/>
Политика, назначаемая этой политике.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на политику планировщика.

### <a name="remarks"></a>Примечания

Часто наиболее удобным способом для определения новой политики планировщика является копирование существующей политики и изменение ее методами `SetPolicyValue` или `SetConcurrencyLimits`.

## <a name="schedulerpolicy"></a><a name="ctor"></a>SchedulerPolicy

Конструирует новую политику планировщика и заполняет ее значениями для [ключей политик](concurrency-namespace-enums.md) , поддерживаемых планировщиками среда выполнения с параллелизмом и диспетчер ресурсов.

```cpp
SchedulerPolicy();

SchedulerPolicy(
    size_t _PolicyKeyCount,
...);

SchedulerPolicy(
    const SchedulerPolicy& _SrcPolicy);
```

### <a name="parameters"></a>Параметры

*_PolicyKeyCount*<br/>
Число пар "ключ-значение", которые следуют за `_PolicyKeyCount` параметром.

*_SrcPolicy*<br/>
Исходная политика для копирования.

### <a name="remarks"></a>Примечания

Первый конструктор создает новую политику планировщика, где все политики будут инициализированы значениями по умолчанию.

Второй конструктор создает новую политику планировщика, в которой используется стиль инициализации с именованными параметрами. Значения после `_PolicyKeyCount` параметра передаются в виде пар "ключ-значение". Любой ключ политики, который не указан в этом конструкторе, будет иметь значение по умолчанию. Этот конструктор может вызывать исключения [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md), [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) или [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md).

Третий конструктор является конструктором копии. Часто наиболее удобным способом для определения новой политики планировщика является копирование существующей политики и изменение ее методами `SetPolicyValue` или `SetConcurrencyLimits`.

## <a name="schedulerpolicy"></a><a name="dtor"></a>~ SchedulerPolicy

Уничтожает политику планировщика.

```cpp
~SchedulerPolicy();
```

## <a name="setconcurrencylimits"></a><a name="setconcurrencylimits"></a>сетконкурренцилимитс

Одновременно задает `MinConcurrency` политики и `MaxConcurrency` для `SchedulerPolicy` объекта.

```cpp
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```

### <a name="parameters"></a>Параметры

*_MinConcurrency*<br/>
Значение для `MinConcurrency` ключа политики.

*_MaxConcurrency*<br/>
Значение для `MaxConcurrency` ключа политики.

### <a name="remarks"></a>Примечания

Метод вызовет исключение [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md) , если значение, указанное для `MinConcurrency` политики, больше, чем указано для `MaxConcurrency` политики.

Метод также может создавать [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) для других недопустимых значений.

## <a name="setpolicyvalue"></a><a name="setpolicyvalue"></a>сетполицивалуе

Задает значение ключа политики, предоставляемое в качестве `key` параметра, и возвращает старое значение.

```cpp
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ политики для задания значения.

*value*<br/>
Значение, для которого необходимо задать ключ политики.

### <a name="return-value"></a>Возвращаемое значение

Если ключ, заданный `key` параметром, поддерживается, старое значение политики для приведения ключа к **`unsigned int`** .

### <a name="remarks"></a>Примечания

Метод вызовет исключение [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) для недопустимого ключа политики или любого ключа политики, значение которого не может быть задано `SetPolicyValue` методом.

Метод вызывает [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) для значения, которое не поддерживается для ключа, указанного `key` параметром.

Обратите внимание, что этот метод не может задавать `MinConcurrency` `MaxConcurrency` политики или. Чтобы задать эти значения, используйте метод [сетконкурренцилимитс](#setconcurrencylimits) .

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[Класс CurrentScheduler](currentscheduler-class.md)<br/>
[Класс Scheduler](scheduler-class.md)<br/>
[планировщик задач](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
