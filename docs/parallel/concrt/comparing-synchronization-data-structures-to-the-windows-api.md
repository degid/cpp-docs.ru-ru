---
title: Сравнение структур данных синхронизации с интерфейсом Windows API
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures, compared to Windows API
- event class, example
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
ms.openlocfilehash: b889570935b3a94e0cb8717c8af1783e2ce31c42
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040345"
---
# <a name="comparing-synchronization-data-structures-to-the-windows-api"></a>Сравнение структур данных синхронизации с интерфейсом Windows API

В этом разделе сравнивается поведение структур данных синхронизации, предоставляемых среда выполнения с параллелизмом, предоставляемых Windows API.

Структуры данных синхронизации, предоставляемые среда выполнения с параллелизмом, соответствуют *модели совместных потоков*. В модели совместного потокового потока примитивы синхронизации явно подают свои вычислительные ресурсы другим потокам. Это отличается от *модели потоков с вытеснением*, в которой вычислительные ресурсы передаются в другие потоки с помощью управляющего планировщика или операционной системы.

## <a name="critical_section"></a>critical_section

Класс [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) напоминает структуру Windows, `CRITICAL_SECTION` так как она может использоваться только потоками одного процесса. Дополнительные сведения о критических разделах в Windows API см. в разделе [объекты критических секций](/windows/win32/Sync/critical-section-objects).

## <a name="reader_writer_lock"></a>reader_writer_lock

Класс [concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) похож на блокировки потоков чтения/записи (SRW) Windows. В следующей таблице описаны сходства и различия.

| Компонент | Класс `reader_writer_lock` | Блокировка SRW |
|--|--|--|
| Без повторных поправ | Да | Да |
| Может повысить уровень читателя до модуля записи (поддержка обновления) | Нет | Нет |
| Может понизить уровень модуля записи до читателя (поддержка перехода на более раннюю версию) | Нет | Нет |
| Блокировка записи и настройки | Да | Нет |
| FIFO — доступ к модулям записи | Да | Нет |

Дополнительные сведения о блокировках SRW см. в разделе [упрощенные блокировки потоков чтения/записи (SRW)](/windows/win32/sync/slim-reader-writer--srw--locks) в пакете SDK платформы.

## <a name="event"></a>event

Класс [concurrency::Event](../../parallel/concrt/reference/event-class.md) напоминает неименованное событие Windows ручного сброса. Однако `event` объект ведет себя совместно, в то время как событие Windows ведет себя с вытеснением. Дополнительные сведения о событиях Windows см. в разделе [объекты событий](/windows/win32/Sync/event-objects).

## <a name="example"></a>Пример

### <a name="description"></a>Описание

Чтобы лучше понять разницу между `event` классом и событиями Windows, рассмотрим следующий пример. Этот пример позволяет планировщику создавать не более двух одновременных задач, а затем вызывает две аналогичные функции, использующие `event` класс и событие Windows ручного сброса. Каждая функция сначала создает несколько задач, которые ожидают, пока общее событие станет сигнальным. Затем каждая функция передает выполняемые задачи, а затем сигнализирует о событии. Затем каждая функция ожидает сигнала о событии.

### <a name="code"></a>Код

[!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/cpp/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]

### <a name="comments"></a>Комментарии

В этом примере выводится следующий пример выходных данных:

```Output
Cooperative event:
    Context 0: waiting on an event.
    Context 1: waiting on an event.
    Context 2: waiting on an event.
    Context 3: waiting on an event.
    Context 4: waiting on an event.
    Setting the event.
    Context 5: received the event.
    Context 6: received the event.
    Context 7: received the event.
    Context 8: received the event.
    Context 9: received the event.
Windows event:
    Context 10: waiting on an event.
    Context 11: waiting on an event.
    Setting the event.
    Context 12: received the event.
    Context 14: waiting on an event.
    Context 15: received the event.
    Context 16: waiting on an event.
    Context 17: received the event.
    Context 18: waiting on an event.
    Context 19: received the event.
    Context 13: received the event.
```

Поскольку `event` класс работает совместно, планировщик может перераспределить ресурсы обработки в другой контекст, когда событие ожидает ввода состояния оповещения. Поэтому в версии, которая использует класс, выполняется больше работы `event` . В версии, которая использует события Windows, каждая ожидающая задача должна войти в сигнальное состояние до запуска следующей задачи.

Дополнительные сведения о задачах см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="see-also"></a>См. также раздел

[Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)
