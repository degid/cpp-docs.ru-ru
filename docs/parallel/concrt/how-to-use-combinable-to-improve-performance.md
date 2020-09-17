---
title: Практическое руководство. Использование класса combinable для повышения производительности
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
ms.openlocfilehash: db27a791b2b92102118606712db4cbd2920f9619
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142432"
---
# <a name="how-to-use-combinable-to-improve-performance"></a>Практическое руководство. Использование класса combinable для повышения производительности

В этом примере показано, как использовать класс [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) для вычисления суммы чисел в объекте [std:: Array](../../standard-library/array-class-stl.md) , являющихся простыми. Класс `combinable` повышает производительность, исключая общее состояние.

> [!TIP]
> В некоторых случаях параллельное отображение ([concurrency::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) и reduce ([concurrency::parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)) могут повысить производительность по сравнению с `combinable`. Пример, использующий операции Map и reduce для получения тех же результатов, что и в этом примере, см. в разделе [parallelических алгоритмов](../../parallel/concrt/parallel-algorithms.md).

## <a name="example---accumulate"></a>Пример накопления

В следующем примере используется функция [std:: accumulate](../../standard-library/numeric-functions.md#accumulate) для вычисления суммы элементов в массиве, которые являются простыми. В этом примере `a` является `array`ным объектом, а функция `is_prime` определяет, является ли входное значение простым.

[!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]

## <a name="example---parallel_for_each"></a>Пример — parallel_for_each

В следующем примере показан наивный способ параллелизации предыдущего примера. В этом примере используется алгоритм [arallel_for_each Concurrency::p](reference/concurrency-namespace-functions.md#parallel_for_each) для параллельной обработки массива и объекта [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) для синхронизации доступа к переменной `prime_sum`. Этот пример не масштабируется, так как каждый поток должен ждать, пока общий ресурс станет доступным.

[!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]

## <a name="example---combinable"></a>Пример — комбинированный

В следующем примере используется объект `combinable` для повышения производительности предыдущего примера. В этом примере устраняется необходимость в объектах синхронизации. он масштабируется, так как объект `combinable` позволяет каждому потоку выполнять свою задачу независимо.

Объект `combinable` обычно используется в двух шагах. Во-первых, можно создать ряд детализированных вычислений, параллельно выполняя работу. Затем объедините (или уменьшите) вычисления в окончательный результат. В этом примере используется метод [concurrency::combinable:: local](reference/combinable-class.md#local) для получения ссылки на локальную сумму. Затем он использует метод [concurrency::combinable:: Combine](reference/combinable-class.md#combine) и объект [std::p них](../../standard-library/plus-struct.md) для объединения локальных вычислений в окончательный результат.

[!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]

## <a name="example---serial-and-parallel"></a>Пример — последовательный и параллельный

Следующий полный пример вычисляет сумму простых чисел как последовательно, так и параллельно. В примере на консоль выводится время, необходимое для выполнения обоих вычислений.

[!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]

В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.

```Output
1709600813
serial time: 6178 ms

1709600813
parallel time: 1638 ms
```

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем `parallel-sum-of-primes.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc Параллел-сум-оф-примес. cpp**

## <a name="robust-programming"></a>Отказоустойчивость

Пример, в котором для получения одинаковых результатов используются операции Map и reduce, см. в разделе [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

## <a name="see-also"></a>См. также раздел

[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Класс combinable](../../parallel/concrt/reference/combinable-class.md)<br/>
[Класс critical_section](../../parallel/concrt/reference/critical-section-class.md)
