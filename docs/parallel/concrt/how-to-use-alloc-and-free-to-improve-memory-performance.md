---
title: Практическое руководство. Использование функций Alloc и Free для повышения производительности операций с памятью
ms.date: 11/04/2016
helpviewer_keywords:
- Alloc and Free, using [Concurrency Runtime]
- Using Alloc and Free [Concurrency Runtime]
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
ms.openlocfilehash: 8438e833262d42c6083f48f759501c573a35c772
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142787"
---
# <a name="how-to-use-alloc-and-free-to-improve-memory-performance"></a>Практическое руководство. Использование функций Alloc и Free для повышения производительности операций с памятью

В этом документе показано, как использовать функции [concurrency::Alloc](reference/concurrency-namespace-functions.md#alloc) и [concurrency::Free](reference/concurrency-namespace-functions.md#free) для повышения производительности памяти. Он сравнивает время, необходимое для изменения числа элементов массива в параллельном режиме для трех различных типов, каждый из которых указывает операторы `new` и `delete`.

Функции `Alloc` и `Free` наиболее полезны, когда несколько потоков часто вызывают как `Alloc`, так и `Free`. Среда выполнения содержит отдельный кэш памяти для каждого потока; Таким образом, среда выполнения управляет памятью без использования блокировок или барьеров памяти.

## <a name="example"></a>Пример

В следующем примере показаны три типа, каждый из которых указывает операторы `new` и `delete`. Класс `new_delete` использует глобальные операторы `new` и `delete`, класс `malloc_free` использует [функции CRT и](../../c-runtime-library/reference/malloc.md) [Free](../../c-runtime-library/reference/free.md) среды выполнения C, а класс `Alloc_Free` использует функции среда выполнения с параллелизмом `Alloc` и `Free`.

[!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]

## <a name="example"></a>Пример

В следующем примере показаны функции `swap` и `reverse_array`. Функция `swap` обменивает содержимое массива по указанным индексам. Она выделяет память из кучи для временной переменной. Функция `reverse_array` создает большой массив и подсчитывает время, необходимое для того, чтобы несколько раз обращаться к этому массиву в параллельном режиме.

[!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]

## <a name="example"></a>Пример

В следующем примере показана функция `wmain`, которая вычислит время, необходимое для работы функции `reverse_array` в типах `new_delete`, `malloc_free`и `Alloc_Free`, каждая из которых использует другую схему выделения памяти.

[!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]

## <a name="example"></a>Пример

Полный пример приведен ниже.

[!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]

В этом примере выводится следующий пример выходных данных для компьютера с четырьмя процессорами.

```Output
Took 2031 ms with new/delete.
Took 1672 ms with malloc/free.
Took 656 ms with Alloc/Free.
```

В этом примере тип, использующий функции `Alloc` и `Free`, обеспечивает лучшую производительность памяти, так как функции `Alloc` и `Free` оптимизированы для частого выделения и освобождения блоков памяти из нескольких потоков.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `allocators.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc распределителя. cpp**

## <a name="see-also"></a>См. также раздел

[Функции управления памятью](../../parallel/concrt/memory-management-functions.md)<br/>
[Alloc, функция](reference/concurrency-namespace-functions.md#alloc)<br/>
[Бесплатная функция](reference/concurrency-namespace-functions.md#free)
