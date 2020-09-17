---
title: Пространство имен Concurrency (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- AMP/Concurrency
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
ms.openlocfilehash: 34c3c10fa6bec2737ba78a71c282f90f284a28c2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139374"
---
# <a name="concurrency-namespace-c-amp"></a>Пространство имен Concurrency (C++ AMP)

Предоставляет классы и функции, которые ускоряют выполнение C++ кода на оборудовании, поддерживающем обработку данных. Дополнительные сведения см. в разделе [ C++ Обзор amp.](../cpp-amp-overview.md)

## <a name="syntax"></a>Синтаксис

```cpp
namespace Concurrency;
```

## <a name="members"></a>Члены

### <a name="namespaces"></a>Пространства имен

|Имя|Описание|
|----------|-----------------|
|[Пространство имен concurrency::direct3d](concurrency-direct3d-namespace.md)|Предоставляет функции, поддерживающие возможность взаимодействия с D3D. Обеспечивает эффективное использование ресурсов D3D для вычислений в коде AMP и использование ресурсов, созданных в AMP в коде D3D, без создания избыточных промежуточных копий. AMP можно использовать C++ для постепенного ускорения ресурсоемких разделов приложений DirectX и использования API D3D на основе данных, полученных от вычислений amp.|
|[Пространство имен Concurrency::fast_math](concurrency-fast-math-namespace.md)|Функции в пространстве имен `fast_math` не соответствуют C99. Предоставляются только версии с одиночной точностью каждой функции. Эти функции используют встроенные функции DirectX, которые выполняются быстрее, чем соответствующие функции в пространстве имен `precise_math` и не нуждаются в расширенной поддержке двойной точности в ускорителе, но они менее точны. Существует две версии каждой функции для совместимости на уровне источника с кодом C99. Обе версии принимают и возвращают значения с одиночной точностью.|
|[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)|Предоставляет типы и функции, предназначенные для программирования графики.|
|[Пространство имен Concurrency::precise_math](concurrency-precise-math-namespace.md)|Функции в пространстве имен `precise_math` соответствуют C99. Включаются обе версии каждой функции: с одной точностью и с двойной точностью. Эти функции, в том числе функции с одной точностью, нуждаются в расширенной поддержке двойной точности в ускорителе.|

### <a name="classes"></a>Классы

|Имя|Описание|
|----------|-----------------|
|[Класс accelerator](accelerator-class.md)|Представляет абстракцию физического оптимизированного для DP кластерного узла.|
|[Класс accelerator_view](accelerator-view-class.md)|Представляет абстракцию виртуального устройства в ускорителе C++ обработки данных amp.|
|[Класс accelerator_view_removed](accelerator-view-removed-class.md)|Исключение, возникающее при сбое базового вызова DirectX из-за механизма обнаружения и восстановления по времени ожидания Windows.|
|[Класс array](array-class.md)|Статистическое выражение данных для `accelerator_view` в домене сетки. Это коллекция переменных, по одному для каждого элемента в домене сетки. Каждая переменная содержит значение, соответствующее определенному C++ типу.|
|[Класс array_view](array-view-class.md)|Представляет представление данных в массиве\<T, N >.|
|[Класс completion_future](completion-future-class.md)|Представляет будущее, соответствующее асинхронной операции C++ amp.|
|[Класс extent](extent-class.md)|Представляет вектор из N целочисленных значений, задающих границы N-мерного пространства с источником 0. Значения в векторе координат упорядочиваются от наиболее значимых к минимально значимым. Например, при декартовой трехмерной плоскости вектор экстента (7, 5, 3) представляет пространство, в котором координата z лежит в диапазоне от 0 до 7, координаты y находятся в диапазоне от 0 до 5, а координаты x — от 0 до 3.|
|[Класс index](index-class.md)|Определяет N-мерный указатель.|
|[Класс invalid_compute_domain](invalid-compute-domain-class.md)|Исключение, возникающее, когда среда выполнения не может запустить ядро с помощью домена вычислений, указанного в `parallel_for_each`ном месте вызова.|
|[Класс out_of_memory](out-of-memory-class.md)|Исключение, возникающее при сбое метода из-за нехватки памяти системы или устройства.|
|[Класс runtime_exception](runtime-exception-class.md)|Базовый тип для исключений в библиотеке C++ amp.|
|[Класс tile_barrier](tile-barrier-class.md)|Класс возможностей, который создается только системой и передается в мозаичную `parallel_for_each` лямбда-выражение как часть параметра `tiled_index`. Он предоставляет один метод, `wait()`, цель которого — синхронизировать выполнение потоков, выполняющихся в группе потоков (плитка).|
|[Класс tiled_extent](tiled-extent-class.md)|Объект `tiled_extent` — это `extent` объект от одного до трех измерений, который разделяет пространство экстентов на одномерные, двухмерные или трехмерные плитки.|
|[Класс tiled_index](tiled-index-class.md)|Предоставляет индекс для объекта `tiled_grid`. Этот класс имеет свойства для доступа к элементу по отношению к локальному источнику плитки и относительно глобального источника.|
|[Класс uninitialized_object](uninitialized-object-class.md)|Исключение, возникающее при использовании неинициализированного объекта.|
|[Класс unsupported_feature](unsupported-feature-class.md)|Исключение, возникающее при использовании неподдерживаемой функции.|

### <a name="enumerations"></a>Перечисления

|Имя|Описание|
|----------|-----------------|
|[Перечисление access_type](concurrency-namespace-enums-amp.md#access_type)|Указывает тип доступа к данным.|
|[Перечисление queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode)|Указывает режимы работы в очереди, которые поддерживаются ускорителем.|

### <a name="operators"></a>Операторы

|Оператор|Description|
|--------------|-----------------|
|[оператор operator = = (C++ amp)](concurrency-namespace-operators-amp.md#operator_eq_eq)|Определяет, равны ли указанные структуры данных.|
|[оператор operator!= (C++ amp)](concurrency-namespace-operators-amp.md#operator_neq)|Определяет, являются ли указанные структуры данных неравными.|
|[оператор operator + (C++ amp)](concurrency-namespace-operators-amp.md#operator_add)|Вычисляет покомпонентную сумму указанных аргументов.|
|[operator-оператор (C++ amp)](concurrency-namespace-operators-amp.md#operator-)|Выполняет покомпонентное различие между заданными аргументами.|
|[оператор operator * (C++ amp)](concurrency-namespace-operators-amp.md#operator_star)|Выполняет покомпонентное произведение заданных аргументов.|
|[оператор operator или operatorC++ (amp)](concurrency-namespace-operators-amp.md#operator_div)|Выполняет покомпонентное частное от указанных аргументов.|
|[оператор% operator (C++ amp)](concurrency-namespace-operators-amp.md#operator_mod)|Выполняет вычисление остатка первого заданного аргумента по второму указанному аргументу.|

### <a name="functions"></a>Функции

|Имя|Описание|
|----------|-----------------|
|[all_memory_fence](concurrency-namespace-functions-amp.md#all_memory_fence)|Блокирует выполнение всех потоков в плитке до тех пор, пока не будут завершены все обращения к памяти.|
|[amp_uninitialize](concurrency-namespace-functions-amp.md#amp_uninitialize)|Отменяет инициализацию среды выполнения C++ amp.|
|[atomic_compare_exchange](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|Перегружен. Если значение, хранящееся в указанном месте, сравнивается со значением, равным первому заданному значению, второе указанное значение хранится в том же расположении, что и атомарная операция.|
|[atomic_exchange](concurrency-namespace-functions-amp.md#atomic_exchange)|Перегружен. Устанавливает значение, хранящееся в указанном расположении, в качестве атомарной операции.|
|[atomic_fetch_add](concurrency-namespace-functions-amp.md#atomic_fetch_add)|Перегружен. Устанавливает значение, хранящееся в указанном местоположении, равным сумме этого значения и указанному значению в виде атомарной операции.|
|[atomic_fetch_and](concurrency-namespace-functions-amp.md#atomic_fetch_and)|Перегружен. Задает значение, хранящееся в указанном расположении, в качестве побитового `and` этого значения и указанного значения в качестве атомарной операции.|
|[atomic_fetch_dec](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|Перегружен. Уменьшает значение, хранящееся в указанном месте, и сохраняет результат в том же расположении, что и атомарная операция.|
|[atomic_fetch_inc](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|Перегружен. Увеличивает значение, хранящееся в указанном месте, и сохраняет результат в том же расположении, что и атомарная операция.|
|[atomic_fetch_max](concurrency-namespace-functions-amp.md#atomic_fetch_max)|Перегружен. Устанавливает значение, хранящееся в указанном расположении, в большую часть этого значения и указанное значение как атомарная операция.|
|[atomic_fetch_min](concurrency-namespace-functions-amp.md#atomic_fetch_min)|Перегружен. Устанавливает значение, хранящееся в указанном месте, до наименьшего из этого значения и указанного значения как атомарной операции.|
|[atomic_fetch_or](concurrency-namespace-functions-amp.md#atomic_fetch_or)|Перегружен. Задает значение, хранящееся в указанном расположении, в качестве побитового `or` этого значения и указанного значения в качестве атомарной операции.|
|[atomic_fetch_sub](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|Перегружен. Устанавливает значение, хранящееся в указанном расположении, в соответствии с разностью этого значения и указанного значения в качестве атомарной операции.|
|[atomic_fetch_xor](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|Перегружен. Задает значение, хранящееся в указанном расположении, в качестве побитового `xor` этого значения и указанного значения в качестве атомарной операции.|
|[copy](concurrency-namespace-functions-amp.md#copy)|Копирует объект C++ amp. Выполнены все синхронные требования к переносу данных. Данные не могут быть скопированы, если код выполняет код в ускорителе. Общая форма этой функции — `copy(src, dest)`.|
|[copy_async](concurrency-namespace-functions-amp.md#copy_async)|Копирует объект C++ amp и возвращает [completion_future](completion-future-class.md) , которые можно ожидать. Копирование данных невозможно, если код работает на ускорителе. Общая форма этой функции — `copy(src, dest)`.|
|[direct3d_abort](concurrency-namespace-functions-amp.md#direct3d_abort)|Прерывает выполнение функции, имеющей предложение ограничения `restrict(amp)`.|
|[direct3d_errorf](concurrency-namespace-functions-amp.md#direct3d_errorf)|Выводит форматированную строку в окно **вывода** Visual Studio и вызывает исключение [runtime_exception](runtime-exception-class.md) с той же строкой форматирования.|
|[direct3d_printf](concurrency-namespace-functions-amp.md#direct3d_printf)|Выводит форматированную строку в окно **вывода** Visual Studio. Он вызывается из функции, имеющей предложение ограничения `restrict(amp)`.|
|[global_memory_fence](concurrency-namespace-functions-amp.md#global_memory_fence)|Блокирует выполнение всех потоков в плитке до тех пор, пока не будут завершены все глобальные доступы к памяти.|
|[Функция parallel_for_each (C++ amp)](concurrency-namespace-functions-amp.md#parallel_for_each)|Выполняет функцию в домене вычислений.|
|[tile_static_memory_fence](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|Блокирует выполнение всех потоков в плитке, пока не будут завершены `tile_static` доступа к памяти.|

## <a name="constants"></a>Константы

|Имя|Описание|
|----------|-----------------|
|[Константа HLSL_MAX_NUM_BUFFERS](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|Максимальное число буферов, разрешенных DirectX.|
|[Константа MODULENAME_MAX_LENGTH](concurrency-namespace-constants-amp.md#modulename_max_length)|Сохраняет максимальную длину имени модуля. Это значение должно быть одинаковым для компилятора и среды выполнения.|

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

## <a name="see-also"></a>См. также раздел

[Справочник (C++ AMP)](reference-cpp-amp.md)
