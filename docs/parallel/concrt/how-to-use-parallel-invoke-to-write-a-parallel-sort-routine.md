---
title: Практическое руководство. Использование функции parallel_invoke для написания программы параллельной сортировки
ms.date: 11/04/2016
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
ms.openlocfilehash: 9d84cdbecb7cc6d39cb30077780c558db85888c0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222723"
---
# <a name="how-to-use-parallel_invoke-to-write-a-parallel-sort-routine"></a>Практическое руководство. Использование функции parallel_invoke для написания программы параллельной сортировки

В этом документе описывается использование алгоритма [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) для повышения производительности алгоритма битонной сортировки. Алгоритм битонной сортировки рекурсивно разделяет входную последовательность на меньшие отсортированные секции. Алгоритм битонной сортировки может выполняться параллельно, так как каждая операция секционирования не зависит от других операций.

Хотя битонной сортировка является примером *сети сортировки* , которая сортирует все сочетания входных последовательностей, в этом примере сортируются последовательности, длина которых равна двум.

> [!NOTE]
> В этом примере для демонстрации используется параллельная подпрограмма сортировки. Можно также использовать встроенные алгоритмы сортировки, предоставляемые PPL: [concurrency::p arallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [concurrency::p arallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort)и [concurrency::p arallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Дополнительные сведения см. в разделе [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

## <a name="sections"></a><a name="top"></a>Священ

В этом документе описаны следующие задачи.

- [Последовательный порядок выполнения битонной сортировки](#serial)

- [Использование parallel_invoke для выполнения битонной сортировки в параллельном режиме](#parallel)

## <a name="performing-bitonic-sort-serially"></a><a name="serial"></a>Последовательный порядок выполнения битонной сортировки

В следующем примере показана последовательная версия алгоритма битонной сортировки. `bitonic_sort`Функция разделяет последовательность на две секции, сортирует эти секции в противоположных направлениях, а затем объединяет результаты. Эта функция вызывает два раза рекурсивно для сортировки каждой секции.

[!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]

[[Top](#top)]

## <a name="using-parallel_invoke-to-perform-bitonic-sort-in-parallel"></a><a name="parallel"></a>Использование parallel_invoke для выполнения битонной сортировки в параллельном режиме

В этом разделе описывается использование `parallel_invoke` алгоритма для параллельного выполнения алгоритма битонной сортировки.

### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>Параллельное выполнение алгоритма битонной сортировки

1. Добавьте `#include` директиву для заголовочного файла PPL.h.

[!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]

1. Добавьте **`using`** директиву для `concurrency` пространства имен.

[!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]

1. Создайте новую функцию с именем `parallel_bitonic_mege` , которая использует `parallel_invoke` алгоритм для слияния параллельных последовательностей, если достаточно объема работы. В противном случае вызовите `bitonic_merge` для последовательного слияния последовательностей.

[!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]

1. Выполните процесс, похожий на предыдущий шаг, но для `bitonic_sort` функции.

[!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]

1. Создайте перегруженную версию `parallel_bitonic_sort` функции, которая сортирует массив в порядке возрастания.

[!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]

`parallel_invoke`Алгоритм сокращает затраты, выполняя последнюю последовательность задач в вызывающем контексте. Например, в `parallel_bitonic_sort` функции первая задача выполняется в отдельном контексте, а вторая задача выполняется в вызывающем контексте.

[!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]

Следующий полный пример выполняет как последовательную, так и параллельную версии алгоритма битонной сортировки. Пример также выводит на консоль время, необходимое для выполнения каждого вычисления.

[!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]

В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.

```Output
serial time: 4353
parallel time: 1248
```

[[Top](#top)]

### <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем, `parallel-bitonic-sort.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **cl.exe/EHsc Параллел-битоник-сорт. cpp**

## <a name="robust-programming"></a>Отказоустойчивость

В этом примере используется `parallel_invoke` алгоритм вместо класса [concurrency::task_group](reference/task-group-class.md) , так как время существования каждой группы задач не выходит за пределы функции. Рекомендуется использовать, `parallel_invoke` когда это может быть вызвано меньшими затратами на выполнение `task group` , чем объектами, и, следовательно, позволяет писать более производительный код.

Параллельные версии некоторых алгоритмов работают лучше, только если достаточно работы. Например, `parallel_bitonic_merge` функция вызывает последовательную версию, `bitonic_merge` Если в последовательности 500 или меньше элементов. Вы также можете спланировать общую стратегию сортировки на основе объема работы. Например, использование последовательной версии алгоритма быстрой сортировки может оказаться более эффективным, если массив содержит менее 500 элементов, как показано в следующем примере:

[!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]

Как и в случае с любым параллельным алгоритмом, рекомендуется пропрофилировать и настроить код соответствующим образом.

## <a name="see-also"></a>См. также раздел

[Параллельное выполнение задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Функция parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)
