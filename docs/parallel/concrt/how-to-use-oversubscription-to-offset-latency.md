---
title: Практическое руководство. Использование лимита подписки для устранения задержек
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
ms.openlocfilehash: f5d48b68d03adc25cd5f87122591b52e37da700a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219603"
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>Практическое руководство. Использование лимита подписки для устранения задержек

Превышение лимита подписки может повысить общую эффективность некоторых приложений, содержащих задачи с большим количеством задержек. В этом разделе показано, как использовать превышение лимита подписки для смещения задержки, вызванной считыванием данных из сетевого подключения.

## <a name="example"></a>Пример

В этом примере используется [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md) для загрузки файлов с серверов HTTP. `http_reader`Класс является производным от [concurrency::Agent](../../parallel/concrt/reference/agent-class.md) и использует передачу сообщений для асинхронного чтения имен URL-адресов для загрузки.

`http_reader`Класс использует класс [concurrency::task_group](reference/task-group-class.md) для параллельного чтения каждого файла. Каждая задача вызывает метод [concurrency::Context:: resubscribe](reference/context-class.md#oversubscribe) с параметром, равным, `_BeginOversubscription` **`true`** чтобы включить превышение лимита подписки в текущем контексте. Затем каждая задача использует классы Microsoft Foundation Classes (MFC) [Цинтернетсессион](../../mfc/reference/cinternetsession-class.md) и [чттпфиле](../../mfc/reference/chttpfile-class.md) для загрузки файла. Наконец, каждая задача вызывает `Context::Oversubscribe` с параметром, равным, `_BeginOversubscription` **`false`** чтобы отключить превышение лимита подписки.

Если превышение лимита подписки включено, среда выполнения создает один дополнительный поток, в котором выполняются задачи. Каждый из этих потоков также может подписываться на текущий контекст и тем самым создавать дополнительные потоки. `http_reader`Класс использует объект [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) для ограничения количества потоков, используемых приложением. Агент инициализирует буфер фиксированным числом значений токена. Для каждой операции загрузки агент считывает значение маркера из буфера до начала операции и затем записывает это значение обратно в буфер после завершения операции. Если буфер пуст, агент ожидает, пока одна из операций скачивания не запишет значение обратно в буфер.

В следующем примере количество одновременных задач ограничивается числом доступных аппаратных потоков в два раза. Это значение является хорошей отправной точкой для использования при эксперименте с превышением лимита подписки. Можно использовать значение, соответствующее определенной среде обработки, или динамически изменить это значение, чтобы оно отвечало на фактическую рабочую нагрузку.

[!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_1.cpp)]

В этом примере на компьютере с четырьмя процессорами выводится следующий результат:

```Output
Downloading http://www.adatum.com/...
Downloading http://www.adventure-works.com/...
Downloading http://www.alpineskihouse.com/...
Downloading http://www.cpandl.com/...
Downloading http://www.cohovineyard.com/...
Downloading http://www.cohowinery.com/...
Downloading http://www.cohovineyardandwinery.com/...
Downloading http://www.contoso.com/...
Downloading http://www.consolidatedmessenger.com/...
Downloading http://www.fabrikam.com/...
Downloading http://www.fourthcoffee.com/...
Downloading http://www.graphicdesigninstitute.com/...
Downloading http://www.humongousinsurance.com/...
Downloading http://www.litwareinc.com/...
Downloading http://www.lucernepublishing.com/...
Downloading http://www.margiestravel.com/...
Downloading http://www.northwindtraders.com/...
Downloading http://www.proseware.com/...
Downloading http://www.fineartschool.net...
Downloading http://www.tailspintoys.com/...
Downloaded 1801040 bytes in 3276 ms.
```

Пример может выполняться быстрее, если превышение лимита подписки включено, так как дополнительные задачи выполняются, пока другие задачи ожидают завершения скрытой операции.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем, `download-oversubscription.cpp` а затем выполните одну из следующих команд в окне **командной строки Visual Studio** .

```cmd
cl.exe /EHsc /MD /D "_AFXDLL" download-oversubscription.cpp
cl.exe /EHsc /MT download-oversubscription.cpp
```

## <a name="robust-programming"></a>Отказоустойчивость

Всегда отключайте превышение лимита подписки, когда оно больше не требуется. Рассмотрим функцию, которая не обрабатывает исключение, вызываемое другой функцией. Если не отключить превышение лимита подписки перед возвратом функции, любая дополнительная параллельная работа также будет переписывать текущий контекст.

Для ограничения превышения лимита подписки на заданную область можно использовать шаблон " *получение ресурсов* " (RAII). В шаблоне RAII структура данных выделяется в стеке. Эта структура данных Инициализирует или получает ресурс при его создании, а также уничтожает или освобождает этот ресурс при уничтожении структуры данных. Шаблон RAII гарантирует, что деструктор вызывается до выхода из охватывающей области. Таким образом, ресурс правильно управляется при возникновении исключения или если функция содержит несколько **`return`** инструкций.

В следующем примере определяется структура с именем `scoped_blocking_signal` . Конструктор `scoped_blocking_signal` структуры включает превышение лимита подписки, а деструктор отключает превышение лимита подписки.

[!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]

В следующем примере изменяется текст `download` метода для использования RAII, чтобы гарантировать, что превышение лимита подписки отключается перед возвратом функции. Эта методика гарантирует, что `download` метод является типобезопасным.

[!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]

## <a name="see-also"></a>См. также раздел

[Контексты](../../parallel/concrt/contexts.md)<br/>
[Метод Context::Oversubscribe](reference/context-class.md#oversubscribe)
