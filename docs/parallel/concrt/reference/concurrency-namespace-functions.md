---
title: Функции пространства имен concurrency
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::Alloc
- concrt/concurrency::DisableTracing
- concrt/concurrency::EnableTracing
- concrtrm/concurrency::GetExecutionContextId
- concrtrm/concurrency::GetOSVersion
- concrtrm/concurrency::GetProcessorNodeCount
- concrtrm/concurrency::GetSchedulerId
- agents/concurrency::asend
- ppltasks/concurrency::cancel_current_task
- ppltasks/concurrency::create_async
- ppltasks/concurrency::create_task
- concurrent_vector/concurrency::internal_assign_iterators
- ppl/concurrency::interruption_point
- agents/concurrency::make_choice
- agents/concurrency::make_greedy_join
- ppl/concurrency::make_task
- ppl/concurrency::parallel_buffered_sort
- ppl/concurrency::parallel_for_each
- ppl/concurrency::parallel_invoke
- ppl/concurrency::parallel_reduce
- ppl/concurrency::parallel_sort
- agents/concurrency::receive
- ppl/concurrency::run_with_cancellation_token
- pplconcrt/concurrency::set_ambient_scheduler
- concrt/concurrency::set_task_execution_resources
- ppltasks/concurrency::task_from_exception
- ppltasks/concurrency::task_from_result
- concrt/concurrency::wait
- ppltasks/concurrency::when_all
- ppltasks/concurrency::when_any
ms.assetid: 520a6dff-9324-4df2-990d-302e3050af6a
ms.openlocfilehash: 25cd74e20102bbc1a75e4b4efe1bf234845f7fcb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840184"
---
# <a name="concurrency-namespace-functions"></a>Функции пространства имен concurrency

:::row:::
   :::column span="":::
      [`Alloc`](#alloc)\
      [`asend`](#asend)\
      [`cancel_current_task`](#cancel_current_task)\
      [`clear`](#clear)\
      [`create_async`](#create_async)\
      [`create_task`](#create_task)\
      [`CreateResourceManager`](#createresourcemanager)\
      [`DisableTracing`](#disabletracing)\
      [`EnableTracing`](#enabletracing)\
      [`Free`](#free)\
      [`get_ambient_scheduler`](#get_ambient_scheduler)\
      [`GetExecutionContextId`](#getexecutioncontextid)\
      [`GetOSVersion`](#getosversion)\
      [`GetProcessorCount`](#getprocessorcount)\
      [`GetProcessorNodeCount`](#getprocessornodecount)
   :::column-end:::
   :::column span="":::
      [`GetSchedulerId`](#getschedulerid)\
      [`internal_assign_iterators`](#internal_assign_iterators)\
      [`interruption_point`](#interruption_point)\
      [`is_current_task_group_canceling`](#is_current_task_group_canceling)\
      [`make_choice`](#make_choice)\
      [`make_greedy_join`](#make_greedy_join)\
      [`make_join`](#make_join)\
      [`make_task`](#make_task)\
      [`parallel_buffered_sort`](#parallel_buffered_sort)\
      [`parallel_for_each`](#parallel_for_each)\
      [`parallel_for`](#parallel_for)\
      [`parallel_invoke`](#parallel_invoke)\
      [`parallel_radixsort`](#parallel_radixsort)\
      [`parallel_reduce`](#parallel_reduce)\
      [`parallel_sort`](#parallel_sort)
   :::column-end:::
   :::column span="":::
      [`parallel_transform`](#parallel_transform)\
      [`receive`](#receive)\
      [`run_with_cancellation_token`](#run_with_cancellation_token)\
      [`send`](#send)\
      [`set_ambient_scheduler`](#set_ambient_scheduler)\
      [`set_task_execution_resources`](#set_task_execution_resources)\
      [`swap`](#swap)\
      [`task_from_exception`](#task_from_exception)\
      [`task_from_result`](#task_from_result)\
      [`Trace_agents_register_name`](#trace_agents_register_name)\
      [`try_receive`](#try_receive)\
      [`wait`](#wait)\
      [`when_all`](#when_all)\
      [`when_any`](#when_any)
   :::column-end:::
:::row-end:::

## <a name="alloc"></a><a name="alloc"></a> Идентификатор

Выделяет блок памяти указанного размера из подраспределителя кэширования среды параллелизма.

```cpp
void* __cdecl Alloc(size_t _NumBytes);
```

### <a name="parameters"></a>Параметры

*_NumBytes*<br/>
Число байтов памяти для выделения.

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что выделенную память.

### <a name="remarks"></a>Примечания

Дополнительные сведения о том, какие сценарии в приложении могут помочь при использовании подраспределителя кэширования, см. в разделе [планировщик задач](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

## <a name="asend"></a><a name="asend"></a> asend

Асинхронная операция отправки, которая планирует задачу для распространения данных в целевой блок.

```cpp
template <class T>
bool asend(
    _Inout_ ITarget<T>* _Trg,
    const T& _Data);

template <class T>
bool asend(
    ITarget<T>& _Trg,
    const T& _Data);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип отправляемых данных.

*_Trg*<br/>
Указатель или ссылка на целевой объект, в который отправляются данные.

*_Data*<br/>
Ссылка на отправляемые данные.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если сообщение было принято до возврата метода; **`false`** в противном случае —.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [функции передачи сообщений](../../../parallel/concrt/message-passing-functions.md).

## <a name="cancel_current_task"></a><a name="cancel_current_task"></a> cancel_current_task

Отменяет выполняющуюся в данный момент задачу. Эту функцию можно вызывать из тела задачи, чтобы прервать выполнение задачи и перевести ее в состояние `canceled`.

Вызов этой функции является неподдерживаемым сценарием, если вы не находитесь в теле `task`. Это приведет к неопределенному поведению, такому как сбой или нереагирование в приложении.

```cpp
inline __declspec(noreturn) void __cdecl cancel_current_task();
```

## <a name="clear"></a><a name="clear"></a> открытым

Очищает параллельную очередь, уничтожая все текущие элементы, поставленные в очередь. Этот метод не является типобезопасным в режиме параллелизма.

```cpp
template<typename T, class _Ax>
void concurrent_queue<T, _Ax>::clear();
```

### <a name="parameters"></a>Параметры

*T*<br/>

*_Ax*<br/>

## <a name="create_async"></a><a name="create_async"></a> create_async

Создает асинхронную конструкцию среды выполнения Windows на основе предоставленного пользователем лямбда-выражения или объекта функции. Тип возвращаемого значения `create_async` — один из следующих: `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^` или `IAsyncOperationWithProgress<TResult, TProgress>^`, в зависимости от сигнатуры лямбда-выражения, переданного методу.

```cpp
template<typename _Function>
__declspec(noinline) auto create_async(const _Function& _Func)
    -> decltype(ref new details::_AsyncTaskGeneratorThunk<_Function>(_Func));
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Введите ,

*_Func*<br/>
Лямбда-выражение или объект функции, из которого требуется создать асинхронную конструкцию среды выполнения Windows.

### <a name="return-value"></a>Возвращаемое значение

Асинхронная конструкция, представленная IAsyncAction ^, IAsyncActionWithProgress \<TProgress> ^, IAsyncOperation \<TResult> ^ или IAsyncOperationWithProgress \<TResult, TProgress> ^. Возвращаемый интерфейс зависит от сигнатуры лямбда-выражения, переданного функции.

### <a name="remarks"></a>Примечания

Возвращаемый тип лямбда-выражения определяет, чем является конструкция — действием или операцией.

Лямбда-выражения, возвращающие значение void, приводят к созданию действий. Лямбда-выражения, возвращающие результат типа `TResult`, приводят к созданию операций TResult.

Лямбда-выражение может также возвращать объект `task<TResult>`, который инкапсулирует асинхронную работу внутри себя или является продолжением цепочки задач, представляющих асинхронную работу. В этом случае лямбда-выражение само выполняется встроенным образом, поскольку задачами являются те, которые выполняются асинхронно, и возвращаемый тип лямбда-выражения распаковывается для создания асинхронной конструкции, возвращаемой `create_async`. Это означает, что лямбда-выражение, возвращающее задачу, вызовет \<void> Создание действий, а лямбда-выражение, возвращающее задачу, приведет к \<TResult> созданию операций TResult.

Лямбда-выражение может принимать ноль, один или два аргумента. Допустимые аргументы — `progress_reporter<TProgress>` и `cancellation_token`, в этом порядке, если используются оба. Лямбда-выражение без аргументов вызывает создание асинхронной конструкции без возможности выдачи отчета о ходе выполнения. Лямбда-выражение, которое принимает progress_reporter, приведет \<TProgress> `create_async` к возврату асинхронной конструкции, которая сообщает о ходе выполнения типа TProgress каждый раз, когда `report` вызывается метод объекта progress_reporter. Лямбда-выражение, которое принимает cancellation_token, может использовать этот токен для проверки отмены или передать создаваемым им задачам, чтобы отмена асинхронной конструкции приводила к отмене этих задач.

Если тело лямбда-выражения или объекта функции возвращает результат (а не задача \<TResult> ), лямбда-будет выполняться асинхронно в рамках процесса MTA в контексте задачи, которую среда выполнения неявно создает для нее. Метод `IAsyncInfo::Cancel` вызовет отмену неявной задачи.

Если тело лямбда-выражения возвращает задачу, лямбда-выражение выполняется встроенным образом, и путем объявления, чтобы лямбда-выражение принимало аргумент типа `cancellation_token`, можно привести в действие отмену всех задач, создаваемых внутри лямбда-выражения путем передачи этого токена при их создании. Можно также использовать метод `register_callback` для этого токена, чтобы вызвать выполнение исполняющей средой обратного вызова при вызове `IAsyncInfo::Cancel` для созданной асинхронной операции или действия.

Эта функция доступна только для среда выполнения Windows приложений.

## <a name="createresourcemanager"></a><a name="createresourcemanager"></a> креатересаурцеманажер

Возвращает интерфейс, который представляет одноэлементный экземпляр диспетчера ресурсов среды выполнения с параллелизмом. Диспетчер ресурсов отвечает за назначение ресурсов планировщикам, которым требуется взаимодействовать друг с другом.

```cpp
IResourceManager* __cdecl CreateResourceManager();
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IResourceManager`.

### <a name="remarks"></a>Примечания

Несколько последующих вызовов этого метода будут возвращать один и тот же экземпляр диспетчер ресурсов. Каждый вызов метода увеличивает счетчик ссылок на диспетчер ресурсов и должен сопоставляться с вызовом метода [метод IResourceManager:: Release](iresourcemanager-structure.md) , когда планировщик выполняет связь с диспетчер ресурсов.

[unsupported_os](unsupported-os-class.md) возникает, если операционная система не поддерживается среда выполнения с параллелизмом.

## <a name="create_task"></a><a name="create_task"></a> create_task

Создает объект [задачи](task-class.md) PPL. Функция `create_task` может использоваться в любой ситуации, где бы вы использовали конструктор задач. Он предоставляется преимущественно для удобства, так как он позволяет использовать **`auto`** ключевое слово при создании задач.

```cpp
template<typename T>
__declspec(noinline) auto create_task(T _Param, const task_options& _TaskOptions = task_options())
    -> task<typename details::_TaskTypeFromParam<T>::T>;

template<typename _ReturnType>
__declspec( noinline) task<_ReturnType> create_task(const task<_ReturnType>& _Task);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип параметра, из которого будет создаваться задача.

*_ReturnType*<br/>
Введите ,

*_Param*<br/>
Параметр, из которого будет создаваться задача. Это может быть лямбда-выражение или объект функции, `task_completion_event` объект, другой `task` объект или интерфейс Windows:: Foundation:: иасинЦинфо, если вы используете задачи в приложении UWP.

*_TaskOptions*<br/>
Параметры задачи.

*_Task*<br/>
Задача, которую требуется создать.

### <a name="return-value"></a>Возвращаемое значение

Новая задача типа `T` , выводимая из `_Param` .

### <a name="remarks"></a>Примечания

Первая перегрузка ведет себя как конструктор задачи, принимающий один параметр.

Вторая перегрузка связывает токен отмены, предоставленный для вновь созданной задачи. При использовании этой перегрузки не допускается передача другого `task` объекта в качестве первого параметра.

Тип возвращаемой задачи выводится из первого параметра функции. Если `_Param` параметр имеет `task_completion_event<T>` тип, `task<T>` или функтор, возвращающий любой из типов `T` или `task<T>` , тип созданной задачи — `task<T>` .

В приложении UWP, если `_Param` имеет тип Windows:: Foundation:: IAsyncOperation \<T> ^ или Windows:: Foundation:: IAsyncOperationWithProgress ^ или \<T,P> функтор, возвращающий любой из этих типов, созданная задача будет иметь тип `task<T>` . Если `_Param` имеет тип Windows:: Foundation:: IAsyncAction ^ или Windows:: Foundation:: IAsyncActionWithProgress \<P> ^ или функтор, возвращающий любой из этих типов, созданная задача будет иметь тип `task<void>` .

## <a name="disabletracing"></a><a name="disabletracing"></a> дисаблетраЦинг

Отключает трассировку в среде выполнения с параллелизмом. Эту функция не рекомендуется использовать, поскольку трассировка событий Windows по умолчанию не регистрируется.

```cpp
__declspec(deprecated("Concurrency::DisableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl DisableTracing();
```

### <a name="return-value"></a>Возвращаемое значение

Если трассировка была правильно отключена, `S_OK` возвращается значение. Если трассировка не была запущена ранее, возвращается `E_NOT_STARTED`

## <a name="enabletracing"></a><a name="enabletracing"></a> EnableTracing

Включает трассировку в среде выполнения с параллелизмом. Эта функция не рекомендована к использованию, поскольку трассировка событий Windows теперь по умолчанию включена.

```cpp
__declspec(deprecated("Concurrency::EnableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl EnableTracing();
```

### <a name="return-value"></a>Возвращаемое значение

Если трассировка была правильно инициирована, `S_OK` возвращается значение; в противном случае `E_NOT_STARTED` возвращается значение.

## <a name="free"></a><a name="free"></a> Свободный

Освобождает блок памяти, ранее выделенный методом `Alloc` для подраспределителя кэширования среды выполнения с параллелизмом.

```cpp
void __cdecl Free(_Pre_maybenull_ _Post_invalid_ void* _PAllocation);
```

### <a name="parameters"></a>Параметры

*_PAllocation*<br/>
Указатель на память, выделенную ранее `Alloc` методом, который должен быть освобожден. Если для параметра `_PAllocation` задано значение `NULL` , этот метод будет игнорировать его и сразу же вернуться.

### <a name="remarks"></a>Примечания

Дополнительные сведения о том, какие сценарии в приложении могут помочь при использовании подраспределителя кэширования, см. в разделе [планировщик задач](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

## <a name="get_ambient_scheduler"></a><a name="get_ambient_scheduler"></a> get_ambient_scheduler

```cpp
inline std::shared_ptr<::Concurrency::scheduler_interface> get_ambient_scheduler();
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="getexecutioncontextid"></a><a name="getexecutioncontextid"></a> жетексекутионконтекстид

Возвращает уникальный идентификатор, который можно назначить контексту выполнения, реализующему интерфейс `IExecutionContext`.

```cpp
unsigned int __cdecl GetExecutionContextId();
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор контекста выполнения.

### <a name="remarks"></a>Примечания

Этот метод используется для получения идентификатора контекста выполнения перед передачей `IExecutionContext` интерфейса в качестве параметра в любой из методов, предлагаемых диспетчер ресурсов.

## <a name="getosversion"></a><a name="getosversion"></a> GetOSVersion

Возвращает версию операционной системы.

```cpp
IResourceManager::OSVersion __cdecl GetOSVersion();
```

### <a name="return-value"></a>Возвращаемое значение

Перечислимое значение, представляющее операционную систему.

### <a name="remarks"></a>Примечания

[unsupported_os](unsupported-os-class.md) возникает, если операционная система не поддерживается среда выполнения с параллелизмом.

## <a name="getprocessorcount"></a><a name="getprocessorcount"></a> жетпроцессоркаунт

Возвращает число аппаратных потоков базовой системы.

```cpp
unsigned int __cdecl GetProcessorCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число аппаратных потоков.

### <a name="remarks"></a>Примечания

[unsupported_os](unsupported-os-class.md) возникает, если операционная система не поддерживается среда выполнения с параллелизмом.

## <a name="getprocessornodecount"></a><a name="getprocessornodecount"></a> жетпроцессорнодекаунт

Возвращает число узлов NUMA или пакетов процессора в базовой системе.

```cpp
unsigned int __cdecl GetProcessorNodeCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество узлов NUMA или пакетов процессоров.

### <a name="remarks"></a>Примечания

Если система содержит больше узлов NUMA, чем пакеты процессоров, возвращается количество узлов NUMA, в противном случае возвращается количество пакетов процессора.

[unsupported_os](unsupported-os-class.md) возникает, если операционная система не поддерживается среда выполнения с параллелизмом.

## <a name="getschedulerid"></a><a name="getschedulerid"></a> жетсчедулерид

Возвращает уникальный идентификатор, который можно назначить планировщику, реализующему интерфейс `IScheduler`.

```cpp
unsigned int __cdecl GetSchedulerId();
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор планировщика.

### <a name="remarks"></a>Примечания

Этот метод используется для получения идентификатора планировщика перед передачей `IScheduler` интерфейса в качестве параметра любому из методов, предлагаемых диспетчер ресурсов.

## <a name="internal_assign_iterators"></a><a name="internal_assign_iterators"></a> internal_assign_iterators

```cpp
template<typename T, class _Ax>
template<class _I>
void concurrent_vector<T, _Ax>::internal_assign_iterators(
   _I first,
   _I last);
```

### <a name="parameters"></a>Параметры

*T*<br/>

*_Ax*<br/>

*_I*<br/>

*first*<br/>

*last*<br/>

## <a name="interruption_point"></a><a name="interruption_point"></a> interruption_point

Создает точку прерывания для отмены. Если отмена выполняется в контексте, где вызывается эта функция, это создает внутреннее исключение, которое прерывает текущую выполняемую параллельную работу. Если отмена не выполняется, функция ничего не делает.

```cpp
inline void interruption_point();
```

### <a name="remarks"></a>Примечания

Не следует перехватывать внутреннее исключение отмены, создаваемое функцией `interruption_point()`. Исключение будет перехвачено и обработано средой выполнения, и его перехват может вызвать непредсказуемое поведение программы.

## <a name="is_current_task_group_canceling"></a><a name="is_current_task_group_canceling"></a> is_current_task_group_canceling

Возвращает значение, указывающее, находится ли группа задач, которая в данный момент выполняется в текущем контексте во встроенном режиме, в процессе активной отмены (или вскоре перейдет в это состояние). Обратите внимание, что если в текущем контексте нет группы задач, выполняющейся в настоящий момент, **`false`** будет возвращено.

```cpp
bool __cdecl is_current_task_group_canceling();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если группа задач, которая выполняется в данный момент, отменяется; **`false`** в противном случае —.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Отмена](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

## <a name="make_choice"></a><a name="make_choice"></a> make_choice

Конструирует блок сообщений `choice` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.

```cpp
template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    Scheduler& _PScheduler,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    ScheduleGroup& _PScheduleGroup,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);
```

### <a name="parameters"></a>Параметры

*T1*<br/>
Тип блока сообщения первого источника.

*T2*<br/>
Тип блока сообщений второго источника.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `choice` .

*_Item1*<br/>
Первый источник.

*_Item2*<br/>
Второй источник.

*_Items*<br/>
Дополнительные источники.

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `choice` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="return-value"></a>Возвращаемое значение

Блок сообщений `choice` с двумя или более источниками входных данных.

## <a name="make_greedy_join"></a><a name="make_greedy_join"></a> make_greedy_join

Конструирует блок сообщений `greedy multitype_join` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.

```cpp
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>,greedy> make_greedy_join(
    Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    T1 _Item1,
    T2 _Items,
    Ts... _Items);
```

### <a name="parameters"></a>Параметры

*T1*<br/>
Тип блока сообщения первого источника.

*T2*<br/>
Тип блока сообщений второго источника.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` .

*_Item1*<br/>
Первый источник.

*_Item2*<br/>
Второй источник.

*_Items*<br/>
Дополнительные источники.

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="return-value"></a>Возвращаемое значение

Блок сообщений `greedy multitype_join` с двумя или более источниками входных данных.

## <a name="make_join"></a><a name="make_join"></a> make_join

Конструирует блок сообщений `non_greedy multitype_join` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.

```cpp
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>>
    make_join(
Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);
```

### <a name="parameters"></a>Параметры

*T1*<br/>
Тип блока сообщения первого источника.

*T2*<br/>
Тип блока сообщений второго источника.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` .

*_Item1*<br/>
Первый источник.

*_Item2*<br/>
Второй источник.

*_Items*<br/>
Дополнительные источники.

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="return-value"></a>Возвращаемое значение

Блок сообщений `non_greedy multitype_join` с двумя или более источниками входных данных.

## <a name="make_task"></a><a name="make_task"></a> make_task

Метод фабрики для создания объекта `task_handle`.

```cpp
template <class _Function>
task_handle<_Function> make_task(const _Function& _Func);
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Тип объекта функции, который будет вызываться для выполнения работы, представленной `task_handle` объектом.

*_Func*<br/>
Функция, которая будет вызываться для выполнения работы, представленной `task_handle` объектом. Это может быть лямбда-функтор, указатель на функцию или любой объект, который поддерживает версию оператора вызова функции с сигнатурой `void operator()()` .

### <a name="return-value"></a>Возвращаемое значение

Объект `task_handle`.

### <a name="remarks"></a>Примечания

Эта функция полезна, если необходимо создать `task_handle` объект с лямбда-выражением, поскольку он позволяет создать объект, не зная истинного типа лямбда-функтор.

## <a name="parallel_buffered_sort"></a><a name="parallel_buffered_sort"></a> parallel_buffered_sort

Упорядочивает элементы в указанном диапазоне в порядке убывания или в соответствии с критерием упорядочивания, заданным бинарным предикатом, в Parallel. Эта функция семантически аналогична `std::sort` в том, что она является нестабильной сортировкой на месте на основе сравнения, за исключением того, что ей требуется `O(n)` дополнительного пространства и инициализация по умолчанию для сортируемых элементов.

```cpp
template<typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```

### <a name="parameters"></a>Параметры

*_Random_iterator*<br/>
Тип итератора входного диапазона.

*_Allocator*<br/>
Тип стандартной библиотеки C++, совместимой с механизмом выделения памяти.

*_Function*<br/>
Тип двоичного сравнения.

*_Begin*<br/>
Итератор произвольного доступа, обращающийся к позиции первого элемента в сортируемом диапазоне.

*_End*<br/>
Итератор произвольного доступа, обращающийся к позиции после последнего элемента в сортируемом диапазоне.

*_Alloc*<br/>
Экземпляр стандартной библиотеки C++, совместимый с механизмом выделения памяти.

*_Func*<br/>
Определяемый пользователем объект функции предиката, который определяет критерии сравнения, которые должны соблюдаться идущими подряд элементами при упорядочении. Бинарный предикат принимает два аргумента и возвращает значение, если они **`true`** удовлетворены и **`false`** не удовлетворены. Эта функция средства сравнения должна задать строгое слабое упорядочение пар элементов последовательности.

*_Chunk_size*<br/>
Минимальный размер блока, который будет разбит на два для параллельного выполнения.

### <a name="remarks"></a>Примечания

Для всех перегрузок требуется `n * sizeof(T)` дополнительное пространство, где `n` — количество элементов для сортировки, а `T` — тип элемента. В большинстве случаев parallel_buffered_sort покажет повышение производительности по сравнению с [parallel_sort](concurrency-namespace-functions.md), и его следует использовать parallel_sort при наличии доступной памяти.

Если не указать двоичное `std::less` средство сравнения, используется по умолчанию, что требует, чтобы тип элемента предоставил оператор `operator<()` .

Если не указать тип или экземпляр распределителя, `std::allocator<T>` для выделения буфера используется распределитель памяти стандартной библиотеки C++.

Алгоритм делит входной диапазон на два блока и последовательно делит каждый блок на два подблока для параллельного выполнения. Необязательный аргумент `_Chunk_size` может использоваться для обозначения алгоритма, что он должен обрабатывать блоки размера < `_Chunk_size` последовательно.

## <a name="parallel_for"></a><a name="parallel_for"></a> parallel_for

`parallel_for` выполняет итерацию по диапазону индексов и выполняет предоставленную пользователем функцию в каждой итерации параллельно.

```cpp
template <typename _Index_type, typename _Function, typename _Partitioner>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func,
    _Partitioner&& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const static_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const simple_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    affinity_partitioner& _Part);
```

### <a name="parameters"></a>Параметры

*_Index_type*<br/>
Тип индекса, используемого для итерации.

*_Function*<br/>
Тип функции, которая будет выполняться при каждой итерации.

*_Partitioner*<br/>
Тип разделителя, используемого для секционирования заданного диапазона.

*first*<br/>
Первый индекс, который необходимо добавить в итерацию.

*last*<br/>
Индекс, который находится за последним индексом, включаемым в итерацию.

*_Step*<br/>
Значение, на которое пошаговое выполнение при переборе с `first` до `last` . Шаг должен быть положительным. [invalid_argument](../../../standard-library/invalid-argument-class.md) создается, если шаг меньше 1.

*_Func*<br/>
Функция, выполняемая при каждой итерации. Это может быть лямбда-выражение, указатель функции или любой объект, который поддерживает версию оператора вызова функции с сигнатурой `void operator()(_Index_type)` .

*_Part*<br/>
Ссылка на объект-разделитель. Аргумент может быть одним из **`const`** [auto_partitioner](auto-partitioner-class.md) `&` , **`const`** [static_partitioner](static-partitioner-class.md) `&` , **`const`** [simple_partitioner](simple-partitioner-class.md) `&` или [affinity_partitioner](affinity-partitioner-class.md) `&` Если используется объект [affinity_partitioner](affinity-partitioner-class.md) , ссылка должна быть неконстантной ссылкой на левостороннее значение, чтобы алгоритм мог сохранить состояние для повторного использования циклов в будущем.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [Параллельные алгоритмы](../../../parallel/concrt/parallel-algorithms.md).

## <a name="parallel_for_each"></a><a name="parallel_for_each"></a> parallel_for_each

`parallel_for_each` применяет указанную функцию к каждому элементу в диапазоне параллельно. Эта функция семантически эквивалентна функции `for_each` в пространстве имен `std`, за исключением того, что итерация по элементам выполняется параллельно и порядок итерации не определен. Аргумент `_Func` должен поддерживать оператор вызова функции формы `operator()(T)`, где параметр `T` является типом элемента контейнера, для которого выполняется итерация.

```cpp
template <typename _Iterator, typename _Function>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func);

template <typename _Iterator, typename _Function, typename _Partitioner>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func,
    _Partitioner&& _Part);
```

### <a name="parameters"></a>Параметры

*_Iterator*<br/>
Тип итератора, используемого для прохода по контейнеру.

*_Function*<br/>
Тип функции, которая будет применена к каждому элементу в диапазоне.

*_Partitioner*<br/>
*first*<br/>
Итератор, обращающийся к положению первого элемента, который должен быть добавлен в параллельную итерацию.

*last*<br/>
Итератор, указывающий на точку, следующую за последним элементом для включения в параллельную итерацию.

*_Func*<br/>
Определяемый пользователем объект функции, применяемый к каждому элементу в диапазоне.

*_Part*<br/>
Ссылка на объект-разделитель. Аргумент может быть одним из **`const`** [auto_partitioner](auto-partitioner-class.md) `&` , **`const`** [static_partitioner](static-partitioner-class.md) `&` , **`const`** [simple_partitioner](simple-partitioner-class.md) `&` или [affinity_partitioner](affinity-partitioner-class.md) `&` Если используется объект [affinity_partitioner](affinity-partitioner-class.md) , ссылка должна быть неконстантной ссылкой на левостороннее значение, чтобы алгоритм мог сохранить состояние для повторного использования циклов в будущем.

### <a name="remarks"></a>Примечания

[auto_partitioner](auto-partitioner-class.md) будет использоваться для перегрузки без явного разделителя.

Для итераторов, которые не поддерживают произвольный доступ, поддерживается только [auto_partitioner](auto-partitioner-class.md) .

Дополнительные сведения см. в разделе [Параллельные алгоритмы](../../../parallel/concrt/parallel-algorithms.md).

## <a name="parallel_invoke"></a><a name="parallel_invoke"></a> parallel_invoke

Выполняет объекты функции, предоставленные в виде параметров, в параллельном режиме и блокирует их до завершения выполнения. Каждый объект функции может быть лямбда-выражением, указателем на функцию или любым объектом, который поддерживает оператор вызова функции с подписью `void operator()()`.

```cpp
template <typename _Function1, typename _Function2>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2);

template <typename _Function1, typename _Function2, typename _Function3>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9,
    typename _Function10>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9,
    const _Function10& _Func10);
```

### <a name="parameters"></a>Параметры

*_Function1*<br/>
Тип первого объекта функции для параллельного выполнения.

*_Function2*<br/>
Тип второго объекта функции для параллельного выполнения.

*_Function3*<br/>
Тип третьего объекта функции для параллельного выполнения.

*_Function4*<br/>
Тип четвертого объекта функции для параллельного выполнения.

*_Function5*<br/>
Тип пятого объекта функции для параллельного выполнения.

*_Function6*<br/>
Тип шестого объекта функции для параллельного выполнения.

*_Function7*<br/>
Тип седьмого объекта функции для параллельного выполнения.

*_Function8*<br/>
Тип восьмого объекта функции для параллельного выполнения.

*_Function9*<br/>
Тип девятого объекта функции для параллельного выполнения.

*_Function10*<br/>
Тип десятого объекта функции для параллельного выполнения.

*_Func1*<br/>
Первый объект функции для параллельного выполнения.

*_Func2*<br/>
Второй объект функции для параллельного выполнения.

*_Func3*<br/>
Третий объект функции для параллельного выполнения.

*_Func4*<br/>
Четвертый объект функции для параллельного выполнения.

*_Func5*<br/>
Пятый объект функции для параллельного выполнения.

*_Func6*<br/>
Шестой объект функции для параллельного выполнения.

*_Func7*<br/>
Седьмой объект функции для параллельного выполнения.

*_Func8*<br/>
Восьмой объект функции для параллельного выполнения.

*_Func9*<br/>
Девятый объект функции для параллельного выполнения.

*_Func10*<br/>
Десятый объект функции для параллельного выполнения.

### <a name="remarks"></a>Примечания

Обратите внимание, что один или несколько объектов функций, переданных в качестве параметров, могут выполняться встроенным образом в вызывающем контексте.

Если один или несколько объектов функций, переданных в качестве параметров этой функции, вызывают исключение, среда выполнения выберет одно такое исключение и распространяет его из вызова `parallel_invoke` .

Дополнительные сведения см. в разделе [Параллельные алгоритмы](../../../parallel/concrt/parallel-algorithms.md).

## <a name="parallel_radixsort"></a><a name="parallel_radixsort"></a> parallel_radixsort

Располагает элементы в указанном диапазоне в неубывающем порядке, используя алгоритм сортировки основания системы счисления. Это стабильная функция сортировки, для которой требуется функция проекции, способная проецировать сортируемые элементы в неподписанные ключи целочисленного типа. Для сортируемых элементов требуется инициализация по умолчанию.

```cpp
template<typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator, typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator, typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);
```

### <a name="parameters"></a>Параметры

*_Random_iterator*<br/>
Тип итератора входного диапазона.

*_Allocator*<br/>
Тип стандартной библиотеки C++, совместимой с механизмом выделения памяти.

*_Function*<br/>
Тип функции проекции.

*_Begin*<br/>
Итератор произвольного доступа, обращающийся к позиции первого элемента в сортируемом диапазоне.

*_End*<br/>
Итератор произвольного доступа, обращающийся к позиции после последнего элемента в сортируемом диапазоне.

*_Alloc*<br/>
Экземпляр стандартной библиотеки C++, совместимый с механизмом выделения памяти.

*_Proj_func*<br/>
Определяемый пользователем объект функции проекции, который преобразует элемент в целочисленное значение.

*_Chunk_size*<br/>
Минимальный размер блока, который будет разбит на два для параллельного выполнения.

### <a name="remarks"></a>Примечания

Для всех перегрузок требуется `n * sizeof(T)` дополнительное пространство, где `n` — количество элементов для сортировки, а `T` — тип элемента. Унарная проекция, функтор с сигнатурой `I _Proj_func(T)` , необходима для возвращения ключа при заданном элементе, где `T` — это тип элемента, а `I` — тип, являющийся целочисленным типом без знака.

Если функция проекции не указана, функция проекции по умолчанию, которая просто возвращает элемент, используется для целочисленных типов. Функция не сможет выполнить компиляцию, если элемент не является целочисленным типом в отсутствие функции проекции.

Если не указать тип или экземпляр распределителя, `std::allocator<T>` для выделения буфера используется распределитель памяти стандартной библиотеки C++.

Алгоритм делит входной диапазон на два блока и последовательно делит каждый блок на два подблока для параллельного выполнения. Необязательный аргумент `_Chunk_size` может использоваться для обозначения алгоритма, что он должен обрабатывать блоки размера < `_Chunk_size` последовательно.

## <a name="parallel_reduce"></a><a name="parallel_reduce"></a> parallel_reduce

Параллельно вычисляет сумму всех элементов в указанном диапазоне путем вычисления последовательных частичных сумм или вычисляет результаты последовательных частичных сумм, полученных сходным образом с использованием указанной бинарной операции, отличной от суммирования. `parallel_reduce` семантически аналогичен `std::accumulate`, но требует, чтобы бинарная операция была ассоциативна, а также значение идентификатора вместо начального значения.

```cpp
template<typename _Forward_iterator>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity);

template<typename _Forward_iterator, typename _Sym_reduce_fun>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity,
    _Sym_reduce_fun _Sym_fun);

template<typename _Reduce_type,
    typename _Forward_iterator,
    typename _Range_reduce_fun,
    typename _Sym_reduce_fun>
inline _Reduce_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const _Reduce_type& _Identity,
    const _Range_reduce_fun& _Range_fun,
    const _Sym_reduce_fun& _Sym_fun);
```

### <a name="parameters"></a>Параметры

*_Forward_iterator*<br/>
Тип итератора диапазона ввода.

*_Sym_reduce_fun*<br/>
Тип функции симметричной редукции. Это должен быть тип функции с сигнатурой `_Reduce_type _Sym_fun(_Reduce_type, _Reduce_type)`, где _Reduce_type совпадает с типом идентификатора и типом результата редукции. В третьей перегрузке он должен быть совместим с типом вывода `_Range_reduce_fun`.

*_Reduce_type*<br/>
Тип, до которого будет редуцирован ввод, который может отличаться от типа входного элемента. Возвращаемое значение и значение идентификатора будут иметь этот тип.

*_Range_reduce_fun*<br/>
Тип функции редукции диапазона. Это должен быть тип функции с сигнатурой `_Reduce_type _Range_fun(_Forward_iterator, _Forward_iterator, _Reduce_type)`, _Reduce_type совпадает с типом идентификатора и типом результата редукции.

*_Begin*<br/>
Итератор ввода, указывающий на первый элемент в диапазоне для редукции.

*_End*<br/>
Итератор ввода, указывающий на позицию после последнего элемента в диапазоне для редукции.

*_Identity*<br/>
Значение идентификатора `_Identity` относится к тому же типу, что и результат редукции, а также совпадает с `value_type` итератора для первой и второй перегрузок. В третьей перегрузке значение идентификатора должно иметь тот же тип, что и результат редукции, но может отличаться от `value_type` итератора. Оно должно иметь такое соответствующее значение, чтобы оператор редукции диапазона `_Range_fun`, примененный к диапазону из единственного элемента типа `value_type` и значению идентификатора, вел себя подобно приведению типа этого значения из типа `value_type` в тип идентификатора.

*_Sym_fun*<br/>
Симметричная функция, которая будет использоваться на второй стадии редукции. Дополнительные сведения см. в примечаниях.

*_Range_fun*<br/>
Симметричная функция, которая будет использоваться на первой стадии редукции. Дополнительные сведения см. в примечаниях.

### <a name="return-value"></a>Возвращаемое значение

Результат редукции.

### <a name="remarks"></a>Примечания

Для выполнения параллельной редукции функция делит диапазон на блоки на основе количества работников, доступных базовому планировщику. Редукция происходит в две стадии, на первой стадии выполняется редукция в каждом блоке, на второй стадии выполняется редукция частичных результатов из каждого блока.

Первая перегрузка требует, чтобы типы итератора `value_type` и `T` были такими же, как и тип значения идентификатора и тип результата редукции. Тип элемента T должен предоставить оператор `T T::operator + (T)`, чтобы выполнить редукцию элементов в каждом блоке. Тот же оператор используется на второй стадии.

Вторая перегрузка также требует, чтобы тип итератора `value_type` был таким же, как и тип значения идентификатора и тип результата редукции. Предоставленный бинарный оператор `_Sym_fun` используется на обеих стадиях редукции со значением идентификатора в качестве начального значения для первой стадии.

В третьей перегрузке тип значения идентификатора должен совпадать с типом результата редукции, но `value_type` итератора может отличаться от них. Функция редукции диапазона `_Range_fun` используется на первой стадии со значением идентификатора в качестве начального значения, а бинарная функция `_Sym_reduce_fun` применяется к промежуточным результатам на второй стадии.

## <a name="parallel_sort"></a><a name="parallel_sort"></a> parallel_sort

Упорядочивает элементы в указанном диапазоне в порядке убывания или в соответствии с критерием упорядочивания, заданным бинарным предикатом, в Parallel. Эта функция семантически схожа с `std::sort`, так как она основана на сравнении, неустойчива, сортирует на месте.

```cpp
template<typename _Random_iterator>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,typename _Function>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```

### <a name="parameters"></a>Параметры

*_Random_iterator*<br/>
Тип итератора входного диапазона.

*_Function*<br/>
Тип бинарного функтора сравнения.

*_Begin*<br/>
Итератор произвольного доступа, обращающийся к позиции первого элемента в сортируемом диапазоне.

*_End*<br/>
Итератор произвольного доступа, обращающийся к позиции после последнего элемента в сортируемом диапазоне.

*_Func*<br/>
Определяемый пользователем объект функции предиката, который определяет критерии сравнения, которые должны соблюдаться идущими подряд элементами при упорядочении. Бинарный предикат принимает два аргумента и возвращает значение, если они **`true`** удовлетворены и **`false`** не удовлетворены. Эта функция средства сравнения должна задать строгое слабое упорядочение пар элементов последовательности.

*_Chunk_size*<br/>
Минимальный размер фрагмента, который будет разбит на два для параллельного выполнения.

### <a name="remarks"></a>Примечания

Первая перегрузка использует двоичное средство сравнения `std::less` .

Вторая перегрузка использует предоставленное бинарное средство сравнения, которое должно иметь сигнатуру `bool _Func(T, T)`, где `T` — тип элементов во входном диапазоне.

Алгоритм делит входной диапазон на два блока и последовательно делит каждый блок на два подблока для параллельного выполнения. Необязательный аргумент `_Chunk_size` может использоваться для обозначения алгоритма, что он должен обрабатывать блоки размера < `_Chunk_size` последовательно.

## <a name="parallel_transform"></a><a name="parallel_transform"></a> parallel_transform

Применяет заданный объект функции к каждому элементу в исходном диапазоне или к паре элементов из двух исходных диапазонов и параллельно копирует возвращаемые значения объекта функции в диапазон назначения. Эта функция семантически эквивалентна `std::transform`.

```cpp
template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const static_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const simple_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    affinity_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator,
    typename _Partitioner>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op,
    _Partitioner&& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op);
```

### <a name="parameters"></a>Параметры

*_Input_iterator1*<br/>
Тип первого или единственного итератора ввода.

*_Output_iterator*<br/>
Тип итератора вывода.

*_Unary_operator*<br/>
Тип унарного функтора, который должен выполняться для каждого элемента во входном диапазоне.

*_Input_iterator2*<br/>
Тип второго итератора ввода.

*_Binary_operator*<br/>
Тип бинарного функтора, выполняемого попарно на элементах из двух исходных диапазонов.

*_Partitioner*<br/>
*first1*<br/>
Итератор ввода указывает на позицию первого элемента в первом или единственном исходном обрабатываемом диапазоне.

*last1*<br/>
Итератор ввода указывает на позицию, следующую за последним элементом в первом или единственном исходном обрабатываемом диапазоне.

*_Result*<br/>
Итератор вывода указывает на позицию первого элемента в диапазоне назначения.

*_Unary_op*<br/>
Определенный пользователем объект унарной функции, который применяется к каждому элементу в исходном диапазоне.

*_Part*<br/>
Ссылка на объект-разделитель. Аргумент может быть одним из **`const`** [auto_partitioner](auto-partitioner-class.md) `&` , **`const`** [static_partitioner](static-partitioner-class.md) `&` , **`const`** [simple_partitioner](simple-partitioner-class.md) `&` или [affinity_partitioner](affinity-partitioner-class.md) `&` Если используется объект [affinity_partitioner](affinity-partitioner-class.md) , ссылка должна быть неконстантной ссылкой на левостороннее значение, чтобы алгоритм мог сохранить состояние для повторного использования циклов в будущем.

*first2*<br/>
Итератор ввода указывает на позицию первого элемента во втором исходном обрабатываемом диапазоне.

*_Binary_op*<br/>
Определяемый пользователем объект бинарной функции, который последовательно применяется к парам элементов из двух исходных диапазонов.

### <a name="return-value"></a>Возвращаемое значение

Итератор вывода указывает на позицию после последнего элемента в диапазоне назначения, который получает выходные элементы, преобразованные объектом функции.

### <a name="remarks"></a>Примечания

[auto_partitioner](auto-partitioner-class.md) будет использоваться для перегрузок без явного аргумента разделителя.

Для итераторов, которые не поддерживают произвольный доступ, поддерживается только [auto_partitioner](auto-partitioner-class.md) .

Перегрузки, принимающие аргумент `_Unary_op`, преобразовывают диапазон ввода в диапазон вывода путем применения унарного функтора к каждому элементу в диапазоне ввода. `_Unary_op` должен поддерживать оператор вызова функции с сигнатурой `operator()(T)`, где `T` является типом значения диапазона, в котором выполняются итерации.

Перегрузки, принимающие аргумент `_Binary_op`, преобразовывают два диапазона ввода в диапазон вывода путем применения бинарного функтора к одному элементу из первого диапазона ввода и к одному элементу из второго диапазона ввода. `_Binary_op` должен поддерживать оператор вызова функции с сигнатурой `operator()(T, U)`, где `T`, `U` являются типами значений двух входных итераторов.

Дополнительные сведения см. в разделе [Параллельные алгоритмы](../../../parallel/concrt/parallel-algorithms.md).

## <a name="receive"></a><a name="receive"></a> получать

Общая реализация получения, позволяющая контексту ожидать данные строго из одного источника и фильтровать значения, которые принимаются.

```cpp
template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных.

*_Src*<br/>
Указатель или ссылка на источник, из которого должны быть возвращены данные.

*_Timeout*<br/>
Максимальное время, в течение которого метод должен иметь данные (в миллисекундах).

*_Filter_proc*<br/>
Функция фильтра, которая определяет, следует ли принимать сообщения.

### <a name="return-value"></a>Возвращаемое значение

Значение из источника типа полезных данных.

### <a name="remarks"></a>Примечания

Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE` , исключение [operation_timed_out](operation-timed-out-class.md) возникает, если срок действия указанного времени истекает до получения сообщения. Если необходимо указать время ожидания нулевой длины, следует использовать функцию [try_receive](concurrency-namespace-functions.md) , в отличие от вызова `receive` с временем ожидания `0` (нулем), так как это более эффективно и не создает исключения при превышении времени ожидания.

Дополнительные сведения см. в разделе [функции передачи сообщений](../../../parallel/concrt/message-passing-functions.md).

## <a name="run_with_cancellation_token"></a><a name="run_with_cancellation_token"></a> run_with_cancellation_token

Немедленно и синхронно выполняет объект функции в контексте заданного токена отмены.

```cpp
template<typename _Function>
void run_with_cancellation_token(
    const _Function& _Func,
    cancellation_token _Ct);
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Тип объекта функции, который будет вызываться.

*_Func*<br/>
Объект функции, который будет выполняться. Этот объект должен поддерживать оператор вызова функции с сигнатурой (void).

*_Ct*<br/>
Токен отмены, который будет управлять неявной отменой объекта функции. Если требуется выполнение функции без возможности неявной отмены из-за отмены родительской группы задач, следует использовать `cancellation_token::none()`.

### <a name="remarks"></a>Примечания

При отмене `cancellation_token` будут активированы все точки прерывания в объекте функции. Явный токен `_Ct` будет изолировать объект `_Func` от родительской отмены, если родитель имеет другой токен или вообще не имеет токена.

## <a name="send"></a><a name="send"></a> Отправить

Синхронная операции отправки, которая ожидает принятия или отклонения сообщения целевым объектом.

```cpp
template <class T>
bool send(_Inout_ ITarget<T>* _Trg, const T& _Data);

template <class T>
bool send(ITarget<T>& _Trg, const T& _Data);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных.

*_Trg*<br/>
Указатель или ссылка на целевой объект, в который отправляются данные.

*_Data*<br/>
Ссылка на отправляемые данные.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если сообщение было принято; **`false`** в противном случае —.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [функции передачи сообщений](../../../parallel/concrt/message-passing-functions.md).

## <a name="set_ambient_scheduler"></a><a name="set_ambient_scheduler"></a> set_ambient_scheduler

```cpp
inline void set_ambient_scheduler(std::shared_ptr<::Concurrency::scheduler_interface> _Scheduler);
```

### <a name="parameters"></a>Параметры

*_Scheduler*<br/>
Задается внешний планировщик.

## <a name="set_task_execution_resources"></a><a name="set_task_execution_resources"></a> set_task_execution_resources

Ограничивает ресурсы выполнения, используемые внутренними рабочими потоками среды выполнения с параллелизмом, определенным набором сходства.

Этот метод можно вызывать только до создания диспетчера ресурсов или между двумя периодами существования диспетчера ресурсов. Его можно вызывать несколько раз при условии, что в момент вызова диспетчер ресурсов не существует. После задания ограничения сходства оно будет оставаться действительным до следующего допустимого вызова метода `set_task_execution_resources`.

Предоставленная маска сходства не обязана быть подмножеством маски сходства процесса. Сходство процесса обновляется при необходимости.

```cpp
void __cdecl set_task_execution_resources(
    DWORD_PTR _ProcessAffinityMask);

void __cdecl set_task_execution_resources(
    unsigned short count,
    PGROUP_AFFINITY _PGroupAffinity);
```

### <a name="parameters"></a>Параметры

*_ProcessAffinityMask*<br/>
Маска сходства, которой должны быть ограничены рабочие потоки среды выполнения с параллелизмом. Используйте этот метод в системе с более чем 64 аппаратными потоками, только если требуется ограничить среду выполнения с параллелизмом подмножеством текущей группы процессоров. Как правило, следует использовать версию метода, которая принимает массив сходств группы в качестве параметра, чтобы ограничить сходство на компьютерах с более чем 64 аппаратными потоками.

*count*<br/>
Количество записей `GROUP_AFFINITY` в массиве, заданном параметром `_PGroupAffinity`.

*_PGroupAffinity*<br/>
Массив записей `GROUP_AFFINITY`.

### <a name="remarks"></a>Примечания

Метод вызовет исключение [invalid_operation](invalid-operation-class.md) , если диспетчер ресурсов имеется в момент вызова, и [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если указанное сходство приводит к пустому набору ресурсов.

Версию метода, принимающую массив сходств группы в качестве параметра, следует использовать только в операционных системах Windows версии 7 и выше. В противном случае выдается исключение [invalid_operation](invalid-operation-class.md) .

Программное изменение сходства процессов после вызова этого метода не приведет к тому, что диспетчер ресурсов повторно вычислит сходство, с которым он ограничен. Таким образом, все изменения сходства процесса необходимо сделать до вызова этого метода.

## <a name="swap"></a><a name="swap"></a> позиции

Меняет местами элементы двух объектов `concurrent_vector`.

```cpp
template<typename T, class _Ax>
inline void swap(
    concurrent_vector<T, _Ax>& _A,
    concurrent_vector<T, _Ax>& _B);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных элементов, хранящихся в параллельных векторах.

*_Ax*<br/>
Тип распределителя параллельных векторов.

*_A*<br/>
Параллельный вектор, элементы которого должны быть заменены элементами параллельного вектора `_B` .

*_B*<br/>
Параллельный вектор, предоставляющий элементы для обмена, или вектор, элементы которого должны быть заменены на объекты параллельного вектора `_A` .

### <a name="remarks"></a>Примечания

Функция-шаблон — это алгоритм, специализированный для класса контейнера `concurrent_vector` для выполнения функции- `_A` члена. [concurrent_vector:: Swap](concurrent-vector-class.md#swap)( `_B` ). Это экземпляры частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, `template <class T> void swap(T&, T&)` в классе algorithm, работает по назначению и является очень высокой операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

Этот метод не является типобезопасным в режиме параллелизма. Необходимо убедиться, что никакие другие потоки не выполняют операции с одним из параллельных векторов при вызове этого метода.

## <a name="task_from_exception"></a><a name="task_from_exception"></a> task_from_exception

```cpp
template<typename _TaskType, typename _ExType>
task<_TaskType> task_from_exception(
    _ExType _Exception,
    const task_options& _TaskOptions = task_options());
```

### <a name="parameters"></a>Параметры

*_TaskType*<br/>

*_ExType*<br/>

*_Exception*<br/>

*_TaskOptions*<br/>

### <a name="return-value"></a>Возвращаемое значение

## <a name="task_from_result"></a><a name="task_from_result"></a> task_from_result

```cpp
template<typename T>
task<T> task_from_result(
    T _Param,
    const task_options& _TaskOptions = task_options());

inline task<bool> task_from_result(ool _Param);

inline task<void> task_from_result(
    const task_options& _TaskOptions = task_options());
```

### <a name="parameters"></a>Параметры

*T*<br/>

*_Param*<br/>

*_TaskOptions*<br/>

### <a name="return-value"></a>Возвращаемое значение

## <a name="trace_agents_register_name"></a><a name="trace_agents_register_name"></a> Trace_agents_register_name

Связывает данное имя с блоком сообщений или агентом в трассировки событий Windows.

```cpp
template <class T>
void Trace_agents_register_name(
    _Inout_ T* _PObject,
    _In_z_ const wchar_t* _Name);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта. Обычно это блок сообщений или агент.

*_PObject*<br/>
Указатель на блок сообщений или агент, который именован в трассировке.

*_Name*<br/>
Имя для заданного объекта.

## <a name="try_receive"></a><a name="try_receive"></a> try_receive

Общая реализация проверки-получения, позволяющая контексту выполнять поиск данных строго из одного источника и фильтровать значения, которые принимаются. Если данные не готовы, метод возвратит значение **`false`** .

```cpp
template <class T>
bool try_receive(_Inout_ ISource<T>* _Src, T& _value);

template <class T>
bool try_receive(
    _Inout_ ISource<T>* _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);

template <class T>
bool try_receive(ISource<T>& _Src, T& _value);

template <class T>
bool try_receive(
    ISource<T>& _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных

*_Src*<br/>
Указатель или ссылка на источник, из которого должны быть возвращены данные.

*_value*<br/>
Ссылка на расположение, куда будет помещен результат.

*_Filter_proc*<br/>
Функция фильтра, которая определяет, следует ли принимать сообщения.

### <a name="return-value"></a>Возвращаемое значение

**`bool`** Значение, указывающее, помещены ли полезные данные в `_value` .

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [функции передачи сообщений](../../../parallel/concrt/message-passing-functions.md).

## <a name="wait"></a><a name="wait"></a> ожидания

Приостанавливает текущий контекст на указанный период времени.

```cpp
void __cdecl wait(unsigned int _Milliseconds);
```

### <a name="parameters"></a>Параметры

*_Milliseconds*<br/>
Число миллисекунд, на которое должен быть приостановлен текущий контекст. Если параметру `_Milliseconds` задано значение `0`, текущий контекст должен уступить выполнение другим работоспособным контекстам перед продолжением.

### <a name="remarks"></a>Примечания

Если этот метод вызывается в контексте планировщика среда выполнения с параллелизмом, планировщик найдет другой контекст для выполнения на базовом ресурсе. Поскольку планировщик предназначен для совместной работы по своей природе, этот контекст не может возобновиться точно после указанного числа миллисекунд. Если планировщик занят выполнением других задач, которые не уступают планировщику совместно, период ожидания может быть не ограничен.

## <a name="when_all"></a><a name="when_all"></a> when_all

Создает задачу, которая завершается успешно, если все задачи, предоставленные в качестве аргументов, завершаются успешно.

```cpp
template <typename _Iterator>
auto when_all(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options()) ->
    decltype (details::_WhenAllImpl<typename std::iterator_traits<_Iterator>::value_type::result_type,
    _Iterator>::_Perform(_TaskOptions, _Begin,  _End));
```

### <a name="parameters"></a>Параметры

*_Iterator*<br/>
Тип итератора ввода.

*_Begin*<br/>
Позиция первого элемента в диапазоне элементов, которые будут объединены в результирующую задачу.

*_End*<br/>
Позиция первого элемента за пределами диапазона элементов, которые будут объединены в результирующую задачу.

*_TaskOptions*<br/>
Объект `task_options`.

### <a name="return-value"></a>Возвращаемое значение

Задача, которая завершается успешно после успешного завершения всех входных задач. Если входные задачи относятся к типу `T`, выводом этой функции будет `task<std::vector<T>>`. Если входные задачи относятся к типу, **`void`** задача вывода также будет иметь тип `task<void>` .

### <a name="remarks"></a>Примечания

Функция `when_all` является функцией без блокировки, в качестве результата создающей `task`. В отличие от [Task:: wait](task-class.md#wait), эту функцию можно вызывать в приложении UWP в потоке ASTA (Application STA).

Если одна из задач отменена или вызывает исключение, возвращаемая задача будет завершена на раннем этапе, в состоянии Canceled, а исключение, если оно произошло, будет вызываться при вызове [задачи:: Get](task-class.md#get) или `task::wait` в этой задаче.

Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="when_any"></a><a name="when_any"></a> when_any

Создает задачу, которая завершается успешно, если любая из задач, предоставленных в качестве аргументов, завершается успешно.

```cpp
template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options())
    -> decltype (
        details::_WhenAnyImpl<
            typename std::iterator_traits<_Iterator>::value_type::result_type,
            _Iterator>::_Perform(_TaskOptions, _Begin, _End));

template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    cancellation_token _CancellationToken)
       -> decltype (
           details::_WhenAnyImpl<
               typename std::iterator_traits<_Iterator>::value_type::result_type,
               _Iterator>::_Perform(_CancellationToken._GetImplValue(), _Begin, _End));
```

### <a name="parameters"></a>Параметры

*_Iterator*<br/>
Тип итератора ввода.

*_Begin*<br/>
Позиция первого элемента в диапазоне элементов, которые будут объединены в результирующую задачу.

*_End*<br/>
Позиция первого элемента за пределами диапазона элементов, которые будут объединены в результирующую задачу.

*_TaskOptions*<br/>
*_CancellationToken*<br/>
Токен отмены, который контролирует отмену возвращаемой задачи. Если токен отмены отсутствует, результирующая задача получит токен отмены, который используется для выполнения задачи.

### <a name="return-value"></a>Возвращаемое значение

Задача, которая завершается успешно, если все входные задачи завершены успешно. Если входные задачи имеют тип `T`, выходными данными этой функции будут `task<std::pair<T, size_t>>>`, где первый элемент пары является результатом завершаемой задачи, а второй элемент — индексом завершенной задачи. Если входные задачи имеют тип Output, то в результате получается **`void`** `task<size_t>` индекс задачи завершения.

### <a name="remarks"></a>Примечания

Функция `when_any` является функцией без блокировки, в качестве результата создающей `task`. В отличие от [Task:: wait](task-class.md#wait), эту функцию можно вызывать в приложении UWP в потоке ASTA (Application STA).

Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)
