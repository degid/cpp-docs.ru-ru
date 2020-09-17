---
title: Параллельные контейнеры и объекты
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: 7387173378e79a4707008a11846eab19d7ae4341
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831792"
---
# <a name="parallel-containers-and-objects"></a>Параллельные контейнеры и объекты

Библиотека параллельных шаблонов (PPL) включает несколько контейнеров и объектов, которые обеспечивают потокобезопасный доступ к их элементам.

*Параллельный контейнер* обеспечивает потокобезопасный доступ к наиболее важным операциям. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода. Функциональные возможности этих контейнеров похожи на функции, предоставляемые стандартной библиотекой C++. Например, класс [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) похож на класс [std:: Vector](../../standard-library/vector-class.md) , за исключением того, что `concurrent_vector` класс позволяет добавлять элементы параллельно. Одновременно используйте параллельные контейнеры, для которых требуется доступ на чтение и запись к одному и тому же контейнеру.

*Параллельный объект* совместно используется компонентами. Процесс, который вычисляет состояние параллельного объекта в Parallel, дает тот же результат, что и другой процесс, который последовательно вычисляет одно и то же состояние. Класс [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) является одним из примеров параллельного типа объекта. `combinable`Класс позволяет выполнять вычисления параллельно, а затем объединять эти вычисления в окончательный результат. Используйте параллельные объекты, если в противном случае использовать механизм синхронизации, например мьютекс, для синхронизации доступа к общей переменной или ресурсу.

## <a name="sections"></a><a name="top"></a> Священ

В этом разделе подробно описаны следующие параллельные контейнеры и объекты.

Параллельные контейнеры:

- [Класс concurrent_vector](#vector)

  - [Различия между concurrent_vector и Vector](#vector-differences)

  - [Операции с параллелизмом](#vector-safety)

  - [Безопасность исключений](#vector-exceptions)

- [Класс concurrent_queue](#queue)

  - [Различия между concurrent_queue и очередью](#queue-differences)

  - [Операции с параллелизмом](#queue-safety)

  - [Поддержка итераторов](#queue-iterators)

- [Класс concurrent_unordered_map](#unordered_map)

  - [Различия между concurrent_unordered_map и unordered_map](#map-differences)

  - [Операции с параллелизмом](#map-safety)

- [Класс concurrent_unordered_multimap](#unordered_multimap)

- [Класс concurrent_unordered_set](#unordered_set)

- [Класс concurrent_unordered_multiset](#unordered_multiset)

Параллельные объекты:

- [Класс combinable](#combinable)

  - [Методы и функции](#combinable-features)

  - [Примеры](#combinable-examples)

## <a name="concurrent_vector-class"></a><a name="vector"></a> Класс concurrent_vector

Класс [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) является классом-контейнером последовательности, который, как и класс [std:: Vector](../../standard-library/vector-class.md) , обеспечивает случайный доступ к его элементам. `concurrent_vector`Класс позволяет выполнять операции добавления и доступа к элементам в режиме параллелизма. Операции добавления не делают недействительными существующие указатели или итераторы. Операции доступа и обхода итератора также являются надежными в режиме параллелизма. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода.

### <a name="differences-between-concurrent_vector-and-vector"></a><a name="vector-differences"></a> Различия между concurrent_vector и Vector

Класс будет похож на класс `concurrent_vector` `vector` . Сложность операций добавления, доступа к элементам и итераторов для `concurrent_vector` объекта аналогична операции для `vector` объекта. Следующие моменты иллюстрируют, где `concurrent_vector` отличия от `vector` :

- Операции добавления, доступа к элементам, итератора и обхода итератора для `concurrent_vector` объекта являются надежными в режиме параллелизма.

- Элементы можно добавлять только в конец `concurrent_vector` объекта. `concurrent_vector`Класс не предоставляет `insert` метод.

- `concurrent_vector`Объект не использует [семантику перемещения](../../cpp/rvalue-reference-declarator-amp-amp.md) при добавлении к ней.

- `concurrent_vector`Класс не предоставляет `erase` `pop_back` методы или. Как и с `vector` , используйте метод [clear](reference/concurrent-vector-class.md#clear) для удаления всех элементов из `concurrent_vector` объекта.

- `concurrent_vector`Класс не хранит свои элементы непрерывно в памяти. Таким образом, нельзя использовать `concurrent_vector` класс во всех способах использования массива. Например, для переменной с именем `v` типа `concurrent_vector` выражение `&v[0]+2` создает неопределенное поведение.

- `concurrent_vector`Класс определяет методы [grow_by](reference/concurrent-vector-class.md#grow_by) и [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) . Эти методы похожи на метод [изменения размера](reference/concurrent-vector-class.md#resize) , за исключением того, что они являются надежными в режиме параллелизма.

- `concurrent_vector`Объект не перемещает свои элементы при добавлении к нему или изменении его размера. Это позволяет существующим указателям и итераторам оставаться действительными во время параллельных операций.

- Среда выполнения не определяет специальную версию `concurrent_vector` для типа **`bool`** .

### <a name="concurrency-safe-operations"></a><a name="vector-safety"></a> Операции с параллелизмом

Все методы, которые добавляют или увеличивают размер `concurrent_vector` объекта или обращаются к элементу в `concurrent_vector` объекте, являются надежными в режиме параллелизма. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода. Исключением из этого правила является `resize` метод.

В следующей таблице показаны общие `concurrent_vector` методы и операторы, которые являются типобезопасными.

:::row:::
   :::column span="":::
      [`at`](reference/concurrent-vector-class.md#at)\
      [`back`](reference/concurrent-vector-class.md#back)\
      [`begin`](reference/concurrent-vector-class.md#begin)\
      [`capacity`](reference/concurrent-vector-class.md#capacity)
   :::column-end:::
   :::column span="":::
      [`empty`](reference/concurrent-vector-class.md#empty)\
      [`end`](reference/concurrent-vector-class.md#end)\
      [`front`](reference/concurrent-vector-class.md#front)\
      [`grow_by`](reference/concurrent-vector-class.md#grow_by)
   :::column-end:::
   :::column span="":::
      [`grow_to_at_least`](reference/concurrent-vector-class.md#grow_to_at_least)\
      [`max_size`](reference/concurrent-vector-class.md#max_size)\
      [`operator[]`](reference/concurrent-vector-class.md#operator_at)\
      [`push_back`](reference/concurrent-vector-class.md#push_back)
   :::column-end:::
   :::column span="":::
      [`rbegin`](reference/concurrent-vector-class.md#rbegin)\
      [`rend`](reference/concurrent-vector-class.md#rend)\
      [`size`](reference/concurrent-vector-class.md#size)
   :::column-end:::
:::row-end:::

Операции, предоставляемые средой выполнения для обеспечения совместимости с стандартной библиотекой C++, например, `reserve` не являются типобезопасными в режиме параллелизма. В следующей таблице показаны общие методы и операторы, которые не являются типобезопасными в режиме параллелизма.

:::row:::
   :::column span="":::
      [`assign`](reference/concurrent-vector-class.md#assign)\
      [`clear`](reference/concurrent-vector-class.md#clear)
   :::column-end:::
   :::column span="":::
      [`operator=`](reference/concurrent-vector-class.md#operator_eq)\
      [`reserve`](reference/concurrent-vector-class.md#reserve)
   :::column-end:::
   :::column span="":::
      [`resize`](reference/concurrent-vector-class.md#resize)
   :::column-end:::
   :::column span="":::
      [`shrink_to_fit`](reference/concurrent-vector-class.md#shrink_to_fit)
   :::column-end:::
:::row-end:::

Операции, изменяющие значение существующих элементов, не являются надежными в режиме параллелизма. Используйте объект синхронизации, например объект [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) , чтобы синхронизировать параллельные операции чтения и записи с одним и тем же элементом данных. Дополнительные сведения об объектах синхронизации см. в разделе [структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md).

При преобразовании существующего кода, используемого `vector` для использования `concurrent_vector` , параллельные операции могут привести к изменению поведения приложения. Например, рассмотрим следующую программу, которая одновременно выполняет две задачи с `concurrent_vector` объектом. Первая задача добавляет дополнительные элементы в `concurrent_vector` объект. Вторая задача вычисляет сумму всех элементов в одном объекте.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

Хотя `end` метод является типобезопасным, параллельный вызов метода [push_back](reference/concurrent-vector-class.md#push_back) вызывает изменение значения, возвращаемого функцией `end` . Число элементов, которые проходит итератор, является неопределенным. Таким образом, эта программа может создавать различные результаты при каждом запуске. Если тип элемента не является тривиальным, то может существовать состояние гонки между `push_back` `end` вызовами и. `end`Метод может возвращать элемент, который выделен, но не полностью инициализирован.

### <a name="exception-safety"></a><a name="vector-exceptions"></a> Безопасность исключений

Если операция увеличения или назначения создает исключение, состояние `concurrent_vector` объекта станет недействительным. Поведение `concurrent_vector` объекта в недопустимом состоянии не определено, если не указано иное. Однако деструктор всегда освобождает память, выделенную объектом, даже если объект находится в недопустимом состоянии.

Тип данных элементов Vector, `T` должен соответствовать следующим требованиям. В противном случае поведение `concurrent_vector` класса не определено.

- Деструктор не должен вызывать исключение.

- Если конструктор по умолчанию или экземпляр создает исключение, деструктор не должен быть объявлен с помощью **`virtual`** ключевого слова и должен правильно работать с памятью, инициализированной нулем.

[[Top](#top)]

## <a name="concurrent_queue-class"></a><a name="queue"></a> Класс concurrent_queue

Класс [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) , как и класс [std:: Queue](../../standard-library/queue-class.md) , позволяет получить доступ к элементам Front и back. `concurrent_queue`Класс включает постановку в очередь с параллелизмом и операции вывода из очереди. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода. `concurrent_queue`Класс также предоставляет поддержку итератора, которая не является надежной в режиме параллелизма.

### <a name="differences-between-concurrent_queue-and-queue"></a><a name="queue-differences"></a> Различия между concurrent_queue и очередью

Класс будет похож на класс `concurrent_queue` `queue` . Следующие моменты иллюстрируют, где `concurrent_queue` отличия от `queue` :

- Операции постановки в очередь и выработки из очереди для `concurrent_queue` объекта являются надежными в режиме параллелизма.

- `concurrent_queue`Класс обеспечивает поддержку итератора, который не является типобезопасным.

- `concurrent_queue`Класс не предоставляет `front` `pop` методы или. `concurrent_queue`Класс заменяет эти методы, определяя метод [try_pop](reference/concurrent-queue-class.md#try_pop) .

- `concurrent_queue`Класс не предоставляет `back` метод. Таким образом, нельзя ссылаться на конец очереди.

- `concurrent_queue`Класс предоставляет [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) метод, а не `size` метод. `unsafe_size`Метод не является типобезопасным.

### <a name="concurrency-safe-operations"></a><a name="queue-safety"></a> Операции с параллелизмом

Все методы, которые помещаются в очередь или `concurrent_queue` удаляются из очереди объекта, являются типобезопасными в режиме параллелизма. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода.

В следующей таблице показаны общие `concurrent_queue` методы и операторы, которые являются типобезопасными.

:::row:::
   :::column span="":::
      [`empty`](reference/concurrent-queue-class.md#empty)
   :::column-end:::
   :::column span="":::
      [`get_allocator`](reference/concurrent-queue-class.md#get_allocator)
   :::column-end:::
   :::column span="":::
      [`push`](reference/concurrent-queue-class.md#push)
   :::column-end:::
   :::column span="":::
      [`try_pop`](reference/concurrent-queue-class.md#try_pop)
   :::column-end:::
:::row-end:::

Хотя `empty` метод является типобезопасным, параллельная операция может привести к увеличению или уменьшению очереди перед `empty` возвратом метода.

В следующей таблице показаны общие методы и операторы, которые не являются типобезопасными в режиме параллелизма.

:::row:::
   :::column span="":::
      [`clear`](reference/concurrent-queue-class.md#clear)
   :::column-end:::
   :::column span="":::
      [`unsafe_begin`](reference/concurrent-queue-class.md#unsafe_begin)
   :::column-end:::
   :::column span="":::
      [`unsafe_end`](reference/concurrent-queue-class.md#unsafe_end)
   :::column-end:::
   :::column span="":::
      [`unsafe_size`](reference/concurrent-queue-class.md#unsafe_size)
   :::column-end:::
:::row-end:::

### <a name="iterator-support"></a><a name="queue-iterators"></a> Поддержка итераторов

`concurrent_queue`Предоставляет итераторы, которые не являются надежными в режиме параллелизма. Рекомендуется использовать эти итераторы только для отладки.

`concurrent_queue`Итератор проходит по элементам только в прямом направлении. В следующей таблице показаны операторы, которые поддерживаются каждым итератором.

|Оператор|Описание|
|--------------|-----------------|
|`operator++`|Переходит к следующему элементу в очереди. Этот оператор перегружен, чтобы обеспечить семантику до и после инкремента.|
|`operator*`|Извлекает ссылку на текущий элемент.|
|`operator->`|Извлекает указатель на текущий элемент.|

\[[Top](#top)]

## <a name="concurrent_unordered_map-class"></a><a name="unordered_map"></a> Класс concurrent_unordered_map

Класс [concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) является ассоциативным классом контейнера, который, как и класс [std:: unordered_map](../../standard-library/unordered-map-class.md) , управляет последовательностью различной длины элементов типа [std::p Air \<const Key, Ty> ](../../standard-library/pair-structure.md). Неупорядоченную карту можно рассматривать как словарь, который позволяет добавить пару "ключ-значение" в или найти значение по ключу. Этот класс полезен при наличии нескольких потоков или задач, которые должны одновременно получить доступ к общему контейнеру, вставить в него или обновить его.

В следующем примере показана базовая структура для использования `concurrent_unordered_map` . В этом примере вставляются ключи символов в диапазоне ["a", "i"]. Так как порядок операций не определен, конечное значение для каждого ключа также не определено. Однако можно выполнять операции вставки параллельно.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

Пример использования `concurrent_unordered_map` для параллельного выполнения операции Map и reduce см. в разделе [как выполнять операции Map и reduce параллельно](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).

### <a name="differences-between-concurrent_unordered_map-and-unordered_map"></a><a name="map-differences"></a> Различия между concurrent_unordered_map и unordered_map

Класс будет похож на класс `concurrent_unordered_map` `unordered_map` . Следующие моменты иллюстрируют, где `concurrent_unordered_map` отличия от `unordered_map` :

- `erase`Методы, `bucket` , и `bucket_count` `bucket_size` имеют имена,, `unsafe_erase` `unsafe_bucket` `unsafe_bucket_count` и `unsafe_bucket_size` соответственно. `unsafe_`Соглашение об именовании указывает, что эти методы не являются типобезопасными. Дополнительные сведения о безопасности параллелизма см. в разделе [операции с параллелизмом](#map-safety).

- Операции INSERT не делают недействительными существующие указатели или итераторы и не изменяют порядок элементов, которые уже существуют на карте. Операции вставки и обхода могут выполняться параллельно.

- `concurrent_unordered_map` поддерживает только прямую итерацию.

- Вставка не делает недействительными или не обновляет итераторы, возвращаемые `equal_range` . Вставка может добавлять неравные элементы в конец диапазона. Итератор begin указывает на равный элемент.

Чтобы избежать взаимоблокировки, метод `concurrent_unordered_map` удерживает блокировку при вызове распределителя памяти, хэш-функций или другого определяемого пользователем кода. Кроме того, необходимо убедиться, что хэш-функция всегда вычисляет равные ключи одинаковым значением. Лучшие хэш-функции распределяют ключи равномерно через пространство хэш-кода.

### <a name="concurrency-safe-operations"></a><a name="map-safety"></a> Операции с параллелизмом

`concurrent_unordered_map`Класс позволяет выполнять операции INSERT и доступа к элементам с параллелизмом. Операции вставки не делают недействительными существующие указатели или итераторы. Операции доступа и обхода итератора также являются надежными в режиме параллелизма. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода. В следующей таблице показаны часто используемые `concurrent_unordered_map` методы и операторы, которые являются типобезопасными.

:::row:::
   :::column span="":::
      [`at`](reference/concurrent-unordered-map-class.md#at)\
      [`begin`](reference/concurrent-unordered-map-class.md#begin)\
      [`cbegin`](reference/concurrent-unordered-map-class.md#cbegin)\
      [`cend`](reference/concurrent-unordered-map-class.md#cend)
   :::column-end:::
   :::column span="":::
      [`count`](reference/concurrent-unordered-map-class.md#count)\
      [`empty`](reference/concurrent-unordered-map-class.md#empty)\
      [`end`](reference/concurrent-unordered-map-class.md#cend)\
      [`equal_range`](reference/concurrent-unordered-map-class.md#equal_range)
   :::column-end:::
   :::column span="":::
      [`find`](reference/concurrent-unordered-map-class.md#find)\
      [`get_allocator`](reference/concurrent-unordered-map-class.md#get_allocator)\
      [`hash_function`](reference/concurrent-unordered-map-class.md#hash_function)\
      [`insert`](reference/concurrent-unordered-map-class.md#insert)
   :::column-end:::
   :::column span="":::
      [`key_eq`](reference/concurrent-unordered-map-class.md#key_eq)\
      [`max_size`](reference/concurrent-unordered-map-class.md#max_size)\
      [`operator[]`](./reference/concurrent-unordered-map-class.md#operator_at)\
      [`size`](reference/concurrent-unordered-map-class.md#size)
   :::column-end:::
:::row-end:::

Хотя `count` метод может быть вызван безопасно из параллельно выполняющихся потоков, различные потоки могут получать разные результаты, если новое значение одновременно вставляется в контейнер.

В следующей таблице показаны часто используемые методы и операторы, которые не являются типобезопасными.

:::row:::
   :::column span="":::
      [`clear`](reference/concurrent-unordered-map-class.md#clear)\
      [`load_factor`](reference/concurrent-unordered-map-class.md#load_factor)
   :::column-end:::
   :::column span="":::
      [`max_load_factor`](reference/concurrent-unordered-map-class.md#max_load_factor)
   :::column-end:::
   :::column span="":::
      [`operator=`](reference/concurrent-unordered-map-class.md#operator_eq)
   :::column-end:::
   :::column span="":::
      [`rehash`](reference/concurrent-unordered-map-class.md#rehash)
   :::column-end:::
:::row-end:::

Помимо этих методов, любой метод, начинающийся с, `unsafe_` также не является типобезопасным.

[[Top](#top)]

## <a name="concurrent_unordered_multimap-class"></a><a name="unordered_multimap"></a> Класс concurrent_unordered_multimap

Класс [concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) похож на `concurrent_unordered_map` класс, за исключением того, что он позволяет сопоставлять несколько значений с одним и тем же ключом. Он также отличается от `concurrent_unordered_map` описанных ниже способов.

- Метод [concurrent_unordered_multimap:: INSERT](reference/concurrent-unordered-multimap-class.md#insert) возвращает итератор, а не `std::pair<iterator, bool>` .

- `concurrent_unordered_multimap`Класс не предоставляет `operator[]` и `at` метод.

В следующем примере показана базовая структура для использования `concurrent_unordered_multimap` . В этом примере вставляются ключи символов в диапазоне ["a", "i"]. `concurrent_unordered_multimap` позволяет ключу иметь несколько значений.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[Top](#top)]

## <a name="concurrent_unordered_set-class"></a><a name="unordered_set"></a> Класс concurrent_unordered_set

Класс [concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) похож на `concurrent_unordered_map` класс, за исключением того, что он управляет значениями вместо пар "ключ — значение". `concurrent_unordered_set`Класс не предоставляет `operator[]` и `at` метод.

В следующем примере показана базовая структура для использования `concurrent_unordered_set` . В этом примере вставляются символьные значения в диапазоне ["a", "i"]. Операции вставки можно выполнять параллельно.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[Top](#top)]

## <a name="concurrent_unordered_multiset-class"></a><a name="unordered_multiset"></a> Класс concurrent_unordered_multiset

Класс [concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) похож на `concurrent_unordered_set` класс, за исключением того, что он допускает дублирование значений. Он также отличается от `concurrent_unordered_set` описанных ниже способов.

- Метод [concurrent_unordered_multiset:: INSERT](reference/concurrent-unordered-multiset-class.md#insert) возвращает итератор, а не `std::pair<iterator, bool>` .

- `concurrent_unordered_multiset`Класс не предоставляет `operator[]` и `at` метод.

В следующем примере показана базовая структура для использования `concurrent_unordered_multiset` . В этом примере вставляются символьные значения в диапазоне ["a", "i"]. `concurrent_unordered_multiset` включает значение, которое будет встречаться несколько раз.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[Top](#top)]

## <a name="combinable-class"></a><a name="combinable"></a> Класс combinable

Класс [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) обеспечивает многократно используемое локальное хранилище потока, которое позволяет выполнять детализированные вычисления, а затем объединять эти вычисления в окончательный результат. Объект `combinable` можно рассматривать как переменную уменьшения.

`combinable`Класс полезен при наличии ресурса, совместно используемого несколькими потоками или задачами. `combinable`Класс помогает исключить общее состояние, предоставляя доступ к общим ресурсам без блокировки. Таким образом, этот класс предоставляет альтернативу использованию механизма синхронизации, например мьютекса, для синхронизации доступа к общим данным из нескольких потоков.

### <a name="methods-and-features"></a><a name="combinable-features"></a> Методы и функции

В следующей таблице показаны некоторые важные методы `combinable` класса. Дополнительные сведения обо всех `combinable` методах класса см. в разделе [класс combinable](../../parallel/concrt/reference/combinable-class.md).

|Метод|Описание|
|------------|-----------------|
|[Языковые](reference/combinable-class.md#local)|Извлекает ссылку на локальную переменную, связанную с текущим контекстом потока.|
|[открытым](reference/combinable-class.md#clear)|Удаляет все локальные переменные потока из `combinable` объекта.|
|[состоят](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|Использует предоставленную функцию combine для создания окончательного значения из набора всех локальных вычислений потока.|

`combinable`Класс является классом шаблона, параметризованным в окончательном объединенном результате. При вызове конструктора по умолчанию `T` тип параметра шаблона должен иметь конструктор по умолчанию и конструктор копии. Если `T` тип параметра шаблона не имеет конструктора по умолчанию, вызовите перегруженную версию конструктора, которая принимает в качестве параметра функцию инициализации.

Можно хранить дополнительные данные в `combinable` объекте после вызова методов [combine](reference/combinable-class.md#combine) или [combine_each](reference/combinable-class.md#combine_each) . Также можно вызывать `combine` `combine_each` методы и несколько раз. Если в объекте не изменяется локальное значение `combinable` , `combine` методы и `combine_each` выдают одинаковый результат при каждом вызове.

### <a name="examples"></a><a name="combinable-examples"></a> Примеры

Примеры использования `combinable` класса см. в следующих разделах:

- [Как использовать комбинирование для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [Как использовать комбинирование для объединения наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[Top](#top)]

## <a name="related-topics"></a>Связанные разделы

[Как использовать параллельные контейнеры для повышения эффективности](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
Показывает, как использовать параллельные контейнеры для эффективного хранения и доступа к данным в параллельном режиме.

[Как использовать комбинирование для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
Показывает, как использовать `combinable` класс для исключения общего состояния и, таким образом, повысить производительность.

[Как использовать комбинирование для объединения наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
Показывает, как использовать `combine` функцию для слияния локальных наборов данных потока.

[Библиотека параллельных шаблонов](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Описывает библиотеку PPL, которая предоставляет императивную модель программирования, которая способствует масштабируемости и простоте использования при разработке параллельных приложений.

## <a name="reference"></a>Справочник

[Класс concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)

[Класс concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)

[Класс concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[Класс concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[Класс concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[Класс concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[Класс combinable](../../parallel/concrt/reference/combinable-class.md)
