---
title: Практическое руководство. Создание задачи, выполняемой после задержки
ms.date: 11/04/2016
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
ms.openlocfilehash: 76189f45eb486e06b040155f6697bf003659b474
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141747"
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>Практическое руководство. Создание задачи, выполняемой после задержки

В этом примере показано, как использовать классы [concurrency::Task](../../parallel/concrt/reference/task-class.md), [concurrency::cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md), [concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md), [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), [concurrency::Timer](../../parallel/concrt/reference/timer-class.md)и [concurrency::Call](../../parallel/concrt/reference/call-class.md) для создания задачи, которая завершается после некоторой задержки. Этот метод можно использовать для создания циклов, которые иногда запрашивают данные, используют время ожидания, задерживают обработку вводимых пользователем данных на заранее определенное время и т. д.

## <a name="example"></a>Пример

В следующем примере показаны функции `complete_after` и `cancel_after_timeout`. Функция `complete_after` создает объект `task`, который выполняется после заданной задержки. Она использует объект `timer` и объект `call` для установки объекта `task_completion_event` после заданной задержки. С помощью класса `task_completion_event` можно определить задачу, которая выполняется после того, как поток или другая задача сообщает, что значение доступно. Когда событие установлено, задачи прослушивателя выполняются и их продолжения планируются для запуска.

> [!TIP]
> Дополнительные сведения о классах `timer` и `call`, которые являются частью библиотеки асинхронных агентов, см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

Функция `cancel_after_timeout` основана на функции `complete_after` и используется для отмены задачи, если эта задача не завершается до истечения заданного времени ожидания. Функция `cancel_after_timeout` создает две задачи. Первая задача указывает на успешное завершение и выполняется после завершения предоставленной задачи; вторая задача указывает на неудачный результат и выполняется после истечения заданного времени ожидания. Функция `cancel_after_timeout` создает задачу продолжения, которая выполняется после выполнения задачи, связанной с успешным или неудачным результатом. Если задача, связанная с неудачным результатом, завершается первой, продолжение отменяет источник токена для отмены всей задачи.

[!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]

## <a name="example"></a>Пример

В следующем примере вычисляется количество простых чисел в диапазоне [0, 100000] несколько раз. Операция завершается неудачей, если она не выполняется полностью за указанное время. Функция `count_primes` демонстрирует, как использовать функцию `cancel_after_timeout`. Она подсчитывает количество простых чисел в заданном диапазоне и завершается неудачей, если задача не выполняется за предоставленное время. Функция `wmain` несколько раз вызывает функцию `count_primes`. Каждый раз она сокращает выделенное время в два раза. Программа завершается после того, как операция не выполняется за выделенное время.

[!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]

При использовании этого метода для отмены задачи после задержки все незапущенные задачи не запускаются после того, как отменяется общая задача. Однако важно, чтобы все продолжительные задачи реагировали на отмену своевременно. Дополнительные сведения об отмене задач см. [в разделе Отмена в библиотеке PPL](cancellation-in-the-ppl.md).

## <a name="example"></a>Пример

Ниже приведен полный код этого примера.

[!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем `task-delay.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

**CL. exe/EHsc ТАСК-делай. cpp**

## <a name="see-also"></a>См. также раздел

[Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Класс task (среда выполнения с параллелизмом)](../../parallel/concrt/reference/task-class.md)<br/>
[Класс cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md)<br/>
[Класс cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md)<br/>
[Класс task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)<br/>
[Класс timer](../../parallel/concrt/reference/timer-class.md)<br/>
[Класс call](../../parallel/concrt/reference/call-class.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)
