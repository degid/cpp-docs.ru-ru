---
title: Практическое руководство. Параллельное выполнение операций сопоставления и сокращения числа элементов
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_transform function, example
- parallel map and reduce, example
- parallel_reduce function, example
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
ms.openlocfilehash: 599e46c05a91a1f2ea6e317fe024d3c98a78977f
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141711"
---
# <a name="how-to-perform-map-and-reduce-operations-in-parallel"></a>Практическое руководство. Параллельное выполнение операций сопоставления и сокращения числа элементов

В этом примере показано, как использовать алгоритмы [concurrency::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) и [concurrency::p arallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) и класс [concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) для подсчета вхождений слов в файлах.

Операция *Map* применяет функцию к каждому значению в последовательности. Операция *сокращения* объединяет элементы последовательности в одно значение. Для выполнения операций Map C++ и reduce можно использовать стандартные библиотеки [std:: Transform](../../standard-library/algorithm-functions.md#transform) и [std:: accumulate](../../standard-library/numeric-functions.md#accumulate) . Однако для повышения производительности при многих проблемах можно использовать алгоритм `parallel_transform` для параллельного выполнения операции сопоставления и алгоритм `parallel_reduce` для параллельного выполнения операции редукции. В некоторых случаях можно использовать `concurrent_unordered_map` для выполнения сопоставления и операции редукции в одной операции.

## <a name="example"></a>Пример

В следующем примере подсчитываются вхождения слов в файлах. Для представления содержимого двух файлов используется [std:: Vector](../../standard-library/vector-class.md) . Операция сопоставления подсчитывает вхождения каждого слова в каждом векторе. Операция редукции накапливает подсчет слов в обоих векторах.

[!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем `parallel-map-reduce.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc Параллел-МАП-редуце. cpp**

## <a name="robust-programming"></a>Отказоустойчивость

В этом примере можно использовать класс `concurrent_unordered_map`, который определен в concurrent_unordered_map.h, чтобы выполнять сопоставление и редукцию в одной операции.

[!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]

Как правило, вы параллелизуете только внешний или внутренний цикл. Параллелизуйте внутренний цикл при наличии относительно небольшого числа файлов, когда каждый файл содержит много слов. Параллелизуйте внешний цикл при наличии довольно большого числа файлов, когда каждый файл содержит мало слов.

## <a name="see-also"></a>См. также раздел

[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Функция parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)<br/>
[Функция parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)<br/>
[Класс concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
