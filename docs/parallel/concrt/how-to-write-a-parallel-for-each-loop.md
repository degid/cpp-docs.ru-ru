---
title: Практическое руководство. Написание цикла parallel_for_each
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
ms.openlocfilehash: 10c281b7db92e2706b20a1c7377fcdb9d924152d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141871"
---
# <a name="how-to-write-a-parallel_for_each-loop"></a>Практическое руководство. Написание цикла parallel_for_each

В этом примере показано, как использовать алгоритм [параллелизма::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) , чтобы вычислить число простых чисел в объекте [std:: Array](../../standard-library/array-class-stl.md) параллельно.

## <a name="example"></a>Пример

В следующем примере число простых чисел в массиве вычисляются дважды. В примере сначала используется алгоритм [std:: for_each](../../standard-library/algorithm-functions.md#for_each) для последовательного вычисления числа. Затем в примере используется алгоритм `parallel_for_each` для параллельного выполнения одной и той же задачи. В этом примере в консоль также выводится время, необходимое на выполнение обоих вычислений.

[!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-each-loop_1.cpp)]

В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.

```Output
serial version:
found 17984 prime numbers
took 6115 ms

parallel version:
found 17984 prime numbers
took 1653 ms
```

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем `parallel-count-primes.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc Параллел-Каунт-примес. cpp**

## <a name="robust-programming"></a>Отказоустойчивость

Лямбда-выражение, которое в примере передается в алгоритм `parallel_for_each`, использует функцию `InterlockedIncrement` для включения параллельных итераций цикла для одновременного увеличения счетчика. Если вы используете такие функции, как `InterlockedIncrement` для синхронизации доступа к общим ресурсам, в коде можно представлять узкие места производительности. Чтобы исключить одновременный доступ к общим ресурсам, можно использовать механизм синхронизации без блокировки, например класс [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) . Пример, в котором используется класс `combinable`, см. в разделе [руководство. Использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).

## <a name="see-also"></a>См. также раздел

[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Функция parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)
