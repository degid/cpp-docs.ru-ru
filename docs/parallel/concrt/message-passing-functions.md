---
title: Функции передачи сообщений
ms.date: 11/04/2016
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
ms.openlocfilehash: 3709e7b5280b96b2b77ec850a06ed15d0e42a7e5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87194632"
---
# <a name="message-passing-functions"></a>Функции передачи сообщений

Библиотека асинхронных агентов предоставляет несколько функций, которые позволяют передавать сообщения между компонентами.

Эти функции передачи сообщений используются с различными типами блоков сообщений. Дополнительные сведения о типах блоков сообщений, определяемых среда выполнения с параллелизмом, см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="sections"></a><a name="top"></a>Священ

В этом разделе описаны следующие функции передачи сообщений:

- [Send и asend](#send)

- [получение и try_receive](#receive)

- [Примеры](#examples)

## <a name="send-and-asend"></a><a name="send"></a>Send и asend

Функция [concurrency::send](reference/concurrency-namespace-functions.md#send) отправляет сообщение указанному целевому объекту синхронно, а функция [concurrency::asend](reference/concurrency-namespace-functions.md#asend) отправляет сообщение указанному целевому объекту асинхронно. Обе `send` функции и `asend` ожидают, пока целевой объект не обозначает, что в конечном итоге будет принимать или отклонять сообщение.

`send`Функция ожидает, пока целевой объект не примет или не отклонит сообщение перед возвратом. `send`Функция возвращает значение, **`true`** Если сообщение было доставлено, и **`false`** в противном случае. Так как `send` функция работает синхронно, она `send` ожидает получения сообщения целевым объектом перед возвратом.

И наоборот, `asend` функция не ожидает принятия или отклонения сообщения целевым объектом перед возвратом. Вместо этого `asend` функция возвращает значение, **`true`** Если целевой объект принимает сообщение и в конечном итоге получит его. В противном случае `asend` возвращает **`false`** значение, указывающее, что целевой объект отклонил сообщение или отказался от принятия решения о том, следует ли принимать сообщение.

[[Top](#top)]

## <a name="receive-and-try_receive"></a><a name="receive"></a>получение и try_receive

Функции [concurrency::Receive](reference/concurrency-namespace-functions.md#receive) и [concurrency::try_receive](reference/concurrency-namespace-functions.md#try_receive) считывают данные из заданного источника. `receive`Функция ожидает, пока данные станут доступными, в то время как `try_receive` функция возвращает значение немедленно.

Используйте `receive` функцию, если для продолжения работы требуются данные. Используйте `try_receive` функцию, если не следует блокировать текущий контекст или нет необходимости для продолжения работы с данными.

[[Top](#top)]

## <a name="examples"></a><a name="examples"></a> Примеры

Примеры использования `send` функций и и см `asend` `receive` . в следующих разделах:

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Как реализовать различные шаблоны "производитель-получатель"](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)

- [Руководство. предоставление рабочих функций классам Call и transformer](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)

- [Как использовать преобразователь в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)

- [Практические руководства. Выбор между завершенными задачами](../../parallel/concrt/how-to-select-among-completed-tasks.md)

- [Как отправить сообщение с постоянным интервалом](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)

- [Как использовать фильтр блоков сообщений](../../parallel/concrt/how-to-use-a-message-block-filter.md)

[[Top](#top)]

## <a name="see-also"></a>См. также раздел

[библиотеку асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функция send](reference/concurrency-namespace-functions.md#send)<br/>
[Функция asend](reference/concurrency-namespace-functions.md#asend)<br/>
[Функция receive](reference/concurrency-namespace-functions.md#receive)<br/>
[Функция try_receive](reference/concurrency-namespace-functions.md#try_receive)
