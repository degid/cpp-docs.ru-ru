---
title: Пошаговое руководство. Создание пользовательского блока сообщений
ms.date: 04/25/2019
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
ms.openlocfilehash: f95eaf7e1da41bd473ab15d12330d0177b98ccdf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219499"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>Пошаговое руководство. Создание пользовательского блока сообщений

В этом документе описывается создание пользовательского типа блока сообщений, который упорядочивает входящие сообщения по приоритету.

Несмотря на то что встроенные типы блоков сообщений предоставляют широкий спектр функций, можно создать собственный тип блока сообщений и настроить его в соответствии с требованиями приложения. Описание встроенных типов блоков сообщений, предоставляемых библиотекой асинхронных агентов, см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="prerequisites"></a>Предварительные требования

Прежде чем приступить к работе с этим пошаговым руководством, прочитайте следующие документы:

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

## <a name="sections"></a><a name="top"></a>Священ

Это пошаговое руководство содержит следующие разделы:

- [Разработка пользовательского блока сообщений](#design)

- [Определение класса priority_buffer](#class)

- [Полный пример](#complete)

## <a name="designing-a-custom-message-block"></a><a name="design"></a>Разработка пользовательского блока сообщений

Блоки сообщений участвуют в действиях отправки и получения сообщений. Блок сообщений, который отправляет сообщения, называется *исходным блоком*. Блок сообщений, принимающий сообщения, называется *целевым блоком*. Блок сообщений, который отправляет и получает сообщения, называется *блоком распространителя*. Библиотека агентов использует абстрактный класс [concurrency::ISource](../../parallel/concrt/reference/isource-class.md) для представления исходных блоков и абстрактный класс [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) для представления целевых блоков. Типы блоков сообщений, выступающих в качестве источников, являются `ISource` типами блоков сообщений, которые являются целями, производными от `ITarget` .

Несмотря на то, что тип блока сообщений можно вычитать непосредственно из `ISource` и `ITarget` , Библиотека агентов определяет три базовых класса, которые выполняют большую часть функциональных возможностей, общих для всех типов блоков сообщений, например, обработка ошибок и соединение блоков сообщений в безопасном режиме. Класс [concurrency::source_block](../../parallel/concrt/reference/source-block-class.md) является производным от `ISource` и отправляет сообщения в другие блоки. Класс [concurrency::target_block](../../parallel/concrt/reference/target-block-class.md) является производным от `ITarget` других блоков и получает сообщения от них. Класс [concurrency::p ropagator_block](../../parallel/concrt/reference/propagator-block-class.md) является производным от `ISource` и `ITarget` и отправляет сообщения в другие блоки и получает сообщения от других блоков. Мы рекомендуем использовать эти три базовых класса для управления сведениями об инфраструктуре, чтобы сосредоточиться на поведении блока сообщений.

`source_block`Классы, `target_block` и `propagator_block` являются шаблонами, параметризованными для типа, который управляет соединениями или связями между исходным и целевым блоками и типом, который управляет обработкой сообщений. Библиотека агентов определяет два типа, выполняющих Управление ссылками, [concurrency::single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) и [concurrency::multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). `single_link_registry`Класс позволяет связать блок сообщений с одним источником или с одним целевым объектом. `multi_link_registry`Класс позволяет связать блок сообщений с несколькими источниками или с несколькими целевыми объектами. Библиотека агентов определяет один класс, который выполняет Управление сообщениями [concurrency::ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). `ordered_message_processor`Класс позволяет блокам сообщений обрабатывать сообщения в порядке их получения.

Чтобы лучше понять, как блоки сообщений связаны с их источниками и целями, рассмотрим следующий пример. В этом примере показано объявление класса [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) .

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

`transformer`Класс является производным от и `propagator_block` , следовательно, действует как как исходный блок, так и как целевой блок. Он принимает сообщения типа `_Input` и отправляет сообщения типа `_Output` . `transformer`Класс указывает в `single_link_registry` качестве диспетчера ссылок для всех целевых блоков и `multi_link_registry` как Диспетчер ссылок для любых исходных блоков. Таким образом, `transformer` объект может иметь до одного целевого объекта и неограниченного числа источников.

Класс, производный от, `source_block` должен реализовывать шесть методов: [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets), [accept_message](reference/source-block-class.md#accept_message), [reserve_message](reference/source-block-class.md#reserve_message), [consume_message](reference/source-block-class.md#consume_message), [release_message](reference/source-block-class.md#release_message)и [resume_propagation](reference/source-block-class.md#resume_propagation). Класс, производный от, `target_block` должен реализовывать метод [propagate_message](reference/propagator-block-class.md#propagate_message) и при необходимости может реализовать метод [send_message](reference/propagator-block-class.md#send_message) . Наследование от `propagator_block` функционально эквивалентно наследованию от `source_block` и `target_block` .

`propagate_to_any_targets`Метод вызывается средой выполнения для асинхронной или синхронной обработки любых входящих сообщений и распространения всех исходящих сообщений. `accept_message`Метод вызывается целевыми блоками для приема сообщений. Многие типы блоков сообщений, такие как `unbounded_buffer` , отправляют сообщения только первому целевому объекту, который получит его. Таким образом, он передает владение сообщения целевой. Другие типы блоков сообщений, такие как [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md), предлагают сообщения каждому из целевых блоков. Поэтому `overwrite_buffer` создает копию сообщения для каждой цели.

`reserve_message`Методы, `consume_message` , `release_message` и `resume_propagation` позволяют блокам сообщений участвовать в резервировании сообщений. Целевые блоки вызывают `reserve_message` метод, когда им предлагается сообщение и необходимо зарезервировать сообщение для последующего использования. После того как целевой блок резервирует сообщение, он может вызвать `consume_message` метод для использования этого сообщения или `release_message` метода отмены резервирования. Как и в `accept_message` случае с методом, реализация `consume_message` может либо передать владение сообщением, либо вернуть копию сообщения. После того как целевой блок использует или освобождает зарезервированное сообщение, среда выполнения вызывает `resume_propagation` метод. Как правило, этот метод возобновляет распространение сообщений, начиная со следующего сообщения в очереди.

Среда выполнения вызывает `propagate_message` метод для асинхронной пересылки сообщения из другого блока в текущий блок. `send_message`Метод похож на `propagate_message` , за исключением того, что он синхронно, а не асинхронно, отправляет сообщение в целевые блоки. Реализация по умолчанию `send_message` отклоняет все входящие сообщения. Среда выполнения не вызывает ни одного из этих методов, если сообщение не передает необязательную функцию фильтра, связанную с целевым блоком. Дополнительные сведения о фильтрах сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).

[[Top](#top)]

## <a name="defining-the-priority_buffer-class"></a><a name="class"></a>Определение класса priority_buffer

`priority_buffer`Класс — это пользовательский тип блока сообщений, который упорядочивает входящие сообщения сначала по приоритету, а затем по порядку получения сообщений. `priority_buffer`Класс похож на класс [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) , так как он содержит очередь сообщений, а также потому, что он действует как исходный и целевой блок сообщений и может одновременно иметь несколько источников и несколько целевых объектов. Однако `unbounded_buffer` распространение сообщений основывается только на порядке, в котором он получает сообщения из своих источников.

`priority_buffer`Класс получает сообщения типа std::[Tuple](../../standard-library/tuple-class.md) , которые содержат `PriorityType` элементы и `Type` . `PriorityType`относится к типу, содержащему приоритет каждого сообщения; `Type`ссылается на часть данных сообщения. `priority_buffer`Класс отправляет сообщения типа `Type` . `priority_buffer`Класс также управляет двумя очередями сообщений: объектом [std::p riority_queue](../../standard-library/priority-queue-class.md) для входящих сообщений и объектом std::[Queue](../../standard-library/queue-class.md) для исходящих сообщений. Упорядочение сообщений по приоритету полезно, когда `priority_buffer` объект получает несколько сообщений одновременно или когда оно получает несколько сообщений перед чтением сообщений потребителями.

Помимо семи методов, которые класс, производный от, `propagator_block` должен реализовывать, `priority_buffer` класс также переопределяет `link_target_notification` `send_message` методы и. `priority_buffer`Класс также определяет два общедоступных вспомогательных метода, `enqueue` и `dequeue` , и закрытый вспомогательный метод `propagate_priority_order` .

В следующей процедуре описывается, как реализовать `priority_buffer` класс.

#### <a name="to-define-the-priority_buffer-class"></a>Определение класса priority_buffer

1. Создайте файл заголовка C++ и присвойте ему имя `priority_buffer.h` . Кроме того, можно использовать существующий файл заголовка, который является частью проекта.

1. В `priority_buffer.h` добавьте следующий код.

    [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. В `std` пространстве имен определите специализации [std:: less](../../standard-library/less-struct.md) и [std:: больше](../../standard-library/greater-struct.md) , которые работают с объектами Concurrency::[Message](../../parallel/concrt/reference/message-class.md) .

    [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

   `priority_buffer`Класс хранит `message` объекты в `priority_queue` объекте. Эти специализации типов позволяют очереди приоритетов сортировать сообщения в соответствии с их приоритетом. Приоритет — это первый элемент `tuple` объекта.

1. В `concurrencyex` пространстве имен объявите `priority_buffer` класс.

    [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

   Класс `priority_buffer` является производным от `propagator_block`. Поэтому он может отправлять и получать сообщения. `priority_buffer`Класс может иметь несколько целевых объектов, которые получают сообщения типа `Type` . Он также может иметь несколько источников, отправляющих сообщения типа `tuple<PriorityType, Type>` .

1. В **`private`** разделе `priority_buffer` класса добавьте следующие переменные члена.

    [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

   `priority_queue`Объект содержит входящие сообщения; `queue` объект содержит исходящие сообщения. `priority_buffer`Объект может получать несколько сообщений одновременно; `critical_section` объект синхронизирует доступ к очереди входных сообщений.

1. В **`private`** разделе Определите конструктор копии и оператор присваивания. Это предотвращает `priority_queue` возможность назначения объектов.

    [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. В **`public`** разделе определите конструкторы, которые являются общими для многих типов блоков сообщений. Также определите деструктор.

    [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. В **`public`** разделе Определите методы `enqueue` и `dequeue` . Эти вспомогательные методы предоставляют альтернативный способ отправки сообщений в объект и получения сообщений от него `priority_buffer` .

    [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

1. В **`protected`** разделе Определите `propagate_to_any_targets` метод.

    [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

   Метод передает сообщение, находящийся в начале `propagate_to_any_targets` очереди ввода, в выходную очередь и распространяет все сообщения в очереди вывода.

1. В **`protected`** разделе Определите `accept_message` метод.

    [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

   Когда целевой блок вызывает `accept_message` метод, `priority_buffer` класс передает владение сообщением первому целевому блоку, который его принимает. (Это напоминает поведение `unbounded_buffer` .)

1. В **`protected`** разделе Определите `reserve_message` метод.

    [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

   `priority_buffer`Класс позволяет целевому блоку резервировать сообщение, если предоставленный идентификатор сообщения совпадает с идентификатором сообщения, находящегося в начале очереди. Иными словами, целевой объект может зарезервировать сообщение, если `priority_buffer` объект еще не получил дополнительное сообщение и еще не распространил текущий.

1. В **`protected`** разделе Определите `consume_message` метод.

    [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

   Целевой блок вызывает `consume_message` , чтобы передавать владение зарезервированным сообщением.

1. В **`protected`** разделе Определите `release_message` метод.

    [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

   Вызов целевого блока `release_message` для отмены резервирования сообщения.

1. В **`protected`** разделе Определите `resume_propagation` метод.

    [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

   Среда выполнения вызывает метод `resume_propagation` после того, как целевой блок использует или освобождает зарезервированное сообщение. Этот метод распространяет все сообщения, находящиеся в очереди вывода.

1. В **`protected`** разделе Определите `link_target_notification` метод.

    [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

   `_M_pReservedFor`Переменная-член определяется базовым классом, `source_block` . Эта переменная-член указывает целевому блоку, если таковой имеется, который удерживает резервирование для сообщения, находящегося в начале очереди вывода. Среда выполнения вызывает, `link_target_notification` когда новая цель связана с `priority_buffer` объектом. Этот метод распространяет все сообщения, находящиеся в очереди вывода, если цель не удерживает резервирование.

1. В **`private`** разделе Определите `propagate_priority_order` метод.

    [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

   Этот метод распространяет все сообщения из очереди вывода. Каждое сообщение в очереди предлагается каждому целевому блоку до тех пор, пока один из целевых блоков не примет сообщение. `priority_buffer`Класс сохраняет порядок исходящих сообщений. Поэтому первое сообщение в очереди вывода должно быть принято целевым блоком перед тем, как этот метод предлагает другое сообщение целевым блокам.

1. В **`protected`** разделе Определите `propagate_message` метод.

    [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

   `propagate_message`Метод позволяет `priority_buffer` классу действовать в качестве получателя сообщения или целевого объекта. Этот метод получает сообщение, предлагаемое предоставленным блоком источника, и вставляет это сообщение в очередь приоритетов. `propagate_message`Затем метод асинхронно отправляет все выходные сообщения в целевые блоки.

   Среда выполнения вызывает этот метод при вызове функции [concurrency::asend](reference/concurrency-namespace-functions.md#asend) или при соединении блока сообщений с другими блоками сообщений.

1. В **`protected`** разделе Определите `send_message` метод.

    [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

   `send_message`Метод похож на `propagate_message` . Однако он отправляет выходные сообщения синхронно, а не асинхронно.

   Среда выполнения вызывает этот метод во время синхронной операции отправки, например при вызове функции [concurrency::send](reference/concurrency-namespace-functions.md#send) .

`priority_buffer`Класс содержит перегрузки конструктора, типичные для многих типов блоков сообщений. Некоторые перегрузки конструктора принимают объекты [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) или [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) , которые позволяют управлять блоком сообщений с помощью определенного планировщика заданий. Другие перегрузки конструктора принимают функцию Filter. Функции фильтрации позволяют блокам сообщений принимать или отклонять сообщения на основе полезных данных. Дополнительные сведения о фильтрах сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md). Дополнительные сведения о планировщиках задач см. в разделе [планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

Так как `priority_buffer` класс упорядочивает сообщения по приоритету, а затем по порядку получения сообщений, этот класс наиболее полезен при асинхронном получении сообщений, например при вызове функции [concurrency::asend](reference/concurrency-namespace-functions.md#asend) или при соединении блока сообщений с другими блоками сообщений.

[[Top](#top)]

## <a name="the-complete-example"></a><a name="complete"></a>Полный пример

В следующем примере показано полное определение `priority_buffer` класса.

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

В следующем примере одновременно выполняется несколько `asend` операций [concurrency::Receive](reference/concurrency-namespace-functions.md#receive) для `priority_buffer` объекта.

[!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]

В этом примере выводится следующий пример выходных данных.

```Output
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
```

`priority_buffer`Класс упорядочивает сообщения сначала по приоритету, а затем по порядку, в котором они получают сообщения. В этом примере сообщения с более высоким числовым приоритетом вставляются ближе к началу очереди.

[[Top](#top)]

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте определение `priority_buffer` класса в файл с именем `priority_buffer.h` и программу тестирования в файл с именем, `priority_buffer.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

**cl.exe/EHsc priority_buffer. cpp**

## <a name="see-also"></a>См. также раздел

[среда выполнения с параллелизмом пошаговые руководства](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
