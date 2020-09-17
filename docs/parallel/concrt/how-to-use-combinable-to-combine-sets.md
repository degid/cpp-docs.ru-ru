---
title: Практическое руководство. Использование класса combinable для комбинирования наборов
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
ms.openlocfilehash: 7ccbb3e8bad5c4d3b6f4177afbfdba3e200681a5
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142119"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>Практическое руководство. Использование класса combinable для комбинирования наборов

В этом разделе показано, как использовать класс [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) для расчета набора простых чисел.

## <a name="example"></a>Пример

В следующем примере набор простых чисел вычисляются два раза. Каждое вычисление сохраняет результат в объекте [std:: битовом массиве](../../standard-library/bitset-class.md) . В примере сначала выполняется последовательное вычисление набора, а затем набор рассчитывается параллельно. В этом примере в консоль также выводится время, необходимое на выполнение обоих вычислений.

В этом примере используется алгоритм [arallel_for Concurrency::p](reference/concurrency-namespace-functions.md#parallel_for) и объект `combinable` для создания локальных наборов потока. Затем он использует метод [concurrency::combinable:: combine_each](reference/combinable-class.md#combine_each) для объединения локальных наборов потоков в окончательный набор.

[!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]

В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.

```Output
serial time: 312 ms

parallel time: 78 ms
```

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `parallel-combine-primes.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc Параллел-комбине-примес. cpp**

## <a name="see-also"></a>См. также раздел

[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Класс combinable](../../parallel/concrt/reference/combinable-class.md)<br/>
[Метод combinable:: combine_each](reference/combinable-class.md#combine_each)
