---
title: Пошаговое руководство. Использование среды выполнения с параллелизмом в приложениях с поддержкой модели COM
ms.date: 04/25/2019
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
ms.openlocfilehash: faa072ab2b5973ace0f0ca138dcedffa56044213
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140627"
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>Пошаговое руководство. Использование среды выполнения с параллелизмом в приложениях с поддержкой модели COM

В этом документе показано, как использовать среда выполнения с параллелизмом в приложении, использующем модель COM.

## <a name="prerequisites"></a>предварительные требования

Прежде чем приступить к работе с этим пошаговым руководством, прочитайте следующие документы:

- [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)

- [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)

- [Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

Дополнительные сведения о модели COM см. в разделе [компонентная объектная модель (com)](/windows/win32/com/component-object-model--com--portal).

## <a name="managing-the-lifetime-of-the-com-library"></a>Управление жизненным циклом библиотеки COM

Хотя использование COM с среда выполнения с параллелизмом следует тем же принципам, что и любой другой механизм параллелизма, следующие рекомендации помогут эффективно использовать эти библиотеки.

- Прежде чем использовать библиотеку COM, поток должен вызвать [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) .

- Поток может вызывать `CoInitializeEx` несколько раз, пока он предоставляет одинаковые аргументы для каждого вызова.

- Для каждого вызова `CoInitializeEx`поток должен также вызывать [CoUninitialize](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize). Иными словами, вызовы `CoInitializeEx` и `CoUninitialize` должны быть сбалансированы.

- Чтобы переключиться с одного подразделения потока на другой, поток должен полностью освободить библиотеку COM перед вызовом `CoInitializeEx` с новой спецификацией потоков.

Другие принципы COM применяются при использовании COM с среда выполнения с параллелизмом. Например, приложение, которое создает объект в однопотоковом подразделении (STA) и маршалирует объект в другое подразделение, также должно предоставить цикл обработки сообщений, обрабатывающий входящие сообщения. Также помните, что маршалирование объектов между апартаментами может привести к снижению производительности.

### <a name="using-com-with-the-parallel-patterns-library"></a>Использование COM с библиотекой параллельных шаблонов

При использовании COM с компонентом в библиотеке параллельных шаблонов (PPL), например в группе задач или параллельном алгоритме, вызывайте `CoInitializeEx` перед использованием библиотеки COM во время каждой задачи или итерации и вызовите `CoUninitialize` до завершения каждой задачи или итерации. В следующем примере показано, как управлять временем существования библиотеки COM с помощью объекта [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) .

[!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]

Необходимо убедиться, что библиотека COM правильно освобождена при отмене задачи или параллельного алгоритма или в случае, если тело задачи создает исключение. Чтобы гарантировать вызов задачи `CoUninitialize` перед ее завершением, используйте блок `try-finally` или шаблон " *получение ресурсов* " (RAII). В следующем примере используется блок `try-finally` для высвобождения библиотеки COM по завершении или отмене задачи или при возникновении исключения.

[!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]

В следующем примере шаблон RAII используется для определения класса `CCoInitializer`, который управляет временем существования библиотеки COM в данной области.

[!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]

Можно использовать класс `CCoInitializer`, чтобы автоматически освободить библиотеку COM при завершении задачи, как показано ниже.

[!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]

Дополнительные сведения об отмене в среда выполнения с параллелизмом см. [в разделе об отмене в PPL](cancellation-in-the-ppl.md).

### <a name="using-com-with-asynchronous-agents"></a>Использование COM с асинхронными агентами

При использовании COM с асинхронными агентами вызывайте `CoInitializeEx` перед использованием библиотеки COM в методе [concurrency::Agent:: Run](reference/agent-class.md#run) для агента. Затем вызовите `CoUninitialize` перед возвратом метода `run`. Не используйте подпрограммы управления COM в конструкторе или деструкторе агента и не переопределяйте [concurrency::Agent:: Start](reference/agent-class.md#start) или [concurrency::Agent::d один](reference/agent-class.md#done) метод, так как эти методы вызываются из другого потока, чем метод `run`.

В следующем примере показан базовый класс агента с именем `CCoAgent`, который управляет библиотекой COM в методе `run`.

[!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]

Полный пример приведен далее в этом пошаговом руководстве.

### <a name="using-com-with-lightweight-tasks"></a>Использование COM с упрощенными задачами

В документе [планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md) описывается роль упрощенных задач в среда выполнения с параллелизмом. Можно использовать COM с упрощенной задачей точно так же, как и с любой подпрограммой потока, передаваемым в функцию `CreateThread` в Windows API. Это показано в следующем примере.

[!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]

## <a name="an-example-of-a-com-enabled-application"></a>Пример приложения с поддержкой COM

В этом разделе показано полное приложение с поддержкой COM, которое использует интерфейс `IScriptControl` для выполнения сценария, который выполняет вычисление n-<sup>го</sup> числа Фибоначчи. Этот пример сначала вызывает скрипт из основного потока, а затем использует PPL и агенты для параллельного вызова скрипта.

Рассмотрим следующую вспомогательную функцию, `RunScriptProcedure`, которая вызывает процедуру в объекте `IScriptControl`.

[!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]

Функция `wmain` создает объект `IScriptControl`, добавляет к нему код скрипта, который выполняет вычисление n-<sup>го</sup> числа Фибоначчи, а затем вызывает функцию `RunScriptProcedure` для выполнения этого скрипта.

[!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]

### <a name="calling-the-script-from-the-ppl"></a>Вызов скрипта из PPL

Следующая функция, `ParallelFibonacci`, использует алгоритм [параллелизма::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) для параллельного вызова скрипта. Эта функция использует класс `CCoInitializer` для управления временем существования библиотеки COM во время каждой итерации задачи.

[!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]

Чтобы использовать функцию `ParallelFibonacci` с примером, добавьте следующий код перед возвратом функции `wmain`.

[!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]

### <a name="calling-the-script-from-an-agent"></a>Вызов скрипта из агента

В следующем примере показан класс `FibonacciScriptAgent`, который вызывает процедуру скрипта для расчета n-<sup>го</sup> числа Фибоначчи. Класс `FibonacciScriptAgent` использует передачу сообщения для получения из основной программы, входные значения в функцию скрипта. Метод `run` управляет временем существования библиотеки COM во всей задаче.

[!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]

Следующая функция, `AgentFibonacci`, создает несколько `FibonacciScriptAgent` объектов и использует передачу сообщений для отправки нескольких входных значений в эти объекты.

[!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]

Чтобы использовать функцию `AgentFibonacci` с примером, добавьте следующий код перед возвратом функции `wmain`.

[!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]

### <a name="the-complete-example"></a>Полный пример

В следующем коде показан полный пример, в котором используются параллельные алгоритмы и асинхронные агенты для вызова процедуры сценария, которая выполняет вычисление чисел Фибоначчи.

[!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]

В примере выводится следующий пример выходных данных.

```Output
Main Thread:
fib(15) = 610

Parallel Fibonacci:
fib(15) = 610
fib(10) = 55
fib(16) = 987
fib(18) = 2584
fib(11) = 89
fib(17) = 1597
fib(19) = 4181
fib(12) = 144
fib(13) = 233
fib(14) = 377

Agent Fibonacci:
fib(30) = 832040
fib(22) = 17711
fib(10) = 55
fib(12) = 144
```

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `parallel-scripts.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc Параллел-скриптс. cpp/Link ole32. lib**

## <a name="see-also"></a>См. также раздел

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)<br/>
[Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)<br/>
[Планировщик заданий](../../parallel/concrt/task-scheduler-concurrency-runtime.md)
