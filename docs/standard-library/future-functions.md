---
title: Функции &lt;future&gt;
ms.date: 11/04/2016
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
helpviewer_keywords:
- std::async [C++]
- std::future_category [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::swap [C++]
ms.openlocfilehash: d419984243d3970533f30814fe0ff451199afb34
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837974"
---
# <a name="ltfuturegt-functions"></a>Функции &lt;future&gt;

[Async](#async)\
[future_category](#future_category)\
[make_error_code](#make_error_code)\
[make_error_condition](#make_error_condition)\
[swap](#swap)|

## <a name="async"></a><a name="async"></a> Async

Представляет *асинхронный поставщик*.

```cpp
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```

### <a name="parameters"></a>Параметры

*policy*\
Значение [launch](../standard-library/future-enums.md#launch).

### <a name="remarks"></a>Примечания

Определения сокращений:

|Сокращение|Описание|
|-|-|
|*дфн*|Результат вызова метода `decay_copy(forward<Fn>(fn))`.|
|*dargs*|Результаты вызовов `decay_copy(forward<ArgsTypes>(args...))`.|
|*Ty*|Тип `result_of<Fn(ArgTypes...)>::type`.|

Первая функция-шаблон возвращает `async(launch::any, fn, args...)`.

Вторая функция возвращает объект `future<Ty>`, *связанное асинхронное состояние* которого содержит результат вместе со значениями функций *dfn* и *dargs* и объектом потока для управления отдельным потоком выполнения.

Пока `decay<Fn>::type` не станет типом, отличным от launch, вторая функция не участвует в разрешении перегрузки.

Стандарт C++ указывает, что если параметр Policy имеет значение Launch:: async, функция создает новый поток. Однако реализация Майкрософт в настоящее время не соответствует. Он получает свои потоки из Windows ThreadPool, что в некоторых случаях может предоставить перезапущенный поток, а не новый. Это означает, что `launch::async` политика фактически реализована как `launch::async|launch::deferred` .  Еще одним следствием реализации на основе ThreadPool является отсутствие гарантии того, что локальные переменные потока будут уничтожены после завершения потока. Если поток перезапускается и предоставляется новому вызову `async` , старые переменные по-прежнему будут существовать. Поэтому рекомендуется не использовать локальные переменные потока с `async` .

Если *Политика* имеет значение `launch::deferred` , функция помечает связанное асинхронное состояние как удерживаемую *отложенную функцию* и возвращает. Первый вызов любой функции без учета времени, которая ожидает наступления связанного асинхронного состояния "ready", фактически вызывает отложенную функцию путем оценки `INVOKE(dfn, dargs..., Ty)`.

Во всех случаях связанное асинхронное состояние объекта `future` не становится *ready* до завершения оценки `INVOKE(dfn, dargs..., Ty)` либо путем создания исключения, либо путем обычного возвращения. Результатом связанного асинхронного состояния получается исключение, если таковое было создано, или любое значение, возвращаемое при оценке.

> [!NOTE]
> Для `future` — или последнего объекта [shared_future](../standard-library/shared-future-class.md), присоединенного к задаче, запущенной с`std::async`, деструктор выполняет блокировку, если задача не была завершена; то есть он выполняет блокировку, если этот поток еще не вызвал `.get()` или `.wait()`, а задача по-прежнему выполняется. Если `future`, полученный из `std::async`, перемещается за пределы локальной области, другой код, который его использует, должен знать, что деструктор может заблокировать переход в общее состояние "ready".

Псевдо-функция `INVOKE` определяется в [\<functional>](../standard-library/functional.md) .

## <a name="future_category"></a><a name="future_category"></a> future_category

Возвращает ссылку на объект [error_category](../standard-library/error-category-class.md), характеризующий ошибки, связанные с объектами `future`.

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a><a name="make_error_code"></a> make_error_code

Создает [error_code](../standard-library/error-code-class.md) вместе с объектом [error_category](../standard-library/error-category-class.md), характеризующий ошибки [future](../standard-library/future-class.md).

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Параметры

*Errno*\
Значение [future_errc](../standard-library/future-enums.md#future_errc), идентифицирующее ошибку.

### <a name="return-value"></a>Возвращаемое значение

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a><a name="make_error_condition"></a> make_error_condition

Создает [error_condition](../standard-library/error-condition-class.md) вместе с объектом [error_category](../standard-library/error-category-class.md), характеризующий ошибки [future](../standard-library/future-class.md).

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Параметры

*Errno*\
Значение [future_errc](../standard-library/future-enums.md#future_errc), идентифицирующее ошибку.

### <a name="return-value"></a>Возвращаемое значение

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a><a name="swap"></a> swap

Обменивается *связанным асинхронным состоянием* одного `promise` объекта с другим.

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>Параметры

*Слева*\
Левый объект `promise`.

*right*\
Правой объект `promise`.

## <a name="see-also"></a>См. также раздел

[\<future>](../standard-library/future.md)
