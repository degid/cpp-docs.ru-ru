---
title: Класс task_handle
ms.date: 03/27/2019
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
ms.openlocfilehash: a61e72f14448d5033d5be9069ffeec7d3bb08061
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142557"
---
# <a name="task_handle-class"></a>Класс task_handle

Класс `task_handle` представляет отдельный параллельный рабочий элемент. Он инкапсулирует инструкции и данные, необходимые для выполнения части работы.

## <a name="syntax"></a>Синтаксис

```cpp
template<
    typename _Function
>
class task_handle : public ::Concurrency::details::_UnrealizedChore;
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Тип объекта функции, который будет вызываться для выполнения работы, представленной объектом `task_handle`.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[task_handle](#task_handle)|Создает новый объект `task_handle`. Работа задачи выполняется путем вызова функции, указанной в качестве параметра конструктора.|
|[Деструктор ~ task_handle](#dtor)|Уничтожает объект `task_handle`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator()](#task_handle__operator_call)|Оператор вызова функции, который вызывается средой выполнения для выполнения работы обработчика задачи.|

## <a name="remarks"></a>Примечания

`task_handle` объекты можно использовать в сочетании с `structured_task_group` или более общим объектом `task_group`, чтобы разбить работу на параллельные задачи. Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Обратите внимание, что создатель объекта `task_handle` отвечает за поддержание времени существования созданного объекта `task_handle`, пока он больше не требуется для среда выполнения с параллелизмом. Как правило, это означает, что `task_handle` объект не должен уничтожения до тех пор, пока не будет вызван метод `wait` или `run_and_wait` `task_group` или `structured_task_group`, с которым он ставится в очередь.

`task_handle` объекты обычно используются в сочетании с C++ лямбда-выражениями. Так как неизвестный тип лямбда-выражения незнаком, функция [make_task](concurrency-namespace-functions.md#make_task) обычно используется для создания объекта `task_handle`.

Среда выполнения создает копию рабочей функции, которая передается в объект `task_handle`. Таким образом, любые изменения состояния, происходящие в объекте функции, который передается в `task_handle` объект, не будут отображаться в копии этого объекта функции.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`task_handle`

## <a name="requirements"></a>Требования

**Заголовок:** PPL.h

**Пространство имен:** concurrency

## <a name="task_handle__operator_call"></a>оператор ()

Оператор вызова функции, который вызывается средой выполнения для выполнения работы обработчика задачи.

```cpp
void operator()() const;
```

## <a name="task_handle"></a>task_handle

Создает новый объект `task_handle`. Работа задачи выполняется путем вызова функции, указанной в качестве параметра конструктора.

```cpp
task_handle(const _Function& _Func);
```

### <a name="parameters"></a>Параметры

*_Func*<br/>
Функция, которая будет вызываться для выполнения работы, представленной объектом `task_handle`. Это может быть лямбда-функтор, указатель на функцию или любой объект, поддерживающий версию оператора вызова функции с сигнатурой `void operator()()`.

### <a name="remarks"></a>Примечания

Среда выполнения создает копию рабочей функции, которая передается в конструктор. Таким образом, любые изменения состояния, происходящие в объекте функции, который передается в `task_handle` объект, не будут отображаться в копии этого объекта функции.

## <a name="dtor"></a>~ task_handle

Уничтожает объект `task_handle`.

```cpp
~task_handle();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс task_group](task-group-class.md)<br/>
[Класс structured_task_group](structured-task-group-class.md)
