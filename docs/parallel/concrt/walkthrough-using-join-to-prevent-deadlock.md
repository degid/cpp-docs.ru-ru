---
title: Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки
ms.date: 04/25/2019
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
ms.openlocfilehash: 5bdd6cd81051d224714dd66d4604cbdec4ddb552
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217887"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки

В этом разделе используется Проблема обедающих философов, чтобы продемонстрировать, как использовать класс [concurrency::Join](../../parallel/concrt/reference/join-class.md) для предотвращения взаимоблокировок в приложении. В приложении программного обеспечения *взаимоблокировка* возникает, когда два или несколько процессов используют ресурс и одновременно ожидают, пока другой процесс не освободит какой-либо из ресурсов.

Проблема обедающих философов — это конкретный пример общего набора проблем, которые могут возникнуть, когда набор ресурсов совместно используется несколькими параллельными процессами.

## <a name="prerequisites"></a>Предварительные требования

Перед началом работы с этим пошаговым руководством ознакомьтесь со следующими разделами:

- [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)

- [Пошаговое руководство. Создание приложения на основе агента](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

- [Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)

## <a name="sections"></a><a name="top"></a>Священ

Это пошаговое руководство содержит следующие разделы:

- [Проблема обедающих философов](#problem)

- [Упрощенная реализация](#deadlock)

- [Использование Join для предотвращения взаимоблокировок](#solution)

## <a name="the-dining-philosophers-problem"></a><a name="problem"></a>Проблема обедающих философов

Проблема с философами обеда показывает, как происходит взаимоблокировка в приложении. В этой проблеме пять философов располагаются в круглой таблице. Каждый философ является альтернативным для мышления и съесть. Каждый философ должен поделиться палочкой с соседом слева и другой палочкой, расположенной справа от соседнего. На следующем рисунке показан этот макет.

![Проблема обедающих философов](../../parallel/concrt/media/dining_philosophersproblem.png "Проблема обедающих философов")

Для EAT, философ должен содержать две палочки. Если у каждого философа есть только одна палочка, ожидающая другой, то ни один из философов не может получить и не дожидаться.

[[Top](#top)]

## <a name="a-nave-implementation"></a><a name="deadlock"></a>Упрощенная реализация

В следующем примере показана упрощенная реализация проблемы обедающих философов. `philosopher`Класс, производный от [concurrency::Agent](../../parallel/concrt/reference/agent-class.md), позволяет каждому философу работать независимо. В примере используется общий массив объектов [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) , чтобы предоставить каждому `philosopher` объекту эксклюзивный доступ к паре палочк.

Чтобы связать реализацию с иллюстрацией, `philosopher` класс представляет одного философа. **`int`** Переменная представляет каждую палочку. `critical_section`Объекты играют роль владельцев, на которых накрываются палочки. `run`Метод имитирует жизнь философа. `think`Метод имитирует процесс мышления, и `eat` метод имитирует действие съесть.

`philosopher`Объект блокирует оба `critical_section` объекта, чтобы имитировать удаление палочк из владельцев перед вызовом `eat` метода. После вызова `eat` `philosopher` объект возвращает палочки владельцам, устанавливая `critical_section` объекты обратно в незаблокированное состояние.

`pickup_chopsticks`Метод показывает, где может произойти взаимоблокировка. Если каждый `philosopher` объект получает доступ к одной из блокировок, то объект не `philosopher` может продолжать работу, так как другая блокировка управляется другим `philosopher` объектом.

### <a name="example"></a>Пример

[!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]

### <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем, `philosophers-deadlock.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **cl.exe/EHsc философерс-деадлокк. cpp**

[[Top](#top)]

## <a name="using-join-to-prevent-deadlock"></a><a name="solution"></a>Использование Join для предотвращения взаимоблокировок

В этом разделе показано, как использовать буферы сообщений и функции передачи сообщений для устранения вероятности взаимоблокировки.

Чтобы связать этот пример с предыдущим, `philosopher` класс заменяет каждый объект с `critical_section` помощью объекта [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) и `join` объекта. `join`Объект выступает в качестве арбитра, предоставляющего палочки философу.

В этом примере используется `unbounded_buffer` класс, так как когда целевой объект получает сообщение от `unbounded_buffer` объекта, сообщение удаляется из очереди сообщений. Это позволяет `unbounded_buffer` объекту, содержащему сообщение, указать, что палочка доступна. `unbounded_buffer`Объект, не содержащий сообщения, указывает, что используется палочка.

В этом примере используется нежадный `join` объект, поскольку нежадное соединение предоставляет каждому `philosopher` объекту доступ к обеим палочкам только в том случае, если оба `unbounded_buffer` объекта содержат сообщение. Жадное соединение не помешает взаимоблокировке, так как жадное соединение принимает сообщения, как только они становятся доступными. Взаимоблокировка может быть вызвана тем, что все жадные `join` объекты получают одно из сообщений, но ожидают бесконечное ожидание, чтобы оно стало доступным.

Дополнительные сведения о жадных и нежадных объединениях, а также различиях между различными типами буферов сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

### <a name="to-prevent-deadlock-in-this-example"></a>Предотвращение взаимоблокировок в этом примере

1. Удалите из примера следующий код.

[!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]

1. Измените тип `_left` `_right` членов данных `philosopher` класса и на `unbounded_buffer` .

[!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]

1. Измените `philosopher` конструктор, чтобы в `unbounded_buffer` качестве параметров использовать объекты.

[!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]

1. Измените `pickup_chopsticks` метод, чтобы использовать нежадный `join` объект для получения сообщений из буферов сообщений для обеих палочк.

[!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]

1. Измените `putdown_chopsticks` метод, чтобы освободить доступ к палочкам, отправив сообщение в буферы сообщений для обеих палочк.

[!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]

1. Измените `run` метод для хранения результатов `pickup_chopsticks` метода и передачи этих результатов в `putdown_chopsticks` метод.

[!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]

1. Измените объявление `chopsticks` переменной в `wmain` функции, чтобы она была массивом `unbounded_buffer` объектов, содержащих одно сообщение.

[!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]

### <a name="description"></a>Описание

Ниже показан готовый пример, использующий нежадные `join` объекты для устранения риска взаимоблокировки.

### <a name="example"></a>Пример

[!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]

В этом примере формируются следующие данные:

```Output
aristotle ate 50 times.
descartes ate 50 times.
hobbes ate 50 times.
socrates ate 50 times.
plato ate 50 times.
```

### <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем, `philosophers-join.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **cl.exe/EHsc философерс-Жоин. cpp**

[[Top](#top)]

## <a name="see-also"></a>См. также раздел

[среда выполнения с параллелизмом пошаговые руководства](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[библиотеку асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)
