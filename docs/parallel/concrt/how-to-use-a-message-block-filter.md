---
title: Практическое руководство. Использование фильтра блоков сообщений
ms.date: 11/04/2016
helpviewer_keywords:
- message-block filters, using [Concurrency Runtime]
- using message-block filters [Concurrency Runtime]
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
ms.openlocfilehash: a5814536e88add5b15f577588d571a06eda6151c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226715"
---
# <a name="how-to-use-a-message-block-filter"></a>Практическое руководство. Использование фильтра блоков сообщений

В этом документе показано, как использовать функцию фильтра, чтобы позволить асинхронному блоку сообщений принимать или отклонять сообщения на основе полезных данных этого сообщения.

При создании объекта блока сообщений, такого как [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency::Call](../../parallel/concrt/reference/call-class.md)или [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md), можно указать *функцию фильтра* , которая определяет, будет ли блок сообщений принимать или отклонять сообщение. Функция фильтра — это удобный способ гарантировать, что блок сообщений получает только определенные значения.

Функции фильтров важны, так как они позволяют подключать блоки сообщений для формирования *сетей потоков*данных. В сети потока данных блоки сообщений управляют ходом обработки сообщений, обрабатывая только те сообщения, которые удовлетворяют определенным условиям. Сравните это с моделью потока управления, где поток данных регулируется с помощью структур управления, таких как условные операторы, циклы и т. д.

В этом документе представлен простой пример использования фильтра сообщений. Дополнительные примеры использования фильтров сообщений и модели потоков данных для подключения блоков сообщений см. в разделе [Пошаговое руководство. Создание агента потоков](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) данных и [Пошаговое руководство. Создание сети обработки изображений](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

## <a name="example"></a>Пример

Рассмотрим следующую функцию, `count_primes` которая иллюстрирует базовое использование блока сообщений, который не фильтрует входящие сообщения. Блок сообщений добавляет простые числа к объекту [std:: Vector](../../standard-library/vector-class.md) . `count_primes`Функция отправляет несколько чисел в блок сообщений, получает выходные значения из блока сообщений и выводит эти числа, которые являются простыми в консоли.

[!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_1.cpp)]

`transformer`Объект обрабатывает все входные значения, однако для него требуются только простые значения. Несмотря на то, что приложение может быть написано таким образом, чтобы отправитель сообщений отправлял только простые числа, требования получателя сообщений не всегда известны.

## <a name="example"></a>Пример

Следующая функция, `count_primes_filter` , выполняет ту же задачу, что и `count_primes` функция. Однако `transformer` объект в этой версии использует функцию Filter, чтобы принимать только те значения, которые являются простыми. Функция, которая выполняет действие, получает только простые числа; Поэтому не нужно вызывать `is_prime` функцию.

Поскольку `transformer` объект получает только простые числа, `transformer` сам объект может содержать простые числа. Иными словами, `transformer` объекту в этом примере не требуется добавлять простые числа в `vector` объект.

[!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_2.cpp)]

`transformer`Теперь объект обрабатывает только те значения, которые являются простыми. В предыдущем примере `transformer` объект обрабатывает все сообщения. Поэтому в предыдущем примере должно быть получено то же количество отправленных сообщений. В этом примере используется результат функции [concurrency::send](reference/concurrency-namespace-functions.md#send) , чтобы определить количество сообщений, получаемых из `transformer` объекта. `send`Функция возвращает, **`true`** когда буфер сообщений принимает сообщение, и **`false`** когда буфер сообщений отклоняет сообщение. Таким образом, количество простых чисел в буфере сообщений соответствует числу значений.

## <a name="example"></a>Пример

Ниже приведен полный пример кода. В примере вызывается `count_primes` и функция, и `count_primes_filter` функция.

[!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_3.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем, `primes-filter.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **cl.exe/EHsc примес-филтер. cpp**

## <a name="robust-programming"></a>Отказоустойчивость

Функция фильтра может быть лямбда-функцией, указателем функции или объектом функции. Каждая функция фильтра имеет одну из следующих форм:

```Output
bool (T)
bool (T const &)
```

Чтобы исключить ненужное копирование данных, используйте вторую форму при наличии статистического типа, передаваемого по значению.

## <a name="see-also"></a>См. также статью

[библиотеку асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Пошаговое руководство. Создание агента потока данных](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[Пошаговое руководство. Создание сети обработки изображений](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[Класс transformer](../../parallel/concrt/reference/transformer-class.md)
