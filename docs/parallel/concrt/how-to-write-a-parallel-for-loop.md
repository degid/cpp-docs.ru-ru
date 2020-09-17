---
title: Практическое руководство. Написание цикла parallel_for
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
ms.openlocfilehash: 5903114a12de46dc06929c83e9995b39d0136810
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141863"
---
# <a name="how-to-write-a-parallel_for-loop"></a>Практическое руководство. Написание цикла parallel_for

В этом примере показано, как использовать метод [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) , чтобы вычислить произведение двух матриц.

## <a name="example"></a>Пример

В следующем примере показана функция `matrix_multiply`, которая вычисляет произведение двух квадратных матриц.

[!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]

## <a name="example"></a>Пример

В следующем примере показана функция `parallel_matrix_multiply`, которая использует алгоритм `parallel_for` для параллельного выполнения внешнего цикла.

[!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]

В этом примере внешний цикл параллелизуются только потому, что он выполняет достаточную работу, чтобы воспользоваться преимуществами дополнительных затрат на параллельную обработку. При параллелизации внутреннего цикла вы не получаете выигрыш в производительности, так как небольшой объем работы, выполняемый внутренним циклом, не позволяет преодолеть издержки при параллельной обработке. Таким образом, параллелизация только внешнего цикла является лучшим способом обеспечить максимальную выгоду от параллелизма в большинстве систем.

## <a name="example"></a>Пример

Следующий более полный пример сравнивает производительность функции `matrix_multiply` и функции `parallel_matrix_multiply`.

[!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]

В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.

```Output
serial: 3853
parallel: 1311
```

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем `parallel-matrix-multiply.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc Параллел-Матрикс-мултипли. cpp**

## <a name="see-also"></a>См. также раздел

[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Функция parallel_for](reference/concurrency-namespace-functions.md#parallel_for)
