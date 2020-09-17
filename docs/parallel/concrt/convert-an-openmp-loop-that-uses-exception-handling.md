---
title: Практическое руководство. Преобразование цикла OpenMP, использующего обработку исключений для использования среды выполнения с параллелизмом
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling, converting from OpenMP to the Concurrency Runtime
- converting from OpenMP to the Concurrency Runtime, exception handling
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
ms.openlocfilehash: 380a96eedb8a70965197c4a5ce0c5199bc268db5
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141812"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-exception-handling-to-use-the-concurrency-runtime"></a>Практическое руководство. Преобразование цикла OpenMP, использующего обработку исключений для использования среды выполнения с параллелизмом

В этом примере показано, как преобразовать [параллельный](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)цикл[for](../../parallel/openmp/reference/for-openmp.md) OpenMP, выполняющий обработку исключений, для использования механизма обработки исключений среда выполнения с параллелизмом.

В OpenMP исключение, создаваемое в параллельной области, должно быть перехвачено и обработано в том же регионе, что и тот же поток. Исключение, управляющее параллельной областью, перехватывается обработчиком необработанных исключений, который по умолчанию завершает процесс.

В среда выполнения с параллелизмом при возникновении исключения в теле рабочей функции, которая передается в группу задач, например в объект [concurrency::task_group](reference/task-group-class.md) или [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) , или в параллельный алгоритм, такой как [:parallel_for](reference/concurrency-namespace-functions.md#parallel_for), среда выполнения сохраняет это исключение и маршалирует его в контекст, который ожидает завершения выполнения группы задач или алгоритма. Для групп задач контекст ожидания — это контекст, вызывающий [concurrency::task_group:: wait](reference/task-group-class.md#wait), [concurrency::structured_task_group:: wait](reference/structured-task-group-class.md#wait), [concurrency::task_group:: run_and_wait](reference/task-group-class.md#run_and_wait)или [concurrency::structured_task_group:: run_and_wait](reference/structured-task-group-class.md#run_and_wait). Для параллельного алгоритма контекст ожидания является контекстом, который вызвал этот алгоритм. Среда выполнения также останавливает все активные задачи, которые находятся в группе задач, в том числе в дочерних группах задач, и удаляет все задачи, которые еще не запущены.

## <a name="example"></a>Пример

В этом примере показано, как выполнять обработку исключений в области `parallel` OpenMP и в вызове `parallel_for`. Функция `do_work` выполняет запрос на выделение памяти, который не удается выполнить, поэтому вызывает исключение типа [std:: bad_alloc](../../standard-library/bad-alloc-class.md). В версии, использующей OpenMP, поток, вызывающий исключение, также должен перехватывать его. Иными словами, каждая итерация параллельного цикла OpenMP должна справиться с исключением. В версии, которая использует среда выполнения с параллелизмом, основной поток перехватывает исключение, вызываемое другим потоком.

[!code-cpp[concrt-openmp#3](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-exception-handling_1.cpp)]

В этом примере формируются следующие данные:

```Output
Using OpenMP...
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
Using the Concurrency Runtime...
An error of type 'class std::bad_alloc' occurred.
```

В версии этого примера, использующей OpenMP, исключение возникает в и обрабатывается каждой итерацией цикла. В версии, которая использует среда выполнения с параллелизмом, среда выполнения сохраняет исключение, останавливает все активные задачи, отклоняет все задачи, которые еще не запущены, и маршалирует исключение в контекст, вызывающий `parallel_for`.

Если требуется, чтобы версия, использующая OpenMP, завершилась после возникновения исключения, можно использовать логический флаг, чтобы сообщить другим итерациям цикла, что произошла ошибка. Как и в примере в разделе [как преобразовать цикл OpenMP, использующий отмену, для использования среда выполнения с параллелизмом](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md), последующие итерации цикла не будут предпринимать никаких действий, если установлен флаг. И наоборот, если требуется, чтобы цикл, использующий среда выполнения с параллелизмом, продолжался после возникновения исключения, обработайте исключение в самом теле параллельного цикла.

Другие компоненты среда выполнения с параллелизмом, такие как асинхронные агенты и упрощенные задачи, не переносят исключения. Вместо этого необработанные исключения перехватываются обработчиком необработанных исключений, который по умолчанию завершает процесс. Дополнительные сведения об обработке исключений см. в разделе [обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

Дополнительные сведения о `parallel_for` и других параллельных алгоритмах см. в разделе [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `concrt-omp-exceptions.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc/OpenMP конкрт-ОМП-ексцептионс. cpp**

## <a name="see-also"></a>См. также раздел

[Переход от OpenMP к среде выполнения с параллелизмом](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Обработка исключений](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)
