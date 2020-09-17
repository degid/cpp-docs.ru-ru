---
title: Пошаговое руководство. Создание приложения на основе агента
ms.date: 04/25/2019
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 4e67b3fc3363955ae02973847912c021eca95ded
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219486"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>Пошаговое руководство. Создание приложения на основе агента

В этом разделе описывается создание базового приложения на основе агента. В этом пошаговом руководстве можно создать агент, который асинхронно считывает данные из текстового файла. Приложение использует алгоритм контрольной суммы Адлер-32 для вычисления контрольной суммы содержимого этого файла.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения этого пошагового руководства необходимо ознакомиться со следующими разделами.

- [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

- [Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)

## <a name="sections"></a><a name="top"></a>Священ

В этом пошаговом руководстве показано, как выполнять следующие задачи:

- [Создание консольного приложения](#createapplication)

- [Создание класса file_reader](#createagentclass)

- [Использование класса file_reader в приложении](#useagentclass)

## <a name="creating-the-console-application"></a><a name="createapplication"></a>Создание консольного приложения

В этом разделе показано, как создать консольное приложение C++, которое ссылается на файлы заголовков, которые будут использоваться программой. Начальные шаги зависят от используемой версии Visual Studio. Чтобы ознакомиться с документацией по предпочтительной версии Visual Studio, используйте селектор **Версия**. Он находится в верхней части оглавления на этой странице.

::: moniker range="vs-2019"

### <a name="to-create-a-c-console-application-in-visual-studio-2019"></a>Создание консольного приложения C++ в Visual Studio 2019

1. В главном меню выберите **Файл ** > **Создать ** > **Проект**, чтобы открыть диалоговое окно **Создание проекта**.

1. В верхней части диалогового окна для параметра **Язык** выберите значение **C++** , для параметра **Платформа** — значение **Windows**, а для параметра **Тип проекта** — значение **Консоль**.

1. В отфильтрованном списке типов проектов щелкните **Консольное приложение**, а затем нажмите кнопку **Далее**. На следующей странице введите в `BasicAgent` качестве имени проекта и при необходимости укажите расположение проекта.

1. Нажмите кнопку **Создать**, чтобы создать проект.

1. Щелкните правой кнопкой мыши узел проекта в **Обозреватель решений**и выберите пункт **свойства**. В разделе **Свойства конфигурации**  >  **C/C++**  >  **Предкомпилированные заголовки предварительно**скомпилированный  >  **заголовок** выберите **создать**.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-c-console-application-in-visual-studio-2017-and-earlier"></a>Создание консольного приложения C++ в Visual Studio 2017 и более ранних версий

1. В меню **файл** выберите пункт **создать**и нажмите кнопку **проект** , чтобы открыть диалоговое окно **Новый проект** .

1. В диалоговом окне **Новый проект** выберите узел **Visual C++** на панели **типы проектов** , а затем в области **шаблоны** выберите **консольное приложение Win32** . Введите имя проекта, например, `BasicAgent` и нажмите кнопку **ОК** , чтобы открыть **Мастер консольного приложения Win32**.

1. В диалоговом окне **Мастер консольных приложений Win32** нажмите кнопку **Готово**.

::: moniker-end

1. В файле *PCH.h* (*stdafx.h* в Visual Studio 2017 и более ранних версиях) добавьте следующий код:

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   Файл заголовка agents.h содержит функциональные возможности класса [concurrency::Agent](../../parallel/concrt/reference/agent-class.md) .

1. Убедитесь, что приложение успешно создано путем его сборки и запуска. Чтобы выполнить сборку приложения, в меню **Сборка** выберите пункт **построить решение**. Если приложение успешно строится, запустите его, выбрав команду **начать отладку** в меню **Отладка** .

[[Top](#top)]

## <a name="creating-the-file_reader-class"></a><a name="createagentclass"></a>Создание класса file_reader

В этом разделе показано, как создать `file_reader` класс. Среда выполнения планирует каждому агенту выполнять работу в собственном контексте. Таким образом, можно создать агент, который выполняет работу синхронно, но взаимодействует с другими компонентами асинхронно. `file_reader`Класс считывает данные из заданного входного файла и отправляет данные из этого файла в заданный целевой компонент.

#### <a name="to-create-the-file_reader-class"></a>Создание класса file_reader

1. Добавьте в проект новый файл заголовка C++. Для этого щелкните правой кнопкой мыши узел **файлы заголовков** в **Обозреватель решений**, выберите команду **Добавить**, а затем щелкните **новый элемент**. В области **шаблоны** выберите **заголовочный файл (.h)**. В диалоговом окне **Добавление нового элемента** введите `file_reader.h` в поле **имя** и нажмите кнопку **Добавить**.

1. В file_reader.h добавьте следующий код.

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. В file_reader.h создайте класс с именем `file_reader` , производным от `agent` .

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. Добавьте следующие члены данных в **`private`** раздел класса.

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   `_file_name`Элемент — это имя файла, из которого агент считывает данные. `_target`Элемент является объектом [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) , в который агент записывает содержимое файла. `_error`Элемент содержит все ошибки, происходящие во время существования агента.

1. Добавьте следующий код для `file_reader` конструкторов в **`public`** раздел `file_reader` класса.

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   Каждая перегрузка конструктора задает `file_reader` элементы данных. Вторая и третья перегрузки конструктора позволяют приложению использовать определенный планировщик с агентом. Первая перегрузка использует планировщик по умолчанию с агентом.

1. Добавьте `get_error` метод в общедоступный раздел `file_reader` класса.

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   `get_error`Метод извлекает все ошибки, происходящие в течение жизненного цикла агента.

1. Реализуйте метод [concurrency::Agent:: Run](reference/agent-class.md#run) в **`protected`** разделе класса.

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]

`run`Метод открывает файл и считывает из него данные. `run`Метод использует обработку исключений для захвата всех ошибок, происходящих во время обработки файла.

   Каждый раз, когда этот метод считывает данные из файла, он вызывает функцию [concurrency::asend](reference/concurrency-namespace-functions.md#asend) для отправки этих данных в целевой буфер. Он отправляет пустую строку в целевой буфер для указания на окончание обработки.

В следующем примере показано полное содержимое файла file_reader.h.

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

[[Top](#top)]

## <a name="using-the-file_reader-class-in-the-application"></a><a name="useagentclass"></a>Использование класса file_reader в приложении

В этом разделе показано, как использовать `file_reader` класс для чтения содержимого текстового файла. Также показано, как создать объект [concurrency::Call](../../parallel/concrt/reference/call-class.md) , который получает данные файла и вычисляет свою контрольную сумму адлер-32.

#### <a name="to-use-the-file_reader-class-in-your-application"></a>Использование класса file_reader в приложении

1. В Басикажент. cpp добавьте следующую `#include` инструкцию.

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. В Басикажент. cpp добавьте следующие **`using`** директивы.

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. В `_tmain` функции создайте объект [concurrency::Event](../../parallel/concrt/reference/event-class.md) , который сигнализирует об окончании обработки.

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. Создайте `call` объект, который обновляет контрольную сумму при получении данных.

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   Этот `call` объект также задает `event` объект при получении пустой строки для сигнализации об окончании обработки.

1. Создайте `file_reader` объект, который считывает данные из файла test.txt и записывает содержимое этого файла в `call` объект.

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. Запустите агент и дождитесь его завершения.

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. Дождитесь `call` получения объектом всех данных и завершите его работу.

[!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]

1. Проверьте модуль чтения файлов на наличие ошибок. Если ошибка не возникла, вычислите итоговую сумму Адлер-32 и распечатайте сумму на консоли.

[!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]

В следующем примере показан полный файл Басикажент. cpp.

[!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]

[[Top](#top)]

## <a name="sample-input"></a>Пример ввода

Это образец содержимого входного файла text.txt:

```Output
The quick brown fox
jumps
over the lazy dog
```

## <a name="sample-output"></a>Пример выходных данных

При использовании с образцом входных данных эта программа создает следующие выходные данные:

```Output
Adler-32 sum is fefb0d75
```

## <a name="robust-programming"></a>Отказоустойчивость

Чтобы предотвратить одновременный доступ к элементам данных, рекомендуется добавить методы, выполняющие работу, в **`protected`** раздел или **`private`** класса. Добавляйте только методы, которые отправляют или получают сообщения от агента в **`public`** раздел класса.

Всегда вызывайте [concurrency::Agent::d один](reference/agent-class.md#done) метод для перемещения агента в состояние завершения. Этот метод обычно вызывается перед возвратом из `run` метода.

## <a name="next-steps"></a>Next Steps

Еще один пример приложения на основе агента см. в разделе [Пошаговое руководство. использование Join для предотвращения взаимоблокировок](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).

## <a name="see-also"></a>См. также раздел

[библиотеку асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)<br/>
[Пошаговое руководство. использование Join для предотвращения взаимоблокировок](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)
