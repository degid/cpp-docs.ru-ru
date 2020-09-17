---
title: Практическое руководство. Использование класса Context для реализации семафора, поддерживающего параллельный доступ
ms.date: 11/04/2016
helpviewer_keywords:
- cooperative semaphore implementing
- context class
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
ms.openlocfilehash: 77cf33288761c75d056649ebe27f9d74c6fa62dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230393"
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>Практическое руководство. Использование класса Context для реализации семафора, поддерживающего параллельный доступ

В этом разделе показано, как использовать класс Concurrency:: Context для реализации класса семафора с совместным использованием.

## <a name="remarks"></a>Примечания

`Context`Класс позволяет блокировать или выдавать текущий контекст выполнения. Блокировка или выработка текущего контекста полезна, если текущий контекст не может быть продолжен, так как ресурс недоступен. *Семафор* — это пример одной ситуации, в которой текущий контекст выполнения должен ждать, пока ресурс станет доступным. Семафор, как и объект критической секции, является объектом синхронизации, который позволяет коду в одном контексте иметь монопольный доступ к ресурсу. Однако, в отличие от объекта критической секции, семафор позволяет параллельно обращаться к ресурсу более чем в одном контексте. Если максимальное число контекстов содержит блокировку семафора, каждый дополнительный контекст должен ожидать освобождения блокировки другим контекстом.

### <a name="to-implement-the-semaphore-class"></a>Реализация класса семафора

1. Объявите класс с именем `semaphore` . Добавьте **`public`** **`private`** разделы и в этот класс.

[!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]

1. В **`private`** разделе `semaphore` класса объявите переменную [std:: Atomic](../../standard-library/atomic-structure.md) , которая содержит количество семафоров и объект [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) , содержащий контексты, которые должны ожидать получения семафора.

[!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]

1. В **`public`** разделе `semaphore` класса реализуйте конструктор. Конструктор принимает **`long long`** значение, указывающее максимальное количество контекстов, которые могут одновременно удерживать блокировку.

[!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]

1. В **`public`** разделе `semaphore` класса реализуйте `acquire` метод. Этот метод уменьшает число семафоров как атомарную операцию. Если число семафоров станет отрицательным, добавьте текущий контекст в конец очереди ожидания и вызовите метод [concurrency::Context:: Block](reference/context-class.md#block) , чтобы заблокировать текущий контекст.

[!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]

1. В **`public`** разделе `semaphore` класса реализуйте `release` метод. Этот метод увеличивает число семафоров в виде атомарной операции. Если число семафоров отрицательно до операции приращения, то существует по крайней мере один контекст, ожидающий блокировки. В этом случае Разблокируйте контекст, находящиеся в начале очереди ожидания.

[!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]

## <a name="example"></a>Пример

`semaphore`Класс в этом примере выполняется совместно, так как `Context::Block` `Context::Yield` методы и возвращают выполнение, чтобы среда выполнения могла выполнять другие задачи.

`acquire`Метод уменьшает счетчик, но может не завершить добавление контекста в очередь ожидания, прежде чем другой контекст вызовет `release` метод. Для этого `release` метод использует цикл Spin, который вызывает метод [concurrency::Context:: Yield](reference/context-class.md#yield) , чтобы дождаться `acquire` завершения добавления контекста в метод.

`release`Метод может вызвать `Context::Unblock` метод до того, как `acquire` метод вызовет `Context::Block` метод. Не требуется защищаться от этого состояния гонки, так как среда выполнения позволяет вызывать эти методы в любом порядке. Если `release` метод вызывает `Context::Unblock` до `acquire` вызова метода для того `Context::Block` же контекста, этот контекст остается незаблокированным. Среда выполнения требует, чтобы каждый вызов `Context::Block` сопоставляется с соответствующим вызовом `Context::Unblock` .

В следующем примере показан полный `semaphore` класс. `wmain`Функция показывает базовое использование этого класса. `wmain`Функция использует алгоритм [arallel_for concurrency::p](reference/concurrency-namespace-functions.md#parallel_for) , чтобы создать несколько задач, которым требуется доступ к семафору. Так как три потока могут удерживать блокировку в любое время, некоторые задачи должны дожидаться завершения другой задачи и освобождения блокировки.

[!code-cpp[concrt-cooperative-semaphore#6](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_6.cpp)]

В этом примере выводится следующий пример выходных данных.

```Output
In loop iteration 5...
In loop iteration 0...
In loop iteration 6...
In loop iteration 1...
In loop iteration 2...
In loop iteration 7...
In loop iteration 3...
In loop iteration 8...
In loop iteration 9...
In loop iteration 4...
```

Дополнительные сведения о `concurrent_queue` классе см. в разделе [Parallel Containers and Objects](../../parallel/concrt/parallel-containers-and-objects.md). Дополнительные сведения об `parallel_for` алгоритме см. в разделе [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем, `cooperative-semaphore.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **cl.exe/EHsc куперативе-семафоре. cpp**

## <a name="robust-programming"></a>Отказоустойчивость

Можно использовать шаблон « *получение ресурсов — инициализация* » (RAII), чтобы ограничить доступ к `semaphore` объекту в заданной области. В шаблоне RAII структура данных выделяется в стеке. Эта структура данных Инициализирует или получает ресурс при его создании, а также уничтожает или освобождает этот ресурс при уничтожении структуры данных. Шаблон RAII гарантирует, что деструктор вызывается до выхода из охватывающей области. Таким образом, ресурс правильно управляется при возникновении исключения или если функция содержит несколько **`return`** инструкций.

В следующем примере определяется класс с именем `scoped_lock` , который определен в **`public`** разделе `semaphore` класса. `scoped_lock`Класс похож на классы [concurrency::critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) и [concurrency::reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) . Конструктор `semaphore::scoped_lock` класса получает доступ к данному `semaphore` объекту, а деструктор освобождает доступ к этому объекту.

[!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]
В следующем примере изменяется текст рабочей функции, которая передается в `parallel_for` алгоритм, чтобы она использовала RAII, чтобы убедиться, что семафор освобожден перед возвратом функции. Этот метод гарантирует, что Рабочая функция будет защищена от исключений.

[!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]

## <a name="see-also"></a>См. также статью

[Контексты](../../parallel/concrt/contexts.md)<br/>
[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)
