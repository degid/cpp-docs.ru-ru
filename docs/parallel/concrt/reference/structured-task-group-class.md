---
title: Класс structured_task_group
ms.date: 11/04/2016
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
ms.openlocfilehash: 44fd2a42f4c98a569e985449f0c55102a9cbc3a6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231680"
---
# <a name="structured_task_group-class"></a>Класс structured_task_group

Класс `structured_task_group` представляет коллекцию параллельной работы со сложной структурой. Можно поместить в очередь `structured_task_group` отдельные параллельные задачи с помощью объектов `task_handle` и ожидать их выполнения или отменить группу задач до завершения выполнения, что приведет к отмене всех задач, которые не начали выполнение.

## <a name="syntax"></a>Синтаксис

```cpp
class structured_task_group;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[structured_task_group](#ctor)|Перегружен. Создает новый объект `structured_task_group`.|
|[Деструктор ~ structured_task_group](#dtor)|Уничтожает объект `structured_task_group` . Ожидается вызов `wait` `run_and_wait` метода или для объекта до выполнения деструктора, если только деструктор не выполняется в результате очистки стека из-за исключения.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[cancel](#cancel)|Предпринимает попытку отменить поддерево работы с корнем в этой группе задач. Если возможно, все задачи, запланированные в группе задач, будут отменены транзитивно.|
|[is_canceling](#is_canceling)|Информирует вызывающий объект о том, находится ли группа задач в данный момент в процессе отмены. Это не обязательно означает, что `cancel` метод был вызван для `structured_task_group` объекта (хотя, безусловно, этот метод должен быть возвращен **`true`** ). Это может быть случай, когда `structured_task_group` объект выполняется в строке, а группа задач в рабочем дереве была отменена. В таких случаях, где среда выполнения может заранее определить, что отмена будет передаваться через этот `structured_task_group` объект, **`true`** также будет возвращена.|
|[запуска](#run)|Перегружен. Планирует задачу для `structured_task_group` объекта. Вызывающий объект управляет временем существования `task_handle` объекта, переданного в `_Task_handle` параметре. Версия, которая принимает параметр `_Placement`, заставляет задачу стремиться к выполнению в расположении, указанном этим параметром.|
|[run_and_wait](#run_and_wait)|Перегружен. Планирует выполнение задачи в вызывающем контексте с помощью `structured_task_group` объекта для полной поддержки отмены. Если `task_handle` объект передается в качестве параметра в `run_and_wait` , вызывающий объект отвечает за управление временем существования `task_handle` объекта. Затем функция ожидает `structured_task_group` завершения или отмены любой работы над объектом.|
|[ожидания](#wait)|Ожидает `structured_task_group` завершения работы или отмены.|

## <a name="remarks"></a>Примечания

Существует ряд строгих ограничений на использование `structured_task_group` объекта для повышения производительности.

- Один `structured_task_group` объект не может использоваться несколькими потоками. Все операции с `structured_task_group` объектом должны выполняться потоком, создавшим объект. Эти два исключения из этого правила являются функциями члена `cancel` и `is_canceling` . Объект может отсутствовать в списке записи лямбда-выражения и использоваться в задаче, если только задача не использует одну из операций отмены.

- Все задачи, запланированные на `structured_task_group` объект, планируются с помощью `task_handle` объектов, которые необходимо явно управлять временем существования.

- Несколько групп можно использовать только в порядке абсолютной вложенности. Если `structured_task_group` объявлено два объекта, второй объявленный (внутренний) должен уничтожения перед любым методом, кроме `cancel` или `is_canceling` , вызывается в первом (внешнем). Это условие имеет значение true в обоих случаях: просто объявляя несколько `structured_task_group` объектов в одной или функционально вложенной области, а также в случае задачи, которая была поставлена в очередь с `structured_task_group` помощью `run` `run_and_wait` методов или.

- В отличие от общего `task_group` класса, все состояния в `structured_task_group` классе являются окончательными. После помещения задач в очередь группы и ожидания их завершения невозможно использовать ту же группу снова.

Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`structured_task_group`

## <a name="requirements"></a>Требования

**Заголовок:** PPL.h

**Пространство имен:** concurrency

## <a name="cancel"></a><a name="cancel"></a>Отмена

Предпринимает попытку отменить поддерево работы с корнем в этой группе задач. Если возможно, все задачи, запланированные в группе задач, будут отменены транзитивно.

```cpp
void cancel();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Отмена](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

## <a name="is_canceling"></a><a name="is_canceling"></a>is_canceling

Информирует вызывающий объект о том, находится ли группа задач в данный момент в процессе отмены. Это не обязательно означает, что `cancel` метод был вызван для `structured_task_group` объекта (хотя, безусловно, этот метод должен быть возвращен **`true`** ). Это может быть случай, когда `structured_task_group` объект выполняется в строке, а группа задач в рабочем дереве была отменена. В таких случаях, где среда выполнения может заранее определить, что отмена будет передаваться через этот `structured_task_group` объект, **`true`** также будет возвращена.

```cpp
bool is_canceling();
```

### <a name="return-value"></a>Возвращаемое значение

Указывает, `structured_task_group` находится ли объект в процессе отмены (или гарантированно будет вскоре).

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Отмена](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

## <a name="run"></a><a name="run"></a>запуска

Планирует задачу для `structured_task_group` объекта. Вызывающий объект управляет временем существования `task_handle` объекта, переданного в `_Task_handle` параметре. Версия, которая принимает параметр `_Placement`, заставляет задачу стремиться к выполнению в расположении, указанном этим параметром.

```cpp
template<class _Function>
void run(
    task_handle<_Function>& _Task_handle);

template<class _Function>
void run(
    task_handle<_Function>& _Task_handle,
    location& _Placement);
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Тип объекта функции, который будет вызываться для выполнения тела маркера задачи.

*_Task_handle*<br/>
Маркер запланированной работы. Обратите внимание, что вызывающий объект отвечает за время существования этого объекта. Среда выполнения продолжит ожидать, пока для `wait` `run_and_wait` этого объекта не будет вызван метод или `structured_task_group` .

*_Placement*<br/>
Ссылка на расположение, в котором должна выполняться задача, представленная параметром `_Task_handle`.

### <a name="remarks"></a>Примечания

Среда выполнения создает копию рабочей функции, которая передается в этот метод. Любые изменения состояния, происходящие в объекте функции, который передается в этот метод, не будут отображаться в копии этого объекта функции.

Если `structured_task_group` деструкторы являются результатом очистки стека из-за исключения, нет необходимости гарантировать, что был сделан вызов `wait` `run_and_wait` метода или. В этом случае деструктор будет отменяться соответствующим образом и ожидать завершения задачи, представленной `_Task_handle` параметром.

Вызывает исключение [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) , если обработчик задач, заданный `_Task_handle` параметром, уже был запланирован на объект группы задач с помощью `run` метода, и не существовал промежуточный вызов `wait` `run_and_wait` метода или в этой группе задач.

## <a name="run_and_wait"></a><a name="run_and_wait"></a>run_and_wait

Планирует выполнение задачи в вызывающем контексте с помощью `structured_task_group` объекта для полной поддержки отмены. Если `task_handle` объект передается в качестве параметра в `run_and_wait` , вызывающий объект отвечает за управление временем существования `task_handle` объекта. Затем функция ожидает `structured_task_group` завершения или отмены любой работы над объектом.

```cpp
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Тип объекта функции, который будет вызываться для выполнения задачи.

*_Task_handle*<br/>
Обработчик для задачи, который будет выполняться встроенным в контекст вызывающего. Обратите внимание, что вызывающий объект отвечает за время существования этого объекта. Среда выполнения будет продолжать ожидать, пока `run_and_wait` метод не завершит выполнение.

*_Func*<br/>
Функция, которая будет вызываться для вызова текста работы. Это может быть лямбда-выражение или другой объект, который поддерживает версию оператора вызова функции с сигнатурой `void operator()()` .

### <a name="return-value"></a>Возвращаемое значение

Значение, указывающее, было ли выполнено ожидание или отменена группа задач из-за явной операции отмены или исключения, вызываемого одной из задач. Дополнительные сведения см. в разделе [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Примечания

Обратите внимание, что одна или несколько задач, запланированных на этот `structured_task_group` объект, могут выполняться встроенным в контекст вызывающего.

Если одна или несколько задач, запланированных на этот `structured_task_group` объект, вызывают исключение, среда выполнения выберет одно из таких исключений и распространит его из вызова `run_and_wait` метода.

После возврата этой функции объект `structured_task_group` находится в конечном состоянии и не должен использоваться. Обратите внимание, что использование после `run_and_wait` возврата метода приведет к неопределенному поведению.

В неисключительном пути выполнения у вас есть требование вызывать этот метод или `wait` метод перед деструктором `structured_task_group` выполнения.

## <a name="structured_task_group"></a><a name="ctor"></a>structured_task_group

Создает новый объект `structured_task_group`.

```cpp
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```

### <a name="parameters"></a>Параметры

*_CancellationToken*<br/>
Токен отмены, связываемый с этой структурной группой задач. Структурированная группа задач будет отменена при отмене маркера.

### <a name="remarks"></a>Примечания

Конструктор, который принимает токен отмены, создает `structured_task_group`, которая будет отменена, когда будет отменен источник, связанный с этим токеном. Предоставление явной лексемы отмены также изолирует эту структурированную группу задач от участия в неявной отмене из родительской группы с другим маркером или без токена.

## <a name="structured_task_group"></a><a name="dtor"></a>~ structured_task_group

Уничтожает объект `structured_task_group` . Ожидается вызов `wait` `run_and_wait` метода или для объекта до выполнения деструктора, если только деструктор не выполняется в результате очистки стека из-за исключения.

```cpp
~structured_task_group();
```

### <a name="remarks"></a>Примечания

Если деструктор выполняется как результат обычного выполнения (например, если не используется Очистка стека из-за исключения) и ни один из методов и `wait` не `run_and_wait` вызван, деструктор может вызвать исключение [missing_wait](missing-wait-class.md) .

## <a name="wait"></a><a name="wait"></a>ожидания

Ожидает `structured_task_group` завершения работы или отмены.

```cpp
task_group_status wait();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, указывающее, было ли выполнено ожидание или отменена группа задач из-за явной операции отмены или исключения, вызываемого одной из задач. Дополнительные сведения см. в разделе [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Примечания

Обратите внимание, что одна или несколько задач, запланированных на этот `structured_task_group` объект, могут выполняться встроенным в контекст вызывающего.

Если одна или несколько задач, запланированных на этот `structured_task_group` объект, вызывают исключение, среда выполнения выберет одно из таких исключений и распространит его из вызова `wait` метода.

После возврата этой функции объект `structured_task_group` находится в конечном состоянии и не должен использоваться. Обратите внимание, что использование после `wait` возврата метода приведет к неопределенному поведению.

В неисключительном пути выполнения у вас есть требование вызывать этот метод или `run_and_wait` метод перед деструктором `structured_task_group` выполнения.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс task_group](task-group-class.md)<br/>
[Класс task_handle](task-handle-class.md)
